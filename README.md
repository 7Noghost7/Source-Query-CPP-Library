# Source Query C++ Library

## Example code
```
#include<iostream>
#include "ssq.hpp"

int main(int argc, char *argv[])
{
  if (argc != 3){
    std::cout<<"Incorrect number of parameters:\n";
    std::cout<<"    "<<argv[0]<<" {server ip} {port}\n";
    return 1;
  }

  Server_info serv;
  serv.start_query(argv[1], argv[2]);
  std::cout<<serv.GetHostname()<<"\n";
  std::cout<<serv.GetMap()<<"\n";
  std::cout<<serv.GetGameFolder()<<"\n";
  std::cout<<serv.GetGame()<<"\n";
  std::cout<<serv.GetAppId()<<"\n";
  std::cout<<serv.GetCurPlayers() << "/" << serv.GetMaxPlayers()<<"\n";
  std::cout<<"Bots:"<<serv.GetCurBots()<<"\n";
  std::cout<<serv.GetServerType()<<"\n";
  std::cout<<serv.GetOS()<<"\n";
  std::cout<<serv.GetVisibility()<<"\n";
  std::cout<<serv.GetSecure()<<"\n";

  return 0;
}
```
## Compiling
```
g++ example.cpp -o example
```
## Example usage
```
./example 127.0.0.1 27015
```

[This page describes the packet format and protocol](https://developer.valvesoftware.com/wiki/Server_queries)
