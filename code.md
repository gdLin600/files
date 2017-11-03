### 退单

// 当退单申请的成人及儿童数量与订单上的成人及儿童数量相等时则为全退

        // 否则为部分退

        // 获取所有的订单子订单的退单信息

        //TODO

        /\*  Long orderNo = orderBackApply.getOrderNo\(\);

        responseEntity = getOrderUnsubscribeInfos\(param\);

        if \(CommonUtil.isFailue\(responseEntity\)\) {

            return responseEntity;

        }

        Map&lt;String, Object&gt; queryMap = new HashMap&lt;String, Object&gt;\(\);

        queryMap.put\("orderNo", orderNo\);

        String queryStr = JSON.toJSONString\(queryMap\);

        responseEntity = checkOrder\(queryStr \);

        if \(CommonUtil.isFailue\(responseEntity\)\) {

            return responseEntity;

        }

        Object data = responseEntity.getData\(\);

        Order order = CommonUtil.fromJson\(JSON.toJSONString\(data\), Order.class, responseEntity\);

        if \(CommonUtil.isFailue\(responseEntity\)\) {

            return responseEntity;

        }

        OrderSubDto dto = new OrderSubDto\(\);

        dto.setOrderNo\(order.getOrderNo\(\)\);

        // 验证  子订单

        List&lt;OrderSub&gt; orderSubList = orderSubService.getList\(dto \);

        // 是否订单全退

        boolean flag = Boolean.TRUE;

        for \(OrderSub orderSub : orderSubList\) {

            responseEntity = orderBackApplyService.getOrderBackApplyVos\(orderSub.getSubOrderNo\(\)\);

            if \(CommonUtil.isFailue\(responseEntity\)\) {

                throw new RuntimeException\(responseEntity.getMsg\(\)\);

            }

            data = responseEntity.getData\(\);

            List&lt;OrderBackApplyVo&gt; orderBackApplyVos = CommonUtil.fromJsonToList\(JSON.toJSONString\(data\), new TypeReference&lt;List&lt;OrderBackApplyVo&gt;&gt;\(\) {

            }, responseEntity\);

            if \(CommonUtil.isFailue\(responseEntity\)\) {

                throw new RuntimeException\(responseEntity.getMsg\(\)\);

            }

            // 子订单成人数量

            Integer adultNo = orderSub.getAdultNo\(\);

            // 子订单儿童人数

            Integer childNo = orderSub.getChildNo\(\);

            // 一个子订单所有的申请的成人数量

            Integer orderBackApplysAdultNum = 0;

            // 一个子订单所有的申请的儿童数量

            Integer orderBackApplysChildNum = 0;

            for \(OrderBackApplyVo orderBackApplyVo : orderBackApplyVos\) {

                orderBackApplysAdultNum+=orderBackApplyVo.getAdultNum\(\);

                orderBackApplysChildNum+=orderBackApplyVo.getChildNum\(\);

            }

            // 有一个

            if \(flag&&!\(adultNo.intValue\(\) == orderBackApplysAdultNum.intValue\(\)&&childNo.intValue\(\) == orderBackApplysChildNum.intValue\(\)\)\) {

                flag = Boolean.FALSE;

            }

        }

     

//        List&lt;OrderBackApplyVo&gt; 

        data = responseEntity.getData\(\);

        if \(ValidateUtils.isEmpty\(data\)\) {

            return responseEntity.failure\("获取订单的订单申请信息失败!"\);

        }

        List&lt;OrderBackApplyVo&gt; orderBackApplyVos = CommonUtil.fromJsonToList\(JSON.toJSONString\(data\), new TypeReference&lt;List&lt;OrderBackApplyVo&gt; &gt;\(\) {

        }, responseEntity\);

        if \(CommonUtil.isFailue\(responseEntity\)\) {

            return responseEntity;

        }\*/

        

        /\*// 成人人数

        Integer adultNum = order.getAdultNum\(\);

        // 儿童人数

        Integer childNum = order.getChildNum\(\);

        // 当flag 为ture 时  则不是全退

        boolean flag = Boolean.FALSE;

        for \(OrderBackApplyVo orderBackApplyVo : orderBackApplyVos\) {

            flag = orderBackApplyVo.getAdultNum\(\).intValue\(\) != adultNum.intValue\(\) \|\| orderBackApplyVo.getChildNum\(\).intValue\(\) != childNum.intValue\(\);

            if \(flag\) {

                break;

            }

        }

       // 当flag 为 FALSE 则是全退

        if \(!flag\) {

            

        }\*/

