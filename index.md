<html>        
<script type="text/javascript">
    if (!window._laq) {
        window._laq = [];
    }
    window._laq.push(function(){
        liveagent.showWhenOnline('573D7000000CnmY', document.getElementById('liveagent_button_online_573D7000000CnmY'));
        liveagent.showWhenOffline('573D7000000CnmY', document.getElementById('liveagent_button_offline_573D7000000CnmY'));
    });
</script>
<script type='text/javascript'>
    function btnEventHandler(e){
        if(e == liveagent.BUTTON_EVENT.BUTTON_AVAILABLE){
            document.getElementById("myspan").innerHTML = "AGENT AVAILABLE";
        }else if(e == liveagent.BUTTON_EVENT.BUTTON_UNAVAILABLE){
            document.getElementById("myspan").innerHTML = "AGENT NOT AVAILABLE";
        }
    }
    liveagent.addButtonEventHandler('573D7000000CnmY', btnEventHandler);        
    liveagent.init('https://d.la3-c1cs-ia6.salesforceliveagent.com/chat', '572D7000000Cmni', '00D63000000o0xw');
    liveagent.setChatWindowHeight(400);
    liveagent.setChatWindowWidth(350);
</script>
</html>
