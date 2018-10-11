# masvasa
API for mobifin gateway


<?php
	$url = "https://mobifinng.primeairtime.com/api/";

	$USERNAME = "univas";
    $PASSWORD = "8f56ktvswuz";
	// $user    = "univas";
	// $pass    = "8f56ktvswuz";

    // CREATING JSON BODY
    $body = '{
        "username" : "$USERNAME",
        "password" : "$PASSWORD"
    }';
    
    // EXECUTING CURL COMMAND
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, $url."auth");
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    // curl_setopt($ch, CURLOPT_USERPWD, "$USERNAME:$PASSWORD");
    curl_setopt($ch, CURLOPT_HTTPHEADER, array( 
            // 'Authorization: Bearer '.$authorization,
            "Content-Type: application/json" 
        )
    );
    curl_setopt($ch, CURLOPT_POST, 1);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $body);
    $result = curl_exec($ch);

    echo "<pre>";
    print_r($result);
   
   ?>
