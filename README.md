# کتاب آموزشی: از صفر تا قهرمانی با React Native و Expo

---

## مقدمه

به دنیای هیجان‌انگیز توسعه اپلیکیشن موبایل با React Native و Expo خوش آمدید! در این کتاب، شما از **مفاهیم پایه تا تکنیک‌های پیشرفته** را فرا خواهید گرفت تا بتوانید ایده‌های خود را به اپلیکیشن‌های موبایل قدرتمند و زیبا برای هر دو پلتفرم iOS و Android تبدیل کنید.

هدف ما این است که شما را از یک توسعه‌دهنده تازه‌کار به یک متخصص در زمینه React Native و Expo تبدیل کنیم، به گونه‌ای که بتوانید هر ایده‌ای را به یک اپلیکیشن واقعی، باکیفیت و قابل انتشار تبدیل کنید. ما مسیر **Expo** را به عنوان استاندارد مدرن و کارآمد دنبال خواهیم کرد. این مسیر، شروع کار را به شدت ساده کرده و به شما امکان می‌دهد با تمرکز بر کد جاوااسکریپت، اپلیکیشن‌های نیتیو بسازید، بدون اینکه نیازی به نصب پیچیده Xcode یا Android Studio در ابتدای کار داشته باشید.

هدف این کتاب، ارائه یک **مسیر یادگیری گام به گام و منطقی** است، به‌گونه‌ای که حتی اگر تجربه قبلی در توسعه موبایل نداشته باشید، بتوانید با اطمینان کامل پیش بروید و در نهایت یک توسعه‌دهنده React Native ماهر شوید. آینده توسعه موبایل در دستان شماست. بیایید شروع کنیم! 🚀

### پیش‌نیازها

پیش از شروع این کتاب، آشنایی با مفاهیم زیر به شما در درک بهتر مطالب کمک شایانی خواهد کرد:

*   **دانش زبان جاوااسکریپت (ES6+)**:
    *   مفاهیم پایه مانند متغیرها، توابع و شرط‌ها.
    *   ویژگی‌های مدرن شامل توابع پیکانی (Arrow Functions)، Promise ها و async/await.
    *   ماژول‌های import و export.
    *   متدهای پرکاربرد آرایه‌ها مانند `.map()` و `.filter()`.
*   **مفاهیم بنیادی React.js**:
    *   کامپوننت‌های تابعی و سینتکس JSX.
    *   مفاهیم Props و State.
    *   هوک‌های پایه مانند `useState` و `useEffect` و درک چرخه حیات کامپوننت.
*   **آشنایی با مفاهیم وب**:
    *   درک ساختاردهی مشابه HTML و استایل‌دهی مشابه CSS.
*   **کار با ترمینال (خط فرمان)**:
    *   توانایی اجرای دستورات پایه‌ای مانند `cd` و استفاده از `npm` یا `npx` برای مدیریت پکیج‌ها.

---

## فصل ۱: خوش آمدگویی به دنیای React Native

در این فصل، شما با هسته فلسفه React Native، نحوه کارکرد آن در پشت صحنه، و مهم‌ترین تصمیم اولیه برای شروع پروژه‌هایتان آشنا خواهید شد. همچنین، با فلسفه اصلی و معماری منحصر به فرد React Native آشنا می‌شویم و تفاوت‌های کلیدی آن را با سایر رویکردهای توسعه موبایل بررسی می‌کنیم.

### ۱-۱: فلسفه اصلی React Native

**React Native** یک فریم‌ورک **متن-باز** است. این فریم‌ورک به شما اجازه می‌دهد با استفاده از دانش **React** و زبان **جاوااسکریپت**، اپلیکیشن‌های موبایل کاملاً **نیتیو (Native)** برای پلتفرم‌های iOS و Android بسازید.

**نکته کلیدی و وجه تمایز اصلی React Native** این است که بر خلاف ابزارهایی که یک وب‌سایت را در قاب اپلیکیشن نمایش می‌دهند (**WebView**)، کدهای شما به عناصر واقعی و بومی رابط کاربری در هر پلتفرم ترجمه می‌شوند. این معماری باعث می‌شود عملکرد، ظاهر و حس اپلیکیشن شما دقیقاً مانند اپلیکیشنی باشد که با زبان‌های اصلی آن پلتفرم (مانند **Swift** برای iOS یا **Kotlin** برای Android) نوشته شده است.

به عنوان مثال:
*   `<View>` در کد React Native شما، به `UIView` در iOS و `ViewGroup` در Android تبدیل می‌شود.
*   `<Text>` در کد React Native شما، به `UITextView` در iOS و `TextView` در Android تبدیل خواهد شد.

### ۱-۲: معماری درونی: نخ JS و نخ UI

یک اپلیکیشن **React Native** در دو "قلمرو" یا **Thread (نخ)** اصلی به صورت موازی عمل می‌کند:

*   **نخ جاوااسکریپت (JS Thread)**:
    *   این نخ مسئولیت اجرای **تمام کدهای React شما**، منطق برنامه، مدیریت وضعیت (state) و فراخوانی APIها را بر عهده دارد.
    *   این نخ را می‌توان به عنوان "مغز" یا "فکر کردن" اپلیکیشن در نظر گرفت.
*   **نخ اصلی/UI (Main/UI Thread)**:
    *   این نخ وظیفه **تمام کارهای بصری** را بر عهده دارد؛ از جمله رندر کردن پیکسل‌ها روی صفحه و پاسخ به ژست‌های لمسی کاربر.
    *   برای اینکه کاربر تجربه‌ای روان و بدون لگ داشته باشد، این نخ باید همیشه آزاد و سریع باقی بماند.

این دو نخ از طریق یک مکانیزم ارتباطی مدرن به نام **JSI (JavaScript Interface)** با یکدیگر ارتباط برقرار می‌کنند. **JSI** به جاوااسکریپت اجازه می‌دهد تا به صورت **مستقیم** به اشیاء و توابع نیتیو دسترسی پیدا کند، که این امر به بهبود عملکرد و پاسخ‌گویی اپلیکیشن کمک شایانی می‌کند.

### ۱-۳: انتخاب مسیر: Expo در مقابل React Native CLI

این مهم‌ترین تصمیم در ابتدای هر پروژه **React Native** است.

*   **Expo**:
    *   یک فریم‌ورک و مجموعه‌ای جامع از ابزارهاست که روی **React Native** ساخته شده تا فرآیند توسعه را به شدت ساده‌تر کند.
    *   با **Expo** نیازی به نصب **Xcode** یا **Android Studio** برای شروع کار ندارید.
    *   این پلتفرم دسترسی به **مجموعه‌ای عظیم از کتابخانه‌های آماده** را فراهم می‌کند که بسیاری از قابلیت‌های رایج موبایل (مانند دوربین، نقشه، اعلان‌ها) را پوشش می‌دهند.
    *   سرویس ابری **EAS** نیز فرآیند ساخت و انتشار اپلیکیشن را به شدت تسهیل می‌کند.
    *   **این مسیر برای ۹۹٪ پروژه‌ها پیشنهاد می‌شود**.
*   **React Native CLI**:
    *   این روش "خالص" و مستقیم استفاده از **React Native** است.
    *   به شما **کنترل کامل** روی تمام جنبه‌های نیتیو پروژه را می‌دهد.
    *   اما راه‌اندازی و نگهداری آن به طور قابل توجهی پیچیده‌تر است و نیازمند دانش عمیق‌تر از توسعه نیتیو می‌باشد.

**در این دوره آموزشی، ما مسیر Expo را به عنوان استاندارد مدرن و کارآمد دنبال خواهیم کرد**.

---

## فصل ۲: راه‌اندازی و گردش کار توسعه

اکنون که با مفاهیم پایه آشنا شدیم، زمان آن رسیده که محیط توسعه خود را راه‌اندازی کرده و اولین اپلیکیشن React Native خود را با Expo بسازیم. این فصل شما را با مراحل اولیه، از ساخت پروژه تا اجرای آن روی دستگاه‌های واقعی یا شبیه‌ساز، و همچنین ابزارهای مهم اشکال‌زدایی آشنا می‌کند.

### ۲-۱: راه‌اندازی محیط

برای ساخت یک پروژه خام (**Blank**) با **Expo** که به طور پیش‌فرض از **TypeScript** استفاده می‌کند [6، 54]، از دستور زیر در ترمینال خود استفاده کنید:

```bash
npx create-expo-app YourProjectName
```

**توضیح**:
*   **npx**: یک ابزار برای اجرای پکیج‌های Node.js بدون نیاز به نصب سراسری آن‌ها.
*   **create-expo-app**: دستوری که توسط Expo برای ایجاد پروژه‌های جدید ارائه شده است.
*   **YourProjectName**: نامی که می‌خواهید برای پروژه خود انتخاب کنید.

پس از اینکه پروژه با موفقیت ساخته شد، وارد پوشه پروژه شوید و سرور توسعه (**Metro Bundler**) را با دستور زیر اجرا کنید:

```bash
cd YourProjectName
npm start
```

**سرور Metro** مسئول کامپایل کردن کد جاوااسکریپت شما و سرویس‌دهی آن به اپلیکیشن در حال اجراست. با اجرای `npm start`، یک **QR Code** در ترمینال نمایش داده می‌شود که برای اجرای اپلیکیشن روی دستگاه واقعی استفاده می‌شود.

### ۲-۲: اجرای اپلیکیشن

شما دو راه اصلی برای دیدن نتیجه کدهای خود دارید:

1.  **دستگاه واقعی (پیشنهادی)**:
    *   ابتدا اپلیکیشن **Expo Go** را از App Store (برای iOS) یا Google Play Store (برای Android) روی گوشی هوشمند خود نصب کنید.
    *   **اطمینان حاصل کنید که کامپیوتر و گوشی شما به یک شبکه Wi-Fi مشترک متصل هستند**.
    *   سپس، **QR Code** نمایش داده شده در ترمینال (پس از اجرای `npm start`) را با استفاده از اپلیکیشن Expo Go در گوشی خود اسکن کنید. اپلیکیشن شما به سرعت روی دستگاه لود و اجرا خواهد شد.
2.  **شبیه‌ساز (Simulator/Emulator)**:
    *   برای اجرای اپلیکیشن روی شبیه‌ساز iOS، باید **Xcode** را روی یک کامپیوتر Mac نصب کنید.
    *   برای اجرای اپلیکیشن روی شبیه‌ساز Android، باید **Android Studio** را روی کامپیوتر خود نصب کنید.
    *   پس از نصب و پیکربندی مناسب، می‌توانید یک گوشی را روی کامپیوتر خود شبیه‌سازی کرده و اپلیکیشن را روی آن اجرا کنید.

### ۲-۳: ابزارهای اشکال‌زدایی (Debugging)

**React Native** و **Expo** ابزارهای قدرتمندی برای اشکال‌زدایی (**Debugging**) ارائه می‌دهند که فرآیند توسعه را سریع‌تر و کارآمدتر می‌کنند:

*   **منوی توسعه‌دهنده (Developer Menu)**:
    *   این منو حاوی گزینه‌های مفیدی برای اشکال‌زدایی و تنظیمات توسعه است.
    *   برای باز کردن آن روی دستگاه واقعی، دستگاه را تکان دهید.
    *   یا با کلیدهای میانبر در شبیه‌ساز (Ctrl+Cmd+Z در iOS یا Ctrl+M در ویندوز/لینوکس).
*   **Fast Refresh**:
    *   یکی از بهترین ویژگی‌های **React Native** که بهره‌وری را به شدت افزایش می‌دهد.
    *   با ذخیره کردن کد، تغییرات به صورت **آنی** و **بدون از دست رفتن وضعیت (state) فعلی اپلیکیشن**، روی صفحه اعمال می‌شوند.
    *   این بدان معناست که لازم نیست هر بار اپلیکیشن را مجدداً بارگذاری کنید و تجربه توسعه را بسیار سریع‌تر می‌کند.
*   **LogBox**:
    *   این ابزار به شما کمک می‌کند تا خطاها و هشدارها را به راحتی شناسایی کنید.
    *   خطاهای جدی را در یک **صفحه قرمز (RedBox)** تمام صفحه نمایش می‌دهد.
    *   هشدارها را در یک **کادر زرد (YellowBox)** در پایین صفحه نمایش می‌دهد.
    *   این به شما کمک می‌کند مشکلات را به سرعت شناسایی کنید.
*   **Element Inspector**:
    *   این ابزار به شما اجازه می‌دهد روی هر عنصر **UI** کلیک کرده و اطلاعات مربوط به استایل، چیدمان (layout) و پراپ‌های آن را بررسی کنید.
    *   این ویژگی مشابه ابزار Inspect Element در مرورگرهای وب است و برای درک نحوه رندر شدن کامپوننت‌ها بسیار مفید است.

---

## فصل ۳: آجرهای ساختمان: کامپوننت‌های اصلی (بخش اول)

در این فصل، با اساسی‌ترین کامپوننت‌های **React Native** که برای ساخت رابط کاربری (**UI**) هر اپلیکیشنی مورد نیاز هستند، آشنا می‌شویم. این کامپوننت‌ها به عنوان آجرهای ساختمانی **UI** شما عمل می‌کنند.

### ۳-۱: `<View>` – ظرف اصلی چیدمان

کامپوننت `<View>` بنیادی‌ترین و پرکاربردترین کامپوننت برای ساخت **UI** در **React Native** است.

*   **معادل وب**: در توسعه وب، `<View>` معادل یک `<div>` است.
*   **کاربرد**:
    *   `<View>` به عنوان یک **کانتینر** برای گروه‌بندی و چیدمان کامپوننت‌های دیگر استفاده می‌شود.
    *   به خودی خود دیده نمی‌شود، مگر اینکه به آن استایل (مانند پس‌زمینه یا حاشیه) بدهید.
    *   این کامپوننت، بستر اصلی پیاده‌سازی **Flexbox** است که یک سیستم قدرتمند برای چیدمان عناصر در رابط کاربری است.

**مثال کد**:
```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

export default function MyBasicView() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>این یک View ساده است!</Text>
      <View style={styles.innerBox} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    backgroundColor: '#ADD8E6', // آبی روشن
    padding: 20,
    margin: 10,
    borderRadius: 8,
    justifyContent: 'center',
    alignItems: 'center',
    height: 150,
  },
  text: {
    color: 'white',
    fontSize: 18,
    fontWeight: 'bold',
    marginBottom: 10,
  },
  innerBox: {
    width: 50,
    height: 50,
    backgroundColor: '#FF6347', // نارنجی
    borderRadius: 5,
  },
});
```

### ۳-۲: `<Text>` – تنها راه نمایش متن

یک قانون بسیار مهم در **React Native** این است که **تمام متن‌ها باید داخل یک کامپوننت `<Text>` قرار بگیرند**. شما نمی‌توانید متن را مستقیماً داخل یک `<View>` یا هر کامپوننت دیگری بنویسید.

*   **معادل وب**: در وب، `<Text>` می‌تواند معادل تگ‌هایی مانند `<p>`, `<span>`, `<h1>` و غیره باشد.
*   **ویژگی**: کامپوننت‌های `<Text>` می‌توانند **داخل هم قرار بگیرند (Nest شوند)** و استایل‌ها را از والد خود به ارث ببرند. این ویژگی برای اعمال استایل‌های متفاوت به بخش‌های مختلف یک جمله مفید است.

**مثال کد**:
```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

export default function NestedTextExample() {
  return (
    <View style={styles.container}>
      <Text style={styles.baseText}>
        این یک متن
        <Text style={styles.boldText}>پررنگ</Text>
        و
        <Text style={styles.italicText}>مورب</Text>
        است که
        <Text style={styles.underlinedText}>زیرخط</Text>
        دارد.
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    padding: 20,
    alignItems: 'center',
  },
  baseText: {
    fontSize: 16,
    color: '#333',
    lineHeight: 24,
  },
  boldText: {
    fontWeight: 'bold',
    color: '#007bff',
  },
  italicText: {
    fontStyle: 'italic',
    color: '#28a745',
  },
  underlinedText: {
    textDecorationLine: 'underline',
    color: '#dc3545',
  },
});
```

### ۳-۳: `<Image>` – نمایش تصاویر

کامپوننت `<Image>` برای نمایش انواع تصاویر در اپلیکیشن شما استفاده می‌شود.

*   **پراپ اصلی**: **source**. این پراپ مسیر یا **URL** تصویر را مشخص می‌کند.
*   **تصاویر محلی**:
    *   برای تصاویری که در پوشه پروژه شما قرار دارند (مثلاً در assets/images)، باید از تابع `require` استفاده کنید.
    *   این کار به باندلر (**Metro**) کمک می‌کند تا عکس را در بسته نهایی اپلیکیشن قرار دهد و در زمان کامپایل، آن را مدیریت کند.
    *   **مثال**:
        ```jsx
        <Image source={require('./assets/images/logo.png')} />
        ```
*   **تصاویر اینترنتی**:
    *   برای عکس‌هایی که از یک **URL** بارگذاری می‌شوند، باید از یک آبجکت با کلید `uri` در پراپ source استفاده کنید.
    *   **حتماً** `width` و `height` را در استایل مشخص کنید، در غیر این صورت تصویر نمایش داده نخواهد شد.
    *   **مثال**:
        ```jsx
        <Image
          source={{ uri: 'https://reactnative.dev/img/tiny_logo.png' }}
          style={{ width: 50, height: 50 }}
        />
        ```

### ۳-۴: `<TextInput>` – دریافت ورودی از کاربر

کامپوننت `<TextInput>` برای ساختن فیلدهای ورودی متن استفاده می‌شود و به کاربر امکان می‌دهد تا متن را وارد کند.

*   **معادل وب**: این کامپوننت معادل تگ `<input type="text">` در وب است.
*   **مهم‌ترین پراپ‌ها**:
    *   `value`: برای **کنترل مقدار ورودی** از طریق **state** در **React** استفاده می‌شود. این باعث می‌شود TextInput یک "کامپوننت کنترل‌شده" باشد.
    *   `onChangeText`: تابعی که با **هر تغییر** در متن ورودی توسط کاربر فراخوانی می‌شود. این تابع معمولاً برای به‌روزرسانی **state** مربوط به مقدار ورودی استفاده می‌شود.
    *   `placeholder`: برای نمایش **متن جایگزین** (**Hint text**) در فیلد ورودی زمانی که خالی است، استفاده می‌شود.
    *   `keyboardType`: برای تعیین **نوع کیبورد** مجازی که برای کاربر نمایش داده می‌شود. برای مثال، `numeric` برای ورودی‌های عددی یا `email-address` برای آدرس ایمیل.
    *   `secureTextEntry`: یک مقدار boolean است که اگر `true` باشد، متن وارد شده را مخفی می‌کند (مانند فیلدهای رمز عبور).

**مثال کد**:
```jsx
import React, { useState } from 'react';
import { View, TextInput, Text, StyleSheet } from 'react-native';

export default function ControlledTextInput() {
  const [username, setUsername] = useState('');
  const [password, setPassword] = useState('');

  return (
    <View style={styles.container}>
      <TextInput
        style={styles.input}
        onChangeText={setUsername}
        value={username}
        placeholder="نام کاربری"
        keyboardType="email-address"
        autoCapitalize="none"
      />
      <TextInput
        style={styles.input}
        onChangeText={setPassword}
        value={password}
        placeholder="رمز عبور"
        secureTextEntry={true}
        keyboardType="default"
      />
      <Text style={styles.display}>نام کاربری: {username}</Text>
      <Text style={styles.display}>رمز عبور (مخفی): {password.replace(/./g, '*')}</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    padding: 20,
    backgroundColor: '#f8f8f8',
    borderRadius: 10,
    margin: 10,
  },
  input: {
    height: 50,
    borderColor: '#ddd',
    borderWidth: 1,
    borderRadius: 8,
    paddingHorizontal: 15,
    marginBottom: 15,
    fontSize: 16,
    backgroundColor: 'white',
  },
  display: {
    fontSize: 15,
    marginTop: 5,
    color: '#555',
  },
});
```

---

## فصل ۴: آجرهای ساختمان: کامپوننت‌های اصلی (بخش دوم)

در این فصل، با دیگر کامپوننت‌های اصلی **React Native** که برای ساخت یک اپلیکیشن کامل و تعاملی نیاز دارید، آشنا می‌شویم. این کامپوننت‌ها امکاناتی از جمله تعاملات لمسی، نمایش محتوای موقت، و کنترل وضعیت‌های مختلف را فراهم می‌کنند.

### ۴-۱: `<Pressable>` – تعامل‌پذیری کامل

کامپوننت `<Pressable>` مدرن‌ترین و اصلی‌ترین راه برای مدیریت هر نوع تعامل لمسی در **React Native** است. `<Pressable>` به عنوان یک "لفافه" (**Wrapper**) عمل می‌کند؛ هر چیزی را که داخل آن قرار دهید، قابل کلیک و تعامل لمسی می‌شود.

*   **پراپ‌های اصلی**:
    *   `onPress`: تابعی که هنگام یک **کلیک کوتاه** یا ضربه زدن فراخوانی می‌شود.
    *   `onLongPress`: تابعی که هنگام **فشردن طولانی** یک عنصر فراخوانی می‌شود.
*   **قابلیت کلیدی**: یکی از ویژگی‌های قدرتمند `<Pressable>` این است که می‌توانید به پراپ `style` آن یک **تابع** بدهید. این تابع یک آبجکت شامل وضعیت `pressed` را دریافت می‌کند (`(style={({ pressed }) => ...})`) و به شما اجازه می‌دهد تا بر اساس وضعیت فشرده شدن، استایل کامپوننت را به صورت **داینامیک تغییر دهید**. این ویژگی برای ایجاد دکمه‌هایی با بازخورد بصری زیبایی هنگام لمس بسیار مفید است.

**مثال کد**:
```jsx
import React from 'react';
import { Pressable, Text, StyleSheet } from 'react-native';

export default function DynamicPressableButton() {
  const handlePress = () => {
    alert('دکمه با موفقیت فشرده شد!');
  };

  const handleLongPress = () => {
    alert('دکمه برای مدت طولانی فشرده شد!');
  };

  return (
    <Pressable
      onPress={handlePress}
      onLongPress={handleLongPress}
      style={({ pressed }) => [
        styles.button,
        pressed ? styles.buttonPressed : styles.buttonNormal,
      ]}
    >
      <Text style={styles.buttonText}>
        فشاردن یا نگه داشتن
      </Text>
    </Pressable>
  );
}

const styles = StyleSheet.create({
  button: {
    paddingVertical: 15,
    paddingHorizontal: 30,
    borderRadius: 10,
    alignItems: 'center',
    justifyContent: 'center',
    margin: 20,
    minWidth: 200,
  },
  buttonNormal: {
    backgroundColor: '#2196F3', // رنگ آبی پیش‌فرض
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.2,
    shadowRadius: 3,
    elevation: 4,
  },
  buttonPressed: {
    backgroundColor: '#0d47a1', // رنگ آبی تیره‌تر هنگام فشردن
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 1 },
    shadowOpacity: 0.3,
    shadowRadius: 2,
    elevation: 2,
  },
  buttonText: {
    color: 'white',
    fontSize: 18,
    fontWeight: 'bold',
  },
});
```

### ۴-۲: `<Button>` – دکمه ساده نیتیو

کامپوننت `<Button>` یک دکمه استاندارد سیستم‌عامل را نمایش می‌دهد.

*   **تفاوت اصلی با `<Pressable>`**:
    *   ظاهر `<Button>` کاملاً **بومی** است.
    *   **قابلیت استایل‌دهی بسیار محدودی** دارد.
    *   ظاهر آن در iOS و Android متفاوت خواهد بود و شما نمی‌توانید استایل‌های پیچیده‌ای روی آن اعمال کنید.
*   **پراپ‌های اصلی**: `title` (برای متن دکمه)، `onPress` (برای تابع کلیک)، و `color` (برای تغییر رنگ دکمه، در اندروید رنگ پس‌زمینه و در iOS رنگ متن).
*   **چه زمانی استفاده کنیم؟** `<Button>` برای کارهای سریع و موقتی مانند دکمه‌های داخل یک Alert یا برای نمونه‌سازی اولیه سریع مناسب است. برای ساخت دکمه‌های اصلی اپلیکیشن که نیاز به ظاهر سفارشی و یکپارچه در سراسر اپلیکیشن دارند، تقریباً همیشه از **`<Pressable>`** استفاده می‌شود.

**مثال کد**:
```jsx
import React from 'react';
import { Button, View, Alert, StyleSheet } from 'react-native';

export default function BasicButtonExample() {
  return (
    <View style={styles.container}>
      <Button
        title="دکمه ساده"
        onPress={() => Alert.alert('هشدار', 'شما روی دکمه ساده کلیک کردید!')}
        color="#841584" // رنگ بنفش
      />
      <View style={styles.separator} />
      <Button
        title="دکمه غیرفعال"
        onPress={() => Alert.alert('هشدار', 'این دکمه غیرفعال است و کار نمی‌کند.')}
        disabled={true}
        color="#a9a9a9" // رنگ خاکستری برای دکمه غیرفعال
      />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    gap: 15,
  },
  separator: {
    marginVertical: 10,
  }
});
```

### ۴-۳: `<Modal>` – نمایش محتوا روی صفحه

کامپوننت `<Modal>` برای نمایش محتوا به صورت موقت و **روی نمای اصلی اپلیکیشن** استفاده می‌شود. این کامپوننت معمولاً برای نمایش دیالوگ‌های پاپ‌آپ، فرم‌های موقت یا پیام‌های تأیید کاربرد دارد.

*   **پراپ‌های اصلی**:
    *   `visible`:
    *
    *     یک مقدار **boolean** که نمایش یا عدم نمایش **Modal** را کنترل می‌کند. اگر `true` باشد، مودال نمایش داده می‌شود.
    *   `animationType`:
    *
    *     نوع انیمیشن ورود مودال را مشخص می‌کند. مقادیر ممکن `'slide'` (از پایین به بالا)، `'fade'` (محو شدن) یا `'none'` (بدون انیمیشن) هستند.
    *   `onRequestClose`:
    *
    *     این تابع برای **پشتیبانی از دکمه بازگشت در اندروید** ضروری است. با فشردن دکمه بازگشت سخت‌افزاری، این تابع فراخوانی می‌شود و شما می‌توانید با به‌روزرسانی وضعیت `visible`، مودال را ببندید.

**مثال کد**:
```jsx
import React, { useState } from 'react';
import { Modal, View, Text, Button, StyleSheet } from 'react-native';

export default function BasicModalExample() {
  const [modalVisible, setModalVisible] = useState(false);

  return (
    <View style={styles.centeredView}>
      <Modal
        animationType="fade" // می تواند "slide" یا "none" باشد
        transparent={true}
        visible={modalVisible}
        onRequestClose={() => { // برای بستن با دکمه برگشت در اندروید
          setModalVisible(!modalVisible);
          console.log('Modal has been closed.');
        }}
      >
        <View style={styles.centeredView}>
          <View style={styles.modalView}>
            <Text style={styles.modalText}>این یک پنجره مودال است!</Text>
            <Button
              title="بستن مودال"
              onPress={() => setModalVisible(!modalVisible)}
            />
          </View>
        </View>
      </Modal>

      <Button
        title="نمایش مودال"
        onPress={() => setModalVisible(true)}
      />
    </View>
  );
}

const styles = StyleSheet.create({
  centeredView: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: 'rgba(0,0,0,0.5)', // پس‌زمینه نیمه‌شفاف
  },
  modalView: {
    margin: 20,
    backgroundColor: 'white',
    borderRadius: 20,
    padding: 35,
    alignItems: 'center',
    shadowColor: '#000',
    shadowOffset: {
      width: 0,
      height: 2,
    },
    shadowOpacity: 0.25,
    shadowRadius: 4,
    elevation: 5,
  },
  modalText: {
    marginBottom: 15,
    textAlign: 'center',
    fontSize: 18,
    fontWeight: 'bold',
    color: '#333',
  },
});
```

### ۴-۴: `<StatusBar>` – کنترل نوار وضعیت

کامپوننت `<StatusBar>` به شما اجازه می‌دهد تا **نوار وضعیت بالای صفحه** (جایی که ساعت، وضعیت باتری و آیکون‌های اعلان نمایش داده می‌شود) را کنترل کنید.

*   **پراپ‌های اصلی**:
    *   `barStyle`: رنگ متن و آیکون‌ها در نوار وضعیت را تعیین می‌کند. مقادیر ممکن عبارتند از:
        *   `'default'`
        *   `'light-content'` (مناسب برای پس‌زمینه‌های تیره نوار وضعیت)
        *   `'dark-content'` (مناسب برای پس‌زمینه‌های روشن نوار وضعیت)
    *   `backgroundColor`: رنگ پس‌زمینه نوار وضعیت را تعیین می‌کند. **این پراپ فقط در اندروید کار می‌کند**.
    *   `hidden`: یک مقدار boolean که برای **مخفی کردن نوار وضعیت** استفاده می‌شود.

**مثال کد**:
```jsx
import React, { useState } from 'react';
import { View, StatusBar, Button, StyleSheet, Text, Platform } from 'react-native';

export default function StatusBarExample() {
  const [isStatusBarHidden, setStatusBarHidden] = useState(false);
  const [statusBarStyle, setStatusBarStyle] = useState('dark-content');
  const [statusBarBackgroundColor, setStatusBarBackgroundColor] = useState('#F5FCFF');

  const changeBarStyle = () => {
    setStatusBarStyle(prevStyle =>
      prevStyle === 'dark-content' ? 'light-content' : 'dark-content'
    );
    if (Platform.OS === 'android') {
      setStatusBarBackgroundColor(prevColor => (prevColor === '#F5FCFF' ? '#333' : '#F5FCFF'));
    }
  };

  return (
    <View style={[styles.container, { backgroundColor: isStatusBarHidden ? '#ccc' : statusBarBackgroundColor }]}>
      <StatusBar
        animated={true}
        backgroundColor={Platform.OS === 'android' ? statusBarBackgroundColor : undefined}
        barStyle={statusBarStyle}
        hidden={isStatusBarHidden}
      />
      <Text style={styles.statusText}>
        نوار وضعیت: {isStatusBarHidden ? 'مخفی' : 'نمایش'}
      </Text>
      <Text style={styles.statusText}>
        استایل متن: {statusBarStyle}
      </Text>
      {Platform.OS === 'android' && (
        <Text style={styles.statusText}>
          رنگ پس‌زمینه (اندروید): {statusBarBackgroundColor}
        </Text>
      )}

      <Button
        title="تغییر استایل نوار وضعیت"
        onPress={changeBarStyle}
      />
      <Button
        title={isStatusBarHidden ? 'نمایش نوار وضعیت' : 'مخفی کردن نوار وضعیت'}
        onPress={() => setStatusBarHidden(!isStatusBarHidden)}
      />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    gap: 15,
  },
  statusText: {
    fontSize: 16,
    marginBottom: 5,
    color: '#333',
  },
});
```

### ۴-۵: `<Switch>` – کلید دو حالته

کامپوننت `<Switch>` یک کلید روشن/خاموش استاندارد نیتیو را نمایش می‌دهد. این کامپوننت معمولاً برای تنظیمات کاربری یا فعال/غیرفعال کردن قابلیت‌ها استفاده می‌شود.

*   **پراپ‌های اصلی**:
    *   `value`:
    *
    *     یک مقدار boolean که **وضعیت فعلی کلید** (روشن یا خاموش) را مشخص می‌کند.
    *   `onValueChange`:
    *
    *     تابعی که با **تغییر وضعیت کلید توسط کاربر** فراخوانی می‌شود. این تابع مقدار جدید boolean کلید را به عنوان آرگومان دریافت می‌کند و شما باید از آن برای به‌روزرسانی **state** مربوطه استفاده کنید.

**مثال کد**:
```jsx
import React, { useState } from 'react';
import { View, Switch, Text, StyleSheet } from 'react-native';

export default function BasicSwitchExample() {
  const [isNotificationsEnabled, setIsNotificationsEnabled] = useState(false);
  const toggleNotifications = () => setIsNotificationsEnabled(previousState => !previousState);

  return (
    <View style={styles.container}>
      <Text style={styles.label}>دریافت اعلان‌ها:</Text>
      <Switch
        trackColor={{ false: '#767577', true: '#81b0ff' }} // رنگ پس‌زمینه مسیر سوئیچ
        thumbColor={isNotificationsEnabled ? '#f5dd4b' : '#f4f3f4'} // رنگ دایره سوئیچ
        ios_backgroundColor="#3e3e3e" // رنگ مسیر در iOS وقتی خاموش است
        onValueChange={toggleNotifications}
        value={isNotificationsEnabled}
      />
      <Text style={styles.status}>
        وضعیت اعلان: {isNotificationsEnabled ? 'فعال' : 'غیرفعال'}
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    padding: 20,
  },
  label: {
    fontSize: 18,
    marginBottom: 10,
    color: '#333',
  },
  status: {
    marginTop: 20,
    fontSize: 16,
    color: '#555',
  }
});
```

### ۴-۶: `Alert API`

**Alert**

یک کامپوننت **React Native** نیست، بلکه یک **API** است. این **API** به شما اجازه می‌دهد تا یک دیالوگ هشدار استاندارد سیستم‌عامل را نمایش دهید. این دیالوگ‌ها برای نمایش پیام‌های مهم، درخواست تأیید کاربر یا نمایش خطاها مناسب هستند.

شما تابع `Alert.alert(title, message, buttons)` را فراخوانی می‌کنید.
*   `title`:
*
*     عنوان دیالوگ.
*   `message`:
*
*     پیام اصلی دیالوگ.
*   `buttons`:
*
*     (اختیاری) آرایه‌ای از آبجکت‌ها برای تعریف دکمه‌ها. هر آبجکت دکمه می‌تواند شامل `text`، `onPress` (تابعی که با کلیک روی دکمه اجرا می‌شود) و `style` (مثلاً `'cancel'` یا `'destructive'`) باشد.

**مثال**:
```jsx
import React from 'react';
import { Button, View, Alert, StyleSheet } from 'react-native';

export default function AlertExample() {
  const showAlert = () => {
    Alert.alert(
      'تایید حذف', // title
      'آیا از حذف این مورد اطمینان دارید؟', // message
      [
        {
          text: 'لغو',
          onPress: () => console.log('عملیات لغو شد'),
          style: 'cancel', // رنگ یا استایل کنسل شدن
        },
        {
          text: 'حذف',
          onPress: () => console.log('مورد حذف شد'),
          style: 'destructive', // رنگ یا استایل تخریب (معمولاً قرمز)
        },
      ],
      { cancelable: false } // آیا می توان با کلیک خارج از دیالوگ آن را بست؟
    );
  };

  return (
    <View style={styles.container}>
      <Button title="نمایش هشدار" onPress={showAlert} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
});
```

---

## فصل ۵: هنر چیدمان و استایل‌دهی

در این فصل، به قلب طراحی رابط کاربری در **React Native** می‌رویم و تکنیک‌های پیشرفته‌تری را برای ساخت **UI** های زیبا و واکنش‌گرا (**Responsive**) یاد می‌گیریم. تسلط بر این مفاهیم برای ساخت اپلیکیشن‌هایی که در اندازه‌ها و جهت‌گیری‌های مختلف صفحه نمایش به خوبی کار می‌کنند، ضروری است.

### ۵-۱: موقعیت‌یابی مطلق (Absolute Positioning)

به طور پیش‌فرض، تمام کامپوننت‌ها در **React Native** دارای `position: 'relative'` هستند. این بدان معناست که آن‌ها در جریان عادی چیدمان (**Flow Layout**) قرار می‌گیرند و نسبت به موقعیت خودشان جابجا می‌شوند.

اما گاهی اوقات شما نیاز دارید که یک عنصر را **روی** عناصر دیگر قرار دهید، به گونه‌ای که از جریان عادی چیدمان خارج شود. به عنوان مثال، قرار دادن یک نشان تعداد اعلان (**Badge**) روی یک آیکون. در این مواقع، از `position: 'absolute'` استفاده می‌کنیم.

عنصری که این استایل را دارد، نسبت به نزدیک‌ترین والد خود که `position` آن `relative` (که پیش‌فرض است) یا `absolute` باشد، موقعیت‌یابی می‌شود.

**مثال کد**:
```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';
import { MaterialIcons } from '@expo/vector-icons'; // فرض می‌کنیم از این کتابخانه برای آیکون‌ها استفاده می‌کنید

export default function AbsolutePositioningExample() {
  return (
    <View style={styles.container}>
      <View style={styles.iconContainer}>
        <MaterialIcons name="notifications" size={40} color="gray" />
        <View style={styles.badge}>
          <Text style={styles.badgeText}>3</Text>
        </View>
      </View>

      <View style={styles.card}>
        <Text style={styles.cardText}>کارت اطلاعات</Text>
        <View style={styles.statusDot} />
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f5f5f5',
    padding: 20,
    gap: 50,
  },
  iconContainer: {
    position: 'relative', // والد برای badge
    width: 60,
    height: 60,
    justifyContent: 'center',
    alignItems: 'center',
  },
  badge: {
    position: 'absolute',
    top: 0,
    right: 0,
    backgroundColor: 'red',
    borderRadius: 15,
    width: 25,
    height: 25,
    justifyContent: 'center',
    alignItems: 'center',
    borderWidth: 2,
    borderColor: 'white',
  },
  badgeText: {
    color: 'white',
    fontSize: 12,
    fontWeight: 'bold',
  },
  card: {
    width: 250,
    height: 150,
    backgroundColor: 'white',
    borderRadius: 15,
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 4 },
    shadowOpacity: 0.1,
    shadowRadius: 8,
    elevation: 6,
    justifyContent: 'center',
    alignItems: 'center',
    position: 'relative', // والد برای statusDot
  },
  cardText: {
    fontSize: 20,
    fontWeight: 'bold',
    color: '#333',
  },
  statusDot: {
    position: 'absolute',
    bottom: 10,
    left: 10,
    width: 15,
    height: 15,
    borderRadius: 7.5,
    backgroundColor: 'green',
    borderWidth: 2,
    borderColor: 'white',
  }
});
```

### ۵-۲: استایل‌دهی ریسپانسیو

ساخت **UI** که روی اندازه‌های مختلف صفحه (گوشی‌های کوچک، تبلت‌ها، حالت افقی و عمودی) خوب به نظر برسد، ترکیبی از چند تکنیک مهم است:

1.  **Flexbox**:
    *   این ابزار، **بهترین ابزار شما برای چیدمان ریسپانسیو** است.
    *   با استفاده از `flex: 1` به کامپوننت‌ها اجازه می‌دهید فضای موجود را پر کنند و به صورت انعطاف‌پذیر گسترش یابند.
    *   با پراپ‌های `justifyContent` (توزیع فضا در جهت اصلی) و `alignItems` (توزیع فضا در جهت متقاطع) نیز می‌توانید توزیع فضا و تراز کردن عناصر را به دقت مدیریت کنید.

**مثال کد برای Flexbox**:
```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

export default function FlexboxExample() {
  return (
    <View style={styles.container}>
      <View style={styles.flexRow}>
        <View style={[styles.box, styles.box1]}>
          <Text style={styles.text}>جعبه ۱</Text>
        </View>
        <View style={[styles.box, styles.box2]}>
          <Text style={styles.text}>جعبه ۲</Text>
        </View>
        <View style={[styles.box, styles.box3]}>
          <Text style={styles.text}>جعبه ۳</Text>
        </View>
      </View>

      <View style={styles.flexColumn}>
        <View style={[styles.box, styles.box4]}>
          <Text style={styles.text}>ردیف ۱</Text>
        </View>
        <View style={[styles.box, styles.box5]}>
          <Text style={styles.text}>ردیف ۲</Text>
        </View>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    padding: 20,
    backgroundColor: '#f0f0f0',
    justifyContent: 'space-around', // توزیع فضا بین ردیف و ستون
  },
  flexRow: {
    flex: 1,
    flexDirection: 'row',
    justifyContent: 'space-between', // توزیع فضا بین آیتم‌ها در راستای افقی
    alignItems: 'center', // وسط‌چین کردن آیتم‌ها در راستای عمودی
    backgroundColor: '#e0f7fa',
    borderRadius: 10,
    padding: 10,
    marginBottom: 20,
  },
  flexColumn: {
    flex: 1,
    flexDirection: 'column',
    justifyContent: 'center', // وسط‌چین کردن آیتم‌ها در راستای عمودی
    alignItems: 'flex-start', // شروع آیتم‌ها از چپ در راستای افقی
    backgroundColor: '#ffe0b2',
    borderRadius: 10,
    padding: 10,
  },
  box: {
    width: 80,
    height: 80,
    borderRadius: 8,
    justifyContent: 'center',
    alignItems: 'center',
    margin: 5,
  },
  box1: { backgroundColor: '#FFC107' }, // زرد
  box2: { backgroundColor: '#4CAF50' }, // سبز
  box3: { backgroundColor: '#2196F3' }, // آبی
  box4: { backgroundColor: '#9C27B0' }, // بنفش
  box5: { backgroundColor: '#FF5722' }, // نارنجی
  text: {
    color: 'white',
    fontWeight: 'bold',
  },
});
```

2.  **درصد (%)**:
    *   می‌توانید برای پراپ‌هایی مانند `width` و `height` از مقادیر **درصدی** استفاده کنید.
    *   این کار باعث می‌شود اندازه یک عنصر همیشه نسبتی از اندازه والدش باشد و با تغییر اندازه والد، اندازه آن نیز متناسباً تغییر کند.

**مثال کد برای درصد**:
```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

export default function PercentageExample() {
  return (
    <View style={styles.container}>
      <View style={styles.parentBox}>
        <View style={[styles.childBox, { width: '50%', height: '50%', backgroundColor: 'lightcoral' }]}>
          <Text style={styles.text}>50%</Text>
        </View>
        <View style={[styles.childBox, { width: '70%', height: '30%', backgroundColor: 'lightseagreen' }]}>
          <Text style={styles.text}>70%</Text>
        </View>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#eee',
  },
  parentBox: {
    width: '90%',
    height: '60%',
    backgroundColor: '#fff',
    borderWidth: 2,
    borderColor: '#ddd',
    borderRadius: 10,
    justifyContent: 'space-around',
    alignItems: 'center',
    flexDirection: 'row',
    flexWrap: 'wrap', // برای اینکه جعبه‌ها در صورت نیاز به خط بعدی بروند
  },
  childBox: {
    justifyContent: 'center',
    alignItems: 'center',
    margin: 5,
    borderRadius: 5,
  },
  text: {
    color: 'white',
    fontWeight: 'bold',
    fontSize: 16,
  },
});
```

3.  **`useWindowDimensions`**:
    *   این **هوک** (**Hook**) ابعاد فعلی صفحه نمایش (عرض و ارتفاع) را به شما می‌دهد.
    *   می‌توانید از آن برای تصمیم‌گیری‌های بزرگ در چیدمان استفاده کنید. به عنوان مثال، اگر عرض صفحه از یک مقدار مشخص (مثلاً ۶۰۰ پیکسل برای تبلت) بیشتر بود، یک لیست را به جای تک ستونه، دو ستونه نمایش دهید.
    *   **مثال**:
        ```jsx
        import React from 'react';
        import { View, Text, StyleSheet, useWindowDimensions } from 'react-native';

        export default function ResponsiveLayout() {
          const { width, height } = useWindowDimensions();

          const isLargeScreen = width > 768; // برای مثال، تبلت یا دسکتاپ

          return (
            <View style={styles.container}>
              <Text style={styles.infoText}>عرض صفحه: {width.toFixed(0)}px</Text>
              <Text style={styles.infoText}>ارتفاع صفحه: {height.toFixed(0)}px</Text>

              <View style={[
                styles.contentArea,
                { flexDirection: isLargeScreen ? 'row' : 'column' }
              ]}>
                <View style={[styles.panel, { flex: isLargeScreen ? 1 : 0, width: isLargeScreen ? 'auto' : '100%' }]}>
                  <Text style={styles.panelText}>پنل اول</Text>
                  <Text style={styles.subText}>این پنل در صفحه کوچک تمام عرض را اشغال می‌کند و در صفحه بزرگ نیمی از عرض.</Text>
                </View>
                <View style={[styles.panel, { flex: isLargeScreen ? 1 : 0, width: isLargeScreen ? 'auto' : '100%' }]}>
                  <Text style={styles.panelText}>پنل دوم</Text>
                  <Text style={styles.subText}>چیدمان بر اساس اندازه صفحه تغییر می‌کند.</Text>
                </View>
              </View>
            </View>
          );
        }

        const styles = StyleSheet.create({
          container: {
            flex: 1,
            alignItems: 'center',
            padding: 20,
            backgroundColor: '#fff',
            justifyContent: 'center',
          },
          infoText: {
            fontSize: 16,
            marginBottom: 10,
            color: '#555',
          },
          contentArea: {
            width: '100%',
            marginTop: 20,
            justifyContent: 'center',
            gap: 15,
          },
          panel: {
            backgroundColor: '#e6ffe6',
            padding: 15,
            borderRadius: 10,
            borderWidth: 1,
            borderColor: '#aaffaa',
            alignItems: 'center',
            justifyContent: 'center',
          },
          panelText: {
            fontSize: 18,
            fontWeight: 'bold',
            marginBottom: 5,
            color: '#333',
          },
          subText: {
            fontSize: 14,
            textAlign: 'center',
            color: '#666',
          }
        });
        ```

### ۵-۳: کدنویسی مختص پلتفرم

گاهی اوقات، لازم است که ظاهر یا رفتار اپلیکیشن شما در iOS و Android متفاوت باشد، زیرا هر پلتفرم دستورالعمل‌های طراحی خاص خود را دارد. **React Native** ابزارهایی برای مدیریت این تفاوت‌ها ارائه می‌دهد:

1.  **ماژول `Platform`**:
    *   این ماژول به شما اجازه می‌دهد در لحظه چک کنید که کد شما روی کدام سیستم‌عامل در حال اجراست.
    *   `Platform.OS`:
    *
    *     یک رشته `'ios'` یا `'android'` را برمی‌گرداند.
    *   `Platform.select()`:
    *
    *     **تمیزترین و توصیه شده‌ترین راه** برای تعریف استایل‌ها یا مقادیر متفاوت بر اساس پلتفرم است. این تابع یک آبجکت دریافت می‌کند که کلیدهای آن نام پلتفرم‌ها (مثلاً `ios`, `android`) و مقادیر آن‌ها استایل‌ها یا مقادیر مورد نظر هستند.
    *   **مثال (`Platform.select()`):**
        ```jsx
        import React from 'react';
        import { Platform, StyleSheet, Text, View } from 'react-native';

        export default function PlatformSpecificExample() {
          return (
            <View style={styles.container}>
              <Text style={styles.header}>
                شما در حال استفاده از {Platform.OS === 'ios' ? 'iOS' : 'Android'} هستید!
              </Text>
              <View style={styles.box}>
                <Text style={styles.text}>
                  این جعبه استایل مخصوص پلتفرم دارد.
                </Text>
              </View>
              <Text style={styles.platformConditionalText}>
                {Platform.OS === 'ios' ? 'این متن فقط در iOS نمایش داده می‌شود.' : 'این متن فقط در Android نمایش داده می‌شود.'}
              </Text>
            </View>
          );
        }

        const styles = StyleSheet.create({
          container: {
            flex: 1,
            justifyContent: 'center',
            alignItems: 'center',
            padding: 20,
            backgroundColor: '#f5f5f5',
          },
          header: {
            fontSize: 20,
            fontWeight: 'bold',
            marginBottom: 30,
            ...Platform.select({
              ios: {
                color: 'blue',
                fontFamily: 'Georgia',
              },
              android: {
                color: 'green',
                fontFamily: 'Roboto',
              },
            }),
          },
          box: {
            width: 200,
            height: 100,
            justifyContent: 'center',
            alignItems: 'center',
            borderRadius: 10,
            ...Platform.select({
              ios: {
                backgroundColor: '#e6e6fa', // Lavender
                borderWidth: 1,
                borderColor: 'purple',
                shadowColor: '#000',
                shadowOffset: { width: 0, height: 2 },
                shadowOpacity: 0.15,
                shadowRadius: 3,
              },
              android: {
                backgroundColor: '#fff0f5', // Lavender Blush
                borderWidth: 2,
                borderColor: 'pink',
                elevation: 5,
              },
            }),
            marginBottom: 20,
          },
          text: {
            fontSize: 16,
            fontWeight: 'bold',
            ...Platform.select({
              ios: { color: 'darkblue' },
              android: { color: 'darkgreen' },
            }),
          },
          platformConditionalText: {
            fontSize: 14,
            marginTop: 10,
            fontStyle: 'italic',
            color: '#666',
            textAlign: 'center',
          }
        });
        ```
        همانطور که در مثال بالا مشاهده می‌کنید، می‌توانیم از `Platform.select()` برای ادغام استایل‌های مخصوص پلتفرم در یک شیء استایل استفاده کنیم. همچنین می‌توانیم از `Platform.OS` به صورت شرطی برای تغییر مقادیر خاص استفاده کنیم.

2.  **پسوندهای فایل (File Extensions)**:
    *   برای تفاوت‌های بزرگتر در کامپوننت‌ها یا منطق، می‌توانید دو فایل جداگانه بسازید. برای مثال:
        *   `MyComponent.ios.js` (فقط برای iOS)
        *   `MyComponent.android.js` (فقط برای Android)
    *   باندلر **React Native (Metro)** به صورت هوشمند و خودکار فایل صحیح را بر اساس پلتفرم در حال اجرا انتخاب و بارگذاری می‌کند.
    *   این رویکرد به شما اجازه می‌دهد تا بخش‌های بزرگی از **UI** یا منطق را به طور کامل برای هر پلتفرم بهینه کنید. این روش برای جداسازی کامل کد مختص هر پلتفرم بسیار مفید است.

---

## فصل ۶: نمایش لیست‌های بهینه

نمایش لیست‌های داده یکی از رایج‌ترین و حیاتی‌ترین کارها در توسعه اپلیکیشن‌های موبایل است. در این فصل، با سه کامپوننت اصلی برای نمایش لیست‌ها آشنا می‌شویم و یاد می‌گیریم که چگونه لیست‌های بلند را به صورت بهینه رندر کنیم تا عملکرد اپلیکیشن شما روان باقی بماند.

### ۶-۱: `<ScrollView>`

کامپوننت `<ScrollView>` یک کانتینر اسکرول ساده است. هر چیزی که داخل آن قرار دهید، اگر از فضای موجود بزرگ‌تر باشد، قابل اسکرول خواهد شد.

*   **نقطه ضعف بزرگ**: ScrollView تمام کامپوننت‌های فرزند خود را **یکجا رندر می‌کند**.
    *   این بدان معناست که حتی اگر آیتمی خارج از صفحه باشد و کاربر آن را نبیند، باز هم در حافظه رندر شده و فضای زیادی را اشغال می‌کند.
    *   این ویژگی باعث می‌شود برای لیست‌های **بلند** (با تعداد زیادی آیتم)، مصرف حافظه بالا رفته و اپلیکیشن **کند** شود.
*   **کاربرد**: ScrollView برای صفحاتی با **تعداد محدودی آیتم** یا محتوای متنی بلند (مانند یک مقاله یا صفحه تنظیمات) که حجم داده زیادی ندارند، مناسب است.

**مثال کد**:
```jsx
import React from 'react';
import { ScrollView, Text, StyleSheet, View } from 'react-native';

export default function BasicScrollView() {
  const longContent = Array.from({ length: 50 }, (_, i) => `این آیتم شماره ${i + 1} است.`).join('\n');

  return (
    <ScrollView style={styles.scrollViewContainer}>
      <Text style={styles.headerText}>مقاله بلند</Text>
      <Text style={styles.contentParagraph}>
        لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است.
        چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز و کاربردهای متنوع با هدف بهبود ابزارهای کاربردی می‌باشد.
        کتابهای زیادی در شصت و سه درصد گذشته، حال و آینده شناخت فراوان جامعه و متخصصان را می‌طلبد تا با نرم‌افزارها برای طراحان رایانه ای و فرهنگ پیشرو در زبان فارسی ایجاد کرد.
      </Text>
      <Text style={styles.longContent}>{longContent}</Text>
      <View style={styles.footer}>
        <Text style={styles.footerText}>پایان مقاله</Text>
      </View>
    </ScrollView>
  );
}

const styles = StyleSheet.create({
  scrollViewContainer: {
    flex: 1,
    padding: 20,
    backgroundColor: '#fff',
  },
  headerText: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 15,
    textAlign: 'center',
    color: '#333',
  },
  contentParagraph: {
    fontSize: 16,
    lineHeight: 24,
    marginBottom: 20,
    color: '#555',
    textAlign: 'justify',
  },
  longContent: {
    fontSize: 14,
    color: '#777',
    lineHeight: 20,
  },
  footer: {
    marginTop: 30,
    paddingVertical: 15,
    backgroundColor: '#f0f0f0',
    borderRadius: 8,
    alignItems: 'center',
  },
  footerText: {
    fontSize: 14,
    color: '#888',
    fontStyle: 'italic',
  },
});
```

### ۶-۲: `<FlatList>` (انتخاب استاندارد)

کامپوننت `<FlatList>` اصلی‌ترین و **بهینه‌ترین** کامپوننت برای نمایش **لیست‌های بلند و پویا** از داده‌ها است.

*   **قابلیت کلیدی: مجازی‌سازی (Virtualization).**
    *   FlatList
    *
    *     به صورت هوشمند عمل می‌کند و **فقط آیتم‌هایی را رندر می‌کند که در حال حاضر روی صفحه قابل مشاهده هستند** (یا نزدیک به آن‌ها هستند).
    *   هنگامی که کاربر اسکرول می‌کند، آیتم‌های قدیمی از حافظه حذف شده و آیتم‌های جدید رندر می‌شوند.
    *   این کار عملکرد را فوق‌العاده بالا می‌برد و مصرف حافظه را بهینه می‌کند.
*   **پراپ‌های ضروری**:
    *   `data`:
    *
    *     **آرایه‌ای از داده‌ها** که قرار است در لیست نمایش داده شوند.
    *   `renderItem`:
    *
    *     یک **تابع** که یک آیتم از آرایه `data` را به عنوان ورودی (`{ item, index }`) دریافت کرده و **کامپوننت مربوط به آن آیتم** را برمی‌گرداند. این تابع مسئول نمایش هر ردیف در لیست است.
    *   `keyExtractor`:
    *
    *     یک **تابع** که یک **کلید (key) منحصر به فرد و از نوع رشته** برای هر آیتم در لیست برمی‌گرداند. **React** از این کلیدها برای شناسایی آیتم‌ها در طول تغییرات (اضافه شدن، حذف شدن، تغییر ترتیب) استفاده می‌کند و برای عملکرد و جلوگیری از باگ‌ها بسیار مهم است.

**مثال**:
```jsx
import React from 'react';
import { FlatList, Text, View, StyleSheet } from 'react-native';

const PRODUCTS = [
  { id: '1', name: 'لپ‌تاپ گیمینگ', price: '45,000,000 تومان' },
  { id: '2', name: 'گوشی هوشمند مدل X', price: '22,000,000 تومان' },
  { id: '3', name: 'هدفون بی‌سیم', price: '3,500,000 تومان' },
  { id: '4', name: 'کنسول بازی نسل جدید', price: '30,000,000 تومان' },
  { id: '5', name: 'مانیتور 4K', price: '12,000,000 تومان' },
  { id: '6', name: 'ماوس گیمینگ', price: '800,000 تومان' },
  { id: '7', name: 'کیبورد مکانیکی', price: '1,500,000 تومان' },
  { id: '8', name: 'هارد اکسترنال 2TB', price: '2,000,000 تومان' },
  { id: '9', name: 'پرینتر چندکاره', price: '7,000,000 تومان' },
  { id: '10', name: 'اسپیکر بلوتوث', price: '1,200,000 تومان' },
  { id: '11', name: 'ساعت هوشمند', price: '5,000,000 تومان' },
  { id: '12', name: 'تبلت آموزشی', price: '9,000,000 تومان' },
  { id: '13', name: 'مودم روتر وایرلس', price: '1,100,000 تومان' },
  { id: '14', name: 'کارت گرافیک RTX 4090', price: '90,000,000 تومان' },
  { id: '15', name: 'صندلی گیمینگ', price: '6,000,000 تومان' },
  { id: '16', name: 'هدست VR', price: '15,000,000 تومان' },
  { id: '17', name: 'هارد SSD 1TB', price: '3,000,000 تومان' },
  { id: '18', name: 'باتری پاوربانک', price: '700,000 تومان' },
  { id: '19', name: 'وب‌کم Full HD', price: '950,000 تومان' },
  { id: '20', name: 'لپ‌تاپ سبک‌وزن', price: '18,000,000 تومان' },
];

export default function ProductList() {
  const renderItem = ({ item }) => (
    <View style={styles.item}>
      <Text style={styles.productName}>{item.name}</Text>
      <Text style={styles.productPrice}>{item.price}</Text>
    </View>
  );

  return (
    <FlatList
      data={PRODUCTS}
      renderItem={renderItem}
      keyExtractor={item => item.id}
      contentContainerStyle={styles.listContainer}
      ListHeaderComponent={() => (
        <Text style={styles.listHeader}>لیست محصولات الکترونیکی</Text>
      )}
      ItemSeparatorComponent={() => <View style={styles.separator} />}
    />
  );
}

const styles = StyleSheet.create({
  listContainer: {
    paddingHorizontal: 16,
    paddingVertical: 10,
    backgroundColor: '#f5f5f5',
  },
  listHeader: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 15,
    textAlign: 'center',
    color: '#333',
  },
  item: {
    backgroundColor: 'white',
    padding: 20,
    marginVertical: 8,
    borderRadius: 10,
    flexDirection: 'row',
    justifyContent: 'space-between',
    alignItems: 'center',
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.1,
    shadowRadius: 3,
    elevation: 3,
  },
  productName: {
    fontSize: 17,
    fontWeight: 'bold',
    color: '#333',
  },
  productPrice: {
    fontSize: 16,
    color: '#28a745',
    fontWeight: '600',
  },
  separator: {
    height: 1,
    backgroundColor: '#eee',
    marginVertical: 4,
  }
});
```

### ۶-۳: `<SectionList>`

کامپوننت `<SectionList>` برای نمایش داده‌هایی است که به صورت **بخش‌بندی شده** یا گروه‌بندی شده هستند. مثال بارز آن، لیست مخاطبین است که بر اساس حروف الفبا (A, B, C و...) گروه‌بندی شده‌اند.

*   **پراپ‌های اصلی**:
    *   `sections`:
    *
    *   **آرایه‌ای از آبجکت‌ها** است. هر آبجکت در این آرایه نشان‌دهنده یک بخش است و شامل یک `title` (عنوان بخش) و یک آرایه `data` (آیتم‌های آن بخش) می‌باشد.
    *   
    *   `renderItem`:
    *
    *     برای رندر هر آیتم در یک بخش. مشابه FlatList عمل می‌کند.
    *   `renderSectionHeader`:
    *
    *     تابعی برای **رندر کردن هدر هر بخش** (مثلاً حرف 'A' برای بخش "آ"). این تابع یک آبجکت شامل `section` (که حاوی `title` آن بخش است) را دریافت می‌کند.

**مثال کد**:
```jsx
import React from 'react';
import { SectionList, Text, View, StyleSheet } from 'react-native';

const CONTACTS_DATA = [
  {
    title: 'A',
    data: [
      { id: 'a1', name: 'احمدی' },
      { id: 'a2', name: 'آریا' },
    ],
  },
  {
    title: 'ب',
    data: [
      { id: 'b1', name: 'بهرامی' },
      { id: 'b2', name: 'بهزاد' },
      { id: 'b3', name: 'بیانی' },
    ],
  },
  {
    title: 'س',
    data: [
      { id: 's1', name: 'سهرابی' },
      { id: 's2', name: 'سارا' },
    ],
  },
  {
    title: 'م',
    data: [
      { id: 'm1', name: 'محمدی' },
      { id: 'm2', name: 'مرادی' },
      { id: 'm3', name: 'مهتاب' },
      { id: 'm4', name: 'میلاد' },
    ],
  },
];

export default function ContactsSectionList() {
  return (
    <SectionList
      sections={CONTACTS_DATA}
      keyExtractor={(item, index) => item.id + index}
      renderItem={({ item }) => (
        <View style={styles.item}>
          <Text style={styles.itemText}>{item.name}</Text>
        </View>
      )}
      renderSectionHeader={({ section: { title } }) => (
        <View style={styles.header}>
          <Text style={styles.headerText}>{title}</Text>
        </View>
      )}
      contentContainerStyle={styles.listContainer}
    />
  );
}

const styles = StyleSheet.create({
  listContainer: {
    paddingHorizontal: 16,
    paddingVertical: 10,
    backgroundColor: '#f5f5f5',
  },
  header: {
    backgroundColor: '#e0e0e0',
    paddingVertical: 8,
    paddingHorizontal: 16,
    borderBottomWidth: 1,
    borderBottomColor: '#ccc',
    marginBottom: 5,
  },
  headerText: {
    fontSize: 20,
    fontWeight: 'bold',
    color: '#444',
  },
  item: {
    backgroundColor: 'white',
    padding: 15,
    marginVertical: 4,
    borderRadius: 8,
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 1 },
    shadowOpacity: 0.05,
    shadowRadius: 2,
    elevation: 2,
  },
  itemText: {
    fontSize: 16,
    color: '#333',
  },
});
```

---

## فصل ۷: هویت بصری: فونت و صفحه اسپلش

در این فصل، دو ابزار مهم برای کنترل هویت بصری و تجربه اولیه کاربری اپلیکیشن خود را یاد می‌گیریم. استفاده از فونت‌های سفارشی می‌تواند برند شما را تقویت کند، و مدیریت صفحه اسپلش تجربه کاربری را هنگام بارگذاری اولیه بهبود می‌بخشد.

### ۷-۱: کار با فونت‌های سفارشی (`useFonts`)

برای استفاده از فونت‌های اختصاصی (**Custom Fonts**) در پروژه **React Native** و **Expo**، از هوک `useFonts` که از کتابخانه `expo-font` می‌آید، استفاده می‌کنیم. این هوک به ما اجازه می‌دهد فونت‌ها را قبل از استفاده، به صورت **غیرهمزمان (asynchronously)** بارگذاری کنیم تا از پدیده "پرش متن" (**Flash Of Unstyled Text - FOUT**) جلوگیری شود.

*   **فرآیند استفاده**:
    1.  **نصب کتابخانه**: ابتدا کتابخانه `expo-font` را نصب کنید:
        ```bash
        npx expo install expo-font
        ```
    2.  **قرار دادن فایل‌های فونت**: فایل‌های فونت خود (`.ttf` یا `.otf`) را در یک پوشه مناسب داخل پروژه خود، معمولاً `assets/fonts/`، قرار دهید.
    3.  **بارگذاری فونت‌ها با `useFonts`**: در کامپوننت اصلی اپلیکیشن خود (معمولاً `App.js` یا `app/_layout.tsx` در پروژه‌های **Expo Router**)، هوک `useFonts` را فراخوانی کنید. این هوک یک آبجکت دریافت می‌کند که نام‌هایی که می‌خواهید برای فونت‌ها استفاده کنید را به مسیر فایل آن‌ها نگاشت می‌کند. این هوک یک آرایه دو عنصری برمی‌گرداند: یک مقدار بولی (`fontsLoaded`) که نشان می‌دهد آیا فونت‌ها بارگذاری شده‌اند یا خیر، و یک تابع `fontError`.
    4.  **توقف رندر تا بارگذاری کامل**: تا زمانی که فونت‌ها به طور کامل بارگذاری نشده‌اند (`fontsLoaded` برابر `false` است)، رندر اپلیکیشن را متوقف کنید. معمولاً با برگرداندن `null` یا یک صفحه بارگذاری ساده این کار انجام می‌شود.
    5.  **استفاده از فونت**: پس از بارگذاری موفق، می‌توانید نام تعریف شده برای فونت را در پراپ `fontFamily` در استایل‌های خود استفاده کنید.
*   **نکته مهم**: بارگذاری فونت به تنهایی آن را به کل برنامه اعمال **نمی‌کند**. شما باید به صراحت در استایل‌ها (مثلاً برای `<Text>`) از آن استفاده کنید.

**مثال (در `app/_layout.tsx` یا `App.js`)**:
```jsx
// app/_layout.tsx یا App.js
import { SplashScreen } from 'expo-router'; // اگر از Expo Router استفاده می‌کنید
import { useFonts } from 'expo-font';
import { useEffect, useCallback } from 'react';
import { View, Text, StyleSheet } from 'react-native'; // برای نمایش محتوا پس از بارگذاری

// از بسته شدن خودکار صفحه اسپلش جلوگیری کنید تا فونت‌ها بارگذاری شوند
SplashScreen.preventAutoHideAsync();

export default function RootLayout() {
  const [fontsLoaded, fontError] = useFonts({
    'Vazirmatn-Regular': require('./assets/fonts/Vazirmatn-Regular.ttf'),
    'Vazirmatn-Bold': require('./assets/fonts/Vazirmatn-Bold.ttf'),
    // فونت‌های دیگر خود را اینجا اضافه کنید
  });

  const onLayoutRootView = useCallback(async () => {
    if (fontsLoaded || fontError) {
      await SplashScreen.hideAsync(); // مخفی کردن صفحه اسپلش پس از بارگذاری فونت
    }
  }, [fontsLoaded, fontError]);

  if (!fontsLoaded && !fontError) {
    return null; // نمایش صفحه اسپلش تا بارگذاری فونت
  }

  // پس از بارگذاری فونت‌ها، محتوای اصلی اپلیکیشن را نمایش دهید
  return (
    <View style={{ flex: 1 }} onLayout={onLayoutRootView}>
      {/* اینجا می‌توانید کامپوننت‌های ناوبری اصلی خود را قرار دهید */}
      <View style={styles.container}>
        <Text style={styles.header}>به اپلیکیشن خوش آمدید!</Text>
        <Text style={styles.regularText}>
          این متن با فونت عادی (Vazirmatn-Regular) است.
        </Text>
        <Text style={styles.boldText}>
          این متن با فونت پررنگ (Vazirmatn-Bold) است.
        </Text>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f5f5f5',
  },
  header: {
    fontSize: 24,
    fontFamily: 'Vazirmatn-Bold', // استفاده از فونت سفارشی
    marginBottom: 20,
    color: '#333',
  },
  regularText: {
    fontSize: 16,
    fontFamily: 'Vazirmatn-Regular', // استفاده از فونت سفارشی
    marginVertical: 5,
    color: '#555',
  },
  boldText: {
    fontSize: 16,
    fontFamily: 'Vazirmatn-Bold', // استفاده از فونت سفارشی
    marginVertical: 5,
    color: '#555',
  },
});
```
*توجه: برای اجرای این مثال، باید فایل‌های فونت `Vazirmatn-Regular.ttf` و `Vazirmatn-Bold.ttf` را در پوشه `assets/fonts/` پروژه خود قرار دهید.*

### ۷-۲: مدیریت صفحه اسپلش (`expo-splash-screen`)

صفحه اسپلش (**Splash Screen**) اولین چیزی است که کاربر هنگام باز کردن اپلیکیشن شما می‌بیند. با استفاده از ماژول `expo-splash-screen`، می‌توانیم نمایش این صفحه را کنترل کنیم تا اطمینان حاصل شود که تمام فرآیندهای آماده‌سازی اولیه اپلیکیشن (مانند بارگذاری فونت‌ها یا دریافت تنظیمات اولیه از سرور) به پایان رسیده‌اند و سپس اپلیکیشن به نرمی نمایش داده شود.

*   **گردش کار**:
    1.  **نصب ماژول**:
        ```bash
        npx expo install expo-splash-screen
        ```
    2.  **جلوگیری از بسته شدن خودکار**: در ابتدای برنامه، معمولاً در فایل اصلی (مثلاً `App.js` یا `_layout.tsx`) با فراخوانی `SplashScreen.preventAutoHideAsync()` از بسته شدن خودکار صفحه اسپلش قبل از آماده شدن کامل اپلیکیشن جلوگیری می‌کنیم.
    3.  **پنهان کردن صفحه اسپلش**: پس از اینکه تمام کارهای لازم (مانند بارگذاری فونت‌ها، دریافت داده‌های اولیه) انجام شد و اپلیکیشن آماده نمایش است، تابع `SplashScreen.hideAsync()` را فراخوانی می‌کنیم. این باعث می‌شود صفحه اسپلش به نرمی محو شده و محتوای اصلی اپلیکیشن نمایش داده شود. این کار معمولاً در یک `useEffect` یا با استفاده از `onLayout` کامپوننت ریشه انجام می‌شود.
*   **مثال**:
    *   لطفاً به مثال کد ارائه شده در بخش **۷-۱: کار با فونت‌های سفارشی (`useFonts`)** مراجعه کنید، چرا که شامل پیاده‌سازی همزمان `SplashScreen.preventAutoHideAsync()` و `SplashScreen.hideAsync()` است.

---

## فصل ۸: ناوبری مدرن با Expo Router و هوک‌های کاربردی

ناوبری (**Navigation**) ستون فقرات هر اپلیکیشن موبایل است که به کاربر امکان می‌دهد بین صفحات مختلف جابجا شود. در این فصل، با **Expo Router** آشنا می‌شویم، یک رویکرد نوین برای مدیریت ناوبری در **React Native** که بر پایه **مسیریابی مبتنی بر فایل** عمل می‌کند و تجربه توسعه را به شدت ساده‌تر می‌سازد.

**Expo Router**

یک لایه هوشمند روی کتابخانه قدرتمند **React Navigation** است. این به ما اجازه می‌دهد ناوبری را به صورت فایل‌محور و شبیه به **Next.js** انجام دهیم. این رویکرد کدنویسی ناوبری را بسیار تمیزتر و قابل پیش‌بینی‌تر می‌کند.

### ۸-۱: مفاهیم کلیدی Expo Router

*   **مسیریابی مبتنی بر فایل**:
    *   اساسی‌ترین مفهوم در **Expo Router** این است که **هر فایل در پوشه `app/` به صورت خودکار به یک مسیر (Route) در اپلیکیشن تبدیل می‌شود**.
    *   برای مثال، فایل `app/settings.tsx` به مسیر `/settings` در اپلیکیشن شما تبدیل می‌شود.
    *   `app/index.tsx` به مسیر اصلی `/` تبدیل می‌شود.
    *   پوشه‌ها نیز مسیرهای تو در تو (**Nested Routes**) ایجاد می‌کنند: `app/users/profile.tsx` به `/users/profile` تبدیل می‌شود.
*   **چیدمان‌ها (`_layout.tsx`)**:
    *   این فایل یک مفهوم بسیار قدرتمند است. فایل `_layout.tsx` در یک پوشه، **نوع ناوبر (Navigator)** را برای آن پوشه و **تمام زیرشاخه‌هایش** مشخص می‌کند.
    *   `app/_layout.tsx`:
    *
    *     این فایل، **ناوبر اصلی کل برنامه** را تعریف می‌کند. معمولاً اینجا یک `Stack Navigator` (ناوبر پشته‌ای) یا `Tab Navigator` (ناوبر تب‌دار) تعریف می‌شود.
    *   شما می‌توانید چندین فایل `_layout.tsx` در زیرپوشه‌ها داشته باشید تا بخش‌های مختلف اپلیکیشن، ناوبری خاص خود را داشته باشند.
*   **گروه‌بندی مسیرها (Route Groups)**:
    *   پوشه‌هایی که نامشان داخل **پرانتز** است (مانند `(tabs)`)، در **URL** نهایی تأثیری ندارند.
    *   این پوشه‌ها فقط برای **سازماندهی کد** و **اعمال یک چیدمان (layout) خاص** به گروهی از صفحات استفاده می‌شوند.
    *   مثال: اگر `app/(tabs)/home.tsx` داشته باشید، مسیر آن همچنان `/home` خواهد بود، اما می‌توانید یک `app/(tabs)/_layout.tsx` برای تعریف یک Tab Navigator برای تمام صفحات داخل `(tabs)` داشته باشید.

### ۸-۲: ابزارهای ناوبری: کامپوننت `<Link>`

کامپوننت **Link** اصلی‌ترین ابزار شما برای **ناوبری اعلانی (Declarative Navigation)** در **React Native** است. این کامپوننت به شما اجازه می‌دهد تا با کلیک کاربر، او را به یک صفحه دیگر منتقل کنید.

*   `href`:
*
*     این پراپ مسیر مقصد را مشخص می‌کند. می‌توانید یک رشته ساده (مانند `href="/settings"`) یا یک آبجکت پیچیده‌تر برای ارسال پارامترها (مانند `href={{ pathname: '/user/123', params: { ... } }}`) به آن بدهید.
*   `replace`:
*
*     این پراپ یک مقدار boolean می‌پذیرد. اگر `true` باشد، صفحه فعلی را از **تاریخچه ناوبری (Navigation Stack)** حذف می‌کند و صفحه جدید را جایگزین آن می‌کند. کاربر دیگر نمی‌تواند با دکمه بازگشت به صفحه قبلی بازگردد. این برای سناریوهایی مانند **بعد از ورود کاربر (Login)** که نمی‌خواهید کاربر بتواند به صفحه ورود برگردد، بسیار مفید است.
*   `asChild`:
*
*     این پراپ (که **بسیار مهم** است) به **Link** می‌گوید که خودش هیچ **UI** ای را رندر نکند و **فقط قابلیت ناوبری را به اولین فرزند خود منتقل کند**. این به شما اجازه می‌دهد تا دکمه‌های کاملاً سفارشی، آیکون‌ها یا هر کامپوننت دیگری را بسازید که مانند یک لینک عمل می‌کنند.

**مثال‌ها**:
```jsx
// در یک کامپوننت دیگر، مثلاً app/index.tsx
import { Link } from 'expo-router';
import { View, Text, StyleSheet } from 'react-native';

export default function HomeScreen() {
  return (
    <View style={styles.container}>
      <Text style={styles.header}>ناوبری با Link</Text>

      {/* لینک ساده */}
      <Link href="/settings" style={styles.link}>
        برو به تنظیمات
      </Link>

      {/* لینک با جایگزینی در تاریخچه (مثلاً بعد از لاگین) */}
      <Link href="/dashboard" replace style={styles.link}>
        برو به داشبورد (با جایگزینی)
      </Link>

      {/* لینک با ارسال پارامتر */}
      <Link href={{ pathname: '/user/[id]', params: { id: '123' } }} style={styles.link}>
        پروفایل کاربر 123
      </Link>

      {/* استفاده از asChild برای دکمه سفارشی */}
      <Link href="/profile" asChild>
        <Pressable style={styles.customButton}>
          <Text style={styles.customButtonText}>مشاهده پروفایل</Text>
        </Pressable>
      </Link>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    gap: 15,
  },
  header: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
    color: '#333',
  },
  link: {
    fontSize: 18,
    color: 'blue',
    textDecorationLine: 'underline',
    paddingVertical: 8,
  },
  customButton: {
    backgroundColor: '#28a745',
    paddingVertical: 12,
    paddingHorizontal: 25,
    borderRadius: 8,
    marginTop: 20,
  },
  customButtonText: {
    color: 'white',
    fontSize: 16,
    fontWeight: 'bold',
  },
});
```
*برای اجرای این مثال، فرض بر این است که فایل‌های `app/settings.tsx`, `app/dashboard.tsx`, `app/user/[id].tsx` و `app/profile.tsx` در پروژه شما وجود دارند.*

### ۸-۳: هوک‌های ناوبری دستوری (`useRouter`, `useLocalSearchParams`, `usePathname`)

علاوه بر ناوبری اعلانی با **Link**, **Expo Router** هوک‌هایی را برای **ناوبری دستوری (Programmatic Navigation)** از داخل کد فراهم می‌کند. این هوک‌ها برای سناریوهایی که ناوبری بعد از یک عملیات (مانند ارسال فرم یا پاسخ **API**) اتفاق می‌افتد، بسیار مفید هستند.

1.  **هوک `useRouter`**:
    *   این هوک، ابزار اصلی شما برای جابجایی بین صفحات به صورت برنامه‌نویسی است.
    *   `router.push('/path')`:

 یک صفحه جدید را روی پشته (**stack**) قرار می‌دهد. کاربر می‌تواند با دکمه بازگشت به صفحه قبلی بازگردد.
    *   `router.replace('/path')`:

 صفحه فعلی را با یک صفحه جدید **جایگزین** می‌کند. کاربر نمی‌تواند به صفحه قبلی بازگردد. این هوک برای سناریوهایی مانند بعد از لاگین کردن کاربر بسیار مفید است.
    *   `router.back()`:

 به صفحه قبلی در پشته ناوبری بازمی‌گردد.

**مثال کد برای `useRouter`**:
```jsx
// app/auth/login.tsx
import React from 'react';
import { View, Text, Button, StyleSheet, TextInput } from 'react-native';
import { useRouter } from 'expo-router';

export default function LoginScreen() {
  const router = useRouter();
  const [username, setUsername] = React.useState('');
  const [password, setPassword] = React.useState('');

  const handleLogin = () => {
    // منطق احراز هویت اینجا قرار می‌گیرد
    if (username === 'user' && password === 'pass') {
      alert('ورود موفقیت‌آمیز!');
      // پس از ورود موفق، کاربر را به داشبورد هدایت کنید و صفحه لاگین را از تاریخچه حذف کنید
      router.replace('/dashboard');
    } else {
      alert('نام کاربری یا رمز عبور اشتباه است.');
    }
  };

  return (
    <View style={styles.container}>
      <Text style={styles.title}>ورود</Text>
      <TextInput
        style={styles.input}
        placeholder="نام کاربری"
        value={username}
        onChangeText={setUsername}
        autoCapitalize="none"
      />
      <TextInput
        style={styles.input}
        placeholder="رمز عبور"
        value={password}
        onChangeText={setPassword}
        secureTextEntry
      />
      <Button title="ورود" onPress={handleLogin} />
      <Button title="بازگشت به خانه" onPress={() => router.push('/')} color="gray" />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    backgroundColor: '#fff',
    gap: 15,
  },
  title: {
    fontSize: 28,
    fontWeight: 'bold',
    marginBottom: 30,
    color: '#333',
  },
  input: {
    width: '90%',
    height: 50,
    borderColor: '#ddd',
    borderWidth: 1,
    borderRadius: 10,
    paddingHorizontal: 15,
    fontSize: 16,
    backgroundColor: '#f9f9f9',
  },
});
```
*برای این مثال، نیاز به یک فایل `app/dashboard.tsx` و `app/index.tsx` دارید.*

2.  **هوک `useLocalSearchParams`**:
    *   این هوک برای **خواندن پارامترهای داینامیک** از **URL صفحه فعلی** استفاده می‌شود.
    *   **کاربرد**: اگر شما یک مسیر داینامیک مانند `app/user/[id].tsx` (که `[id]` یک پارامتر است) داشته باشید و کاربر به آدرس `/user/123` برود، هوک `useLocalSearchParams` یک آبجکت به شکل `{ id: '123' }` را برمی‌گرداند. این به شما اجازه می‌دهد تا داده‌های مربوط به آن `id` را از سرور دریافت و نمایش دهید.
    *   **مثال (در فایل `app/user/[id].tsx`)**:
        ```jsx
        // app/user/[id].tsx
        import { useLocalSearchParams } from 'expo-router';
        import { Text, View, StyleSheet } from 'react-native';

        export default function UserProfile() {
          // به تایپ‌اسکریپت می‌گوییم که انتظار یک آبجکت با کلید `id` از نوع `string` را داریم
          const { id } = useLocalSearchParams<{ id: string }>();

          return (
            <View style={styles.container}>
              <Text style={styles.header}>پروفایل کاربر</Text>
              <Text style={styles.userIdText}>شناسه کاربر: {id}</Text>
              <Text style={styles.infoText}>
                {`در اینجا می‌توانید اطلاعات کاربر با شناسه ${id} را از یک API دریافت و نمایش دهید.`}
              </Text>
            </View>
          );
        }

        const styles = StyleSheet.create({
          container: {
            flex: 1,
            justifyContent: 'center',
            alignItems: 'center',
            padding: 20,
            backgroundColor: '#f8f8f8',
          },
          header: {
            fontSize: 24,
            fontWeight: 'bold',
            marginBottom: 20,
            color: '#333',
          },
          userIdText: {
            fontSize: 20,
            color: '#007bff',
            marginBottom: 10,
          },
          infoText: {
            fontSize: 16,
            textAlign: 'center',
            color: '#555',
            marginTop: 10,
          }
        });
        ```

3.  **هوک `usePathname`**:
    *   این یک هوک ساده است که **آدرس مسیر فعلی** را به صورت یک رشته برمی‌گرداند (مثلاً `/user/123`).
    *   **کاربرد**: برای هایلایت کردن لینک فعال در یک منوی ناوبری سفارشی یا برای ارسال آدرس فعلی صفحه به سرویس‌های آنالیتیکس (**Analytics**) مفید است.

**مثال کد برای `usePathname`**:
```jsx
// app/any-path.tsx (می‌تواند هر فایلی در پوشه app/ باشد)
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';
import { usePathname } from 'expo-router';

export default function CurrentPathScreen() {
  const pathname = usePathname();

  return (
    <View style={styles.container}>
      <Text style={styles.title}>مسیر فعلی:</Text>
      <Text style={styles.pathText}>{pathname}</Text>
      <Text style={styles.description}>
        این هوک به شما کمک می‌کند تا آدرس صفحه فعلی را در هر کجای اپلیکیشن خود بدست آورید.
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    backgroundColor: '#eef',
  },
  title: {
    fontSize: 22,
    fontWeight: 'bold',
    marginBottom: 10,
    color: '#333',
  },
  pathText: {
    fontSize: 20,
    color: '#8a2be2', // BlueViolet
    backgroundColor: '#fff',
    paddingHorizontal: 15,
    paddingVertical: 8,
    borderRadius: 8,
    marginBottom: 20,
    fontWeight: '600',
  },
  description: {
    fontSize: 15,
    textAlign: 'center',
    color: '#555',
    lineHeight: 22,
  }
});
```

---

## فصل ۹: ارتباط با دنیای خارج: شبکه (Networking)

تقریباً تمام اپلیکیشن‌های مدرن موبایل نیاز به ارتباط با دنیای خارج دارند؛ یعنی برای دریافت و ارسال داده به سرورها از طریق اینترنت با **API** ها تعامل می‌کنند. در این فصل، با روش‌های مختلف برقراری ارتباط شبکه در **React Native** آشنا می‌شویم.

### ۹-۱: `Fetch API`

**React Native**:

به صورت داخلی از **Fetch API** پشتیبانی می‌کند. این یک استاندارد مدرن وب برای ارسال درخواست‌های شبکه (مانند GET, POST, PUT, DELETE) است. **Fetch API** مبتنی بر **Promise** است و به خوبی با ساختار `async/await` در جاوااسکریپت کار می‌کند، که کد را خواناتر و مدیریت خطا را آسان‌تر می‌کند.

**مثال ساده `Fetch`**:
```jsx
import React from 'react';
import { Button, Text, View, StyleSheet } from 'react-native';

export default function FetchExample() {
  const fetchData = async () => {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
      const json = await response.json();
      alert(`عنوان: ${json.title}\nکامل شده: ${json.completed ? 'بله' : 'خیر'}`);
    } catch (error) {
      console.error('خطا در دریافت داده:', error);
      alert('خطا در دریافت اطلاعات. لطفاً دوباره تلاش کنید.');
    }
  };

  return (
    <View style={styles.container}>
      <Text style={styles.title}>دریافت اطلاعات از API</Text>
      <Button title="دریافت TODO" onPress={fetchData} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
  },
  title: {
    fontSize: 20,
    fontWeight: 'bold',
    marginBottom: 30,
    color: '#333',
  },
});
```

### ۹-۲: گردش کار دریافت داده (الگوی کلاسیک)

این الگو از هوک‌های `useEffect` و `useState` برای مدیریت چرخه حیات داده در کامپوننت‌های تابعی استفاده می‌کند. این روش رایج‌ترین الگوی دریافت داده قبل از **React 19** بود و هنوز هم در بسیاری از پروژه‌ها استفاده می‌شود.

**مراحل اصلی**:
1.  **تعریف State ها**: سه **state** مجزا برای نگهداری وضعیت‌های مختلف تعریف می‌کنیم:
    *   `data`: برای ذخیره داده‌های دریافتی موفقیت‌آمیز.
    *   `isLoading`: یک مقدار boolean برای نمایش وضعیت بارگذاری (مثلاً نمایش یک Spinner).
    *   `error`: برای ذخیره هرگونه خطای احتمالی در حین فرایند دریافت داده.
2.  **ارسال درخواست در `useEffect`**: درخواست fetch را داخل یک هوک `useEffect` قرار می‌دهیم. برای اطمینان از اینکه درخواست **فقط یک بار** هنگام باز شدن صفحه (یا mount شدن کامپوننت) اجرا شود، آرایه وابستگی (**Dependency Array**) هوک `useEffect` را **خالی (`[]`)** قرار می‌دهیم.
3.  **مدیریت پاسخ (`Try...Catch...Finally`)**: از یک بلاک `try...catch...finally` برای مدیریت نتایج درخواست استفاده می‌کنیم:
    *   در بلاک `try`: داده‌های دریافتی را به فرمت **JSON** تبدیل کرده و آن‌ها را در **state** مربوط به `data` قرار می‌دهیم.
    *   در بلاک `catch`: هر خطایی که در طول درخواست یا پردازش رخ دهد را دریافت کرده و آن را در **state** مربوط به `error` ذخیره می‌کنیم.
    *   در بلاک `finally`: وضعیت `isLoading` را به `false` تغییر می‌دهیم تا نشان دهیم که عملیات بارگذاری به پایان رسیده است، چه با موفقیت و چه با خطا.
4.  **رندر شرطی**: در رابط کاربری (**UI**)، بر اساس مقادیر `isLoading` و `error`، یک نمایشگر لودینگ، پیام خطا یا لیست داده‌های دریافتی را به کاربر نمایش می‌دهیم.

**مثال**:
```jsx
import React, { useState, useEffect } from 'react';
import { View, Text, ActivityIndicator, StyleSheet, FlatList } from 'react-native';

export default function ClassicDataFetch() {
  const [data, setData] = useState([]);
  const [isLoading, setIsLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/posts?_limit=5');
        if (!response.ok) {
          throw new Error(`خطای HTTP! وضعیت: ${response.status}`);
        }
        const json = await response.json();
        setData(json);
      } catch (err) {
        setError(err);
        console.error('خطا در دریافت پست‌ها:', err);
      } finally {
        setIsLoading(false);
      }
    };

    fetchPosts();
  }, []); // آرایه وابستگی خالی: فقط یک بار هنگام mount شدن اجرا شود

  if (isLoading) {
    return (
      <View style={styles.centered}>
        <ActivityIndicator size="large" color="#0000ff" />
        <Text style={styles.loadingText}>در حال بارگذاری داده‌ها...</Text>
      </View>
    );
  }

  if (error) {
    return (
      <View style={styles.centered}>
        <Text style={styles.errorText}>خطا: {error.message}</Text>
        <Text style={styles.errorDetail}>لطفاً اتصال اینترنت خود را بررسی کنید.</Text>
      </View>
    );
  }

  return (
    <View style={styles.container}>
      <Text style={styles.listHeader}>آخرین پست‌ها</Text>
      <FlatList
        data={data}
        keyExtractor={item => item.id.toString()}
        renderItem={({ item }) => (
          <View style={styles.postItem}>
            <Text style={styles.postTitle}>{item.title}</Text>
            <Text style={styles.postBody}>{item.body}</Text>
          </View>
        )}
      />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    paddingTop: 40,
    backgroundColor: '#f5f5f5',
  },
  centered: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f5f5f5',
  },
  loadingText: {
    marginTop: 10,
    fontSize: 16,
    color: '#555',
  },
  errorText: {
    fontSize: 18,
    color: 'red',
    marginBottom: 5,
    fontWeight: 'bold',
  },
  errorDetail: {
    fontSize: 14,
    color: '#777',
    textAlign: 'center',
  },
  listHeader: {
    fontSize: 22,
    fontWeight: 'bold',
    textAlign: 'center',
    marginBottom: 20,
    color: '#333',
  },
  postItem: {
    backgroundColor: 'white',
    padding: 15,
    marginHorizontal: 16,
    marginVertical: 8,
    borderRadius: 10,
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.1,
    shadowRadius: 4,
    elevation: 3,
  },
  postTitle: {
    fontSize: 18,
    fontWeight: 'bold',
    marginBottom: 5,
    color: '#333',
  },
  postBody: {
    fontSize: 14,
    color: '#666',
    lineHeight: 20,
  },
});
```

### ۹-۳: گردش کار مدرن با React 19 (`use` و `Suspense`)

با پشتیبانی **Expo** از **React 19** (یا نسخه‌های بالاتر که این ویژگی‌ها را دارند)، می‌توانیم فرآیند دریافت داده را بسیار ساده‌تر و بهینه‌تر کنیم. این رویکرد جدید از هوک `use` و کامپوننت `Suspense` بهره می‌برد. این الگو نیاز به مدیریت **state** های لودینگ و خطا را در هر کامپوننت از بین می‌برد.

*   **هوک `use`**:
    *   این هوک انقلابی به ما اجازه می‌دهد تا **نتیجه یک Promise را مستقیماً "باز" (unwrap) کنیم**.
    *   دیگر نیازی به `useEffect` و `useState` برای مدیریت چرخه حیات درخواست نیست.
    *   این هوک فقط در کامپوننت‌های سمت سرور (**Server Components**) یا کامپوننت‌هایی که با Suspense پیچیده شده‌اند قابل استفاده است.
*   **`Suspense`**:
    *   این کامپوننت به ما اجازه می‌دهد تا یک **UI جایگزین (fallback)** (مانند `ActivityIndicator` یا یک **skeleton UI**) را نمایش دهیم.
    *   این **fallback UI** تا زمانی که داده‌های کامپوننت فرزند آماده شوند، به کاربر نمایش داده می‌شود.
    *   این یک راه بسیار تمیز برای مدیریت وضعیت‌های لودینگ در سطح کامپوننت است.
    *   این جداسازی منطق بارگذاری از منطق نمایش داده‌ها، کد را خواناتر و ماژولارتر می‌کند.

**مثال**:
```jsx
import React, { Suspense } from 'react';
import { View, Text, ActivityIndicator, StyleSheet } from 'react-native';

// تابع شبیه‌سازی دریافت داده از API
async function fetchSomeData() {
  return new Promise(resolve => setTimeout(() => {
    resolve({ message: 'داده‌ها با موفقیت دریافت شدند!' });
  }, 2000)); // شبیه‌سازی تاخیر 2 ثانیه‌ای
}

// کامپوننت فرزند که از هوک use برای خواندن Promise استفاده می‌کند
function MyDataComponent() {
  const data = React.use(fetchSomeData()); // استفاده از هوک use

  return (
    <View style={styles.dataContainer}>
      <Text style={styles.dataText}>{data.message}</Text>
    </View>
  );
}

// کامپوننت والد که از Suspense استفاده می‌کند
export default function ModernDataFetch() {
  return (
    <View style={styles.container}>
      <Text style={styles.header}>گردش کار مدرن با Suspense و use</Text>
      <Suspense fallback={<LoadingState />}>
        {/* MyDataComponent تا زمانی که fetchSomeData کامل شود، بارگذاری نمی‌شود */}
        <MyDataComponent />
      </Suspense>
      <Text style={styles.footerText}>
        این متن بدون انتظار برای بارگذاری داده‌ها رندر می‌شود.
      </Text>
    </View>
  );
}

// کامپوننت fallback برای Suspense
function LoadingState() {
  return (
    <View style={styles.loadingContainer}>
      <ActivityIndicator size="large" color="#0000ff" />
      <Text style={styles.loadingText}>در حال آماده‌سازی محتوا...</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f8f8f8',
    padding: 20,
  },
  header: {
    fontSize: 22,
    fontWeight: 'bold',
    marginBottom: 40,
    color: '#333',
    textAlign: 'center',
  },
  loadingContainer: {
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    minHeight: 100,
  },
  loadingText: {
    marginTop: 10,
    fontSize: 16,
    color: '#555',
  },
  dataContainer: {
    backgroundColor: '#e6ffe6',
    padding: 25,
    borderRadius: 15,
    borderWidth: 1,
    borderColor: '#aaffaa',
    alignItems: 'center',
    minHeight: 100,
    justifyContent: 'center',
  },
  dataText: {
    fontSize: 18,
    fontWeight: '600',
    color: '#28a745',
    textAlign: 'center',
  },
  footerText: {
    marginTop: 50,
    fontSize: 14,
    color: '#777',
    textAlign: 'center',
  },
});
```
**توضیح**: در این رویکرد، `ParentComponent` با استفاده از `<Suspense>`، یک **UI** جایگزین (لودینگ اسپینر) را نمایش می‌دهد تا `MyDataComponent` داده‌های خود را با `use(fetchMyData())` دریافت کند. وقتی داده‌ها آماده شدند، `<Suspense>` به طور خودکار `MyDataComponent` را رندر می‌کند. این امر کد را به شدت تمیزتر می‌کند و منطق بارگذاری را از منطق نمایش جدا می‌سازد. برای مدیریت خطاها در این سناریو، باید از **Error Boundaries** استفاده کنید (خارج از محدوده این منبع).

---

## فصل ۱۰: حافظه پایدار: ذخیره‌سازی داده‌ها

اغلب نیاز داریم اطلاعات را روی دستگاه کاربر ذخیره کنیم تا با بسته و باز شدن اپلیکیشن، این اطلاعات از بین نروند. این فصل شما را با ابزارهای اصلی برای ذخیره‌سازی داده‌ها در **React Native**، از اطلاعات ساده تا داده‌های حساس و پیچیده، آشنا می‌کند.

### ۱۰-۱: `AsyncStorage` – انبار ساده کلید-مقدار

**AsyncStorage**:

استاندارد اصلی برای ذخیره داده‌های **ساده و غیرحساس** در **React Native** است. عملکردی شبیه به `localStorage` در وب دارد، اما به صورت ناهمزمان (**Asynchronous**) عمل می‌کند.

*   **ساختار**: داده‌ها به صورت **کلید-مقدار (Key-Value)** ذخیره می‌شوند. هم کلید و هم مقدار باید به صورت **رشته (string)** باشند.
*   **برای ذخیره آبجکت‌ها**: باید ابتدا آن‌ها را با `JSON.stringify()` به رشته تبدیل کنید و هنگام بازیابی با `JSON.parse()` به آبجکت اصلی برگردانید.
*   **کاربرد**: ذخیره تنظیمات کاربر (مانند تم برنامه، زبان)، نام کاربری، یا وضعیت‌های کوچک.
*   **نصب**: `npx expo install @react-native-async-storage/async-storage`

**مثال**:
```jsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button, TextInput, StyleSheet, ActivityIndicator } from 'react-native';
import AsyncStorage from '@react-native-async-storage/async-storage';

export default function AsyncStorageExample() {
  const [username, setUsername] = useState('');
  const [savedUsername, setSavedUsername] = useState('');
  const [isLoading, setIsLoading] = useState(true);

  useEffect(() => {
    loadUsername();
  }, []);

  const saveUsername = async () => {
    try {
      await AsyncStorage.setItem('@my_app_username', username);
      setSavedUsername(username);
      alert('نام کاربری ذخیره شد!');
    } catch (e) {
      console.error('خطا در ذخیره نام کاربری:', e);
      alert('خطا در ذخیره داده.');
    }
  };

  const loadUsername = async () => {
    try {
      const value = await AsyncStorage.getItem('@my_app_username');
      if (value !== null) {
        setSavedUsername(value);
        setUsername(value); // برای نمایش در TextInput
      }
    } catch (e) {
      console.error('خطا در بارگذاری نام کاربری:', e);
    } finally {
      setIsLoading(false);
    }
  };

  const clearUsername = async () => {
    try {
      await AsyncStorage.removeItem('@my_app_username');
      setSavedUsername('');
      setUsername('');
      alert('نام کاربری حذف شد!');
    } catch (e) {
      console.error('خطا در حذف نام کاربری:', e);
      alert('خطا در حذف داده.');
    }
  };

  if (isLoading) {
    return (
      <View style={styles.centered}>
        <ActivityIndicator size="large" color="#0000ff" />
        <Text>در حال بارگذاری...</Text>
      </View>
    );
  }

  return (
    <View style={styles.container}>
      <Text style={styles.header}>ذخیره‌سازی با AsyncStorage</Text>
      <TextInput
        style={styles.input}
        placeholder="نام کاربری خود را وارد کنید"
        value={username}
        onChangeText={setUsername}
      />
      <View style={styles.buttonContainer}>
        <Button title="ذخیره نام کاربری" onPress={saveUsername} />
        <Button title="حذف نام کاربری" onPress={clearUsername} color="red" />
      </View>
      {savedUsername ? (
        <Text style={styles.savedText}>نام کاربری ذخیره شده: {savedUsername}</Text>
      ) : (
        <Text style={styles.savedText}>نام کاربری ذخیره شده‌ای ندارید.</Text>
      )}
    </View>
  );
}

const styles = StyleSheet.create({
  centered: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  container: {
    flex: 1,
    padding: 20,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f5f5f5',
  },
  header: {
    fontSize: 22,
    fontWeight: 'bold',
    marginBottom: 30,
    color: '#333',
  },
  input: {
    width: '90%',
    height: 50,
    borderColor: '#ddd',
    borderWidth: 1,
    borderRadius: 8,
    paddingHorizontal: 15,
    marginBottom: 20,
    backgroundColor: 'white',
    fontSize: 16,
  },
  buttonContainer: {
    flexDirection: 'row',
    justifyContent: 'space-around',
    width: '90%',
    marginBottom: 20,
    gap: 10,
  },
  savedText: {
    fontSize: 16,
    color: '#555',
    marginTop: 10,
  },
});
```

### ۱۰-۲: `SecureStore` – گاوصندوق اطلاعات حساس

برای ذخیره اطلاعات **حساس** که نباید به راحتی قابل خواندن باشند (حتی با دسترسی مستقیم به فایل‌های دستگاه)، از ماژول `expo-secure-store` استفاده می‌کنیم.

*   **امنیت**: این ماژول از قابلیت‌های امنیتی خود سیستم‌عامل (**Keychain** در iOS و **Keystore** در Android) برای **رمزنگاری داده‌ها** استفاده می‌کند. این به این معنی است که داده‌ها به صورت امن در محل مخصوص سیستم‌عامل ذخیره می‌شوند و دسترسی به آن‌ها بدون احراز هویت مناسب بسیار دشوار است.
*   **کاربرد**: ذخیره توکن‌های احراز هویت (**JWT**), کلیدهای **API** خصوصی، و رمزهای عبور.
*   **نصب**: `npx expo install expo-secure-store`

**مثال**:
```jsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button, TextInput, StyleSheet, ActivityIndicator } from 'react-native';
import * as SecureStore from 'expo-secure-store';

export default function SecureStoreExample() {
  const [token, setToken] = useState('');
  const [savedToken, setSavedToken] = useState('');
  const [isLoading, setIsLoading] = useState(true);

  useEffect(() => {
    loadToken();
  }, []);

  const saveToken = async () => {
    try {
      await SecureStore.setItemAsync('my-auth-token', token);
      setSavedToken(token);
      alert('توکن با موفقیت ذخیره شد!');
    } catch (e) {
      console.error('خطا در ذخیره توکن:', e);
      alert('خطا در ذخیره توکن امن.');
    }
  };

  const loadToken = async () => {
    try {
      const value = await SecureStore.getItemAsync('my-auth-token');
      if (value !== null) {
        setSavedToken(value);
        setToken(value); // برای نمایش در TextInput
      }
    } catch (e) {
      console.error('خطا در بارگذاری توکن:', e);
    } finally {
      setIsLoading(false);
    }
  };

  const deleteToken = async () => {
    try {
      await SecureStore.deleteItemAsync('my-auth-token');
      setSavedToken('');
      setToken('');
      alert('توکن حذف شد!');
    } catch (e) {
      console.error('خطا در حذف توکن:', e);
      alert('خطا در حذف توکن امن.');
    }
  };

  if (isLoading) {
    return (
      <View style={styles.centered}>
        <ActivityIndicator size="large" color="#0000ff" />
        <Text>در حال بارگذاری امن...</Text>
      </View>
    );
  }

  return (
    <View style={styles.container}>
      <Text style={styles.header}>ذخیره‌سازی امن با SecureStore</Text>
      <TextInput
        style={styles.input}
        placeholder="توکن محرمانه را وارد کنید"
        value={token}
        onChangeText={setToken}
        secureTextEntry // برای جلوگیری از نمایش متن
      />
      <View style={styles.buttonContainer}>
        <Button title="ذخیره توکن" onPress={saveToken} />
        <Button title="حذف توکن" onPress={deleteToken} color="red" />
      </View>
      {savedToken ? (
        <Text style={styles.savedText}>توکن ذخیره شده (نمایش ستاره): {savedToken.replace(/./g, '*')}</Text>
      ) : (
        <Text style={styles.savedText}>توکن ذخیره شده‌ای ندارید.</Text>
      )}
      <Text style={styles.warningText}>
        **توجه:** توکن واقعی در محیط امن ذخیره می‌شود و نباید به راحتی نمایش داده شود.
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  centered: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  container: {
    flex: 1,
    padding: 20,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f0f8ff', // LightCyan
  },
  header: {
    fontSize: 22,
    fontWeight: 'bold',
    marginBottom: 30,
    color: '#333',
  },
  input: {
    width: '90%',
    height: 50,
    borderColor: '#aaddff',
    borderWidth: 1,
    borderRadius: 8,
    paddingHorizontal: 15,
    marginBottom: 20,
    backgroundColor: 'white',
    fontSize: 16,
  },
  buttonContainer: {
    flexDirection: 'row',
    justifyContent: 'space-around',
    width: '90%',
    marginBottom: 20,
    gap: 10,
  },
  savedText: {
    fontSize: 16,
    color: '#555',
    marginTop: 10,
  },
  warningText: {
    fontSize: 12,
    color: '#888',
    textAlign: 'center',
    marginTop: 20,
    fontStyle: 'italic',
  }
});
```

### ۱۰-۳: `SQLite` – دیتابیس رابطه‌ای

برای مدیریت داده‌های **حجیم، پیچیده و رابطه‌ای** که نیاز به کوئری‌های پیشرفته و عملکرد بالا در حالت آفلاین دارند، به یک دیتابیس واقعی روی دستگاه نیاز داریم. `expo-sqlite` یک پیاده‌سازی از دیتابیس محبوب **SQLite** را فراهم می‌کند. این دیتابیس به صورت یک فایل روی دستگاه کاربر ذخیره می‌شود.

*   **کاربرد**: ساخت اپلیکیشن‌هایی که باید به صورت آفلاین به خوبی کار کنند، اپ‌های مدیریت وظایف، یا هر برنامه‌ای با داده‌های ساختاریافته که نیاز به جستجو و فیلترهای پیچیده دارند.
*   **نصب**: `npx expo install expo-sqlite`

**مثال (ایجاد دیتابیس و جدول)**:
```jsx
import React, { useEffect, useState } from 'react';
import { View, Text, Button, TextInput, StyleSheet, FlatList, ActivityIndicator } from 'react-native';
import * as SQLite from 'expo-sqlite';

// باز کردن یا ایجاد دیتابیس
const db = SQLite.openDatabase('notes.db');

export default function SQLiteExample() {
  const [noteText, setNoteText] = useState('');
  const [notes, setNotes] = useState([]);
  const [isLoading, setIsLoading] = useState(true);

  useEffect(() => {
    db.transaction(tx => {
      tx.executeSql(
        'create table if not exists notes (id integer primary key not null, text text);',
        [],
        () => console.log('جدول ایجاد شد یا از قبل وجود داشت.'),
        (_, error) => console.error('خطا در ایجاد جدول:', error)
      );
    }, null, () => {
      console.log('تراکنش ایجاد جدول کامل شد.');
      loadNotes(); // پس از اطمینان از وجود جدول، یادداشت‌ها را بارگذاری کنید
    });
  }, []);

  const addNote = () => {
    if (noteText.trim()) {
      db.transaction(tx => {
        tx.executeSql('insert into notes (text) values (?);', [noteText],
          (_, result) => {
            console.log('یادداشت اضافه شد:', result.insertId);
            setNoteText('');
            loadNotes();
          },
          (_, error) => console.error('خطا در افزودن یادداشت:', error)
        );
      });
    } else {
      alert('لطفاً متن یادداشت را وارد کنید.');
    }
  };

  const loadNotes = () => {
    setIsLoading(true);
    db.transaction(tx => {
      tx.executeSql('select * from notes order by id desc;', [],
        (_, { rows: { _array } }) => {
          setNotes(_array);
          console.log('یادداشت‌ها بارگذاری شدند:', _array);
        },
        (_, error) => console.error('خطا در بارگذاری یادداشت‌ها:', error)
      );
    }, null, () => setIsLoading(false)); // پس از تکمیل تراکنش، isLoading را false کنید
  };

  const deleteNote = (id) => {
    db.transaction(tx => {
      tx.executeSql('delete from notes where id = ?;', [id],
        () => {
          console.log('یادداشت حذف شد:', id);
          loadNotes();
        },
        (_, error) => console.error('خطا در حذف یادداشت:', error)
      );
    });
  };

  if (isLoading && notes.length === 0) { // فقط در ابتدا یا وقتی که هنوز داده‌ای لود نشده، لودینگ نشان دهد
    return (
      <View style={styles.centered}>
        <ActivityIndicator size="large" color="#0000ff" />
        <Text>در حال آماده‌سازی دیتابیس...</Text>
      </View>
    );
  }

  return (
    <View style={styles.container}>
      <Text style={styles.header}>مدیریت یادداشت‌ها با SQLite</Text>
      <TextInput
        style={styles.input}
        placeholder="یادداشت جدید..."
        value={noteText}
        onChangeText={setNoteText}
      />
      <Button title="افزودن یادداشت" onPress={addNote} />

      <Text style={styles.notesHeader}>یادداشت‌های من:</Text>
      <FlatList
        data={notes}
        keyExtractor={(item) => item.id.toString()}
        renderItem={({ item }) => (
          <View style={styles.noteItem}>
            <Text style={styles.noteText}>{item.text}</Text>
            <Button title="حذف" onPress={() => deleteNote(item.id)} color="red" />
          </View>
        )}
        ListEmptyComponent={<Text style={styles.emptyText}>هنوز یادداشتی وجود ندارد.</Text>}
      />
    </View>
  );
}

const styles = StyleSheet.create({
  centered: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  container: {
    flex: 1,
    paddingTop: 50,
    paddingHorizontal: 20,
    backgroundColor: '#e6e6fa', // Light purple background
  },
  header: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
    textAlign: 'center',
    color: '#4b0082', // Indigo
  },
  input: {
    height: 50,
    borderColor: '#9370db', // MediumPurple
    borderWidth: 1,
    borderRadius: 8,
    paddingHorizontal: 15,
    marginBottom: 15,
    backgroundColor: 'white',
    fontSize: 16,
  },
  notesHeader: {
    fontSize: 20,
    fontWeight: 'bold',
    marginTop: 30,
    marginBottom: 15,
    color: '#4b0082',
    textAlign: 'center',
  },
  noteItem: {
    backgroundColor: 'white',
    padding: 15,
    borderRadius: 8,
    marginBottom: 10,
    flexDirection: 'row',
    justifyContent: 'space-between',
    alignItems: 'center',
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.1,
    shadowRadius: 3,
    elevation: 3,
  },
  noteText: {
    fontSize: 16,
    flexShrink: 1,
    marginRight: 10,
    color: '#333',
  },
  emptyText: {
    fontSize: 16,
    color: '#888',
    textAlign: 'center',
    marginTop: 20,
  }
});
```

---

## فصل ۱۱: روح بخشیدن به اپ: انیمیشن و جسچرها

انیمیشن‌های روان و بازخوردهای لمسی جذاب، تجربه کاربری (**UX**) را به سطح دیگری می‌برند و اپلیکیشن شما را زنده و پویاتر می‌کنند. در این فصل، با استفاده از کتابخانه‌های قدرتمند **React Native Reanimated** و `react-native-gesture-handler`، یاد می‌گیریم چگونه انیمیشن‌های پیشرفته و تعاملات لمسی پیچیده را پیاده‌سازی کنیم.

### ۱۱-۱: انیمیشن با React Native Reanimated

**React Native Reanimated**:

کتابخانه استاندارد و مدرن برای پیاده‌سازی انیمیشن‌های با عملکرد بالا در **React Native** است. دلیل اصلی برتری آن این است که منطق انیمیشن را مستقیماً روی **نخ UI (Main Thread)** اجرا می‌کند. این کار باعث می‌شود انیمیشن‌ها حتی زمانی که نخ جاوااسکریپت مشغول است، به صورت **روان و ۶۰ فریم بر ثانیه** اجرا شوند. این از گیر کردن انیمیشن‌ها هنگام پردازش‌های سنگین در نخ **JS** جلوگیری می‌کند.

*   **مفاهیم اصلی**:
    *   `useSharedValue`:
    *
    *     این هوک برای تعریف مقادیری استفاده می‌شود که قرار است **انیمیت شوند**. مانند `useState` عمل می‌کند، اما مقدار ذخیره شده در آن بین نخ **JS** و نخ **UI** "به اشتراک گذاشته" می‌شود. تغییر این مقادیر مستقیماً در نخ **UI** اعمال می‌شود.
    *   `useAnimatedStyle`:
    *
    *     این هوک یک آبجکت استایل انیمیشنی را برمی‌گرداند که به مقادیر اشتراکی (`Shared Values`) شما متصل است. هر زمان که مقدار اشتراکی تغییر کند، استایل مربوطه به صورت انیمیت شده به‌روزرسانی می‌شود. این هوک یک آبجکت استایل برمی‌گرداند که می‌توانید آن را به کامپوننت‌های **Animated** خود بدهید.
    *   `Animated.View`, `Animated.Text` و `Animated.Image`:
    *
    *     نسخه‌های انیمیشنی کامپوننت‌های اصلی **React Native** هستند. شما باید کامپوننت‌هایی را که می‌خواهید انیمیت کنید، به این نسخه‌های **Animated** تبدیل کنید تا بتوانند استایل‌های انیمیشنی را دریافت کنند.
    *   `withTiming` و `withSpring`:
    *
    *     این توابع به **Reanimated** می‌گویند که یک مقدار را **چگونه** انیمیت کند.
        *   `withTiming(toValue, config)`:
        *
        *     یک انیمیشن مبتنی بر **زمان** (**Duration**) ایجاد می‌کند. برای انیمیشن‌های با مدت زمان مشخص و منحنی (easing).
        *   `withSpring(toValue, config)`:
        *
        *     یک انیمیشن **فنری** و طبیعی ایجاد می‌کند که حالت ارتداد (**Bouncy**) دارد.
        * 
*   **نصب**:
    *   `npx expo install react-native-reanimated`
    *   پس از نصب، باید `plugins: ['react-native-reanimated/plugin']` را به فایل `babel.config.js` خود اضافه کرده و سرور **Metro** را ریستارت کنید.

**مثال (یک `View` که با کلیک کردن اندازه آن تغییر می‌کند)**:
```jsx
import React from 'react';
import { View, Text, StyleSheet, Button } from 'react-native';
import Animated, {
  useSharedValue,
  useAnimatedStyle,
  withTiming,
  withSpring,
} from 'react-native-reanimated';

export default function ReanimatedScaleExample() {
  const scale = useSharedValue(1); // مقدار اولیه 1 (بدون تغییر اندازه)

  const handlePress = () => {
    // تغییر مقدار scale.value باعث انیمیشن می‌شود
    scale.value = withSpring(scale.value === 1 ? 1.5 : 1); // تغییر به 1.5 یا بازگشت به 1
  };

  // تعریف استایل انیمیشنی بر اساس مقدار scale
  const animatedStyle = useAnimatedStyle(() => {
    return {
      transform: [{ scale: scale.value }],
    };
  });

  return (
    <View style={styles.container}>
      <Animated.View style={[styles.box, animatedStyle]}>
        <Text style={styles.text}>کلیک کن!</Text>
      </Animated.View>
      <Button title="تغییر اندازه" onPress={handlePress} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f0f0f0',
  },
  box: {
    width: 150,
    height: 150,
    backgroundColor: '#61dafb',
    borderRadius: 15,
    justifyContent: 'center',
    alignItems: 'center',
    marginBottom: 50,
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 4 },
    shadowOpacity: 0.2,
    shadowRadius: 5,
    elevation: 8,
  },
  text: {
    fontSize: 20,
    fontWeight: 'bold',
    color: 'white',
  },
});
```

### ۱۱-۲: کار با حرکات لمسی (Gestures)

برای مدیریت حرکات لمسی پیچیده مانند کشیدن (**Drag**), زوم کردن، یا چرخاندن، ما از کتابخانه **`react-native-gesture-handler`** در ترکیب با **Reanimated** استفاده می‌کنیم. این کتابخانه‌ها به ما اجازه می‌دهند که حرکات لمسی را به صورت بومی و با عملکرد بالا پردازش کنیم. این ترکیب به شما امکان می‌دهد جسچرهای پیچیده را تعریف کنید و انیمیشن‌های مربوطه را مستقیماً روی نخ **UI** اجرا کنید.

*   **API مدرن**:
    *   به جای هوک‌های قدیمی، از آبجکت **`Gesture`** برای تعریف نوع حرکت (مثلاً `Gesture.Pan()` برای کشیدن، `Gesture.Tap()` برای ضربه) و از کامپوننت **`<GestureDetector>`** برای اعمال آن به یک عنصر استفاده می‌کنیم.
    *   این باعث می‌شود تعریف جسچرها بسیار تمیزتر و ماژولارتر باشد.
*   **Worklets**:
    *   توابعی که قرار است در پاسخ به جسچرها روی نخ **UI** اجرا شوند، باید با دستورالعمل `"worklet";` در ابتدای آن‌ها مشخص شوند.
    *   این دستورالعمل به باندلر می‌گوید که این تابع را برای اجرا در محیط **Reanimated** آماده کند و از کرش کردن برنامه جلوگیری می‌کند.
*   **نصب**:
    *   `npx expo install react-native-gesture-handler`
    *   پس از نصب `react-native-gesture-handler`، باید آن را در entry-point اصلی برنامه (معمولا `index.js` یا `App.js`) ایمپورت کنید: `import 'react-native-gesture-handler';`.

**مثال (کشیدن یک جعبه)**:
```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';
import { Gesture, GestureDetector } from 'react-native-gesture-handler';
import Animated, {
  useSharedValue,
  useAnimatedStyle,
  runOnJS,
} from 'react-native-reanimated';

export default function DraggableBox() {
  const translateX = useSharedValue(0);
  const translateY = useSharedValue(0);

  // این تابع در نخ UI اجرا می‌شود، بنابراین باید "worklet" باشد.
  const handleDragEnd = (event) => {
    'worklet';
    // می‌توانید اینجا منطقی را به JS Thread برگردانید، مثلاً برای ذخیره موقعیت نهایی
    runOnJS(console.log)('Box dragged to:', { x: event.translationX, y: event.translationY });
  };

  const panGesture = Gesture.Pan()
    .onStart((event) => {
      // در شروع حرکت، موقعیت فعلی را ذخیره کنید
    })
    .onUpdate((event) => {
      // موقعیت فعلی را بر اساس حرکت انگشت به روز کنید
      translateX.value = event.translationX;
      translateY.value = event.translationY;
    })
    .onEnd((event) => {
      // بعد از پایان حرکت، موقعیت را ریست کنید یا به موقعیت خاصی برگردانید
      // می‌توانید از withSpring یا withTiming برای انیمیشن بازگشت استفاده کنید
      translateX.value = withSpring(0);
      translateY.value = withSpring(0);
      handleDragEnd(event); // فراخوانی تابع در JS Thread
    });

  const animatedStyle = useAnimatedStyle(() => {
    return {
      transform: [{ translateX: translateX.value }, { translateY: translateY.value }],
    };
  });

  return (
    <View style={styles.container}>
      <Text style={styles.header}>جعبه را بکشید!</Text>
      <GestureDetector gesture={panGesture}>
        <Animated.View style={[styles.box, animatedStyle]}>
          <Text style={styles.boxText}>مرا بکش</Text>
        </Animated.View>
      </GestureDetector>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f5f5f5',
  },
  header: {
    fontSize: 22,
    fontWeight: 'bold',
    marginBottom: 50,
    color: '#333',
  },
  box: {
    width: 120,
    height: 120,
    backgroundColor: '#ff69b4', // HotPink
    borderRadius: 20,
    justifyContent: 'center',
    alignItems: 'center',
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 5 },
    shadowOpacity: 0.3,
    shadowRadius: 10,
    elevation: 10,
  },
  boxText: {
    color: 'white',
    fontSize: 18,
    fontWeight: 'bold',
  },
});
```
*توجه: مطمئن شوید `react-native-gesture-handler` در فایل اصلی اپلیکیشن شما (معمولاً `index.js` یا `App.js`) ایمپورت شده است: `import 'react-native-gesture-handler';`*

---

## فصل ۱۳: بهینه‌سازی و عملکرد (Performance Optimization)

عملکرد (**Performance**) یکی از مهم‌ترین جنبه‌های هر اپلیکیشن موبایل است. یک اپلیکیشن سریع، روان و پاسخگو، تجربه کاربری بهتری را ارائه می‌دهد و کاربران را راضی نگه می‌دارد. در این فصل، یاد می‌گیریم چطور اپلیکیشن خود را سریع، روان و بهینه نگه داریم تا بهترین تجربه کاربری را ارائه دهیم.

### ۱۳-۱: ابزارهای اصلی

برای شناسایی مشکلات عملکردی در اپلیکیشن **React Native**، ابزارهای قدرتمندی در دسترس داریم:

*   **Profiler در React DevTools**:
    *   این ابزار، که از طریق **Flipper** قابل دسترسی است، به شما اجازه می‌دهد **عملکرد رندرینگ اپلیکیشن** را ضبط و تحلیل کنید.
    *   با استفاده از **Profiler** می‌توانید ببینید کدام کامپوننت‌ها بیهوده دوباره رندر می‌شوند یا رندر آن‌ها زمان‌بر است. این ابزار به شناسایی `bottlenecks` (نقاط گلوگاهی) در رندرینگ کمک می‌کند.
*   **Flipper**:
    *   **Flipper**:
    *
    *     یک اپلیکیشن دسکتاپ و ابزار دیباگینگ **همه‌کاره** است که توسط فیس‌بوک توسعه یافته است.
    *   این ابزار پلاگین‌های متنوعی برای بررسی جنبه‌های مختلف اپلیکیشن ارائه می‌دهد:
        *   **Layout (چیدمان)**: برای بررسی و تغییر چیدمان عناصر **UI** در زمان واقعی.
        *   **Network (شبکه)**: برای مشاهده تمام درخواست‌های شبکه و پاسخ‌های آن‌ها.
        *   **Logs (لاگ‌ها)**: برای مشاهده پیام‌های `console.log` و خطاها.
        *   **Shared Preferences/AsyncStorage**: برای بررسی داده‌های ذخیره شده در دستگاه.
    *   استفاده از **Flipper** برای دیباگینگ و مانیتورینگ عملکرد بسیار توصیه می‌شود.

### ۱۳-۲: تکنیک‌های بهینه‌سازی

برای بهبود عملکرد اپلیکیشن، چندین تکنیک کلیدی وجود دارد:

1.  **جلوگیری از رندرهای غیرضروری**:
    *   رندر شدن بیش از حد کامپوننت‌ها (حتی اگر **UI** تغییری نکرده باشد) یکی از دلایل اصلی افت عملکرد است. **React** ابزارهایی برای جلوگیری از این رندرهای اضافی ارائه می‌دهد:
        *   **`React.memo`**:

 یک **Higher-Order Component (HOC)** است که کامپوننت‌های تابعی را **memoize** می‌کند. این کامپوننت‌ها اگر **props** آن‌ها تغییر نکرده باشد، از رندر شدن مجدد محافظت می‌شوند. اگر پراپ‌های یک کامپوننت memoized تغییر نکرده باشد، **React** از آخرین رندر کش شده آن استفاده می‌کند.
 
        *   **`useCallback`**:

 از ساخته شدن **مجدد توابع** در هر رندر جلوگیری می‌کند. این هوک به خصوص برای توابعی که به عنوان **props** به کامپوننت‌های memoized پاس داده می‌شوند، مفید است تا رندر غیرضروری آن‌ها را متوقف کند.
        *   **`useMemo`**:
        
 نتیجه محاسبات سنگین را در حافظه **کش** می‌کند تا از اجرای مجدد آن‌ها در هر رندر جلوگیری شود. از این هوک برای محاسباتی استفاده کنید که زمان‌بر هستند.

**مثال کد برای `React.memo`, `useCallback`, و `useMemo`**:
```jsx
import React, { useState, useCallback, useMemo, memo } from 'react';
import { View, Text, Button, StyleSheet } from 'react-native';

// 1. استفاده از React.memo برای جلوگیری از رندر غیرضروری کامپوننت فرزند
// این کامپوننت فقط زمانی رندر می‌شود که پراپ‌های آن (count یا onIncrement) تغییر کنند.
const MemoizedChildComponent = memo(({ count, onIncrement }) => {
  console.log('MemoizedChildComponent rendered!');
  return (
    <View style={styles.childContainer}>
      <Text style={styles.childText}>شمارنده فرزند: {count}</Text>
      <Button title="افزایش شمارنده فرزند" onPress={onIncrement} />
    </View>
  );
});

// 2. کامپوننتی که از useMemo برای کش کردن نتیجه یک محاسبه سنگین استفاده می‌کند
function ExpensiveCalculationComponent({ value }) {
  // useMemo فقط زمانی تابع را دوباره اجرا می‌کند که 'value' تغییر کرده باشد
  const calculatedResult = useMemo(() => {
    console.log('Performing expensive calculation...');
    let sum = 0;
    for (let i = 0; i < 1000000; i++) { // یک حلقه سنگین برای شبیه‌سازی
      sum += i;
    }
    return sum + value;
  }, [value]); // آرایه وابستگی: اگر value تغییر کند، محاسبه دوباره انجام می‌شود

  return (
    <View style={styles.expensiveCalcContainer}>
      <Text style={styles.expensiveCalcText}>
        نتیجه محاسبه سنگین (بستگی به ورودی): {calculatedResult}
      </Text>
    </View>
  );
}

export default function OptimizationExample() {
  const [parentCount, setParentCount] = useState(0);
  const [childCount, setChildCount] = useState(0);

  // 3. استفاده از useCallback برای Memoize کردن تابع onIncrement
  // این تضمین می‌کند که تابع 'handleIncrementChild' فقط یک بار ایجاد شود
  // و هر بار که کامپوننت والد رندر می‌شود، دوباره ایجاد نشود.
  // این برای پراپ‌های توابع که به کامپوننت‌های memoized ارسال می‌شوند بسیار مهم است.
  const handleIncrementChild = useCallback(() => {
    setChildCount(prev => prev + 1);
  }, []); // آرایه وابستگی خالی به این معنی است که تابع فقط یک بار در mount ایجاد می‌شود

  return (
    <View style={styles.container}>
      <Text style={styles.header}>مثال بهینه‌سازی React</Text>

      <Text style={styles.parentText}>شمارنده والد: {parentCount}</Text>
      <Button
        title="افزایش شمارنده والد (باعث رندر شدن Parent می‌شود)"
        onPress={() => setParentCount(parentCount + 1)}
      />

      {/* کامپوننت فرزند که با React.memo بهینه شده است */}
      <MemoizedChildComponent count={childCount} onIncrement={handleIncrementChild} />

      {/* کامپوننتی که از useMemo استفاده می‌کند */}
      <ExpensiveCalculationComponent value={parentCount} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    backgroundColor: '#fff',
    gap: 20,
  },
  header: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 30,
    color: '#333',
  },
  parentText: {
    fontSize: 18,
    marginBottom: 10,
    color: '#444',
  },
  childContainer: {
    marginTop: 30,
    padding: 20,
    borderRadius: 10,
    borderWidth: 1,
    borderColor: '#aaddff',
    alignItems: 'center',
    backgroundColor: '#e0f7fa',
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.1,
    shadowRadius: 4,
    elevation: 3,
  },
  childText: {
    fontSize: 16,
    marginBottom: 10,
    color: '#007bff',
  },
  expensiveCalcContainer: {
    marginTop: 30,
    padding: 15,
    borderRadius: 10,
    backgroundColor: '#fffbe0',
    borderWidth: 1,
    borderColor: '#ffd700',
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.1,
    shadowRadius: 4,
    elevation: 3,
  },
  expensiveCalcText: {
    fontSize: 14,
    fontStyle: 'italic',
    color: '#8a6d3b',
    textAlign: 'center',
  }
});
```

2.  **بهینه‌سازی `FlatList`**:
    *   FlatList:
    *
    *     به طور طبیعی بهینه است، اما پراپ‌های خاصی می‌توانند عملکرد آن را برای لیست‌های بسیار بلند بیشتر بهبود بخشند.
    *   `getItemLayout`:
    *
    *     اگر ارتفاع تمام آیتم‌های لیست ثابت است، با تعریف این پراپ می‌توانید به FlatList کمک کنید تا بدون نیاز به اندازه‌گیری، موقعیت و ابعاد آیتم‌ها را محاسبه کند. این به اسکرولینگ بسیار روان‌تر منجر می‌شود.
    *   `initialNumToRender`:
    *
    *     تعداد آیتم‌هایی که FlatList باید در ابتدا رندر کند را مشخص می‌کند. تنظیم صحیح این مقدار می‌تواند زمان بارگذاری اولیه را بهبود بخشد.

3.  **موتور Hermes**:
    *   **Hermes**:
    *
    *     موتور جاوااسکریپت بهینه‌سازی شده برای **React Native** است که توسط **Meta** توسعه یافته است.
    *   این موتور به طور پیش‌فرض در پروژه‌های **Expo** فعال است و باعث کاهش مصرف حافظه و افزایش سرعت بارگذاری اولیه اپلیکیشن می‌شود.
    *   فعال بودن **Hermes** به طور کلی عملکرد اپلیکیشن شما را به میزان قابل توجهی بهبود می‌بخشد. مطمئن شوید که **Hermes** در پروژه شما فعال است (`in app.json` یا `app.config.js`).

---

## فصل ۱۴: گردش کار حرفه‌ای: Development Builds

این بخش، کلید عبور از محدودیت‌های گذشته **Expo Go** و رسیدن به نهایت قدرت **Expo** است.

### ۱۴-۱: مشکل Expo Go

اپلیکیشن **Expo Go** که برای اجرای سریع پروژه‌ها روی دستگاه‌های واقعی استفاده می‌شود، شامل مجموعه‌ای از **ماژول‌های نیتیو از پیش نصب شده** است. این ماژول‌ها کتابخانه‌های پرکاربرد **Expo** (مانند `expo-camera`, `expo-location` و غیره) را فراهم می‌کنند.

**مشکل اینجا پیش می‌آید**: اگر شما به یک **کتابخانه نیتیو دیگری** نیاز داشته باشید که جزو ماژول‌های از پیش نصب شده در **Expo Go** نیست (مثلاً یک کتابخانه پرداخت سفارشی، `react-native-blur` یا یک **SDK** خاص)، اپلیکیشن شما در **Expo Go کرش می‌کند** و قابل اجرا نخواهد بود. در گذشته، برای استفاده از چنین کتابخانه‌هایی، مجبور بودید پروژه را به **React Native CLI** "Eject" کنید، که به معنای از دست دادن سادگی **Expo** و ورود به دنیای پیچیده‌تر مدیریت کدهای نیتیو بود.

### ۱۴-۲: راه حل: Development Builds

**Development Build (بیلد توسعه)**:

یک نسخه کاملاً **سفارشی از اپلیکیشن Expo Go** است که **مخصوص پروژه شما** ساخته می‌شود. این بیلد، علاوه بر ماژول‌های پیش‌فرض **Expo**، **تمام کتابخانه‌های نیتیو دیگری که شما به پروژه خود اضافه کرده‌اید** را نیز شامل می‌شود.

*   **نتیجه**: شما دیگر هیچ محدودیتی در استفاده از کتابخانه‌های اکوسیستم گسترده **React Native** ندارید و در عین حال از سادگی و سرعت توسعه **Expo** (مانند **Fast Refresh** و **Metro Bundler**) بهره‌مند می‌شوید. این به شما اجازه می‌دهد تا هر پکیج npm که شامل کد نیتیو است را نصب و استفاده کنید.
*   **فرآیند**:
    1.  **نصب `expo-dev-client`**:
        ```bash
        npx expo install expo-dev-client
        ```
    2.  **ساخت Development Build**: با اجرای دستور `eas build --profile development`، یک نسخه توسعه از اپلیکیشن خود می‌سازید. این دستور بیلد را در سرویس ابری **EAS** انجام می‌دهد و یک فایل `.apk` (برای اندروید) یا `.ipa` (برای iOS) به شما می‌دهد.
    3.  **استفاده**: پس از ساخت و نصب این بیلد روی دستگاه واقعی یا شبیه‌ساز، از آن به جای اپلیکیشن **Expo Go** برای توسعه روزمره خود استفاده می‌کنید. این بیلد به سرور **Metro** شما متصل می‌شود و **Fast Refresh** و سایر ابزارهای دیباگینگ همچنان کار می‌کنند.
*   **خلاصه**: **Development Builds** به شما بهترین هر دو دنیا را می‌دهد: سادگی **Expo** برای توسعه سریع جاوااسکریپت، و انعطاف‌پذیری **React Native CLI** برای استفاده از هر کتابخانه نیتیوی که نیاز دارید.

---

## فصل ۱۵: از کد تا کاربر: ساخت و انتشار با EAS

پس از اینکه اپلیکیشن خود را توسعه دادید و از کیفیت آن مطمئن شدید، گام نهایی تبدیل کد شما به یک اپلیکیشن واقعی و قابل انتشار در فروشگاه‌های اپلیکیشن (**Google Play Store** و **Apple App Store**) است. **Expo** به وسیله سرویس **EAS (Expo Application Services)** این فرآیند را به شدت ساده و خودکار می‌کند.

### ۱۵-۱: EAS Build

**EAS Build**:

یک سرویس ابری از **Expo** است که کدهای شما را دریافت کرده و **فایل‌های نهایی اپلیکیشن** را برای پلتفرم‌های مختلف در فضای ابری برایتان می‌سازد.

*   **خروجی**: برای اندروید، فایل‌های `.apk` (برای نصب مستقیم) یا `.aab` (**Android App Bundle**، فرمت توصیه شده برای انتشار در پلی استور) تولید می‌شود. برای iOS، فایل `.ipa` تولید می‌شود.
*   **مزیت اصلی**: **بدون نیاز به داشتن مک برای ساخت خروجی iOS** و بدون درگیر شدن با تنظیمات پیچیده **Xcode** و **Android Studio**. **EAS Build** تمام فرآیند کامپایل نیتیو را در سرورهای خود انجام می‌دهد.
*   **دستور**:
    *   `eas build --platform all` (برای ساخت بیلد برای هر دو پلتفرم)
    *   شما می‌توانید با `---platform android` یا `---platform ios` فقط برای یک پلتفرم خاص بیلد بگیرید.

### ۱۵-۲: EAS Update (آپدیت هوایی - OTA)

**EAS Update**:

یکی از قدرتمندترین قابلیت‌های **Expo** است. این ویژگی به شما اجازه می‌دهد تا **تمام تغییرات جاوااسکریپت** (مانند اصلاح باگ‌ها، تغییرات ظاهری، به‌روزرسانی‌های منطق برنامه) را **بدون نیاز به انتشار نسخه جدید در اپ استورها**، مستقیماً برای کاربران خود ارسال کنید.

*   **نحوه کار**: **EAS Update** یک بسته جاوااسکریپت جدید تولید می‌کند و آن را روی **CDN** (شبکه توزیع محتوا) میزبانی می‌کند. اپلیکیشن‌های کاربران شما در پس‌زمینه این به‌روزرسانی‌ها را دریافت کرده و در اجرای بعدی یا پس از چند دقیقه آن‌ها را اعمال می‌کنند.
*   **اهمیت**: این ویژگی می‌تواند زمان انتشار به‌روزرسانی‌ها را از چند روز/هفته به **چند دقیقه** کاهش دهد و برای رفع سریع باگ‌ها یا اعمال تغییرات کوچک بسیار حیاتی است.
*   **دستور**: `eas update`

### ۱۵-۳: EAS Submit

**EAS Submit**:

یک سرویس دیگر از **EAS** است که فرآیند **آپلود کردن فایل نهایی اپلیکیشن** (که توسط **EAS Build** تولید شده) به **Google Play Console** (برای اندروید) و **App Store Connect** (برای iOS) را به صورت خودکار و از طریق خط فرمان انجام می‌دهد.

*   **مزیت**: این کار باعث صرفه‌جویی زیادی در زمان و کاهش خطاهای انسانی در فرآیند انتشار می‌شود. نیاز به آپلود دستی فایل‌ها، پر کردن جزئیات و مدیریت گواهی‌ها را کاهش می‌دهد و این فرآیند اغلب پیچیده را ساده می‌کند.
*   **دستور**:
    *   `eas submit -p android` (برای اندروید)
    *   `eas submit -p ios` (برای iOS)
*   این دستورات به شما کمک می‌کنند تا بیلد نهایی را به راحتی به فروشگاه‌های مربوطه ارسال کنید.

---

## فصل ۱۶: قدرت نوع‌دهی: TypeScript در React Native

در این فصل، یاد می‌گیریم که چگونه با استفاده از TypeScript، کدهای خود را قوی‌تر، خواناتر و با خطاهای کمتری بنویسیم. TypeScript یک لایه اضافی روی جاوااسکریپت است که قابلیت نوع‌دهی ایستا (Static Typing) را به آن اضافه می‌کند.

همانطور که در فصل ۲ اشاره شد، پروژه‌های جدید Expo به طور پیش‌فرض با TypeScript ساخته می‌شوند. این نشان‌دهنده اهمیت روزافزون آن در توسعه مدرن است. هدف این فصل، آشنایی شما با الگوهای اصلی استفاده از TypeScript در یک پروژه React Native است تا بتوانید از تمام مزایای آن بهره‌مند شوید.

### ۱۶-۱: چرا از TypeScript استفاده کنیم؟

استفاده از TypeScript در پروژه‌های React Native چندین مزیت کلیدی به همراه دارد:

*   **کشف خطاها قبل از اجرا**: TypeScript بسیاری از خطاهای رایج (مانند اشتباهات تایپی در نام پراپ‌ها یا ارسال نوع داده اشتباه) را در همان محیط کدنویسی (IDE) شناسایی می‌کند، نه در زمان اجرای اپلیکیشن.
*   **تکمیل خودکار کد (Autocompletion) هوشمند**: ویرایشگر کد شما با درک کامل انواع داده‌ها، پراپ‌ها و توابع، پیشنهادات بسیار دقیق‌تری ارائه می‌دهد که سرعت کدنویسی را به شدت افزایش می‌دهد.
*   **کد خود-مستندساز (Self-Documenting Code)**: با تعریف انواع (Types) برای پراپ‌ها و stateها، کد شما به طور خودکار خواناتر می‌شود. هر کسی با دیدن تعاریف انواع، به سرعت ساختار داده‌های مورد انتظار یک کامپوننت را درک می‌کند.
*   **بازسازی کد (Refactoring) با اطمینان**: هنگامی که نیاز به تغییر نام یک پراپ یا ساختار یک آبجکت دارید، TypeScript به شما کمک می‌کند تا تمام مکان‌هایی که نیاز به آپدیت دارند را به راحتی پیدا کنید و از بروز باگ‌های ناخواسته جلوگیری می‌کند.

### ۱۶-۲: نوع‌دهی کامپوننت‌ها و پراپ‌ها (Props)

پایه‌ای‌ترین کاربرد TypeScript در React، تعریف نوع برای پراپ‌های (Props) یک کامپوننت است. این کار تضمین می‌کند که کامپوننت همیشه داده‌های صحیح را دریافت کند. برای این کار، از `interface` یا `type` استفاده می‌کنیم.

**مثال (یک کامپوننت کارت ساده)**:
```typescript
import React from 'react';
import { View, Text, StyleSheet, type ReactNode } from 'react-native';

// 1. تعریف نوع برای پراپ‌ها
type CardProps = {
  title: string;
  subtitle?: string; // این پراپ اختیاری است
  children: ReactNode; // ReactNode نوعی است که هر چیزی که در React قابل رندر باشد را می‌پذیرد
};

// 2. استفاده از نوع تعریف شده برای پراپ‌های کامپوننت
export default function Card({ title, subtitle, children }: CardProps) {
  return (
    <View style={styles.card}>
      <Text style={styles.title}>{title}</Text>
      {subtitle && <Text style={styles.subtitle}>{subtitle}</Text>}
      <View style={styles.content}>
        {children}
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  card: {
    backgroundColor: 'white',
    padding: 16,
    borderRadius: 8,
    margin: 10,
    elevation: 3, // برای اندروید
    shadowColor: '#000', // برای iOS
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.1,
    shadowRadius: 4,
  },
  title: {
    fontSize: 18,
    fontWeight: 'bold',
    marginBottom: 5,
    color: '#333',
  },
  subtitle: {
    fontSize: 14,
    color: '#666',
    marginBottom: 10,
  },
  content: {
    // استایل برای محتوای داخل کارت
    marginTop: 5,
  },
});
```

### ۱۶-۳: نوع‌دهی هوک‌ها (Hooks)

این TypeScript با هوک‌های React به زیبایی کار می‌کند و در بیشتر موارد، نوع‌ها را به صورت خودکار استنتاج (Infer) می‌کند.

#### `useState`

هنگام استفاده از `useState`، تایپ‌اسکریپت معمولاً نوع state را از مقدار اولیه آن تشخیص می‌دهد.

```typescript
// در اینجا، تایپ‌اسکریپت به طور خودکار تشخیص می‌دهد که `count` از نوع `number` است
const [count, setCount] = useState(0);

// در اینجا، `name` از نوع `string` است
const [name, setName] = useState('سارا');
```

گاهی اوقات نیاز داریم نوع را به صراحت مشخص کنیم، به خصوص زمانی که مقدار اولیه `null` یا `undefined` است.

```typescript
import { useState } from 'react';

type User = {
  id: number;
  name: string;
};

// state می‌تواند یک آبجکت User یا null باشد
const [user, setUser] = useState<User | null>(null);

// ... بعد از دریافت داده از API
// setUser({ id: 1, name: 'کاربر تست' });
```

#### `useRef`

برای `useRef`، به خصوص هنگام ارجاع به یک کامپوننت (مانند `TextInput`)، باید نوع آن را مشخص کنیم.

```typescript
import { useRef } from 'react';
import { TextInput, View, Button, StyleSheet } from 'react-native'; // نوع TextInput را ایمپورت می‌کنیم

function MyInput() {
  // این رف، به یک کامپوننت TextInput یا null اشاره خواهد کرد
  const inputRef = useRef<TextInput>(null);

  const focusInput = () => {
    inputRef.current?.focus(); // ?. برای اطمینان از اینکه ref به یک عنصر متصل است
  };

  return (
    <View style={styles.container}>
      <TextInput
        ref={inputRef}
        placeholder="فوکوس روی من"
        style={styles.input}
      />
      <Button title="فوکوس روی ورودی" onPress={focusInput} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    padding: 20,
    justifyContent: 'center',
    alignItems: 'center',
  },
  input: {
    height: 40,
    width: '80%',
    borderColor: 'gray',
    borderWidth: 1,
    paddingHorizontal: 10,
    marginBottom: 20,
    borderRadius: 5,
  },
});
```

### ۱۶-۴: نوع‌دهی در استایل‌دهی (StyleSheet)

هنگام استفاده از `StyleSheet.create`، تایپ‌اسکریپت به طور خودکار نوع استایل‌ها را استنتاج می‌کند. اما اگر بخواهید استایل‌ها را به عنوان پراپ ارسال کنید یا در خارج از StyleSheet تعریف کنید، می‌توانید از انواع داخلی React Native استفاده کنید.

*   `ViewStyle`: برای استایل‌های کامپوننت `<View>`.
*   `TextStyle`: برای استایل‌های کامپوننت `<Text>`.
*   `ImageStyle`: برای استایل‌های کامپوننت `<Image>`.

**مثال (یک دکمه سفارشی که استایل می‌پذیرد)**:
```typescript
import React from 'react';
import { Pressable, Text, StyleSheet, type ViewStyle, type TextStyle } from 'react-native';

type CustomButtonProps = {
  title: string;
  onPress: () => void;
  style?: ViewStyle; // پراپ استایل از نوع ViewStyle و اختیاری است
  textStyle?: TextStyle;
};

export default function CustomButton({ title, onPress, style, textStyle }: CustomButtonProps) {
  return (
    <Pressable onPress={onPress} style={[styles.buttonBase, style]}>
      <Text style={[styles.buttonTextBase, textStyle]}>{title}</Text>
    </Pressable>
  );
}

const styles = StyleSheet.create({
  buttonBase: {
    paddingVertical: 12,
    paddingHorizontal: 20,
    borderRadius: 8,
    backgroundColor: '#007bff', // Default blue background
    alignItems: 'center',
    justifyContent: 'center',
  },
  buttonTextBase: {
    color: 'white',
    fontSize: 16,
    fontWeight: 'bold',
  },
});

// نحوه استفاده:
// <CustomButton
//   title="دکمه من"
//   onPress={() => alert('دکمه سفارشی کلیک شد!')}
//   style={{ backgroundColor: 'green', margin: 10 }}
//   textStyle={{ fontSize: 18, color: 'yellow' }}
// />
```

### ۱۶-۵: نوع‌دهی در ناوبری با Expo Router

یکی از قدرتمندترین کاربردهای TypeScript، در بخش ناوبری است. با نوع‌دهی پارامترهای مسیر، از بروز خطاهای مربوط به داده‌های ارسالی بین صفحات جلوگیری می‌کنید.

#### خواندن پارامترهای مسیر با `useLocalSearchParams`

همانطور که در فصل ۸ دیدیم، `useLocalSearchParams` برای خواندن پارامترها از URL استفاده می‌شود. با استفاده از Generics در TypeScript، می‌توانیم نوع این پارامترها را مشخص کنیم.

**مثال (در فایل `app/user/[id].tsx`)**:
```typescript
import { useLocalSearchParams } from 'expo-router';
import { Text, View, StyleSheet } from 'react-native';

export default function UserProfile() {
  // به تایپ‌اسکریپت می‌گوییم که انتظار یک آبجکت با کلید `id` از نوع `string` را داریم
  const { id } = useLocalSearchParams<{ id: string }>();

  // حالا تایپ‌اسکریپت می‌داند که `id` یک رشته است و در استفاده از آن به ما کمک می‌کند
  if (!id) {
    return (
      <View style={styles.container}>
        <Text style={styles.errorText}>شناسه کاربر یافت نشد!</Text>
      </View>
    );
  }

  return (
    <View style={styles.container}>
      <Text style={styles.profileHeader}>پروفایل کاربر</Text>
      <Text style={styles.profileText}>شناسه کاربر: {id}</Text>
      <Text style={styles.profileDetails}>
        این صفحه جزئیات کاربر با شناسه "{id}" را نمایش می‌دهد.
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    backgroundColor: '#f9f9f9',
  },
  profileHeader: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
    color: '#333',
  },
  profileText: {
    fontSize: 20,
    color: '#007bff',
    marginBottom: 10,
    fontWeight: '600',
  },
  profileDetails: {
    fontSize: 16,
    textAlign: 'center',
    color: '#555',
    marginTop: 10,
    lineHeight: 24,
  },
  errorText: {
    fontSize: 18,
    color: 'red',
    fontWeight: 'bold',
  }
});
```

### ۱۶-۶: نوع‌دهی رویدادها و توابع Callback

نوع‌دهی توابعی که به عنوان پراپ ارسال می‌شوند (مانند `onPress`) بسیار مهم است.

**مثال (`onChangeText` در `<TextInput>`)**:
کامپوننت `<TextInput>` در پراپ `onChangeText` خود، یک تابع انتظار دارد که یک آرگومان از نوع `string` دریافت می‌کند.

```typescript
import React, { useState } from 'react';
import { View, TextInput, Text, StyleSheet } from 'react-native';
import { NativeSyntheticEvent, TextInputChangeEventData } from 'react-native'; // برای نوع‌دهی دقیق‌تر رویداد

export default function SearchComponent() {
  const [query, setQuery] = useState('');

  // نیازی به تعریف نوع `text` نیست، چون تایپ‌اسکریپت از تعریف کامپوننت TextInput
  // می‌داند که onChangeText یک رشته برمی‌گرداند.
  const handleTextChange = (text: string) => { // اینجا نوع به صورت خودکار تشخیص داده می‌شود
    setQuery(text);
  };

  // مثال نوع‌دهی صریح برای رویدادهای پیچیده‌تر (اختیاری در این مورد خاص)
  const handleNativeChangeEvent = (e: NativeSyntheticEvent<TextInputChangeEventData>) => {
    // console.log(e.nativeEvent.text);
  };

  return (
    <View style={styles.container}>
      <TextInput
        style={styles.input}
        placeholder="جستجو..."
        value={query}
        onChangeText={handleTextChange} // یا مستقیماً: onChangeText={setQuery}
        onEndEditing={handleNativeChangeEvent} // مثال استفاده از یک رویداد Native
      />
      <Text style={styles.searchText}>متن جستجو شده: {query}</Text>
      {query.length > 0 && (
        <Text style={styles.charCount}>تعداد کاراکتر: {query.length}</Text>
      )}
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
    backgroundColor: '#eef',
  },
  input: {
    height: 50,
    width: '90%',
    borderColor: '#add8e6',
    borderWidth: 1,
    borderRadius: 10,
    paddingHorizontal: 15,
    marginBottom: 20,
    backgroundColor: 'white',
    fontSize: 16,
  },
  searchText: {
    fontSize: 18,
    marginBottom: 10,
    color: '#333',
  },
  charCount: {
    fontSize: 14,
    color: '#666',
    fontStyle: 'italic',
  }
});
```

با استفاده از این الگوها، می‌توانید کدهای React Native خود را به سطح جدیدی از پایداری و خوانایی برسانید و فرآیند توسعه را لذت‌بخش‌تر کنید.
