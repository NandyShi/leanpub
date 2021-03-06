
# RIPPLE

{style=poem}
~~~~~~  
 Send money to anyone, anytime anywhere in any currency。
                    -- 瑞波指南

当http被发明时，没人会想到会诞生谷歌或者youtube这样的网站。  
类似，也没人能预测ripple的无限潜能。  
                    -- 瑞波指南 
~~~~~~

## 为什么会有ripple
虽然比特币名气更胜，实际Ripple系统的历史早于比特币。2004年工程师Ryan Fugger的推出了第一版Ripple；后来Mt.Gox的创始人Jed McCaleb，加上曾经在网络金融领域有多年创业经验Chris Larsen，两者共同成立了OpenCoin来接管Ripple，负责运行和维护Ripple的平台。Ripple 致力于打造一个分布式的点对点的支付和交换系统， 且支持任意的币种，无论美元，人民币，比特币都没问题。

T> Ripple Labs的前称是Opencoin，在2013年4月份获得了来自谷歌和IDG的投资之后备受关注。

现在很多公司都在基于现有互联网支付的基础设施进行一些创新，但是在这个过程中遇到很多问题，进而发现现有的基础设施不够用。比如现在的各种独立支付网络相互之间是隔离的，你用支付宝给另一个支付宝转钱很简单，但是如果用另一个支付工具比如财付通就比较困难了。但真正的互联网不是这样的，访问网站可以用任何一个浏览器，但是现在的支付系统不是这样的。

![currency_symbol](http://upload.wikimedia.org/wikipedia/commons/b/b8/Currency-Symbol_Regions_of_the_World_circa_2006.png)


现在的支付和70年代电子邮件的景象类似，如果多家支付系统进行合作，就可以实现跨网络进行支付，但是目前没有一种协议可以让网络之间的支付变得很平常。在邮件的发展过程中有过许多尝试，比如说建立一个超级服务器，让任何东西都通过他们的服务器来解决，但是没有公司成功。而成功的是现在这套开放协议SMTP，它允许大家都介入，从而让跨网络的电子邮件沟通成为了可能。正是这些开放协议的出现，使邮件服务从早期的割据到现在通过一个协议将不同的邮件连接起来，成为一个非常通用的服务。

从IT技术的角度看，支付相对邮件更加困难，因为支付有先后顺序的问题。比方说如果你用你帐户里的钱开了一张支票，又开了另一张支票，但是帐户里的钱只够支付一张支票，就必须要有一张作废，这种情况下需要一个中间机构来决定。比特币的出现解决了这个双重出现问题，Ripple用一个类似的方案也解决了这个问题。Ripple希望能连接各个支付网络，大家可以从一个支付网络给另一个支付网络进行交互，而你的顾客或者你的接受方愿意用什么支付网络都没有关系。

在日常生活中，比方说一个人想给另一个人发钱，愿意支付这一方只有一个支付宝帐户，另一方有一个美国银行的帐户，这是一个很常见行不通的情形，钱没法过去，中间有一个障碍。通常，大家会进行一个操作，找一个中间人，然后这个中间人可以既有美元、美国银行帐户，也有支付宝帐户。他愿意帮你把美元付出去，也愿意支付宝结算。

如果你用Ripple完成上面所描述的支付过程，很重要一点就是你不需要相信中间人，它不仅能帮你把美元发出去，也能接受人民币。Ripple这个网络就会让你的两笔转帐同时发生，中间人可以是陌生人，也可以就是做事的机构，但是你完全不需要信任它。另外由于Ripple的中间人省去了谈价格这个过程，并且这个网络是一套协议，它会自动给你找最优的价格。比方说用人民币兑换美元，它有可能基于现在的网络情况，用人民币换成比特币，再换成美元。这样得到的价格比较合理，这个网络自动帮你执行这样一个过程。然后有很多很复杂的路径，这些都是网络自动选取的。

总体来看，Ripple省略了找中间人这一个步骤。而跨国支付的问题，Ripple并不是不需要中间人，而是中间人隐藏在网络这套协议当中，而且它解决了信用问题。

## 原理概述
Ripple 系统的核心是一个共享的公共的数据库， 它包含一个总帐簿存着所有账户的收支信息，所有人都可以查看这个帐簿，任意账户的每一笔帐目往来。此外，帐簿还存有买卖信息，你可以买卖某种货币或资产，从而实现了一个分布式的兑换系统。每一个该网络的使用者都必须通过某种方式达成共识，最后一致同意对总帐簿进行修改，我们把这种过程叫做共识(consensus)。共识每2至5秒钟就进行一次，这样我们不需要集中化的清算系统，也可以进行交易。

![ledger](https://ripple.com/wp-content/uploads/2013/02/ledger.png)

现代的货币体系都是基于信用的，如现金和债券都有国家信用担保。对存在银行中的钱来说更是如此，你有100元存在银行意味着只要你需要，你就可以取出这100元，国家信用担保。Ripple使用类似的信用体系，只是信用不是来自国家，而是一个全球的公共的分布式在线帐簿（以及你自己对特定网关的信任），该帐簿由一个运行ripple服务器软件的点对点网络共同维护。为了使每个节点的帐簿保持一致，之前描述的共识过程会持续进行。总帐簿包含每一笔借贷记录： 谁借了另一个人多少钱，是什么币种，什么时候发生的。法定货币在ripple系统中是以虚拟货币（IOU）的形式记录的，所有每一个账户的虚拟货币结余由账户所有的借贷交易共同决定。

Ripple系统有一个重要的概念叫网关，它的作用有点像银行，接受用户现实中的法定货币并转化其ripple的账户中的虚拟货币(IOU)。例如你在网关中存一万元人民币，网关会在ripple系统中给你发行等量的虚拟人民币，表示你在网关中有一万块人民币，你可以提取，兑换或支付给别人。*与银行不同的是，该账簿不是银行私有的会计帐本，而是全球公享的一个在线总帐*。这样，ripple网络就和外部世界连接起来了。虽然网关这个概念一般用来称呼往ripple系统中存取钱的商业机构，实际上它和别的ripple账户没有什么不同，只要别人愿意信任你，任何人都可以作为一个网关。

![consensus](https://ripple.com/wp-content/uploads/2012/12/consensus1.png)

W> 选择网关时一定要非常谨慎，因为不像瑞波币是整个ripple网络通用的，某网关发行的虚拟货币一般**只能在该网关交易和提现**,建议只信任 ripple 官方推荐的网关。

当支付行为在ripple中发生时，不同账户间的虚拟货币余额会自动调整，来体现这笔交易。但记住，ripple系统只负责帐簿的记录，它并不能强制网关（或其他参与者）履行提现义务，所以ripple用户必须十分小心，你只有真正信任另一个用户时，才告诉系统你只信任哪个账户，信任的币种是什么，额度是多少。这中ripple系统中叫信任链。当付款人和收款人直接没有直接相连的信任链时，ripple会查找有没有连通的间接信任链，撮合交易使其成功。一个交易会像波纹一样沿着信任链扩散出去，直到到达接收者。最后，总帐簿显示的是所有货币余额，你就可以按需中网关那里体取现金或还款。

I> 六度空间理论表明，一个人通过社交链找到世界上的另一个人，中间人个数不超过六个。Ripple信任链的工作原理和六度空间类似。

除了借助系统中的信任链，Ripple也允许外部的交易商交易不同网关发行的货币借贷，这样，即使某笔支付找不到一条信任链促成交易，也可以在外部交易商的帮助下完成交易。

为了防止单点故障及有人试图控制ripple币，ripple被设计成一个分布式的系统，任何人，包括 Ripple Labs 都不能控制系统，除非征得大多数节点的一致同意。

## ripple币，比特币 2.0?
除了分布式的支付和交换系统，ripple也有自己的货币，瑞波币。Ripple网络的使用者并不一定需要使用瑞波币，系统支持任意的货币。 作为 ripple 系统的内置货币，瑞波币与其他货币有一些不同。它限量发行1000亿个，每一个ripple网络的参与者都支持瑞波币，这就避免了交易对手风险。而其它货币在ripple中表现为虚拟货币，你可以使用虚拟货币在 ripple 系统中交易，但你需要提防交易对手违约或者欺诈的风险(主要是网关)。瑞波币还有一些额外的作用。

### 防止 ripple 网络被滥用
**防止交易泛滥**。 为防止系统受到分布式拒绝服务攻击(DDOS),对每一笔交易，系统都会收取很少量的，正常情况下可以忽略的瑞波币作为交易费用。但如果系统负载太高，比如受到攻击，这个费用会被临时提高，使得攻击者负担不了高额的交易费用而不得不停止攻击。
 
**防止总帐增长太快**。 系统会跟踪系统中账户的状态，账户每使用一次系统资源，必须保留一定的 ripple 币作为保证金，交易成功时保证金退回。这样就防止某些账户无节制的提交很多交易，滥用系统资源造成总帐簿过膨胀。

### 作为中间货币
如果没有中间货币，你可能要将人民币换成日元，再换成欧元，再换成目标货币美元，甚至中间还会有更多的链条。瑞波币的存在使得任意两种货币的兑换都至多只经过一次转换即可。下面几个因素让 ripple 币成为理想的中间货币：
**最高的流动性**。没有中间环节，没有交易费用，你可以直接将货币付给另一个账户。

**没有交易对手风险**。瑞波币是ripple系统内置的货币，在系统内可以全流通而不需要信任链。

**不能超发**。Ripple网络创建时，1000亿瑞波币即创建好了，创始人保留了一部分，其余800亿瑞波币被授权给 ripple labs 公司用来发展 ripple 系统。

T> 货币只有流通和使用才有价值，故Ripple Labs会通过慈善，赠送等有意义的渠道分发瑞波币。

###　最小单位－滴
 瑞波币的最小单位是滴，一个瑞波币等于一百万滴瑞波币。现在系统会对每次交易收取10滴瑞波币作为交易费用，这10滴瑞波币会被摧毁掉。一个瑞波币就够一个账户做10万个交易了，所以这个设置看上去不错。如果瑞波币升值了，也可以通过共识过程降低交易费用。


