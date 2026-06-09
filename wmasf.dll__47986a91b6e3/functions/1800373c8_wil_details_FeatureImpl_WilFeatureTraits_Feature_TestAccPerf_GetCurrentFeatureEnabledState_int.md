# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800373c8`
- end: `0x1800374a6`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180036c54`

## callees

- `0x1800373c8`
- `0x180039e28`
- `0x18003bc40`
- `0x18003bf78`

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
0x1800373c8  push    rbx
0x1800373ca  push    rbp
0x1800373cb  push    rsi
0x1800373cc  push    rdi
0x1800373cd  sub     rsp, 28h
0x1800373d1  mov     ecx, 3667CADh; this
0x1800373d6  mov     rbx, rdx
0x1800373d9  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800373de  mov     edx, eax
0x1800373e0  mov     qword ptr [rbx], 0
0x1800373e7  and     edx, 0FFFFFF3Fh
0x1800373ed  mov     ecx, eax
0x1800373ef  and     eax, 80h
0x1800373f4  mov     r8d, edx
0x1800373f7  and     r8d, 3
0x1800373fb  mov     ebp, 40h ; '@'
0x180037400  shl     r8d, 2
0x180037404  and     ecx, ebp
0x180037406  or      r8d, ecx
0x180037409  shl     r8d, 2
0x18003740d  or      r8d, eax
0x180037410  shl     r8d, 3
0x180037414  test    edx, edx
0x180037416  jnz     short loc_18003741E
0x180037418  mov     ecx, ebp
0x18003741a  mov     edx, ebp
0x18003741c  jmp     short loc_180037428
0x18003741e  xor     ecx, ecx
0x180037420  cmp     edx, 2
0x180037423  cmovz   ecx, ebp
0x180037426  mov     edx, ecx
0x180037428  mov     eax, r8d
0x18003742b  mov     edi, 1
0x180037430  or      eax, edx
0x180037432  or      r8d, ecx
0x180037435  mov     [rbx], eax
0x180037437  bt      r8d, 0Ah
0x18003743c  jnb     short loc_18003744C
0x18003743e  cmp     r8d, 800h
0x180037445  jb      short loc_18003744C
0x180037447  mov     sil, dil
0x18003744a  jmp     short loc_180037456
0x18003744c  xor     sil, sil
0x18003744f  xor     cl, cl
0x180037451  test    bpl, r8b
0x180037454  jz      short loc_180037486
0x180037456  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18003745d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180037462  test    al, al
0x180037464  jz      short loc_180037477
0x180037466  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x18003746d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180037472  mov     cl, dil
0x180037475  jmp     short loc_180037479
0x180037477  xor     cl, cl
0x180037479  test    sil, sil
0x18003747c  jz      short loc_180037486
0x18003747e  test    cl, cl
0x180037480  jnz     short loc_180037486
0x180037482  btr     dword ptr [rbx], 0Ah
0x180037486  mov     eax, [rbx]
0x180037488  test    bpl, al
0x18003748b  jz      short loc_180037491
0x18003748d  test    cl, cl
0x18003748f  jnz     short loc_180037493
0x180037491  xor     edi, edi
0x180037493  and     eax, 0FFFFFFFEh
0x180037496  or      eax, edi
0x180037498  mov     [rbx], eax
0x18003749a  mov     rax, rbx
0x18003749d  add     rsp, 28h
0x1800374a1  pop     rdi
0x1800374a2  pop     rsi
0x1800374a3  pop     rbp
0x1800374a4  pop     rbx
0x1800374a5  retn
```
