#Music_Genre_Classification

Use machine learning, python automatically classify music to its genre, a project of my machine learning class.


### Dataset

GTZAN Dataset : <http://marsyasweb.appspot.com/download/data_sets/>


Developed Test Set : <https://github.com/KrisYu/Muisc_Genre_Classification/tree/master/DevelopedTestSet>

In addtion, I collected 4 * 20 songs from Free Music Archive <http://freemusicarchive.org> , then apply some formats changes, make Developed Test Set.


### Pre-process 

##### SOX

The GTZAN Dataset is in AU format, you need SOX to change it to wav:

<https://github.com/JoFrhwld/FAVE/wiki/SoX-on-OS-X>

##### batch music format changes

Use Python to write bash file :


```
filepath = 'to deal path'

file_list = []
for root,dirs,files in os.walk(filepath):
	for file in files:
		file_list.append(file)


cmds = []
for file in file_list:
	newf = file.replace('au','wav')
	cmd = 'sox ' + file + ' '+ newf
	cmds.append(cmd)


f = open('copy.sh','w')
for cmd in cmds:
	f.write(cmd+'\n')
f.close()

```

Execute it in Terminal


```
chmod 755 copy.sh
./copy.sh
```




### Learning Phase

### Applying Phase

see my 