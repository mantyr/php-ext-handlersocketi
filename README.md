# HandlerSocket plugin for MySQL Improved Extension #

The handlersocketi extension allows you to access the functionality
provided by HandlerSocket plugin for MySQL.

More information about the HandlerSocket plugin for MySQL can be found at
[» http://github.com/ahiguti/HandlerSocket-Plugin-for-MySQL](http://github.com/ahiguti/HandlerSocket-Plugin-for-MySQL)

Note: Documentation of HandlerSocket not suitable.
Old documentation : https://code.google.com/p/php-handlersocket/
New documentation in the process of writing:

HandlerSocketi {
    /* Methods */
    public __construct( string $host, string $port [, array $options ] ), $options = [ "timeout" => XXX, "persistent" => XXX ]
    public auth( string $key, string $type)
    public open_index( string $db, string $table, string $fields [, array $options = array()] )
}

$options = [ "limit" => XXX, "offset" => XXX ];

/* Defaults */
$options['limit'] = HS_DEFAULT_LIMIT = 1
$options['ofset'] = HS_DEFAULT_OFFSET = 0
$options['timeout'] = HS_STREAM_DEFAULT_TIMEOUT = 5

HandlerSocketi_index {
    /* Methods */
    public __construct( $hs, $db, $table, $fields [, $options] )
    public find( $query [, array $options] )
    public insert( $args ), type value is "NULL", "Long", "Double", (string)value
    public update( $query, $update [, $options] )
    public remove( $query [, $options] )
    public multi( $args ), find,insert,update,remove
    public get_error()
    public get_id()
    public get_name()
    public get_db()
    public get_table()
    public get_field()
    public get_filter()
    public get_operator()
}

/* $options */
HandlerSocketi::__construct() -> $options = [ "timeout" => XXX, "persistent" => XXX ]
HandlerSocketi::open_index() -> $options = [ "id" => XXX, "index" => "PRIMARY", "filter" => XXX ]

HandlerSocketi_index::find(), update(), remove() -> $options = [ "limit" => XXX, "offset" => XXX ]
