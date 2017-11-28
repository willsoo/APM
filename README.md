# APM
# This Python file is to gather all APM input, then run APM 
import os
import shutil

fw = open ('d:/users/91223/APMauto/ACMS.txt','w') # open AMP input file(write only)

os.chdir ('D:/users/91223/APMauto') #change APM running dir to this

# copy all files from one dir to another dir
src = 'C:/users/91223/crzRpt/747' # APM input source dir
dest = 'D:/users/91223/APMauto/crzRpt' # APM input destination dir
src_files = os.listdir(src) 
for file_name in src_files:
    if file_name.endswith ('.TXT'):
        full_file_name = os.path.join(src, file_name) # append path to file_name
        if (os.path.isfile(full_file_name)):
            fr = open (full_file_name,'r') # open fr as read only
            crzInfo = fr.read() # read full content of fr and return as crzInfo
            fw.write (crzInfo) # write full content of crzInfo on fw
            fr.close()
fw.close() # close APM input file
os.system ('APM.exe') #execute APM
