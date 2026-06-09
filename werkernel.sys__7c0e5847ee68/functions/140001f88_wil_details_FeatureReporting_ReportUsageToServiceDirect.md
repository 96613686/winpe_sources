# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140001f88`
- end: `0x140002071`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: `_BOOL8 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140001e68`

## callees

- `0x140001b8c`
- `0x140001f88`
- `0x140002750`
- `0x140002790`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14000203c`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14000203c`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  __int64 v5; // rax
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v8[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h] BYREF
  __int64 v10; // [rsp+60h] [rbp-18h]

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         (volatile signed __int32 *)&Feature_Servicing_WerReportBootLKD__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *(_QWORD *)(v5 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(59383985, a3, 1, &Feature_Servicing_WerReportBootLKD__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 59383985;
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
0x140001f88  mov     [rsp+arg_0], rbx
0x140001f8d  mov     [rsp+arg_18], rsi
0x140001f92  push    rdi
0x140001f93  sub     rsp, 70h
0x140001f97  mov     rax, cs:__security_cookie
0x140001f9e  xor     rax, rsp
0x140001fa1  mov     [rsp+78h+var_10], rax
0x140001fa6  mov     r9, rdx
0x140001fa9  lea     rcx, [rsp+78h+var_40]
0x140001fae  mov     rbx, rdx
0x140001fb1  shr     r9, 20h
0x140001fb5  mov     rdx, cs:off_140008B40
0x140001fbc  mov     edi, r8d
0x140001fbf  call    wil_details_FeatureReporting_RecordUsageInCache
0x140001fc4  mov     esi, 1
0x140001fc9  movups  xmm1, xmmword ptr [rax]
0x140001fcc  movups  [rsp+78h+var_28], xmm1
0x140001fd1  movsd   xmm0, qword ptr [rax+10h]
0x140001fd6  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140001fdd  movsd   [rsp+78h+var_18], xmm0
0x140001fe3  test    rax, rax
0x140001fe6  jz      short loc_140002008
0x140001fe8  mov     r9, cs:off_140008B40
0x140001fef  lea     rcx, [rsp+78h+var_28]
0x140001ff4  mov     [rsp+78h+var_58], rcx
0x140001ff9  mov     r8d, esi
0x140001ffc  mov     ecx, 38A20B1h
0x140002001  mov     edx, edi
0x140002003  call    _guard_dispatch_icall
0x140002008  bt      ebx, 0Ah
0x14000200c  jnb     short loc_140002048
0x14000200e  cmp     edi, 0FEh
0x140002014  jz      short loc_140002048
0x140002016  mov     [rsp+78h+var_48], 0
0x14000201f  mov     dword ptr [rsp+78h+var_48], 38A20B1h
0x140002027  mov     word ptr [rsp+78h+var_48+4], di
0x14000202c  bt      ebx, 0Bh
0x140002030  jnb     short loc_140002037
0x140002032  or      word ptr [rsp+78h+var_48+6], si
0x140002037  lea     rcx, [rsp+78h+var_48]
0x14000203c  call    cs:__imp_RtlNotifyFeatureUsage
0x140002043  nop     dword ptr [rax+rax+00h]
0x140002048  xor     eax, eax
0x14000204a  cmp     dword ptr [rsp+78h+var_18], eax
0x14000204e  setz    al
0x140002051  mov     rcx, [rsp+78h+var_10]
0x140002056  xor     rcx, rsp; StackCookie
0x140002059  call    __security_check_cookie
0x14000205e  lea     r11, [rsp+78h+var_8]
0x140002063  mov     rbx, [r11+10h]
0x140002067  mov     rsi, [r11+28h]
0x14000206b  mov     rsp, r11
0x14000206e  pop     rdi
0x14000206f  retn
```
