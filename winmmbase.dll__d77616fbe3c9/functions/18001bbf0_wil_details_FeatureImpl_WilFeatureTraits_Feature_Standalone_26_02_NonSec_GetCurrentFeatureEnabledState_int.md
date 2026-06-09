# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bbf0`
- end: `0x18001bc5e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b2dc`

## callees

- `0x1800162fc`
- `0x18001bbf0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37E287E, (unsigned int)a2, a3, a4);
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
0x18001bbf0  push    rbx
0x18001bbf2  sub     rsp, 20h
0x18001bbf6  mov     ecx, 37E287Eh; this
0x18001bbfb  mov     rbx, rdx
0x18001bbfe  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bc03  mov     r9d, eax
0x18001bc06  mov     qword ptr [rbx], 0
0x18001bc0d  and     r9d, 0FFFFFF3Fh
0x18001bc14  mov     ecx, eax
0x18001bc16  and     eax, 80h
0x18001bc1b  mov     r8d, r9d
0x18001bc1e  and     r8d, 3
0x18001bc22  mov     edx, 40h ; '@'
0x18001bc27  shl     r8d, 2
0x18001bc2b  and     ecx, edx
0x18001bc2d  or      r8d, ecx
0x18001bc30  shl     r8d, 2
0x18001bc34  or      r8d, eax
0x18001bc37  shl     r8d, 3
0x18001bc3b  test    r9d, r9d
0x18001bc3e  jz      short loc_18001BC4B
0x18001bc40  xor     eax, eax
0x18001bc42  cmp     r9d, 2
0x18001bc46  cmovz   eax, edx
0x18001bc49  mov     edx, eax
0x18001bc4b  or      r8d, edx
0x18001bc4e  mov     rax, rbx
0x18001bc51  or      r8d, 1
0x18001bc55  mov     [rbx], r8d
0x18001bc58  add     rsp, 20h
0x18001bc5c  pop     rbx
0x18001bc5d  retn
```
