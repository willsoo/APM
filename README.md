# APM
# This Python file is to gather all APM input, then run APM 
import os
import shutil

# open AMP input file(write only)
fw = open ('d:/users/91223/APMauto/ACMS.txt','w')

# change APM running dir to this
os.chdir ('D:/users/91223/APMauto')

# copy all files from one dir to another dir
# APM input source dir
src = 'C:/users/91223/crzRpt/747'
# APM input destination dir
dest = 'D:/users/91223/APMauto/crzRpt'
src_files = os.listdir(src) 
for file_name in src_files:
    if file_name.endswith ('.TXT'):
# append path to file_name
        full_file_name = os.path.join(src, file_name)
        if (os.path.isfile(full_file_name)):
# open fr as read only
            fr = open (full_file_name,'r') 
# read full content of fr and return as crzInfo
            crzInfo = fr.read()
# write full content of crzInfo on fw
            fw.write (crzInfo) 
            fr.close()
# close APM input file
fw.close()
# execute APM
os.system ('APM.exe')
