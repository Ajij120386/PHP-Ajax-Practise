<?php

// Check if 'id' is set in POST and is an array
if(isset($_POST['id']) && is_array($_POST['id'])) {
    // Convert Array into String
    $str = implode(",", $_POST['id']);

    // Connect to the database
    $conn = mysqli_connect("localhost","root","","testing1") or die("Connection Failed");

    // Escape the string to prevent SQL injection
    $escaped_str = mysqli_real_escape_string($conn, $str);

    // Construct the SQL query
    $sql = "DELETE FROM students WHERE id IN ({$escaped_str})";

    // Execute the query
    if(mysqli_query($conn, $sql)){
        // Successful deletion
        echo 1;
    } else {
        // Error in deletion
        echo 0;
    }

    // Close the database connection
    mysqli_close($conn);
} else {
    // Handle case where 'id' is not set in POST or not an array
    echo "No valid student IDs provided";
}

?>
