# wil_details_RegisterFeatureUsageProvider

- ea: `0x14000b4dc`
- end: `0x14000b557`
- name: `wil_details_RegisterFeatureUsageProvider`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d078`

## callees

- `0x140004f0c`
- `0x14000b4dc`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14000b536`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14000b536`

## pseudocode

```c
__int64 wil_details_RegisterFeatureUsageProvider()
{
  __int64 result; // rax
  _QWORD v1[5]; // [rsp+20h] [rbp-28h] BYREF

  g_wil_details_recordFeatureUsage = (__int64)wil_details_RecordFeatureUsageReporting;
  v1[0] = wil_details_FeatureDescriptors_SkipPadding(wil_details_featureDescriptors_a);
  v1[2] = 0;
  v1[1] = wil_details_featureDescriptors_a;
  result = RtlRegisterFeatureUsageProvider(
             wil_details_OnFeatureUsageProviderFlushNotification,
             v1,
             &g_wil_details_featureUsageProvider);
  if ( (_DWORD)result )
    g_wil_details_featureUsageProvider = 0;
  return result;
}

```

## disassembly

```asm
0x14000b4dc  sub     rsp, 48h
0x14000b4e0  xor     eax, eax
0x14000b4e2  lea     rcx, wil_details_featureDescriptors_a
0x14000b4e9  mov     [rsp+48h+var_18], rax
0x14000b4ee  xorps   xmm0, xmm0
0x14000b4f1  lea     rax, wil_details_RecordFeatureUsageReporting
0x14000b4f8  movups  [rsp+48h+var_28], xmm0
0x14000b4fd  mov     cs:g_wil_details_recordFeatureUsage, rax
0x14000b504  call    wil_details_FeatureDescriptors_SkipPadding
0x14000b509  mov     qword ptr [rsp+48h+var_28], rax
0x14000b50e  lea     r8, g_wil_details_featureUsageProvider
0x14000b515  lea     rax, wil_details_featureDescriptors_a
0x14000b51c  mov     [rsp+48h+var_18], 0
0x14000b525  lea     rdx, [rsp+48h+var_28]
0x14000b52a  mov     qword ptr [rsp+48h+var_28+8], rax
0x14000b52f  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x14000b536  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x14000b53d  nop     dword ptr [rax+rax+00h]
0x14000b542  test    eax, eax
0x14000b544  jz      short loc_14000B551
0x14000b546  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000b551  add     rsp, 48h
0x14000b555  retn
```
