 public function statuscobranca($code){
        


       
        $token = $this->doacao_model->get_dados_asaas()->token;
        $curl = curl_init();

        curl_setopt_array($curl, [
        CURLOPT_URL => $this->doacao_model->get_dados_asaas()->CURLOPT_URL."payments/".$code,
        CURLOPT_RETURNTRANSFER => true,
        CURLOPT_ENCODING => "",
        CURLOPT_MAXREDIRS => 450,
        CURLOPT_TIMEOUT => 30,
        CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
        CURLOPT_CUSTOMREQUEST => "CREATE",
        CURLOPT_SSL_VERIFYPEER => 0,
        CURLOPT_SSL_VERIFYHOST => 0,
        CURLOPT_HTTPHEADER => [
            "accept: application/json",
            "access_token: ".$token 
        ],
        ]);

        $response = curl_exec($curl);
        $err = curl_error($curl);

        curl_close($curl);

        #limpando codigo

        




    }
