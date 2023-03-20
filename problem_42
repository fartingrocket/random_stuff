class Solution:
	def trap(self, height: List[int]) -> int:
		ans = 0
		# pop zero values
		if len(height) >= 3:
			while (height[0] == 0 or height[1] >= height[0]) and len(height) > 2:
				height.pop(0)
			while (height[-1] == 0 or height[-2] >= height[-1]) and len(height) > 2:
				height.pop()
		if len(height) < 3:
			return ans
    
		while len(height) > 2:
			
			absolute_max = max(height)
			while height.count(absolute_max) == 1:
				height[height.index(absolute_max)] -= 1
				absolute_max = max(height)
			
			# find the next max
			r = 1
			while r < len(height)-1 and height[r] < height[0]:
				r += 1
			
			# sum up everything
			local_max = min(height[0], height[r])
			for j in range(r+1):
				if local_max > height[j]:
					ans += local_max - height[j]
			
			# remove this subset from the list
			height = height[r:]
			
		return ans
