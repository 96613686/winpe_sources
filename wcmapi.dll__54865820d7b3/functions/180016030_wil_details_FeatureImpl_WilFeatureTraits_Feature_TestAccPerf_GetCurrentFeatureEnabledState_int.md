# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180016030`
- end: `0x18001610f`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015a30`

## callees

- `0x180016030`
- `0x180016740`
- `0x180016cd4`
- `0x180016db4`

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
0x180016030  push    rbx
0x180016032  push    rbp
0x180016033  push    rsi
0x180016034  push    rdi
0x180016035  sub     rsp, 28h
0x180016039  mov     ecx, 3667CADh; this
0x18001603e  mov     rbx, rdx
0x180016041  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180016046  mov     edx, eax
0x180016048  mov     qword ptr [rbx], 0
0x18001604f  and     edx, 0FFFFFF3Fh
0x180016055  mov     ecx, eax
0x180016057  and     eax, 80h
0x18001605c  mov     r8d, edx
0x18001605f  and     r8d, 3
0x180016063  mov     ebp, 40h ; '@'
0x180016068  shl     r8d, 2
0x18001606c  and     ecx, ebp
0x18001606e  or      r8d, ecx
0x180016071  shl     r8d, 2
0x180016075  or      r8d, eax
0x180016078  shl     r8d, 3
0x18001607c  test    edx, edx
0x18001607e  jnz     short loc_180016086
0x180016080  mov     ecx, ebp
0x180016082  mov     edx, ebp
0x180016084  jmp     short loc_180016090
0x180016086  xor     ecx, ecx
0x180016088  cmp     edx, 2
0x18001608b  cmovz   ecx, ebp
0x18001608e  mov     edx, ecx
0x180016090  mov     eax, r8d
0x180016093  mov     edi, 1
0x180016098  or      eax, edx
0x18001609a  or      r8d, ecx
0x18001609d  mov     [rbx], eax
0x18001609f  bt      r8d, 0Ah
0x1800160a4  jnb     short loc_1800160B4
0x1800160a6  cmp     r8d, 800h
0x1800160ad  jb      short loc_1800160B4
0x1800160af  mov     sil, dil
0x1800160b2  jmp     short loc_1800160BE
0x1800160b4  xor     sil, sil
0x1800160b7  xor     cl, cl
0x1800160b9  test    bpl, r8b
0x1800160bc  jz      short loc_1800160EE
0x1800160be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x1800160c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x1800160ca  test    al, al
0x1800160cc  jz      short loc_1800160DF
0x1800160ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x1800160d5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800160da  mov     cl, dil
0x1800160dd  jmp     short loc_1800160E1
0x1800160df  xor     cl, cl
0x1800160e1  test    sil, sil
0x1800160e4  jz      short loc_1800160EE
0x1800160e6  test    cl, cl
0x1800160e8  jnz     short loc_1800160EE
0x1800160ea  btr     dword ptr [rbx], 0Ah
0x1800160ee  mov     eax, [rbx]
0x1800160f0  test    bpl, al
0x1800160f3  jz      short loc_1800160F9
0x1800160f5  test    cl, cl
0x1800160f7  jnz     short loc_1800160FB
0x1800160f9  xor     edi, edi
0x1800160fb  and     eax, 0FFFFFFFEh
0x1800160fe  or      eax, edi
0x180016100  mov     [rbx], eax
0x180016102  mov     rax, rbx
0x180016105  add     rsp, 28h
0x180016109  pop     rdi
0x18001610a  pop     rsi
0x18001610b  pop     rbp
0x18001610c  pop     rbx
0x18001610d  retn
```
