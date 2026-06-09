# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bcfc`
- end: `0x18001bd6a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b36c`

## callees

- `0x18001bcfc`
- `0x180026d60`

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
0x18001bcfc  push    rbx
0x18001bcfe  sub     rsp, 20h
0x18001bd02  mov     ecx, 37E286Ch; this
0x18001bd07  mov     rbx, rdx
0x18001bd0a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bd0f  mov     r9d, eax
0x18001bd12  mov     qword ptr [rbx], 0
0x18001bd19  and     r9d, 0FFFFFF3Fh
0x18001bd20  mov     ecx, eax
0x18001bd22  and     eax, 80h
0x18001bd27  mov     r8d, r9d
0x18001bd2a  and     r8d, 3
0x18001bd2e  mov     edx, 40h ; '@'
0x18001bd33  shl     r8d, 2
0x18001bd37  and     ecx, edx
0x18001bd39  or      r8d, ecx
0x18001bd3c  shl     r8d, 2
0x18001bd40  or      r8d, eax
0x18001bd43  shl     r8d, 3
0x18001bd47  test    r9d, r9d
0x18001bd4a  jz      short loc_18001BD57
0x18001bd4c  xor     eax, eax
0x18001bd4e  cmp     r9d, 2
0x18001bd52  cmovz   eax, edx
0x18001bd55  mov     edx, eax
0x18001bd57  or      r8d, edx
0x18001bd5a  mov     rax, rbx
0x18001bd5d  or      r8d, 1
0x18001bd61  mov     [rbx], r8d
0x18001bd64  add     rsp, 20h
0x18001bd68  pop     rbx
0x18001bd69  retn
```
