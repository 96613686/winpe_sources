# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180016118`
- end: `0x1800161f7`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015b24`

## callees

- `0x180016118`
- `0x1800167dc`
- `0x180016cd4`
- `0x180016d3c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl'::`2'::impl);
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
0x180016118  push    rbx
0x18001611a  push    rbp
0x18001611b  push    rsi
0x18001611c  push    rdi
0x18001611d  sub     rsp, 28h
0x180016121  mov     ecx, 38419ACh; this
0x180016126  mov     rbx, rdx
0x180016129  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001612e  mov     edx, eax
0x180016130  mov     qword ptr [rbx], 0
0x180016137  and     edx, 0FFFFFF3Fh
0x18001613d  mov     ecx, eax
0x18001613f  and     eax, 80h
0x180016144  mov     r8d, edx
0x180016147  and     r8d, 3
0x18001614b  mov     ebp, 40h ; '@'
0x180016150  shl     r8d, 2
0x180016154  and     ecx, ebp
0x180016156  or      r8d, ecx
0x180016159  shl     r8d, 2
0x18001615d  or      r8d, eax
0x180016160  shl     r8d, 3
0x180016164  test    edx, edx
0x180016166  jnz     short loc_18001616E
0x180016168  mov     ecx, ebp
0x18001616a  mov     edx, ebp
0x18001616c  jmp     short loc_180016178
0x18001616e  xor     ecx, ecx
0x180016170  cmp     edx, 2
0x180016173  cmovz   ecx, ebp
0x180016176  mov     edx, ecx
0x180016178  mov     eax, r8d
0x18001617b  mov     edi, 1
0x180016180  or      eax, edx
0x180016182  or      r8d, ecx
0x180016185  mov     [rbx], eax
0x180016187  bt      r8d, 0Ah
0x18001618c  jnb     short loc_18001619C
0x18001618e  cmp     r8d, 800h
0x180016195  jb      short loc_18001619C
0x180016197  mov     sil, dil
0x18001619a  jmp     short loc_1800161A6
0x18001619c  xor     sil, sil
0x18001619f  xor     cl, cl
0x1800161a1  test    bpl, r8b
0x1800161a4  jz      short loc_1800161D6
0x1800161a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x1800161ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x1800161b2  test    al, al
0x1800161b4  jz      short loc_1800161C7
0x1800161b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x1800161bd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800161c2  mov     cl, dil
0x1800161c5  jmp     short loc_1800161C9
0x1800161c7  xor     cl, cl
0x1800161c9  test    sil, sil
0x1800161cc  jz      short loc_1800161D6
0x1800161ce  test    cl, cl
0x1800161d0  jnz     short loc_1800161D6
0x1800161d2  btr     dword ptr [rbx], 0Ah
0x1800161d6  mov     eax, [rbx]
0x1800161d8  test    bpl, al
0x1800161db  jz      short loc_1800161E1
0x1800161dd  test    cl, cl
0x1800161df  jnz     short loc_1800161E3
0x1800161e1  xor     edi, edi
0x1800161e3  and     eax, 0FFFFFFFEh
0x1800161e6  or      eax, edi
0x1800161e8  mov     [rbx], eax
0x1800161ea  mov     rax, rbx
0x1800161ed  add     rsp, 28h
0x1800161f1  pop     rdi
0x1800161f2  pop     rsi
0x1800161f3  pop     rbp
0x1800161f4  pop     rbx
0x1800161f5  retn
```
