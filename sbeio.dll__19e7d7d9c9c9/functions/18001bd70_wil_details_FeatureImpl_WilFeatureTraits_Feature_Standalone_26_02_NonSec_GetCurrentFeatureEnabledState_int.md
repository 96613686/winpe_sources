# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bd70`
- end: `0x18001bdde`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b460`

## callees

- `0x18001bd70`
- `0x180026d60`

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
0x18001bd70  push    rbx
0x18001bd72  sub     rsp, 20h
0x18001bd76  mov     ecx, 37E287Eh; this
0x18001bd7b  mov     rbx, rdx
0x18001bd7e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bd83  mov     r9d, eax
0x18001bd86  mov     qword ptr [rbx], 0
0x18001bd8d  and     r9d, 0FFFFFF3Fh
0x18001bd94  mov     ecx, eax
0x18001bd96  and     eax, 80h
0x18001bd9b  mov     r8d, r9d
0x18001bd9e  and     r8d, 3
0x18001bda2  mov     edx, 40h ; '@'
0x18001bda7  shl     r8d, 2
0x18001bdab  and     ecx, edx
0x18001bdad  or      r8d, ecx
0x18001bdb0  shl     r8d, 2
0x18001bdb4  or      r8d, eax
0x18001bdb7  shl     r8d, 3
0x18001bdbb  test    r9d, r9d
0x18001bdbe  jz      short loc_18001BDCB
0x18001bdc0  xor     eax, eax
0x18001bdc2  cmp     r9d, 2
0x18001bdc6  cmovz   eax, edx
0x18001bdc9  mov     edx, eax
0x18001bdcb  or      r8d, edx
0x18001bdce  mov     rax, rbx
0x18001bdd1  or      r8d, 1
0x18001bdd5  mov     [rbx], r8d
0x18001bdd8  add     rsp, 20h
0x18001bddc  pop     rbx
0x18001bddd  retn
```
