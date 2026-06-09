# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180007c40`
- end: `0x180007de4`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000716c`

## callees

- `0x1800066a8`
- `0x18000724c`
- `0x180007c40`
- `0x18000b2e0`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+20h] BYREF
  __int64 v18; // [rsp+68h] [rbp+28h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048231, 3);
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
    v13 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v11, &v18);
      v13 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_1800218B8, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
    v15 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180021868, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x180007c40  mov     [rsp-18h+arg_10], rbx
0x180007c45  mov     [rsp-18h+arg_0], rcx
0x180007c4a  push    rbp
0x180007c4b  push    rdi
0x180007c4c  push    r14
0x180007c4e  mov     rbp, rsp
0x180007c51  sub     rsp, 40h
0x180007c55  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180007c5c  mov     rdi, rdx
0x180007c5f  test    rax, rax
0x180007c62  jz      short loc_180007C77
0x180007c64  mov     edx, 3
0x180007c69  mov     ecx, 3667CA7h
0x180007c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c73  mov     edx, eax
0x180007c75  jmp     short loc_180007C85
0x180007c77  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180007c7e  test    rax, rax
0x180007c81  jnz     short loc_180007C64
0x180007c83  xor     edx, edx
0x180007c85  mov     r8d, edx
0x180007c88  mov     qword ptr [rdi], 0
0x180007c8f  and     r8d, 0FFFFFF3Fh
0x180007c96  mov     eax, edx
0x180007c98  and     edx, 80h
0x180007c9e  mov     ecx, r8d
0x180007ca1  and     ecx, 3
0x180007ca4  mov     r14d, 40h ; '@'
0x180007caa  shl     ecx, 2
0x180007cad  and     eax, r14d
0x180007cb0  or      ecx, eax
0x180007cb2  shl     ecx, 2
0x180007cb5  or      ecx, edx
0x180007cb7  shl     ecx, 3
0x180007cba  test    r8d, r8d
0x180007cbd  jnz     short loc_180007CC7
0x180007cbf  mov     edx, r14d
0x180007cc2  mov     r8d, r14d
0x180007cc5  jmp     short loc_180007CD4
0x180007cc7  xor     edx, edx
0x180007cc9  cmp     r8d, 2
0x180007ccd  cmovz   edx, r14d
0x180007cd1  mov     r8d, edx
0x180007cd4  mov     eax, ecx
0x180007cd6  mov     ebx, 1
0x180007cdb  or      eax, r8d
0x180007cde  or      ecx, edx
0x180007ce0  mov     [rdi], eax
0x180007ce2  bt      ecx, 0Ah
0x180007ce6  jnb     short loc_180007CF0
0x180007ce8  cmp     ecx, 800h
0x180007cee  jnb     short loc_180007CFB
0x180007cf0  xor     dl, dl
0x180007cf2  test    r14b, cl
0x180007cf5  jz      loc_180007DBF
0x180007cfb  mov     rax, cs:Feature_ValLabTest__descriptor
0x180007d02  mov     r8d, [rax]
0x180007d05  test    r8b, 4
0x180007d09  jnz     short loc_180007D1E
0x180007d0b  lea     rdx, [rbp+arg_8]
0x180007d0f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180007d14  mov     rcx, [rax]
0x180007d17  mov     [rbp+arg_8], rcx
0x180007d1b  mov     r8d, ecx
0x180007d1e  xor     eax, eax
0x180007d20  mov     word ptr [rbp+arg_0+4], 3
0x180007d26  mov     r9d, r8d
0x180007d29  mov     [rsp+40h+var_10], eax
0x180007d2d  mov     dword ptr [rbp+arg_0], eax
0x180007d30  lea     rcx, qword_1800218B8
0x180007d37  shr     r9d, 0Bh
0x180007d3b  lea     rax, [rbp+arg_0]
0x180007d3f  shr     r8d, 0Ah
0x180007d43  and     r9d, ebx
0x180007d46  and     r8d, ebx
0x180007d49  mov     [rsp+40h+var_18], ebx
0x180007d4d  mov     edx, 3667CA2h
0x180007d52  mov     [rsp+40h+var_20], rax
0x180007d57  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180007d5c  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180007d63  mov     r8d, [rax]
0x180007d66  test    r8b, 4
0x180007d6a  jnz     short loc_180007D7F
0x180007d6c  lea     rdx, [rbp+arg_8]
0x180007d70  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x180007d75  mov     rcx, [rax]
0x180007d78  mov     [rbp+arg_8], rcx
0x180007d7c  mov     r8d, ecx
0x180007d7f  xor     eax, eax
0x180007d81  mov     word ptr [rbp+arg_0+4], 3
0x180007d87  mov     r9d, r8d
0x180007d8a  mov     [rsp+40h+var_10], eax
0x180007d8e  mov     dword ptr [rbp+arg_0], eax
0x180007d91  lea     rcx, qword_180021868
0x180007d98  shr     r9d, 0Bh
0x180007d9c  lea     rax, [rbp+arg_0]
0x180007da0  shr     r8d, 0Ah
0x180007da4  and     r9d, ebx
0x180007da7  and     r8d, ebx
0x180007daa  mov     [rsp+40h+var_18], ebx
0x180007dae  mov     edx, 2AF34F8h
0x180007db3  mov     [rsp+40h+var_20], rax
0x180007db8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180007dbd  mov     dl, bl
0x180007dbf  mov     eax, [rdi]
0x180007dc1  test    r14b, al
0x180007dc4  jz      short loc_180007DCA
0x180007dc6  test    dl, dl
0x180007dc8  jnz     short loc_180007DCC
0x180007dca  xor     ebx, ebx
0x180007dcc  and     eax, 0FFFFFFFEh
0x180007dcf  or      eax, ebx
0x180007dd1  mov     rbx, [rsp+40h+arg_10]
0x180007dd6  mov     [rdi], eax
0x180007dd8  mov     rax, rdi
0x180007ddb  add     rsp, 40h
0x180007ddf  pop     r14
0x180007de1  pop     rdi
0x180007de2  pop     rbp
0x180007de3  retn
```
