# TmInitSystemPhase2Ext

- ea: `0x14000dff0`
- end: `0x14000e27f`
- name: `TmInitSystemPhase2Ext`
- size: `655`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001a0c`
- `0x1400024e0`
- `0x14000dff0`
- `0x14000f120`
- `0x14000f1b4`
- `0x1400242b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e148`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e148`
- `ntoskrnl!KeInitializeTimer` at `0x14000e15b`
- `ntoskrnl!KeInitializeTimer` at `0x14000e15b`
- `ntoskrnl!KeInitializeDpc` at `0x14000e178`
- `ntoskrnl!KeInitializeDpc` at `0x14000e178`
- `ntoskrnl!RtlGUIDFromString` at `0x14000e130`
- `ntoskrnl!RtlGUIDFromString` at `0x14000e130`
- `ntoskrnl!KeSetTimer` at `0x14000e199`
- `ntoskrnl!KeSetTimer` at `0x14000e199`
- `ntoskrnl!EtwRegister` at `0x14000e1b8`
- `ntoskrnl!EtwRegister` at `0x14000e1d7`
- `ntoskrnl!EtwRegister` at `0x14000e1b8`
- `ntoskrnl!EtwRegister` at `0x14000e1d7`

## string_xrefs

- `0x14000e0ac`: `\Registry\Machine\Software\Microsoft\MSDTC\KtmRm`
- `0x14000e028`: `\Registry\Machine\System\CurrentControlSet\Control\KTM`

## pseudocode

```c
__int64 TmInitSystemPhase2Ext()
{
  LARGE_INTEGER v0; // rax
  NTSTATUS v1; // eax
  PVOID v2; // rbx
  __int64 result; // rax
  _BYTE v4[4]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v5; // [rsp+34h] [rbp-CCh] BYREF
  PVOID P; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING v7; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING v8; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING GuidString; // [rsp+60h] [rbp-A0h] BYREF
  char v10; // [rsp+70h] [rbp-90h] BYREF

  *(_QWORD *)&v8.Length = 7209068;
  P = &v10;
  *(_QWORD *)&v7.Length = 3801144;
  v8.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\KTM";
  v4[0] = 0;
  v7.Buffer = L"TmAdvanceTailWarningInterval";
  v5 = 156;
  GuidString = 0;
  if ( TmpQueryValueKey(&v8, &v7, &v5, &P, v4) >= 0 )
    v0.QuadPart = -10000000LL * (unsigned int)-*(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  else
    v0.QuadPart = -9000000000LL;
  TmpTmAdvanceTailWarningInterval = v0;
  *(_DWORD *)&v8.Length = 6422624;
  v8.Buffer = L"\\Registry\\Machine\\Software\\Microsoft\\MSDTC\\KtmRm";
  *(_DWORD *)&v7.Length = 2359330;
  v7.Buffer = L"KtmRmTmIdentifier";
  v1 = TmpQueryValueKey(&v8, &v7, &v5, &P, v4);
  v2 = P;
  if ( v1 >= 0 )
  {
    GuidString.Buffer = (wchar_t *)((char *)P + *((unsigned int *)P + 2));
    GuidString.Length = *((_WORD *)P + 6);
    GuidString.MaximumLength = *((_WORD *)P + 6);
    RtlGUIDFromString(&GuidString, &TmpKtmRmTmGuid);
  }
  else
  {
    TmpKtmRmTmGuid = 0;
  }
  if ( v4[0] )
    ExFreePoolWithTag(v2, 0);
  KeInitializeTimer(&TmpCheckForProgressTimer);
  KeInitializeDpc(&TmpCheckForProgressDpc, TmpCheckForProgressDpcRoutine, 0);
  KeSetTimer(&TmpCheckForProgressTimer, TmpTmAdvanceTailWarningInterval, &TmpCheckForProgressDpc);
  EtwRegister(&KTM_ETW_PROVIDER, 0, 0, &TmpEtwHandle);
  EtwRegister(&KTM_ETW_TRIGGER_PROVIDER, 0, 0, &TmpTriggerHandle);
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_TmLog;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  result = (__int64)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    result = *((unsigned int *)WPP_GLOBAL_Control + 11);
    if ( (result & 8) != 0 )
      return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 48, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000dff0  mov     [rsp-8+arg_0], rbx
0x14000dff5  push    rbp
0x14000dff6  lea     rbp, [rsp-20h]
0x14000dffb  sub     rsp, 120h
0x14000e002  mov     rax, cs:__security_cookie
0x14000e009  xor     rax, rsp
0x14000e00c  mov     [rbp+20h+var_10], rax
0x14000e010  lea     rax, [rsp+120h+var_B0]
0x14000e015  mov     [rsp+120h+var_D0], 6E006Ch
0x14000e01e  mov     [rsp+120h+P], rax
0x14000e023  lea     r9, [rsp+120h+P]
0x14000e028  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000e02f  mov     [rsp+120h+var_E0], 3A0038h
0x14000e038  mov     [rsp+120h+var_C8], rax
0x14000e03d  lea     r8, [rsp+120h+var_EC]
0x14000e042  lea     rax, aTmadvancetailw; "TmAdvanceTailWarningInterval"
0x14000e049  mov     [rsp+120h+var_F0], 0
0x14000e04e  mov     [rsp+120h+var_D8], rax
0x14000e053  lea     rdx, [rsp+120h+var_E0]
0x14000e058  lea     rax, [rsp+120h+var_F0]
0x14000e05d  mov     [rsp+120h+var_EC], 9Ch
0x14000e065  xorps   xmm0, xmm0
0x14000e068  mov     [rsp+120h+var_100], rax
0x14000e06d  lea     rcx, [rsp+120h+var_D0]
0x14000e072  movups  xmmword ptr [rsp+120h+GuidString.Length], xmm0
0x14000e077  call    TmpQueryValueKey
0x14000e07c  test    eax, eax
0x14000e07e  jns     short loc_14000E08C
0x14000e080  mov     rax, 0FFFFFFFDE78EE600h
0x14000e08a  jmp     short loc_14000E0A0
0x14000e08c  mov     rcx, [rsp+120h+P]
0x14000e091  mov     eax, [rcx+8]
0x14000e094  mov     eax, [rax+rcx]
0x14000e097  neg     eax
0x14000e099  imul    rax, 0FFFFFFFFFF676980h
0x14000e0a0  mov     qword ptr cs:TmpTmAdvanceTailWarningInterval, rax
0x14000e0a7  lea     r9, [rsp+120h+P]
0x14000e0ac  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Microsof"...
0x14000e0b3  mov     dword ptr [rsp+120h+var_D0], 620060h
0x14000e0bb  mov     [rsp+120h+var_C8], rax
0x14000e0c0  lea     r8, [rsp+120h+var_EC]
0x14000e0c5  lea     rax, aKtmrmtmidentif; "KtmRmTmIdentifier"
0x14000e0cc  mov     dword ptr [rsp+120h+var_E0], 240022h
0x14000e0d4  mov     [rsp+120h+var_D8], rax
0x14000e0d9  lea     rdx, [rsp+120h+var_E0]
0x14000e0de  lea     rax, [rsp+120h+var_F0]
0x14000e0e3  lea     rcx, [rsp+120h+var_D0]
0x14000e0e8  mov     [rsp+120h+var_100], rax
0x14000e0ed  call    TmpQueryValueKey
0x14000e0f2  mov     rbx, [rsp+120h+P]
0x14000e0f7  test    eax, eax
0x14000e0f9  jns     short loc_14000E107
0x14000e0fb  xorps   xmm0, xmm0
0x14000e0fe  movups  xmmword ptr cs:TmpKtmRmTmGuid.Data1, xmm0
0x14000e105  jmp     short loc_14000E13C
0x14000e107  mov     eax, [rbx+8]
0x14000e10a  lea     rdx, TmpKtmRmTmGuid; Guid
0x14000e111  add     rax, rbx
0x14000e114  lea     rcx, [rsp+120h+GuidString]; GuidString
0x14000e119  mov     [rsp+120h+GuidString.Buffer], rax
0x14000e11e  movzx   eax, word ptr [rbx+0Ch]
0x14000e122  mov     [rsp+120h+GuidString.Length], ax
0x14000e127  movzx   eax, word ptr [rbx+0Ch]
0x14000e12b  mov     [rsp+120h+GuidString.MaximumLength], ax
0x14000e130  call    cs:__imp_RtlGUIDFromString
0x14000e137  nop     dword ptr [rax+rax+00h]
0x14000e13c  cmp     [rsp+120h+var_F0], 0
0x14000e141  jz      short loc_14000E154
0x14000e143  xor     edx, edx; Tag
0x14000e145  mov     rcx, rbx; P
0x14000e148  call    cs:__imp_ExFreePoolWithTag
0x14000e14f  nop     dword ptr [rax+rax+00h]
0x14000e154  lea     rcx, TmpCheckForProgressTimer; Timer
0x14000e15b  call    cs:__imp_KeInitializeTimer
0x14000e162  nop     dword ptr [rax+rax+00h]
0x14000e167  xor     r8d, r8d; DeferredContext
0x14000e16a  lea     rdx, TmpCheckForProgressDpcRoutine; DeferredRoutine
0x14000e171  lea     rcx, TmpCheckForProgressDpc; Dpc
0x14000e178  call    cs:__imp_KeInitializeDpc
0x14000e17f  nop     dword ptr [rax+rax+00h]
0x14000e184  mov     rdx, qword ptr cs:TmpTmAdvanceTailWarningInterval; DueTime
0x14000e18b  lea     r8, TmpCheckForProgressDpc; Dpc
0x14000e192  lea     rcx, TmpCheckForProgressTimer; Timer
0x14000e199  call    cs:__imp_KeSetTimer
0x14000e1a0  nop     dword ptr [rax+rax+00h]
0x14000e1a5  lea     r9, TmpEtwHandle; RegHandle
0x14000e1ac  xor     r8d, r8d; CallbackContext
0x14000e1af  xor     edx, edx; EnableCallback
0x14000e1b1  lea     rcx, KTM_ETW_PROVIDER; ProviderId
0x14000e1b8  call    cs:__imp_EtwRegister
0x14000e1bf  nop     dword ptr [rax+rax+00h]
0x14000e1c4  lea     r9, TmpTriggerHandle; RegHandle
0x14000e1cb  xor     r8d, r8d; CallbackContext
0x14000e1ce  xor     edx, edx; EnableCallback
0x14000e1d0  lea     rcx, KTM_ETW_TRIGGER_PROVIDER; ProviderId
0x14000e1d7  call    cs:__imp_EtwRegister
0x14000e1de  nop     dword ptr [rax+rax+00h]
0x14000e1e3  lea     rax, WPP_ThisDir_CTLGUID_TmLog
0x14000e1ea  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14000e1f5  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14000e1fc  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14000e207  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000e212  mov     cs:WPP_MAIN_CB.Timer, 1
0x14000e21d  call    WppLoadTracingSupport
0x14000e222  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000e22d  call    WppInitKm
0x14000e232  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e239  lea     rax, WPP_GLOBAL_Control
0x14000e240  cmp     rcx, rax
0x14000e243  jz      short loc_14000E261
0x14000e245  mov     eax, [rcx+2Ch]
0x14000e248  test    al, 8
0x14000e24a  jz      short loc_14000E261
0x14000e24c  mov     rcx, [rcx+18h]
0x14000e250  lea     r8, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids
0x14000e257  mov     edx, 30h ; '0'
0x14000e25c  call    WPP_SF_
0x14000e261  mov     rcx, [rbp+20h+var_10]
0x14000e265  xor     rcx, rsp; StackCookie
0x14000e268  call    __security_check_cookie
0x14000e26d  mov     rbx, [rsp+120h+arg_0]
0x14000e275  add     rsp, 120h
0x14000e27c  pop     rbp
0x14000e27d  retn
```
