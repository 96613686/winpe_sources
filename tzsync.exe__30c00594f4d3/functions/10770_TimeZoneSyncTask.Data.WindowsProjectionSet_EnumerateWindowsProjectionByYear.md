# TimeZoneSyncTask.Data.WindowsProjectionSet::EnumerateWindowsProjectionByYear

- ea: `0x10770`
- end: `0x107c4`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::EnumerateWindowsProjectionByYear`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x11bf0`

## callees

- `0x104d0`
- `0x10770`

## pseudocode

```c

```

## disassembly

```asm
0x10770  ldarg.0
0x10771  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x10776  ldarg.0
0x10777  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::<EnumerateWindowsProjectionByYear>b__27_0(valuetype [mscorlib]System.TimeSpan tsUtcOffset)
0x1077d  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.TimeSpan, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>>::.ctor(object, native int)
0x10782  ldsfld   class [mscorlib]System.Func`3<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>> <>c::<>9__27_1
0x10787  dup
0x10788  brtrue.s loc_107A1
0x1078a  pop
0x1078b  ldsfld   class <>c <>c::<>9
0x10790  ldftn    instance class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> <>c::<EnumerateWindowsProjectionByYear>b__27_1(valuetype [mscorlib]System.TimeSpan tsUtcOffset, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> dtStandardDate)
0x10796  newobj   instance void class [mscorlib]System.Func`3<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>>::.ctor(object, native int)
0x1079b  dup
0x1079c  stsfld   class [mscorlib]System.Func`3<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>> <>c::<>9__27_1
0x107a1  call     T0x2B000025
0x107a6  ldarg.0
0x107a7  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::<EnumerateWindowsProjectionByYear>b__27_2(class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> <>h__TransparentIdentifier0)
0x107ad  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>>::.ctor(object, native int)
0x107b2  ldarg.0
0x107b3  ldftn    instance valuetype TimeZoneSyncTask.Data.WindowsProjection TimeZoneSyncTask.Data.WindowsProjectionSet::<EnumerateWindowsProjectionByYear>b__27_3(class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> <>h__TransparentIdentifier0, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> dtDaylightDate)
0x107b9  newobj   instance void class [mscorlib]System.Func`3<class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype TimeZoneSyncTask.Data.WindowsProjection>::.ctor(object, native int)
0x107be  call     T0x2B000026
0x107c3  ret
```
