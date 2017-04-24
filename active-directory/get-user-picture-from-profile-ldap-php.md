Images are stored in LDAP profile base64 encoded.

> $tempFile = tempnam(sys_get_temp_dir(), 'image');
file_put_contents($tempFile, $imageString);
$finfo = new finfo(FILEINFO_MIME_TYPE);
$mime  = explode(';', $finfo->file($tempFile));
echo '<img src="data:' . $mime[0] . ';base64,' . base64_encode($imageString) . '"/>';

Alternate solution:


> <?php
    $result = ldap_search($ad , $dn , $filter, $attributes);
    $aduser = ldap_get_attributes($ad, ldap_first_entry($ad,$result));
?>