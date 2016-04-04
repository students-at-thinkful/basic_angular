# basic_angular

```
<script type="text/javascript" src="../../files/angular.min.js"></script>
<script>
var demo = angular.module("demo", [],
  function($interpolateProvider) {
    $interpolateProvider.startSymbol('[!');
    $interpolateProvider.endSymbol('!]');
}) ///

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

</script>
</head>
```
