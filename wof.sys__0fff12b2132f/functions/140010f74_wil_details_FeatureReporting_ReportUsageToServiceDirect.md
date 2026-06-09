# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140010f74`
- end: `0x14001105d`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140010ef8`

## callees

- `0x140010d74`
- `0x140010f74`
- `0x140011560`
- `0x140011640`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140011028`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140011028`

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
         (volatile signed __int32 *)&Feature_ReFS_WOF_Support__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *((_QWORD *)v5 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(44406110, a3, 1, &Feature_ReFS_WOF_Support__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 44406110;
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
0x140010f74  mov     [rsp+arg_0], rbx
0x140010f79  mov     [rsp+arg_18], rsi
0x140010f7e  push    rdi
0x140010f7f  sub     rsp, 70h
0x140010f83  mov     rax, cs:__security_cookie
0x140010f8a  xor     rax, rsp
0x140010f8d  mov     [rsp+78h+var_10], rax
0x140010f92  mov     r9, rdx
0x140010f95  lea     rcx, [rsp+78h+var_40]
0x140010f9a  mov     rbx, rdx
0x140010f9d  shr     r9, 20h
0x140010fa1  mov     rdx, cs:off_140017B98
0x140010fa8  mov     edi, r8d
0x140010fab  call    wil_details_FeatureReporting_RecordUsageInCache
0x140010fb0  mov     esi, 1
0x140010fb5  movups  xmm1, xmmword ptr [rax]
0x140010fb8  movups  [rsp+78h+var_28], xmm1
0x140010fbd  movsd   xmm0, qword ptr [rax+10h]
0x140010fc2  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140010fc9  movsd   [rsp+78h+var_18], xmm0
0x140010fcf  test    rax, rax
0x140010fd2  jz      short loc_140010FF4
0x140010fd4  mov     r9, cs:off_140017B98
0x140010fdb  lea     rcx, [rsp+78h+var_28]
0x140010fe0  mov     [rsp+78h+var_58], rcx
0x140010fe5  mov     r8d, esi
0x140010fe8  mov     ecx, 2A5955Eh
0x140010fed  mov     edx, edi
0x140010fef  call    _guard_dispatch_icall
0x140010ff4  bt      ebx, 0Ah
0x140010ff8  jnb     short loc_140011034
0x140010ffa  cmp     edi, 0FEh
0x140011000  jz      short loc_140011034
0x140011002  mov     [rsp+78h+var_48], 0
0x14001100b  mov     dword ptr [rsp+78h+var_48], 2A5955Eh
0x140011013  mov     word ptr [rsp+78h+var_48+4], di
0x140011018  bt      ebx, 0Bh
0x14001101c  jnb     short loc_140011023
0x14001101e  or      word ptr [rsp+78h+var_48+6], si
0x140011023  lea     rcx, [rsp+78h+var_48]
0x140011028  call    cs:__imp_RtlNotifyFeatureUsage
0x14001102f  nop     dword ptr [rax+rax+00h]
0x140011034  xor     eax, eax
0x140011036  cmp     dword ptr [rsp+78h+var_18], eax
0x14001103a  setz    al
0x14001103d  mov     rcx, [rsp+78h+var_10]
0x140011042  xor     rcx, rsp; StackCookie
0x140011045  call    __security_check_cookie
0x14001104a  lea     r11, [rsp+78h+var_8]
0x14001104f  mov     rbx, [r11+10h]
0x140011053  mov     rsi, [r11+28h]
0x140011057  mov     rsp, r11
0x14001105a  pop     rdi
0x14001105b  retn
```
