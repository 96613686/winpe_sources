# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800077f0`
- end: `0x180007959`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180006ecc`

## callees

- `0x18000681c`
- `0x1800077f0`
- `0x18000b2e0`
- `0x18000d604`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048237, 3);
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180021878, 45036797, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800077f0  mov     [rsp+arg_10], rbx
0x1800077f5  mov     [rsp+arg_0], rcx
0x1800077fa  push    rbp
0x1800077fb  push    rsi
0x1800077fc  push    rdi
0x1800077fd  sub     rsp, 40h
0x180007801  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180007808  mov     rbx, rdx
0x18000780b  test    rax, rax
0x18000780e  jz      short loc_180007823
0x180007810  mov     edx, 3
0x180007815  mov     ecx, 3667CADh
0x18000781a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781f  mov     edx, eax
0x180007821  jmp     short loc_180007831
0x180007823  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000782a  test    rax, rax
0x18000782d  jnz     short loc_180007810
0x18000782f  xor     edx, edx
0x180007831  mov     r8d, edx
0x180007834  mov     qword ptr [rbx], 0
0x18000783b  and     r8d, 0FFFFFF3Fh
0x180007842  mov     eax, edx
0x180007844  and     edx, 80h
0x18000784a  mov     ecx, r8d
0x18000784d  and     ecx, 3
0x180007850  mov     ebp, 40h ; '@'
0x180007855  shl     ecx, 2
0x180007858  and     eax, ebp
0x18000785a  or      ecx, eax
0x18000785c  shl     ecx, 2
0x18000785f  or      ecx, edx
0x180007861  shl     ecx, 3
0x180007864  test    r8d, r8d
0x180007867  jnz     short loc_180007870
0x180007869  mov     edx, ebp
0x18000786b  mov     r8d, ebp
0x18000786e  jmp     short loc_18000787C
0x180007870  xor     edx, edx
0x180007872  cmp     r8d, 2
0x180007876  cmovz   edx, ebp
0x180007879  mov     r8d, edx
0x18000787c  mov     eax, ecx
0x18000787e  mov     edi, 1
0x180007883  or      eax, r8d
0x180007886  or      ecx, edx
0x180007888  mov     [rbx], eax
0x18000788a  bt      ecx, 0Ah
0x18000788e  jnb     short loc_18000789D
0x180007890  cmp     ecx, 800h
0x180007896  jb      short loc_18000789D
0x180007898  mov     sil, dil
0x18000789b  jmp     short loc_1800078AB
0x18000789d  xor     sil, sil
0x1800078a0  xor     dl, dl
0x1800078a2  test    bpl, cl
0x1800078a5  jz      loc_180007935
0x1800078ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x1800078b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x1800078b7  test    al, al
0x1800078b9  jz      short loc_180007926
0x1800078bb  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1800078c2  mov     r8d, [rax]
0x1800078c5  test    r8b, 4
0x1800078c9  jnz     short loc_1800078E0
0x1800078cb  lea     rdx, [rsp+58h+arg_8]
0x1800078d0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x1800078d5  mov     rcx, [rax]
0x1800078d8  mov     [rsp+58h+arg_8], rcx
0x1800078dd  mov     r8d, ecx
0x1800078e0  xor     eax, eax
0x1800078e2  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800078e9  mov     r9d, r8d
0x1800078ec  mov     [rsp+58h+var_28], eax
0x1800078f0  mov     dword ptr [rsp+58h+arg_0], eax
0x1800078f4  lea     rcx, qword_180021878
0x1800078fb  shr     r9d, 0Bh
0x1800078ff  lea     rax, [rsp+58h+arg_0]
0x180007904  shr     r8d, 0Ah
0x180007908  and     r9d, edi
0x18000790b  and     r8d, edi
0x18000790e  mov     [rsp+58h+var_30], edi
0x180007912  mov     edx, 2AF34FDh
0x180007917  mov     [rsp+58h+var_38], rax
0x18000791c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180007921  mov     dl, dil
0x180007924  jmp     short loc_180007928
0x180007926  xor     dl, dl
0x180007928  test    sil, sil
0x18000792b  jz      short loc_180007935
0x18000792d  test    dl, dl
0x18000792f  jnz     short loc_180007935
0x180007931  btr     dword ptr [rbx], 0Ah
0x180007935  mov     eax, [rbx]
0x180007937  test    bpl, al
0x18000793a  jz      short loc_180007940
0x18000793c  test    dl, dl
0x18000793e  jnz     short loc_180007942
0x180007940  xor     edi, edi
0x180007942  and     eax, 0FFFFFFFEh
0x180007945  or      eax, edi
0x180007947  mov     [rbx], eax
0x180007949  mov     rax, rbx
0x18000794c  mov     rbx, [rsp+58h+arg_10]
0x180007951  add     rsp, 40h
0x180007955  pop     rdi
0x180007956  pop     rsi
0x180007957  pop     rbp
0x180007958  retn
```
