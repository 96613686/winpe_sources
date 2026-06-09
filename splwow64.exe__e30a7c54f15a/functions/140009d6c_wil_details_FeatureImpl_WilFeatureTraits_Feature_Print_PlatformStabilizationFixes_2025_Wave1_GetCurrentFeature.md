# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140009d6c`
- end: `0x140009eae`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140009b0c`

## callees

- `0x140009bec`
- `0x140009d6c`
- `0x14000b5d0`
- `0x140016010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCurrentFeatureEnabledState(
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
    v4 = v2(56523872, 3);
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
      (__int64)&qword_140021818,
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
0x140009d6c  mov     [rsp+arg_10], rbx
0x140009d71  mov     [rsp+arg_18], rsi
0x140009d76  mov     [rsp+arg_0], rcx
0x140009d7b  push    rdi
0x140009d7c  sub     rsp, 40h
0x140009d80  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009d87  mov     rbx, rdx
0x140009d8a  test    rax, rax
0x140009d8d  jz      short loc_140009DA2
0x140009d8f  mov     edx, 3
0x140009d94  mov     ecx, 35E7C60h
0x140009d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d9e  mov     edx, eax
0x140009da0  jmp     short loc_140009DB0
0x140009da2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009da9  test    rax, rax
0x140009dac  jnz     short loc_140009D8F
0x140009dae  xor     edx, edx
0x140009db0  mov     r8d, edx
0x140009db3  mov     qword ptr [rbx], 0
0x140009dba  and     r8d, 0FFFFFF3Fh
0x140009dc1  mov     eax, edx
0x140009dc3  and     edx, 80h
0x140009dc9  mov     ecx, r8d
0x140009dcc  and     ecx, 3
0x140009dcf  mov     esi, 40h ; '@'
0x140009dd4  shl     ecx, 2
0x140009dd7  and     eax, esi
0x140009dd9  or      ecx, eax
0x140009ddb  shl     ecx, 2
0x140009dde  or      ecx, edx
0x140009de0  shl     ecx, 3
0x140009de3  test    r8d, r8d
0x140009de6  jnz     short loc_140009DEF
0x140009de8  mov     edx, esi
0x140009dea  mov     r8d, esi
0x140009ded  jmp     short loc_140009DFB
0x140009def  xor     edx, edx
0x140009df1  cmp     r8d, 2
0x140009df5  cmovz   edx, esi
0x140009df8  mov     r8d, edx
0x140009dfb  mov     eax, ecx
0x140009dfd  mov     edi, 1
0x140009e02  or      eax, r8d
0x140009e05  or      ecx, edx
0x140009e07  mov     [rbx], eax
0x140009e09  bt      ecx, 0Ah
0x140009e0d  jnb     short loc_140009E17
0x140009e0f  cmp     ecx, 800h
0x140009e15  jnb     short loc_140009E1E
0x140009e17  xor     dl, dl
0x140009e19  test    sil, cl
0x140009e1c  jz      short loc_140009E87
0x140009e1e  mov     rax, cs:Feature_UxLabTest__descriptor
0x140009e25  mov     r8d, [rax]
0x140009e28  test    r8b, 4
0x140009e2c  jnz     short loc_140009E43
0x140009e2e  lea     rdx, [rsp+48h+arg_8]
0x140009e33  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)
0x140009e38  mov     rcx, [rax]
0x140009e3b  mov     [rsp+48h+arg_8], rcx
0x140009e40  mov     r8d, ecx
0x140009e43  xor     eax, eax
0x140009e45  mov     word ptr [rsp+48h+arg_0+4], 3
0x140009e4c  mov     r9d, r8d
0x140009e4f  mov     [rsp+48h+var_18], eax
0x140009e53  mov     dword ptr [rsp+48h+arg_0], eax
0x140009e57  lea     rcx, qword_140021818
0x140009e5e  shr     r9d, 0Bh
0x140009e62  lea     rax, [rsp+48h+arg_0]
0x140009e67  shr     r8d, 0Ah
0x140009e6b  and     r9d, edi
0x140009e6e  and     r8d, edi
0x140009e71  mov     [rsp+48h+var_20], edi
0x140009e75  mov     edx, 3667C9Ah
0x140009e7a  mov     [rsp+48h+var_28], rax
0x140009e7f  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140009e84  mov     dl, dil
0x140009e87  mov     eax, [rbx]
0x140009e89  test    sil, al
0x140009e8c  jz      short loc_140009E92
0x140009e8e  test    dl, dl
0x140009e90  jnz     short loc_140009E94
0x140009e92  xor     edi, edi
0x140009e94  mov     rsi, [rsp+48h+arg_18]
0x140009e99  and     eax, 0FFFFFFFEh
0x140009e9c  or      eax, edi
0x140009e9e  mov     [rbx], eax
0x140009ea0  mov     rax, rbx
0x140009ea3  mov     rbx, [rsp+48h+arg_10]
0x140009ea8  add     rsp, 40h
0x140009eac  pop     rdi
0x140009ead  retn
```
