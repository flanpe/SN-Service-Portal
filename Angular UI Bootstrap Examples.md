# Advanced Angular UI Bootstrap Components Example
## Widget
### HTML
```html
<div class="panel panel-default">
  <div class="panel-heading text-center">
    <h3>Advanced Angular UI Bootstrap Components Example</h3>
  </div>
  <div class="panel-body">

    <!-- Modal Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Modal</h4>
        <p>A modal dialog example that pulls details from the incident table.</p>
      </div>
      <button class="btn btn-primary" ng-click="c.openIncidentModal()">Open Incident Modal</button>
    </div>
    <!-- Modal Example End -->

    <hr>

    <!-- Tooltip Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Tooltip</h4>
        <p>Hover over the button to see the tooltip. The tooltip content is dynamic based on incident data.</p>
      </div>
      <button class="btn btn-info" uib-tooltip="{{c.incidentTooltip}}" tooltip-placement="top">Hover me!</button>
    </div>
    <!-- Tooltip Example End -->

    <hr>

    <!-- Popover Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Popover</h4>
        <p>Click the button to see a popover with dynamic content from the incident table.</p>
      </div>
      <button class="btn btn-warning" uib-popover="{{c.incidentPopover}}" popover-placement="right" popover-title="Incident Info">Click me!</button>
    </div>
    <!-- Popover Example End -->

    <hr>

    <!-- Accordion Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Accordion</h4>
        <p>An accordion displaying a list of recent incidents.</p>
      </div>
      <uib-accordion>
        <uib-accordion-group heading="Recent Incidents" ng-repeat="incident in c.incidents">
          <p><strong>Number:</strong> {{incident.number}}</p>
          <p><strong>Short Description:</strong> {{incident.short_description}}</p>
        </uib-accordion-group>
      </uib-accordion>
    </div>
    <!-- Accordion Example End -->

    <hr>

    <!-- Accordion with Nested Content Example Start -->
    <div class="example-section">
      <div class="example-description">
        <h4>Accordion with Nested Content</h4>
        <p>An accordion that contains nested content such as sub-lists or additional details.</p>
      </div>
      <uib-accordion close-others="true">
        <uib-accordion-group heading="Main Section 1">
          <p>This is some main content.</p>
          <uib-accordion close-others="false">
            <uib-accordion-group heading="Nested Section 1.1">
              <p>Nested content 1.1</p>
            </uib-accordion-group>
            <uib-accordion-group heading="Nested Section 1.2">
              <p>Nested content 1.2</p>
            </uib-accordion-group>
          </uib-accordion>
        </uib-accordion-group>
        <uib-accordion-group heading="Main Section 2">
          <p>This is another main content section.</p>
        </uib-accordion-group>
      </uib-accordion>
    </div>
    <!-- Accordion with Nested Content Example End -->

    <hr>

    <!-- Alert Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Alert</h4>
        <p>An alert that shows an incident's priority level. This alert is dynamically generated based on incident data.</p>
      </div>
      <uib-alert type="{{c.incidentAlertType}}" close="c.closeAlert()">Incident Priority: {{c.incidentPriority}}</uib-alert>
    </div>
    <!-- Alert Example End -->

    <hr>

    <!-- Buttons Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Buttons</h4>
        <p>Toggle buttons to filter incidents by priority.</p>
      </div>
      <label class="btn btn-primary" ng-model="c.filterPriority" uib-btn-radio="'1'">Priority 1</label>
      <label class="btn btn-info" ng-model="c.filterPriority" uib-btn-radio="'2'">Priority 2</label>
      <label class="btn btn-warning" ng-model="c.filterPriority" uib-btn-radio="'3'">Priority 3</label>
    </div>
    <!-- Buttons Example End -->

    <hr>

    <!-- Carousel Example Start -->
    <div class="example-section">
      <div class="example-description">
        <h4>Carousel</h4>
        <p>A carousel displaying example images.</p>
      </div>
      <div class="carousel-container text-center">
        <uib-carousel interval="5000" active="c.activeSlide" no-wrap="false">
          <uib-slide ng-repeat="slide in c.exampleSlides" index="slide.id">
            <div class="carousel-content">
              <img ng-src="{{slide.image}}" alt="{{slide.text}}" class="img-responsive" style="width: 100%; max-height: 300px; object-fit: cover;">
              <div class="carousel-caption">
                <h4>{{slide.text}}</h4>
              </div>
            </div>
          </uib-slide>
        </uib-carousel>
      </div>
    </div>
    <!-- Carousel Example End -->

    <hr>

    <!-- Collapse Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Collapse</h4>
        <p>Click to toggle visibility of the incident's description.</p>
      </div>
      <button class="btn btn-default" ng-click="c.isCollapsed = !c.isCollapsed">Toggle Description</button>
      <div uib-collapse="c.isCollapsed">
        <div class="well well-lg">{{c.incidentDescription}}</div>
      </div>
    </div>
    <!-- Collapse Example End -->

    <hr>

    <!-- Datepicker Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Datepicker</h4>
        <p>Select a date to filter incidents by creation date.</p>
      </div>
      <uib-datepicker ng-model="c.selectedDate" ng-change="c.filterByDate()"></uib-datepicker>
    </div>
    <!-- Datepicker Example End -->

    <hr>

    <!-- Dropdown Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Dropdown</h4>
        <p>A dropdown menu to select incident categories.</p>
      </div>
      <div uib-dropdown>
        <button id="single-button" type="button" class="btn btn-primary" uib-dropdown-toggle>
          Select Category <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" uib-dropdown-menu role="menu" aria-labelledby="single-button">
          <li role="menuitem" ng-repeat="category in c.categories"><a href="javascript:void(0)" ng-click="c.selectCategory(category)">{{category}}</a></li>
        </ul>
      </div>
    </div>
    <!-- Dropdown Example End -->

    <hr>

    <!-- Pagination Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Pagination</h4>
        <p>Pagination control for navigating through incident records.</p>
      </div>
      <uib-pagination total-items="c.totalIncidents" ng-model="c.currentPage" max-size="5" boundary-links="true" ng-change="c.pageChanged()"></uib-pagination>
    </div>
    <!-- Pagination Example End -->

    <hr>

    <!-- Progressbar Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Progressbar</h4>
        <p>A progress bar showing the completion percentage of resolved incidents.</p>
      </div>
      <uib-progressbar max="100" value="c.resolutionProgress">{{c.resolutionProgress}}% Resolved</uib-progressbar>
    </div>
    <!-- Progressbar Example End -->

    <hr>

    <!-- Rating Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Rating</h4>
        <p>Rate the quality of an incident's resolution.</p>
      </div>
      <uib-rating ng-model="c.incidentRating" max="5" ng-change="c.saveRating()"></uib-rating>
    </div>
    <!-- Rating Example End -->

    <hr>

    <!-- Tabs Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Tabs</h4>
        <p>A tabbed interface for different incident views.</p>
      </div>
      <uib-tabset>
        <uib-tab heading="Open Incidents">
          <ul>
            <li ng-repeat="incident in c.openIncidents">{{incident.number}} - {{incident.short_description}}</li>
          </ul>
        </uib-tab>
        <uib-tab heading="Resolved Incidents">
          <ul>
            <li ng-repeat="incident in c.resolvedIncidents">{{incident.number}} - {{incident.short_description}}</li>
          </ul>
        </uib-tab>
      </uib-tabset>
    </div>
    <!-- Tabs Example End -->

    <hr>

    <!-- Timepicker Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Timepicker</h4>
        <p>Select a time to set a reminder for an incident follow-up.</p>
      </div>
      <uib-timepicker ng-model="c.followUpTime"></uib-timepicker>
    </div>
    <!-- Timepicker Example End -->

    <hr>

    <!-- Typeahead Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Typeahead</h4>
        <p>An input with autocomplete for incident numbers.</p>
      </div>
      <input type="text" ng-model="c.selectedIncident" uib-typeahead="incident.number for incident in c.incidents | filter:$viewValue | limitTo:8" class="form-control" ng-blur="c.loadIncidentDetails(c.selectedIncident)">
    </div>
    <!-- Typeahead Example End -->
    
    <hr>

    <!-- Modal with Form Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Modal with Form</h4>
        <p>A modal dialog that includes a form for user input.</p>
      </div>
      <button class="btn btn-success" ng-click="c.openFormModal()">Open Form Modal</button>
    </div>
    <!-- Modal with Form Example End -->

    <hr>

    <!-- Tooltip with HTML Content Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Tooltip with HTML</h4>
        <p>A tooltip that displays rich HTML content.</p>
      </div>
      <button class="btn btn-info" uib-tooltip-html="c.htmlTooltipContent" tooltip-placement="top">Hover me!</button>
    </div>
    <!-- Tooltip with HTML Content Example End -->

    <hr>

    <!-- Multi-select Dropdown Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Multi-select Dropdown</h4>
        <p>A dropdown menu that allows multiple selections.</p>
      </div>
      <div uib-dropdown>
        <button id="multi-select-button" type="button" class="btn btn-primary" uib-dropdown-toggle>
          Select Options <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" uib-dropdown-menu role="menu" aria-labelledby="multi-select-button">
          <li role="menuitem" ng-repeat="option in c.multiSelectOptions">
            <input type="checkbox" ng-model="option.selected"> {{option.label}}
          </li>
        </ul>
      </div>
    </div>
    <!-- Multi-select Dropdown Example End -->

    <hr>

    <!-- Popover with Dynamic Content Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Popover with Dynamic Content</h4>
        <p>A popover that loads dynamic content.</p>
      </div>
      <button class="btn btn-warning" uib-popover-template="c.dynamicPopoverTemplateUrl" popover-title="Dynamic Content" popover-trigger="mouseenter">Hover me!</button>
    </div>
    <!-- Popover with Dynamic Content Example End -->

    <hr>

    <!-- Advanced Pagination with Filters Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Advanced Pagination</h4>
        <p>Pagination combined with filters to navigate and filter content.</p>
      </div>

      <div class="filter-section">
        <label for="filterInput">Filter by Short Description:</label>
        <input type="text" id="filterInput" class="form-control" ng-model="c.searchFilter" ng-change="c.applyFilter()">
      </div>

      <uib-pagination total-items="c.filteredItems.length" ng-model="c.currentPage" max-size="5" items-per-page="c.itemsPerPage" boundary-links="true" ng-change="c.updatePage()"></uib-pagination>

      <ul class="list-group">
        <li class="list-group-item" ng-repeat="item in c.paginatedItems">
          <strong>{{item.number}}:</strong> {{item.short_description}}
        </li>
      </ul>
    </div>
    <!-- Advanced Pagination with Filters Example End -->

    <hr>

    <!-- File Upload with Progress Bar Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>File Upload with Progress Bar</h4>
        <p>Upload a file and see the upload progress.</p>
      </div>
      <input type="file" ng-model="c.file" onchange="angular.element(this).scope().c.uploadFile(this.files)">
      <uib-progressbar max="100" value="c.uploadProgress" type="info" class="progress-striped active">{{c.uploadProgress}}%</uib-progressbar>
    </div>
    <!-- File Upload with Progress Bar Example End -->

    <hr>

    <!-- Sortable and Filterable Table Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Sortable and Filterable Table</h4>
        <p>Sort and filter table columns dynamically.</p>
      </div>
      <input type="text" ng-model="c.tableFilter" placeholder="Filter by short description" class="form-control">
      <table class="table table-striped">
        <thead>
          <tr>
            <th ng-click="c.sortBy('number')">Number <span ng-if="c.sortField == 'number'">{{c.sortReverse ? '▼' : '▲'}}</span></th>
            <th ng-click="c.sortBy('short_description')">Short Description <span ng-if="c.sortField == 'short_description'">{{c.sortReverse ? '▼' : '▲'}}</span></th>
          </tr>
        </thead>
        <tbody>
          <tr ng-repeat="item in c.filteredItems | filter:c.tableFilter | orderBy:c.sortField:c.sortReverse">
            <td>{{item.number}}</td>
            <td>{{item.short_description}}</td>
          </tr>
        </tbody>
      </table>
    </div>
    <!-- Sortable and Filterable Table Example End -->

    <hr>

    <!-- Tabs with Dynamic Content Example Start -->
    <div class="example-section text-center">
      <div class="example-description">
        <h4>Tabs with Dynamic Content</h4>
        <p>Tabs that load content dynamically based on the selected tab.</p>
      </div>
      <uib-tabset active="c.activeTab">
        <uib-tab heading="Open Incidents" select="c.loadTabContent('open')">
          <ul>
            <li ng-repeat="incident in c.tabContent">{{incident.number}} - {{incident.short_description}}</li>
          </ul>
        </uib-tab>
        <uib-tab heading="Resolved Incidents" select="c.loadTabContent('resolved')">
          <ul>
            <li ng-repeat="incident in c.tabContent">{{incident.number}} - {{incident.short_description}}</li>
          </ul>
        </uib-tab>
        <uib-tab heading="In-Progress Incidents" select="c.loadTabContent('in_progress')">
          <ul>
            <li ng-repeat="incident in c.tabContent">{{incident.number}} - {{incident.short_description}}</li>
          </ul>
        </uib-tab>
      </uib-tabset>
    </div>
    <!-- Tabs with Dynamic Content Example End -->

    <hr>

    <!-- Notification Toasts Example Start -->
    <div class="example-section">
      <div class="example-description">
        <h4>Notification Toasts</h4>
        <p>Display small, non-intrusive alerts to notify the user of events.</p>
      </div>
      <div>
        <button class="btn btn-success" ng-click="c.showToast('success', 'Action completed successfully!')">Show Success Toast</button>
        <button class="btn btn-danger" ng-click="c.showToast('error', 'An error occurred!')">Show Error Toast</button>
      </div>
      <div class="toast-container" ng-if="c.toasts.length">
        <div class="toast" ng-repeat="toast in c.toasts" ng-class="toast.type">
          {{toast.message}}
        </div>
      </div>
    </div>
    <!-- Notification Toasts Example End -->

    <hr>

    <!-- Loading Spinner Example Start -->
    <div class="example-section">
      <div class="example-description">
        <h4>Loading Spinner</h4>
        <p>A spinner that shows while data is loading.</p>
      </div>
      <div ng-show="c.loading" class="spinner-container">
        <div class="spinner"></div>
      </div>
      <button class="btn btn-primary" ng-click="c.loadData()">Load Data</button>
    </div>
    <!-- Loading Spinner Example End -->

    <hr>

    <!-- Modal with Dynamic Content Example Start -->
    <div class="example-section">
      <div class="example-description">
        <h4>Modal with Dynamic Content</h4>
        <p>Select an incident from the dropdown to view its details in a modal.</p>
      </div>
      <div class="form-group">
        <label for="incidentSelect">Select Incident:</label>
        <select id="incidentSelect" ng-model="c.selectedIncident" ng-options="incident as incident.number + ' - ' + incident.short_description for incident in c.incidents" class="form-control">
          <option value="">-- Select an Incident --</option>
        </select>
      </div>
      <button class="btn btn-info" ng-click="c.openDynamicModal()" ng-disabled="!c.selectedIncident">Open Incident Details</button>
    </div>
    <!-- Modal with Dynamic Content Example End -->

    <hr>

    <!-- Modal with Editable Content Example Start -->
    <div class="example-section">
      <div class="example-description">
        <h4>Modal with Editable Content</h4>
        <p>Select an incident from the dropdown to view and edit its details in a modal.</p>
      </div>
      <div class="form-group">
        <label for="incidentSelect">Select Incident:</label>
        <select id="incidentSelect" ng-model="c.selectedIncident" ng-options="incident as incident.number + ' - ' + incident.short_description for incident in c.incidents" class="form-control">
          <option value="">-- Select an Incident --</option>
        </select>
      </div>
      <button class="btn btn-info" ng-click="c.openDynamicModalEditable()" ng-disabled="!c.selectedIncident">Open Incident Details</button>
    </div>
    <!-- Modal with Editable Content Example End -->

    <hr>

    <!-- Modal with Comment Section Example Start -->
    <div class="example-section">
      <div class="example-description">
        <h4>Modal with Comment Section</h4>
        <p>Select an incident from the dropdown to view and edit its details, including adding comments, in a modal.</p>
      </div>
      <div class="form-group">
        <label for="incidentSelect">Select Incident:</label>
        <select id="incidentSelect" ng-model="c.selectedIncident" ng-options="incident as incident.number + ' - ' + incident.short_description for incident in c.incidents" class="form-control">
          <option value="">-- Select an Incident --</option>
        </select>
      </div>
      <button class="btn btn-info" ng-click="c.openDynamicModalWithComments()" ng-disabled="!c.selectedIncident">Open Incident Details</button>
    </div>
    <!-- Modal with Comment Section Example End -->

    <hr>

    <!-- Modal with Related Records Example Start -->
    <div class="example-section">
      <div class="example-description">
        <h4>Modal with Related Records</h4>
        <p>Select an incident from the dropdown to view and edit its details, with links to related records, in a modal.</p>
      </div>
      <div class="form-group">
        <label for="incidentSelect">Select Incident:</label>
        <select id="incidentSelect" ng-model="c.selectedIncident" ng-options="incident as incident.number + ' - ' + incident.short_description for incident in c.incidents" class="form-control">
          <option value="">-- Select an Incident --</option>
        </select>
      </div>
      <button class="btn btn-info" ng-click="c.openDynamicModalWithRelatedRecords()" ng-disabled="!c.selectedIncident">Open Incident Details</button>
    </div>
    <!-- Modal with Related Records Example End -->

  </div>
</div>
```
### CSS
```css
.example-section {
  margin-bottom: 20px;
}

.example-description {
  background-color: #f5f5f5;
  padding: 10px;
  border-radius: 5px;
  text-align: left;
  margin-bottom: 10px;
}

.carousel-container {
  max-width: 600px; /* Set a maximum width for the carousel */
  margin: 0 auto; /* Center the carousel */
}

.carousel-content {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #ddd;
  border-radius: 5px;
  padding: 10px;
  height: 300px; /* Set a consistent height for the carousel */
}

.carousel-caption {
  background-color: rgba(0, 0, 0, 0.5);
  color: #fff;
  padding: 5px;
  border-radius: 3px;
  position: absolute;
  bottom: 40px; /* Move the text higher */
  left: 50%;
  transform: translateX(-50%);
}

.filter-section {
  margin-bottom: 20px;
  text-align: left;
}

.list-group-item {
  text-align: left;
}

.text-center {
  text-align: left;
}

hr {
  margin: 40px 0;
  border: none;
  border-top: 1px solid #ddd;
}

/* toast start */
.toast-container {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 9999;
}

.toast {
  padding: 10px 20px;
  margin-bottom: 10px;
  border-radius: 5px;
  color: #fff;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  animation: fadeInOut 4s forwards;
}

.toast.success {
  background-color: #28a745;
}

.toast.error {
  background-color: #dc3545;
}

@keyframes fadeInOut {
  0% {
    opacity: 0;
    transform: translateX(100%);
  }
  10%, 90% {
    opacity: 1;
    transform: translateX(0);
  }
  100% {
    opacity: 0;
    transform: translateX(100%);
  }
}
/* toast end */

/* Loading Spinner Example Start */
.spinner-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100px;
}

.spinner {
  border: 4px solid rgba(0, 0, 0, 0.1);
  border-left-color: #007bff;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
/* Loading Spinner Example End */
```
### Client Script
```javascript
api.controller = function ($scope, $uibModal, $http) {
    var c = this;

    // Load incidents when the widget loads
    loadIncidents();

    // Fetch incidents for various examples
    function loadIncidents() {
        $http.get('/api/now/table/incident?sysparm_limit=10').then(function(response) {
            c.incidents = response.data.result;

            // Populate various examples Start
            if (c.incidents.length > 0) {
                c.incidentTooltip = "Incident: " + c.incidents[0].number + " - " + c.incidents[0].short_description;
                c.incidentPopover = "Incident: " + c.incidents[1].number + " - " + c.incidents[1].short_description;
                c.incidentDescription = c.incidents[2].description;
                c.incidentPriority = c.incidents[3].priority;
                c.incidentAlertType = getAlertType(c.incidentPriority);
                c.incidentCarouselSlides = c.incidents.slice(0, 3); // Use first 3 incidents for the carousel
                c.openIncidents = c.incidents.filter(i => i.state == '1'); // Open incidents
                c.resolvedIncidents = c.incidents.filter(i => i.state == '6'); // Resolved incidents
            }
            // Populate various examples End
        });
    }

    // Function to determine alert type based on priority Start
    function getAlertType(priority) {
        switch (priority) {
            case '1':
                return 'danger';
            case '2':
                return 'warning';
            case '3':
                return 'info';
            default:
                return 'success';
        }
    }
    // Function to determine alert type based on priority End

    // Modal Example Start
    c.openIncidentModal = function() {
        var modalInstance = $uibModal.open({
            template: '<div class="modal-header"><h3 class="modal-title">Incident Details</h3></div>' +
                      '<div class="modal-body">' +
                      '<p><strong>Number:</strong> {{incident.number}}</p>' +
                      '<p><strong>Short Description:</strong> {{incident.short_description}}</p>' +
                      '<p><strong>Description:</strong> {{incident.description}}</p>' +
                      '</div>' +
                      '<div class="modal-footer">' +
                      '<button class="btn btn-primary" ng-click="ok()">OK</button>' +
                      '<button class="btn btn-warning" ng-click="cancel()">Cancel</button>' +
                      '</div>',
            controller: function($scope, $uibModalInstance) {
                $scope.incident = c.incidents[0]; // Pass the first incident as an example
                $scope.ok = function() {
                    $uibModalInstance.close();
                };
                $scope.cancel = function() {
                    $uibModalInstance.dismiss('cancel');
                };
            }
        });
    };
    // Modal Example End

    // Datepicker filter example Start
    c.filterByDate = function() {
        // Example: Filter incidents by creation date
        var selectedDate = c.selectedDate.toISOString().split('T')[0];
        $http.get('/api/now/table/incident?sysparm_query=sys_created_on>=' + selectedDate).then(function(response) {
            c.incidents = response.data.result;
        });
    };
    // Datepicker filter example End

    // Category dropdown selection example Start
    c.categories = ['Software', 'Hardware', 'Network'];
    c.selectCategory = function(category) {
        // Example: Filter incidents by category
        console.log('Selected Category: ', category);
    };
    // Category dropdown selection example End

    // Pagination example Start
    c.totalIncidents = 64; // Example total incidents for pagination
    c.currentPage = 1;
    c.pageChanged = function() {
        console.log('Page changed to: ' + c.currentPage);
    };
    // Pagination example End

    // Progress bar example Start
    c.resolutionProgress = 70; // Example progress of resolved incidents
    // Progress bar example End

    // Rating example Start
    c.incidentRating = 4; // Example rating value
    c.saveRating = function() {
        console.log('Saved Rating: ', c.incidentRating);
    };
    // Rating example End

    // Typeahead incident selection Start
    c.loadIncidentDetails = function(incidentNumber) {
        // Example: Load incident details based on selected number
        var selectedIncident = c.incidents.find(i => i.number === incidentNumber);
        if (selectedIncident) {
            console.log('Selected Incident: ', selectedIncident);
        }
    };
    // Typeahead incident selection End

    // Carousel Example Start
    c.activeSlide = 0; // Initialize the first slide as active

    c.exampleSlides = [
        {
            id: 0,
            image: 'https://via.placeholder.com/600x300.png?text=Example+Image+1',
            text: 'Example Image 1'
        },
        {
            id: 1,
            image: 'https://via.placeholder.com/600x300.png?text=Example+Image+2',
            text: 'Example Image 2'
        },
        {
            id: 2,
            image: 'https://via.placeholder.com/600x300.png?text=Example+Image+3',
            text: 'Example Image 3'
        }
    ];
    // Carousel Example End

    // Modal with Form Example Start
    c.openFormModal = function() {
        var modalInstance = $uibModal.open({
            template: `
                <div class="modal-header"><h3 class="modal-title">Input Form</h3></div>
                <div class="modal-body">
                  <form name="form">
                    <div class="form-group">
                      <label for="name">Name:</label>
                      <input type="text" id="name" class="form-control" ng-model="formData.name" required>
                    </div>
                    <div class="form-group">
                      <label for="email">Email:</label>
                      <input type="email" id="email" class="form-control" ng-model="formData.email" required>
                    </div>
                  </form>
                </div>
                <div class="modal-footer">
                  <button class="btn btn-primary" ng-click="save()">Save</button>
                  <button class="btn btn-secondary" ng-click="cancel()">Cancel</button>
                </div>`,
            controller: function($scope, $uibModalInstance) {
                $scope.formData = {};

                $scope.save = function() {
                    console.log('Form Data:', $scope.formData);
                    $uibModalInstance.close($scope.formData);
                };

                $scope.cancel = function() {
                    $uibModalInstance.dismiss('cancel');
                };
            }
        });
    };
    // Modal with Form Example End

    // Tooltip with HTML Content Example Start
    c.htmlTooltipContent = `
        <div>
          <strong>Tooltip Title</strong>
          <ul>
            <li>First item</li>
            <li>Second item</li>
            <li>Third item</li>
          </ul>
        </div>`;
    // Tooltip with HTML Content Example End

    // Multi-select Dropdown Example Start
    c.multiSelectOptions = [
        { label: 'Option 1', selected: false },
        { label: 'Option 2', selected: false },
        { label: 'Option 3', selected: false }
    ];
    // Multi-select Dropdown Example End

    // Popover with Dynamic Content Example Start
    c.dynamicPopoverTemplateUrl = 'https://dev243134.service-now.com/sp?id=index';
    // The content of the popover is defined in an external template file
    // Popover with Dynamic Content Example End

    // Advanced Pagination with Filters Example Start
    // Simulate data with a list of incidents
    c.items = [
        { number: 'INC001', short_description: 'Network issue in building 1' },
        { number: 'INC002', short_description: 'Email server not responding' },
        { number: 'INC003', short_description: 'Software installation request' },
        { number: 'INC004', short_description: 'Cannot access VPN' },
        { number: 'INC005', short_description: 'Slow internet connection' },
        { number: 'INC006', short_description: 'Printer not working' },
        { number: 'INC007', short_description: 'Password reset request' },
        { number: 'INC008', short_description: 'New user account setup' },
        { number: 'INC009', short_description: 'Hardware replacement needed' },
        { number: 'INC010', short_description: 'Security breach reported' }
    ];

    // Pagination settings Start
    c.currentPage = 1;
    c.itemsPerPage = 5;
    c.searchFilter = '';

    // Function to apply the filter and reset pagination
    c.applyFilter = function() {
        c.filteredItems = c.items.filter(item => item.short_description.toLowerCase().includes(c.searchFilter.toLowerCase()));
        c.updatePage();
    };

    // Function to update the displayed page of items
    c.updatePage = function() {
        var begin = ((c.currentPage - 1) * c.itemsPerPage);
        var end = begin + c.itemsPerPage;
        c.paginatedItems = c.filteredItems.slice(begin, end);
    };

    // Initialize the filtered items and pagination
    c.applyFilter();
    // Pagination settings End
    // Advanced Pagination with Filters Example End

    // File Upload with Progress Bar Example Start
    c.uploadProgress = 0;

    c.uploadFile = function(files) {
        var file = files[0];
        var formData = new FormData();
        formData.append('file', file);

        // Simulate file upload for the example
        var simulatedUpload = function() {
            if (c.uploadProgress < 100) {
                c.uploadProgress += 10;
                setTimeout(simulatedUpload, 500);
                $scope.$apply();  // Update the scope
            }
        };

        simulatedUpload();
    };
    // File Upload with Progress Bar Example End

    // Sortable and Filterable Table Example Start
    c.sortField = 'number';
    c.sortReverse = false;

    c.sortBy = function(field) {
        if (c.sortField === field) {
            c.sortReverse = !c.sortReverse;
        } else {
            c.sortField = field;
            c.sortReverse = false;
        }
    };

    c.filteredItems = [
        { number: 'INC001', short_description: 'Network issue in building 1' },
        { number: 'INC002', short_description: 'Email server not responding' },
        { number: 'INC003', short_description: 'Software installation request' },
        // More items...
    ];
    // Sortable and Filterable Table Example End

    // Tabs with Dynamic Content Example Start
    c.activeTab = 0;

    c.loadTabContent = function(tab) {
        // Simulate loading data based on the tab
        switch (tab) {
            case 'open':
                c.tabContent = [
                    { number: 'INC001', short_description: 'Network issue in building 1' },
                    { number: 'INC002', short_description: 'Email server not responding' }
                ];
                break;
            case 'resolved':
                c.tabContent = [
                    { number: 'INC003', short_description: 'Software installation request' },
                    { number: 'INC004', short_description: 'Cannot access VPN' }
                ];
                break;
            case 'in_progress':
                c.tabContent = [
                    { number: 'INC005', short_description: 'Slow internet connection' },
                    { number: 'INC006', short_description: 'Printer not working' }
                ];
                break;
        }
    };

    // Load initial tab content
    c.loadTabContent('open');
    // Tabs with Dynamic Content Example End

    // Notification Toasts Example Start
    c.toasts = [];

    c.showToast = function(type, message) {
        var toast = { type: type, message: message };
        c.toasts.push(toast);

        // Automatically remove the toast after 4 seconds
        setTimeout(function() {
            var index = c.toasts.indexOf(toast);
            if (index > -1) {
                c.toasts.splice(index, 1);
                $scope.$apply(); // Ensure Angular updates the UI
            }
        }, 4000);
    };
    // Notification Toasts Example End

    // Loading Spinner Example Start
    c.loading = false;

    c.loadData = function() {
        c.loading = true;

        // Simulate data loading
        setTimeout(function() {
            c.loading = false;
            $scope.$apply(); // Ensure Angular updates the UI
            alert('Data Loaded');
        }, 3000);
    };
    // Loading Spinner Example End

    // Modal with Dynamic Content Example Start
    c.selectedIncident = null; // Initialize the selected incident

    c.openDynamicModal = function() {
        var modalInstance = $uibModal.open({
            template: `
                <div class="modal-header"><h3 class="modal-title">Incident Details</h3></div>
                <div class="modal-body">
                  <p><strong>Number:</strong> {{incident.number}}</p>
                  <p><strong>Short Description:</strong> {{incident.short_description}}</p>
                  <p><strong>Description:</strong> {{incident.description}}</p>
                </div>
                <div class="modal-footer">
                  <button class="btn btn-primary" ng-click="ok()">OK</button>
                  <button class="btn btn-secondary" ng-click="cancel()">Cancel</button>
                </div>`,
            controller: function($scope, $uibModalInstance) {
                // Pass the selected incident data to the modal
                $scope.incident = angular.copy(c.selectedIncident);

                $scope.ok = function() {
                    $uibModalInstance.close();
                };

                $scope.cancel = function() {
                    $uibModalInstance.dismiss('cancel');
                };
            }
        });
    };
    // Modal with Dynamic Content Example End

    // Modal with Editable Content Example Start
    c.selectedIncident = null;

    c.openDynamicModalEditable = function() {
        var modalInstance = $uibModal.open({
            template: `
                <div class="modal-header"><h3 class="modal-title">Incident Details</h3></div>
                <div class="modal-body">
                  <form>
                    <div class="form-group">
                      <label>Number:</label>
                      <p>{{incident.number}}</p>
                    </div>
                    <div class="form-group">
                      <label>Short Description:</label>
                      <input type="text" ng-model="incident.short_description" class="form-control">
                    </div>
                    <div class="form-group">
                      <label>Description:</label>
                      <textarea ng-model="incident.description" class="form-control"></textarea>
                    </div>
                  </form>
                </div>
                <div class="modal-footer">
                  <button class="btn btn-primary" ng-click="save()">Save</button>
                  <button class="btn btn-secondary" ng-click="cancel()">Cancel</button>
                </div>`,
            controller: function($scope, $uibModalInstance, $http) {
                $scope.incident = angular.copy(c.selectedIncident);

                $scope.save = function() {
                    var params = {
                        sys_id: $scope.incident.sys_id,
                        short_description: $scope.incident.short_description,
                        description: $scope.incident.description
                    };

                    $http.post('/api/now/table/incident/' + params.sys_id, params)
                        .then(function(response) {
                            c.updateIncidentInList(response.data.result);
                            $uibModalInstance.close();
                            spUtil.addInfoMessage('Incident updated successfully.');
                        }, function(error) {
                            spUtil.addErrorMessage('Failed to update the incident.');
                        });
                };

                $scope.cancel = function() {
                    $uibModalInstance.dismiss('cancel');
                };
            }
        });
    };

    c.updateIncidentInList = function(updatedIncident) {
        var index = c.incidents.findIndex(incident => incident.sys_id === updatedIncident.sys_id);
        if (index > -1) {
            c.incidents[index] = updatedIncident;
        }
    };
    // Modal with Editable Content Example End

    // Modal with Comment Section Example Start
    c.selectedIncident = null;

    c.openDynamicModalWithComments = function() {
        var modalInstance = $uibModal.open({
            template: `
                <div class="modal-header"><h3 class="modal-title">Incident Details</h3></div>
                <div class="modal-body">
                  <form>
                    <div class="form-group">
                      <label>Number:</label>
                      <p>{{incident.number}}</p>
                    </div>
                    <div class="form-group">
                      <label>Short Description:</label>
                      <input type="text" ng-model="incident.short_description" class="form-control">
                    </div>
                    <div class="form-group">
                      <label>Description:</label>
                      <textarea ng-model="incident.description" class="form-control"></textarea>
                    </div>
                    <div class="form-group">
                      <label>New Comment:</label>
                      <textarea ng-model="newComment" class="form-control" placeholder="Add a comment..."></textarea>
                    </div>
                  </form>
                  <div class="comments-section">
                    <h5>Comments:</h5>
                    <ul>
                      <li ng-repeat="comment in incident.comments">{{comment}}</li>
                    </ul>
                  </div>
                </div>
                <div class="modal-footer">
                  <button class="btn btn-primary" ng-click="save()">Save</button>
                  <button class="btn btn-secondary" ng-click="cancel()">Cancel</button>
                </div>`,
            controller: function($scope, $uibModalInstance, $http) {
                $scope.incident = angular.copy(c.selectedIncident);
                $scope.newComment = '';

                $scope.save = function() {
                    if ($scope.newComment) {
                        $scope.incident.comments = $scope.incident.comments || [];
                        $scope.incident.comments.push($scope.newComment);
                    }

                    var params = {
                        sys_id: $scope.incident.sys_id,
                        short_description: $scope.incident.short_description,
                        description: $scope.incident.description,
                        comments: $scope.incident.comments
                    };

                    $http.post('/api/now/table/incident/' + params.sys_id, params)
                        .then(function(response) {
                            c.updateIncidentInList(response.data.result);
                            $uibModalInstance.close();
                            spUtil.addInfoMessage('Incident updated successfully.');
                        }, function(error) {
                            spUtil.addErrorMessage('Failed to update the incident.');
                        });
                };

                $scope.cancel = function() {
                    $uibModalInstance.dismiss('cancel');
                };
            }
        });
    };

    c.updateIncidentInList = function(updatedIncident) {
        var index = c.incidents.findIndex(incident => incident.sys_id === updatedIncident.sys_id);
        if (index > -1) {
            c.incidents[index] = updatedIncident;
        }
    };
    // Modal with Comment Section Example End

    // Modal with Related Records Example Start
    c.selectedIncident = null;

    c.openDynamicModalWithRelatedRecords = function() {
        var modalInstance = $uibModal.open({
            template: `
                <div class="modal-header"><h3 class="modal-title">Incident Details</h3></div>
                <div class="modal-body">
                  <form>
                    <div class="form-group">
                      <label>Number:</label>
                      <p>{{incident.number}}</p>
                    </div>
                    <div class="form-group">
                      <label>Short Description:</label>
                      <input type="text" ng-model="incident.short_description" class="form-control">
                    </div>
                    <div class="form-group">
                      <label>Description:</label>
                      <textarea ng-model="incident.description" class="form-control"></textarea>
                    </div>
                    <div class="form-group">
                      <label>New Comment:</label>
                      <textarea ng-model="newComment" class="form-control" placeholder="Add a comment..."></textarea>
                    </div>
                  </form>
                  <div class="comments-section">
                    <h5>Comments:</h5>
                    <ul>
                      <li ng-repeat="comment in incident.comments">{{comment}}</li>
                    </ul>
                  </div>
                  <div class="related-records">
                    <h5>Related Records:</h5>
                    <ul>
                      <li><a ng-href="/nav_to.do?uri=problem.do?sys_id={{incident.problem_id}}">Related Problem</a></li>
                      <li><a ng-href="/nav_to.do?uri=change_request.do?sys_id={{incident.change_id}}">Related Change</a></li>
                    </ul>
                  </div>
                </div>
                <div class="modal-footer">
                  <button class="btn btn-primary" ng-click="save()">Save</button>
                  <button class="btn btn-secondary" ng-click="cancel()">Cancel</button>
                </div>`,
            controller: function($scope, $uibModalInstance, $http) {
                $scope.incident = angular.copy(c.selectedIncident);
                $scope.newComment = '';

                $scope.save = function() {
                    if ($scope.newComment) {
                        $scope.incident.comments = $scope.incident.comments || [];
                        $scope.incident.comments.push($scope.newComment);
                    }

                    var params = {
                        sys_id: $scope.incident.sys_id,
                        short_description: $scope.incident.short_description,
                        description: $scope.incident.description,
                        comments: $scope.incident.comments
                    };

                    $http.post('/api/now/table/incident/' + params.sys_id, params)
                        .then(function(response) {
                            c.updateIncidentInList(response.data.result);
                            $uibModalInstance.close();
                            spUtil.addInfoMessage('Incident updated successfully.');
                        }, function(error) {
                            spUtil.addErrorMessage('Failed to update the incident.');
                        });
                };

                $scope.cancel = function() {
                    $uibModalInstance.dismiss('cancel');
                };
            }
        });
    };

    c.updateIncidentInList = function(updatedIncident) {
        var index = c.incidents.findIndex(incident => incident.sys_id === updatedIncident.sys_id);
        if (index > -1) {
            c.incidents[index] = updatedIncident;
        }
    };
    // Modal with Related Records Example End
};
```
### Server Script
### incident table
```javascript
(function() {
    // This script could be used to pull data from the incident table to populate the widget
    var gr = new GlideRecord('incident');
    gr.setLimit(20);  // Limiting for the example
    gr.query();

    data.incidents = [];
    while (gr.next()) {
        data.incidents.push({
					sys_id: gr.getValue('sys_id'),
            number: gr.getValue('number'),
            short_description: gr.getValue('short_description'),
					description: gr.getValue('description')
        });
    }
})();
```
