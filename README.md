# LeetCode-Problem-Solutions


class Solution {
public:
    bool isRobotBounded(string instructions) {
        
        int l=instructions.size();
        char dir='N';
        int x=0,y=0;
        for(int i=0;i<l;i++)
        {
            if(instructions[i]=='G')
            {
                if(dir=='N')
                    y+=1;
                   else  if(dir=='S')
                       y-=1;
                       else  if(dir=='E')
                           x+=1;
                           else  if(dir=='W')
                               x-=1;
            }
            else if(instructions[i]=='L')
            {
                if(dir=='N')
                    dir='W';
                   else  if(dir=='S')
                       dir='E';
                       else  if(dir=='E')
                           dir='N';
                           else  if(dir=='W')
                               dir='S';
            }
            else
            {
                if(dir=='N')
                    dir='E';
                   else  if(dir=='S')
                       dir='W';
                       else  if(dir=='E')
                           dir='S';
                           else  if(dir=='W')
                               dir='N';
            }
                
        }
        if(x==0 && y==0)
            return true;
        else if(dir=='N')
            return false;
        else
            return true;
        
    }
};
