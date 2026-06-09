# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bb08`
- end: `0x18001bb76`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b11c`

## callees

- `0x1800162fc`
- `0x18001bb08`

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
0x18001bb08  push    rbx
0x18001bb0a  sub     rsp, 20h
0x18001bb0e  mov     ecx, 2AF34FDh; this
0x18001bb13  mov     rbx, rdx
0x18001bb16  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bb1b  mov     r9d, eax
0x18001bb1e  mov     qword ptr [rbx], 0
0x18001bb25  and     r9d, 0FFFFFF3Fh
0x18001bb2c  mov     ecx, eax
0x18001bb2e  and     eax, 80h
0x18001bb33  mov     r8d, r9d
0x18001bb36  and     r8d, 3
0x18001bb3a  mov     edx, 40h ; '@'
0x18001bb3f  shl     r8d, 2
0x18001bb43  and     ecx, edx
0x18001bb45  or      r8d, ecx
0x18001bb48  shl     r8d, 2
0x18001bb4c  or      r8d, eax
0x18001bb4f  shl     r8d, 3
0x18001bb53  test    r9d, r9d
0x18001bb56  jz      short loc_18001BB63
0x18001bb58  xor     eax, eax
0x18001bb5a  cmp     r9d, 2
0x18001bb5e  cmovz   eax, edx
0x18001bb61  mov     edx, eax
0x18001bb63  or      r8d, edx
0x18001bb66  mov     rax, rbx
0x18001bb69  or      r8d, 1
0x18001bb6d  mov     [rbx], r8d
0x18001bb70  add     rsp, 20h
0x18001bb74  pop     rbx
0x18001bb75  retn
```
