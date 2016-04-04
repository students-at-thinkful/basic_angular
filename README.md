# basic_angular

#### File
```
<script type="text/javascript" src="../../files/angular.min.js"></script>
```

#### Module
```
var demo = angular.module("demo", [],
  function($interpolateProvider) {
    $interpolateProvider.startSymbol('[!');
    $interpolateProvider.endSymbol('!]');
}) ///
```

#### Controller [( view )](https://github.com/students-at-thinkful/angular_page_controller)
```
demo.controller('Ctrl', function($scope, $http) {
  $scope.huDisplay = 'on';

  $scope.items = [];
  
  $http({ method: 'GET', url: '../../list/entries' })
  .success(function(data, status) { $scope.items = data; console.log(data); });
  
  $scope.delete = function(data_id) {
    if (confirm("Delete This Entry?") == true) {
      $http({ method: 'GET', url: '../../delete/data?' + data_id})
        .success(function(data, status) { $scope.items = data; console.log(data); });
    }
};

}) ///
```
