# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bfe4`
- end: `0x18001c052`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b73c`

## callees

- `0x1800162fc`
- `0x18001bfe4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA2, (unsigned int)a2, a3, a4);
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
0x18001bfe4  push    rbx
0x18001bfe6  sub     rsp, 20h
0x18001bfea  mov     ecx, 3667CA2h; this
0x18001bfef  mov     rbx, rdx
0x18001bff2  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bff7  mov     r9d, eax
0x18001bffa  mov     qword ptr [rbx], 0
0x18001c001  and     r9d, 0FFFFFF3Fh
0x18001c008  mov     ecx, eax
0x18001c00a  and     eax, 80h
0x18001c00f  mov     r8d, r9d
0x18001c012  and     r8d, 3
0x18001c016  mov     edx, 40h ; '@'
0x18001c01b  shl     r8d, 2
0x18001c01f  and     ecx, edx
0x18001c021  or      r8d, ecx
0x18001c024  shl     r8d, 2
0x18001c028  or      r8d, eax
0x18001c02b  shl     r8d, 3
0x18001c02f  test    r9d, r9d
0x18001c032  jz      short loc_18001C03F
0x18001c034  xor     eax, eax
0x18001c036  cmp     r9d, 2
0x18001c03a  cmovz   eax, edx
0x18001c03d  mov     edx, eax
0x18001c03f  or      r8d, edx
0x18001c042  mov     rax, rbx
0x18001c045  or      r8d, 1
0x18001c049  mov     [rbx], r8d
0x18001c04c  add     rsp, 20h
0x18001c050  pop     rbx
0x18001c051  retn
```
