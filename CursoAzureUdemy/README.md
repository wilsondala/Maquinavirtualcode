[Hands-On] Instalando Azure CLI no Ubuntu Linux
 Para instalar o Azure CLI em estacao com Ubuntu Linux precisamos seguir os seguintes passos:



Obter os pacotes necessários para o processo de instalação:



#  sudo apt-get update
# sudo apt-get install ca-certificates curl apt-transport-https lsb-release gnupg


Baixar e instalar a chave de autenticação da Microsoft:

# curl -sL https://packages.microsoft.com/keys/microsoft.asc |
   #  gpg --dearmor |
    sudo tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null


Adicionar o repositório de software da CLI do Azure:

# AZ_REPO=$(lsb_release -cs)
#  echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" |
    sudo tee /etc/apt/sources.list.d/azure-cli.list


Atualizar as informações do repositório e instale o pacote azure-cli:



# sudo apt-get update
# sudo apt-get install azure-cli



/* Estilizar setas de navegação */
.slick-prev, .slick-next {
    background-color: #000;
    border-radius: 50%;
    padding: 10px;
}

/* Estilizar pontos de navegação */
.slick-dots li button:before {
    color: #000;
}



selector .swiper-container{
    width: 100%;
    height: 100%;
    overflow: hidden;
}
selector .swiper-wrapper{
    display: flex;
    animation: infiniteSlide 30s linear infinite;
}
@keyframes infiniteSlide {
    from {
        transform: translateX(0%);
    }
    to {
        transform: translateX(-100%);
    }
}


AVISO LEGAL: As informações fornecidas através deste site e dos serviços associados ao Método Supremo são apenas para fins educacionais e informativos.
Ao utilizar nosso site e serviços, você concorda com os termos deste aviso legal. Se você não concorda com estes termos, por favor, não utilize nosso site ou serviços.
TERMOS DE USO E POLITICA DE PRIVACIDADE

https://charmecheiroso.com.br/politica-de-privacidade/