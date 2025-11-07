# SSO_PROTOS for nergous.ru

Прото-файлы созданные для SSO приложения на Golang для комплекса веб-приложений nergous.ru.

На данный момент созданы 3 вида контрактов соединенных между собой:

 1. **user.proto**
 2. **app.proto**
 3. **auth.proto**

# USER.proto
Данный контракт описывает способы взаимодействия с пользователями ресурсов. По порядку разберем все методы контракта:

## rpc UserInfo

    rpc UserInfo(UserInfoRequest) returns (UserInfoResponse);

Метод для получения информации о пользователе.

    message UserInfoRequest {
        uint32 user_id = 1;
    }
    
    message UserInfoResponse {
        string email = 1;
        string steam_url = 2;
        string path_to_photo = 3;
    }

## rpc GetAllUsers

    rpc GetAllUsers(GetAllUsersRequest) returns (GetAllUsersResponse);

Метод для получения всех пользователей.

    message GetAllUsersRequest {}
    
    message GetAllUsersResponse {
        repeated UserModel users = 1;
    }
    
    message UserModel {
	    uint32 id = 1;
	    string email = 2;
	    string steam_url = 3;
	    string path_to_photo = 4;
	}
   
   ## rpc UpdateUser

    rpc UpdateUser(UpdateUserRequest) returns (UpdateUserResponse);

Метод для обновления данных пользователей.

    message UpdateUserRequest {
	    uint32 id = 1;
	    string email = 2;
	    string password = 3;
	    string steam_url = 4;
	    string path_to_photo = 5;
    }
    
    message UpdateUserResponse {}

## rpc DeleteUser

    rpc DeleteUser(DeleteUserRequest) returns (DeleteUserResponse);

Метод для удаления данных пользователей.

    message DeleteUserRequest {
	    uint32 id = 1;
    }
    message DeleteUserResponse {}

