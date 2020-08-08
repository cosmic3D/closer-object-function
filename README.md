# closer-object-function
With this simple function you will be able to get the nearest object (you can set a distance)to an object in an array of GameObjects for unity

private GameObject FindMinValue(GameObject[] points, GameObject point, float minDistance = 0)
    {

        GameObject closerObject = null;
        

        if (minDistance > 0)
        {
            for (int i = 0; i < points.Length; i++)
            {
                if (closerObject == null && Vector2.Distance(points[i].transform.position, point.transform.position) < minDistance)
                {
                    closerObject = points[i];
                }
                else if (Vector2.Distance(points[i].transform.position, point.transform.position) < minDistance && Vector2.Distance(points[i].transform.position, point.transform.position) < Vector2.Distance(closerObject.transform.position, point.transform.position))
                {
                    closerObject = points[i];
                    
                }
            }
        }
        else if(minDistance == 0f)
        {
         
            for (int i = 0; i < points.Length; i++)
            {
                
                if (closerObject == null)
                {
                    closerObject = points[0];
                   
                }
                else if (Vector2.Distance(points[i].transform.position, point.transform.position) < Vector2.Distance(closerObject.transform.position, point.transform.position))
                {
                    closerObject = points[i];
                    
                }
            }
        }
        else
        {
            //USE AN ALLOWED VALUE CUNT
            Debug.Log("YOU CANNOT SET THE DISTANCE TO THAT VALUE :)");
        }

        return closerObject;
    }
