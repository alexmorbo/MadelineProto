---
title: help.setBotUpdatesStatus
description: help.setBotUpdatesStatus parameters, return type and example
---
## Method: help.setBotUpdatesStatus  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|pending\_updates\_count|[int](../types/int.md) | Yes|
|message|[string](../types/string.md) | Yes|


### Return type: [Bool](../types/Bool.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $this->bot_login($token);
}
if (isset($number)) { // Login as a user
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$Bool = $MadelineProto->help->setBotUpdatesStatus(['pending_updates_count' => int, 'message' => string, ]);
```

Or, if you're into Lua:

```
Bool = help.setBotUpdatesStatus({pending_updates_count=int, message=string, })
```


## Return value 

If the length of the provided message is bigger than 4096, the message will be split in chunks and the method will be called multiple times, with the same parameters (except for the message), and an array of [Bool](../types/Bool.md) will be returned instead.


