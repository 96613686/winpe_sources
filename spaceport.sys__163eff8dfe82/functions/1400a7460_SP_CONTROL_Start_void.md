# SP_CONTROL::Start(void)

- ea: `0x1400a7460`
- end: `0x1400a789f`
- name: `?Start@SP_CONTROL@@QEAAJXZ`
- size: `1087`
- prototype: `__int64 __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140033640`
- `0x1400a43c4`

## callees

- `0x140011970`
- `0x1400a7460`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400a74a1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a74b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a74a1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a74b8`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a74cc`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a74cc`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400a7507`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400a7553`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400a7507`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400a7553`
- `ntoskrnl!PcwRegister` at `0x1400a766b`
- `ntoskrnl!PcwRegister` at `0x1400a76c5`
- `ntoskrnl!PcwRegister` at `0x1400a771f`
- `ntoskrnl!PcwRegister` at `0x1400a7779`
- `ntoskrnl!PcwRegister` at `0x1400a77d3`
- `ntoskrnl!PcwRegister` at `0x1400a782d`
- `ntoskrnl!PcwRegister` at `0x1400a766b`
- `ntoskrnl!PcwRegister` at `0x1400a76c5`
- `ntoskrnl!PcwRegister` at `0x1400a771f`
- `ntoskrnl!PcwRegister` at `0x1400a7779`
- `ntoskrnl!PcwRegister` at `0x1400a77d3`
- `ntoskrnl!PcwRegister` at `0x1400a782d`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400a7882`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400a7882`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a7525`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a756e`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a7525`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a756e`
- `ntoskrnl!IoRegisterLastChanceShutdownNotification` at `0x1400a7611`
- `ntoskrnl!IoRegisterLastChanceShutdownNotification` at `0x1400a7611`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a75b5`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a75f8`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a7868`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a75b5`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a75f8`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a7868`

## pseudocode

```c
__int64 __fastcall SP_CONTROL::Start(SP_CONTROL *this)
{
  NTSTATUS ChanceShutdownNotification; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+50h] [rbp-19h] BYREF
  _PCW_REGISTRATION_INFORMATION Info; // [rsp+60h] [rbp-9h] BYREF
  __int64 v7; // [rsp+90h] [rbp+27h]

  DestinationString = 0;
  v7 = 0;
  SymbolicLinkName = 0;
  memset(&Info, 0, sizeof(Info));
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Spaceport");
  RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\Spaceport");
  IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
  SP_WORKITEM::Insert((char *)this + 2240, 0, 0xEA600u, 0);
  ChanceShutdownNotification = IoRegisterDeviceInterface(
                                 *((PDEVICE_OBJECT *)this + 3),
                                 &GUID_DEVINTERFACE_SE_MANAGER,
                                 0,
                                 (PUNICODE_STRING)this + 179);
  if ( ChanceShutdownNotification >= 0 )
  {
    ChanceShutdownNotification = IoSetDeviceInterfaceState((PUNICODE_STRING)this + 179, 1u);
    if ( ChanceShutdownNotification >= 0 )
    {
      ChanceShutdownNotification = IoRegisterDeviceInterface(
                                     *((PDEVICE_OBJECT *)this + 3),
                                     &VOLMGR_VOLUME_MANAGER_GUID,
                                     0,
                                     (PUNICODE_STRING)this + 180);
      if ( ChanceShutdownNotification >= 0 )
      {
        ChanceShutdownNotification = IoSetDeviceInterfaceState((PUNICODE_STRING)this + 180, 1u);
        if ( ChanceShutdownNotification >= 0 )
        {
          ChanceShutdownNotification = IoRegisterPlugPlayNotification(
                                         EventCategoryDeviceInterfaceChange,
                                         1u,
                                         &GUID_DEVINTERFACE_SES,
                                         *((PDRIVER_OBJECT *)this + 1),
                                         SpEnclosureNotification,
                                         0,
                                         (PVOID *)this + 362);
          if ( ChanceShutdownNotification >= 0 )
          {
            ChanceShutdownNotification = IoRegisterPlugPlayNotification(
                                           EventCategoryDeviceInterfaceChange,
                                           1u,
                                           &GUID_DEVINTERFACE_PR_MANAGER,
                                           *((PDRIVER_OBJECT *)this + 1),
                                           SpPrmNotification,
                                           0,
                                           (PVOID *)this + 363);
            if ( ChanceShutdownNotification >= 0 )
            {
              ChanceShutdownNotification = IoRegisterLastChanceShutdownNotification(*(PDEVICE_OBJECT *)this);
              if ( ChanceShutdownNotification >= 0 )
              {
                *(_QWORD *)&Info.Version = 256;
                Info.Name = (PCUNICODE_STRING)L"68";
                *(_QWORD *)&Info.CounterCount = 64;
                Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`SpInitRegistrationInformationSpaceCounterSet'::`2'::Descriptors;
                v7 = 0;
                Info.Callback = (PPCW_CALLBACK)SpSpaceCounterSetCallback;
                Info.CallbackContext = 0;
                ChanceShutdownNotification = PcwRegister(&SpSpaceCounterSet, &Info);
                if ( ChanceShutdownNotification >= 0 )
                {
                  *(_QWORD *)&Info.Version = 256;
                  Info.Name = (PCUNICODE_STRING)L"<>";
                  *(_QWORD *)&Info.CounterCount = 8;
                  Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`SpInitRegistrationInformationSpaceIoCounterSet'::`2'::Descriptors;
                  v7 = 0;
                  Info.Callback = (PPCW_CALLBACK)SpSpaceIoCounterSetCallback;
                  Info.CallbackContext = 0;
                  ChanceShutdownNotification = PcwRegister(&SpSpaceIoCounterSet, &Info);
                  if ( ChanceShutdownNotification >= 0 )
                  {
                    *(_QWORD *)&Info.Version = 256;
                    Info.Name = (PCUNICODE_STRING)L">@";
                    *(_QWORD *)&Info.CounterCount = 9;
                    Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`SpInitRegistrationInformationSpaceMapCounterSet'::`2'::Descriptors;
                    v7 = 0;
                    Info.Callback = (PPCW_CALLBACK)SpSpaceMapCounterSetCallback;
                    Info.CallbackContext = 0;
                    ChanceShutdownNotification = PcwRegister(&SpSpaceMapCounterSet, &Info);
                    if ( ChanceShutdownNotification >= 0 )
                    {
                      *(_QWORD *)&Info.Version = 256;
                      Info.Name = (PCUNICODE_STRING)L"&(";
                      *(_QWORD *)&Info.CounterCount = 19;
                      Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`SpInitRegistrationInformationTierCounterSet'::`2'::Descriptors;
                      v7 = 0;
                      Info.Callback = (PPCW_CALLBACK)SpTierCounterSetCallback;
                      Info.CallbackContext = 0;
                      ChanceShutdownNotification = PcwRegister(&SpTierCounterSet, &Info);
                      if ( ChanceShutdownNotification >= 0 )
                      {
                        *(_QWORD *)&Info.Version = 256;
                        Info.Name = (PCUNICODE_STRING)L"46";
                        *(_QWORD *)&Info.CounterCount = 40;
                        Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`SpInitRegistrationInformationCacheCounterSet'::`2'::Descriptors;
                        v7 = 0;
                        Info.Callback = (PPCW_CALLBACK)SpCacheCounterSetCallback;
                        Info.CallbackContext = 0;
                        ChanceShutdownNotification = PcwRegister(&SpCacheCounterSet, &Info);
                        if ( ChanceShutdownNotification >= 0 )
                        {
                          *(_QWORD *)&Info.Version = 256;
                          Info.Name = (PCUNICODE_STRING)L"$&";
                          *(_QWORD *)&Info.CounterCount = 11;
                          Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`SpInitRegistrationInformationDrtCounterSet'::`2'::Descriptors;
                          v7 = 0;
                          Info.Callback = (PPCW_CALLBACK)SpDrtCounterSetCallback;
                          Info.CallbackContext = 0;
                          ChanceShutdownNotification = PcwRegister(&SpDrtCounterSet, &Info);
                          if ( ChanceShutdownNotification >= 0 )
                          {
                            IoRegisterPlugPlayNotification(
                              (IO_NOTIFICATION_EVENT_CATEGORY)4,
                              0,
                              0,
                              *((PDRIVER_OBJECT *)this + 1),
                              SpKsrNotification,
                              0,
                              (PVOID *)this + 375);
                            IoRegisterDriverReinitialization(*((PDRIVER_OBJECT *)this + 1), SpDriverReinitialization, 0);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)ChanceShutdownNotification;
}

```

## disassembly

```asm
0x1400a7460  push    rbp
0x1400a7462  push    rbx
0x1400a7463  push    rsi
0x1400a7464  push    rdi
0x1400a7465  push    r14
0x1400a7467  lea     rbp, [rsp-37h]
0x1400a746c  sub     rsp, 0A0h
0x1400a7473  xorps   xmm0, xmm0
0x1400a7476  lea     rdx, aDeviceSpacepor; "\\Device\\Spaceport"
0x1400a747d  mov     rdi, rcx
0x1400a7480  xorps   xmm1, xmm1
0x1400a7483  xor     eax, eax
0x1400a7485  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400a7489  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400a748d  mov     [rbp+57h+var_30], rax
0x1400a7491  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm1
0x1400a7495  movups  xmmword ptr [rbp+57h+Info.Version], xmm0
0x1400a7499  movups  xmmword ptr [rbp+57h+Info.CounterCount], xmm0
0x1400a749d  movups  xmmword ptr [rbp+57h+Info.Callback], xmm0
0x1400a74a1  call    cs:__imp_RtlInitUnicodeString
0x1400a74a8  nop     dword ptr [rax+rax+00h]
0x1400a74ad  lea     rdx, aDosdevicesSpac; "\\DosDevices\\Spaceport"
0x1400a74b4  lea     rcx, [rbp+57h+SymbolicLinkName]; DestinationString
0x1400a74b8  call    cs:__imp_RtlInitUnicodeString
0x1400a74bf  nop     dword ptr [rax+rax+00h]
0x1400a74c4  lea     rdx, [rbp+57h+DestinationString]; DeviceName
0x1400a74c8  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1400a74cc  call    cs:__imp_IoCreateSymbolicLink
0x1400a74d3  nop     dword ptr [rax+rax+00h]
0x1400a74d8  lea     rcx, [rdi+8C0h]; Context
0x1400a74df  xor     r9d, r9d; unsigned __int8
0x1400a74e2  xor     edx, edx; struct _LIST_ENTRY *
0x1400a74e4  mov     r8d, 0EA600h; unsigned int
0x1400a74ea  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400a74ef  mov     rcx, [rdi+18h]; PhysicalDeviceObject
0x1400a74f3  lea     rsi, [rdi+0B30h]
0x1400a74fa  mov     r9, rsi; SymbolicLinkName
0x1400a74fd  lea     rdx, GUID_DEVINTERFACE_SE_MANAGER; InterfaceClassGuid
0x1400a7504  xor     r8d, r8d; ReferenceString
0x1400a7507  call    cs:__imp_IoRegisterDeviceInterface
0x1400a750e  nop     dword ptr [rax+rax+00h]
0x1400a7513  xor     r14d, r14d
0x1400a7516  mov     ebx, eax
0x1400a7518  test    eax, eax
0x1400a751a  js      loc_1400A788E
0x1400a7520  mov     dl, 1; Enable
0x1400a7522  mov     rcx, rsi; SymbolicLinkName
0x1400a7525  call    cs:__imp_IoSetDeviceInterfaceState
0x1400a752c  nop     dword ptr [rax+rax+00h]
0x1400a7531  mov     ebx, eax
0x1400a7533  test    eax, eax
0x1400a7535  js      loc_1400A788E
0x1400a753b  mov     rcx, [rdi+18h]; PhysicalDeviceObject
0x1400a753f  lea     rsi, [rdi+0B40h]
0x1400a7546  mov     r9, rsi; SymbolicLinkName
0x1400a7549  lea     rdx, VOLMGR_VOLUME_MANAGER_GUID; InterfaceClassGuid
0x1400a7550  xor     r8d, r8d; ReferenceString
0x1400a7553  call    cs:__imp_IoRegisterDeviceInterface
0x1400a755a  nop     dword ptr [rax+rax+00h]
0x1400a755f  mov     ebx, eax
0x1400a7561  test    eax, eax
0x1400a7563  js      loc_1400A788E
0x1400a7569  mov     dl, 1; Enable
0x1400a756b  mov     rcx, rsi; SymbolicLinkName
0x1400a756e  call    cs:__imp_IoSetDeviceInterfaceState
0x1400a7575  nop     dword ptr [rax+rax+00h]
0x1400a757a  mov     ebx, eax
0x1400a757c  test    eax, eax
0x1400a757e  js      loc_1400A788E
0x1400a7584  mov     r9, [rdi+8]; DriverObject
0x1400a7588  lea     rax, [rdi+0B50h]
0x1400a758f  mov     [rsp+0C0h+NotificationEntry], rax; NotificationEntry
0x1400a7594  lea     edx, [r14+1]; EventCategoryFlags
0x1400a7598  lea     esi, [rdx+1]
0x1400a759b  mov     [rsp+0C0h+Context], r14; Context
0x1400a75a0  lea     rax, ?SpEnclosureNotification@@YAJPEAX0@Z; SpEnclosureNotification(void *,void *)
0x1400a75a7  mov     ecx, esi; EventCategory
0x1400a75a9  lea     r8, GUID_DEVINTERFACE_SES; EventCategoryData
0x1400a75b0  mov     [rsp+0C0h+CallbackRoutine], rax; CallbackRoutine
0x1400a75b5  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400a75bc  nop     dword ptr [rax+rax+00h]
0x1400a75c1  mov     ebx, eax
0x1400a75c3  test    eax, eax
0x1400a75c5  js      loc_1400A788E
0x1400a75cb  mov     r9, [rdi+8]; DriverObject
0x1400a75cf  lea     rax, [rdi+0B58h]
0x1400a75d6  mov     [rsp+0C0h+NotificationEntry], rax; NotificationEntry
0x1400a75db  lea     r8, GUID_DEVINTERFACE_PR_MANAGER; EventCategoryData
0x1400a75e2  lea     rax, ?SpPrmNotification@@YAJPEAX0@Z; SpPrmNotification(void *,void *)
0x1400a75e9  mov     [rsp+0C0h+Context], r14; Context
0x1400a75ee  lea     edx, [rsi-1]; EventCategoryFlags
0x1400a75f1  mov     [rsp+0C0h+CallbackRoutine], rax; CallbackRoutine
0x1400a75f6  mov     ecx, esi; EventCategory
0x1400a75f8  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400a75ff  nop     dword ptr [rax+rax+00h]
0x1400a7604  mov     ebx, eax
0x1400a7606  test    eax, eax
0x1400a7608  js      loc_1400A788E
0x1400a760e  mov     rcx, [rdi]; DeviceObject
0x1400a7611  call    cs:__imp_IoRegisterLastChanceShutdownNotification
0x1400a7618  nop     dword ptr [rax+rax+00h]
0x1400a761d  mov     ebx, eax
0x1400a761f  test    eax, eax
0x1400a7621  js      loc_1400A788E
0x1400a7627  lea     rax, ?Name@?1??SpInitRegistrationInformationSpaceCounterSet@@9@4U_UNICODE_STRING@@B; "68"
0x1400a762e  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a7636  mov     [rbp+57h+Info.Name], rax
0x1400a763a  lea     rdx, [rbp+57h+Info]; Info
0x1400a763e  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationSpaceCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationSpaceCounterSet'::`2'::Descriptors
0x1400a7645  mov     qword ptr [rbp+57h+Info.CounterCount], 40h ; '@'
0x1400a764d  mov     [rbp+57h+Info.Counters], rax
0x1400a7651  lea     rcx, SpSpaceCounterSet; Registration
0x1400a7658  lea     rax, ?SpSpaceCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpSpaceCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a765f  mov     [rbp+57h+var_30], r14
0x1400a7663  mov     [rbp+57h+Info.Callback], rax
0x1400a7667  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a766b  call    cs:__imp_PcwRegister
0x1400a7672  nop     dword ptr [rax+rax+00h]
0x1400a7677  mov     ebx, eax
0x1400a7679  test    eax, eax
0x1400a767b  js      loc_1400A788E
0x1400a7681  lea     rax, ?Name@?1??SpInitRegistrationInformationSpaceIoCounterSet@@9@4U_UNICODE_STRING@@B; "<>"
0x1400a7688  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a7690  mov     [rbp+57h+Info.Name], rax
0x1400a7694  lea     rdx, [rbp+57h+Info]; Info
0x1400a7698  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationSpaceIoCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationSpaceIoCounterSet'::`2'::Descriptors
0x1400a769f  mov     qword ptr [rbp+57h+Info.CounterCount], 8
0x1400a76a7  mov     [rbp+57h+Info.Counters], rax
0x1400a76ab  lea     rcx, SpSpaceIoCounterSet; Registration
0x1400a76b2  lea     rax, ?SpSpaceIoCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpSpaceIoCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a76b9  mov     [rbp+57h+var_30], r14
0x1400a76bd  mov     [rbp+57h+Info.Callback], rax
0x1400a76c1  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a76c5  call    cs:__imp_PcwRegister
0x1400a76cc  nop     dword ptr [rax+rax+00h]
0x1400a76d1  mov     ebx, eax
0x1400a76d3  test    eax, eax
0x1400a76d5  js      loc_1400A788E
0x1400a76db  lea     rax, ?Name@?1??SpInitRegistrationInformationSpaceMapCounterSet@@9@4U_UNICODE_STRING@@B; ">@"
0x1400a76e2  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a76ea  mov     [rbp+57h+Info.Name], rax
0x1400a76ee  lea     rdx, [rbp+57h+Info]; Info
0x1400a76f2  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationSpaceMapCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationSpaceMapCounterSet'::`2'::Descriptors
0x1400a76f9  mov     qword ptr [rbp+57h+Info.CounterCount], 9
0x1400a7701  mov     [rbp+57h+Info.Counters], rax
0x1400a7705  lea     rcx, SpSpaceMapCounterSet; Registration
0x1400a770c  lea     rax, ?SpSpaceMapCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpSpaceMapCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a7713  mov     [rbp+57h+var_30], r14
0x1400a7717  mov     [rbp+57h+Info.Callback], rax
0x1400a771b  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a771f  call    cs:__imp_PcwRegister
0x1400a7726  nop     dword ptr [rax+rax+00h]
0x1400a772b  mov     ebx, eax
0x1400a772d  test    eax, eax
0x1400a772f  js      loc_1400A788E
0x1400a7735  lea     rax, ?Name@?1??SpInitRegistrationInformationTierCounterSet@@9@4U_UNICODE_STRING@@B; "&("
0x1400a773c  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a7744  mov     [rbp+57h+Info.Name], rax
0x1400a7748  lea     rdx, [rbp+57h+Info]; Info
0x1400a774c  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationTierCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationTierCounterSet'::`2'::Descriptors
0x1400a7753  mov     qword ptr [rbp+57h+Info.CounterCount], 13h
0x1400a775b  mov     [rbp+57h+Info.Counters], rax
0x1400a775f  lea     rcx, SpTierCounterSet; Registration
0x1400a7766  lea     rax, ?SpTierCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpTierCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a776d  mov     [rbp+57h+var_30], r14
0x1400a7771  mov     [rbp+57h+Info.Callback], rax
0x1400a7775  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a7779  call    cs:__imp_PcwRegister
0x1400a7780  nop     dword ptr [rax+rax+00h]
0x1400a7785  mov     ebx, eax
0x1400a7787  test    eax, eax
0x1400a7789  js      loc_1400A788E
0x1400a778f  lea     rax, ?Name@?1??SpInitRegistrationInformationCacheCounterSet@@9@4U_UNICODE_STRING@@B; "46"
0x1400a7796  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a779e  mov     [rbp+57h+Info.Name], rax
0x1400a77a2  lea     rdx, [rbp+57h+Info]; Info
0x1400a77a6  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationCacheCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationCacheCounterSet'::`2'::Descriptors
0x1400a77ad  mov     qword ptr [rbp+57h+Info.CounterCount], 28h ; '('
0x1400a77b5  mov     [rbp+57h+Info.Counters], rax
0x1400a77b9  lea     rcx, SpCacheCounterSet; Registration
0x1400a77c0  lea     rax, ?SpCacheCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpCacheCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a77c7  mov     [rbp+57h+var_30], r14
0x1400a77cb  mov     [rbp+57h+Info.Callback], rax
0x1400a77cf  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a77d3  call    cs:__imp_PcwRegister
0x1400a77da  nop     dword ptr [rax+rax+00h]
0x1400a77df  mov     ebx, eax
0x1400a77e1  test    eax, eax
0x1400a77e3  js      loc_1400A788E
0x1400a77e9  lea     rax, ?Name@?1??SpInitRegistrationInformationDrtCounterSet@@9@4U_UNICODE_STRING@@B; "$&"
0x1400a77f0  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a77f8  mov     [rbp+57h+Info.Name], rax
0x1400a77fc  lea     rdx, [rbp+57h+Info]; Info
0x1400a7800  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationDrtCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationDrtCounterSet'::`2'::Descriptors
0x1400a7807  mov     qword ptr [rbp+57h+Info.CounterCount], 0Bh
0x1400a780f  mov     [rbp+57h+Info.Counters], rax
0x1400a7813  lea     rcx, SpDrtCounterSet; Registration
0x1400a781a  lea     rax, ?SpDrtCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpDrtCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a7821  mov     [rbp+57h+var_30], r14
0x1400a7825  mov     [rbp+57h+Info.Callback], rax
0x1400a7829  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a782d  call    cs:__imp_PcwRegister
0x1400a7834  nop     dword ptr [rax+rax+00h]
0x1400a7839  mov     ebx, eax
0x1400a783b  test    eax, eax
0x1400a783d  js      short loc_1400A788E
0x1400a783f  mov     r9, [rdi+8]; DriverObject
0x1400a7843  lea     rax, [rdi+0BB8h]
0x1400a784a  mov     [rsp+0C0h+NotificationEntry], rax; NotificationEntry
0x1400a784f  lea     ecx, [rsi+2]; EventCategory
0x1400a7852  lea     rax, ?SpKsrNotification@@YAJPEAX0@Z; SpKsrNotification(void *,void *)
0x1400a7859  mov     [rsp+0C0h+Context], r14; Context
0x1400a785e  xor     r8d, r8d; EventCategoryData
0x1400a7861  mov     [rsp+0C0h+CallbackRoutine], rax; CallbackRoutine
0x1400a7866  xor     edx, edx; EventCategoryFlags
0x1400a7868  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400a786f  nop     dword ptr [rax+rax+00h]
0x1400a7874  mov     rcx, [rdi+8]; DriverObject
0x1400a7878  lea     rdx, ?SpDriverReinitialization@@YAXPEAU_DRIVER_OBJECT@@PEAXK@Z; DriverReinitializationRoutine
0x1400a787f  xor     r8d, r8d; Context
0x1400a7882  call    cs:__imp_IoRegisterDriverReinitialization
0x1400a7889  nop     dword ptr [rax+rax+00h]
0x1400a788e  mov     eax, ebx
0x1400a7890  add     rsp, 0A0h
0x1400a7897  pop     r14
0x1400a7899  pop     rdi
0x1400a789a  pop     rsi
0x1400a789b  pop     rbx
0x1400a789c  pop     rbp
0x1400a789d  retn
```
