# کتاب آموزشی: از صفر تا قهرمانی با React Native و Expo

## مقدمه

به دنیای هیجان‌انگیز توسعه اپلیکیشن موبایل با React Native و Expo خوش آمدید! در این کتاب، شما از **مفاهیم پایه تا تکنیک‌های پیشرفته** را فرا خواهید گرفت تا بتوانید ایده‌های خود را به اپلیکیشن‌های موبایل قدرتمند و زیبا برای هر دو پلتفرم iOS و Android تبدیل کنید.

ما مسیر **Expo** را به عنوان استاندارد مدرن و کارآمد دنبال خواهیم کرد. این مسیر، شروع کار را به شدت ساده کرده و به شما امکان می‌دهد با تمرکز بر کد جاوااسکریپت، اپلیکیشن‌های نیتیو بسازید، بدون اینکه نیازی به نصب پیچیده Xcode یا Android Studio در ابتدای کار داشته باشید.

هدف این کتاب، ارائه یک **مسیر یادگیری گام به گام و منطقی** است، به‌گونه‌ای که حتی اگر تجربه قبلی در توسعه موبایل نداشته باشید، بتوانید با اطمینان کامل پیش بروید و در نهایت یک توسعه‌دهنده React Native ماهر شوید.

آینده توسعه موبایل در دستان شماست. بیایید شروع کنیم! 🚀

---

## فصل ۱: خوش آمدگویی به دنیای React Native

در این فصل، با فلسفه اصلی و معماری منحصر به فرد React Native آشنا می‌شویم و تفاوت‌های کلیدی آن را با سایر رویکردهای توسعه موبایل بررسی می‌کنیم. همچنین، تصمیم مهم بین استفاده از Expo و React Native CLI را توضیح خواهیم داد.

### ۱-۱: فلسفه اصلی React Native

کتابخانه React Native  **فریم‌ورک متن-باز** است که به شما این امکان را می‌دهد تا با بهره‌گیری از دانش خود در React و زبان جاوااسکریپت، اپلیکیشن‌های موبایل کاملاً **نیتیو (Native)** را برای سیستم‌عامل‌های iOS و Android توسعه دهید.

**نکته کلیدی و وجه تمایز اصلی React Native** این است که کدهای شما به عناصر واقعی و بومی رابط کاربری در هر پلتفرم ترجمه می‌شوند. این برخلاف ابزارهایی است که صرفاً یک وب‌سایت را در قالب یک اپلیکیشن نمایش می‌دهند (WebView). به عنوان مثال، یک کامپوننت `<View>` در کد React Native شما، به `UIView` در iOS و `ViewGroup` در Android تبدیل می‌شود. به همین ترتیب، `<Text>` به `UITextView` در iOS و `TextView` در Android تبدیل خواهد شد. این **معماری بومی‌سازی** تضمین می‌کند که عملکرد، ظاهر و حس اپلیکیشن شما دقیقاً مانند اپلیکیشنی باشد که با زبان‌های اصلی آن پلتفرم (مانند Swift برای iOS یا Kotlin برای Android) نوشته شده است.

### ۱-۲: معماری درونی: نخ JS و نخ UI

یک اپلیکیشن React Native در دو "قلمرو" یا **Thread (نخ)** اصلی به صورت موازی عمل می‌کند:

*   **نخ جاوااسکریپت (JS Thread):** این نخ مسئولیت اجرای **تمام کدهای React شما**، منطق برنامه، مدیریت وضعیت (state) و فراخوانی APIها را بر عهده دارد. این نخ را می‌توان به عنوان "مغز" یا "فکر کردن" اپلیکیشن در نظر گرفت.
*   **نخ اصلی/UI (Main/UI Thread):** این نخ وظیفه **تمام کارهای بصری** را بر عهده دارد؛ از جمله رندر کردن پیکسل‌ها روی صفحه و پاسخ به ژست‌های لمسی کاربر. برای اینکه کاربر تجربه‌ای روان و بدون لگ داشته باشد، این نخ باید همیشه آزاد و سریع باقی بماند.

این دو نخ از طریق یک مکانیزم ارتباطی مدرن به نام **JSI (JavaScript Interface)** با یکدیگر ارتباط برقرار می‌کنند. JSI به جاوااسکریپت اجازه می‌دهد تا به صورت **مستقیم** به اشیاء و توابع نیتیو دسترسی پیدا کند، که این امر به بهبود عملکرد و پاسخ‌گویی اپلیکیشن کمک شایانی می‌کند.

### ۱-۳: انتخاب مسیر: Expo در مقابل React Native CLI

یکی از مهم‌ترین تصمیم‌ها در ابتدای هر پروژه React Native، انتخاب بین **Expo** و **React Native CLI** است:

* فریمورک **Expo:** یک **فریم‌ورک و مجموعه‌ای جامع از ابزارها** است که بر روی React Native ساخته شده تا فرآیند توسعه را به شدت ساده‌تر کند. با Expo، نیازی به نصب Xcode یا Android Studio برای شروع کار ندارید. این پلتفرم دسترسی به **مجموعه‌ای عظیم از کتابخانه‌های آماده** را فراهم می‌کند که بسیاری از قابلیت‌های رایج موبایل (مانند دوربین، نقشه، اعلان‌ها) را پوشش می‌دهند. سرویس ابری **EAS** نیز فرآیند ساخت و انتشار اپلیکیشن را به شدت تسهیل می‌کند. **این مسیر برای ۹۹٪ پروژه‌ها پیشنهاد می‌شود**.
* دستور **React Native CLI:** این روش، استفاده "خالص" و مستقیم از React Native است. این روش **کنترل کامل** بر تمام جنبه‌های نیتیو پروژه را به شما می‌دهد، اما راه‌اندازی و نگهداری آن به طور قابل توجهی پیچیده‌تر است و نیازمند دانش عمیق‌تر از توسعه نیتیو می‌باشد.

**در این دوره آموزشی، ما مسیر Expo را به عنوان استاندارد مدرن و کارآمد دنبال خواهیم کرد**.

---

## فصل ۲: راه‌اندازی و گردش کار توسعه

اکنون که با مفاهیم پایه آشنا شدیم، زمان آن رسیده که محیط توسعه خود را راه‌اندازی کرده و اولین اپلیکیشن React Native خود را با Expo بسازیم. این فصل شما را با مراحل اولیه، از ساخت پروژه تا اجرای آن روی دستگاه‌های واقعی یا شبیه‌ساز، و همچنین ابزارهای مهم اشکال‌زدایی آشنا می‌کند.

### ۲-۱: راه‌اندازی محیط

برای ساخت یک پروژه خام (Blank) با Expo که به طور پیش‌فرض از TypeScript استفاده می‌کند، از دستور زیر در ترمینال خود استفاده کنید:

```bash
npx create-expo-app YourProjectName
```

**توضیح:**
*   `npx`: یک ابزار برای اجرای پکیج‌های Node.js بدون نیاز به نصب سراسری آن‌ها.
*   `create-expo-app`: دستوری که توسط Expo برای ایجاد پروژه‌های جدید ارائه شده است.
*   `YourProjectName`: نامی که می‌خواهید برای پروژه خود انتخاب کنید.

پس از اینکه پروژه با موفقیت ساخته شد، وارد پوشه پروژه شوید و سرور توسعه (Metro Bundler) را با دستور زیر اجرا کنید:

```bash
cd YourProjectName
npm start
```

**سرور Metro** مسئول کامپایل کردن کد جاوااسکریپت شما و سرویس‌دهی آن به اپلیکیشن در حال اجراست. با اجرای `npm start`، یک QR Code در ترمینال نمایش داده می‌شود که برای اجرای اپلیکیشن روی دستگاه واقعی استفاده می‌شود.

### ۲-۲: اجرای اپلیکیشن

برای دیدن نتیجه کدهای خود، دو راه اصلی دارید:

1.  **دستگاه واقعی (پیشنهادی):**
    *   ابتدا اپلیکیشن **Expo Go** را از App Store (برای iOS) یا Google Play Store (برای Android) روی گوشی هوشمند خود نصب کنید.
    *   **اطمینان حاصل کنید که کامپیوتر و گوشی شما به یک شبکه Wi-Fi مشترک متصل هستند**.
    *   سپس، **QR Code** نمایش داده شده در ترمینال (پس از اجرای `npm start`) را با استفاده از اپلیکیشن Expo Go در گوشی خود اسکن کنید. اپلیکیشن شما به سرعت روی دستگاه لود و اجرا خواهد شد.

2.  **شبیه‌ساز (Simulator/Emulator):**
    *   برای اجرای اپلیکیشن روی شبیه‌ساز iOS، باید **Xcode** را روی یک کامپیوتر Mac نصب کنید.
    *   برای اجرای اپلیکیشن روی شبیه‌ساز Android، باید **Android Studio** را روی کامپیوتر خود نصب کنید.
    *   پس از نصب و پیکربندی مناسب، می‌توانید یک گوشی را روی کامپیوتر خود شبیه‌سازی کرده و اپلیکیشن را روی آن اجرا کنید.

### ۲-۳: ابزارهای اشکال‌زدایی (Debugging)

ابزار‌های React Native و Expo ابزارهای قدرتمندی برای اشکال‌زدایی (Debugging) ارائه می‌دهند که فرآیند توسعه را سریع‌تر و کارآمدتر می‌کنند:

*   **منوی توسعه‌دهنده (Developer Menu):** این منو حاوی گزینه‌های مفیدی برای اشکال‌زدایی و تنظیمات توسعه است.
    *   برای باز کردن آن روی دستگاه واقعی، دستگاه را تکان دهید.
    *   برای شبیه‌ساز، از کلیدهای میانبر استفاده کنید: `Ctrl+Cmd+Z` در iOS یا `Ctrl+M` در ویندوز/لینوکس.

**Fast Refresh:**:
*  یکی از بهترین ویژگی‌های React Native که بهره‌وری را به شدت افزایش می‌دهد. با ذخیره کردن کد، تغییرات به صورت **آنی** و **بدون از دست رفتن وضعیت (state) فعلی اپلیکیشن**، روی صفحه اعمال می‌شوند. این بدان معناست که لازم نیست هر بار اپلیکیشن را مجدداً بارگذاری کنید.

**LogBox:**:
    * این ابزار به شما کمک می‌کند تا خطاها و هشدارها را به راحتی شناسایی کنید.
    *   خطاهای جدی در یک **صفحه قرمز (RedBox)** تمام صفحه نمایش داده می‌شوند.
    *   هشدارها در یک **کادر زرد (YellowBox)** در پایین صفحه ظاهر می‌شوند.

*   **Element Inspector:**:
 این ابزار به شما اجازه می‌دهد تا روی هر عنصر UI کلیک کنید و اطلاعات مربوط به استایل، چیدمان (layout) و پراپ‌های آن را بررسی کنید. این ویژگی مشابه ابزار Inspect Element در مرورگرهای وب است و برای درک نحوه رندر شدن کامپوننت‌ها بسیار مفید است.

---

## فصل ۳: آجرهای ساختمان: کامپوننت‌های اصلی (بخش اول)

در این فصل، با اساسی‌ترین کامپوننت‌های React Native که برای ساخت رابط کاربری (UI) هر اپلیکیشنی مورد نیاز هستند، آشنا می‌شویم. این کامپوننت‌ها به عنوان آجرهای ساختمانی UI شما عمل می‌کنند.

### ۳-۱ ظرف اصلی چیدمان - `<View>`:

کامپوننت `<View>` بنیادی‌ترین و پرکاربردترین کامپوننت برای ساخت UI در React Native است.

*   **معادل وب:** در توسعه وب، `<View>` معادل یک `<div>` است.
*   **کاربرد:** `<View>` به عنوان یک **کانتینر** برای گروه‌بندی و چیدمان کامپوننت‌های دیگر استفاده می‌شود. به خودی خود دیده نمی‌شود، مگر اینکه به آن استایل (مانند پس‌زمینه یا حاشیه) بدهید. `<View>` بستر اصلی برای پیاده‌سازی **Flexbox** است که یک سیستم قدرتمند برای چیدمان عناصر در رابط کاربری است.

**مثال:**

```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text>این یک متن داخل یک View است.</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

### ۳-۲ تنها راه نمایش متن - `<Text>`:

یک قانون بسیار مهم در React Native این است که **تمام متن‌ها باید داخل یک کامپوننت `<Text>` قرار بگیرند**. شما نمی‌توانید متن را مستقیماً داخل یک `<View>` یا هر کامپوننت دیگری بنویسید.

*   **معادل وب:** در وب، `<Text>` می‌تواند معادل تگ‌هایی مانند `<p>`, `<span>`, `<h1>` و غیره باشد.
*   **ویژگی:** کامپوننت‌های `<Text>` می‌توانند **داخل هم قرار بگیرند (Nest شوند)** و استایل‌ها را از والد خود به ارث ببرند. این ویژگی برای اعمال استایل‌های متفاوت به بخش‌های مختلف یک جمله مفید است.

**مثال:**

```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text style={styles.baseText}>
        سلام، {' '}
        <Text style={styles.innerText}>این متن برجسته است!</Text>
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  baseText: {
    fontSize: 18,
    color: 'black',
  },
  innerText: {
    fontWeight: 'bold',
    color: 'red',
  },
});
```

### ۳-۳ نمایش تصاویر - `<Image>`:

کامپوننت `<Image>` برای نمایش انواع تصاویر در اپلیکیشن شما استفاده می‌شود.

*   **پراپ اصلی: `source`**. این پراپ مسیر یا URL تصویر را مشخص می‌کند.

*   **تصاویر محلی:** برای تصاویری که در پوشه پروژه شما قرار دارند (مثلاً در `assets/images`)، باید از تابع `require` استفاده کنید. این کار به باندلر (Metro) کمک می‌کند تا عکس را در بسته نهایی اپلیکیشن قرار دهد و در زمان کامپایل، آن را مدیریت کند.

    ```jsx
    <Image source={require('./assets/images/logo.png')} />
    ```

*   **تصاویر اینترنتی:** برای عکس‌هایی که از یک URL بارگذاری می‌شوند، باید از یک آبجکت با کلید `uri` در پراپ `source` استفاده کنید. **حتماً** باید `width` و `height` را در استایل مشخص کنید، در غیر این صورت تصویر نمایش داده نخواهد شد.

    ```jsx
    <Image
      source={{ uri: 'https://reactnative.dev/img/tiny_logo.png' }}
      style={{ width: 50, height: 50 }}
    />
    ```

**مثال کامل:**

```jsx
import React from 'react';
import { View, Image, StyleSheet } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text>تصویر محلی:</Text>
      <Image source={require('./assets/icon.png')} style={styles.localImage} />

      <Text>تصویر اینترنتی:</Text>
      <Image
        source={{ uri: 'https://reactnative.dev/img/tiny_logo.png' }}
        style={styles.webImage}
      />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    gap: 20, // فاصله بین آیتم ها
  },
  localImage: {
    width: 100,
    height: 100,
    resizeMode: 'contain', // نحوه نمایش تصویر
  },
  webImage: {
    width: 150,
    height: 150,
  },
});
```

### ۳-۴ دریافت ورودی از کاربر - `<TextInput>`:

کامپوننت `<TextInput>` برای ساختن فیلدهای ورودی متن استفاده می‌شود و به کاربر امکان می‌دهد تا متن را وارد کند.

*   **معادل وب:** این کامپوننت معادل تگ `<input type="text">` در وب است.

*   **مهم‌ترین پراپ‌ها:**
    *   `value`: برای **کنترل مقدار ورودی** از طریق `state` در React استفاده می‌شود. این باعث می‌شود `TextInput` یک "کامپوننت کنترل‌شده" باشد.
    *   `onChangeText`: تابعی که با **هر تغییر** در متن ورودی توسط کاربر فراخوانی می‌شود. این تابع معمولاً برای به‌روزرسانی `state` مربوط به مقدار ورودی استفاده می‌شود.
    *   `placeholder`: برای نمایش **متن جایگزین** (Hint text) در فیلد ورودی زمانی که خالی است، استفاده می‌شود.
    *   `keyboardType`: برای تعیین **نوع کیبورد** مجازی که برای کاربر نمایش داده می‌شود. برای مثال، `numeric` برای ورودی‌های عددی یا `email-address` برای آدرس ایمیل.
    *   `secureTextEntry`: یک مقدار `boolean` است که اگر `true` باشد، متن وارد شده را مخفی می‌کند (مانند فیلدهای رمز عبور).

**مثال:**

```jsx
import React, { useState } from 'react';
import { View, TextInput, StyleSheet } from 'react-native';

export default function App() {
  const [name, setName] = useState('');
  const [password, setPassword] = useState('');

  return (
    <View style={styles.container}>
      <TextInput
        style={styles.input}
        onChangeText={setName}
        value={name}
        placeholder="نام کاربری"
      />
      <TextInput
        style={styles.input}
        onChangeText={setPassword}
        value={password}
        placeholder="رمز عبور"
        secureTextEntry // برای فیلد رمز عبور
        keyboardType="default" // نوع کیبورد پیش فرض
      />
      <TextInput
        style={styles.input}
        placeholder="شماره تلفن"
        keyboardType="numeric" // کیبورد عددی
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
  input: {
    height: 40,
    width: '80%',
    borderColor: 'gray',
    borderWidth: 1,
    paddingHorizontal: 10,
    borderRadius: 5,
  },
});
```

---

## فصل ۴: آجرهای ساختمان: کامپوننت‌های اصلی (بخش دوم)

در این فصل، با دیگر کامپوننت‌های اصلی React Native که برای ساخت یک اپلیکیشن کامل و تعاملی نیاز دارید، آشنا می‌شویم. این کامپوننت‌ها امکاناتی از جمله تعاملات لمسی، نمایش محتوای موقت، و کنترل وضعیت‌های مختلف را فراهم می‌کنند.

### ۴-۱ تعامل‌پذیری کامل - `<Pressable>`:

کامپوننت `<Pressable>` مدرن‌ترین و اصلی‌ترین راه برای مدیریت هر نوع تعامل لمسی در React Native است. `<Pressable>` به عنوان یک "لفافه" (Wrapper) عمل می‌کند؛ هر چیزی را که داخل آن قرار دهید، قابل کلیک و تعامل لمسی می‌شود.

*   **پراپ‌های اصلی:**
    *   `onPress`: تابعی که هنگام یک **کلیک کوتاه** یا ضربه زدن فراخوانی می‌شود.
    *   `onLongPress`: تابعی که هنگام **فشردن طولانی** یک عنصر فراخوانی می‌شود.

*   **قابلیت کلیدی:** یکی از ویژگی‌های قدرتمند `<Pressable>` این است که می‌توانید به پراپ `style` آن یک **تابع** بدهید. این تابع یک آبجکت شامل وضعیت `pressed` را دریافت می‌کند (`(style={({ pressed }) => ...})`) و به شما اجازه می‌دهد تا بر اساس وضعیت فشرده شدن، استایل کامپوننت را به صورت **داینامیک تغییر دهید**. این ویژگی برای ایجاد دکمه‌هایی با بازخورد بصری هنگام لمس بسیار مفید است.

**مثال:**

```jsx
import React from 'react';
import { Pressable, Text, StyleSheet } from 'react-native';

export default function CustomButton({ onPress, title }) {
  return (
    <Pressable
      onPress={onPress}
      style={({ pressed }) => [
        styles.button,
        pressed ? styles.buttonPressed : {},
      ]}
    >
      <Text style={styles.buttonText}>{title}</Text>
    </Pressable>
  );
}

const styles = StyleSheet.create({
  button: {
    backgroundColor: '#007bff',
    padding: 10,
    borderRadius: 5,
    alignItems: 'center',
    marginVertical: 10,
  },
  buttonPressed: {
    backgroundColor: '#0056b3', // رنگ تیره تر هنگام فشرده شدن
  },
  buttonText: {
    color: 'white',
    fontSize: 16,
    fontWeight: 'bold',
  },
});
```

### ۴-۲ دکمه ساده نیتیو - `<Button>`:

کامپوننت `<Button>` یک دکمه استاندارد سیستم‌عامل را نمایش می‌دهد.

*   **تفاوت اصلی با `<Pressable>`:** ظاهر `<Button>` کاملاً **بومی** است و **قابلیت استایل‌دهی بسیار محدودی** دارد. ظاهر آن در iOS و Android متفاوت خواهد بود و شما نمی‌توانید استایل‌های پیچیده‌ای روی آن اعمال کنید.
*   **پراپ‌های اصلی:** `title` (برای متن دکمه)، `onPress` (برای تابع کلیک)، و `color` (برای تغییر رنگ دکمه، در اندروید رنگ پس‌زمینه و در iOS رنگ متن).
*   **چه زمانی استفاده کنیم؟** `<Button>` برای کارهای سریع و موقتی مانند دکمه‌های داخل یک `Alert` یا برای نمونه‌سازی اولیه سریع مناسب است. برای ساخت دکمه‌های اصلی اپلیکیشن که نیاز به ظاهر سفارشی و یکپارچه در سراسر اپلیکیشن دارند، تقریباً همیشه از **`<Pressable>`** استفاده می‌شود.

**مثال:**

```jsx
import React from 'react';
import { View, Button, Alert, StyleSheet } from 'react-native';

export default function App() {
  const handlePress = () => {
    Alert.alert('دکمه فشار داده شد!');
  };

  return (
    <View style={styles.container}>
      <Button
        title="دکمه استاندارد"
        onPress={handlePress}
        color="#841584" // رنگ دکمه
      />
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

### ۴-۳ نمایش محتوا روی صفحه - `<Modal>`:

کامپوننت `<Modal>` برای نمایش محتوا به صورت موقت و **روی نمای اصلی اپلیکیشن** استفاده می‌شود. این کامپوننت معمولاً برای نمایش دیالوگ‌های پاپ‌آپ، فرم‌های موقت یا پیام‌های تأیید کاربرد دارد.

*   **پراپ‌های اصلی:**
    *   `visible`: یک مقدار **`boolean`** که نمایش یا عدم نمایش Modal را کنترل می‌کند. اگر `true` باشد، مودال نمایش داده می‌شود.
    *   `animationType`: نوع انیمیشن ورود مودال را مشخص می‌کند. مقادیر ممکن `'slide'` (از پایین به بالا)، `'fade'` (محو شدن) یا `'none'` (بدون انیمیشن) هستند.
    *   `onRequestClose`: این تابع برای **پشتیبانی از دکمه بازگشت در اندروید** ضروری است. با فشردن دکمه بازگشت سخت‌افزاری، این تابع فراخوانی می‌شود و شما می‌توانید با به‌روزرسانی وضعیت `visible`، مودال را ببندید.

**مثال:**

```jsx
import React, { useState } from 'react';
import { View, Text, Button, Modal, StyleSheet } from 'react-native';

export default function App() {
  const [modalVisible, setModalVisible] = useState(false);

  return (
    <View style={styles.container}>
      <Text>صفحه اصلی اپلیکیشن</Text>
      <Button title="نمایش Modal" onPress={() => setModalVisible(true)} />

      <Modal
        animationType="slide" // انیمیشن ورود از پایین
        transparent={true} // پس زمینه شفاف
        visible={modalVisible}
        onRequestClose={() => {
          // برای پشتیبانی از دکمه بازگشت در اندروید
          setModalVisible(!modalVisible);
        }}
      >
        <View style={styles.centeredView}>
          <View style={styles.modalView}>
            <Text style={styles.modalText}>این یک پنجره Modal است!</Text>
            <Button title="بستن Modal" onPress={() => setModalVisible(false)} />
          </View>
        </View>
      </Modal>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  centeredView: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    marginTop: 22,
    backgroundColor: 'rgba(0,0,0,0.5)', // پس زمینه نیمه شفاف
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
  },
});
```

### ۴-۴ کنترل نوار وضعیت - `<StatusBar>`:

کامپوننت `<StatusBar>` به شما اجازه می‌دهد تا **نوار وضعیت بالای صفحه** (جایی که ساعت، وضعیت باتری و آیکون‌های اعلان نمایش داده می‌شود) را کنترل کنید.

*   **پراپ‌های اصلی:**
    *   `barStyle`: رنگ متن و آیکون‌ها در نوار وضعیت را تعیین می‌کند. مقادیر ممکن عبارتند از:
        *   `'default'`
        *   `'light-content'` (مناسب برای پس‌زمینه‌های تیره نوار وضعیت)
        *   `'dark-content'` (مناسب برای پس‌زمینه‌های روشن نوار وضعیت)
    *   `backgroundColor`: رنگ پس‌زمینه نوار وضعیت را تعیین می‌کند. **این پراپ فقط در اندروید کار می‌کند**.
    *   `hidden`: یک مقدار `boolean` که برای **مخفی کردن نوار وضعیت** استفاده می‌شود.

**مثال:**

```jsx
import React, { useState } from 'react';
import { View, StatusBar, Button, StyleSheet } from 'react-native';

export default function App() {
  const [hidden, setHidden] = useState(false);
  const [statusBarStyle, setStatusBarStyle] = useState('dark-content');
  const [statusBarBackgroundColor, setStatusBarBackgroundColor] = useState('#F0F0F0');

  const changeBarStyle = () => {
    setStatusBarStyle(
      statusBarStyle === 'dark-content' ? 'light-content' : 'dark-content'
    );
  };

  const changeBackgroundColor = () => {
    setStatusBarBackgroundColor(
      statusBarBackgroundColor === '#F0F0F0' ? '#333333' : '#F0F0F0'
    );
  };

  return (
    <View style={styles.container}>
      <StatusBar
        animated={true} // انیمیشن برای تغییرات
        backgroundColor={statusBarBackgroundColor} // فقط اندروید
        barStyle={statusBarStyle}
        hidden={hidden}
      />
      <Text>وضعیت نوار وضعیت</Text>
      <Button title="تغییر Style" onPress={changeBarStyle} />
      <Button title="تغییر پس زمینه (اندروید)" onPress={changeBackgroundColor} />
      <Button title="مخفی/نمایش نوار" onPress={() => setHidden(!hidden)} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    gap: 15,
  },
});
```

### ۴-۵ کلید دو حالته - `<Switch>`:

کامپوننت `<Switch>` یک کلید روشن/خاموش استاندارد نیتیو را نمایش می‌دهد. این کامپوننت معمولاً برای تنظیمات کاربری یا فعال/غیرفعال کردن قابلیت‌ها استفاده می‌شود.

*   **پراپ‌های اصلی:**
    *   `value`: یک مقدار `boolean` که **وضعیت فعلی کلید** (روشن یا خاموش) را مشخص می‌کند.
    *   `onValueChange`: تابعی که با **تغییر وضعیت کلید توسط کاربر** فراخوانی می‌شود. این تابع مقدار جدید `boolean` کلید را به عنوان آرگومان دریافت می‌کند و شما باید از آن برای به‌روزرسانی `state` مربوطه استفاده کنید.

**مثال:**

```jsx
import React, { useState } from 'react';
import { View, Text, Switch, StyleSheet } from 'react-native';

export default function App() {
  const [isEnabled, setIsEnabled] = useState(false);
  const toggleSwitch = () => setIsEnabled(previousState => !previousState);

  return (
    <View style={styles.container}>
      <Text>فعال کردن قابلیت:</Text>
      <Switch
        trackColor={{ false: '#767577', true: '#81b0ff' }}
        thumbColor={isEnabled ? '#f5dd4b' : '#f4f3f4'}
        ios_backgroundColor="#3e3e3e"
        onValueChange={toggleSwitch}
        value={isEnabled}
      />
      <Text>وضعیت: {isEnabled ? 'فعال' : 'غیرفعال'}</Text>
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

### ۴-۶ هشدار - `Alert` API:

یک کامپوننت React Native نیست، بلکه یک **API** است. این API به شما اجازه می‌دهد تا یک دیالوگ هشدار استاندارد سیستم‌عامل را نمایش دهید. این دیالوگ‌ها برای نمایش پیام‌های مهم، درخواست تأیید کاربر یا نمایش خطاها مناسب هستند.

شما تابع `Alert.alert(title, message, buttons)` را فراخوانی می‌کنید.

*   `title`: عنوان دیالوگ.
*   `message`: پیام اصلی دیالوگ.
*   `buttons`: (اختیاری) آرایه‌ای از آبجکت‌ها برای تعریف دکمه‌ها. هر آبجکت دکمه می‌تواند شامل `text`، `onPress` (تابعی که با کلیک روی دکمه اجرا می‌شود) و `style` (مثلاً `'cancel'` یا `'destructive'`) باشد.

**مثال:**

```jsx
import React from 'react';
import { View, Button, Alert, StyleSheet } from 'react-native';

export default function App() {
  const showAlert = () => {
    Alert.alert(
      'حذف آیتم',
      'آیا مطمئن هستید که می‌خواهید این آیتم را حذف کنید؟',
      [
        {
          text: 'لغو',
          onPress: () => console.log('عملیات حذف لغو شد'),
          style: 'cancel', // دکمه لغو
        },
        {
          text: 'حذف',
          onPress: () => console.log('آیتم با موفقیت حذف شد'),
          style: 'destructive', // دکمه تخریب گر (قرمز)
        },
      ],
      { cancelable: false } // آیا با کلیک بیرون از دیالوگ بسته شود؟
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

در این فصل، به قلب طراحی رابط کاربری در React Native می‌رویم و تکنیک‌های پیشرفته‌تری را برای ساخت UIهای زیبا و واکنش‌گرا (Responsive) یاد می‌گیریم. تسلط بر این مفاهیم برای ساخت اپلیکیشن‌هایی که در اندازه‌ها و جهت‌گیری‌های مختلف صفحه نمایش به خوبی کار می‌کنند، ضروری است.

### ۵-۱: موقعیت‌یابی مطلق (Absolute Positioning)

به طور پیش‌فرض، تمام کامپوننت‌ها در React Native دارای `position: 'relative'` هستند. این بدان معناست که آن‌ها در جریان عادی چیدمان (Flow Layout) قرار می‌گیرند و نسبت به موقعیت خودشان جابجا می‌شوند.

اما گاهی اوقات شما نیاز دارید که یک عنصر را **روی** عناصر دیگر قرار دهید، به گونه‌ای که از جریان عادی چیدمان خارج شود. به عنوان مثال، قرار دادن یک نشان تعداد اعلان (Badge) روی یک آیکون. در این مواقع، از `position: 'absolute'` استفاده می‌کنیم. عنصری که این استایل را دارد، نسبت به نزدیک‌ترین والد خود که `position` آن `relative` (که پیش‌فرض است) یا `absolute` باشد، موقعیت‌یابی می‌شود.

**مثال:**

```jsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <View style={styles.card}>
        <Text style={styles.cardText}>کارت اصلی</Text>
        <View style={styles.badge}>
          <Text style={styles.badgeText}>3</Text>
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
  },
  card: {
    width: 200,
    height: 100,
    backgroundColor: '#f0f0f0',
    borderRadius: 10,
    justifyContent: 'center',
    alignItems: 'center',
    // position: 'relative' به طور پیش فرض وجود دارد
  },
  cardText: {
    fontSize: 20,
    fontWeight: 'bold',
  },
  badge: {
    position: 'absolute', // موقعیت یابی مطلق
    top: -10, // 10 پیکسل بالاتر از لبه بالایی والد
    right: -10, // 10 پیکسل سمت راست لبه والد
    backgroundColor: 'red',
    borderRadius: 15,
    width: 30,
    height: 30,
    justifyContent: 'center',
    alignItems: 'center',
  },
  badgeText: {
    color: 'white',
    fontSize: 14,
    fontWeight: 'bold',
  },
});
```

### ۵-۲: استایل‌دهی ریسپانسیو

ساخت UI که روی اندازه‌های مختلف صفحه (گوشی‌های کوچک، تبلت‌ها، حالت افقی و عمودی) خوب به نظر برسد، ترکیبی از چند تکنیک مهم است:

1.  **Flexbox:**:
2.  این ابزار، **بهترین ابزار شما برای چیدمان ریسپانسیو** است. با استفاده از `flex: 1` به کامپوننت‌ها اجازه می‌دهید فضای موجود را پر کنند و به صورت انعطاف‌پذیر گسترش یابند. با پراپ‌های `justifyContent` (توزیع فضا در جهت اصلی) و `alignItems` (توزیع فضا در جهت متقاطع) نیز می‌توانید توزیع فضا و تراز کردن عناصر را به دقت مدیریت کنید.

    **مثال (Flexbox):**

    ```jsx
    <View style={{ flex: 1, flexDirection: 'row', justifyContent: 'space-around', alignItems: 'center' }}>
      <View style={{ width: 50, height: 50, backgroundColor: 'red' }} />
      <View style={{ width: 50, height: 50, backgroundColor: 'green' }} />
      <View style={{ width: 50, height: 50, backgroundColor: 'blue' }} />
    </View>
    ```

3.  **درصد (%):** می‌توانید برای پراپ‌هایی مانند `width` و `height` از مقادیر **درصدی** استفاده کنید. این کار باعث می‌شود اندازه یک عنصر همیشه نسبتی از اندازه والدش باشد و با تغییر اندازه والد، اندازه آن نیز متناسباً تغییر کند.

    **مثال (درصد):**

    ```jsx
    <View style={{ width: '100%', height: '50%', backgroundColor: 'lightblue' }}>
      <Text>این View نیمی از ارتفاع والد خود را اشغال می‌کند.</Text>
    </View>
    ```

4.  **`useWindowDimensions`:**
 این **هوک** (Hook) ابعاد فعلی صفحه نمایش (عرض و ارتفاع) را به شما می‌دهد. می‌توانید از آن برای تصمیم‌گیری‌های بزرگ در چیدمان استفاده کنید. به عنوان مثال، اگر عرض صفحه از یک مقدار مشخص (مثلاً ۶۰۰ پیکسل برای تبلت) بیشتر بود، یک لیست را به جای تک ستونه، دو ستونه نمایش دهید.

    **مثال (`useWindowDimensions`):**

    ```jsx
    import React from 'react';
    import { View, Text, StyleSheet, useWindowDimensions } from 'react-native';

    export default function App() {
      const { width, height } = useWindowDimensions();

      const isLargeScreen = width > 600;

      return (
        <View style={styles.container}>
          <Text style={styles.text}>عرض صفحه: {width.toFixed(0)}px</Text>
          <Text style={styles.text}>ارتفاع صفحه: {height.toFixed(0)}px</Text>
          {isLargeScreen ? (
            <Text style={styles.largeScreenText}>
              این یک صفحه نمایش بزرگ است!
            </Text>
          ) : (
            <Text style={styles.smallScreenText}>
              این یک صفحه نمایش کوچک است.
            </Text>
          )}
        </View>
      );
    }

    const styles = StyleSheet.create({
      container: {
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
      },
      text: {
        fontSize: 18,
        marginVertical: 5,
      },
      largeScreenText: {
        fontSize: 24,
        color: 'green',
        marginTop: 20,
      },
      smallScreenText: {
        fontSize: 16,
        color: 'red',
        marginTop: 20,
      },
    });
    ```

### ۵-۳: کدنویسی مختص پلتفرم

گاهی اوقات، لازم است که ظاهر یا رفتار اپلیکیشن شما در iOS و Android متفاوت باشد، زیرا هر پلتفرم دستورالعمل‌های طراحی خاص خود را دارد. React Native ابزارهایی برای مدیریت این تفاوت‌ها ارائه می‌دهد:

1.  **ماژول `Platform`:** این ماژول به شما اجازه می‌دهد در لحظه چک کنید که کد شما روی کدام سیستم‌عامل در حال اجراست.
    *   `Platform.OS`: یک رشته `'ios'` یا `'android'` را برمی‌گرداند.
    *   `Platform.select()`: **تمیزترین و توصیه شده‌ترین راه** برای تعریف استایل‌ها یا مقادیر متفاوت بر اساس پلتفرم است. این تابع یک آبجکت دریافت می‌کند که کلیدهای آن نام پلتفرم‌ها (مثلاً `ios`, `android`) و مقادیر آن‌ها استایل‌ها یا مقادیر مورد نظر هستند.

    **مثال (`Platform.select()`):**

    ```javascript
    import { StyleSheet, Platform } from 'react-native';

    const styles = StyleSheet.create({
      card: {
        backgroundColor: 'white',
        borderRadius: 8,
        padding: 16,
        margin: 10,
        // استایل های متفاوت بر اساس پلتفرم
        ...Platform.select({
          ios: {
            shadowColor: '#000',
            shadowOffset: { width: 0, height: 2 },
            shadowOpacity: 0.1,
            shadowRadius: 3,
          },
          android: {
            elevation: 3, // سایه در اندروید
          },
        }),
      },
      text: {
        fontSize: Platform.OS === 'ios' ? 18 : 16, // اندازه فونت متفاوت
        color: Platform.OS === 'android' ? 'darkblue' : 'purple', // رنگ متن متفاوت
      },
    });
    ```
    همانطور که در مثال بالا مشاهده می‌کنید، می‌توانیم از `Platform.select()` برای ادغام استایل‌های مخصوص پلتفرم در یک شیء استایل استفاده کنیم. همچنین می‌توانیم از `Platform.OS` به صورت شرطی برای تغییر مقادیر خاص استفاده کنیم.

2.  **پسوندهای فایل (File Extensions):** برای تفاوت‌های بزرگتر در کامپوننت‌ها یا منطق، می‌توانید دو فایل جداگانه بسازید. برای مثال:
    *   `MyComponent.ios.js` (فقط برای iOS)
    *   `MyComponent.android.js` (فقط برای Android)
    باندلر React Native (Metro) به صورت هوشمند و خودکار فایل صحیح را بر اساس پلتفرم در حال اجرا انتخاب و بارگذاری می‌کند. این رویکرد به شما اجازه می‌دهد تا بخش‌های بزرگی از UI یا منطق را به طور کامل برای هر پلتفرم بهینه کنید.

---

## فصل ۶: نمایش لیست‌های بهینه

نمایش لیست‌های داده یکی از رایج‌ترین و حیاتی‌ترین کارها در توسعه اپلیکیشن‌های موبایل است. در این فصل، با سه کامپوننت اصلی برای نمایش لیست‌ها آشنا می‌شویم و یاد می‌گیریم که چگونه لیست‌های بلند را به صورت بهینه رندر کنیم تا عملکرد اپلیکیشن شما روان باقی بماند.

### ۶-۱: `<ScrollView>`

کامپوننت `<ScrollView>` یک کانتینر اسکرول ساده است. هر چیزی که داخل آن قرار دهید، اگر از فضای موجود بزرگ‌تر باشد، قابل اسکرول خواهد شد.

*   **نقطه ضعف بزرگ:** `ScrollView` تمام کامپوننت‌های فرزند خود را **یکجا رندر می‌کند**. این بدان معناست که حتی اگر آیتمی خارج از صفحه باشد و کاربر آن را نبیند، باز هم در حافظه رندر شده و فضای زیادی را اشغال می‌کند. این ویژگی باعث می‌شود برای لیست‌های **بلند** (با تعداد زیادی آیتم)، مصرف حافظه بالا رفته و اپلیکیشن **کند** شود.

*   **کاربرد:** `ScrollView` برای صفحاتی با **تعداد محدودی آیتم** یا محتوای متنی بلند (مانند یک مقاله یا صفحه تنظیمات) که حجم داده زیادی ندارند، مناسب است.

**مثال:**

```jsx
import React from 'react';
import { ScrollView, Text, StyleSheet } from 'react-native';

export default function App() {
  const items = Array.from({ length: 20 }, (_, i) => `آیتم شماره ${i + 1}`);

  return (
    <ScrollView style={styles.container}>
      {items.map((item, index) => (
        <Text key={index} style={styles.item}>
          {item}
        </Text>
      ))}
    </ScrollView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    paddingTop: 50,
  },
  item: {
    padding: 20,
    fontSize: 18,
    borderBottomWidth: 1,
    borderBottomColor: '#ccc',
  },
});
```

### ۶-۲: `<FlatList>` (انتخاب استاندارد)

کامپوننت `<FlatList>` اصلی‌ترین و **بهینه‌ترین** کامپوننت برای نمایش **لیست‌های بلند و پویا** از داده‌ها است.

*   **قابلیت کلیدی: مجازی‌سازی (Virtualization).** `<FlatList>` به صورت هوشمند عمل می‌کند و **فقط آیتم‌هایی را رندر می‌کند که در حال حاضر روی صفحه قابل مشاهده هستند** (یا نزدیک به آن‌ها هستند). هنگامی که کاربر اسکرول می‌کند، آیتم‌های قدیمی از حافظه حذف شده و آیتم‌های جدید رندر می‌شوند. این کار عملکرد را فوق‌العاده بالا می‌برد و مصرف حافظه را بهینه می‌کند.

*   **پراپ‌های ضروری:**
    *   `data`: **آرایه‌ای از داده‌ها** که قرار است در لیست نمایش داده شوند.
    *   `renderItem`: یک **تابع** که یک آیتم از آرایه `data` را به عنوان ورودی (`{ item, index }`) دریافت کرده و **کامپوننت مربوط به آن آیتم** را برمی‌گرداند. این تابع مسئول نمایش هر ردیف در لیست است.
    *   `keyExtractor`: یک **تابع** که یک **کلید (key) منحصر به فرد و از نوع رشته** برای هر آیتم در لیست برمی‌گرداند. React از این کلیدها برای شناسایی آیتم‌ها در طول تغییرات (اضافه شدن، حذف شدن، تغییر ترتیب) استفاده می‌کند و برای عملکرد و جلوگیری از باگ‌ها حیاتی است.

**مثال:**

```jsx
import React from 'react';
import { FlatList, Text, StyleSheet, View } from 'react-native';

export default function App() {
  const users = [
    { id: '1', name: 'علی' },
    { id: '2', name: 'سارا' },
    { id: '3', name: 'رضا' },
    { id: '4', name: 'مریم' },
    { id: '5', name: 'حسن' },
    { id: '6', name: 'فاطمه' },
    { id: '7', name: 'مهدی' },
    { id: '8', name: 'نازنین' },
    { id: '9', name: 'جواد' },
    { id: '10', name: 'لیلا' },
    { id: '11', name: 'امیر' },
    { id: '12', name: 'زینب' },
    { id: '13', name: 'کوروش' },
    { id: '14', name: 'شبنم' },
    { id: '15', name: 'پویا' },
  ];

  const renderUserItem = ({ item }) => (
    <View style={styles.item}>
      <Text style={styles.title}>{item.name}</Text>
    </View>
  );

  return (
    <FlatList
      data={users}
      renderItem={renderUserItem}
      keyExtractor={item => item.id} // استفاده از ID به عنوان کلید منحصر به فرد
      style={styles.list}
    />
  );
}

const styles = StyleSheet.create({
  list: {
    flex: 1,
    marginTop: 50,
  },
  item: {
    backgroundColor: '#f9c2ff',
    padding: 20,
    marginVertical: 8,
    marginHorizontal: 16,
    borderRadius: 8,
  },
  title: {
    fontSize: 24,
  },
});
```

### ۶-۳: `<SectionList>`

کامپوننت `<SectionList>` برای نمایش داده‌هایی است که به صورت **بخش‌بندی شده** یا گروه‌بندی شده هستند. مثال بارز آن، لیست مخاطبین است که بر اساس حروف الفبا (A, B, C و...) گروه‌بندی شده‌اند.

*   **پراپ‌های اصلی:**
    *   `sections`: **آرایه‌ای از آبجکت‌ها** است. هر آبجکت در این آرایه نشان‌دهنده یک بخش است و شامل یک `title` (عنوان بخش) و یک آرایه `data` (آیتم‌های آن بخش) می‌باشد.
    *   `renderItem`: تابعی برای **رندر هر آیتم** در یک بخش. مشابه `FlatList` عمل می‌کند.
    *   `renderSectionHeader`: تابعی برای **رندر کردن هدر هر بخش** (مثلاً حرف 'A' برای بخش "آ"). این تابع یک آبجکت شامل `section` (که حاوی `title` آن بخش است) را دریافت می‌کند.

**مثال:**

```jsx
import React from 'react';
import { SectionList, Text, View, StyleSheet } from 'react-native';

export default function App() {
  const DATA = [
    {
      title: 'میوه‌ها',
      data: ['سیب', 'موز', 'پرتقال'],
    },
    {
      title: 'سبزیجات',
      data: ['هویج', 'کاهو', 'گوجه'],
    },
    {
      title: 'لبنیات',
      data: ['شیر', 'پنیر', 'ماست'],
    },
  ];

  return (
    <SectionList
      sections={DATA}
      keyExtractor={(item, index) => item + index}
      renderItem={({ item }) => (
        <View style={styles.item}>
          <Text style={styles.title}>{item}</Text>
        </View>
      )}
      renderSectionHeader={({ section: { title } }) => (
        <Text style={styles.header}>{title}</Text>
      )}
      style={styles.list}
    />
  );
}

const styles = StyleSheet.create({
  list: {
    flex: 1,
    marginTop: 50,
  },
  item: {
    backgroundColor: '#f9c2ff',
    padding: 20,
    marginVertical: 8,
    marginHorizontal: 16,
    borderRadius: 8,
  },
  header: {
    fontSize: 32,
    backgroundColor: '#fff',
    padding: 10,
    fontWeight: 'bold',
  },
  title: {
    fontSize: 24,
  },
});
```

---

## فصل ۷: هویت بصری: فونت و صفحه اسپلش

در این فصل، دو ابزار مهم برای کنترل هویت بصری و تجربه اولیه کاربری اپلیکیشن خود را یاد می‌گیریم. استفاده از فونت‌های سفارشی می‌تواند برند شما را تقویت کند، و مدیریت صفحه اسپلش تجربه کاربری را هنگام بارگذاری اولیه بهبود می‌بخشد.

### ۷-۱: کار با فونت‌های سفارشی (`useFonts`)

برای استفاده از فونت‌های اختصاصی (Custom Fonts) در پروژه React Native و Expo، از هوک `useFonts` که از کتابخانه `expo-font` می‌آید، استفاده می‌کنیم. این هوک به ما اجازه می‌دهد فونت‌ها را قبل از استفاده، به صورت **غیرهمزمان (asynchronously)** بارگذاری کنیم تا از پدیده "پرش متن" (Flash Of Unstyled Text - FOUT) جلوگیری شود.

*   **فرآیند استفاده:**
    1.  **نصب کتابخانه:** ابتدا کتابخانه `expo-font` را نصب کنید:
        ```bash
        npx expo install expo-font
        ```
    2.  **قرار دادن فایل‌های فونت:** فایل‌های فونت خود (`.ttf` یا `.otf`) را در یک پوشه مناسب داخل پروژه خود، معمولاً `assets/fonts/`، قرار دهید.
    3.  **بارگذاری فونت‌ها با `useFonts`:** در کامپوننت اصلی اپلیکیشن خود (معمولاً `App.js` یا `app/_layout.tsx` در پروژه‌های Expo Router)، هوک `useFonts` را فراخوانی کنید. این هوک یک آبجکت دریافت می‌کند که نام‌هایی که می‌خواهید برای فونت‌ها استفاده کنید را به مسیر فایل آن‌ها نگاشت می‌کند. این هوک یک آرایه دو عنصری برمی‌گرداند: یک مقدار بولی (`fontsLoaded`) که نشان می‌دهد آیا فونت‌ها بارگذاری شده‌اند یا خیر، و یک تابع `fontError`.
    4.  **توقف رندر تا بارگذاری کامل:** تا زمانی که فونت‌ها به طور کامل بارگذاری نشده‌اند (`fontsLoaded` برابر `false` است)، رندر اپلیکیشن را متوقف کنید. معمولاً با برگرداندن `null` یا یک صفحه بارگذاری ساده این کار انجام می‌شود.
    5.  **استفاده از فونت:** پس از بارگذاری موفق، می‌توانید نام تعریف شده برای فونت را در پراپ `fontFamily` در استایل‌های خود استفاده کنید.

**نکته مهم:** بارگذاری فونت به تنهایی آن را به کل برنامه اعمال **نمی‌کند**. شما باید به صراحت در استایل‌ها (مثلاً برای `<Text>`) از آن استفاده کنید.

**مثال:**

```jsx
// app/_layout.tsx یا App.js
import { Stack } from 'expo-router'; // اگر از Expo Router استفاده می‌کنید
import { useFonts } from 'expo-font';
import { useEffect, useCallback } from 'react';
import * as SplashScreen from 'expo-splash-screen'; // برای مدیریت صفحه اسپلش

// از بسته شدن خودکار صفحه اسپلش جلوگیری کنید
SplashScreen.preventAutoHideAsync(); //

export default function RootLayout() {
  const [fontsLoaded, fontError] = useFonts({
    'Inter-Black': require('./assets/fonts/Inter-Black.ttf'),
    'CustomFont-Bold': require('./assets/fonts/CustomFont-Bold.ttf'), // مثال: فرض کنید این فونت در assets/fonts موجود است
  }); //

  const onLayoutRootView = useCallback(async () => {
    if (fontsLoaded || fontError) {
      await SplashScreen.hideAsync(); // پنهان کردن صفحه اسپلش پس از بارگذاری فونت ها
    }
  }, [fontsLoaded, fontError]);

  if (!fontsLoaded && !fontError) {
    return null; // نمایش ندادن چیزی تا بارگذاری کامل فونت ها
  }

  // اگر از Expo Router استفاده می کنید:
  return (
    <Stack onLayout={onLayoutRootView}>
      {/* صفحات شما */}
    </Stack>
  );
  // اگر از React Navigation استفاده می کنید:
  // return (
  //   <View style={{ flex: 1 }} onLayout={onLayoutRootView}>
  //     <Text style={{ fontFamily: 'CustomFont-Bold', fontSize: 24 }}>
  //       این متن با فونت سفارشی است.
  //     </Text>
  //   </View>
  // );
}

// مثال استفاده از فونت در یک کامپوننت دیگر:
// import { Text, StyleSheet } from 'react-native';
// const MyComponent = () => {
//   return <Text style={styles.myText}>متن با فونت سفارشی</Text>;
// };
// const styles = StyleSheet.create({
//   myText: {
//     fontFamily: 'CustomFont-Bold', // نامی که در useFonts تعریف کرده بودید
//     fontSize: 20,
//   },
// });
```

### ۷-۲: مدیریت صفحه اسپلش (`expo-splash-screen`)

صفحه اسپلش (Splash Screen) اولین چیزی است که کاربر هنگام باز کردن اپلیکیشن شما می‌بیند. با استفاده از ماژول `expo-splash-screen`، می‌توانیم نمایش این صفحه را کنترل کنیم تا اطمینان حاصل شود که تمام فرآیندهای آماده‌سازی اولیه اپلیکیشن (مانند بارگذاری فونت‌ها یا دریافت تنظیمات اولیه از سرور) به پایان رسیده‌اند و سپس اپلیکیشن به نرمی نمایش داده شود.

*   **گردش کار:**
    1.  **نصب ماژول:**
        ```bash
        npx expo install expo-splash-screen
        ```
    2.  **جلوگیری از بسته شدن خودکار:** در ابتدای برنامه، معمولاً در فایل اصلی (مثلاً `App.js` یا `_layout.tsx`):
        ```javascript
        import * as SplashScreen from 'expo-splash-screen';
        SplashScreen.preventAutoHideAsync(); //
        ```
        این تابع از بسته شدن خودکار صفحه اسپلش قبل از آماده شدن کامل اپلیکیشن جلوگیری می‌کند.
    3.  **پنهان کردن صفحه اسپلش:** پس از اینکه تمام کارهای لازم (مانند بارگذاری فونت‌ها، دریافت داده‌های اولیه) انجام شد و اپلیکیشن آماده نمایش است، تابع `SplashScreen.hideAsync()` را فراخوانی می‌کنیم. این باعث می‌شود صفحه اسپلش به نرمی محو شده و محتوای اصلی اپلیکیشن نمایش داده شود. این کار معمولاً در یک `useEffect` یا با استفاده از `onLayout` کامپوننت ریشه انجام می‌شود.

**مثال (کامل شده با مثال فونت در بالا):**

```jsx
// app/_layout.tsx یا App.js
import { Stack } from 'expo-router';
import { useFonts } from 'expo-font';
import { useEffect, useCallback } from 'react';
import * as SplashScreen from 'expo-splash-screen';

// از بسته شدن خودکار صفحه اسپلش جلوگیری کنید
SplashScreen.preventAutoHideAsync(); //

export default function RootLayout() {
  const [fontsLoaded, fontError] = useFonts({
    'Inter-Black': require('./assets/fonts/Inter-Black.ttf'),
    'CustomFont-Bold': require('./assets/fonts/CustomFont-Bold.ttf'),
  });

  const onLayoutRootView = useCallback(async () => {
    if (fontsLoaded || fontError) {
      // پنهان کردن صفحه اسپلش پس از بارگذاری فونت ها (و هر کار اولیه دیگر)
      await SplashScreen.hideAsync(); //
    }
  }, [fontsLoaded, fontError]);

  if (!fontsLoaded && !fontError) {
    // اگر فونت ها بارگذاری نشده اند، چیزی نمایش نده
    return null;
  }

  return (
    // Stack Navigator برای Expo Router
    <Stack onLayout={onLayoutRootView}>
      {/* صفحات اپلیکیشن شما در اینجا رندر می شوند */}
      <Stack.Screen name="index" options={{ title: 'خانه' }} />
      <Stack.Screen name="settings" options={{ title: 'تنظیمات' }} />
    </Stack>
  );
}
```

---

## فصل ۸: ناوبری مدرن با Expo Router و هوک‌های کاربردی

ناوبری (Navigation) ستون فقرات هر اپلیکیشن موبایل است که به کاربر امکان می‌دهد بین صفحات مختلف جابجا شود. در این فصل، با **Expo Router** آشنا می‌شویم، یک رویکرد نوین برای مدیریت ناوبری در React Native که بر پایه **مسیریابی مبتنی بر فایل** عمل می‌کند و تجربه توسعه را به شدت ساده‌تر می‌سازد.

روتر Expo Router یک لایه هوشمند روی کتابخانه قدرتمند `React Navigation` است که به ما اجازه می‌دهد ناوبری را به صورت فایل‌محور و شبیه به Next.js انجام دهیم.

### ۸-۱: مفاهیم کلیدی Expo Router

*   **مسیریابی مبتنی بر فایل:** اساسی‌ترین مفهوم در Expo Router این است که **هر فایل در پوشه `app/` به صورت خودکار به یک مسیر (Route) در اپلیکیشن تبدیل می‌شود**.
    *   مثال: فایل `app/settings.tsx` به مسیر `/settings` در اپلیکیشن شما تبدیل می‌شود.
    *   `app/index.tsx` به مسیر اصلی `/` تبدیل می‌شود.
    *   پوشه‌ها نیز مسیرهای تو در تو (Nested Routes) ایجاد می‌کنند: `app/users/profile.tsx` به `/users/profile` تبدیل می‌شود.

*   **چیدمان‌ها (`_layout.tsx`):** این فایل یک مفهوم بسیار قدرتمند است. فایل `_layout.tsx` در یک پوشه، **نوع ناوبر (Navigator)** را برای آن پوشه و **تمام زیرشاخه‌هایش** مشخص می‌کند.
    *   `app/_layout.tsx`:
 این فایل، **ناوبر اصلی کل برنامه** را تعریف می‌کند. معمولاً اینجا یک `Stack` Navigator (ناوبر پشته‌ای) یا `Tab` Navigator (ناوبر تب‌دار) تعریف می‌شود.
    *   شما می‌توانید چندین فایل `_layout.tsx` در زیرپوشه‌ها داشته باشید تا بخش‌های مختلف اپلیکیشن، ناوبری خاص خود را داشته باشند.

*   **گروه‌بندی مسیرها (Route Groups):** پوشه‌هایی که نامشان داخل **پرانتز** است (مثلاً `(tabs)`)، در URL نهایی تأثیری ندارند. این پوشه‌ها فقط برای **سازماندهی کد** و **اعمال یک چیدمان (layout) خاص** به گروهی از صفحات استفاده می‌شوند.
    *   مثال: اگر `app/(tabs)/home.tsx` داشته باشید، مسیر آن همچنان `/home` خواهد بود، اما می‌توانید یک `app/(tabs)/_layout.tsx` برای تعریف یک Tab Navigator برای تمام صفحات داخل `(tabs)` داشته باشید.

### ۸-۲: ابزارهای ناوبری: کامپوننت `<Link>`

کامپوننت `<Link>` اصلی‌ترین ابزار شما برای **ناوبری اعلانی (Declarative Navigation)** در React Native است. این کامپوننت به شما اجازه می‌دهد تا با کلیک کاربر، او را به یک صفحه دیگر منتقل کنید.

*   `href`:
 این پراپ مسیر مقصد را مشخص می‌کند. می‌توانید یک رشته ساده (مانند `href="/settings"`) یا یک آبجکت پیچیده‌تر برای ارسال پارامترها (مانند `href={{ pathname: '/user/123', params: { ... } }}`) به آن بدهید.

    **مثال (ارسال پارامتر با `href`):**
    ```jsx
    import { Link } from 'expo-router';
    import { Text } from 'react-native';

    export default function UsersList() {
      return (
        <Link href={{ pathname: '/user/[id]', params: { id: '123' } }}>
          <Text>مشاهده کاربر 123</Text>
        </Link>
      );
    }
    ```

*   `replace`:
 این پراپ یک مقدار `boolean` می‌پذیرد. اگر `true` باشد، صفحه فعلی را از **تاریخچه ناوبری (Navigation Stack)** حذف می‌کند و صفحه جدید را جایگزین آن می‌کند. کاربر دیگر نمی‌تواند با دکمه بازگشت به صفحه قبلی بازگردد. این برای سناریوهایی مانند **بعد از ورود کاربر (Login)** که نمی‌خواهید کاربر بتواند به صفحه ورود برگردد، بسیار مفید است.

    **مثال (`replace`):**
    ```jsx
    import { Link } from 'expo-router';
    import { Text } from 'react-native';

    export default function LoginPage() {
      const handleLogin = () => {
        // ... منطق ورود
        // بعد از ورود موفق:
        return (
          <Link href="/dashboard" replace>
            <Text>ورود به داشبورد</Text>
          </Link>
        );
      };
      // ...
    }
    ```

*   `asChild`:
 این پراپ (که **بسیار مهم** است) به `<Link>` می‌گوید که خودش هیچ UI ای را رندر نکند و **فقط قابلیت ناوبری را به اولین فرزند خود منتقل کند**. این به شما اجازه می‌دهد تا دکمه‌های کاملاً سفارشی، آیکون‌ها یا هر کامپوننت دیگری را بسازید که مانند یک لینک عمل می‌کنند.

    **مثال (`asChild`):**
    ```jsx
    import { Link } from 'expo-router';
    import { Pressable, Text, StyleSheet } from 'react-native';

    export default function Home() {
      return (
        <Link href="/settings" asChild>
          <Pressable style={styles.customButton}>
            <Text style={styles.buttonText}>تنظیمات من</Text>
          </Pressable>
        </Link>
      );
    }

    const styles = StyleSheet.create({
      customButton: {
        backgroundColor: 'rebeccapurple',
        padding: 15,
        borderRadius: 10,
        margin: 20,
      },
      buttonText: {
        color: 'white',
        fontWeight: 'bold',
      },
    });
    ```

### ۸-۳: هوک‌های ناوبری دستوری (`useRouter`, `useLocalSearchParams`, `usePathname`)

علاوه بر ناوبری اعلانی با `<Link>`, Expo Router هوک‌هایی را برای **ناوبری دستوری (Programmatic Navigation)** از داخل کد فراهم می‌کند. این هوک‌ها برای سناریوهایی که ناوبری بعد از یک عملیات (مانند ارسال فرم یا پاسخ API) اتفاق می‌افتد، بسیار مفید هستند.

1.  **هوک `useRouter`:** این هوک، ابزار اصلی شما برای جابجایی بین صفحات به صورت برنامه‌نویسی است.
    *   `router.push('/path')`: یک صفحه جدید را روی پشته (stack) قرار می‌دهد. کاربر می‌تواند با دکمه بازگشت به صفحه قبلی بازگردد.
    *   `router.replace('/path')`: صفحه فعلی را با یک صفحه جدید **جایگزین** می‌کند. کاربر نمی‌تواند به صفحه قبلی بازگردد. این هوک برای سناریوهایی مانند بعد از لاگین کردن کاربر بسیار مفید است.
    *   `router.back()`: به صفحه قبلی در پشته ناوبری بازمی‌گردد.

    **مثال (`useRouter`):**

    ```jsx
    import { useRouter } from 'expo-router';
    import { Button, View } from 'react-native';

    export default function DetailsScreen() {
      const router = useRouter();

      const goToSettings = () => {
        router.push('/settings'); // برو به صفحه تنظیمات
      };

      const goToHomeAndReplace = () => {
        router.replace('/'); // برو به صفحه اصلی و صفحه فعلی را از پشته حذف کن
      };

      const goBack = () => {
        router.back(); // بازگشت به صفحه قبلی
      };

      return (
        <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Button title="برو به تنظیمات" onPress={goToSettings} />
          <Button title="برو به خانه (جایگزینی)" onPress={goToHomeAndReplace} />
          <Button title="بازگشت" onPress={goBack} />
        </View>
      );
    }
    ```

2.  **هوک `useLocalSearchParams`:** این هوک برای **خواندن پارامترهای داینامیک** از URL **صفحه فعلی** استفاده می‌شود.
    *   **کاربرد:** اگر شما یک مسیر داینامیک مانند `app/user/[id].tsx` (که `[id]` یک پارامتر است) داشته باشید و کاربر به آدرس `/user/123` برود، هوک `useLocalSearchParams` یک آبجکت به شکل `{ id: '123' }` را برمی‌گرداند. این به شما اجازه می‌دهد تا داده‌های مربوط به آن `id` را از سرور دریافت و نمایش دهید.

    **مثال (`useLocalSearchParams`):**
    ```tsx
    // در فایل app/user/[id].tsx
    import { useLocalSearchParams } from 'expo-router';
    import { View, Text } from 'react-native';

    export default function UserProfile() {
      const { id } = useLocalSearchParams<{ id: string }>(); // دریافت پارامتر id

      return (
        <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Text>پروفایل کاربر با شناسه: {id}</Text>
        </View>
      );
    }
    ```

3.  **هوک `usePathname`:** این یک هوک ساده است که **آدرس مسیر فعلی** را به صورت یک رشته برمی‌گرداند (مثلاً `/user/123`).
    *   **کاربرد:** برای هایلایت کردن لینک فعال در یک منوی ناوبری سفارشی یا برای ارسال آدرس فعلی صفحه به سرویس‌های آنالیتیکس (Analytics) مفید است.

    **مثال (`usePathname`):**

    ```jsx
    import { usePathname } from 'expo-router';
    import { View, Text } from 'react-native';

    export default function CurrentPath() {
      const pathname = usePathname();

      return (
        <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Text>مسیر فعلی: {pathname}</Text>
        </View>
      );
    }
    ```

---

## فصل ۹: ارتباط با دنیای خارج: شبکه (Networking)

تقریباً تمام اپلیکیشن‌های مدرن موبایل نیاز به ارتباط با دنیای خارج دارند؛ یعنی برای دریافت و ارسال داده به سرورها از طریق اینترنت با APIها تعامل می‌کنند. در این فصل، با روش‌های مختلف برقراری ارتباط شبکه در React Native آشنا می‌شویم.

### ۹-۱: `Fetch API`

ریکت نیتیو به صورت داخلی از **Fetch API** پشتیبانی می‌کند. این یک استاندارد مدرن وب برای ارسال درخواست‌های شبکه (مانند GET, POST, PUT, DELETE) است. `Fetch API` مبتنی بر **Promise** است و به خوبی با ساختار `async/await` در جاوااسکریپت کار می‌کند، که کد را خواناتر و مدیریت خطا را آسان‌تر می‌کند.

**مثال ساده `Fetch`:**

```javascript
async function fetchPosts() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts');
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("خطا در دریافت داده:", error);
  }
}

// فراخوانی تابع
fetchPosts();
```

### ۹-۲: گردش کار دریافت داده (الگوی کلاسیک)

این الگو از هوک‌های `useEffect` و `useState` برای مدیریت چرخه حیات داده در کامپوننت‌های تابعی استفاده می‌کند. این روش رایج‌ترین الگوی دریافت داده قبل از React 19 بود و هنوز هم در بسیاری از پروژه‌ها استفاده می‌شود.

**مراحل اصلی:**

1.  **تعریف State ها:** سه `state` مجزا برای نگهداری وضعیت‌های مختلف تعریف می‌کنیم:
    *   `data`: برای ذخیره داده‌های دریافتی موفقیت‌آمیز.
    *   `isLoading`: یک مقدار `boolean` برای نمایش وضعیت بارگذاری (مثلاً نمایش یک Spinner).
    *   `error`: برای ذخیره هرگونه خطای احتمالی در حین فرایند دریافت داده.

2.  **ارسال درخواست در `useEffect`:** درخواست `fetch` را داخل یک هوک `useEffect` قرار می‌دهیم. برای اطمینان از اینکه درخواست **فقط یک بار** هنگام باز شدن صفحه (یا mount شدن کامپوننت) اجرا شود، آرایه وابستگی (Dependency Array) هوک `useEffect` را **خالی (`[]`)** قرار می‌دهیم.

3.  **مدیریت پاسخ (Try...Catch...Finally):** از یک بلاک `try...catch...finally` برای مدیریت نتایج درخواست استفاده می‌کنیم:
    *   در بلاک `try`: داده‌های دریافتی را به فرمت JSON تبدیل کرده و آن‌ها را در `state` مربوط به `data` قرار می‌دهیم.
    *   در بلاک `catch`: هر خطایی که در طول درخواست یا پردازش رخ دهد را دریافت کرده و آن را در `state` مربوط به `error` ذخیره می‌کنیم.
    *   در بلاک `finally`: وضعیت `isLoading` را به `false` تغییر می‌دهیم تا نشان دهیم که عملیات بارگذاری به پایان رسیده است، چه با موفقیت و چه با خطا.

4.  **رندر شرطی:** در رابط کاربری (UI)، بر اساس مقادیر `isLoading` و `error`، یک نمایشگر لودینگ، پیام خطا یا لیست داده‌های دریافتی را به کاربر نمایش می‌دهیم.

**مثال:**

```jsx
import React, { useState, useEffect } from 'react';
import { View, Text, ActivityIndicator, StyleSheet, FlatList } from 'react-native';

export default function PostsScreen() {
  const [posts, setPosts] = useState([]); //
  const [isLoading, setIsLoading] = useState(true); //
  const [error, setError] = useState(null); //

  useEffect(() => {
    const fetchPosts = async () => {
      try {
        setIsLoading(true); //
        const response = await fetch('https://jsonplaceholder.typicode.com/posts');
        if (!response.ok) {
          throw new Error(`HTTP error! status: ${response.status}`);
        }
        const data = await response.json();
        setPosts(data); //
      } catch (err) {
        setError(err); //
      } finally {
        setIsLoading(false); //
      }
    };

    fetchPosts();
  }, []); // آرایه وابستگی خالی برای اجرای یک بار

  if (isLoading) {
    return (
      <View style={styles.center}>
        <ActivityIndicator size="large" color="#0000ff" />
        <Text>در حال بارگذاری...</Text>
      </View>
    ); //
  }

  if (error) {
    return (
      <View style={styles.center}>
        <Text style={styles.errorText}>خطا: {error.message}</Text>
      </View>
    ); //
  }

  return (
    <FlatList
      data={posts}
      keyExtractor={item => item.id.toString()}
      renderItem={({ item }) => (
        <View style={styles.postItem}>
          <Text style={styles.postTitle}>{item.title}</Text>
          <Text>{item.body}</Text>
        </View>
      )}
    />
  ); //
}

const styles = StyleSheet.create({
  center: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  errorText: {
    color: 'red',
    fontSize: 16,
  },
  postItem: {
    padding: 15,
    borderBottomWidth: 1,
    borderBottomColor: '#eee',
  },
  postTitle: {
    fontSize: 18,
    fontWeight: 'bold',
    marginBottom: 5,
  },
});
```

### ۹-۳: گردش کار مدرن با React 19 (`use` و `Suspense`)

با پشتیبانی Expo از React 19 (و نسخه‌های بالاتر)، می‌توانیم فرآیند دریافت داده را بسیار ساده‌تر و بهینه‌تر کنیم. این رویکرد جدید از هوک `use` و کامپوننت `Suspense` بهره می‌برد.

*   **هوک `use`:** این هوک انقلابی به ما اجازه می‌دهد تا **نتیجه یک Promise را مستقیماً "باز" (unwrap) کنیم**، بدون نیاز به `useEffect` یا `useState` برای مدیریت وضعیت‌های لودینگ و خطا. اگر Promise در حال حل شدن باشد، کامپوننت به حالت تعلیق (Suspense) می‌رود. اگر Promise رد شود (Reject شود)، خطا به نزدیک‌ترین `Error Boundary` منتقل می‌شود.

*   **`Suspense`:**
 این کامپوننت به ما اجازه می‌دهد تا یک **UI جایگزین (fallback)** (مانند یک `ActivityIndicator` یا یک پیام "در حال بارگذاری") را نمایش دهیم **تا زمانی که داده‌های کامپوننت فرزند آماده شوند**. این جداسازی منطق بارگذاری از منطق نمایش داده‌ها، کد را خواناتر و ماژولارتر می‌کند.

**مثال:**

```jsx
// کامپوننت والد: ParentComponent.js
import React, { Suspense } from 'react'; //
import { View, Text, ActivityIndicator, StyleSheet } from 'react-native';
import MyDataComponent from './MyDataComponent'; // کامپوننت فرزند که از use استفاده می کند

export default function ParentComponent() {
  return (
    <View style={styles.container}>
      <Text style={styles.header}>لیست پست‌ها (مدرن)</Text>
      <Suspense fallback={<ActivityIndicator size="large" color="#0000ff" />}>
        {/* در حالیکه MyDataComponent در حال fetch کردن داده است، fallback نمایش داده می شود. */}
        <MyDataComponent />
      </Suspense>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    paddingTop: 50,
  },
  header: {
    fontSize: 24,
    fontWeight: 'bold',
    textAlign: 'center',
    marginBottom: 20,
  },
});
```

```jsx
// کامپوننت فرزند: MyDataComponent.js
import React, { use } from 'react'; //
import { Text, FlatList, View, StyleSheet } from 'react-native';

// تابع برای fetch داده
const fetchMyData = () => {
  return fetch('https://jsonplaceholder.typicode.com/posts')
    .then(res => {
      if (!res.ok) {
        throw new Error(`HTTP error! status: ${res.status}`);
      }
      return res.json();
    });
}; //

export default function MyDataComponent() {
  // دیگر نیازی به بررسی isLoding و error نیست، use این کار را مدیریت می کند
  const data = use(fetchMyData()); //

  return (
    <FlatList
      data={data}
      keyExtractor={item => item.id.toString()}
      renderItem={({ item }) => (
        <View style={styles.postItem}>
          <Text style={styles.postTitle}>{item.title}</Text>
          <Text>{item.body}</Text>
        </View>
      )}
    />
  ); //
}

const styles = StyleSheet.create({
  postItem: {
    padding: 15,
    borderBottomWidth: 1,
    borderBottomColor: '#eee',
  },
  postTitle: {
    fontSize: 18,
    fontWeight: 'bold',
    marginBottom: 5,
  },
});
```
**توضیح:** در این رویکرد، `ParentComponent` با استفاده از `<Suspense>`، یک UI جایگزین (لودینگ اسپینر) را نمایش می‌دهد تا `MyDataComponent` داده‌های خود را با `use(fetchMyData())` دریافت کند. وقتی داده‌ها آماده شدند، `<Suspense>` به طور خودکار `MyDataComponent` را رندر می‌کند. این امر کد را به شدت تمیزتر می‌کند و منطق بارگذاری را از منطق نمایش جدا می‌سازد. برای مدیریت خطاها در این سناریو، باید از **Error Boundaries** استفاده کنید (خارج از محدوده این منبع).

---

## فصل ۱۰: حافظه پایدار: ذخیره‌سازی داده‌ها

در بسیاری از اپلیکیشن‌ها، نیاز داریم اطلاعاتی را روی دستگاه کاربر ذخیره کنیم تا با بسته و باز شدن اپلیکیشن، این اطلاعات از بین نروند. این فصل شما را با روش‌های مختلف ذخیره‌سازی داده‌ها، از اطلاعات ساده تا داده‌های حساس و پیچیده، آشنا می‌کند.

### ۱۰-۱: `AsyncStorage` - انبار ساده کلید-مقدار

`AsyncStorage`
 استاندارد اصلی برای ذخیره داده‌های **ساده و غیرحساس** در React Native است. عملکردی شبیه به `localStorage` در وب دارد، اما به صورت ناهمزمان (Asynchronous) عمل می‌کند.

*   **ساختار:** داده‌ها به صورت **کلید-مقدار (Key-Value)** ذخیره می‌شوند. هم کلید و هم مقدار باید به صورت **رشته (string)** باشند.
*   **برای ذخیره آبجکت‌ها:** باید ابتدا آن‌ها را با `JSON.stringify()` به رشته تبدیل کنید و هنگام بازیابی با `JSON.parse()` به آبجکت اصلی برگردانید.
*   **کاربرد:** ذخیره تنظیمات کاربر (مانند تم برنامه، زبان)، نام کاربری یا وضعیت‌های ساده.
*   **نصب:**
    ```bash
    npx expo install @react-native-async-storage/async-storage
    ```

**مثال:**

```jsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button, TextInput, StyleSheet, Alert } from 'react-native';
import AsyncStorage from '@react-native-async-storage/async-storage';

export default function App() {
  const [username, setUsername] = useState('');
  const [savedUsername, setSavedUsername] = useState('');

  useEffect(() => {
    // بارگذاری نام کاربری هنگام باز شدن برنامه
    const loadUsername = async () => {
      try {
        const value = await AsyncStorage.getItem('user_name');
        if (value !== null) {
          setSavedUsername(value);
        }
      } catch (e) {
        Alert.alert('خطا در بارگذاری', 'نام کاربری بارگذاری نشد.');
      }
    };
    loadUsername();
  }, []);

  const saveUsername = async () => {
    try {
      await AsyncStorage.setItem('user_name', username);
      setSavedUsername(username);
      Alert.alert('موفقیت', 'نام کاربری ذخیره شد!');
    } catch (e) {
      Alert.alert('خطا در ذخیره', 'نام کاربری ذخیره نشد.');
    }
  };

  return (
    <View style={styles.container}>
      <Text style={styles.header}>AsyncStorage مثال</Text>
      <TextInput
        style={styles.input}
        placeholder="نام کاربری خود را وارد کنید"
        value={username}
        onChangeText={setUsername}
      />
      <Button title="ذخیره نام کاربری" onPress={saveUsername} />
      {savedUsername ? (
        <Text style={styles.savedText}>نام کاربری ذخیره شده: {savedUsername}</Text>
      ) : (
        <Text style={styles.savedText}>نام کاربری ذخیره نشده است.</Text>
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
    gap: 15,
  },
  header: {
    fontSize: 22,
    fontWeight: 'bold',
    marginBottom: 20,
  },
  input: {
    width: '90%',
    height: 40,
    borderColor: 'gray',
    borderWidth: 1,
    paddingHorizontal: 10,
    borderRadius: 5,
  },
  savedText: {
    marginTop: 20,
    fontSize: 16,
  },
});
```

### ۱۰-۲: `SecureStore` - گاوصندوق اطلاعات حساس

برای ذخیره اطلاعات **حساس** که نباید به راحتی قابل خواندن باشند (حتی با دسترسی مستقیم به فایل‌های دستگاه)، از ماژول `expo-secure-store` استفاده می‌کنیم.

*   **امنیت:** این ماژول از قابلیت‌های امنیتی خود سیستم‌عامل (**Keychain** در iOS و **Keystore** در Android) برای **رمزنگاری داده‌ها** استفاده می‌کند. این به این معنی است که داده‌ها به صورت امن در محل مخصوص سیستم‌عامل ذخیره می‌شوند و دسترسی به آن‌ها بدون احراز هویت مناسب بسیار دشوار است.
*   **کاربرد:** ذخیره توکن‌های احراز هویت (مانند JWT)، کلیدهای API خصوصی یا هر اطلاعات کاربری دیگری که نباید لو برود.
*   **نصب:**
    ```bash
    npx expo install expo-secure-store
    ```

**مثال:**

```jsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button, TextInput, StyleSheet, Alert } from 'react-native';
import * as SecureStore from 'expo-secure-store';

export default function App() {
  const [token, setToken] = useState('');
  const [savedToken, setSavedToken] = useState('');

  useEffect(() => {
    const loadToken = async () => {
      try {
        const value = await SecureStore.getItemAsync('user_jwt_token');
        if (value) {
          setSavedToken(value);
        }
      } catch (e) {
        Alert.alert('خطا', 'توکن بارگذاری نشد.');
      }
    };
    loadToken();
  }, []);

  const saveToken = async () => {
    try {
      await SecureStore.setItemAsync('user_jwt_token', token);
      setSavedToken(token);
      Alert.alert('موفقیت', 'توکن با امنیت ذخیره شد!');
    } catch (e) {
      Alert.alert('خطا', 'توکن ذخیره نشد.');
    }
  };

  const deleteToken = async () => {
    try {
      await SecureStore.deleteItemAsync('user_jwt_token');
      setSavedToken('');
      setToken('');
      Alert.alert('موفقیت', 'توکن حذف شد!');
    } catch (e) {
      Alert.alert('خطا', 'توکن حذف نشد.');
    }
  };

  return (
    <View style={styles.container}>
      <Text style={styles.header}>SecureStore مثال</Text>
      <TextInput
        style={styles.input}
        placeholder="توکن خود را وارد کنید"
        value={token}
        onChangeText={setToken}
        secureTextEntry // برای ورود ایمن تر
      />
      <Button title="ذخیره توکن" onPress={saveToken} />
      <Button title="حذف توکن" onPress={deleteToken} color="red" />
      {savedToken ? (
        <Text style={styles.savedText}>توکن ذخیره شده (مخفی): ****{savedToken.substring(savedToken.length - 4)}</Text>
      ) : (
        <Text style={styles.savedText}>توکنی ذخیره نشده است.</Text>
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
    gap: 15,
  },
  header: {
    fontSize: 22,
    fontWeight: 'bold',
    marginBottom: 20,
  },
  input: {
    width: '90%',
    height: 40,
    borderColor: 'gray',
    borderWidth: 1,
    paddingHorizontal: 10,
    borderRadius: 5,
  },
  savedText: {
    marginTop: 20,
    fontSize: 16,
  },
});
```

### ۱۰-۳: `SQLite` - دیتابیس رابطه‌ای

برای مدیریت داده‌های **حجیم، پیچیده و رابطه‌ای** که نیاز به کوئری‌های پیشرفته و عملکرد بالا در حالت آفلاین دارند، به یک دیتابیس واقعی روی دستگاه نیاز داریم. `expo-sqlite` یک پیاده‌سازی از دیتابیس محبوب **SQLite** را فراهم می‌کند که به صورت یک فایل روی دستگاه کاربر ذخیره می‌شود.

*   **کاربرد:** ساخت اپلیکیشن‌هایی که باید به صورت آفلاین به خوبی کار کنند (مانند اپ‌های مدیریت وظایف، برنامه‌های یادداشت‌برداری، یا هر برنامه‌ای با داده‌های ساختاریافته).
*   **نصب:**
    ```bash
    npx expo install expo-sqlite
    ```

**مثال (نمونه استفاده اولیه):**

```jsx
import React, { useEffect, useState } from 'react';
import { View, Text, Button, TextInput, FlatList, StyleSheet } from 'react-native';
import * as SQLite from 'expo-sqlite';

const db = SQLite.openDatabase('mydb.db'); //

export default function App() {
  const [todo, setTodo] = useState('');
  const [todos, setTodos] = useState([]);

  useEffect(() => {
    db.transaction(tx => {
      // ایجاد جدول اگر وجود ندارد
      tx.executeSql(
        'CREATE TABLE IF NOT EXISTS todos (id INTEGER PRIMARY KEY AUTOINCREMENT, text TEXT)'
      );
    });
    fetchTodos();
  }, []);

  const fetchTodos = () => {
    db.transaction(tx => {
      tx.executeSql('SELECT * FROM todos', [], (_, { rows }) => {
        setTodos(rows._array);
      });
    });
  };

  const addTodo = () => {
    if (todo.trim() === '') return;
    db.transaction(tx => {
      tx.executeSql('INSERT INTO todos (text) VALUES (?)', [todo], () => {
        setTodo('');
        fetchTodos();
      });
    });
  };

  const deleteTodo = (id) => {
    db.transaction(tx => {
      tx.executeSql('DELETE FROM todos WHERE id = ?', [id], () => {
        fetchTodos();
      });
    });
  };

  return (
    <View style={styles.container}>
      <Text style={styles.header}>لیست کارهای من (SQLite)</Text>
      <View style={styles.inputContainer}>
        <TextInput
          style={styles.input}
          placeholder="کار جدید"
          value={todo}
          onChangeText={setTodo}
        />
        <Button title="اضافه کن" onPress={addTodo} />
      </View>
      <FlatList
        data={todos}
        keyExtractor={item => item.id.toString()}
        renderItem={({ item }) => (
          <View style={styles.todoItem}>
            <Text style={styles.todoText}>{item.text}</Text>
            <Button title="حذف" onPress={() => deleteTodo(item.id)} color="red" />
          </View>
        )}
      />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    paddingTop: 50,
    paddingHorizontal: 20,
  },
  header: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
    textAlign: 'center',
  },
  inputContainer: {
    flexDirection: 'row',
    marginBottom: 20,
    gap: 10,
  },
  input: {
    flex: 1,
    borderWidth: 1,
    borderColor: '#ccc',
    padding: 10,
    borderRadius: 5,
  },
  todoItem: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    alignItems: 'center',
    padding: 15,
    backgroundColor: '#f0f0f0',
    borderRadius: 5,
    marginBottom: 10,
  },
  todoText: {
    fontSize: 18,
  },
});
```

---

## فصل ۱۱: روح بخشیدن به اپ: انیمیشن و جسچرها

انیمیشن‌های روان و بازخوردهای لمسی جذاب، تجربه کاربری (UX) را به سطح دیگری می‌برند و اپلیکیشن شما را زنده و پویاتر می‌کنند. در این فصل، با استفاده از کتابخانه‌های قدرتمند `React Native Reanimated` و `react-native-gesture-handler`، یاد می‌گیریم چگونه انیمیشن‌های پیشرفته و تعاملات لمسی پیچیده را پیاده‌سازی کنیم.

### ۱۱-۱: انیمیشن با React Native Reanimated

`React Native Reanimated`
 کتابخانه استاندارد و مدرن برای پیاده‌سازی انیمیشن‌های با عملکرد بالا در React Native است. دلیل اصلی برتری آن این است که منطق انیمیشن را مستقیماً روی **نخ UI (Main Thread)** اجرا می‌کند. این کار باعث می‌شود انیمیشن‌ها حتی زمانی که نخ جاوااسکریپت مشغول است، به صورت **روان و ۶۰ فریم بر ثانیه** اجرا شوند.

*   **مفاهیم اصلی:**
    *   **`useSharedValue`**: این هوک برای تعریف مقادیری استفاده می‌شود که قرار است **انیمیت شوند**. مانند `useState` عمل می‌کند، اما مقدار ذخیره شده در آن بین نخ JS و نخ UI "به اشتراک گذاشته" می‌شود.
    *   **`useAnimatedStyle`**: این هوک یک آبجکت استایل انیمیشنی را برمی‌گرداند که به مقادیر اشتراکی (Shared Values) شما متصل است. هر زمان که مقدار اشتراکی تغییر کند، استایل مربوطه به صورت انیمیت شده به‌روزرسانی می‌شود.
    *   **`Animated.View`، `Animated.Text` و `Animated.Image`**: نسخه‌های انیمیشنی کامپوننت‌های اصلی React Native هستند. شما باید کامپوننت‌هایی را که می‌خواهید انیمیت کنید، به این نسخه‌های `Animated` تبدیل کنید تا بتوانند استایل‌های انیمیشنی را دریافت کنند.
    *   **`withTiming` و `withSpring`**: این توابع به Reanimated می‌گویند که یک مقدار را **چگونه** انیمیت کند.
        *   `withTiming(toValue, config)`: یک انیمیشن مبتنی بر **زمان** (Duration) ایجاد می‌کند.
        *   `withSpring(toValue, config)`: یک انیمیشن **فنری** و طبیعی ایجاد می‌کند که حالت ارتداد (Bouncy) دارد.

**نصب:**
```bash
npx expo install react-native-reanimated
```
پس از نصب، باید `plugins: ['react-native-reanimated/plugin']` را به فایل `babel.config.js` خود اضافه کرده و سرور Metro را ریستارت کنید.

**مثال (انیمیشن با `withTiming`):**

```jsx
import React from 'react';
import { Button, StyleSheet, View } from 'react-native';
import Animated, { useSharedValue, useAnimatedStyle, withTiming } from 'react-native-reanimated'; //

export default function ReanimatedExample() {
  const offset = useSharedValue(0); //

  const animatedStyles = useAnimatedStyle(() => {
    return {
      transform: [{ translateX: offset.value }], //
    };
  });

  const handleMoveBox = () => {
    offset.value = withTiming(Math.random() * 250, { duration: 1000 }); //
  };

  return (
    <View style={styles.container}>
      <Animated.View style={[styles.box, animatedStyles]} /> {/* */}
      <Button title="حرکت جعبه" onPress={handleMoveBox} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  box: {
    width: 100,
    height: 100,
    backgroundColor: 'rebeccapurple',
    borderRadius: 10,
    marginBottom: 50,
  },
});
```

### ۱۱-۲: کار با حرکات لمسی (Gestures)

برای مدیریت حرکات لمسی پیچیده مانند کشیدن (Drag)، زوم کردن، یا چرخاندن، ما از کتابخانه **`react-native-gesture-handler`** در ترکیب با Reanimated استفاده می‌کنیم. این کتابخانه‌ها به ما اجازه می‌دهند که حرکات لمسی را به صورت بومی و با عملکرد بالا پردازش کنیم.

*   **API مدرن:** به جای هوک‌های قدیمی، از آبجکت **`Gesture`** برای تعریف نوع حرکت (مثلاً `Gesture.Pan()` برای کشیدن، `Gesture.Tap()` برای ضربه) و از کامپوننت **`<GestureDetector>`** برای اعمال آن به یک عنصر استفاده می‌کنیم.
*   **Worklets:** توابعی که قرار است در پاسخ به جسچرها روی **نخ UI** اجرا شوند، باید با دستورالعمل `"worklet";` در ابتدای آن‌ها مشخص شوند. این کار باعث می‌شود کد به درستی در Context نخ UI اجرا شود و از کرش کردن برنامه جلوگیری می‌کند.

**نصب:**
```bash
npx expo install react-native-gesture-handler react-native-reanimated
```
پس از نصب `react-native-gesture-handler`, باید آن را در `entry-point` اصلی برنامه (معمولا `index.js` یا `App.js`) ایمپورت کنید: `import 'react-native-gesture-handler';`

**مثال (کشیدن یک جعبه با `Gesture.Pan`):**

```jsx
import React from 'react';
import { StyleSheet, View } from 'react-native';
import Animated, {
  useSharedValue,
  useAnimatedStyle,
  withSpring,
} from 'react-native-reanimated';
import { Gesture, GestureDetector } from 'react-native-gesture-handler'; //

export default function DraggableBox() {
  const translateX = useSharedValue(0);
  const translateY = useSharedValue(0);

  // تعریف جسچر کشیدن (Pan Gesture)
  const panGesture = Gesture.Pan()
    .onStart((event) => {
      // این تابع روی نخ UI اجرا می شود
      'worklet'; //
      // می توانید مقادیر اولیه را اینجا ذخیره کنید
    })
    .onUpdate((event) => {
      'worklet'; //
      translateX.value = event.translationX; //
      translateY.value = event.translationY; //
    })
    .onEnd((event) => {
      'worklet'; //
      // پس از پایان کشیدن، جعبه را به حالت فنری به مبدأ برگردانید (مثلا)
      // یا آن را در موقعیت فعلی با انیمیشن فنری نگه دارید
      translateX.value = withSpring(0);
      translateY.value = withSpring(0);
    });

  // استایل انیمیشنی برای جعبه
  const animatedStyle = useAnimatedStyle(() => {
    return {
      transform: [{ translateX: translateX.value }, { translateY: translateY.value }],
    };
  });

  return (
    <View style={styles.container}>
      {/* اعمال جسچر به جعبه با GestureDetector */}
      <GestureDetector gesture={panGesture}>
        <Animated.View style={[styles.box, animatedStyle]} />
      </GestureDetector>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  box: {
    width: 100,
    height: 100,
    backgroundColor: 'royalblue',
    borderRadius: 10,
  },
});
```

---

## فصل ۱۲: تضمین کیفیت: تست‌نویسی (Testing)

نوشتن تست‌های خودکار (Automated Tests) یک بخش حیاتی از فرآیند توسعه نرم‌افزار حرفه‌ای است. تست‌ها تضمین می‌کنند که اپلیکیشن شما در طول زمان باکیفیت، پایدار و بدون باگ‌های ناخواسته باقی بماند، حتی با اضافه شدن ویژگی‌های جدید. این فصل، شما را با سه نوع اصلی تست‌نویسی در React Native آشنا می‌کند.

### ۱۲-۱: تست واحد (Unit Testing)

*   **هدف:** تست واحد بر **کوچکترین واحد کد** (معمولاً یک تابع یا یک ماژول کوچک) تمرکز دارد. هدف این است که مطمئن شویم هر واحد کد به صورت **ایزوله** و مستقل، همانطور که انتظار می‌رود، کار می‌کند.
*   **ابزار:** **Jest**. Jest یک فریم‌ورک تست جاوااسکریپت است که توسط فیس‌بوک (توسعه‌دهنده React Native) ساخته شده است. این فریم‌ورک به طور پیش‌فرض در پروژه‌های Expo پیکربندی شده است و نیاز به تنظیمات کمی دارد.

**مثال (تابع ساده):**

```javascript
// utils/math.js
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}
```

```javascript
// __tests__/math.test.js
import { add, subtract } from '../utils/math';

describe('Math functions', () => { //
  test('add function should correctly add two numbers', () => { //
    expect(add(1, 2)).toBe(3); //
    expect(add(-1, 5)).toBe(4);
    expect(add(0, 0)).toBe(0);
  });

  test('subtract function should correctly subtract two numbers', () => { //
    expect(subtract(5, 2)).toBe(3);
    expect(subtract(10, 20)).toBe(-10);
    expect(subtract(7, 7)).toBe(0);
  });
});
```

برای اجرای تست‌ها: `npm test` یا `yarn test`

### ۱۲-۲: تست کامپوننت (Component Testing)

*   **هدف:** تست کامپوننت بر تست کردن **یک کامپوننت React به تنهایی** تمرکز دارد. این تست‌ها بررسی می‌کنند که آیا کامپوننت به درستی رندر می‌شود، ورودی‌ها (پراپ‌ها) را به درستی دریافت می‌کند و به تعاملات کاربر (مانند کلیک) واکنش صحیح نشان می‌دهد.
*   **ابزار:** **React Native Testing Library**. این کتابخانه بر اساس فلسفه "تست بر اساس نحوه استفاده کاربر" بنا شده است و به شما کمک می‌کند تا تست‌هایی بنویسید که شبیه به تعاملات واقعی کاربر با UI باشند.

**نصب:**
```bash
npm install --save-dev @testing-library/react-native jest-expo react-test-renderer
```
(یا `yarn add --dev ...`)

**مثال (کامپوننت ساده دکمه):**

```jsx
// components/MyButton.js
import React from 'react';
import { Pressable, Text, StyleSheet } from 'react-native';

export default function MyButton({ title, onPress }) {
  return (
    <Pressable style={styles.button} onPress={onPress}>
      <Text style={styles.text}>{title}</Text>
    </Pressable>
  );
}

const styles = StyleSheet.create({
  button: {
    backgroundColor: '#007bff',
    padding: 10,
    borderRadius: 5,
  },
  text: {
    color: 'white',
    fontSize: 16,
  },
});
```

```jsx
// __tests__/MyButton.test.js
import React from 'react';
import { render, fireEvent } from '@testing-library/react-native'; //
import MyButton from '../components/MyButton';

describe('MyButton', () => { //
  test('renders correctly with given title', () => {
    const { getByText } = render(<MyButton title="کلیک کنید" onPress={() => {}} />); //
    expect(getByText('کلیک کنید')).toBeTruthy(); //
  });

  test('calls onPress when button is pressed', () => {
    const mockOnPress = jest.fn(); // Mock کردن تابع onPress
    const { getByText } = render(<MyButton title="تست" onPress={mockOnPress} />); //

    fireEvent.press(getByText('تست')); // شبیه سازی کلیک
    expect(mockOnPress).toHaveBeenCalledTimes(1); // بررسی اینکه تابع فراخوانی شده است
  });
});
```

### ۱۲-۳: تست سرتاسری (End-to-End - E2E)

*   **هدف:** تست E2E بر تست کردن **کل جریان کاری اپلیکیشن**، از دید یک کاربر واقعی، تمرکز دارد. در این نوع تست، یک ربات یا ابزار خودکار، اپلیکیشن را روی یک شبیه‌ساز واقعی یا دستگاه فیزیکی باز می‌کند و سناریوهای مختلف کاربر (مانند ورود، پیمایش بین صفحات، ارسال فرم) را اجرا می‌کند تا مطمئن شود کل سیستم به درستی با هم کار می‌کند.
*   **ابزارها:**
    *   **Maestro:** یک ابزار نسبتاً جدید و ساده‌تر برای نوشتن تست‌های E2E است.
    *   **Detox:** یک فریم‌ورک تست E2E قوی‌تر و با قابلیت‌های بیشتر است.

تست E2E پیچیده‌تر است و نیاز به پیکربندی بیشتری دارد که در این بخش به جزئیات آن نمی‌پردازیم، اما درک مفهوم آن برای یک توسعه‌دهنده حرفه‌ای ضروری است.

---

## فصل ۱۳: بهینه‌سازی و عملکرد (Performance Optimization)

عملکرد (Performance) یکی از مهم‌ترین جنبه‌های هر اپلیکیشن موبایل است. یک اپلیکیشن سریع، روان و پاسخگو، تجربه کاربری بهتری را ارائه می‌دهد و کاربران را راضی نگه می‌دارد. در این فصل، یاد می‌گیریم چطور اپلیکیشن خود را سریع، روان و بهینه نگه داریم.

### ۱۳-۱: ابزارهای اصلی

برای شناسایی مشکلات عملکردی در اپلیکیشن React Native، ابزارهای قدرتمندی در دسترس داریم:

*   **Profiler در React DevTools:** این ابزار، که از طریق **Flipper** قابل دسترسی است، به شما اجازه می‌دهد **عملکرد رندرینگ اپلیکیشن** را ضبط و تحلیل کنید. با استفاده از Profiler می‌توانید ببینید کدام کامپوننت‌ها بیهوده دوباره رندر می‌شوند یا رندر آنها زمان‌بر است. این ابزار به شناسایی bottlenecks (نقاط گلوگاهی) در رندرینگ کمک می‌کند.

*   **Flipper:** Flipper یک اپلیکیشن دسکتاپ و ابزار دیباگینگ **همه‌کاره** است که توسط فیس‌بوک توسعه یافته است. این ابزار پلاگین‌های متنوعی برای بررسی جنبه‌های مختلف اپلیکیشن ارائه می‌دهد:
    *   **Layout (چیدمان):** برای بررسی و تغییر چیدمان عناصر UI در زمان واقعی.
    *   **Network (شبکه):** برای مشاهده تمام درخواست‌های شبکه و پاسخ‌های آن‌ها.
    *   **Logs (لاگ‌ها):** برای مشاهده پیام‌های `console.log` و خطاها.
    *   **Shared Preferences/AsyncStorage:** برای بررسی داده‌های ذخیره شده در دستگاه.
    استفاده از Flipper برای دیباگینگ و مانیتورینگ عملکرد بسیار توصیه می‌شود.

### ۱۳-۲: تکنیک‌های بهینه‌سازی

برای بهبود عملکرد اپلیکیشن، چندین تکنیک کلیدی وجود دارد:

1.  **جلوگیری از رندرهای غیرضروری:** رندر شدن بیش از حد کامپوننت‌ها (حتی اگر UI تغییری نکرده باشد) یکی از دلایل اصلی افت عملکرد است. React ابزارهایی برای جلوگیری از این رندرهای اضافی ارائه می‌دهد:
    *   **`React.memo`**: این یک Higher-Order Component (HOC) است که کامپوننت‌های فرزندی را که `props` (ویژگی‌ها) آنها تغییر نکرده‌اند، از رندر شدن مجدد محافظت می‌کند. اگر پراپ‌های یک کامپوننت `memoized` تغییر نکرده باشد، React از آخرین رندر کش شده آن استفاده می‌کند.
    *   **`useCallback`**: این هوک از ساخته شدن **مجدد توابع** در هر رندر جلوگیری می‌کند. وقتی یک تابع را به عنوان پراپ به یک کامپوننت `memoized` پاس می‌دهید، `useCallback` تضمین می‌کند که تابع تنها در صورت تغییر وابستگی‌هایش (Dependencies) دوباره ساخته شود.
    *   **`useMemo`**: این هوک نتیجه **محاسبات سنگین** را در حافظه کش می‌کند تا از اجرای مجدد آنها در هر رندر جلوگیری شود. برای مثال، اگر یک لیست بزرگ را فیلتر یا مرتب می‌کنید، می‌توانید نتیجه را `useMemo` کنید.

    **مثال (استفاده از `React.memo` و `useCallback`):**

    ```jsx
    import React, { useState, useCallback, memo } from 'react';
    import { View, Text, Button, StyleSheet } from 'react-native';

    // یک کامپوننت فرزند که می خواهیم آن را بهینه کنیم
    const ChildComponent = memo(({ count, onIncrement }) => { //
      console.log('ChildComponent رندر شد');
      return (
        <View style={styles.childContainer}>
          <Text>شمارنده فرزند: {count}</Text>
          <Button title="افزایش فرزند" onPress={onIncrement} />
        </View>
      );
    });

    export default function ParentComponent() {
      const [parentCount, setParentCount] = useState(0);
      const [childCount, setChildCount] = useState(0);

      // تابع onIncrement با useCallback بهینه شده است
      // تنها زمانی دوباره ساخته می شود که childCount تغییر کند
      const handleChildIncrement = useCallback(() => {
        setChildCount(prev => prev + 1);
      }, []);

      console.log('ParentComponent رندر شد');

      return (
        <View style={styles.container}>
          <Text style={styles.header}>شمارنده والد: {parentCount}</Text>
          <Button title="افزایش والد" onPress={() => setParentCount(prev => prev + 1)} />

          <ChildComponent count={childCount} onIncrement={handleChildIncrement} />
        </View>
      );
    }

    const styles = StyleSheet.create({
      container: {
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
        gap: 20,
      },
      header: {
        fontSize: 24,
        fontWeight: 'bold',
      },
      childContainer: {
        marginTop: 30,
        padding: 20,
        backgroundColor: '#e0f7fa',
        borderRadius: 10,
        alignItems: 'center',
        gap: 10,
      },
    });
    ```

2.  **بهینه‌سازی `FlatList`**: در فصل ۶ به اهمیت `FlatList` اشاره شد. برای لیست‌های بسیار بلند، می‌توانید از پراپ‌های پیشرفته‌تری نیز استفاده کنید:
    *   `getItemLayout`:
 اگر ارتفاع تمام آیتم‌های لیست ثابت است، می‌توانید یک تابع `getItemLayout` ارائه دهید. این به `FlatList` کمک می‌کند تا بدون نیاز به اندازه‌گیری هر آیتم، موقعیت دقیق آن‌ها را محاسبه کند و عملکرد اسکرول را به شدت بهبود بخشد.
    *   `initialNumToRender`:
 تعداد آیتم‌هایی که `FlatList` در ابتدا رندر می‌کند را مشخص می‌کند. تنظیم این مقدار بهینه می‌تواند سرعت بارگذاری اولیه لیست را تسریع کند.

3.  **موتور Hermes**: Hermes یک **موتور جاوااسکریپت بهینه‌سازی شده** است که توسط فیس‌بوک برای React Native توسعه یافته است. این موتور به طور پیش‌فرض در پروژه‌های Expo فعال است و استفاده از آن باعث **کاهش مصرف حافظه** و **افزایش سرعت بارگذاری اولیه** اپلیکیشن می‌شود. مطمئن شوید که Hermes در پروژه شما فعال است (در `app.json` یا `app.config.js`).

---

## فصل ۱۴: گردش کار حرفه‌ای: Development Builds

یکی از محدودیت‌های اولیه Expo، وابستگی به اپلیکیشن **Expo Go** برای توسعه بود. در این فصل، با مفهوم **Development Builds** آشنا می‌شویم که کلید عبور از این محدودیت‌ها و رسیدن به نهایت قدرت توسعه با Expo است.

### ۱۴-۱: مشکل Expo Go

اپلیکیشن Expo Go که برای اجرای سریع پروژه‌ها روی دستگاه‌های واقعی استفاده می‌شود، شامل مجموعه‌ای از **ماژول‌های نیتیو از پیش نصب شده** است. این ماژول‌ها کتابخانه‌های پرکاربرد Expo (مانند `expo-camera`, `expo-location` و غیره) را فراهم می‌کنند.

**مشکل اینجا پیش می‌آید:** اگر شما به یک **کتابخانه نیتیو دیگری** نیاز داشته باشید که جزو ماژول‌های از پیش نصب شده در Expo Go نیست (مثلاً یک کتابخانه پرداخت سفارشی یا یک SDK خاص)، اپلیکیشن شما در Expo Go **کرش می‌کند**. در گذشته، برای استفاده از چنین کتابخانه‌هایی، مجبور بودید پروژه را به React Native CLI "Eject" کنید، که به معنای از دست دادن سادگی Expo و ورود به دنیای پیچیده‌تر مدیریت کدهای نیتیو بود.

### ۱۴-۲: راه حل: Development Builds

**Development Build (بیلد توسعه)**:
 یک نسخه کاملاً **سفارشی از اپلیکیشن Expo Go** است که **مخصوص پروژه شما** ساخته می‌شود. این بیلد، علاوه بر ماژول‌های پیش‌فرض Expo، **تمام کتابخانه‌های نیتیو دیگری که شما به پروژه خود اضافه کرده‌اید** را نیز شامل می‌شود.

*   **نتیجه:** شما دیگر هیچ محدودیتی در استفاده از کتابخانه‌های اکوسیستم گسترده React Native ندارید و در عین حال از سادگی و سرعت توسعه Expo بهره‌مند می‌شوید. این به شما اجازه می‌دهد تا هر پکیج npm که شامل کد نیتیو است را نصب و استفاده کنید.

*   **فرآیند:**
    1.  **نصب `expo-dev-client`:**
        ```bash
        npx expo install expo-dev-client
        ```
    2.  **ساخت Development Build:** با اجرای دستور `eas build --profile development`، یک نسخه توسعه از اپلیکیشن خود می‌سازید. این دستور بیلد را در سرویس ابری EAS انجام می‌دهد و یک فایل `.apk` (برای اندروید) یا `.ipa` (برای iOS) به شما می‌دهد.
    3.  **استفاده:** پس از ساخت و نصب این بیلد روی دستگاه واقعی یا شبیه‌ساز، از آن به جای اپلیکیشن Expo Go برای توسعه روزمره استفاده می‌کنید. این بیلد به سرور Metro شما متصل می‌شود و `Fast Refresh` و سایر ابزارهای دیباگینگ همچنان کار می‌کنند.

**خلاصه:** Development Builds به شما بهترین هر دو دنیا را می‌دهد: سادگی Expo برای توسعه سریع جاوااسکریپت، و انعطاف‌پذیری React Native CLI برای استفاده از هر کتابخانه نیتیوی که نیاز دارید.

---

## فصل ۱۵: از کد تا کاربر: ساخت و انتشار با EAS

پس از اینکه اپلیکیشن خود را توسعه دادید و از کیفیت آن مطمئن شدید، گام نهایی تبدیل کد شما به یک اپلیکیشن واقعی و قابل انتشار در فروشگاه‌های اپلیکیشن (Google Play Store و Apple App Store) است. Expo به وسیله سرویس **EAS (Expo Application Services)** این فرآیند را به شدت ساده و خودکار می‌کند.

### ۱۵-۱: EAS Build

`EAS Build` یک سرویس ابری از Expo است که کدهای شما را دریافت کرده و **فایل‌های نهایی اپلیکیشن** را برای پلتفرم‌های مختلف در فضای ابری برایتان می‌سازد.

*   **خروجی:** برای اندروید، فایل‌های `.apk` (برای نصب مستقیم) یا `.aab` (Android App Bundle، فرمت توصیه شده برای انتشار در پلی استور) تولید می‌شود. برای iOS، فایل `.ipa` تولید می‌شود.
*   **مزیت اصلی:** **بدون نیاز به داشتن مک برای ساخت خروجی iOS** و بدون درگیر شدن با تنظیمات پیچیده Xcode و Android Studio. EAS Build تمام فرآیند کامپایل نیتیو را در سرورهای خود انجام می‌دهد.
*   **دستور:**
    ```bash
    eas build --platform all
    ```
    این دستور یک بیلد برای هر دو پلتفرم iOS و Android ایجاد می‌کند. شما می‌توانید با `--platform android` یا `--platform ios` فقط برای یک پلتفرم خاص بیلد بگیرید.

### ۱۵-۲: EAS Update (آپدیت هوایی - OTA)

`EAS Update` یکی از قدرتمندترین قابلیت‌های Expo است. این ویژگی به شما اجازه می‌دهد تا **تمام تغییرات جاوااسکریپت** (مانند اصلاح باگ‌ها، تغییرات ظاهری، به‌روزرسانی‌های منطق برنامه) را **بدون نیاز به انتشار نسخه جدید در اپ استورها**، مستقیماً برای کاربران خود ارسال کنید.

*   **نحوه کار:** EAS Update یک بسته جاوااسکریپت جدید تولید می‌کند و آن را روی CDN (شبکه توزیع محتوا) میزبانی می‌کند. اپلیکیشن‌های کاربران شما در پس‌زمینه این به‌روزرسانی‌ها را دریافت کرده و در اجرای بعدی یا پس از چند دقیقه آن‌ها را اعمال می‌کنند.
*   **دستور:**
    ```bash
    eas update
    ```
    این دستور یک به‌روزرسانی جدید ایجاد و آن را منتشر می‌کند.

**اهمیت:** این ویژگی می‌تواند زمان انتشار به‌روزرسانی‌ها را از چند روز/هفته به **چند دقیقه** کاهش دهد و برای رفع سریع باگ‌ها یا اعمال تغییرات کوچک بسیار حیاتی است.

### ۱۵-۳: EAS Submit

`EAS Submit` یک سرویس دیگر از EAS است که فرآیند **آپلود کردن فایل نهایی اپلیکیشن** (که توسط EAS Build تولید شده) به **Google Play Console** و **App Store Connect** را به صورت خودکار و از طریق خط فرمان انجام می‌دهد.

*   **مزیت:** نیاز به آپلود دستی فایل‌ها، پر کردن جزئیات و مدیریت گواهی‌ها را کاهش می‌دهد و این فرآیند اغلب پیچیده را ساده می‌کند.
*   **دستور:**
    ```bash
    eas submit -p android
    ```
    یا
    ```bash
    eas submit -p ios
    ```
    این دستورات به شما کمک می‌کنند تا بیلد نهایی را به راحتی به فروشگاه‌های مربوطه ارسال کنید.

---

## پایان دوره

تبریک می‌گویم! شما با موفقیت تمام مراحل ساخت یک اپلیکیشن مدرن با React Native و Expo را از صفر تا صد طی کردید. شما اکنون دانش و ابزارهای لازم برای تبدیل هر ایده‌ای به یک اپلیکیشن واقعی، باکیفیت و قابل انتشار را در اختیار دارید.

**قدم بعدی، شروع ساخت پروژه شخصی خودتان است.** هیچ چیز به اندازه پیاده‌سازی آموخته‌ها در یک پروژه عملی، به شما کمک نمی‌کند تا مفاهیم را عمیق‌تر درک کنید و مهارت‌های خود را تقویت کنید.

موفق باشید! 🚀

---
