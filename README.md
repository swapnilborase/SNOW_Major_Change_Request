# SNOW_Major_Change_Request
  Create custom Change Request called `Major Change` in SNOW.

## Steps to create New Change Management in SNOW
### Complete the following steps to add a new choice to the Type field.
  1. Open an existing change request.
  1. Right-click the Type field and select Show Choice List.
  1. Click New and fill in the following fields
      - Table : Change Request [change_request]
      - Label : Major
      - Value : major
  1. Submit
  
### Complete the following steps to add the new change type to the change request interceptor.
  1. Navigate to System Definition => Interceptors.
  1. Open the Change Request interceptor.
  1. Open any Answer from Related List & Enter following details then Insert & Save it. 

  <img width="600" alt="Interceptors #1" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/68af84e2-e47a-4809-bd1e-bc95cf16e243">
  <img width="600" alt="Interceptors #2" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/61ae2ec9-c3d4-468a-a5ba-b7259c92ccf3">

### Complete the following steps to create the Script Include for the new change type
  1. Navigate to System Definition => Script Includes
  1. Create 2 New Script Include :
     - ChangeRequestStateModel_major
     - ChangeRequestStateModelSNC_major
       <img width="700" alt="Screenshot 2023-07-10 201518" src="https://github.com/swapnilborase/SNOW_Major_Change_Request/assets/73363115/17efcdfd-dfad-488b-9405-ed37edd92697">
       <img width="700" alt="Screenshot 2023-07-10 201531" src="https://github.com/swapnilborase/SNOW_Major_Change_Request/assets/73363115/21c2ee51-d7b0-4727-a122-eb7f6df23025">

  1. Find `ChangeRequestStateHandler` Script Include & edit it [Refer the screenshot]

  <img width="600" alt="script_include_change_req_state_handler" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/d8aa2b20-8f0f-41f3-bf40-99377c70894d">

### Complete the following steps to Create New Change Model & it's states.
  1. Navigate to Change => Administration => Change Model
  2. Click New.
  3. Refer the Screenshot Below:

<img width="600" alt="cr_model_view" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/7477c4c6-74b5-471f-8f3a-790d3c66ffe5">
<img width="600" alt="cr_model_state_view_1" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/ae79bd79-12bc-469f-9a57-c224e58bfc15">
<img width="600" alt="cr_model_state_view_2" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/be215b55-e731-43de-8ef1-96e61c809afc">
<img width="600" alt="cr_model_state_view_3" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/d14aed3f-27dc-4c74-9939-e65a1c4246e7">
<img width="600" alt="cr_model_state_view_4" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/9e5e9b3f-94e0-4201-adae-afdfce6af59f">
<img width="600" alt="cr_model_state_view_5" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/85968739-b25b-45a4-bd7f-c5d6b49c2c20">


### Complete the following steps to create a flows for the new Change Request type [FLOW DESIGNER]
  * Search `change - normal` flow & you will see this result :

  <img width="600" alt="Normal flows" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/72355e5d-43d9-4bf8-a719-b63216b98930">

  * Copy these flows from more option & rename as this :

  <img width="600" alt="flows" src="https://github.com/swapnilborase/SNOW_Major_Custom_Change_Request/assets/73363115/484e9644-ff83-48cf-aec1-a995f8b32220">

  * Change the flow trigger condition under which new flow will execute as follow :
       - Model : Major

  ### Complete the following steps to create a Workflow for the new change request type [WORKFLOW EDITOR]
   1. Navigate to Workflow > Workflow Editor
   2. Open an existing change request workflow. For example: `Change Request – Normal`.
   3. Select Copy from the Actions menu to copy the workflow and name the new workflow. For example: `Change Request - Major`.
   4. Select Properties from the Actions menu to update the condition under which the new workflow executes. For example: `[Type]-[is]-[Major]`.
   5. Open the matching change tasks workflow that is called by the main workflow. For example: `Change Request - Normal change tasks`
   6. Select Copy from the Actions menu to copy the workflow and name the new workflow. For example: `Change Request - Major change tasks`.
   7. Select Publish from the Actions menu to publish the new change tasks workflow and make it available for use.
   8. Go back to the first workflow you created and update the Workflow activity to reference the new change tasks workflow. For example: `Change Request - Major change tasks`
   9. Select Publish from the Actions menu to publish the new workflow and make it available for use.
        
     
