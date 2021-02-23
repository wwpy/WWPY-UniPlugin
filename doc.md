```javascript
<script>
	// #ifdef APP-PLUS
	var testModule = uni.requireNativePlugin("WWPYUniPlugin-WWTestModule")
	const modal = uni.requireNativePlugin('modal');
	// #endif
	export default {
		data() {
			return {
				stepNum: "0"
			}
		},
		methods: {
			// 调用异步方法
			testAsyncFunc() {
				testModule.testAsyncFunc({
					'name': 'unimp',
					'age': 1
				},
				(ret) => {
					modal.toast({
						message: ret,
						duration: 1.5
					});
				})
			},
			// 调用同步方法
			testSyncFunc() {
				var ret = testModule.testSyncFunc({
					'name': 'unimp',
					'age': 1
				})
				modal.toast({
					message: ret,
					duration: 1.5
				});
			},
			// 跳转原生页面
			gotoNativePage() {
				testModule.gotoNativePage();
			},
		}, // end methods
	}
</script>
```

