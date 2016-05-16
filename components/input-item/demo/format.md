---
order: 1
title: 格式
---------

支持银行卡（format="bankCard"）,手机号码（format="phone"）,密码三种类型的格式（format="password"）

---

````jsx
import { List, InputItem } from 'antm';
import { createForm } from 'rc-form';

let FormatExample = React.createClass({
  render() {
    const { getFieldProps } = this.props.form;
    return (<List>
      <List.Header>格式</List.Header>
      <List.Body>
        <InputItem
          {...getFieldProps('bankCard', {
            initialValue: '8888 8888 8888 8888',
            valuePropName: 'value'
          })}
          format="bankCard"
          placeholder="8888 8888 8888 8888"
          clear
          maxLength={22}
          onBlur={function (e) {console.log('onBlur'); console.log(e);}}
          onFocus={function (e) {console.log('onFocus'); console.log(e);}}
        >银行卡</InputItem>
        <InputItem
          {...getFieldProps('phone', {
            initialValue: '186 1234 1234',
            valuePropName: 'value'
          })}
          format="phone"
          placeholder="186 1234 1234"
          clear
          maxLength={22}
          onBlur={ function (e) {console.log('onBlur'); console.log(e);}}
          onFocus={ function (e) {console.log('onFocus'); console.log(e);}}
        >电话号码</InputItem>
        <InputItem
          {...getFieldProps('password', {
            initialValue: '123131',
            valuePropName: 'value'
          })}
          format="password"
          placeholder="****"
          clear
          maxLength={22}
          onBlur={ function (e) {console.log('onBlur'); console.log(e);}}
          onFocus={ function (e) {console.log('onFocus'); console.log(e);}}
        >密码</InputItem>
      </List.Body>
    </List>);
  }
});

FormatExample = createForm()(FormatExample);

ReactDOM.render(<FormatExample />, mountNode);

````