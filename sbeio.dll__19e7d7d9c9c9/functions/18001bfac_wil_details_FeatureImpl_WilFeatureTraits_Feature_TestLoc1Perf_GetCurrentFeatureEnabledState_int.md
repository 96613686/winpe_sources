# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bfac`
- end: `0x18001c08a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b73c`

## callees

- `0x18001bfac`
- `0x1800203a8`
- `0x180026d60`
- `0x180027020`

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
0x18001bfac  push    rbx
0x18001bfae  push    rbp
0x18001bfaf  push    rsi
0x18001bfb0  push    rdi
0x18001bfb1  sub     rsp, 28h
0x18001bfb5  mov     ecx, 38419ACh; this
0x18001bfba  mov     rbx, rdx
0x18001bfbd  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bfc2  mov     edx, eax
0x18001bfc4  mov     qword ptr [rbx], 0
0x18001bfcb  and     edx, 0FFFFFF3Fh
0x18001bfd1  mov     ecx, eax
0x18001bfd3  and     eax, 80h
0x18001bfd8  mov     r8d, edx
0x18001bfdb  and     r8d, 3
0x18001bfdf  mov     ebp, 40h ; '@'
0x18001bfe4  shl     r8d, 2
0x18001bfe8  and     ecx, ebp
0x18001bfea  or      r8d, ecx
0x18001bfed  shl     r8d, 2
0x18001bff1  or      r8d, eax
0x18001bff4  shl     r8d, 3
0x18001bff8  test    edx, edx
0x18001bffa  jnz     short loc_18001C002
0x18001bffc  mov     ecx, ebp
0x18001bffe  mov     edx, ebp
0x18001c000  jmp     short loc_18001C00C
0x18001c002  xor     ecx, ecx
0x18001c004  cmp     edx, 2
0x18001c007  cmovz   ecx, ebp
0x18001c00a  mov     edx, ecx
0x18001c00c  mov     eax, r8d
0x18001c00f  mov     edi, 1
0x18001c014  or      eax, edx
0x18001c016  or      r8d, ecx
0x18001c019  mov     [rbx], eax
0x18001c01b  bt      r8d, 0Ah
0x18001c020  jnb     short loc_18001C030
0x18001c022  cmp     r8d, 800h
0x18001c029  jb      short loc_18001C030
0x18001c02b  mov     sil, dil
0x18001c02e  jmp     short loc_18001C03A
0x18001c030  xor     sil, sil
0x18001c033  xor     cl, cl
0x18001c035  test    bpl, r8b
0x18001c038  jz      short loc_18001C06A
0x18001c03a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18001c041  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18001c046  test    al, al
0x18001c048  jz      short loc_18001C05B
0x18001c04a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x18001c051  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001c056  mov     cl, dil
0x18001c059  jmp     short loc_18001C05D
0x18001c05b  xor     cl, cl
0x18001c05d  test    sil, sil
0x18001c060  jz      short loc_18001C06A
0x18001c062  test    cl, cl
0x18001c064  jnz     short loc_18001C06A
0x18001c066  btr     dword ptr [rbx], 0Ah
0x18001c06a  mov     eax, [rbx]
0x18001c06c  test    bpl, al
0x18001c06f  jz      short loc_18001C075
0x18001c071  test    cl, cl
0x18001c073  jnz     short loc_18001C077
0x18001c075  xor     edi, edi
0x18001c077  and     eax, 0FFFFFFFEh
0x18001c07a  or      eax, edi
0x18001c07c  mov     [rbx], eax
0x18001c07e  mov     rax, rbx
0x18001c081  add     rsp, 28h
0x18001c085  pop     rdi
0x18001c086  pop     rsi
0x18001c087  pop     rbp
0x18001c088  pop     rbx
0x18001c089  retn
```
