#!/bin/bash -x 
#week4scripts
title="Week4scripts"
RIGHT_NOW=$(date +"%x %r %z")
TIME_STAMP="updated on $RIGHT_NOW by $USER"
#### Functions
drive_space ()
{
echo "<h3>Filesystem Sace</h3>"
echo"<pre>"
df
echo"</pre>"
}
SWAP_File ()
{
echo "<h3>SwapFile space allocation</h2>"
echo "<pre>"
dd if=/dev/zero of=cache1 bs=1024k count=30
echo "</pre>"
}
cat <<- _EOF_
	<html>
	<head>
		<title>
		$title
		</title>
	</head>

	<body>
	<p>$TIME_STAMP</p>
	$(SWAP_File)
	$(drive_space)
</body>
</html>
_EOF_
