# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001c090`
- end: `0x18001c15e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b830`

## callees

- `0x18001c090`
- `0x180020270`
- `0x180020770`
- `0x180026d60`

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
0x18001c090  mov     [rsp+arg_0], rbx
0x18001c095  mov     [rsp+arg_8], rsi
0x18001c09a  push    rdi
0x18001c09b  sub     rsp, 20h
0x18001c09f  mov     ecx, 3667CA7h; this
0x18001c0a4  mov     rbx, rdx
0x18001c0a7  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001c0ac  mov     edx, eax
0x18001c0ae  mov     qword ptr [rbx], 0
0x18001c0b5  and     edx, 0FFFFFF3Fh
0x18001c0bb  mov     ecx, eax
0x18001c0bd  and     eax, 80h
0x18001c0c2  mov     r8d, edx
0x18001c0c5  and     r8d, 3
0x18001c0c9  mov     esi, 40h ; '@'
0x18001c0ce  shl     r8d, 2
0x18001c0d2  and     ecx, esi
0x18001c0d4  or      r8d, ecx
0x18001c0d7  shl     r8d, 2
0x18001c0db  or      r8d, eax
0x18001c0de  shl     r8d, 3
0x18001c0e2  test    edx, edx
0x18001c0e4  jnz     short loc_18001C0EC
0x18001c0e6  mov     ecx, esi
0x18001c0e8  mov     edx, esi
0x18001c0ea  jmp     short loc_18001C0F6
0x18001c0ec  xor     ecx, ecx
0x18001c0ee  cmp     edx, 2
0x18001c0f1  cmovz   ecx, esi
0x18001c0f4  mov     edx, ecx
0x18001c0f6  mov     eax, r8d
0x18001c0f9  mov     edi, 1
0x18001c0fe  or      eax, edx
0x18001c100  or      r8d, ecx
0x18001c103  mov     [rbx], eax
0x18001c105  bt      r8d, 0Ah
0x18001c10a  jnb     short loc_18001C115
0x18001c10c  cmp     r8d, 800h
0x18001c113  jnb     short loc_18001C11C
0x18001c115  xor     cl, cl
0x18001c117  test    sil, r8b
0x18001c11a  jz      short loc_18001C137
0x18001c11c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x18001c123  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001c128  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x18001c12f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001c134  mov     cl, dil
0x18001c137  mov     eax, [rbx]
0x18001c139  test    sil, al
0x18001c13c  jz      short loc_18001C142
0x18001c13e  test    cl, cl
0x18001c140  jnz     short loc_18001C144
0x18001c142  xor     edi, edi
0x18001c144  mov     rsi, [rsp+28h+arg_8]
0x18001c149  and     eax, 0FFFFFFFEh
0x18001c14c  or      eax, edi
0x18001c14e  mov     [rbx], eax
0x18001c150  mov     rax, rbx
0x18001c153  mov     rbx, [rsp+28h+arg_0]
0x18001c158  add     rsp, 20h
0x18001c15c  pop     rdi
0x18001c15d  retn
```
