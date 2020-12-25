# 卓越运营支柱--良好架构框架

## 摘要
本文的重点是 Well-Architected Framework 的卓越运营支柱。它提供指导，帮助您在设计、交付和维护云上工作负载时应用最佳实践。

## 介绍
Well-Architected Framework 可帮助您了解在云上构建工作负载时所做决策的收益和风险。通过使用该框架，您将学习在云中设计和运行可靠、安全、高效和具有成本效益的工作负载的运营和架构上的最佳实践。它提供了一种方法，可以根据最佳实践持续衡量您的运营和架构，并识别需要改进的领域。我们相信，拥有架构良好的工作负载，并在设计时考虑到运营，将大大提高业务成功的可能性。

本文重点介绍卓越运营支柱，以及如何将其作为架构完善的解决方案的基础。在运营被认为是一个与它所支持的业务线和开发团队隔离和不同的功能的环境中，实现卓越运营具有挑战性。通过采用本文中的实践，您可以构建能够深入了解其状态的架构，启用有效和高效的运营和事件响应，并可以持续改进和支持您的业务目标。

本文的读者对象是从事技术工作的人员，如首席技术官（CTO）、架构师、开发人员和运营团队成员。阅读本文后，您将了解 AWS 最佳实践以及在设计云架构以实现卓越运营时应使用的策略。本文不提供实施细节或架构模式。但是，它确实包含了对这些信息的适当资源的参考。

## 卓越运营

卓越运营支柱包括您的组织如何支持您的业务目标、有效运行工作量的能力、深入了解其运营情况，以及不断改进支持流程和程序以实现业务价值。

### 设计原则

云计算中的卓越运营有五个设计原则。

以代码的方式执行操作。在云中，你可以将用于应用代码的工程纪律应用到整个环境中。您可以将您的整个工作负载（应用程序、基础设施等）定义为代码，并通过代码进行更新。您可以为您的操作程序编写脚本，并通过响应事件触发它们来自动执行它们。通过以代码形式执行操作，您可以限制人为错误，并实现对事件的一致响应。

进行频繁的、小的、可逆的更改。设计工作负载以允许组件定期更新，以增加有益的变化流入你的工作负载。以小的增量进行更改，如果更改失败，可以逆转，以帮助识别和解决引入到您的环境中的问题（尽可能不影响客户）。

经常完善操作程序。当你使用操作程序时，寻找改进的机会。随着您的工作量的发展，适当地发展您的程序。设置定期的游戏日，审查和验证所有程序是否有效，团队是否熟悉这些程序。

预测失败。进行 "死前 "演习，以确定潜在的失败来源，从而可以消除或减轻它们。测试您的故障场景，并验证您对其影响的理解。测试您的响应程序，以确保它们是有效的，并确保团队熟悉它们的执行。设置定期的游戏日，以测试工作负荷和团队对模拟事件的响应。

从所有的运营失败中学习。通过从所有操作事件和失败中吸取经验教训来推动改进。在各团队之间并通过整个组织分享所学到的东西。

### 定义

云计算中的卓越运营由四个方面组成。

组织

准备

操作

发展

你的组织的领导层确定了业务目标。你的组织必须理解要求和优先事项，并利用这些要求和优先事项来组织和开展工作，以支持业务成果的实现。您的工作负载必须发出必要的信息来支持它。实施服务以实现您的工作负载的集成、部署和交付，将使重复性流程自动化，从而使有益的变化更多地流入生产。

您的工作负载的运行可能存在固有的风险。您必须了解这些风险，并做出进入生产的明智决定。您的团队必须能够支持您的工作量。从期望的业务结果中得出的业务和运营指标将使您能够了解您的工作量的健康状况、您的运营活动，并对事故作出反应。您的优先级会随着您的业务需求和业务环境的变化而变化。将这些作为一个反馈循环，不断推动您的组织和工作量的运行改进。

## 组织
你需要了解你的组织的优先事项、组织结构，以及你的组织如何支持你的团队成员，以便他们能够支持你的业务成果。

为了实现卓越运营，你必须了解以下内容。

课题

本组织的优先事项
运作模式
组织文化

### 本组织的优先事项

你的团队需要对你的整个工作量、他们在其中的角色以及共同的业务目标有一个共同的理解，以确定优先事项，从而使业务成功。明确的优先级将使你的工作效益最大化。定期审查你的优先事项，以便随着需求的变化而更新。

评估外部客户需求。让关键的利益相关者参与进来，包括业务、开发和运营团队，以确定在外部客户需求方面的工作重点。

评估内部客户需求。让关键的利益相关者，包括业务、开发和运营团队参与进来，以确定在内部客户需求方面的工作重点。

评估客户需求将确保您对实现业务成果所需的支持有一个全面的了解。

使用您既定的优先事项，将您的改进工作集中在能够产生最大影响的地方（例如，发展团队技能、提高工作量性能、降低成本、自动化运行簿或加强监控）。随着需求的变化，更新您的优先事项。

评估治理要求。确保你了解你的组织所定义的准则或义务，这些准则或义务可能会规定或强调特定的重点。评估内部因素，如组织政策、标准和要求。验证你是否有机制来识别治理的变化。如果没有确定治理要求，确保你已经对这一判断进行了尽职调查。

评估外部合规要求。确保你了解可能授权或强调特定重点的准则或义务。评估外部因素，如监管合规要求和行业标准。验证你是否有机制来识别合规要求的变化。如果没有识别出合规性要求，确保你已经对这一判断进行了尽职调查。

如果有适用于您的组织的外部监管或合规性要求，您应该使用AWS云合规性提供的资源来帮助教育您的团队，以便他们能够确定对您的优先事项的影响。

评估威胁状况。评估对业务的威胁（例如，竞争、业务风险和负债、运营风险和信息安全威胁），并在风险注册表中维护当前信息。在确定工作重点时，要将风险的影响纳入其中。

架构良好的框架强调学习、衡量和改进。它为您提供了一个一致的方法来评估架构，并实施将随着时间推移而扩展的设计。AWS提供了AWS Well-Architected工具，帮助您在开发前审查您的方法，在生产前审查您的工作负载状态，以及在生产中审查您的工作负载状态。您可以将它们与最新的 AWS 架构最佳实践进行比较，监控您的工作负载的整体状态，并深入了解潜在的风险。

企业支持客户有资格获得对其任务关键型工作负载的指导性 "良好架构审查"，以根据 AWS 最佳实践衡量其架构。

他们也有资格获得运营审查，该审查旨在帮助他们确定在云中运营的方法中存在的差距。

这些审查的跨团队参与有助于建立对您的工作负载以及团队角色如何促进成功的共同理解。通过审查确定的需求可以帮助形成您的优先事项。

AWS Trusted Advisor 是一个工具，它提供了对核心检查集的访问权限，这些检查推荐的优化可能有助于形成您的优先事项。业务和企业支持客户可获得侧重于安全、可靠性、性能和成本优化的额外检查，这些检查可进一步帮助塑造其优先事项。

评估折衷方案。评估竞争利益或替代方法之间权衡的影响，以便在确定运营工作的重点或选择行动方案时做出明智的决定。例如，可能会强调加快新功能的上市速度，而不是成本优化，或者您可能会为非关系型数据选择关系型数据库，以简化迁移系统的工作，而不是迁移到针对您的数据类型优化的数据库并更新您的应用程序。

AWS可以帮助您教育您的团队了解AWS及其服务，以提高他们对其选择如何对您的工作负载产生影响的理解。您应该使用 AWS 支持提供的资源（AWS 知识中心、AWS 讨论表和 AWS 支持中心）和 AWS 文档来教育您的团队。通过AWS支持中心联系AWS支持，以帮助您解决AWS问题。

AWS 还在 The Amazon Builders' Library 中分享了我们在运营 AWS 过程中了解到的最佳实践和模式。其他各种有用的在

### Operating Model
### Organizational Culture


## Prepare
### Design Telemetry
### Design for Operations
### Mitigate Deployment Risks
### Operational Readiness

## Operate
### Understanding Workload Health
### Understanding Operational Health
### Responding to Events

## Evolve
### Learn, Share, and Improve

## Conclusion

Operational excellence is an ongoing and iterative effort.

Set up your organization for success by having shared goals. Ensure that everyone understands their part in achieving business outcomes and how they impact the ability of others to succeed. Provide support for your team members so that they can support your business outcomes.

Every operational event and failure should be treated as an opportunity to improve the operations of your architecture. By understanding the needs of your workloads, predefining runbooks for routine activities, and playbooks to guide issue resolution, using the operations as code features in AWS, and maintaining situational awareness, your operations will be better prepared and able to respond more effectively when incidents occur.

Through focusing on incremental improvement based on priorities as they change, and lessons learned from event response and retrospective analysis, you will enable the success of your business by increasing the efficiency and effectiveness of your activities.

AWS strives to help you build and operate architectures that maximize efficiency while you build highly responsive and adaptive deployments. To increase the operational excellence of your workloads, you should use the best practices discussed in this paper.
