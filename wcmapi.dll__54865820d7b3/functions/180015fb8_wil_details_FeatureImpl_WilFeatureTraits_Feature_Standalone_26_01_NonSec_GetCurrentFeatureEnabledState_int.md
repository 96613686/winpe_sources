# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015fb8`
- end: `0x180016027`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001593c`

## callees

- `0x180015fb8`
- `0x180016cd4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37E286C, (unsigned int)a2, a3, a4);
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
0x180015fb8  push    rbx
0x180015fba  sub     rsp, 20h
0x180015fbe  mov     ecx, 37E286Ch; this
0x180015fc3  mov     rbx, rdx
0x180015fc6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015fcb  mov     r9d, eax
0x180015fce  mov     qword ptr [rbx], 0
0x180015fd5  and     r9d, 0FFFFFF3Fh
0x180015fdc  mov     ecx, eax
0x180015fde  and     eax, 80h
0x180015fe3  mov     r8d, r9d
0x180015fe6  and     r8d, 3
0x180015fea  mov     edx, 40h ; '@'
0x180015fef  shl     r8d, 2
0x180015ff3  and     ecx, edx
0x180015ff5  or      r8d, ecx
0x180015ff8  shl     r8d, 2
0x180015ffc  or      r8d, eax
0x180015fff  shl     r8d, 3
0x180016003  test    r9d, r9d
0x180016006  jz      short loc_180016013
0x180016008  xor     eax, eax
0x18001600a  cmp     r9d, 2
0x18001600e  cmovz   eax, edx
0x180016011  mov     edx, eax
0x180016013  or      r8d, edx
0x180016016  mov     rax, rbx
0x180016019  or      r8d, 1
0x18001601d  mov     [rbx], r8d
0x180016020  add     rsp, 20h
0x180016024  pop     rbx
0x180016025  retn
```
