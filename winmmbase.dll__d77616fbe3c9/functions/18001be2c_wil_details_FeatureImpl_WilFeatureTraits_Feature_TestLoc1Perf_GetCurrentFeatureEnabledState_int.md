# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001be2c`
- end: `0x18001bf0a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b57c`

## callees

- `0x1800162fc`
- `0x18001be2c`
- `0x18001c420`
- `0x18001c8e8`

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
0x18001be2c  push    rbx
0x18001be2e  push    rbp
0x18001be2f  push    rsi
0x18001be30  push    rdi
0x18001be31  sub     rsp, 28h
0x18001be35  mov     ecx, 38419ACh; this
0x18001be3a  mov     rbx, rdx
0x18001be3d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001be42  mov     edx, eax
0x18001be44  mov     qword ptr [rbx], 0
0x18001be4b  and     edx, 0FFFFFF3Fh
0x18001be51  mov     ecx, eax
0x18001be53  and     eax, 80h
0x18001be58  mov     r8d, edx
0x18001be5b  and     r8d, 3
0x18001be5f  mov     ebp, 40h ; '@'
0x18001be64  shl     r8d, 2
0x18001be68  and     ecx, ebp
0x18001be6a  or      r8d, ecx
0x18001be6d  shl     r8d, 2
0x18001be71  or      r8d, eax
0x18001be74  shl     r8d, 3
0x18001be78  test    edx, edx
0x18001be7a  jnz     short loc_18001BE82
0x18001be7c  mov     ecx, ebp
0x18001be7e  mov     edx, ebp
0x18001be80  jmp     short loc_18001BE8C
0x18001be82  xor     ecx, ecx
0x18001be84  cmp     edx, 2
0x18001be87  cmovz   ecx, ebp
0x18001be8a  mov     edx, ecx
0x18001be8c  mov     eax, r8d
0x18001be8f  mov     edi, 1
0x18001be94  or      eax, edx
0x18001be96  or      r8d, ecx
0x18001be99  mov     [rbx], eax
0x18001be9b  bt      r8d, 0Ah
0x18001bea0  jnb     short loc_18001BEB0
0x18001bea2  cmp     r8d, 800h
0x18001bea9  jb      short loc_18001BEB0
0x18001beab  mov     sil, dil
0x18001beae  jmp     short loc_18001BEBA
0x18001beb0  xor     sil, sil
0x18001beb3  xor     cl, cl
0x18001beb5  test    bpl, r8b
0x18001beb8  jz      short loc_18001BEEA
0x18001beba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18001bec1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18001bec6  test    al, al
0x18001bec8  jz      short loc_18001BEDB
0x18001beca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x18001bed1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001bed6  mov     cl, dil
0x18001bed9  jmp     short loc_18001BEDD
0x18001bedb  xor     cl, cl
0x18001bedd  test    sil, sil
0x18001bee0  jz      short loc_18001BEEA
0x18001bee2  test    cl, cl
0x18001bee4  jnz     short loc_18001BEEA
0x18001bee6  btr     dword ptr [rbx], 0Ah
0x18001beea  mov     eax, [rbx]
0x18001beec  test    bpl, al
0x18001beef  jz      short loc_18001BEF5
0x18001bef1  test    cl, cl
0x18001bef3  jnz     short loc_18001BEF7
0x18001bef5  xor     edi, edi
0x18001bef7  and     eax, 0FFFFFFFEh
0x18001befa  or      eax, edi
0x18001befc  mov     [rbx], eax
0x18001befe  mov     rax, rbx
0x18001bf01  add     rsp, 28h
0x18001bf05  pop     rdi
0x18001bf06  pop     rsi
0x18001bf07  pop     rbp
0x18001bf08  pop     rbx
0x18001bf09  retn
```
