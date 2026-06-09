# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140011a78`
- end: `0x140011b52`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400119f0`

## callees

- `0x14001186c`
- `0x140011a78`
- `0x140014d10`
- `0x140014d50`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140011b24`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140011b24`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  _DWORD *v6; // rax
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h]
  _BYTE v10[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v11; // [rsp+50h] [rbp-48h] BYREF
  __int64 v12; // [rsp+60h] [rbp-38h]

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v10,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2));
  v11 = *(_OWORD *)v6;
  v12 = *((_QWORD *)v6 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), a3, 1, *(_QWORD *)(a1 + 8), &v11);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    v9 = (unsigned __int16)a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    RtlNotifyFeatureUsage(&v8);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x140011a78  push    rbx
0x140011a7a  push    rbp
0x140011a7b  push    rsi
0x140011a7c  push    rdi
0x140011a7d  push    r14
0x140011a7f  sub     rsp, 70h
0x140011a83  mov     rax, cs:__security_cookie
0x140011a8a  xor     rax, rsp
0x140011a8d  mov     [rsp+98h+var_30], rax
0x140011a92  mov     r9, rdx
0x140011a95  mov     rbx, rdx
0x140011a98  mov     rdx, [rcx+8]
0x140011a9c  mov     rbp, rcx
0x140011a9f  shr     r9, 20h
0x140011aa3  lea     rcx, [rsp+98h+var_60]
0x140011aa8  mov     esi, r8d
0x140011aab  call    wil_details_FeatureReporting_RecordUsageInCache
0x140011ab0  mov     r14d, 1
0x140011ab6  movups  xmm1, xmmword ptr [rax]
0x140011ab9  movups  [rsp+98h+var_48], xmm1
0x140011abe  movsd   xmm0, qword ptr [rax+10h]
0x140011ac3  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140011aca  movsd   [rsp+98h+var_38], xmm0
0x140011ad0  test    rax, rax
0x140011ad3  jz      short loc_140011AF0
0x140011ad5  mov     r9, [rbp+8]
0x140011ad9  lea     rcx, [rsp+98h+var_48]
0x140011ade  mov     [rsp+98h+var_78], rcx
0x140011ae3  mov     r8d, r14d
0x140011ae6  mov     ecx, [rbp+18h]
0x140011ae9  mov     edx, esi
0x140011aeb  call    _guard_dispatch_icall
0x140011af0  bt      ebx, 0Ah
0x140011af4  jnb     short loc_140011B30
0x140011af6  cmp     esi, 0FEh
0x140011afc  jz      short loc_140011B30
0x140011afe  mov     eax, [rbp+18h]
0x140011b01  mov     [rsp+98h+var_68], 0
0x140011b0a  mov     dword ptr [rsp+98h+var_68], eax
0x140011b0e  mov     word ptr [rsp+98h+var_68+4], si
0x140011b13  bt      ebx, 0Bh
0x140011b17  jnb     short loc_140011B1F
0x140011b19  or      word ptr [rsp+98h+var_68+6], r14w
0x140011b1f  lea     rcx, [rsp+98h+var_68]
0x140011b24  call    cs:__imp_RtlNotifyFeatureUsage
0x140011b2b  nop     dword ptr [rax+rax+00h]
0x140011b30  xor     eax, eax
0x140011b32  cmp     dword ptr [rsp+98h+var_38], eax
0x140011b36  setz    al
0x140011b39  mov     rcx, [rsp+98h+var_30]
0x140011b3e  xor     rcx, rsp; StackCookie
0x140011b41  call    __security_check_cookie
0x140011b46  add     rsp, 70h
0x140011b4a  pop     r14
0x140011b4c  pop     rdi
0x140011b4d  pop     rsi
0x140011b4e  pop     rbp
0x140011b4f  pop     rbx
0x140011b50  retn
```
