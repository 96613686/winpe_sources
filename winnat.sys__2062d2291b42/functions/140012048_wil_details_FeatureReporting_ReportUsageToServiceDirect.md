# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140012048`
- end: `0x140012122`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140011fc0`

## callees

- `0x140011e3c`
- `0x140012048`
- `0x14001f320`
- `0x14001f4b0`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x1400120f4`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x1400120f4`

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
0x140012048  push    rbx
0x14001204a  push    rbp
0x14001204b  push    rsi
0x14001204c  push    rdi
0x14001204d  push    r14
0x14001204f  sub     rsp, 70h
0x140012053  mov     rax, cs:__security_cookie
0x14001205a  xor     rax, rsp
0x14001205d  mov     [rsp+98h+var_30], rax
0x140012062  mov     r9, rdx
0x140012065  mov     rbx, rdx
0x140012068  mov     rdx, [rcx+8]
0x14001206c  mov     rbp, rcx
0x14001206f  shr     r9, 20h
0x140012073  lea     rcx, [rsp+98h+var_60]
0x140012078  mov     esi, r8d
0x14001207b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140012080  mov     r14d, 1
0x140012086  movups  xmm1, xmmword ptr [rax]
0x140012089  movups  [rsp+98h+var_48], xmm1
0x14001208e  movsd   xmm0, qword ptr [rax+10h]
0x140012093  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14001209a  movsd   [rsp+98h+var_38], xmm0
0x1400120a0  test    rax, rax
0x1400120a3  jz      short loc_1400120C0
0x1400120a5  mov     r9, [rbp+8]
0x1400120a9  lea     rcx, [rsp+98h+var_48]
0x1400120ae  mov     [rsp+98h+var_78], rcx
0x1400120b3  mov     r8d, r14d
0x1400120b6  mov     ecx, [rbp+18h]
0x1400120b9  mov     edx, esi
0x1400120bb  call    _guard_dispatch_icall
0x1400120c0  bt      ebx, 0Ah
0x1400120c4  jnb     short loc_140012100
0x1400120c6  cmp     esi, 0FEh
0x1400120cc  jz      short loc_140012100
0x1400120ce  mov     eax, [rbp+18h]
0x1400120d1  mov     [rsp+98h+var_68], 0
0x1400120da  mov     dword ptr [rsp+98h+var_68], eax
0x1400120de  mov     word ptr [rsp+98h+var_68+4], si
0x1400120e3  bt      ebx, 0Bh
0x1400120e7  jnb     short loc_1400120EF
0x1400120e9  or      word ptr [rsp+98h+var_68+6], r14w
0x1400120ef  lea     rcx, [rsp+98h+var_68]
0x1400120f4  call    cs:__imp_RtlNotifyFeatureUsage
0x1400120fb  nop     dword ptr [rax+rax+00h]
0x140012100  xor     eax, eax
0x140012102  cmp     dword ptr [rsp+98h+var_38], eax
0x140012106  setz    al
0x140012109  mov     rcx, [rsp+98h+var_30]
0x14001210e  xor     rcx, rsp; StackCookie
0x140012111  call    __security_check_cookie
0x140012116  add     rsp, 70h
0x14001211a  pop     r14
0x14001211c  pop     rdi
0x14001211d  pop     rsi
0x14001211e  pop     rbp
0x14001211f  pop     rbx
0x140012120  retn
```
