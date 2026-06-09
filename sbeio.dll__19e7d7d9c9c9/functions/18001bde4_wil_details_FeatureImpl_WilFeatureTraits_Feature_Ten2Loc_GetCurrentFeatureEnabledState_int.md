# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bde4`
- end: `0x18001bec2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b554`

## callees

- `0x18001bde4`
- `0x180020444`
- `0x180026d60`
- `0x18002705c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl'::`2'::impl);
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
0x18001bde4  push    rbx
0x18001bde6  push    rbp
0x18001bde7  push    rsi
0x18001bde8  push    rdi
0x18001bde9  sub     rsp, 28h
0x18001bded  mov     ecx, 38419CAh; this
0x18001bdf2  mov     rbx, rdx
0x18001bdf5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bdfa  mov     edx, eax
0x18001bdfc  mov     qword ptr [rbx], 0
0x18001be03  and     edx, 0FFFFFF3Fh
0x18001be09  mov     ecx, eax
0x18001be0b  and     eax, 80h
0x18001be10  mov     r8d, edx
0x18001be13  and     r8d, 3
0x18001be17  mov     ebp, 40h ; '@'
0x18001be1c  shl     r8d, 2
0x18001be20  and     ecx, ebp
0x18001be22  or      r8d, ecx
0x18001be25  shl     r8d, 2
0x18001be29  or      r8d, eax
0x18001be2c  shl     r8d, 3
0x18001be30  test    edx, edx
0x18001be32  jnz     short loc_18001BE3A
0x18001be34  mov     ecx, ebp
0x18001be36  mov     edx, ebp
0x18001be38  jmp     short loc_18001BE44
0x18001be3a  xor     ecx, ecx
0x18001be3c  cmp     edx, 2
0x18001be3f  cmovz   ecx, ebp
0x18001be42  mov     edx, ecx
0x18001be44  mov     eax, r8d
0x18001be47  mov     edi, 1
0x18001be4c  or      eax, edx
0x18001be4e  or      r8d, ecx
0x18001be51  mov     [rbx], eax
0x18001be53  bt      r8d, 0Ah
0x18001be58  jnb     short loc_18001BE68
0x18001be5a  cmp     r8d, 800h
0x18001be61  jb      short loc_18001BE68
0x18001be63  mov     sil, dil
0x18001be66  jmp     short loc_18001BE72
0x18001be68  xor     sil, sil
0x18001be6b  xor     cl, cl
0x18001be6d  test    bpl, r8b
0x18001be70  jz      short loc_18001BEA2
0x18001be72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18001be79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18001be7e  test    al, al
0x18001be80  jz      short loc_18001BE93
0x18001be82  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl(void)'::`2'::impl
0x18001be89  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001be8e  mov     cl, dil
0x18001be91  jmp     short loc_18001BE95
0x18001be93  xor     cl, cl
0x18001be95  test    sil, sil
0x18001be98  jz      short loc_18001BEA2
0x18001be9a  test    cl, cl
0x18001be9c  jnz     short loc_18001BEA2
0x18001be9e  btr     dword ptr [rbx], 0Ah
0x18001bea2  mov     eax, [rbx]
0x18001bea4  test    bpl, al
0x18001bea7  jz      short loc_18001BEAD
0x18001bea9  test    cl, cl
0x18001beab  jnz     short loc_18001BEAF
0x18001bead  xor     edi, edi
0x18001beaf  and     eax, 0FFFFFFFEh
0x18001beb2  or      eax, edi
0x18001beb4  mov     [rbx], eax
0x18001beb6  mov     rax, rbx
0x18001beb9  add     rsp, 28h
0x18001bebd  pop     rdi
0x18001bebe  pop     rsi
0x18001bebf  pop     rbp
0x18001bec0  pop     rbx
0x18001bec1  retn
```
