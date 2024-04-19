# zenz94.github.io

{
	"info": {
		"_postman_id": "1f9f0cbe-be41-43ef-9850-20bcf366eee6",
		"name": "bitcoin",
		"description": "Connecting Postman to a bitcoin node.",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
	},
	"item": [
		{
			"name": "Blockchain",
			"item": [
				{
					"name": "getblockhash",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblockhash\",\n    \"params\": [\n        {{height}}\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# `getblockhash`\nReturns hash of block in best-block-chain at height provided.\n\n## Argument #1 - height\nType: numeric, required\n\nThe height index"
					},
					"response": []
				},
				{
					"name": "getbestblockhash",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getbestblockhash\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# `getblockhash`\nReturns hash of block in best-block-chain at height provided.\n\n## Argument #1 - height\nType: numeric, required\n\nThe height index"
					},
					"response": []
				},
				{
					"name": "gettxout",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"gettxout\",\n    \"params\": [\n        \"{{txid}}\",\n        {{vout}},\n        {{include_mempool}}]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# gettxout\n`gettxout \"txid\" n ( include_mempool )`\n\nReturns details about an unspent transaction output.\n\n## Argument #1 - txid\n**Type**: string, required\n\nThe transaction id\n\n## Argument #2 - n\n**Type**: numeric, required\n\nvout number\n\n## Argument #3 - include_mempool\n**Type**: boolean, optional, default=true\n\nWhether to include the mempool. Note that an unspent output that is spent in the mempool won’t appear.\n\n## Result\n```\n{                             (json object)\n  \"bestblock\" : \"hex\",        (string) The hash of the block at the tip of the chain\n  \"confirmations\" : n,        (numeric) The number of confirmations\n  \"value\" : n,                (numeric) The transaction value in BTC\n  \"scriptPubKey\" : {          (json object)\n    \"asm\" : \"hex\",            (string)\n    \"hex\" : \"hex\",            (string)\n    \"reqSigs\" : n,            (numeric) Number of required signatures\n    \"type\" : \"hex\",           (string) The type, eg pubkeyhash\n    \"addresses\" : [           (json array) array of bitcoin addresses\n      \"str\",                  (string) bitcoin address\n      ...\n    ]\n  },\n  \"coinbase\" : true|false     (boolean) Coinbase or not\n}\n```\n## Examples\n```\nGet unspent transactions:\n\nbitcoin-cli listunspent\nView the details:\n\nbitcoin-cli gettxout \"txid\" 1\nAs a JSON-RPC call:\n\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"gettxout\", \"params\": [\"txid\", 1]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getblock",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblock\",\n    \"params\": [\n        \"{{blockhash}}\",\n        {{verbosity}}\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						}
					},
					"response": []
				},
				{
					"name": "getchaintxstats",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getchaintxstats\",\n    \"params\": [\n        {{nblocks}},\n        \"{{blockhash}}\"\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getchaintxstats\n`getchaintxstats ( nblocks \"blockhash\" )`\n\nCompute statistics about the total number and rate of transactions in the chain.\n\n## Argument #1 - nblocks\nType: numeric, optional, default=one month\n\nSize of the window in number of blocks\n\n## Argument #2 - blockhash\nType: string, optional, default=chain tip\n\nThe hash of the block that ends the window.\n\n## Result\n```\n{                                       (json object)\n  \"time\" : xxx,                         (numeric) The timestamp for the final block in the window, expressed in UNIX epoch time\n  \"txcount\" : n,                        (numeric) The total number of transactions in the chain up to that point\n  \"window_final_block_hash\" : \"hex\",    (string) The hash of the final block in the window\n  \"window_final_block_height\" : n,      (numeric) The height of the final block in the window.\n  \"window_block_count\" : n,             (numeric) Size of the window in number of blocks\n  \"window_tx_count\" : n,                (numeric) The number of transactions in the window. Only returned if \"window_block_count\" is > 0\n  \"window_interval\" : n,                (numeric) The elapsed time in the window in seconds. Only returned if \"window_block_count\" is > 0\n  \"txrate\" : n                          (numeric) The average rate of transactions per second in the window. Only returned if \"window_interval\" is > 0\n}\n```\n## Examples\n```\nbitcoin-cli getchaintxstats\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getchaintxstats\", \"params\": [2016]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getblockheader",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblockheader\",\n    \"params\": [\n        \"{{blockhash}}\",\n        {{verbose}}\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getblockheader\n`getblockheader \"blockhash\" ( verbose )`\n\nIf verbose is false, returns a string that is serialized, hex-encoded data for blockheader ‘hash’.\n\nIf verbose is true, returns an Object with information about blockheader ‘hash’.\n\n## Argument #1 - blockhash\n**Type**: string, required\n\nThe block hash\n\n## Argument #2 - verbose\n**Type**: boolean, optional, default=true\n\ntrue for a json object, false for the hex-encoded data\n\n## Result (for verbose = true)\n```\n{                                 (json object)\n  \"hash\" : \"hex\",                 (string) the block hash (same as provided)\n  \"confirmations\" : n,            (numeric) The number of confirmations, or -1 if the block is not on the main chain\n  \"height\" : n,                   (numeric) The block height or index\n  \"version\" : n,                  (numeric) The block version\n  \"versionHex\" : \"hex\",           (string) The block version formatted in hexadecimal\n  \"merkleroot\" : \"hex\",           (string) The merkle root\n  \"time\" : xxx,                   (numeric) The block time expressed in UNIX epoch time\n  \"mediantime\" : xxx,             (numeric) The median block time expressed in UNIX epoch time\n  \"nonce\" : n,                    (numeric) The nonce\n  \"bits\" : \"hex\",                 (string) The bits\n  \"difficulty\" : n,               (numeric) The difficulty\n  \"chainwork\" : \"hex\",            (string) Expected number of hashes required to produce the current chain\n  \"nTx\" : n,                      (numeric) The number of transactions in the block\n  \"previousblockhash\" : \"hex\",    (string) The hash of the previous block\n  \"nextblockhash\" : \"hex\"         (string) The hash of the next block\n}\n```\n## Result (for verbose=false)\nName\n\nType\n\nDescription\n\nhex\n\nstring\n\nA string that is serialized, hex-encoded data for block ‘hash’\n\n## Examples\n```\nbitcoin-cli getblockheader \"00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09\"\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getblockheader\", \"params\": [\"00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09\"]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getblockchaintips",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getchaintips\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						}
					},
					"response": []
				},
				{
					"name": "getblockstats",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								},
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblockstats\",\n    \"params\": [\n        {{height}},\n        []\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getblockstats\n`getblockstats hash_or_height ( stats )`\n\nCompute per block statistics for a given window. All amounts are in satoshis.\n\nIt won’t work for some heights with pruning.\n\n## Argument #1 - hash_or_height\n**Type**: string or numeric, required\n\nThe block hash or height of the target block\n\n## Argument #2 - stats\n**Type**: json array, optional, default=all values\n\nValues to plot (see result below)\n```\n[\n  \"height\",     (string) Selected statistic\n  \"time\",       (string) Selected statistic\n  ...\n]\n```\nResult\n```\n{                              (json object)\n  \"avgfee\" : n,                (numeric) Average fee in the block\n  \"avgfeerate\" : n,            (numeric) Average feerate (in satoshis per virtual byte)\n  \"avgtxsize\" : n,             (numeric) Average transaction size\n  \"blockhash\" : \"hex\",         (string) The block hash (to check for potential reorgs)\n  \"feerate_percentiles\" : [    (json array) Feerates at the 10th, 25th, 50th, 75th, and 90th percentile weight unit (in satoshis per virtual byte)\n    n,                         (numeric) The 10th percentile feerate\n    n,                         (numeric) The 25th percentile feerate\n    n,                         (numeric) The 50th percentile feerate\n    n,                         (numeric) The 75th percentile feerate\n    n                          (numeric) The 90th percentile feerate\n  ],\n  \"height\" : n,                (numeric) The height of the block\n  \"ins\" : n,                   (numeric) The number of inputs (excluding coinbase)\n  \"maxfee\" : n,                (numeric) Maximum fee in the block\n  \"maxfeerate\" : n,            (numeric) Maximum feerate (in satoshis per virtual byte)\n  \"maxtxsize\" : n,             (numeric) Maximum transaction size\n  \"medianfee\" : n,             (numeric) Truncated median fee in the block\n  \"mediantime\" : n,            (numeric) The block median time past\n  \"mediantxsize\" : n,          (numeric) Truncated median transaction size\n  \"minfee\" : n,                (numeric) Minimum fee in the block\n  \"minfeerate\" : n,            (numeric) Minimum feerate (in satoshis per virtual byte)\n  \"mintxsize\" : n,             (numeric) Minimum transaction size\n  \"outs\" : n,                  (numeric) The number of outputs\n  \"subsidy\" : n,               (numeric) The block subsidy\n  \"swtotal_size\" : n,          (numeric) Total size of all segwit transactions\n  \"swtotal_weight\" : n,        (numeric) Total weight of all segwit transactions\n  \"swtxs\" : n,                 (numeric) The number of segwit transactions\n  \"time\" : n,                  (numeric) The block time\n  \"total_out\" : n,             (numeric) Total amount in all outputs (excluding coinbase and thus reward [ie subsidy + totalfee])\n  \"total_size\" : n,            (numeric) Total size of all non-coinbase transactions\n  \"total_weight\" : n,          (numeric) Total weight of all non-coinbase transactions\n  \"totalfee\" : n,              (numeric) The fee total\n  \"txs\" : n,                   (numeric) The number of transactions (including coinbase)\n  \"utxo_increase\" : n,         (numeric) The increase/decrease in the number of unspent outputs\n  \"utxo_size_inc\" : n          (numeric) The increase/decrease in size for the utxo index (not discounting op_return and similar)\n}\n```\nExamples\n```\nbitcoin-cli getblockstats '\"00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09\"' '[\"minfeerate\",\"avgfeerate\"]'\nbitcoin-cli getblockstats 1000 '[\"minfeerate\",\"avgfeerate\"]'\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getblockstats\", \"params\": [\"00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09\", [\"minfeerate\",\"avgfeerate\"]]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.\n```"
					},
					"response": []
				},
				{
					"name": "getblockchaininfo",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblockchaininfo\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getblockchaininfo\n`getblockchaininfo`\n\nReturns an object containing various state info regarding blockchain processing.\n\n## Result\n```\n{                                         (json object)\n  \"chain\" : \"str\",                        (string) current network name (main, test, regtest)\n  \"blocks\" : n,                           (numeric) the height of the most-work fully-validated chain. The genesis block has height 0\n  \"headers\" : n,                          (numeric) the current number of headers we have validated\n  \"bestblockhash\" : \"str\",                (string) the hash of the currently best block\n  \"difficulty\" : n,                       (numeric) the current difficulty\n  \"mediantime\" : n,                       (numeric) median time for the current best block\n  \"verificationprogress\" : n,             (numeric) estimate of verification progress [0..1]\n  \"initialblockdownload\" : true|false,    (boolean) (debug information) estimate of whether this node is in Initial Block Download mode\n  \"chainwork\" : \"hex\",                    (string) total amount of work in active chain, in hexadecimal\n  \"size_on_disk\" : n,                     (numeric) the estimated size of the block and undo files on disk\n  \"pruned\" : true|false,                  (boolean) if the blocks are subject to pruning\n  \"pruneheight\" : n,                      (numeric) lowest-height complete block stored (only present if pruning is enabled)\n  \"automatic_pruning\" : true|false,       (boolean) whether automatic pruning is enabled (only present if pruning is enabled)\n  \"prune_target_size\" : n,                (numeric) the target size used by pruning (only present if automatic pruning is enabled)\n  \"softforks\" : {                         (json object) status of softforks\n    \"xxxx\" : {                            (json object) name of the softfork\n      \"type\" : \"str\",                     (string) one of \"buried\", \"bip9\"\n      \"bip9\" : {                          (json object) status of bip9 softforks (only for \"bip9\" type)\n        \"status\" : \"str\",                 (string) one of \"defined\", \"started\", \"locked_in\", \"active\", \"failed\"\n        \"bit\" : n,                        (numeric) the bit (0-28) in the block version field used to signal this softfork (only for \"started\" status)\n        \"start_time\" : xxx,               (numeric) the minimum median time past of a block at which the bit gains its meaning\n        \"timeout\" : xxx,                  (numeric) the median time past of a block at which the deployment is considered failed if not yet locked in\n        \"since\" : n,                      (numeric) height of the first block to which the status applies\n        \"statistics\" : {                  (json object) numeric statistics about BIP9 signalling for a softfork (only for \"started\" status)\n          \"period\" : n,                   (numeric) the length in blocks of the BIP9 signalling period\n          \"threshold\" : n,                (numeric) the number of blocks with the version bit set required to activate the feature\n          \"elapsed\" : n,                  (numeric) the number of blocks elapsed since the beginning of the current period\n          \"count\" : n,                    (numeric) the number of blocks with the version bit set in the current period\n          \"possible\" : true|false         (boolean) returns false if there are not enough blocks left in this period to pass activation threshold\n        }\n      },\n      \"height\" : n,                       (numeric) height of the first block which the rules are or will be enforced (only for \"buried\" type, or \"bip9\" type with \"active\" status)\n      \"active\" : true|false               (boolean) true if the rules are enforced for the mempool and the next block\n    },\n    ...\n  },\n  \"warnings\" : \"str\"                      (string) any network and blockchain warnings\n}\n```\n## Examples\n```\nbitcoin-cli getblockchaininfo\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getblockchaininfo\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getchaintxstats",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getchaintxstats\",\n    \"params\": [{{height}}]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getchaintxstats\n`getchaintxstats ( nblocks \"blockhash\" )`\n\nCompute statistics about the total number and rate of transactions in the chain.\n\nArgument #1 - `nblocks`\nType: numeric, optional, default=one month\n\nSize of the window in number of blocks\n\nArgument #2 - `blockhash`\nType: string, optional, default=chain tip\n\nThe hash of the block that ends the window."
					},
					"response": []
				},
				{
					"name": "getblockcount",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblockcount\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						}
					},
					"response": []
				},
				{
					"name": "getdifficulty",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getdifficulty\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getdifficulty\n`getdifficulty`\n\nReturns the proof-of-work difficulty as a multiple of the minimum difficulty.\n\n## Result\nName\n\nType\n\nDescription\n\nn\n\nnumeric\n\nthe proof-of-work difficulty as a multiple of the minimum difficulty.\n\n## Examples\n```\nbitcoin-cli getdifficulty\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getdifficulty\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getblockfilter",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblockfilter\",\n    \"params\": [\n        \"{{blockhash}}\",\n        \"basic\"\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getblockfilter\n\n`getblockfilter \"blockhash\" ( \"filtertype\" )`\n\nRetrieve a BIP 157 content filter for a particular block.\n\n## Argument #1 - blockhash\n\n**Type:** string, required\n\nThe hash of the block\n\n## Argument #2 - filtertype\n\n**Type:** string, optional, default=basic\n\nThe type name of the filter\n\n## Result\n\n```\n{                      (json object)\n  \"filter\" : \"hex\",    (string) the hex-encoded filter data\n  \"header\" : \"hex\"     (string) the hex-encoded filter header}\n```\n\n## Examples\n\n``` bash\nbitcoin-cli getblockfilter \"00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09\" \"basic\"\n```\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getblockfilter\", \"params\": [\"00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09\", \"basic\"]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```\n\n# TAKE NOTE! \n\nMay not work on your node.  See [https://bitcoin.stackexchange.com/questions/96752/getblockfilter-error-index-is-not-enabled-for-filtertype-basic](https://bitcoin.stackexchange.com/questions/96752/getblockfilter-error-index-is-not-enabled-for-filtertype-basic)"
					},
					"response": []
				},
				{
					"name": "getmempoolinfo",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getmempoolinfo\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getmempoolinfo\n`getmempoolinfo`\n\nReturns details on the active state of the TX memory pool.\n\n## Result\n```\n{                            (json object)\n  \"loaded\" : true|false,     (boolean) True if the mempool is fully loaded\n  \"size\" : n,                (numeric) Current tx count\n  \"bytes\" : n,               (numeric) Sum of all virtual transaction sizes as defined in BIP 141. Differs from actual serialized size because witness data is discounted\n  \"usage\" : n,               (numeric) Total memory usage for the mempool\n  \"maxmempool\" : n,          (numeric) Maximum memory usage for the mempool\n  \"mempoolminfee\" : n,       (numeric) Minimum fee rate in BTC/kB for tx to be accepted. Is the maximum of minrelaytxfee and minimum mempool fee\n  \"minrelaytxfee\" : n,       (numeric) Current minimum relay fee for transactions\n  \"unbroadcastcount\" : n     (numeric) Current number of transactions that haven't passed initial broadcast yet\n}\n```\n## Examples\n```\nbitcoin-cli getmempoolinfo\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getmempoolinfo\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getrawmempool",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getrawmempool\",\n    \"params\": [{{verbose}}]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getrawmempool\n`getrawmempool ( verbose mempool_sequence )`\n\nReturns all transaction ids in memory pool as a json array of string transaction ids.\n\nHint: use `getmempoolentry` to fetch a specific transaction from the mempool.\n\n## Argument #1 - verbose\n**Type**: boolean, optional, default=false\n\nTrue for a json object, false for array of transaction ids\n\n## Argument #2 - mempool_sequence\n**Type**: boolean, optional, default=false\n\nIf verbose=false, returns a json object with transaction list and mempool sequence number attached.\n\n## Result (for verbose = false)\n```\n[           (json array)\n  \"hex\",    (string) The transaction id\n  ...\n]\n``\n## Result (for verbose = true)\n```\n{                                         (json object)\n  \"transactionid\" : {                     (json object)\n    \"vsize\" : n,                          (numeric) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.\n    \"weight\" : n,                         (numeric) transaction weight as defined in BIP 141.\n    \"fee\" : n,                            (numeric) transaction fee in BTC (DEPRECATED)\n    \"modifiedfee\" : n,                    (numeric) transaction fee with fee deltas used for mining priority (DEPRECATED)\n    \"time\" : xxx,                         (numeric) local time transaction entered pool in seconds since 1 Jan 1970 GMT\n    \"height\" : n,                         (numeric) block height when transaction entered pool\n    \"descendantcount\" : n,                (numeric) number of in-mempool descendant transactions (including this one)\n    \"descendantsize\" : n,                 (numeric) virtual transaction size of in-mempool descendants (including this one)\n    \"descendantfees\" : n,                 (numeric) modified fees (see above) of in-mempool descendants (including this one) (DEPRECATED)\n    \"ancestorcount\" : n,                  (numeric) number of in-mempool ancestor transactions (including this one)\n    \"ancestorsize\" : n,                   (numeric) virtual transaction size of in-mempool ancestors (including this one)\n    \"ancestorfees\" : n,                   (numeric) modified fees (see above) of in-mempool ancestors (including this one) (DEPRECATED)\n    \"wtxid\" : \"hex\",                      (string) hash of serialized transaction, including witness data\n    \"fees\" : {                            (json object)\n      \"base\" : n,                         (numeric) transaction fee in BTC\n      \"modified\" : n,                     (numeric) transaction fee with fee deltas used for mining priority in BTC\n      \"ancestor\" : n,                     (numeric) modified fees (see above) of in-mempool ancestors (including this one) in BTC\n      \"descendant\" : n                    (numeric) modified fees (see above) of in-mempool descendants (including this one) in BTC\n    },\n    \"depends\" : [                         (json array) unconfirmed transactions used as inputs for this transaction\n      \"hex\",                              (string) parent transaction id\n      ...\n    ],\n    \"spentby\" : [                         (json array) unconfirmed transactions spending outputs from this transaction\n      \"hex\",                              (string) child transaction id\n      ...\n    ],\n    \"bip125-replaceable\" : true|false,    (boolean) Whether this transaction could be replaced due to BIP125 (replace-by-fee)\n    \"unbroadcast\" : true|false            (boolean) Whether this transaction is currently unbroadcast (initial broadcast not yet acknowledged by any peers)\n  },\n  ...\n}\nResult (for verbose = false and mempool_sequence = true)\n{                            (json object)\n  \"txids\" : [                (json array)\n    \"hex\",                   (string) The transaction id\n    ...\n  ],\n  \"mempool_sequence\" : n     (numeric) The mempool sequence value.\n}\n```\n## Examples\n```\nbitcoin-cli getrawmempool true\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getrawmempool\", \"params\": [true]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				}
			]
		},
		{
			"name": "Mining",
			"item": [
				{
					"name": "getblocktemplate",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblocktemplate\",\n    \"params\": [{\"rules\": [\"segwit\"]}]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						}
					},
					"response": []
				},
				{
					"name": "getmininginfo",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getmininginfo\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getmininginfo\n`getmininginfo`\n\nReturns a json object containing mining-related information.\n\n## Result\n```\n{                              (json object)\n  \"blocks\" : n,                (numeric) The current block\n  \"currentblockweight\" : n,    (numeric, optional) The block weight of the last assembled block (only present if a block was ever assembled)\n  \"currentblocktx\" : n,        (numeric, optional) The number of block transactions of the last assembled block (only present if a block was ever assembled)\n  \"difficulty\" : n,            (numeric) The current difficulty\n  \"networkhashps\" : n,         (numeric) The network hashes per second\n  \"pooledtx\" : n,              (numeric) The size of the mempool\n  \"chain\" : \"str\",             (string) current network name (main, test, regtest)\n  \"warnings\" : \"str\"           (string) any network and blockchain warnings\n}\n```\n## Examples\n```\nbitcoin-cli getmininginfo\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getmininginfo\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getnetworkhashps",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getnetworkhashps\",\n    \"params\": [{{nblocks}},{{height}}]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getnetworkhashps\n`getnetworkhashps ( nblocks height )`\n\nReturns the estimated network hashes per second based on the last n blocks.\n\nPass in [`blocks`] to override # of blocks, -1 specifies since last difficulty change.\n\nPass in [`height`] to estimate the network speed at the time when a certain block was found.\n\n## Argument #1 - nblocks\n**Type**: numeric, optional, default=120\n\nThe number of blocks, or -1 for blocks since last difficulty change.\n\n## Argument #2 - height\n**Type**: numeric, optional, default=-1\n\nTo estimate at the time of the given height.\n\n## Result\nName\n\nType\n\nDescription\n\nn\n\nnumeric\n\nHashes per second estimated\n\n## Examples\n```\nbitcoin-cli getnetworkhashps\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getnetworkhashps\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				}
			]
		},
		{
			"name": "Control",
			"item": [
				{
					"name": "uptime",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"uptime\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# `uptime`\n\nReturns the total uptime of the server."
					},
					"response": []
				},
				{
					"name": "help",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"help\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# help \n`help ( \"command\" )`\n\nList all commands, or get help for a specified command.\n\n## Argument #1 - command\n**Type**: string, optional, default=all commands\n\nThe command to get help on"
					},
					"response": []
				},
				{
					"name": "getrpcinfo",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getrpcinfo\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getrpcinfo¶\n`getrpcinfo`\n\nReturns details of the RPC server.\n\n## Result\n```\n{                          (json object)\n  \"active_commands\" : [    (json array) All active commands\n    {                      (json object) Information about an active command\n      \"method\" : \"str\",    (string) The name of the RPC command\n      \"duration\" : n       (numeric) The running time in microseconds\n    },\n    ...\n  ],\n  \"logpath\" : \"str\"        (string) The complete file path to the debug log\n}\n```\n## Examples\n```\nbitcoin-cli getrpcinfo\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getrpcinfo\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getmemoryinfo",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getmemoryinfo\",\n    \"params\": [\"stats\"]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getmemoryinfo\n`getmemoryinfo ( \"mode\" )`\n\nReturns an object containing information about memory usage.\n\n## Argument #1 - mode\n**Type**: string, optional, default=”stats”\n\ndetermines what kind of information is returned.\n“stats” returns general statistics about memory usage in the daemon.\n\n“mallocinfo” returns an XML string describing low-level heap state (only available if compiled with glibc 2.10+).\n\n## Result (mode “stats”)\n```\n{                         (json object)\n  \"locked\" : {            (json object) Information about locked memory manager\n    \"used\" : n,           (numeric) Number of bytes used\n    \"free\" : n,           (numeric) Number of bytes available in current arenas\n    \"total\" : n,          (numeric) Total number of bytes managed\n    \"locked\" : n,         (numeric) Amount of bytes that succeeded locking. If this number is smaller than total, locking pages failed at some point and key data could be swapped to disk.\n    \"chunks_used\" : n,    (numeric) Number allocated chunks\n    \"chunks_free\" : n     (numeric) Number unused chunks\n  }\n}\n```\nResult (mode “mallocinfo”)\nName\n\nType\n\nDescription\n\nstr\n\nstring\n\n“<malloc version=”1”>…”\n\n## Examples\n```\nbitcoin-cli getmemoryinfo\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getmemoryinfo\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				}
			]
		},
		{
			"name": "Network",
			"item": [
				{
					"name": "getpeerinfo",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getpeerinfo\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getpeerinfo\n`getpeerinfo`\n\nReturns data about each connected network node as a json array of objects.\n\n## Result\n```\n[                                  (json array)\n  {                                (json object)\n    \"id\" : n,                      (numeric) Peer index\n    \"addr\" : \"str\",                (string) (host:port) The IP address and port of the peer\n    \"addrbind\" : \"str\",            (string) (ip:port) Bind address of the connection to the peer\n    \"addrlocal\" : \"str\",           (string) (ip:port) Local address as reported by the peer\n    \"network\" : \"str\",             (string) Network (ipv4, ipv6, or onion) the peer connected through\n    \"mapped_as\" : n,               (numeric) The AS in the BGP route to the peer used for diversifying\n                                   peer selection (only available if the asmap config flag is set)\n    \"services\" : \"hex\",            (string) The services offered\n    \"servicesnames\" : [            (json array) the services offered, in human-readable form\n      \"str\",                       (string) the service name if it is recognised\n      ...\n    ],\n    \"relaytxes\" : true|false,      (boolean) Whether peer has asked us to relay transactions to it\n    \"lastsend\" : xxx,              (numeric) The UNIX epoch time of the last send\n    \"lastrecv\" : xxx,              (numeric) The UNIX epoch time of the last receive\n    \"last_transaction\" : xxx,      (numeric) The UNIX epoch time of the last valid transaction received from this peer\n    \"last_block\" : xxx,            (numeric) The UNIX epoch time of the last block received from this peer\n    \"bytessent\" : n,               (numeric) The total bytes sent\n    \"bytesrecv\" : n,               (numeric) The total bytes received\n    \"conntime\" : xxx,              (numeric) The UNIX epoch time of the connection\n    \"timeoffset\" : n,              (numeric) The time offset in seconds\n    \"pingtime\" : n,                (numeric) ping time (if available)\n    \"minping\" : n,                 (numeric) minimum observed ping time (if any at all)\n    \"pingwait\" : n,                (numeric) ping wait (if non-zero)\n    \"version\" : n,                 (numeric) The peer version, such as 70001\n    \"subver\" : \"str\",              (string) The string version\n    \"inbound\" : true|false,        (boolean) Inbound (true) or Outbound (false)\n    \"addnode\" : true|false,        (boolean) Whether connection was due to addnode/-connect or if it was an automatic/inbound connection\n                                   (DEPRECATED, returned only if the config option -deprecatedrpc=getpeerinfo_addnode is passed)\n    \"connection_type\" : \"str\",     (string) Type of connection:\n                                   outbound-full-relay (default automatic connections),\n                                   block-relay-only (does not relay transactions or addresses),\n                                   inbound (initiated by the peer),\n                                   manual (added via addnode RPC or -addnode/-connect configuration options),\n                                   addr-fetch (short-lived automatic connection for soliciting addresses),\n                                   feeler (short-lived automatic connection for testing addresses).\n                                   Please note this output is unlikely to be stable in upcoming releases as we iterate to\n                                   best capture connection behaviors.\n    \"startingheight\" : n,          (numeric) The starting height (block) of the peer\n    \"banscore\" : n,                (numeric) The ban score (DEPRECATED, returned only if config option -deprecatedrpc=banscore is passed)\n    \"synced_headers\" : n,          (numeric) The last header we have in common with this peer\n    \"synced_blocks\" : n,           (numeric) The last block we have in common with this peer\n    \"inflight\" : [                 (json array)\n      n,                           (numeric) The heights of blocks we're currently asking from this peer\n      ...\n    ],\n    \"whitelisted\" : true|false,    (boolean, optional) Whether the peer is whitelisted with default permissions\n                                   (DEPRECATED, returned only if config option -deprecatedrpc=whitelisted is passed)\n    \"permissions\" : [              (json array) Any special permissions that have been granted to this peer\n      \"str\",                       (string) bloomfilter (allow requesting BIP37 filtered blocks and transactions),\n                                   noban (do not ban for misbehavior; implies download),\n                                   forcerelay (relay transactions that are already in the mempool; implies relay),\n                                   relay (relay even in -blocksonly mode, and unlimited transaction announcements),\n                                   mempool (allow requesting BIP35 mempool contents),\n                                   download (allow getheaders during IBD, no disconnect after maxuploadtarget limit),\n                                   addr (responses to GETADDR avoid hitting the cache and contain random records with the most up-to-date info).\n\n      ...\n    ],\n    \"minfeefilter\" : n,            (numeric) The minimum fee rate for transactions this peer accepts\n    \"bytessent_per_msg\" : {        (json object)\n      \"msg\" : n,                   (numeric) The total bytes sent aggregated by message type\n                                   When a message type is not listed in this json object, the bytes sent are 0.\n                                   Only known message types can appear as keys in the object.\n      ...\n    },\n    \"bytesrecv_per_msg\" : {        (json object)\n      \"msg\" : n                    (numeric) The total bytes received aggregated by message type\n                                   When a message type is not listed in this json object, the bytes received are 0.\n                                   Only known message types can appear as keys in the object and all bytes received\n                                   of unknown message types are listed under '*other*'.\n    }\n  },\n  ...\n]\n```\n## Examples\n```\nbitcoin-cli getpeerinfo\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getpeerinfo\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getnetworkinfo",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getnetworkinfo\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getnetworkinfo\n`getnetworkinfo`\n\nReturns an object containing various state info regarding P2P networking.\n\n## Result\n```\n{                                                    (json object)\n  \"version\" : n,                                     (numeric) the server version\n  \"subversion\" : \"str\",                              (string) the server subversion string\n  \"protocolversion\" : n,                             (numeric) the protocol version\n  \"localservices\" : \"hex\",                           (string) the services we offer to the network\n  \"localservicesnames\" : [                           (json array) the services we offer to the network, in human-readable form\n    \"str\",                                           (string) the service name\n    ...\n  ],\n  \"localrelay\" : true|false,                         (boolean) true if transaction relay is requested from peers\n  \"timeoffset\" : n,                                  (numeric) the time offset\n  \"connections\" : n,                                 (numeric) the total number of connections\n  \"connections_in\" : n,                              (numeric) the number of inbound connections\n  \"connections_out\" : n,                             (numeric) the number of outbound connections\n  \"networkactive\" : true|false,                      (boolean) whether p2p networking is enabled\n  \"networks\" : [                                     (json array) information per network\n    {                                                (json object)\n      \"name\" : \"str\",                                (string) network (ipv4, ipv6 or onion)\n      \"limited\" : true|false,                        (boolean) is the network limited using -onlynet?\n      \"reachable\" : true|false,                      (boolean) is the network reachable?\n      \"proxy\" : \"str\",                               (string) (\"host:port\") the proxy that is used for this network, or empty if none\n      \"proxy_randomize_credentials\" : true|false     (boolean) Whether randomized credentials are used\n    },\n    ...\n  ],\n  \"relayfee\" : n,                                    (numeric) minimum relay fee for transactions in BTC/kB\n  \"incrementalfee\" : n,                              (numeric) minimum fee increment for mempool limiting or BIP 125 replacement in BTC/kB\n  \"localaddresses\" : [                               (json array) list of local addresses\n    {                                                (json object)\n      \"address\" : \"str\",                             (string) network address\n      \"port\" : n,                                    (numeric) network port\n      \"score\" : n                                    (numeric) relative score\n    },\n    ...\n  ],\n  \"warnings\" : \"str\"                                 (string) any network and blockchain warnings\n}\n```\n## Examples\n```\nbitcoin-cli getnetworkinfo\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getnetworkinfo\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getconnectioncount",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getconnectioncount\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getconnectioncount\n`getconnectioncount`\n\nReturns the number of connections to other nodes.\n\n## Result\nName\n\nType\n\nDescription\n\nn\n\nnumeric\n\nThe connection count\n\n## Examples\n```\nbitcoin-cli getconnectioncount\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getconnectioncount\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "getnettotals",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getnettotals\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getnettotals\n`getnettotals`\n\nReturns information about network traffic, including bytes in, bytes out, and current time.\n\n## Result\n```\n{                                              (json object)\n  \"totalbytesrecv\" : n,                        (numeric) Total bytes received\n  \"totalbytessent\" : n,                        (numeric) Total bytes sent\n  \"timemillis\" : xxx,                          (numeric) Current UNIX epoch time in milliseconds\n  \"uploadtarget\" : {                           (json object)\n    \"timeframe\" : n,                           (numeric) Length of the measuring timeframe in seconds\n    \"target\" : n,                              (numeric) Target in bytes\n    \"target_reached\" : true|false,             (boolean) True if target is reached\n    \"serve_historical_blocks\" : true|false,    (boolean) True if serving historical blocks\n    \"bytes_left_in_cycle\" : n,                 (numeric) Bytes left in current time cycle\n    \"time_left_in_cycle\" : n                   (numeric) Seconds left in current time cycle\n  }\n}\n```\n## Examples\n```\nbitcoin-cli getnettotals\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getnettotals\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n```"
					},
					"response": []
				},
				{
					"name": "listbanned",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"listbanned\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# listbanned\n\n`listbanned`\n\nList all manually banned IPs/Subnets.\n\n## Result\n\n``` bash\n[\n  {\n  \"address\": \n\n```\n\n## Examples\n\n``` bash\nbitcoin-cli listbanned\n\n```\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"listbanned\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n\n```"
					},
					"response": []
				},
				{
					"name": "ping",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								},
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"ping\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# ping\n\n`ping`\n\nRequests that a ping be sent to all other nodes, to measure ping time.\n\nResults provided in getpeerinfo, pingtime and pingwait fields are decimal seconds.\n\nPing command is handled in queue with all other commands, so it measures processing backlog, not just network ping.\n\n## Result\n\n``` bash\nnull    (json null)\n\n```\n\n## Examples\n\n``` bash\nbitcoin-cli ping\n\n```\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"ping\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n\n```"
					},
					"response": []
				}
			]
		},
		{
			"name": "Rawtransactions",
			"item": []
		},
		{
			"name": "Util",
			"item": []
		},
		{
			"name": "Wallet",
			"item": [
				{
					"name": "createwallet",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								},
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"createwallet\",\n    \"params\": [\n        \"muffy.dat\"\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# createwallet\n\n`createwallet \"wallet_name\" ( disable_private_keys blank \"passphrase\" avoid_reuse descriptors load_on_startup )`\n\nCreates and loads a new wallet.\n\n## Argument #1 - wallet_name\n\n**Type:** string, required\n\nThe name for the new wallet. If this is a path, the wallet will be created at the path location.\n\n## Argument #2 - disable_private_keys\n\n**Type:** boolean, optional, default=false\n\nDisable the possibility of private keys (only watchonlys are possible in this mode).\n\n## Argument #3 - blank\n\n**Type:** boolean, optional, default=false\n\nCreate a blank wallet. A blank wallet has no keys or HD seed. One can be set using sethdseed.\n\n## Argument #4 - passphrase\n\n**Type:** string\n\nEncrypt the wallet with this passphrase.\n\n## Argument #5 - avoid_reuse\n\n**Type:** boolean, optional, default=false\n\nKeep track of coin reuse, and treat dirty and clean coins differently with privacy considerations in mind.\n\n## Argument #6 - descriptors\n\n**Type:** boolean, optional, default=false\n\nCreate a native descriptor wallet. The wallet will use descriptors internally to handle address creation\n\n## Argument #7 - load_on_startup\n\n**Type:** boolean, optional, default=null\n\nSave wallet name to persistent settings and load on startup. True to  \nadd wallet to startup list, false to remove, null to leave unchanged.\n\n## Result\n\n```\n{                       (json object)\n  \"name\" : \"str\",       (string) The wallet name if created successfully. If the wallet was created using a full path, the wallet_name will be the full path.\n  \"warning\" : \"str\"     (string) Warning message if wallet was not loaded cleanly.}\n```\n\n## Examples\n\n``` bash\nbitcoin-cli createwallet \"testwallet\"\n```\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"createwallet\", \"params\": [\"testwallet\"]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n\n```"
					},
					"response": []
				},
				{
					"name": "getwalletinfo",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								},
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"listwalletdir\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# getwalletinfo\n\n`getwalletinfo`\n\nReturns an object containing various wallet state info.\n\n## Result\n\n``` json\n{                                         (json object)\n  \"walletname\" : \"str\",                   (string) the wallet name\n  \"walletversion\" : n,                    (numeric) the wallet version\n  \"format\" : \"str\",                       (string) the database format (bdb or sqlite)\n  \"balance\" : n,                          (numeric) DEPRECATED. Identical to getbalances().mine.trusted\n  \"unconfirmed_balance\" : n,              (numeric) DEPRECATED. Identical to getbalances().mine.untrusted_pending\n  \"immature_balance\" : n,                 (numeric) DEPRECATED. Identical to getbalances().mine.immature\n  \"txcount\" : n,                          (numeric) the total number of transactions in the wallet\n  \"keypoololdest\" : xxx,                  (numeric) the UNIX epoch time of the oldest pre-generated key in the key pool. Legacy wallets only.\n  \"keypoolsize\" : n,                      (numeric) how many new keys are pre-generated (only counts external keys)\n  \"keypoolsize_hd_internal\" : n,          (numeric) how many new keys are pre-generated for internal use (used for change outputs, only appears if the wallet is using this feature, otherwise external keys are used)\n  \"unlocked_until\" : xxx,                 (numeric, optional) the UNIX epoch time until which the wallet is unlocked for transfers, or 0 if the wallet is locked (only present for passphrase-encrypted wallets)\n  \"paytxfee\" : n,                         (numeric) the transaction fee configuration, set in BTC/kvB\n  \"hdseedid\" : \"hex\",                     (string, optional) the Hash160 of the HD seed (only present when HD is enabled)\n  \"private_keys_enabled\" : true|false,    (boolean) false if privatekeys are disabled for this wallet (enforced watch-only wallet)\n  \"avoid_reuse\" : true|false,             (boolean) whether this wallet tracks clean/dirty coins in terms of reuse\n  \"scanning\" : {                          (json object) current scanning details, or false if no scan is in progress\n    \"duration\" : n,                       (numeric) elapsed seconds since scan start\n    \"progress\" : n                        (numeric) scanning progress percentage [0.0, 1.0]\n  },\n  \"descriptors\" : true|false              (boolean) whether this wallet uses descriptors for scriptPubKey management}\n```\n\n## Examples\n\n``` bash\nbitcoin-cli getwalletinfo\n\n```\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"getwalletinfo\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n\n```"
					},
					"response": []
				},
				{
					"name": "loadwallet",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								},
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"loadwallet\",\n    \"params\": [\n        \"muffy.dat\"\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# loadwallet\n\n`loadwallet \"filename\" ( load_on_startup )`\n\nLoads a wallet from a wallet file or directory.\n\nNote that all wallet command-line options used when starting bitcoind will be  \napplied to the new wallet (eg -rescan, etc).\n\n## Argument #1 - filename\n\n**Type:** string, required\n\nThe wallet directory or .dat file.\n\n## Argument #2 - load_on_startup\n\n**Type:** boolean, optional, default=null\n\nSave wallet name to persistent settings and load on startup. True to  \nadd wallet to startup list, false to remove, null to leave unchanged.\n\n## Result\n\n```\n{                       (json object)\n  \"name\" : \"str\",       (string) The wallet name if loaded successfully.\n  \"warning\" : \"str\"     (string) Warning message if wallet was not loaded cleanly.}\n```\n\n## Examples\n\n``` bash\nbitcoin-cli loadwallet \"test.dat\"\n```\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"loadwallet\", \"params\": [\"test.dat\"]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n\n```"
					},
					"response": []
				},
				{
					"name": "listtransactions",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								},
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"listtransactions\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# listtransactions\n\n`listtransactions ( \"label\" count skip include_watchonly )`\n\nIf a label name is provided, this will return only incoming transactions paying to addresses with the specified label.\n\nReturns up to ‘count’ most recent transactions skipping the first ‘from’ transactions.\n\n## Argument #1 - label\n\n**Type:** string, optional\n\nIf set, should be a valid label name to return only incoming transactions\n\nwith the specified label, or “*” to disable filtering and return all transactions.\n\n## Argument #2 - count\n\n**Type:** numeric, optional, default=10\n\nThe number of transactions to return\n\n## Argument #3 - skip\n\n**Type:** numeric, optional, default=0\n\nThe number of transactions to skip\n\n## Argument #4 - include_watchonly\n\n**Type:** boolean, optional, default=true for watch-only wallets, otherwise false\n\nInclude transactions to watch-only addresses (see ‘importaddress’)\n\n## Result\n\n``` json\n[                                        (json array)\n  {                                      (json object)\n    \"involvesWatchonly\" : true|false,    (boolean) Only returns true if imported addresses were involved in transaction.\n    \"address\" : \"str\",                   (string) The bitcoin address of the transaction.\n    \"category\" : \"str\",                  (string) The transaction category.\n                                         \"send\"                  Transactions sent.\n                                         \"receive\"               Non-coinbase transactions received.\n                                         \"generate\"              Coinbase transactions received with more than 100 confirmations.\n                                         \"immature\"              Coinbase transactions received with 100 or fewer confirmations.\n                                         \"orphan\"                Orphaned coinbase transactions received.\n    \"amount\" : n,                        (numeric) The amount in BTC. This is negative for the 'send' category, and is positive\n                                         for all other categories\n    \"label\" : \"str\",                     (string) A comment for the address/transaction, if any\n    \"vout\" : n,                          (numeric) the vout value\n    \"fee\" : n,                           (numeric) The amount of the fee in BTC. This is negative and only available for the\n                                         'send' category of transactions.\n    \"confirmations\" : n,                 (numeric) The number of confirmations for the transaction. Negative confirmations means the\n                                         transaction conflicted that many blocks ago.\n    \"generated\" : true|false,            (boolean) Only present if transaction only input is a coinbase one.\n    \"trusted\" : true|false,              (boolean) Only present if we consider transaction to be trusted and so safe to spend from.\n    \"blockhash\" : \"hex\",                 (string) The block hash containing the transaction.\n    \"blockheight\" : n,                   (numeric) The block height containing the transaction.\n    \"blockindex\" : n,                    (numeric) The index of the transaction in the block that includes it.\n    \"blocktime\" : xxx,                   (numeric) The block time expressed in UNIX epoch time.\n    \"txid\" : \"hex\",                      (string) The transaction id.\n    \"walletconflicts\" : [                (json array) Conflicting transaction ids.\n      \"hex\",                             (string) The transaction id.\n      ...\n    ],\n    \"time\" : xxx,                        (numeric) The transaction time expressed in UNIX epoch time.\n    \"timereceived\" : xxx,                (numeric) The time received expressed in UNIX epoch time.\n    \"comment\" : \"str\",                   (string) If a comment is associated with the transaction, only present if not empty.\n    \"bip125-replaceable\" : \"str\",        (string) (\"yes|no|unknown\") Whether this transaction could be replaced due to BIP125 (replace-by-fee);\n                                         may be unknown for unconfirmed transactions not in the mempool\n    \"abandoned\" : true|false             (boolean) 'true' if the transaction has been abandoned (inputs are respendable). Only available for the\n                                         'send' category of transactions.\n  },\n  ...]\n```\n\n## Examples\n\nList the most recent 10 transactions in the systems:\n\n``` bash\nbitcoin-cli listtransactions\n\n```\n\nList transactions 100 to 120:\n\n``` bash\nbitcoin-cli listtransactions \"*\" 20 100\n```\n\nAs a JSON-RPC call:\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"listtransactions\", \"params\": [\"*\", 20, 100]}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n\n```"
					},
					"response": []
				},
				{
					"name": "listwalletdir",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								},
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"listwalletdir\",\n    \"params\": []\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# listwalletdir\n\n`listwalletdir`\n\nReturns a list of wallets in the wallet directory.\n\n## Result\n\n```\n{                        (json object)\n  \"wallets\" : [          (json array)\n    {                    (json object)\n      \"name\" : \"str\"     (string) The wallet name\n    },\n    ...\n  ]}\n\n```\n\n## Examples\n\n``` bash\nbitcoin-cli listwalletdir\n\n```\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"listwalletdir\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n\n```"
					},
					"response": []
				},
				{
					"name": "listwallets",
					"protocolProfileBehavior": {
						"disabledSystemHeaders": {}
					},
					"request": {
						"auth": {
							"type": "basic",
							"basic": [
								{
									"key": "username",
									"value": "{{username}}",
									"type": "string"
								},
								{
									"key": "password",
									"value": "{{password}}",
									"type": "string"
								}
							]
						},
						"method": "POST",
						"header": [],
						"body": {
							"mode": "raw",
							"raw": "{\n    \"method\": \"getblockstats\",\n    \"params\": [\n        {{height}},\n        []\n    ]\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{protocol}}://{{server}}:{{port}}",
							"protocol": "{{protocol}}",
							"host": [
								"{{server}}"
							],
							"port": "{{port}}"
						},
						"description": "# listwallets\n\n`listwallets`\n\nReturns a list of currently loaded wallets.\n\nFor full information on the wallet, use “getwalletinfo”\n\n## Result\n\n```\n[           (json array)\n  \"str\",    (string) the wallet name\n  ...]\n\n```\n\n## Examples\n\n``` bash\nbitcoin-cli listwallets\n\n```\n\n``` bash\ncurl --user myusername --data-binary '{\"jsonrpc\": \"1.0\", \"id\": \"curltest\", \"method\": \"listwallets\", \"params\": []}' -H 'content-type: text/plain;' http://127.0.0.1:8332/\n\n```"
					},
					"response": []
				},
				{
					"name": "unloadwallet",
					"request": {
						"method": "POST",
						"header": []
					},
					"response": []
				}
			]
		}
	],
	"auth": {
		"type": "basic",
		"basic": [
			{
				"key": "password",
				"value": "",
				"type": "string"
			},
			{
				"key": "username",
				"value": "",
				"type": "string"
			}
		]
	},
	"event": [
		{
			"listen": "prerequest",
			"script": {
				"type": "text/javascript",
				"exec": [
					""
				]
			}
		},
		{
			"listen": "test",
			"script": {
				"type": "text/javascript",
				"exec": [
					""
				]
			}
		}
	]
}
