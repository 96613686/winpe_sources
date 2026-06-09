# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14001e8b4`
- end: `0x14001e98e`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14001e82c`

## callees

- `0x14001e6a8`
- `0x14001e8b4`
- `0x140040a30`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14001e960`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14001e960`

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
0x14001e8b4  push    rbx
0x14001e8b6  push    rbp
0x14001e8b7  push    rsi
0x14001e8b8  push    rdi
0x14001e8b9  push    r14
0x14001e8bb  sub     rsp, 70h
0x14001e8bf  mov     rax, cs:__security_cookie
0x14001e8c6  xor     rax, rsp
0x14001e8c9  mov     [rsp+98h+var_30], rax
0x14001e8ce  mov     r9, rdx
0x14001e8d1  mov     rbx, rdx
0x14001e8d4  mov     rdx, [rcx+8]
0x14001e8d8  mov     rbp, rcx
0x14001e8db  shr     r9, 20h
0x14001e8df  lea     rcx, [rsp+98h+var_60]
0x14001e8e4  mov     esi, r8d
0x14001e8e7  call    wil_details_FeatureReporting_RecordUsageInCache
0x14001e8ec  mov     r14d, 1
0x14001e8f2  movups  xmm1, xmmword ptr [rax]
0x14001e8f5  movups  [rsp+98h+var_48], xmm1
0x14001e8fa  movsd   xmm0, qword ptr [rax+10h]
0x14001e8ff  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14001e906  movsd   [rsp+98h+var_38], xmm0
0x14001e90c  test    rax, rax
0x14001e90f  jz      short loc_14001E92C
0x14001e911  mov     r9, [rbp+8]
0x14001e915  lea     rcx, [rsp+98h+var_48]
0x14001e91a  mov     [rsp+98h+var_78], rcx
0x14001e91f  mov     r8d, r14d
0x14001e922  mov     ecx, [rbp+18h]
0x14001e925  mov     edx, esi
0x14001e927  call    _guard_dispatch_icall
0x14001e92c  bt      ebx, 0Ah
0x14001e930  jnb     short loc_14001E96C
0x14001e932  cmp     esi, 0FEh
0x14001e938  jz      short loc_14001E96C
0x14001e93a  mov     eax, [rbp+18h]
0x14001e93d  mov     [rsp+98h+var_68], 0
0x14001e946  mov     dword ptr [rsp+98h+var_68], eax
0x14001e94a  mov     word ptr [rsp+98h+var_68+4], si
0x14001e94f  bt      ebx, 0Bh
0x14001e953  jnb     short loc_14001E95B
0x14001e955  or      word ptr [rsp+98h+var_68+6], r14w
0x14001e95b  lea     rcx, [rsp+98h+var_68]
0x14001e960  call    cs:__imp_RtlNotifyFeatureUsage
0x14001e967  nop     dword ptr [rax+rax+00h]
0x14001e96c  xor     eax, eax
0x14001e96e  cmp     dword ptr [rsp+98h+var_38], eax
0x14001e972  setz    al
0x14001e975  mov     rcx, [rsp+98h+var_30]
0x14001e97a  xor     rcx, rsp; StackCookie
0x14001e97d  call    __security_check_cookie
0x14001e982  add     rsp, 70h
0x14001e986  pop     r14
0x14001e988  pop     rdi
0x14001e989  pop     rsi
0x14001e98a  pop     rbp
0x14001e98b  pop     rbx
0x14001e98c  retn
```
