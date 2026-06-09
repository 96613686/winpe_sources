# SP_CONTROL::Start(void)

- ea: `0x1400a7330`
- end: `0x1400a776f`
- name: `?Start@SP_CONTROL@@QEAAJXZ`
- size: `1087`
- prototype: `__int64 __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140033590`
- `0x1400a4294`

## callees

- `0x140011970`
- `0x1400a7330`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7371`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7388`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7371`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7388`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a739c`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400a739c`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400a73d7`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400a7423`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400a73d7`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400a7423`
- `ntoskrnl!PcwRegister` at `0x1400a753b`
- `ntoskrnl!PcwRegister` at `0x1400a7595`
- `ntoskrnl!PcwRegister` at `0x1400a75ef`
- `ntoskrnl!PcwRegister` at `0x1400a7649`
- `ntoskrnl!PcwRegister` at `0x1400a76a3`
- `ntoskrnl!PcwRegister` at `0x1400a76fd`
- `ntoskrnl!PcwRegister` at `0x1400a753b`
- `ntoskrnl!PcwRegister` at `0x1400a7595`
- `ntoskrnl!PcwRegister` at `0x1400a75ef`
- `ntoskrnl!PcwRegister` at `0x1400a7649`
- `ntoskrnl!PcwRegister` at `0x1400a76a3`
- `ntoskrnl!PcwRegister` at `0x1400a76fd`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400a7752`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400a7752`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a73f5`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a743e`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a73f5`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a743e`
- `ntoskrnl!IoRegisterLastChanceShutdownNotification` at `0x1400a74e1`
- `ntoskrnl!IoRegisterLastChanceShutdownNotification` at `0x1400a74e1`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a7485`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a74c8`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a7738`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a7485`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a74c8`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400a7738`

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
0x1400a7330  push    rbp
0x1400a7332  push    rbx
0x1400a7333  push    rsi
0x1400a7334  push    rdi
0x1400a7335  push    r14
0x1400a7337  lea     rbp, [rsp-37h]
0x1400a733c  sub     rsp, 0A0h
0x1400a7343  xorps   xmm0, xmm0
0x1400a7346  lea     rdx, aDeviceSpacepor; "\\Device\\Spaceport"
0x1400a734d  mov     rdi, rcx
0x1400a7350  xorps   xmm1, xmm1
0x1400a7353  xor     eax, eax
0x1400a7355  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400a7359  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400a735d  mov     [rbp+57h+var_30], rax
0x1400a7361  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm1
0x1400a7365  movups  xmmword ptr [rbp+57h+Info.Version], xmm0
0x1400a7369  movups  xmmword ptr [rbp+57h+Info.CounterCount], xmm0
0x1400a736d  movups  xmmword ptr [rbp+57h+Info.Callback], xmm0
0x1400a7371  call    cs:__imp_RtlInitUnicodeString
0x1400a7378  nop     dword ptr [rax+rax+00h]
0x1400a737d  lea     rdx, aDosdevicesSpac; "\\DosDevices\\Spaceport"
0x1400a7384  lea     rcx, [rbp+57h+SymbolicLinkName]; DestinationString
0x1400a7388  call    cs:__imp_RtlInitUnicodeString
0x1400a738f  nop     dword ptr [rax+rax+00h]
0x1400a7394  lea     rdx, [rbp+57h+DestinationString]; DeviceName
0x1400a7398  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1400a739c  call    cs:__imp_IoCreateSymbolicLink
0x1400a73a3  nop     dword ptr [rax+rax+00h]
0x1400a73a8  lea     rcx, [rdi+8C0h]; Context
0x1400a73af  xor     r9d, r9d; unsigned __int8
0x1400a73b2  xor     edx, edx; struct _LIST_ENTRY *
0x1400a73b4  mov     r8d, 0EA600h; unsigned int
0x1400a73ba  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400a73bf  mov     rcx, [rdi+18h]; PhysicalDeviceObject
0x1400a73c3  lea     rsi, [rdi+0B30h]
0x1400a73ca  mov     r9, rsi; SymbolicLinkName
0x1400a73cd  lea     rdx, GUID_DEVINTERFACE_SE_MANAGER; InterfaceClassGuid
0x1400a73d4  xor     r8d, r8d; ReferenceString
0x1400a73d7  call    cs:__imp_IoRegisterDeviceInterface
0x1400a73de  nop     dword ptr [rax+rax+00h]
0x1400a73e3  xor     r14d, r14d
0x1400a73e6  mov     ebx, eax
0x1400a73e8  test    eax, eax
0x1400a73ea  js      loc_1400A775E
0x1400a73f0  mov     dl, 1; Enable
0x1400a73f2  mov     rcx, rsi; SymbolicLinkName
0x1400a73f5  call    cs:__imp_IoSetDeviceInterfaceState
0x1400a73fc  nop     dword ptr [rax+rax+00h]
0x1400a7401  mov     ebx, eax
0x1400a7403  test    eax, eax
0x1400a7405  js      loc_1400A775E
0x1400a740b  mov     rcx, [rdi+18h]; PhysicalDeviceObject
0x1400a740f  lea     rsi, [rdi+0B40h]
0x1400a7416  mov     r9, rsi; SymbolicLinkName
0x1400a7419  lea     rdx, VOLMGR_VOLUME_MANAGER_GUID; InterfaceClassGuid
0x1400a7420  xor     r8d, r8d; ReferenceString
0x1400a7423  call    cs:__imp_IoRegisterDeviceInterface
0x1400a742a  nop     dword ptr [rax+rax+00h]
0x1400a742f  mov     ebx, eax
0x1400a7431  test    eax, eax
0x1400a7433  js      loc_1400A775E
0x1400a7439  mov     dl, 1; Enable
0x1400a743b  mov     rcx, rsi; SymbolicLinkName
0x1400a743e  call    cs:__imp_IoSetDeviceInterfaceState
0x1400a7445  nop     dword ptr [rax+rax+00h]
0x1400a744a  mov     ebx, eax
0x1400a744c  test    eax, eax
0x1400a744e  js      loc_1400A775E
0x1400a7454  mov     r9, [rdi+8]; DriverObject
0x1400a7458  lea     rax, [rdi+0B50h]
0x1400a745f  mov     [rsp+0C0h+NotificationEntry], rax; NotificationEntry
0x1400a7464  lea     edx, [r14+1]; EventCategoryFlags
0x1400a7468  lea     esi, [rdx+1]
0x1400a746b  mov     [rsp+0C0h+Context], r14; Context
0x1400a7470  lea     rax, ?SpEnclosureNotification@@YAJPEAX0@Z; SpEnclosureNotification(void *,void *)
0x1400a7477  mov     ecx, esi; EventCategory
0x1400a7479  lea     r8, GUID_DEVINTERFACE_SES; EventCategoryData
0x1400a7480  mov     [rsp+0C0h+CallbackRoutine], rax; CallbackRoutine
0x1400a7485  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400a748c  nop     dword ptr [rax+rax+00h]
0x1400a7491  mov     ebx, eax
0x1400a7493  test    eax, eax
0x1400a7495  js      loc_1400A775E
0x1400a749b  mov     r9, [rdi+8]; DriverObject
0x1400a749f  lea     rax, [rdi+0B58h]
0x1400a74a6  mov     [rsp+0C0h+NotificationEntry], rax; NotificationEntry
0x1400a74ab  lea     r8, GUID_DEVINTERFACE_PR_MANAGER; EventCategoryData
0x1400a74b2  lea     rax, ?SpPrmNotification@@YAJPEAX0@Z; SpPrmNotification(void *,void *)
0x1400a74b9  mov     [rsp+0C0h+Context], r14; Context
0x1400a74be  lea     edx, [rsi-1]; EventCategoryFlags
0x1400a74c1  mov     [rsp+0C0h+CallbackRoutine], rax; CallbackRoutine
0x1400a74c6  mov     ecx, esi; EventCategory
0x1400a74c8  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400a74cf  nop     dword ptr [rax+rax+00h]
0x1400a74d4  mov     ebx, eax
0x1400a74d6  test    eax, eax
0x1400a74d8  js      loc_1400A775E
0x1400a74de  mov     rcx, [rdi]; DeviceObject
0x1400a74e1  call    cs:__imp_IoRegisterLastChanceShutdownNotification
0x1400a74e8  nop     dword ptr [rax+rax+00h]
0x1400a74ed  mov     ebx, eax
0x1400a74ef  test    eax, eax
0x1400a74f1  js      loc_1400A775E
0x1400a74f7  lea     rax, ?Name@?1??SpInitRegistrationInformationSpaceCounterSet@@9@4U_UNICODE_STRING@@B; "68"
0x1400a74fe  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a7506  mov     [rbp+57h+Info.Name], rax
0x1400a750a  lea     rdx, [rbp+57h+Info]; Info
0x1400a750e  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationSpaceCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationSpaceCounterSet'::`2'::Descriptors
0x1400a7515  mov     qword ptr [rbp+57h+Info.CounterCount], 40h ; '@'
0x1400a751d  mov     [rbp+57h+Info.Counters], rax
0x1400a7521  lea     rcx, SpSpaceCounterSet; Registration
0x1400a7528  lea     rax, ?SpSpaceCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpSpaceCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a752f  mov     [rbp+57h+var_30], r14
0x1400a7533  mov     [rbp+57h+Info.Callback], rax
0x1400a7537  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a753b  call    cs:__imp_PcwRegister
0x1400a7542  nop     dword ptr [rax+rax+00h]
0x1400a7547  mov     ebx, eax
0x1400a7549  test    eax, eax
0x1400a754b  js      loc_1400A775E
0x1400a7551  lea     rax, ?Name@?1??SpInitRegistrationInformationSpaceIoCounterSet@@9@4U_UNICODE_STRING@@B; "<>"
0x1400a7558  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a7560  mov     [rbp+57h+Info.Name], rax
0x1400a7564  lea     rdx, [rbp+57h+Info]; Info
0x1400a7568  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationSpaceIoCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationSpaceIoCounterSet'::`2'::Descriptors
0x1400a756f  mov     qword ptr [rbp+57h+Info.CounterCount], 8
0x1400a7577  mov     [rbp+57h+Info.Counters], rax
0x1400a757b  lea     rcx, SpSpaceIoCounterSet; Registration
0x1400a7582  lea     rax, ?SpSpaceIoCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpSpaceIoCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a7589  mov     [rbp+57h+var_30], r14
0x1400a758d  mov     [rbp+57h+Info.Callback], rax
0x1400a7591  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a7595  call    cs:__imp_PcwRegister
0x1400a759c  nop     dword ptr [rax+rax+00h]
0x1400a75a1  mov     ebx, eax
0x1400a75a3  test    eax, eax
0x1400a75a5  js      loc_1400A775E
0x1400a75ab  lea     rax, ?Name@?1??SpInitRegistrationInformationSpaceMapCounterSet@@9@4U_UNICODE_STRING@@B; ">@"
0x1400a75b2  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a75ba  mov     [rbp+57h+Info.Name], rax
0x1400a75be  lea     rdx, [rbp+57h+Info]; Info
0x1400a75c2  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationSpaceMapCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationSpaceMapCounterSet'::`2'::Descriptors
0x1400a75c9  mov     qword ptr [rbp+57h+Info.CounterCount], 9
0x1400a75d1  mov     [rbp+57h+Info.Counters], rax
0x1400a75d5  lea     rcx, SpSpaceMapCounterSet; Registration
0x1400a75dc  lea     rax, ?SpSpaceMapCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpSpaceMapCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a75e3  mov     [rbp+57h+var_30], r14
0x1400a75e7  mov     [rbp+57h+Info.Callback], rax
0x1400a75eb  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a75ef  call    cs:__imp_PcwRegister
0x1400a75f6  nop     dword ptr [rax+rax+00h]
0x1400a75fb  mov     ebx, eax
0x1400a75fd  test    eax, eax
0x1400a75ff  js      loc_1400A775E
0x1400a7605  lea     rax, ?Name@?1??SpInitRegistrationInformationTierCounterSet@@9@4U_UNICODE_STRING@@B; "&("
0x1400a760c  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a7614  mov     [rbp+57h+Info.Name], rax
0x1400a7618  lea     rdx, [rbp+57h+Info]; Info
0x1400a761c  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationTierCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationTierCounterSet'::`2'::Descriptors
0x1400a7623  mov     qword ptr [rbp+57h+Info.CounterCount], 13h
0x1400a762b  mov     [rbp+57h+Info.Counters], rax
0x1400a762f  lea     rcx, SpTierCounterSet; Registration
0x1400a7636  lea     rax, ?SpTierCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpTierCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a763d  mov     [rbp+57h+var_30], r14
0x1400a7641  mov     [rbp+57h+Info.Callback], rax
0x1400a7645  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a7649  call    cs:__imp_PcwRegister
0x1400a7650  nop     dword ptr [rax+rax+00h]
0x1400a7655  mov     ebx, eax
0x1400a7657  test    eax, eax
0x1400a7659  js      loc_1400A775E
0x1400a765f  lea     rax, ?Name@?1??SpInitRegistrationInformationCacheCounterSet@@9@4U_UNICODE_STRING@@B; "46"
0x1400a7666  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a766e  mov     [rbp+57h+Info.Name], rax
0x1400a7672  lea     rdx, [rbp+57h+Info]; Info
0x1400a7676  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationCacheCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationCacheCounterSet'::`2'::Descriptors
0x1400a767d  mov     qword ptr [rbp+57h+Info.CounterCount], 28h ; '('
0x1400a7685  mov     [rbp+57h+Info.Counters], rax
0x1400a7689  lea     rcx, SpCacheCounterSet; Registration
0x1400a7690  lea     rax, ?SpCacheCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpCacheCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a7697  mov     [rbp+57h+var_30], r14
0x1400a769b  mov     [rbp+57h+Info.Callback], rax
0x1400a769f  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a76a3  call    cs:__imp_PcwRegister
0x1400a76aa  nop     dword ptr [rax+rax+00h]
0x1400a76af  mov     ebx, eax
0x1400a76b1  test    eax, eax
0x1400a76b3  js      loc_1400A775E
0x1400a76b9  lea     rax, ?Name@?1??SpInitRegistrationInformationDrtCounterSet@@9@4U_UNICODE_STRING@@B; "$&"
0x1400a76c0  mov     qword ptr [rbp+57h+Info.Version], 100h
0x1400a76c8  mov     [rbp+57h+Info.Name], rax
0x1400a76cc  lea     rdx, [rbp+57h+Info]; Info
0x1400a76d0  lea     rax, ?Descriptors@?1??SpInitRegistrationInformationDrtCounterSet@@9@4QBU_PCW_COUNTER_DESCRIPTOR@@B; _PCW_COUNTER_DESCRIPTOR const near * const `SpInitRegistrationInformationDrtCounterSet'::`2'::Descriptors
0x1400a76d7  mov     qword ptr [rbp+57h+Info.CounterCount], 0Bh
0x1400a76df  mov     [rbp+57h+Info.Counters], rax
0x1400a76e3  lea     rcx, SpDrtCounterSet; Registration
0x1400a76ea  lea     rax, ?SpDrtCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z; SpDrtCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)
0x1400a76f1  mov     [rbp+57h+var_30], r14
0x1400a76f5  mov     [rbp+57h+Info.Callback], rax
0x1400a76f9  mov     [rbp+57h+Info.CallbackContext], r14
0x1400a76fd  call    cs:__imp_PcwRegister
0x1400a7704  nop     dword ptr [rax+rax+00h]
0x1400a7709  mov     ebx, eax
0x1400a770b  test    eax, eax
0x1400a770d  js      short loc_1400A775E
0x1400a770f  mov     r9, [rdi+8]; DriverObject
0x1400a7713  lea     rax, [rdi+0BB8h]
0x1400a771a  mov     [rsp+0C0h+NotificationEntry], rax; NotificationEntry
0x1400a771f  lea     ecx, [rsi+2]; EventCategory
0x1400a7722  lea     rax, ?SpKsrNotification@@YAJPEAX0@Z; SpKsrNotification(void *,void *)
0x1400a7729  mov     [rsp+0C0h+Context], r14; Context
0x1400a772e  xor     r8d, r8d; EventCategoryData
0x1400a7731  mov     [rsp+0C0h+CallbackRoutine], rax; CallbackRoutine
0x1400a7736  xor     edx, edx; EventCategoryFlags
0x1400a7738  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400a773f  nop     dword ptr [rax+rax+00h]
0x1400a7744  mov     rcx, [rdi+8]; DriverObject
0x1400a7748  lea     rdx, ?SpDriverReinitialization@@YAXPEAU_DRIVER_OBJECT@@PEAXK@Z; DriverReinitializationRoutine
0x1400a774f  xor     r8d, r8d; Context
0x1400a7752  call    cs:__imp_IoRegisterDriverReinitialization
0x1400a7759  nop     dword ptr [rax+rax+00h]
0x1400a775e  mov     eax, ebx
0x1400a7760  add     rsp, 0A0h
0x1400a7767  pop     r14
0x1400a7769  pop     rdi
0x1400a776a  pop     rsi
0x1400a776b  pop     rbx
0x1400a776c  pop     rbp
0x1400a776d  retn
```
