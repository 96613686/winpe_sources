# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015f40`
- end: `0x180015faf`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015848`

## callees

- `0x180015f40`
- `0x180016cd4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2AF34FD, (unsigned int)a2, a3, a4);
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
0x180015f40  push    rbx
0x180015f42  sub     rsp, 20h
0x180015f46  mov     ecx, 2AF34FDh; this
0x180015f4b  mov     rbx, rdx
0x180015f4e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015f53  mov     r9d, eax
0x180015f56  mov     qword ptr [rbx], 0
0x180015f5d  and     r9d, 0FFFFFF3Fh
0x180015f64  mov     ecx, eax
0x180015f66  and     eax, 80h
0x180015f6b  mov     r8d, r9d
0x180015f6e  and     r8d, 3
0x180015f72  mov     edx, 40h ; '@'
0x180015f77  shl     r8d, 2
0x180015f7b  and     ecx, edx
0x180015f7d  or      r8d, ecx
0x180015f80  shl     r8d, 2
0x180015f84  or      r8d, eax
0x180015f87  shl     r8d, 3
0x180015f8b  test    r9d, r9d
0x180015f8e  jz      short loc_180015F9B
0x180015f90  xor     eax, eax
0x180015f92  cmp     r9d, 2
0x180015f96  cmovz   eax, edx
0x180015f99  mov     edx, eax
0x180015f9b  or      r8d, edx
0x180015f9e  mov     rax, rbx
0x180015fa1  or      r8d, 1
0x180015fa5  mov     [rbx], r8d
0x180015fa8  add     rsp, 20h
0x180015fac  pop     rbx
0x180015fad  retn
```
