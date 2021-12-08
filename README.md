# ionic5--common-commands

1. Create ionic project
-> ionic start myApp blank

2. Create ionic Page
-> ionic generate page pages/page1

3.  navigate to another page:
Html:
  <button ion-button icon-only (click) ="addItem()"  >
Typescript:
  addItem(){
    this.router.navigate(['/add'])
  }

OR

 <ion-button routerlink= "/page2">Next Page</ion-button>


4. Create service (for logical handling)
-> ionic generate service api/user -> create in api folder if want to


5. Forms
-------------------------
Html:  <input type="text" [(ngModel)]="favoriteColor"
ts File:
	---------------------------
	
 	 favoriteColor = '';

6. Passing data to next page

	a.Html: set (click)= "methodName(objectProperty1, objProperty2)"
	b. set router.navigate(['path'], objProperty1, objProperty2)
	c. app routing
	set destination-page/:id/:age and  destination page path

7. Get route data from previous age

	ts file of next page-> private route: ActivatedRoute
	var1 = this.router.snapshot.params['objPropert1']

8. loop items and displaying them
	 -> use *ngFor="let item of itemsArr"

9. Building Ionics into apk:

	What to do after downloading any capacitor package?
	1. run ionic build

	Android Permissions
	1. Download android package folder:
	ionic cap add android
	2. go to AndroidManifest.xml in app ->src->main->AndroidManifest.xml
	3. add into permissions section:
	<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
	<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />

	PWA Permissions
	1. download:
	npm install @ionic/pwa-elements
	2. import into main.ts(src->main.ts):
	import {defineCustomElements} from '@ionic/pwa-elements/loader'
	3. add statement:
	defineCustomElements(window)

	Opening in Android Emulator witout android studio:
	everytime you perfom ionic build
	ionic cap copy

	sync your ionic code with native code( code that runs on android/ios)
	ionic cap sync

	open ionic project(transformed into native in android studio)
	ionic cap open android
	*This will take very long time have to wait
	press play after that

10. using camera:
