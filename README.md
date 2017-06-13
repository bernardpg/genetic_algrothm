# genetic_algrothm
it's for matlab genetic_algrothm

function varargout=GA_algo(varargin)


need_variable={'cost_function','range','population','bit_length'}


cost_function=varargin{1};


range=varargin{2};


x_data=range(:,1);


y_data=[]


y_data=range(:,2);


variables={'x','y','z','a','b','c','d','e','f'};


%range_variables()


%cell2struct


population=varargin{3};%number


bit_length=varargin{4};%bit_length


need_variable_num={cost_function,range,population,bit_length};


 needed=cell2struct(need_variable_num,need_variable,2); 


cross_over_percent=0.7


mutation_percent=0.1


elite=0


% range 


% random數字


%for i=1:()


%if i==1


[random_x_data]=random_ini(x_data,needed.population,bit_length);


%[random_y_data]=random_ini(y_data,population,bit_length);


new_cost_function_value=selection(cost_function,random_x_data)


cross_over(new_cost_function_value,cross_over_percent)


cross_over()


mutation(mutation_percent)


bit_decimal()


%else 


% [bit_random_x_data,random_x_data]=random_ini(x_data,population);


% [bit_random_y_data,random_y_data]=random_ini(y_data,population);


% selection(cost_function,random_x_data,random_y_data)


% cross_over()


% cross_over()


% mutation()


% bit_decimal()


% end


% end


end


function initialize()


end


function variable_callback


end


function [a]=random_ini(x,population,bit_length)


x_lowerbond=x(1,1);


x_upperbond=x(2,1);


a=(x_upperbond-x_lowerbond)*rand(1,population)+x_lowerbond;


% bit_change=((a-x_lowerbond)/(x_upperbond-x_lowerbond))*(2^bit_length-1);


% bit_change=dec2bin(bit_change,bit_length);


end


function bit_decimal


end


function decimal_bit


end


function [new_cost_function_value]=selection(cost_function,random_x_data)


[cost_function_value]=cost_function(random_x_data);


[cost_function_value]=sort(cost_function_value); 


% selection=fix(population*percent)


Q3=prctile(cost_function_value,50);%1/2位數


cost_function_value_percent=floor(cost_function_value/Q3)


k=1;


length=size(cost_function_value,2)


for i=1:length


if cost_function_value_percent(i)>0


for j=1:cost_function_value_percent(i)+1


new_cost_function_value(:,k)=cost_function_value(:,i)


k=k+1;


end


end


end 


end    


function cross_over(new_cost_function_value,cross_over_percent,bit_length)


length=size(new_cost_function_value,2)


a=shuffle(length)


b=shuffle(bit_length)


cross_number=length*cross_over_percent


k=1;


%兩個random_number 


for i=1:cross_number


a()

end


end


function  a=shuffle(trail_numb)


for j=1:trail_numb


a(j)=j;


end


for i=1:trail_numb


tmp=a(i);


ans=rem(randi(65536),(trail_numb+1)-i)+1;


a(i)=a(ans);


a(ans)=tmp;


end


end


function mutation(mutation_percent)


end

