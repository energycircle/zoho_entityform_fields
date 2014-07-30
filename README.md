zoho_entityform_fields
======================

Zoho / Entityform Integration



Place the below code in template.php of your theme and define the names of your forms.





//***Add form_id to the following array to add Zoho Handling post-submit
  //***
  //***to-do: set array dynamically from admin settings once best method agreed upon
  
  
 function at_national_form_alter(&$form, &$form_state, $form_id){
	 
 $aZohoForms = array(
     'schedule_your_service_request_entityform_edit_form',
	 'contact_entityform_edit_form',
	 'promotion_entityform_edit_form',
	 'healthy_air_survey_entityform_edit_form',
	 'schedule_your_service_entityform_edit_form',
  );
  if (in_array($form_id,$aZohoForms))
  {
     $form['actions']['submit']['#submit'][] = 'zoho_entityform_fields_submit_leads';
  }
}

// */