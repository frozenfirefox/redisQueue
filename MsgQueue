<?php
    /*****************************************************************************

                                简单消息队列redis实现：
                                @author Alpha
                                @date 2018/08/01
                                @params $host, $port

    *****************************************************************************/
    class MsgQueue{
        protected $_server = null;

        protected __construct($host = '127.0.0.1', $port = 6379){
            $this->_server = new \Redis();
            $result = $this->_server->connect('127,0,0,1', 6379);
            if($result){
                $this->_server = null;
            }
        }

        public function _set($key, $val){
            $res = $this->_server->lPush($key, $val);
            printf("入队：%s", $res);
        }

        public function _get($key){
            $res = $this->_server->rPop($key);
            printf("出队：%s", $res);
        }
    }
