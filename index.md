<html>        
    <a id="liveagent_button_online_573D7000000CnmY" href="javascript://Chat" style="display: none;" onclick="liveagent.startChat('573D7000000CnmY')">Online Chat Content</a>
    <div id="liveagent_button_offline_573D7000000CnmY" style="display: none;">Offline Chat Content</div>
<script type="text/javascript">
    if (!window._laq) { window._laq = []; }
    window._laq.push(function(){liveagent.showWhenOnline('573D7000000CnmY', document.getElementById('liveagent_button_online_573D7000000CnmY'));
    liveagent.showWhenOffline('573D7000000CnmY', document.getElementById('liveagent_button_offline_573D7000000CnmY'));
    });
</script>


    <script type='text/javascript' src='https://c.la3-c1cs-ia6.salesforceliveagent.com/content/g/js/58.0/deployment.js'></script>
    <script type='text/javascript'>
    liveagent.init('https://d.la3-c1cs-ia6.salesforceliveagent.com/chat', '572D7000000Cmni', '00D63000000o0xw');
    </script>

<script type='text/javascript'>
    (function() {
    function handlePageLoad() {
    var endpointMatcher = new RegExp("[\\?\\&]endpoint=([^&#]*)");
    document.getElementById('prechatForm').setAttribute('action',
    decodeURIComponent(endpointMatcher.exec(document.location.search)[1]));
    } if (window.addEventListener) {
    window.addEventListener('load', handlePageLoad, false);
    } else { window.attachEvent('onload', handlePageLoad, false);
    }})();
</script>
 
<!-- Form that gathers information from the chat visitor and sets the values to Live Agent Custom Details used later in the example -->
<div id='prechatForm' style = "align= Center;">
  <table align= 'Center'>
        <tr>
            <td> Full Name: </td><td><input type='text' name='liveagent.prechat:fullName' id='Name' /><br /></td>
        </tr>
        <tr>
            <td>E-mail: </td> <td><input type='text' name='liveagent.prechat:AccountEmail' id='Email__c'  /><br /></td>
        </tr>
        <tr>
            <td>Phone: </td> <td><input type='text' name='liveagent.prechat:AccountPhone' id='Phone'  /> <br /></td>
        </tr>
      <tr>
            <td><br/>Or<br/></td>
        </tr>
  <tr>
            <td><br/>Raised Case already, enter<br/></td>
        </tr>
   
      <tr>
            <td>Case Number: </td> <td><input type='text' name='liveagent.prechat:CaseN' id='CaseNumber' /> <br /></td>
        </tr>
    </table>
 
    <!-- Hidden fields used to set additional custom details -->
    <input type="hidden" name="liveagent.prechat:CaseStatus" value="New" /><br />
    <input type="hidden" name="liveagent.prechat:CasePriority" value="Low" /><br />
     
 
    <!-- Used to set the visitor's name for the agent in the Console -->
    <input type="hidden" name="liveagent.prechat.name" id="prechat_field_name" />
<!-- map: Use the data from prechat form to map it to the Salesforce record's fields -->
<input type="hidden" name="liveagent.prechat.findorcreate.map:Account" value="Name,fullName;Email__c,AccountEmail;Phone,AccountPhone" />
 
<!-- doFind, doCreate and isExactMatch example for a Contact:
    Find a contact whose Email exactly matches the value provided by the customer in the form
    If there's no match, then create a Contact record and set it's First Name, Last Name, Email, and Phone to the values provided by the customer -->
<input type="hidden" name="liveagent.prechat.findorcreate.map.doFind:Account" value="Email__c,true" />
<input type="hidden" name="liveagent.prechat.findorcreate.map.isExactMatch:Account" value="Email__c,true" />
<input type="hidden" name="liveagent.prechat.findorcreate.map.doCreate:Account" value="Name,true;Email__c,true;Phone,true;" />

<!-- If consumer has created already case and has case number with him, will put case number directly and that will search and open the case -->
<input type="hidden" name="liveagent.prechat.findorcreate.map.doFind:Case" value="CaseNumber,true" />
<input type="hidden" name="liveagent.prechat.findorcreate.map.isExactMatch:Case" value="CaseNumber,true" /> 
<!--Mapping case fields with specified chat fields. We can map standard as well as custom fields. -->
<input type="hidden" name="liveagent.prechat.findorcreate.map:Case" value="CaseNumber,CaseN;Subject,CaseSubject;Status,CaseStatus;Priority,CasePriority;" />


<!-- doCreate example for a Case: create a case to attach to the chat, set the Case Subject to the value provided by the customer and set the case's Status and Origin fields -->
<input type="hidden" name="liveagent.prechat.findorcreate.map.doCreate:Case" value="CaseNumber,true;Subject,true;Status,true;Origin,true;Priority,true" />
<!-- linkToEntity: Set the record Contact record, found/created above, as the Contact on the Case that's created -->
<input type="hidden" name="liveagent.prechat.findorcreate.linkToEntity:Account" value="Case,AccountId" /> 
<!-- showOnCreate: Open the Account and Case records as sub-tabs to the chat for the agent in the Console -->
<input type="hidden" name="liveagent.prechat.findorcreate.showOnCreate:Account" value="true" />
<input type="hidden" name="liveagent.prechat.findorcreate.showOnCreate:Case" value="true" /> 
<!-- saveToTranscript: Associates the records found / created, i.e. Account and Case, to the Live Chat Transcript record. -->
<input type="hidden" name="liveagent.prechat.findorcreate.saveToTranscript:Account" value="AccountId" />
<input type="hidden" name="liveagent.prechat.findorcreate.saveToTranscript:Case" value="CaseId" />
<!-- displayToAgent: Hides the case record type from the agent -->
<input type="hidden" name="liveagent.prechat.findorcreate.displayToAgent:CaseRecordType" value="false" />
<!-- searchKnowledge: Searches knowledge article based on the text, this assumes that Knowledge is setup -->
<input type="hidden" name="liveagent.prechat.knowledgeSearch:CaseSubject" value="true" />
 
<!-- Link the Account to the Case -->
<input type= "hidden" name="liveagent.prechat.findorcreate.linkToEntity:Account" value="Case,AccountId" />
 
<input type='submit' value='Click to Chat' id='prechat_submit' />

<style type="text/css">
p {font-weight: bolder }
</style>
</div>
</html>
