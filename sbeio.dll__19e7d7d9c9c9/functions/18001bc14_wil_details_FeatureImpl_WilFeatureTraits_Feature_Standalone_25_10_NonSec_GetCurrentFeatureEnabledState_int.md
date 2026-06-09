# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bc14`
- end: `0x18001bc82`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b184`

## callees

- `0x18001bc14`
- `0x180026d60`

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
0x18001bc14  push    rbx
0x18001bc16  sub     rsp, 20h
0x18001bc1a  mov     ecx, 2AF34F8h; this
0x18001bc1f  mov     rbx, rdx
0x18001bc22  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bc27  mov     r9d, eax
0x18001bc2a  mov     qword ptr [rbx], 0
0x18001bc31  and     r9d, 0FFFFFF3Fh
0x18001bc38  mov     ecx, eax
0x18001bc3a  and     eax, 80h
0x18001bc3f  mov     r8d, r9d
0x18001bc42  and     r8d, 3
0x18001bc46  mov     edx, 40h ; '@'
0x18001bc4b  shl     r8d, 2
0x18001bc4f  and     ecx, edx
0x18001bc51  or      r8d, ecx
0x18001bc54  shl     r8d, 2
0x18001bc58  or      r8d, eax
0x18001bc5b  shl     r8d, 3
0x18001bc5f  test    r9d, r9d
0x18001bc62  jz      short loc_18001BC6F
0x18001bc64  xor     eax, eax
0x18001bc66  cmp     r9d, 2
0x18001bc6a  cmovz   eax, edx
0x18001bc6d  mov     edx, eax
0x18001bc6f  or      r8d, edx
0x18001bc72  mov     rax, rbx
0x18001bc75  or      r8d, 1
0x18001bc79  mov     [rbx], r8d
0x18001bc7c  add     rsp, 20h
0x18001bc80  pop     rbx
0x18001bc81  retn
```
