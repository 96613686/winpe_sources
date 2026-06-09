# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140006bec`
- end: `0x140006d2e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x140006b0c`

## callees

- `0x14000698c`
- `0x140006bec`
- `0x14000936c`
- `0x14001e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(56864097, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_UxLabTest__descriptor;
    if ( (*(_DWORD *)Feature_UxLabTest__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(v11, &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(
      (__int64)&unk_14002C648,
      0x3667C9Au,
      (v13 >> 10) & 1,
      (v13 >> 11) & 1,
      (__int64)&v15,
      1u,
      0);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x140006bec  mov     [rsp+arg_10], rbx
0x140006bf1  mov     [rsp+arg_18], rsi
0x140006bf6  mov     [rsp+arg_0], rcx
0x140006bfb  push    rdi
0x140006bfc  sub     rsp, 40h
0x140006c00  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140006c07  mov     rbx, rdx
0x140006c0a  test    rax, rax
0x140006c0d  jz      short loc_140006C22
0x140006c0f  mov     edx, 3
0x140006c14  mov     ecx, 363AD61h
0x140006c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c1e  mov     edx, eax
0x140006c20  jmp     short loc_140006C30
0x140006c22  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140006c29  test    rax, rax
0x140006c2c  jnz     short loc_140006C0F
0x140006c2e  xor     edx, edx
0x140006c30  mov     r8d, edx
0x140006c33  mov     qword ptr [rbx], 0
0x140006c3a  and     r8d, 0FFFFFF3Fh
0x140006c41  mov     eax, edx
0x140006c43  and     edx, 80h
0x140006c49  mov     ecx, r8d
0x140006c4c  and     ecx, 3
0x140006c4f  mov     esi, 40h ; '@'
0x140006c54  shl     ecx, 2
0x140006c57  and     eax, esi
0x140006c59  or      ecx, eax
0x140006c5b  shl     ecx, 2
0x140006c5e  or      ecx, edx
0x140006c60  shl     ecx, 3
0x140006c63  test    r8d, r8d
0x140006c66  jnz     short loc_140006C6F
0x140006c68  mov     edx, esi
0x140006c6a  mov     r8d, esi
0x140006c6d  jmp     short loc_140006C7B
0x140006c6f  xor     edx, edx
0x140006c71  cmp     r8d, 2
0x140006c75  cmovz   edx, esi
0x140006c78  mov     r8d, edx
0x140006c7b  mov     eax, ecx
0x140006c7d  mov     edi, 1
0x140006c82  or      eax, r8d
0x140006c85  or      ecx, edx
0x140006c87  mov     [rbx], eax
0x140006c89  bt      ecx, 0Ah
0x140006c8d  jnb     short loc_140006C97
0x140006c8f  cmp     ecx, 800h
0x140006c95  jnb     short loc_140006C9E
0x140006c97  xor     dl, dl
0x140006c99  test    sil, cl
0x140006c9c  jz      short loc_140006D07
0x140006c9e  mov     rax, cs:Feature_UxLabTest__descriptor
0x140006ca5  mov     r8d, [rax]
0x140006ca8  test    r8b, 4
0x140006cac  jnz     short loc_140006CC3
0x140006cae  lea     rdx, [rsp+48h+arg_8]
0x140006cb3  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)
0x140006cb8  mov     rcx, [rax]
0x140006cbb  mov     [rsp+48h+arg_8], rcx
0x140006cc0  mov     r8d, ecx
0x140006cc3  xor     eax, eax
0x140006cc5  mov     word ptr [rsp+48h+arg_0+4], 3
0x140006ccc  mov     r9d, r8d
0x140006ccf  mov     [rsp+48h+var_18], eax
0x140006cd3  mov     dword ptr [rsp+48h+arg_0], eax
0x140006cd7  lea     rcx, unk_14002C648
0x140006cde  shr     r9d, 0Bh
0x140006ce2  lea     rax, [rsp+48h+arg_0]
0x140006ce7  shr     r8d, 0Ah
0x140006ceb  and     r9d, edi
0x140006cee  and     r8d, edi
0x140006cf1  mov     [rsp+48h+var_20], edi
0x140006cf5  mov     edx, 3667C9Ah
0x140006cfa  mov     [rsp+48h+var_28], rax
0x140006cff  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140006d04  mov     dl, dil
0x140006d07  mov     eax, [rbx]
0x140006d09  test    sil, al
0x140006d0c  jz      short loc_140006D12
0x140006d0e  test    dl, dl
0x140006d10  jnz     short loc_140006D14
0x140006d12  xor     edi, edi
0x140006d14  mov     rsi, [rsp+48h+arg_18]
0x140006d19  and     eax, 0FFFFFFFEh
0x140006d1c  or      eax, edi
0x140006d1e  mov     [rbx], eax
0x140006d20  mov     rax, rbx
0x140006d23  mov     rbx, [rsp+48h+arg_10]
0x140006d28  add     rsp, 40h
0x140006d2c  pop     rdi
0x140006d2d  retn
```
