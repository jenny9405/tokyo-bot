
# tokyo-bot
Tokyo Telegram Bot

# Repository Info

* Project Name : Tokyo-bot
* Project Owner : Kevin
* Project Maintainer : Jenny
* Project Reviewer : Jenny

# Contents

## [questions for dialog with bot](questions.json)
```
{
   "_comment":[
      "Tokyo-bot questions",
      "https://github.com/Onther-Tech/tokyo-schema을 기준으로 만들어짐",
      "ICO 삼위일체 불가능성 중, 토큰의 사후적 분배율과 토큰의 판매가 결정되는 모델을 기준으로 작성(토큰 발행량은 유동적)"
   ],
   "General":{
      "message":{
         "triple_dilemma":"(a)토큰 발행량, (b)토큰의 사후적 분배율, (c)토큰 판매가의 세 가지가 동시에 정해질 수 없다는 ICO삼위일체불가능성에 대해서 알고 계신가요?",
         "project_name":"프로젝트 이름은 무엇인가요?"
      }
   },
   "Token":{
     "_comment" : {
       "not_implemented" : {
         "no_mint_after_sale":"토큰의 추가 발행이 가능한 토큰(Mintable)"
        }
       },
      "message":{
         "token_name":"토큰의 이름은 무엇인가요?",
         "symbol":"토큰의 심볼은 무엇인가요?",
         "is_minime":"특정 블록높이를 기준으로 잔액 분포를 알 수 있는 토큰(Minime)",
         "decimal":"토큰의 소수점은 몇 번째 자리수까지 인가요?",
         "burnable":"사용자가 본인의 토큰을 태워 없애는 기능이 필요한가요?",
         "pausable":"관리자가 토큰의 전체 전송을 일시정지하는 기능이 필요한가요?",
         "new_owner":"세일이 끝난 후 토큰의 ownership을 가질 지갑 주소를 적어주세요."
       }
   },
   "Stage":{
      "_comment":[
         "스테이지 : 스테이지란 프리세일, 퍼블릭 세일 등으로 나눠지는 구간을 말한다. 구간과 구간 사이를 멀리 둘 수 있다.",
         "m - 총 스테이지",
         "m_n - m개중 n번째 스테이지"
      ],
      "message":{
         "total_num_stages":"총 세일 기간동안 몇 개의 스테이지로 나눠서 진행하나요?",
         "n_stage_start_time":"n번째 스테이지의 시작 시간은 언제인가요?",
         "n_stage_end_time":"n번째 스테이지의 종료 시간은 언제인가요?",
         "n_stage_hardcap":"n번째 스테이지의 하드캡을 비율로 적어주세요(별도의 캡이 없는 경우 0으로 설정해주세요)",
         "n_stage_max_purchase_limit":"n번째 스테이지의 최대 구매 가능 금액을 적어주세요",
         "n_stage_min_purchase_limit":"n번째 스테이지의 최소 구매 가능 금액을 적어주세요",
         "n_stage_is_kyc":"n번째 스테이지는 KYC를 하나요?",
         "_comment":{
            "total_num_stages":"m결정"
         }
      }
   },
   "Crowdsale":{
      "_comment":[
         "*****크라우드세일의 도중 오너키가 분실되었을 경우의 문제에 관한 항목 필요*****"
      ],
      "message":{
         "ether_hardcap":"ICO의 하드캡은 몇 이더인가요?",
         "ether_softcap":"ICO의 소프트캡은 몇 이더인가요?",
         "start":"ICO의 시작일은 언제인가요?",
         "end":"ICO의 종료일은 언제인가요?",
         "base_rate":"기본가격은 얼마인가요?(1이더당 토큰 발행량)",
         "ether_max_purchase_limit":"1계정당 최대 구매 가능 금액은 얼마인가요?",
         "ether_min_perchase_limit":"1계정당 최소 구매 가능 금액은 얼마인가요?",
         "purchase_interval":"토큰 재구매 가능한 블록 간격을 적어주세요"
      }
   },
   "PeriodBonusStage":{
      "_comment":[
         "m - 총 구간 갯수",
         "m_n - m개중 n번째 구간"
      ],
      "message":{
         "num_bonuses":"몇 개의 기간별 보너스 구간이 있나요?",
         "n_end_time":"n번째 스테이지에 y번째 보너스 구간의 종료 시간을 적어주세요.",
         "n_bonus_rate":"n번째 스테이지에 y번째 보너스 구간의 보너스 퍼센트를 적어주세요.",
         "_comment":{
            "num_bonuses":"m결정",
            "n_end_time":"m번 반복",
            "n_bonus_rate":"m번 반복"
         }
      }
   },
   "AmountBonusStage":{
      "_comment":[
         "z - 총 z개의 구매 수량 보너스 구간",
         "z_k = 총 z개의 구간 중 k번째 보너스 구간 : 1번째는 가장 큰 보너스, k번째는 가장 작은 보너스 구간"
      ],
      "message":{
         "is_amount_bonus":"구매 수량 보너스가 있나요?",
         "num_amount_bonus":"몇 개의 수량 보너스 구간이 있나요?",
         "k_amount":"k번째 구매 수량 보너스의 수량을 적어주세요(큰 보너스 --> 작은 보너스 순, 큰 보너스 부터)",
         "k_bonus":"k번째 구매 수량 보너스의 퍼센트를 적어주세요(큰 보너스 --> 작은 보너스 순, 큰 보너스 부터)",
         "_comment":{
            "num_amount_bonus": "z결정",
            "k_amount":"z번 반복",
            "k_bonus":"z번 반복"
         }
      }
   },
   "Multisig":{
      "_comment":[
         "m개의 멀티시그 지갑 사용",
         "n번째 멀티시그 지갑",
         "n_x : n번째 멀티시그 지갑의 x개의 오너 EOA 갯수",
         "n_x_y : n번째 멀티시그 지갑의 x개의 오너 중 y번째 EOA"
      ],
      "message":{
         "is_multisig":"멀티시그니처 기능을 사용하나요?",
         "num_multisig":"몇개의 멀티시그 지갑을 쓸 건가요?",
         "n_num_owner":"n번째 멀티시그 지갑의 오너 계정은 몇개인가요?",
         "n_num_required":"오너 계정 중 몇개의 계정이 동의해야 출금 가능한가요?",
         "n_y_owner":"n번째 멀티시그 지갑의 y번째 오너 계정을 적어주세요(이더리움 계정)",
         "_comment":{
            "num_multisig":"m결정",
            "n_y_owner":"x번 반복"
         }
      }
   },
   "Locker":{
      "_comment":[
         "Locker for token",
         "m개의 락커 사용",
         "n번째 락커",
         "n_x : n번째 락커로부터 토큰을 받는 총 x개의 계정",
         "n_x_y : n번째 락커로부터 토큰을 받는 총x개의 계정 중 y번째 계정",
         "n_x_y_i : n번째 락커로부터 토큰을 받는 총x개의 계정 중 y번째 계정의 i번째 릴리즈 구간"
      ],
      "message":{
         "use_locker":"토큰을 보관해 두었다가 특정 기간에 릴리즈하는 Locker 기능이 필요한가요?",
         "num_locker":"몇 개의 락커가 필요한가요?",
         "n_num_owner":"m개의 락커 중 n번째 락커의 토큰을 받을 계정은 몇개인가요?",
         "y_is_multisig":"x개의 계정 중 y번째 계정은 <멀티시그> 인가요 <EOA>인가요?",
         "y_multisig_num":"(멀티시그라면) n번째 락커에서 y번째 계정으로 쓸 멀티시그 지갑을 선택해주세요",
         "y_eoa_address":"(EOA라면) n번째 락커에서 y번째 계정으로 쓸 EOA 어카운트를 적어주세요",
         "n_y_distribution_ratio":"n번 락커의 y번째 계정은 락커가 보유한 토큰의 몇 퍼센트를 가져가나요?",
         "n_y_release_type":"n번 락커의 y번째 계정의 릴리즈 타입은?(#1 : 계단형, #2 : 선형)",
         "n_y_num_release":"n번 락커의 y번째 계정은 몇 번의 기간에 걸쳐 릴리즈를 하나요?",
         "n_y_i_end_time":"n번 락커의 y번째 계정의 i번째 구간의 릴리즈 종료 시간을 설정해주세요",
         "n_y_i_release_ratio":"n번 락커의 y번째 계정의 i번째 구간의 릴리즈 비율을 설정해 주세요",
         "_comment":{
            "num_locker":"m결정",
            "m_num_owner":"m번 반복, x결정",
            "y_is_multisig":"x번 반복",
            "y_multisig_num":"x번 반복(아래항과 합쳐서)",
            "y_eoa_address":"x번 반복(위항과 합쳐서)",
            "n_y_num_release":"i결정",
            "n_y_i_end_time":"i번 반복",
            "n_y_i_release_ratio":"i번 반복, 릴리즈 ratio는 누적%"
         }
      }
   },
   "TokenDistribution":{
      "_comment":[
         "Token Distribution",
         "m : 크라우드 세일을 제외하고 토큰을 받는 어카운트 갯수",
         "n : m개의 어카운트 중 n번째 어카운트"
      ],
      "message":{
         "crowdsale_token_ratio":"크라우드세일을 통해 판매되는 토큰은 몇 퍼센트 인가요?",
         "num_account_distribution":"크라우드 세일 이외에 토큰이 분배되는 계정의 갯수는 몇개인가요?",
         "n_account_type":"m개 중 n번째 계정의 종류는 무엇인가요?(락커, EOA)",
         "n_eoa_address":"(n번째 계정이 EOA일 경우)주소를 입력 해 주세요",
         "n_multisig_num":"(n번째 계정이 multisig일 경우)번호를 입력 해 주세요",
         "n_account_ratio":"m개 중 n번째 계정이 전체 토큰 발행량 중 가져가는 비율은?",
         "_comment":{
            "num_account_distribution":"m결정"
         }
      }
   },
   "EtherDistribution":{
      "_comment":[
         "Ether Distribution",
         "m : m개의 주소에 통해 이더를 보관",
         "n : n번째 주소를 통해 이더를 보관"
      ],
      "message":{
         "num_account":"몇 개의 주소에 이더를 보관하나요?",
         "n_account_type":"m개의 주소 중 n번째 계정의 종류는?(1.EOA 2.멀티시그)",
         "n_account_eoa_address":"(EOA라면)m개 중 n번째의 주소(address)를 적어주세요",
         "n_multisig_num":"(멀티시그라면)m개 중 n번째의 멀티시그 월렛 번호(앞에서 만든)를 적어주세요",
         "n_account_distribution_ratio":"m개의 주소 중 n번째 주소의 할당량을 적어주세요",
         "_comment":{
            "num_account":"m결정",
            "n_account_type":"m번 반복",
            "n_account_eoa_address":"(아래것과 합쳐서) m번 반복",
            "n_multisig_num":"(위의것과 합쳐서) m번 반복",
            "n_account_distribution_ratio":"m번 반복"
         }
      }
   }
}
```

## Install

```
$ git clone https://github.com/Onther-Tech/tokyo-bot.git
$ cd tokyo-bot && npm install
```

For your test,
Replace [TOKEN](https://github.com/Onther-Tech/tokyo-bot/blob/master/test.js#L4)

or make config.json in root directory

```
//config.json
{
  "TOKEN" : "<BOT ACCESS TOKEN>"
}

```

## Running

```
$ node tokyo-bot.js
```

## Reference
* [Bot-brother](https://github.com/SerjoPepper/bot-brother)
* [Bot source code reference](https://github.com/SerjoPepper/delorean_bot/blob/master/src/bot.js)
* [Tokyo Schema](https://github.com/Onther-Tech/tokyo/tree/master/packages/tokyo-schema)
* [Joi](https://github.com/hapijs/joi)

## etc..

# license

Apache 2.0
