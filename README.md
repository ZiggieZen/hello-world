# hello-world
My first repository

Hi, It's ziggie 

This is my first repository and looking forward to getting more into code.
Music is really cool you should try it

This is cool, where is Christian
lol
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    private float turnSpeed = 25.0f;
    private float horiztontalInput;
    private float forwardInput;
    public GameObject player;
    private float speed = 5.0f;
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame

    void Update()
    {
        //Move the vehicle forward
        horiztontalInput = Input.GetAxis("Horizontal");
        forwardInput = Input.GetAxis("Vertical");
        // Moves the car forward based on vertical input
        transform.Translate(Vector3.forward * Time.deltaTime * speed * forwardInput);
        // Rotates the car based on horizontal input
        transform.Rotate(Vector3.up, Time.deltaTime * turnSpeed * horiztontalInput);
    }
}




using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FollowPlayer : MonoBehaviour
{
    public GameObject player;
    private Vector3 offset = new Vector3(0, 5, -7);
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void LateUpdate()
    {
        transform.position = player.transform.position + offset;
    }
}
