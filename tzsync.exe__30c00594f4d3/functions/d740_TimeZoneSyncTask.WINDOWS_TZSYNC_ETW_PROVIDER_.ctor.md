# TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::.ctor

- ea: `0xd740`
- end: `0xd8c4`
- name: `TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::.ctor`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xc470`

## callees

- `0xdaf0`

## pseudocode

```c

```

## disassembly

```asm
0xd740  ldarg.0
0xd741  ldstr    a3527cb55129849// "3527cb55-1298-49d4-ab94-1243db0fcaff"
0xd746  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd74b  newobj   instance void TimeZoneSyncTask.EventProviderVersionTwo::.ctor(valuetype [mscorlib]System.Guid id)
0xd750  stfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd755  ldarg.0
0xd756  ldstr    a3840a6620e3443// "3840a662-0e34-43c4-bae8-1af27f4216d3"
0xd75b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd760  stfld    valuetype [mscorlib]System.Guid TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::InitializationId
0xd765  ldarg.0
0xd766  ldstr    aA556bce02f3047// "a556bce0-2f30-471e-b810-815af95e780f"
0xd76b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd770  stfld    valuetype [mscorlib]System.Guid TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::ConversionId
0xd775  ldarg.0
0xd776  call     instance void [mscorlib]System.Object::.ctor()
0xd77b  ldarg.0
0xd77c  ldc.i4.1
0xd77d  ldc.i4.0
0xd77e  ldc.i4.s 0x11
0xd780  ldc.i4.4
0xd781  ldc.i4.1
0xd782  ldc.i4.0
0xd783  ldc.i8   0x4000000000000000
0xd78c  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd791  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TZSyncStart
0xd796  ldarg.0
0xd797  ldc.i4.2
0xd798  ldc.i4.0
0xd799  ldc.i4.s 0x11
0xd79b  ldc.i4.4
0xd79c  ldc.i4.2
0xd79d  ldc.i4.0
0xd79e  ldc.i8   0x4000000000000000
0xd7a7  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd7ac  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TZSyncStop
0xd7b1  ldarg.0
0xd7b2  ldc.i4.3
0xd7b3  ldc.i4.0
0xd7b4  ldc.i4.s 0x10
0xd7b6  ldc.i4.4
0xd7b7  ldc.i4.1
0xd7b8  ldc.i4.1
0xd7b9  ldc.i8   0x8000000000000000
0xd7c2  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd7c7  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::InitializationStart
0xd7cc  ldarg.0
0xd7cd  ldc.i4.4
0xd7ce  ldc.i4.0
0xd7cf  ldc.i4.s 0x10
0xd7d1  ldc.i4.4
0xd7d2  ldc.i4.2
0xd7d3  ldc.i4.1
0xd7d4  ldc.i8   0x8000000000000000
0xd7dd  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd7e2  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::InitializationStop
0xd7e7  ldarg.0
0xd7e8  ldc.i4.5
0xd7e9  ldc.i4.0
0xd7ea  ldc.i4.s 0x10
0xd7ec  ldc.i4.4
0xd7ed  ldc.i4.1
0xd7ee  ldc.i4.2
0xd7ef  ldc.i8   0x8000000000000000
0xd7f8  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd7fd  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::ConversionStart
0xd802  ldarg.0
0xd803  ldc.i4.6
0xd804  ldc.i4.0
0xd805  ldc.i4.s 0x10
0xd807  ldc.i4.4
0xd808  ldc.i4.2
0xd809  ldc.i4.2
0xd80a  ldc.i8   0x8000000000000000
0xd813  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd818  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::ConversionStop
0xd81d  ldarg.0
0xd81e  ldc.i4.7
0xd81f  ldc.i4.0
0xd820  ldc.i4.s 0x10
0xd822  ldc.i4.4
0xd823  ldc.i4.1
0xd824  ldc.i4.2
0xd825  ldc.i8   0x8000000000000000
0xd82e  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd833  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TzItemConversionStart
0xd838  ldarg.0
0xd839  ldc.i4.8
0xd83a  ldc.i4.0
0xd83b  ldc.i4.s 0x10
0xd83d  ldc.i4.4
0xd83e  ldc.i4.2
0xd83f  ldc.i4.2
0xd840  ldc.i8   0x8000000000000000
0xd849  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd84e  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TzItemConversionStop
0xd853  ldarg.0
0xd854  ldc.i4.s 9
0xd856  ldc.i4.0
0xd857  ldc.i4.s 0x11
0xd859  ldc.i4.2
0xd85a  ldc.i4.0
0xd85b  ldc.i4.1
0xd85c  ldc.i8   0x4000000000000000
0xd865  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd86a  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::InitializationError
0xd86f  ldarg.0
0xd870  ldc.i4.s 0xA
0xd872  ldc.i4.0
0xd873  ldc.i4.s 0x11
0xd875  ldc.i4.2
0xd876  ldc.i4.0
0xd877  ldc.i4.2
0xd878  ldc.i8   0x4000000000000000
0xd881  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd886  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TzItemConversionError
0xd88b  ldarg.0
0xd88c  ldc.i4.s 0xB
0xd88e  ldc.i4.0
0xd88f  ldc.i4.s 0x11
0xd891  ldc.i4.2
0xd892  ldc.i4.0
0xd893  ldc.i4.2
0xd894  ldc.i8   0x4000000000000000
0xd89d  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd8a2  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::ConversionError
0xd8a7  ldarg.0
0xd8a8  ldc.i4.s 0xC
0xd8aa  ldc.i4.0
0xd8ab  ldc.i4.s 0x11
0xd8ad  ldc.i4.2
0xd8ae  ldc.i4.0
0xd8af  ldc.i4.0
0xd8b0  ldc.i8   0x4000000000000000
0xd8b9  newobj   instance void [System.Core]System.Diagnostics.Eventing.EventDescriptor::.ctor(int32, unsigned int8, unsigned int8, unsigned int8, unsigned int8, int32, int64)
0xd8be  stfld    valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TZSyncError
0xd8c3  ret
```
