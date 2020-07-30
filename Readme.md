# react-native-responsive-dimension

react-native-responsive-dimension is a small library that provides simple methods to convert pixels in to DP based on the device's width and height so that React Native developers can code their UI elements completely responsive without using media queries.

It also provides an optional method for screen orientation detection and automatic re-rendering according to new dimensions.

# Installation

Run this command in terminal inside your projects root folder.

`npm install react-native-responsive-dimension`

Or if you using Yarn

`yarn add react-native-responsive-dimension`


# Usage

### With Fixed Size

```
import {fixedWidth as fw, fixedHeight as fh} from 'react-native-responsive-dimension';

class AwesomeResponsiveComponent extends Component {
  render() {
    return (
      <View style={styles.container}>
        <View style={styles.textWrapper}>
          <Text style={styles.myText}>Login</Text>
        </View>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: { flex: 1 },
  textWrapper: {
    height: fh(70), // 70 dp calculated based on device's height
    width: fw(80)   // 80 dp calculated based on device's width
  },
  myText: {
    fontSize: fw(12) // Scale up/down on different devices equivalent to 12px -> 12sp
  }
});

export default AwesomeResponsiveComponent;

...

```

### With Percentage size

```
import {percentageWidth as pw, percentageHeight as ph} from 'react-native-responsive-dimension';

class AwesomeResponsiveComponent extends Component {
  render() {
    return (
      <View style={styles.container}>
        <View style={styles.textWrapper}>
          <Text style={styles.myText}>Login</Text>
        </View>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: { flex: 1 },
  textWrapper: {
    height: ph(70), // 70% of height device screen
    width: pw(80)   // 80% of width device screen
  },
  myText: {
    fontSize: ph(5) // 5% of height device screen
  }
});

export default AwesomeResponsiveComponent;

...

```
