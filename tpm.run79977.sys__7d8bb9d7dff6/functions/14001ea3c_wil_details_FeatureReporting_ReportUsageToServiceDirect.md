# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14001ea3c`
- end: `0x14001eb16`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14001e9b4`

## callees

- `0x14001e830`
- `0x14001ea3c`
- `0x140039740`
- `0x140039780`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14001eae8`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14001eae8`

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
0x14001ea3c  push    rbx
0x14001ea3e  push    rbp
0x14001ea3f  push    rsi
0x14001ea40  push    rdi
0x14001ea41  push    r14
0x14001ea43  sub     rsp, 70h
0x14001ea47  mov     rax, cs:__security_cookie
0x14001ea4e  xor     rax, rsp
0x14001ea51  mov     [rsp+98h+var_30], rax
0x14001ea56  mov     r9, rdx
0x14001ea59  mov     rbx, rdx
0x14001ea5c  mov     rdx, [rcx+8]
0x14001ea60  mov     rbp, rcx
0x14001ea63  shr     r9, 20h
0x14001ea67  lea     rcx, [rsp+98h+var_60]
0x14001ea6c  mov     esi, r8d
0x14001ea6f  call    wil_details_FeatureReporting_RecordUsageInCache
0x14001ea74  mov     r14d, 1
0x14001ea7a  movups  xmm1, xmmword ptr [rax]
0x14001ea7d  movups  [rsp+98h+var_48], xmm1
0x14001ea82  movsd   xmm0, qword ptr [rax+10h]
0x14001ea87  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14001ea8e  movsd   [rsp+98h+var_38], xmm0
0x14001ea94  test    rax, rax
0x14001ea97  jz      short loc_14001EAB4
0x14001ea99  mov     r9, [rbp+8]
0x14001ea9d  lea     rcx, [rsp+98h+var_48]
0x14001eaa2  mov     [rsp+98h+var_78], rcx
0x14001eaa7  mov     r8d, r14d
0x14001eaaa  mov     ecx, [rbp+18h]
0x14001eaad  mov     edx, esi
0x14001eaaf  call    _guard_dispatch_icall
0x14001eab4  bt      ebx, 0Ah
0x14001eab8  jnb     short loc_14001EAF4
0x14001eaba  cmp     esi, 0FEh
0x14001eac0  jz      short loc_14001EAF4
0x14001eac2  mov     eax, [rbp+18h]
0x14001eac5  mov     [rsp+98h+var_68], 0
0x14001eace  mov     dword ptr [rsp+98h+var_68], eax
0x14001ead2  mov     word ptr [rsp+98h+var_68+4], si
0x14001ead7  bt      ebx, 0Bh
0x14001eadb  jnb     short loc_14001EAE3
0x14001eadd  or      word ptr [rsp+98h+var_68+6], r14w
0x14001eae3  lea     rcx, [rsp+98h+var_68]
0x14001eae8  call    cs:__imp_RtlNotifyFeatureUsage
0x14001eaef  nop     dword ptr [rax+rax+00h]
0x14001eaf4  xor     eax, eax
0x14001eaf6  cmp     dword ptr [rsp+98h+var_38], eax
0x14001eafa  setz    al
0x14001eafd  mov     rcx, [rsp+98h+var_30]
0x14001eb02  xor     rcx, rsp; StackCookie
0x14001eb05  call    __security_check_cookie
0x14001eb0a  add     rsp, 70h
0x14001eb0e  pop     r14
0x14001eb10  pop     rdi
0x14001eb11  pop     rsi
0x14001eb12  pop     rbp
0x14001eb13  pop     rbx
0x14001eb14  retn
```
