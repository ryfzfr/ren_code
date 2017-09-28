public class Two_Sum_1 {
	// 我的解决方法
	int[] arr = new int[2];

	public int[] twoSum(int[] nums, int target) {
		for (int i = 0; i < nums.length - 1; i++) {
			for (int j = i + 1; j < nums.length; j++)
				if (nums[i] + nums[j] == target) {
					arr[0] = i;
					arr[1] = j;
				}
		}
		return arr;
	}

	// 大神解决方法
	public int[] twoSum1(int[] nums, int target) {
		Map<Integer, Integer> map = new HashMap<Integer, Integer>();
		for (int i = 0; i < nums.length; i++) {
			map.put(nums[i], i);
		}
		for (int i = 0; i < nums.length; i++) {
			int complement = target - nums[i];
			if (map.containsKey(complement) && map.get(complement) != i) {
				return new int[] { i, map.get(complement) };
			}
		}
		throw new IllegalArgumentException("No two sum solution");
	}
