# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015ec8`
- end: `0x180015f37`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015754`

## callees

- `0x180015ec8`
- `0x180016cd4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // r9d
  int v7; // edx
  int v8; // r8d
  int v9; // eax
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2AF34F8, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 64;
  v8 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v9 = 0;
    if ( v6 == 2 )
      v9 = 64;
    v7 = v9;
  }
  result = a2;
  *(_DWORD *)a2 = v7 | v8 | 1;
  return result;
}

```

## disassembly

```asm
0x180015ec8  push    rbx
0x180015eca  sub     rsp, 20h
0x180015ece  mov     ecx, 2AF34F8h; this
0x180015ed3  mov     rbx, rdx
0x180015ed6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015edb  mov     r9d, eax
0x180015ede  mov     qword ptr [rbx], 0
0x180015ee5  and     r9d, 0FFFFFF3Fh
0x180015eec  mov     ecx, eax
0x180015eee  and     eax, 80h
0x180015ef3  mov     r8d, r9d
0x180015ef6  and     r8d, 3
0x180015efa  mov     edx, 40h ; '@'
0x180015eff  shl     r8d, 2
0x180015f03  and     ecx, edx
0x180015f05  or      r8d, ecx
0x180015f08  shl     r8d, 2
0x180015f0c  or      r8d, eax
0x180015f0f  shl     r8d, 3
0x180015f13  test    r9d, r9d
0x180015f16  jz      short loc_180015F23
0x180015f18  xor     eax, eax
0x180015f1a  cmp     r9d, 2
0x180015f1e  cmovz   eax, edx
0x180015f21  mov     edx, eax
0x180015f23  or      r8d, edx
0x180015f26  mov     rax, rbx
0x180015f29  or      r8d, 1
0x180015f2d  mov     [rbx], r8d
0x180015f30  add     rsp, 20h
0x180015f34  pop     rbx
0x180015f35  retn
```
