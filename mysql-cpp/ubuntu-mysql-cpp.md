# MySQL Ubuntu Linux CPP Development
## Required Package Installation
```sh
sudo apt-get install libmysql-dev
sudo apt-get install libmysqlcppconn-dev
```

## In Qt Creator Linux Version Include following line to ``` Project.pro ``` File
```sh
LIBS += -lmysqlcppconn
```

## Example Code To Test
```cpp
/* Standard C++ includes */
#include <stdlib.h>
#include <iostream>

/*
Include directly the different
headers from cppconn/ and mysql_driver.h + mysql_util.h
(and mysql_connection.h). This will reduce your build time!
*/
#include "mysql_connection.h"
#include "mysql_driver.h"

#include <cppconn/driver.h>
#include <cppconn/exception.h>
#include <cppconn/resultset.h>
#include <cppconn/statement.h>

using namespace std;
using namespace sql;

int main(void)
{
    cout << endl;
    cout << "Running MySQL Query..." << endl;

        try {
        sql::Driver *driver;
        sql::Connection *con;
        sql::Statement *stmt;
        sql::ResultSet *res;

        /* Create a connection */
        driver = sql::mysql::get_mysql_driver_instance();
        con = driver->connect("tcp://127.0.0.1:3306", "root", "nopass");

        /* Connect to the MySQL database */
        con->setSchema("phpcrud");

        stmt = con->createStatement();
        res = stmt->executeQuery("select * from customers");

        while (res->next()) {
            cout << res->getInt(1) << "\t";
            cout << res->getString(2) << "\t";
            cout << res->getString(3) << endl;
        }
        delete res;
        delete stmt;
        delete con;

    }
    catch (sql::SQLException &e) {
        cout << "# ERR: SQLException in " << __FILE__;
        cout << "(" << __FUNCTION__ << ") on line " << __LINE__ << endl;
        cout << "# ERR: " << e.what();
        cout << " (MySQL error code: " << e.getErrorCode();
        cout << ", SQLState: " << e.getSQLState() << " )" << endl;
    }

    cout << endl;

    getchar();

    return EXIT_SUCCESS;
}
```
