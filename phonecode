public function zr_dxyzm_ajax(){
	
	if(!preg_match("/1[3458]{1}\d{9}$/",$_GET['shouji'])){  
		echo json_encode(array("zt"=>'cw',"ts"=>"请填写正确手机号！"));
		exit;
	} 
	
	$zr_rand=rand(1000,9999);
	
	//$url='http://sms.webchinese.cn/web_api/?Uid=&Key=&smsMob='.$_GET['shouji'].'&smsText='.$zr_rand;
	$url='http://utf8.sms.webchinese.cn/?Uid=huzhu2016&Key=10a172a45194bfda5a55&smsMob='.$_GET['shouji'].'&smsText=手机验证码:'.$zr_rand.'111';
	
	//发送
	$ch = curl_init();
	$timeout = 5;
	curl_setopt ($ch, CURLOPT_URL, $url);
	curl_setopt ($ch, CURLOPT_RETURNTRANSFER, 1);
	curl_setopt ($ch, CURLOPT_CONNECTTIMEOUT, $timeout);
	$file_contents = curl_exec($ch);
	curl_close($ch);
	
	if($file_contents){
		echo json_encode(array("md5"=>md5($zr_rand),"zt"=>'cg'));
	}else{
		echo json_encode(array("zt"=>'cw',"ts"=>'短信发送失败！'));
	}
	
}
