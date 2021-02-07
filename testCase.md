# Test Cases

## Test Case #1: Search for Queue ID based on Company ID '1000000001'
### Description: 
- A successful request should show the Queue IDs the Company is in in the drop down menu.
### Pre-condition:
1. Backend tester should be running - both company and customer
2. Backend should be populated
### Test Steps:
1. Start up the backend tester and ensure that the backend is populated
2. Go live on port 5500
3. Click 'Add Another'
4. Input the company id '100000001' 
5. Click 'Search'
6. Click the dropdown menu
### Expected Results:
- All the queue ids under that company id should be there (QueueId: "QUEUE01001", "QUEUE01002", "QUEUE01003", "QUEUE01004", "QUEUE01005") where "QUEUE01004" and "QUEUE01005" should be inactive (greyed out).

</br>
</br> 

## Test Case #2: Hide Inactive Queues
### Description:
- The inactive queues should be hidden and not part of the drop down menu
### Pre-condition:
1. Backend tester should be running - both company and customer
2. Backend should be populated
3. The company id has been searched
### Test Steps:
1. Click on the checkbox that says "Show Inactive" and ensure that it is not ticked.
2. Click on the drop down menu
### Expected Results:
- There should only be 3 queue ids showing (QueueId: "QUEUE01001", "QUEUE01002", "QUEUE01003"). There are no greyed out queue ids

</br>
</br> 

## Test Case #3: View Arrival Rate Based on Queue ID 'QUEUE01002' while refreshing every 3 seconds
### Description:
- Arrival Rate appears in the graph for the Queue ID 'QUEUE01002' in the form of a line graph and auto-refreshes every 3 seconds
### Pre-condition:
1. Backend Tester should be running - both company and customer
2. Backend should be populated
3. The company id has been searched
### Test Steps:
1. Run double peak scenario in the backend tester
2. Click on the queue drop down menu and click on 'QUEUE01002'
### Expected Results:
- A graph should appear which auto-refreshes every 3 seconds and there will be a double-peak graph

</br>
</br> 

## Test Case #4: View graphs 'QUEUE01002' & 'QUEUE01003' at the same time
### Description:
- Able to view multiple graphs at the same time and it auto-refreshes every 3 seconds
### Pre-condition:
1. Backend Tester should be running - both company and customer
2. Backend should be populated
### Test Steps:
1. Click 'Add Another'
2. Input the company id '100000001' 
3. Click 'Search'
4. Run double peak in the backend tester
5. Click on the drop down menu and select 'QUEUE01002'
6. Repeat steps 1 to 4
7. Click on the drop down menu and select 'QUEUE01003'
### Expected Results:
- Both graphs should be shown and both will auto-refresh every 3 seconds 

</br>
</br>

# Error Test Cases

## Error Test Case #1: Search for Queue ID based on Company ID 'qwe'
### Description: 
- Search for Queue IDs with a Company ID that is not in the valid format
### Pre-condition:
1. Backend tester should be running - both company and customer
2. Backend should be populated
### Test Steps:
1. Start up the backend tester and ensure that the backend is populated
2. Go live on port 5500
3. Click 'Add Another'
4. Input the company id 'qwe' 
5. Click 'Search'
### Expected Results:
- An alert should pop up saying "Invalid Company Id Format"

</br>
</br> 

## Error Test Case #2: Search for Queue ID based on Company ID '2222222222'
### Description: 
- Search for Queue IDs with a Company ID that does not exist in the database
### Pre-condition:
1. Backend tester should be running - both company and customer
2. Backend should be populated
### Test Steps:
1. Start up the backend tester and ensure that the backend is populated
2. Go live on port 5500
3. Click 'Add Another'
4. Input the company id '2222222222' 
5. Click 'Search'
### Expected Results:
- An alert should pop up saying "Company ID Does Not Exist"
