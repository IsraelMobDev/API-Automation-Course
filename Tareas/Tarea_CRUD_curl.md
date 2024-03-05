# CRUD with CURL
## API: TODOIST

### We save the token as a variable
```
token_todoist=67e9b91cfb30bd1d2587549eef18766151208957
```
### Create a Project
#### Call
````
curl "https://api.todoist.com/rest/v2/projects" \
    -X POST \
    --data '{"name": "Shopping List"}' \
    -H "Content-Type: application/json" \
    -H "Authorization: Bearer ${token_todoist}"
````
#### Response
````
{
	"id": "2329720096",
	"parent_id": null,
	"order": 2,
	"color": "charcoal",
	"name": "Shopping List",
	"comment_count": 0,
	"is_shared": false,
	"is_favorite": false,
	"is_inbox_project": false,
	"is_team_inbox": false,
	"url": "https://todoist.com/showProject?id=2329720096",
	"view_style": "list"
}
````
### Read the details of a specific Project
#### Call
````
curl "https://api.todoist.com/rest/v2/projects/2329720096" \ 
  -H "Authorization: Bearer ${token_todoist}"
````
#### Response
````
{
	"id": "2329720096",
	"parent_id": null,
	"order": 2,
	"color": "charcoal",
	"name": "Shopping List",
	"comment_count": 0,
	"is_shared": false,
	"is_favorite": false,
	"is_inbox_project": false,
	"is_team_inbox": false,
	"url": "https://todoist.com/showProject?id=2329720096",
	"view_style": "list"
}
````
### Change the name of a Project
#### Call
````
curl "https://api.todoist.com/rest/v2/projects/2329720096" \
    -X POST \
    --data '{"name": "Title Changeddd"}' \
    -H "Content-Type: application/json" \
    -H "Authorization: Bearer ${token_todoist}"
````
#### Response
````
{
	"id": "2329720096",
	"parent_id": null,
	"order": 2,
	"color": "charcoal",
	"name": "Title Changeddd",
	"comment_count": 0,
	"is_shared": false,
	"is_favorite": false,
	"is_inbox_project": false,
	"is_team_inbox": false,
	"url": "https://todoist.com/showProject?id=2329720096",
	"view_style": "list"
}

````
### Delete a Project
#### Call
````
curl -X DELETE "https://api.todoist.com/rest/v2/projects/2329720096" \
    -H "Authorization: Bearer ${token_todoist}"
````
Now we get all the projects
![Screen Shot 2024-03-04 at 22.06.30.png](..%2F..%2F..%2F..%2F..%2F..%2Fvar%2Ffolders%2Fb3%2F21yt3m1x13q6zmt49dkl0_yh0000gn%2FT%2FTemporaryItems%2FNSIRD_screencaptureui_Ftfr9P%2FScreen%20Shot%202024-03-04%20at%2022.06.30.png)
as we can see the project recently deleted is not present