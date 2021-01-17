<style>table { width: 100%; }</style>
**React Native Pincode**

The options look intimidating, but don't worry. Almost all of them are optional while allowing you to customize the text and layout.

## Properties
| Name           | Description                                                                                                                                                                                                              | Required | Default |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------- | ------- |
| visible        | Show or not show the component                                                                                                                                                                                           | true     | false   |
| mode           | The component has 4 modes:<ul><li>enter: user has to enter the PIN to access</li><li>set: set up new PIN</li><li>locked: lock the user from accessing and count down.</li><li>reset: allow user to remove PIN.</li></ul> | true     | 'enter' |
| onEnterSuccess | callback when the mode is 'enter' and the user has entered PIN successfully.<br/>Parameters:<ul><li>pin (string, optional): the entered PIN</li></ul>                                                                    | false    |         |
| onSetSuccess   | callback when the mode is 'set' and the user has set a new PIN successfully.<br/>Parameters:<ul><li>pin (string, optional): the set PIN</li></ul>                                                                        | false    |         |
| onSetCancel    | callback when the mode is 'set' and the user has canceled the setting.                                                                                                                                                   | false    |         |
| onResetSuccess | callback when the mode is 'reset' and the PIN is cleared successfully.                                                                                                                                                   | false    |         |
| options        | Specify how the component works. Check the options below                                                                                                                                                                 | false    |         |
| textOptions    | Allow customizing the texts in the component. Check the options below                                                                                                                                                    | false    |         |
| styles         | Allow customizing the layout of the screens. Check the style options below                                                                                                                                               | false    |         |

## Options
| Name         | Description                                                                                                                                                                                                                                        | Required | Default |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------- |
| disableLock  | Do not display lock screen. By default, the locked screen is shown when maxAttempt has reached.                                                                                                                                                    | false    | false   |
| maxAttempt   | The number of attempts when entering PIN. When user enters wrong PIN for a number of times, the Locked screen is shown                                                                                                                             | 10       | false   |
| lockDuration | The time that the Locked screen is shown in miliseconds                                                                                                                                                                                            | false    | 60000   |
| allowReset   | If allowReset is set to true, the "Forgot PIN?" button is displayed at the bottom of the Enter screen                                                                                                                                              | false    | true    |
| backSpace    | On Enter/Set screen the "Delete" button is used to delete the entered digit. But you can pass an ```<Icon name='backspace' size={24} />``` to display an icon instead. This is to remove the react-native-vector-icon dependency from the package. | false    |         |
| backSpace    | On Locked screen the "Locked" text is shown above the clock. But you can pass an ```<Icon name='lock' size={24} />``` to display an icon instead. This is to remove the react-native-vector-icon dependency from the package.                      | false    |         |

## Text Options
The text options are grouped by screen for the ease to find. You can pass the textOptions in this syntax
```
<Pincode mode='enter' 
  textOptions={{
    enter: {
      title: 'custom enter title',
      subTitle: 'custom sub title',
      error: 'wrong pin',
      backSpace: 'del'
    },
    set: {
      title: 'custom set title',
      subTitle: 'custom sub title',
      repeat: 'Enter pin again',
      error: 'repeated pin doesn't match '
    },
    locked: {
      title: 'custom locked title',
      subTitle: 'custom locked sub title',
      lockedText: 'locked'
    },
    reset: {
      title: 'custom reset title',
      subTitle: 'custom reset sub title',
      confirm: 'custom confirm text'
    }
  }}
/>
```
#### Enter screen text options
| Name      | Description                             | Required | Default                      |
| --------- | --------------------------------------- | -------- | ---------------------------- |
| title     | the Enter screen title                  | false    | Enter PIN                    |
| subTitle  | the Enter screen sub title              | false    | Enter 4-digit PIN to access. |
| error     | error message when user enter wrong PIN | false    | Wrong PIN! Try again.        |
| backSpace | the text of the backspace button        | false    | Delete                       |

#### Set screen text options
| Name     | Description                                       | Required | Default                                   |
| -------- | ------------------------------------------------- | -------- | ----------------------------------------- |
| title    | the Set screen title                              | false    | Set up a new PIN                          |
| subTitle | the Set screen sub title                          | false    | Enter 4 digits.                           |
| repeat   | the text to ask to enter new PIN again            | false    | Enter new PIN again.                      |
| error    | the error message when repeated PIN doesn't match | false    | PIN don't match. Start the process again. |

#### Locked screen text options
| Name       | Description                                                                      | Required | Default                                                                    |
| ---------- | -------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------- |
| title      | the Locked screen title                                                          | false    | Locked                                                                     |
| subTitle   | the Locked screen sub title                                                      | false    | Your have entered wrong PIN many times.<br/>The app is temporarily locked. |
| lockedText | the locked text (this can be replaced with icon) by using the lockedIcon options | false    | Locked                                                                     |

#### Reset screen text options
| Name     | Description                       | Required | Default                                                |
| -------- | --------------------------------- | -------- | ------------------------------------------------------ |
| title    | the Reset screen title            | false    | Forgot PIN?                                            |
| subTitle | the Reset screen sub title        | false    | Remove the PIN may wipe out the app data and settings. |
| confirm  | Ask user to confirm removeing PIN | false    | Are you sure you want remove the PIN?                  |

## Styles options
The style is organized like textOptions for the ease of finding
