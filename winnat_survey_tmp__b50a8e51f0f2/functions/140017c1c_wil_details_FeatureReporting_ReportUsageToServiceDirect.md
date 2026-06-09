# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140017c1c`
- end: `0x140017cf6`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140017b94`

## callees

- `0x140017a10`
- `0x140017c1c`
- `0x14001ede0`
- `0x14001ef70`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140017cc8`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140017cc8`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  int *v6; // rax
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
0x140017c1c  push    rbx
0x140017c1e  push    rbp
0x140017c1f  push    rsi
0x140017c20  push    rdi
0x140017c21  push    r14
0x140017c23  sub     rsp, 70h
0x140017c27  mov     rax, cs:__security_cookie
0x140017c2e  xor     rax, rsp
0x140017c31  mov     [rsp+98h+var_30], rax
0x140017c36  mov     r9, rdx
0x140017c39  mov     rbx, rdx
0x140017c3c  mov     rdx, [rcx+8]
0x140017c40  mov     rbp, rcx
0x140017c43  shr     r9, 20h
0x140017c47  lea     rcx, [rsp+98h+var_60]
0x140017c4c  mov     esi, r8d
0x140017c4f  call    wil_details_FeatureReporting_RecordUsageInCache
0x140017c54  mov     r14d, 1
0x140017c5a  movups  xmm1, xmmword ptr [rax]
0x140017c5d  movups  [rsp+98h+var_48], xmm1
0x140017c62  movsd   xmm0, qword ptr [rax+10h]
0x140017c67  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140017c6e  movsd   [rsp+98h+var_38], xmm0
0x140017c74  test    rax, rax
0x140017c77  jz      short loc_140017C94
0x140017c79  mov     r9, [rbp+8]
0x140017c7d  lea     rcx, [rsp+98h+var_48]
0x140017c82  mov     [rsp+98h+var_78], rcx
0x140017c87  mov     r8d, r14d
0x140017c8a  mov     ecx, [rbp+18h]
0x140017c8d  mov     edx, esi
0x140017c8f  call    _guard_dispatch_icall
0x140017c94  bt      ebx, 0Ah
0x140017c98  jnb     short loc_140017CD4
0x140017c9a  cmp     esi, 0FEh
0x140017ca0  jz      short loc_140017CD4
0x140017ca2  mov     eax, [rbp+18h]
0x140017ca5  mov     [rsp+98h+var_68], 0
0x140017cae  mov     dword ptr [rsp+98h+var_68], eax
0x140017cb2  mov     word ptr [rsp+98h+var_68+4], si
0x140017cb7  bt      ebx, 0Bh
0x140017cbb  jnb     short loc_140017CC3
0x140017cbd  or      word ptr [rsp+98h+var_68+6], r14w
0x140017cc3  lea     rcx, [rsp+98h+var_68]
0x140017cc8  call    cs:__imp_RtlNotifyFeatureUsage
0x140017ccf  nop     dword ptr [rax+rax+00h]
0x140017cd4  xor     eax, eax
0x140017cd6  cmp     dword ptr [rsp+98h+var_38], eax
0x140017cda  setz    al
0x140017cdd  mov     rcx, [rsp+98h+var_30]
0x140017ce2  xor     rcx, rsp; StackCookie
0x140017ce5  call    __security_check_cookie
0x140017cea  add     rsp, 70h
0x140017cee  pop     r14
0x140017cf0  pop     rdi
0x140017cf1  pop     rsi
0x140017cf2  pop     rbp
0x140017cf3  pop     rbx
0x140017cf4  retn
```
