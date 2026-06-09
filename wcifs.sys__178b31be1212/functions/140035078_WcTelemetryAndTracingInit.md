# WcTelemetryAndTracingInit

- ea: `0x140035078`
- end: `0x1400351ac`
- name: `WcTelemetryAndTracingInit`
- size: `308`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1400351b4`

## callees

- `0x1400020c4`
- `0x140007c60`
- `0x14001b83c`
- `0x14001b904`
- `0x140022dc0`
- `0x140035078`

## import_xrefs

- `WppRecorder!imp_WppRecorderConfigure` at `0x14003512d`
- `WppRecorder!imp_WppRecorderConfigure` at `0x14003512d`

## pseudocode

```c
__int64 __fastcall WcTelemetryAndTracingInit(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // edx
  int v6; // [rsp+38h] [rbp-30h]
  _QWORD v7[2]; // [rsp+40h] [rbp-28h] BYREF

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WcifsTrace;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(a1, a2);
  v7[0] = 0x100000010LL;
  v7[1] = 0x200000002LL;
  imp_WppRecorderConfigure(wil_details_featureDescriptors_a, v7);
  result = TlgRegisterAggregateProvider();
  if ( (int)result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = result;
    LOBYTE(v5) = 2;
    return WPP_RECORDER_SF_sDd(
             wil_details_featureDescriptors_a->DeviceExtension,
             v5,
             1,
             10,
             (__int64)WPP_fd6e5da2a1a53c4972de035ee243e502_Traceguids,
             (__int64)"onecore\\base\\fs\\wci\\wcifs\\telemetry.c",
             97,
             v6);
  }
  return result;
}

```

## disassembly

```asm
0x140035078  mov     [rsp+arg_10], rbx
0x14003507d  push    rdi
0x14003507e  sub     rsp, 60h
0x140035082  mov     rax, cs:__security_cookie
0x140035089  xor     rax, rsp
0x14003508c  mov     [rsp+68h+var_18], rax
0x140035091  lea     rax, WPP_ThisDir_CTLGUID_WcifsTrace
0x140035098  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x1400350a3  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400350aa  mov     rdi, rdx
0x1400350ad  xor     eax, eax
0x1400350af  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x1400350ba  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x1400350c0  mov     rbx, rcx
0x1400350c3  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400350ce  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400350d9  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400350e4  call    WppLoadTracingSupport
0x1400350e9  mov     rdx, rdi
0x1400350ec  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400350f7  mov     rcx, rbx
0x1400350fa  call    WppInitKm
0x1400350ff  mov     rcx, cs:wil_details_featureDescriptors_a
0x140035106  lea     rdx, [rsp+68h+var_28]
0x14003510b  xorps   xmm0, xmm0
0x14003510e  mov     ebx, 2
0x140035113  movups  [rsp+68h+var_28], xmm0
0x140035118  mov     dword ptr [rsp+68h+var_28], 10h
0x140035120  mov     byte ptr [rsp+68h+var_28+4], 1
0x140035125  mov     dword ptr [rsp+68h+var_28+8], ebx
0x140035129  mov     dword ptr [rsp+68h+var_28+0Ch], ebx
0x14003512d  call    cs:__imp_imp_WppRecorderConfigure
0x140035134  nop     dword ptr [rax+rax+00h]
0x140035139  call    TlgRegisterAggregateProvider
0x14003513e  test    eax, eax
0x140035140  jns     short loc_140035190
0x140035142  lea     rcx, WPP_RECORDER_INITIALIZED
0x140035149  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140035150  jz      short loc_140035190
0x140035152  mov     rcx, cs:wil_details_featureDescriptors_a
0x140035159  lea     r9d, [rbx+8]
0x14003515d  mov     [rsp+68h+var_30], eax
0x140035161  lea     r8d, [rbx-1]
0x140035165  lea     rax, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\wcifs\\telemetr"...
0x14003516c  mov     [rsp+68h+var_38], 61h ; 'a'
0x140035174  mov     [rsp+68h+var_40], rax
0x140035179  mov     dl, bl
0x14003517b  mov     rcx, [rcx+40h]
0x14003517f  lea     rax, WPP_fd6e5da2a1a53c4972de035ee243e502_Traceguids
0x140035186  mov     [rsp+68h+var_48], rax
0x14003518b  call    WPP_RECORDER_SF_sDd
0x140035190  mov     rcx, [rsp+68h+var_18]
0x140035195  xor     rcx, rsp; StackCookie
0x140035198  call    __security_check_cookie
0x14003519d  mov     rbx, [rsp+68h+arg_10]
0x1400351a5  add     rsp, 60h
0x1400351a9  pop     rdi
0x1400351aa  retn
```
