# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1400116bc`
- end: `0x1400117a5`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140011640`

## callees

- `0x1400114bc`
- `0x1400116bc`
- `0x14001bc30`
- `0x14001bd10`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140011770`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140011770`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  _DWORD *v5; // rax
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v8[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h] BYREF
  __int64 v10; // [rsp+60h] [rbp-18h]

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         (volatile signed __int32 *)&Feature_Udfs_Bitmap_Dismount__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *((_QWORD *)v5 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(56791059, a3, 1, &Feature_Udfs_Bitmap_Dismount__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 56791059;
    WORD2(v7) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v7) |= 1u;
    RtlNotifyFeatureUsage(&v7);
  }
  return (_DWORD)v10 == 0;
}

```

## disassembly

```asm
0x1400116bc  mov     [rsp+arg_0], rbx
0x1400116c1  mov     [rsp+arg_18], rsi
0x1400116c6  push    rdi
0x1400116c7  sub     rsp, 70h
0x1400116cb  mov     rax, cs:__security_cookie
0x1400116d2  xor     rax, rsp
0x1400116d5  mov     [rsp+78h+var_10], rax
0x1400116da  mov     r9, rdx
0x1400116dd  lea     rcx, [rsp+78h+var_40]
0x1400116e2  mov     rbx, rdx
0x1400116e5  shr     r9, 20h
0x1400116e9  mov     rdx, cs:off_140024CC8
0x1400116f0  mov     edi, r8d
0x1400116f3  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400116f8  mov     esi, 1
0x1400116fd  movups  xmm1, xmmword ptr [rax]
0x140011700  movups  [rsp+78h+var_28], xmm1
0x140011705  movsd   xmm0, qword ptr [rax+10h]
0x14001170a  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140011711  movsd   [rsp+78h+var_18], xmm0
0x140011717  test    rax, rax
0x14001171a  jz      short loc_14001173C
0x14001171c  mov     r9, cs:off_140024CC8
0x140011723  lea     rcx, [rsp+78h+var_28]
0x140011728  mov     [rsp+78h+var_58], rcx
0x14001172d  mov     r8d, esi
0x140011730  mov     ecx, 3629013h
0x140011735  mov     edx, edi
0x140011737  call    _guard_dispatch_icall
0x14001173c  bt      ebx, 0Ah
0x140011740  jnb     short loc_14001177C
0x140011742  cmp     edi, 0FEh
0x140011748  jz      short loc_14001177C
0x14001174a  mov     [rsp+78h+var_48], 0
0x140011753  mov     dword ptr [rsp+78h+var_48], 3629013h
0x14001175b  mov     word ptr [rsp+78h+var_48+4], di
0x140011760  bt      ebx, 0Bh
0x140011764  jnb     short loc_14001176B
0x140011766  or      word ptr [rsp+78h+var_48+6], si
0x14001176b  lea     rcx, [rsp+78h+var_48]
0x140011770  call    cs:__imp_RtlNotifyFeatureUsage
0x140011777  nop     dword ptr [rax+rax+00h]
0x14001177c  xor     eax, eax
0x14001177e  cmp     dword ptr [rsp+78h+var_18], eax
0x140011782  setz    al
0x140011785  mov     rcx, [rsp+78h+var_10]
0x14001178a  xor     rcx, rsp; StackCookie
0x14001178d  call    __security_check_cookie
0x140011792  lea     r11, [rsp+78h+var_8]
0x140011797  mov     rbx, [r11+10h]
0x14001179b  mov     rsi, [r11+28h]
0x14001179f  mov     rsp, r11
0x1400117a2  pop     rdi
0x1400117a3  retn
```
