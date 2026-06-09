# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180016200`
- end: `0x1800162cf`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015c18`

## callees

- `0x180016200`
- `0x1800166a4`
- `0x180016a64`
- `0x180016cd4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
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
  char v12; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, (unsigned int)a2, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl'::`2'::impl);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl'::`2'::impl);
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
0x180016200  mov     [rsp+arg_0], rbx
0x180016205  mov     [rsp+arg_8], rsi
0x18001620a  push    rdi
0x18001620b  sub     rsp, 20h
0x18001620f  mov     ecx, 3667CA7h; this
0x180016214  mov     rbx, rdx
0x180016217  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001621c  mov     edx, eax
0x18001621e  mov     qword ptr [rbx], 0
0x180016225  and     edx, 0FFFFFF3Fh
0x18001622b  mov     ecx, eax
0x18001622d  and     eax, 80h
0x180016232  mov     r8d, edx
0x180016235  and     r8d, 3
0x180016239  mov     esi, 40h ; '@'
0x18001623e  shl     r8d, 2
0x180016242  and     ecx, esi
0x180016244  or      r8d, ecx
0x180016247  shl     r8d, 2
0x18001624b  or      r8d, eax
0x18001624e  shl     r8d, 3
0x180016252  test    edx, edx
0x180016254  jnz     short loc_18001625C
0x180016256  mov     ecx, esi
0x180016258  mov     edx, esi
0x18001625a  jmp     short loc_180016266
0x18001625c  xor     ecx, ecx
0x18001625e  cmp     edx, 2
0x180016261  cmovz   ecx, esi
0x180016264  mov     edx, ecx
0x180016266  mov     eax, r8d
0x180016269  mov     edi, 1
0x18001626e  or      eax, edx
0x180016270  or      r8d, ecx
0x180016273  mov     [rbx], eax
0x180016275  bt      r8d, 0Ah
0x18001627a  jnb     short loc_180016285
0x18001627c  cmp     r8d, 800h
0x180016283  jnb     short loc_18001628C
0x180016285  xor     cl, cl
0x180016287  test    sil, r8b
0x18001628a  jz      short loc_1800162A7
0x18001628c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x180016293  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180016298  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x18001629f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800162a4  mov     cl, dil
0x1800162a7  mov     eax, [rbx]
0x1800162a9  test    sil, al
0x1800162ac  jz      short loc_1800162B2
0x1800162ae  test    cl, cl
0x1800162b0  jnz     short loc_1800162B4
0x1800162b2  xor     edi, edi
0x1800162b4  mov     rsi, [rsp+28h+arg_8]
0x1800162b9  and     eax, 0FFFFFFFEh
0x1800162bc  or      eax, edi
0x1800162be  mov     [rbx], eax
0x1800162c0  mov     rax, rbx
0x1800162c3  mov     rbx, [rsp+28h+arg_0]
0x1800162c8  add     rsp, 20h
0x1800162cc  pop     rdi
0x1800162cd  retn
```
