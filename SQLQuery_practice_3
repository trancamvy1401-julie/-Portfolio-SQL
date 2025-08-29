--Database Example_Sales
--Windows Function

select *
from employee

--1. Thống kê tổng sal
select Ename, job, hiredate, sal,
sum(sal)    over()    AS totalsal
from employee

--2. Thống kê tổng sal, BQ sal
select Ename, job, hiredate, sal,
sum(sal)    over()    AS totalsal,
avg(sal)    over()    AS Avgsal
from employee 

--3. Thống kê tổng sal, tỷ lệ của sal/totalsal
select Ename, job, hiredate, sal,
sum(sal)    over()    AS totalsal,
sal/(sum(sal)    over())  AS ratiosal
from employee 

--4. Thống kê tổng sal theo từng job
select Ename, job, hiredate, sal,
sum(sal)    over(partition by job)  
from employee

--5. Thống kê tổng sal theo từng job
select Ename, job, hiredate, sal,
sum(sal)    over(partition by job)     
from employee

--6. Thống kê lũy kế sal theo hiredate tăng dần
select Ename, job, hiredate, sal,
sum(sal)    over(order by hiredate ASC)  AS Runningsal                
from employee

--7. Thống kê lũy kế sal theo hiredate tăng dần trong từng job
select Ename, job, hiredate, sal,
sum(sal)    over(partition by job order by hiredate)  AS Runningsal                
from employee

--8. Đánh số thứ tự theo sal tăng dần
select Ename, job, hiredate, sal,
row_number()     over(order by hiredate)  AS RowNo                
from employee

--9. Đánh số thứ tự theo sal tăng dần trong từng job
select Ename, job, hiredate, sal,
row_number()     over(partition by job order by hiredate)  AS RowNo                
from employee

--10. Đánh số thứ tự theo sal tăng dần trong từng job
select Ename, job, hiredate, sal,
row_number()     over(partition by job order by hiredate)  AS RowNo                
from Employee

--11. Xếp hạng theo sal giảm dần trong từng job
select Ename, job, hiredate, sal,
rank()     over(partition by job order by sal DESC)  AS RankNo                
from Employee

--12 Liệt kê dữ liệu dòng trên, dòng dưới trên cơ sở sắp xếp theo hiredate tăng dần
select Ename, job, hiredate, sal,
lag(sal)  over(order by hiredate)  AS Lagsal,   --lấy dữ liệu dòng trên bỏ xuống dòng dưới
lead(sal) over(order by hiredate)  AS Leadsal    --lấy dữ liệu dòng dưới bỏ lên dòng trên
from Employee

--13 Chia nhóm dữ liệu theo hiredate tăng dần
select Ename, job, hiredate, sal,
NTILE(2)  over(order by hiredate)  AS Twogroup,
NTILE(3) over(order by hiredate)  AS Threegroup

from Employee  
