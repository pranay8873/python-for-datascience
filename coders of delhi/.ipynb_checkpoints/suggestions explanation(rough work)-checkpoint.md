
# creates a dict with id as key and a list of friends as values

user_friends{
id    friends
 x       [1,1,1,]
}


# if given user id is not avalable it returns empty list exits function

input->user id    not there in user_friends returns []

# extracting direct friends of given user_id
 direct_friends=user_friends[user_id]
 for x it returns [1,1,1,....]

# itterating through friends of direct friends to ectract mutual friends
for friend in direct_friends:                //selecting one direct friend           eg: for 1 dir_fr's [2,3]

# itterating through all friends of direct friend
for mutual in user_friends[friend]:         //extracting friends of that one selected direct friend   eg: extracting friends of 2 and 3

 # checking weather the extracted friend is given id friend or present in direct friends list if not 
 if mutual!=user_id and mutual not in user_friends:

 # Increasing count of recomendations based on mutuals 

 suggestions[mutual]=suggestions.get(mutual,0)+1           //eg: if one mutual for x  (id x,1)   if 2 (id x,2)   storecd in a suggestions dictionary (key,value)
 
 # sorting based on mutual count not on the id value 
 sorted_suggestions=sorted(suggestions.items(),key= lambda x:x[1],reverse=True)
 
 # returning recomendation list only id's
  return [user_id for user_id,_ in sorted_suggestions]
      



