# angular-electron-sqlite-project

1. download and install nodejs binaries from nodejs.org for your operating system and 

2. check nodejs installed
	node -v

3. check node package manager installed
	npm -v

4. install githubs package electronjs globally
	npm install electron -g

5. check electronjs installed
	electron -v

6. install angular-cli globally
	npm install -g @angular/cli

7. check angular-cli installed
	ng -v

8. create new angular project call-register
	ng new call-register

9. cd call-register

10. code .

11. check the angular app working fine in browser @ localhost:4200
	ng serve 

12. goto electron quick-start app @ https://electronjs.org/docs/tutorial/first-app and copy the last main.js example code

13. Now merge the angular as well as electron each other by creating a new file main.js in apps root and paste the copied code. modify the following as is
	pathname: path.join(__dirname, 'dist/index.html'),

14. goto the package.json add "main": "main.js" 

15. goto src/app/index.html
	<base href="/">
	to
	<base href="./">

16. goto the package.json and add the following
	"exe": "ng build && electron .

17. now run following 
	npm run exe

18. enable electron api under angular
	npm install ngx-electron --save

19. import the ngx-electron in src/app/app.module.ts
	import { NgxElectronModule } from 'ngx-electron';

20. import the ngx-electron in src/app/app.component.ts
	import { ElectronService } from 'ngx-electron';
	pass args in private _electronService: ElectronService
	construct( private _electronService: ElectronService )

21. if u encounter the following error
	error TS2307: Cannot find module 'electron'.
	error TS2503: Cannot find namespace 'NodeJS'.

22. run the following command
	npm install ngx-fs --save

23. execute eject 
	ng eject

24. then
	npm install

25. modify the webpack.config.js module.exports object
	"target": "electron-renderer",

26. now the following command runs successfully
	npm run exe

27. install sqlite-sync package @ https://www.npmjs.com/package/sqlite-sync
	npm install sqlite-sync --save

28. now create the new service implement the sqlite db conn as suggested
	ng g s services/user

29. import the service in app component 
	import { UserService } from "./services/user.service";
	var obj = new UserService();
    console.log(obj);
