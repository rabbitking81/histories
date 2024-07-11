# FANTO
  - 백서 : https://docs.fanto.io/

## 프로젝트 구성
- fanto-web : 웹어플리케이션
- fanto-core : 스마트컨트랙트
- fanto-serverless : REST API 서버 (시세 조회용)
- fanto-discordbot : 디스코드봇


### Contracts
 주요 기능들은 아래와 같이 구분됩니다.
  - 크리에이터 정보 관리
  - 토큰 스왑
  - 보상
  - 토큰 베스팅 + 에어드랍

  **주요 컨트랙트**
   - creator/CreatorFactory.sol
        - Fanto 프로젝트에서 활동하는 크리에이터의 정보를 저장하고 관리하는 컨트랙트
        - 이 컨트랙트에는 토큰주소와 크리에이터 지갑주소만 저장하고, 그 외 부가적인 메타정보(이름, 설명, 이미지 주소, 소셜 미디어 정보 등)는 IPFS 관리함
   - farm/FantoFarm.sol
        - MasterChef.sol 기반으로 개발
        - 기본적인 로직은 MasterChef와 동일하며 특정 기간동안에는 보상을 2배로 지급하는 기능이 추가되었음
        - 보상에 사용되는 토큰은 miningTreasury로부터 지급되게 되어있음 
- interfaces/\*.sol
            - 공통으로 사용되는 인터페이스들
- libraries/\*.sol
  - 공통으로 사용되는 라이브러리들
- swap/\*.sol
  - 스왑에 사용되는 컨트랙트들
  - Uniswap V2 기반으로 개발되었음
- token/CT
  - CreatorToken.sol
    - Fanto 프로젝트의 크리에이터 토큰 컨트랙트
    - 프로젝트 내 크리에이터 수만큼의 컨트랙트가 배포됨
  - CTMiningTreasury.sol
    - 크리에이터 토큰 구매시 사용자에게 전송될 토큰을 가지고 있는 컨트랙트
- token/FTN
  - FantoToken.sol
    - Fanto 프로젝트의 거버넌스 토큰(FTN) 컨트랙트
  - MiningTreasury.sol
    - 보상(FantoFarm)에 사용할 토큰을 가지고 있는 컨트랙트
- token/WKLAY.sol
  - Wrapped KLAY
- vesting/FantoAirdrop.sol
  - 에어드롭 대상자 지갑 주소과 금액을 저장하고 클래임 할 수 있는 기능을 제공하는 컨트랙트
- vesting/FantoVestingWallet.sol
  - Vesting Wallet 컨트랙트로 아래의 OpenZeppelin 구현체를 기반으로 개발
  - [https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.6.0/contracts/finance/VestingWallet.sol](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.6.0/contracts/finance/VestingWallet.sol)
- vesting/FantoVestingWalletV2.sol
  - Revoke 및 기타 관리용 기능이 추가된 VestingWallet
  - 위의 FantoVestingWallet과 FantoVestingWalletV2 둘 중 하나를 사용할 예정


### [주요 컨트랙트 주소 모음](https://docs.fanto.io/contract/contract-addresses)
