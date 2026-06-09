# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180006970`
- end: `0x180006ab2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180006674`

## callees

- `0x1800064f4`
- `0x180006970`
- `0x18000a358`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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
    v4 = v2(48433719, 3);
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
    v13 = *(_DWORD *)Feature_Standalone_Future__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_1800236B8,
      0x2F29A04u,
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
0x180006970  mov     [rsp+arg_10], rbx
0x180006975  mov     [rsp+arg_18], rsi
0x18000697a  mov     [rsp+arg_0], rcx
0x18000697f  push    rdi
0x180006980  sub     rsp, 40h
0x180006984  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000698b  mov     rbx, rdx
0x18000698e  test    rax, rax
0x180006991  jz      short loc_1800069A6
0x180006993  mov     edx, 3
0x180006998  mov     ecx, 2E30A37h
0x18000699d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069a2  mov     edx, eax
0x1800069a4  jmp     short loc_1800069B4
0x1800069a6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800069ad  test    rax, rax
0x1800069b0  jnz     short loc_180006993
0x1800069b2  xor     edx, edx
0x1800069b4  mov     r8d, edx
0x1800069b7  mov     qword ptr [rbx], 0
0x1800069be  and     r8d, 0FFFFFF3Fh
0x1800069c5  mov     eax, edx
0x1800069c7  and     edx, 80h
0x1800069cd  mov     ecx, r8d
0x1800069d0  and     ecx, 3
0x1800069d3  mov     esi, 40h ; '@'
0x1800069d8  shl     ecx, 2
0x1800069db  and     eax, esi
0x1800069dd  or      ecx, eax
0x1800069df  shl     ecx, 2
0x1800069e2  or      ecx, edx
0x1800069e4  shl     ecx, 3
0x1800069e7  test    r8d, r8d
0x1800069ea  jnz     short loc_1800069F3
0x1800069ec  mov     edx, esi
0x1800069ee  mov     r8d, esi
0x1800069f1  jmp     short loc_1800069FF
0x1800069f3  xor     edx, edx
0x1800069f5  cmp     r8d, 2
0x1800069f9  cmovz   edx, esi
0x1800069fc  mov     r8d, edx
0x1800069ff  mov     eax, ecx
0x180006a01  mov     edi, 1
0x180006a06  or      eax, r8d
0x180006a09  or      ecx, edx
0x180006a0b  mov     [rbx], eax
0x180006a0d  bt      ecx, 0Ah
0x180006a11  jnb     short loc_180006A1B
0x180006a13  cmp     ecx, 800h
0x180006a19  jnb     short loc_180006A22
0x180006a1b  xor     dl, dl
0x180006a1d  test    sil, cl
0x180006a20  jz      short loc_180006A8B
0x180006a22  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180006a29  mov     r8d, [rax]
0x180006a2c  test    r8b, 4
0x180006a30  jnz     short loc_180006A47
0x180006a32  lea     rdx, [rsp+48h+arg_8]
0x180006a37  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180006a3c  mov     rcx, [rax]
0x180006a3f  mov     [rsp+48h+arg_8], rcx
0x180006a44  mov     r8d, ecx
0x180006a47  xor     eax, eax
0x180006a49  mov     word ptr [rsp+48h+arg_0+4], 3
0x180006a50  mov     r9d, r8d
0x180006a53  mov     [rsp+48h+var_18], eax
0x180006a57  mov     dword ptr [rsp+48h+arg_0], eax
0x180006a5b  lea     rcx, qword_1800236B8
0x180006a62  shr     r9d, 0Bh
0x180006a66  lea     rax, [rsp+48h+arg_0]
0x180006a6b  shr     r8d, 0Ah
0x180006a6f  and     r9d, edi
0x180006a72  and     r8d, edi
0x180006a75  mov     [rsp+48h+var_20], edi
0x180006a79  mov     edx, 2F29A04h
0x180006a7e  mov     [rsp+48h+var_28], rax
0x180006a83  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180006a88  mov     dl, dil
0x180006a8b  mov     eax, [rbx]
0x180006a8d  test    sil, al
0x180006a90  jz      short loc_180006A96
0x180006a92  test    dl, dl
0x180006a94  jnz     short loc_180006A98
0x180006a96  xor     edi, edi
0x180006a98  mov     rsi, [rsp+48h+arg_18]
0x180006a9d  and     eax, 0FFFFFFFEh
0x180006aa0  or      eax, edi
0x180006aa2  mov     [rbx], eax
0x180006aa4  mov     rax, rbx
0x180006aa7  mov     rbx, [rsp+48h+arg_10]
0x180006aac  add     rsp, 40h
0x180006ab0  pop     rdi
0x180006ab1  retn
```
