---
title: channels.createChannel
description: channels.createChannel parameters, return type and example
---
## Method: channels.createChannel  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|title|[string](../types/string.md) | Yes|
|about|[string](../types/string.md) | Yes|
|users|Array of [InputUser](../types/InputUser.md) | Yes|


### Return type: [Updates](../types/Updates.md)

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

$Updates = $MadelineProto->channels->createChannel(['title' => string, 'about' => string, 'users' => [InputUser], ]);
```

Or, if you're into Lua:

```
Updates = channels.createChannel({title=string, about=string, users={InputUser}, })
```

