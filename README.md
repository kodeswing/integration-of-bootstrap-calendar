# integration-of-bootstrap-calendar

**Step 1: Create index.html**

**Step 2: Add AngualrJS CDN**

````<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.7/angular.min.js"></script>````

**Step 3: Add bootstrap (CSS only)**

````bower install bootstrap````

````<link rel="stylesheet" type="text/css" href="bower_components/bootstrap/dist/css/bootstrap.min.css">````

**Step 4: Add moment.js**

````bower install moment````

````<script type="text/javascript" src="bower_components/moment/min/moment.min.js"></script>````

**Step 5: Add angular-ui-bootstrap**

````npm install angular-ui-bootstrap````

````<link rel="stylesheet" type="text/css" href="node_modules/angular-ui-bootstrap/dist/ui-bootstrap-csp.css">````

````<script type="text/javascript" src="node_modules/angular-ui-bootstrap/dist/ui-bootstrap-tpls.js"></script>````


**Step 6: Add angular-bootstrap-calendar**

````npm install angular-bootstrap-calendar````

````<link href="bower_components/angular-bootstrap-calendar/dist/css/angular-bootstrap-calendar.min.css" rel="stylesheet">````

````<script src="bower_components/angular-bootstrap-calendar/dist/js/angular-bootstrap-calendar-tpls.min.js"></script>````

**Step 7: Add ng-app directive in body tag & setup angularjs module for this app**

````
<body ng-app="myApp">
.....

<script type="text/javascript">
  angular.module('myApp',[]);
</script>
</body>
````

**Step 8: Add dependencies to angular module**

````
<script type="text/javascript">
  angular.module('myApp',['mwl.calendar', 'ui.bootstrap']);
</script>

````

**Step 9: Add HTML snippet for calendar**

````

<mwl-calendar
    view="calendarView"
    view-date="calendarDate"
    events="events"
    view-title="calendarTitle"
    on-event-click="eventClicked(calendarEvent)"
    on-event-times-changed="calendarEvent.startsAt = calendarNewEventStart; calendarEvent.endsAt = calendarNewEventEnd"
    edit-event-html="'<i class=\'glyphicon glyphicon-pencil\'></i>'"
    delete-event-html="'<i class=\'glyphicon glyphicon-remove\'></i>'"
    on-edit-event-click="eventEdited(calendarEvent)"
    on-delete-event-click="eventDeleted(calendarEvent)"
    cell-is-open="true">
</mwl-calendar>

````
**Step 10: Setup angularjs controller**

````
<div ng-controller="calCtrl">
<mwl-calendar
    view="calendarView"
    view-date="calendarDate"
    events="events"
    view-title="calendarTitle"
    on-event-click="eventClicked(calendarEvent)"
    on-event-times-changed="calendarEvent.startsAt = calendarNewEventStart; calendarEvent.endsAt = calendarNewEventEnd"
    edit-event-html="'<i class=\'glyphicon glyphicon-pencil\'></i>'"
    delete-event-html="'<i class=\'glyphicon glyphicon-remove\'></i>'"
    on-edit-event-click="eventEdited(calendarEvent)"
    on-delete-event-click="eventDeleted(calendarEvent)"
    cell-is-open="true">
</mwl-calendar>
</div>
..........
..........




<script type="text/javascript">
angular.module('myApp',['mwl.calendar', 'ui.bootstrap'])
		.controller('calCtrl',function($scope){

			$scope.message = "Hello World from Angular!";
			$scope.calendarView = 'month';
			$scope.calendarDate = new Date();
		});
</script>
````

**That's all. You should see calendar in browser when you run index.html.**

