# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bc88`
- end: `0x18001bcf6`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b278`

## callees

- `0x18001bc88`
- `0x180026d60`

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
0x18001bc88  push    rbx
0x18001bc8a  sub     rsp, 20h
0x18001bc8e  mov     ecx, 2AF34FDh; this
0x18001bc93  mov     rbx, rdx
0x18001bc96  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bc9b  mov     r9d, eax
0x18001bc9e  mov     qword ptr [rbx], 0
0x18001bca5  and     r9d, 0FFFFFF3Fh
0x18001bcac  mov     ecx, eax
0x18001bcae  and     eax, 80h
0x18001bcb3  mov     r8d, r9d
0x18001bcb6  and     r8d, 3
0x18001bcba  mov     edx, 40h ; '@'
0x18001bcbf  shl     r8d, 2
0x18001bcc3  and     ecx, edx
0x18001bcc5  or      r8d, ecx
0x18001bcc8  shl     r8d, 2
0x18001bccc  or      r8d, eax
0x18001bccf  shl     r8d, 3
0x18001bcd3  test    r9d, r9d
0x18001bcd6  jz      short loc_18001BCE3
0x18001bcd8  xor     eax, eax
0x18001bcda  cmp     r9d, 2
0x18001bcde  cmovz   eax, edx
0x18001bce1  mov     edx, eax
0x18001bce3  or      r8d, edx
0x18001bce6  mov     rax, rbx
0x18001bce9  or      r8d, 1
0x18001bced  mov     [rbx], r8d
0x18001bcf0  add     rsp, 20h
0x18001bcf4  pop     rbx
0x18001bcf5  retn
```
