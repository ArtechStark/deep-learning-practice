# PyTorchѧϰ�ʼ�

## Сϸ��

### 1. numpy()��from_numpy()�໥ת��������
ʹ��������������tensor��array�໥ת���󣬹����ڴ档������һ������״�仯������ת�ã�֮����һ��ά�ֲ��䣬�������Ԫ�ػ��ǰ���ԭ�ȵ�˳��һһ��Ӧ������a.t_()֮��ִ��a[1, 0] = 0����Ӧ�仯����b[0, 1]��

### 2. data()��detach()
data()��detach()�������ܷ��ز����ݶȵ�tensor����data()���ص�ֵ���޸ĺ�ԭ�ȵ��ݶ�Ҳ��仯����������Ĵ������ױ����֡�detach()����ֵ���޸ĺ��õ�ԭ�ݶ�ʱ�ᱨ�������°汾�Ƽ�ʹ��detach()��

### 3. nn.RNN/nn.LSTM�����롢�����ά��
model = nn.RNN(input_size, hidden_layer, num_layers)  
&emsp;&emsp;input_size������ÿһ���������������ά�ȣ������Ը���  
&emsp;&emsp;hidden_size��RNN�����㵥Ԫ��  
&emsp;&emsp;num_layers��RNN����  
  
inputs = torch.randn(time_steps, batch_size, input_size)  
&emsp;&emsp;time_steps������ʱ�����е����г��ȣ�������һ��ʮ�����ʵľ��ӣ�time_steps��Ϊ10  
&emsp;&emsp;batch_size����������˼  
&emsp;&emsp;input_size������ÿһ���������������ά�ȣ������Ը�����������һ��)  
&emsp;&emsp;ע�⣺������Ĭ����Ҫ��inputs����ά�ȣ�batch_sizeλ�ڵڶ�ά�������model�Ĳ������潫batch_first=True������Ҫ��inputsά�ȱ�Ϊ(batch_size, time_steps, input_size)  
  
h0 = torch.zeros(num_layers, batch_size, hidden_size)  
out, h = model(inputs, h0)  
&emsp;&emsp;out��shapeΪ[time_steps, batch_size, hidden_size]  
&emsp;&emsp;h��shapeΪ[num_layers, batch_size, hidden_size]  
&emsp;&emsp;����out[-1, :, :]��h[-1, :, :]���
