# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180007960`
- end: `0x180007ac9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180006fac`

## callees

- `0x180006990`
- `0x180007960`
- `0x18000b2e0`
- `0x18000d430`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58988972, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180021888, 58599532, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180007960  mov     [rsp+arg_10], rbx
0x180007965  mov     [rsp+arg_0], rcx
0x18000796a  push    rbp
0x18000796b  push    rsi
0x18000796c  push    rdi
0x18000796d  sub     rsp, 40h
0x180007971  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180007978  mov     rbx, rdx
0x18000797b  test    rax, rax
0x18000797e  jz      short loc_180007993
0x180007980  mov     edx, 3
0x180007985  mov     ecx, 38419ACh
0x18000798a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000798f  mov     edx, eax
0x180007991  jmp     short loc_1800079A1
0x180007993  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000799a  test    rax, rax
0x18000799d  jnz     short loc_180007980
0x18000799f  xor     edx, edx
0x1800079a1  mov     r8d, edx
0x1800079a4  mov     qword ptr [rbx], 0
0x1800079ab  and     r8d, 0FFFFFF3Fh
0x1800079b2  mov     eax, edx
0x1800079b4  and     edx, 80h
0x1800079ba  mov     ecx, r8d
0x1800079bd  and     ecx, 3
0x1800079c0  mov     ebp, 40h ; '@'
0x1800079c5  shl     ecx, 2
0x1800079c8  and     eax, ebp
0x1800079ca  or      ecx, eax
0x1800079cc  shl     ecx, 2
0x1800079cf  or      ecx, edx
0x1800079d1  shl     ecx, 3
0x1800079d4  test    r8d, r8d
0x1800079d7  jnz     short loc_1800079E0
0x1800079d9  mov     edx, ebp
0x1800079db  mov     r8d, ebp
0x1800079de  jmp     short loc_1800079EC
0x1800079e0  xor     edx, edx
0x1800079e2  cmp     r8d, 2
0x1800079e6  cmovz   edx, ebp
0x1800079e9  mov     r8d, edx
0x1800079ec  mov     eax, ecx
0x1800079ee  mov     edi, 1
0x1800079f3  or      eax, r8d
0x1800079f6  or      ecx, edx
0x1800079f8  mov     [rbx], eax
0x1800079fa  bt      ecx, 0Ah
0x1800079fe  jnb     short loc_180007A0D
0x180007a00  cmp     ecx, 800h
0x180007a06  jb      short loc_180007A0D
0x180007a08  mov     sil, dil
0x180007a0b  jmp     short loc_180007A1B
0x180007a0d  xor     sil, sil
0x180007a10  xor     dl, dl
0x180007a12  test    bpl, cl
0x180007a15  jz      loc_180007AA5
0x180007a1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180007a22  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180007a27  test    al, al
0x180007a29  jz      short loc_180007A96
0x180007a2b  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180007a32  mov     r8d, [rax]
0x180007a35  test    r8b, 4
0x180007a39  jnz     short loc_180007A50
0x180007a3b  lea     rdx, [rsp+58h+arg_8]
0x180007a40  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x180007a45  mov     rcx, [rax]
0x180007a48  mov     [rsp+58h+arg_8], rcx
0x180007a4d  mov     r8d, ecx
0x180007a50  xor     eax, eax
0x180007a52  mov     word ptr [rsp+58h+arg_0+4], 3
0x180007a59  mov     r9d, r8d
0x180007a5c  mov     [rsp+58h+var_28], eax
0x180007a60  mov     dword ptr [rsp+58h+arg_0], eax
0x180007a64  lea     rcx, qword_180021888
0x180007a6b  shr     r9d, 0Bh
0x180007a6f  lea     rax, [rsp+58h+arg_0]
0x180007a74  shr     r8d, 0Ah
0x180007a78  and     r9d, edi
0x180007a7b  and     r8d, edi
0x180007a7e  mov     [rsp+58h+var_30], edi
0x180007a82  mov     edx, 37E286Ch
0x180007a87  mov     [rsp+58h+var_38], rax
0x180007a8c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180007a91  mov     dl, dil
0x180007a94  jmp     short loc_180007A98
0x180007a96  xor     dl, dl
0x180007a98  test    sil, sil
0x180007a9b  jz      short loc_180007AA5
0x180007a9d  test    dl, dl
0x180007a9f  jnz     short loc_180007AA5
0x180007aa1  btr     dword ptr [rbx], 0Ah
0x180007aa5  mov     eax, [rbx]
0x180007aa7  test    bpl, al
0x180007aaa  jz      short loc_180007AB0
0x180007aac  test    dl, dl
0x180007aae  jnz     short loc_180007AB2
0x180007ab0  xor     edi, edi
0x180007ab2  and     eax, 0FFFFFFFEh
0x180007ab5  or      eax, edi
0x180007ab7  mov     [rbx], eax
0x180007ab9  mov     rax, rbx
0x180007abc  mov     rbx, [rsp+58h+arg_10]
0x180007ac1  add     rsp, 40h
0x180007ac5  pop     rdi
0x180007ac6  pop     rsi
0x180007ac7  pop     rbp
0x180007ac8  retn
```
