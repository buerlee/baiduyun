# baiduyun
针对 百度云 净网行动
# -*- coding: utf-8 -*-

import hashlib
import shutil
import os
from os import walk
from os import listdir


def get_filepaths(directory):
    file_paths = []  # List which will store all of the full filepaths.

    for root, directories, files in os.walk(directory):
        for filename in files:
            filepath = os.path.join(root, filename)
            extension = os.path.splitext(filename)[1][1:]
            if extension in ("jpg", "png", "torrent"):
                os.remove(filepath)
            else:
                file_paths.append(filepath)  # Add it to the list.

    return file_paths  

dir = "D://xunleidown//private" // your dir 
new_file_name = []

files = get_filepaths(dir)

for file in files:
    filename, file_extension = os.path.splitext(file)
    new_file_name = filename + "bak" + file_extension

    with open(file, "a") as testFile:
        testFile.write("ah")

print "done"
