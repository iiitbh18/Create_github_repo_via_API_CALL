# Create_github_repo_via_API_CALL And authenticate the gitHub account via API call
We will be able to see how we can create github repo via API call and user authentication of your gitHub account.



The easiest and best way to authenticate with the GitHub API is by using Basic Authentication via OAuth tokens.
   https://api.github.com/user  // on accesing it, it  has mention requires authentication.
  {
  "message": "Requires authentication",
  "documentation_url": <"https://docs.github.com/rest/reference/users#get-the-authenticated-user">
}
  
To make any requests we need to use  ## <b>request.get('Here is the url to which we want to make our API call',a parameter named auth for authentication).</b>
response = requests.get('https://api.github.com/user/repos',auth = ('username', 'password')), Where username is our email id and password we can get via generated tokes, for generating tokens follow the steps given in the documentation:-https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token  ,so with this  request we can authenticate ourself while making any get request to API which requires authentication.





Now, to create the new repo we need to use post requests, not get requests, because we are updating something,:- requests.post('url to which we want to make our post requests', data(we want to pass with this url),auth)
import json
info = {'name': 'test_repo', 'description': 'created via API call', 'auto_init': 'true'}
a = requests.post('https://api.github.com/user/repos',auth = ('bhaskarjha654321@gmail.com', 'generated tokens'), data = json.dumps(info)) # and here we need to convert python daa in to json by using json.dumps(python_data).


  





