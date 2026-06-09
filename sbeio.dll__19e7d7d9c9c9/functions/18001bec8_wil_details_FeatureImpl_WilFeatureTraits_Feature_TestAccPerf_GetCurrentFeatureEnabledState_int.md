# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bec8`
- end: `0x18001bfa6`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b648`

## callees

- `0x18001bec8`
- `0x18002030c`
- `0x180026d60`
- `0x180027098`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
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
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl'::`2'::impl);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001bec8  push    rbx
0x18001beca  push    rbp
0x18001becb  push    rsi
0x18001becc  push    rdi
0x18001becd  sub     rsp, 28h
0x18001bed1  mov     ecx, 3667CADh; this
0x18001bed6  mov     rbx, rdx
0x18001bed9  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bede  mov     edx, eax
0x18001bee0  mov     qword ptr [rbx], 0
0x18001bee7  and     edx, 0FFFFFF3Fh
0x18001beed  mov     ecx, eax
0x18001beef  and     eax, 80h
0x18001bef4  mov     r8d, edx
0x18001bef7  and     r8d, 3
0x18001befb  mov     ebp, 40h ; '@'
0x18001bf00  shl     r8d, 2
0x18001bf04  and     ecx, ebp
0x18001bf06  or      r8d, ecx
0x18001bf09  shl     r8d, 2
0x18001bf0d  or      r8d, eax
0x18001bf10  shl     r8d, 3
0x18001bf14  test    edx, edx
0x18001bf16  jnz     short loc_18001BF1E
0x18001bf18  mov     ecx, ebp
0x18001bf1a  mov     edx, ebp
0x18001bf1c  jmp     short loc_18001BF28
0x18001bf1e  xor     ecx, ecx
0x18001bf20  cmp     edx, 2
0x18001bf23  cmovz   ecx, ebp
0x18001bf26  mov     edx, ecx
0x18001bf28  mov     eax, r8d
0x18001bf2b  mov     edi, 1
0x18001bf30  or      eax, edx
0x18001bf32  or      r8d, ecx
0x18001bf35  mov     [rbx], eax
0x18001bf37  bt      r8d, 0Ah
0x18001bf3c  jnb     short loc_18001BF4C
0x18001bf3e  cmp     r8d, 800h
0x18001bf45  jb      short loc_18001BF4C
0x18001bf47  mov     sil, dil
0x18001bf4a  jmp     short loc_18001BF56
0x18001bf4c  xor     sil, sil
0x18001bf4f  xor     cl, cl
0x18001bf51  test    bpl, r8b
0x18001bf54  jz      short loc_18001BF86
0x18001bf56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18001bf5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18001bf62  test    al, al
0x18001bf64  jz      short loc_18001BF77
0x18001bf66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x18001bf6d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001bf72  mov     cl, dil
0x18001bf75  jmp     short loc_18001BF79
0x18001bf77  xor     cl, cl
0x18001bf79  test    sil, sil
0x18001bf7c  jz      short loc_18001BF86
0x18001bf7e  test    cl, cl
0x18001bf80  jnz     short loc_18001BF86
0x18001bf82  btr     dword ptr [rbx], 0Ah
0x18001bf86  mov     eax, [rbx]
0x18001bf88  test    bpl, al
0x18001bf8b  jz      short loc_18001BF91
0x18001bf8d  test    cl, cl
0x18001bf8f  jnz     short loc_18001BF93
0x18001bf91  xor     edi, edi
0x18001bf93  and     eax, 0FFFFFFFEh
0x18001bf96  or      eax, edi
0x18001bf98  mov     [rbx], eax
0x18001bf9a  mov     rax, rbx
0x18001bf9d  add     rsp, 28h
0x18001bfa1  pop     rdi
0x18001bfa2  pop     rsi
0x18001bfa3  pop     rbp
0x18001bfa4  pop     rbx
0x18001bfa5  retn
```
