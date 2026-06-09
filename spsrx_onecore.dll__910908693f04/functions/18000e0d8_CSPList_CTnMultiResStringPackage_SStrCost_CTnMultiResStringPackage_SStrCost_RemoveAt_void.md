# CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::RemoveAt(void *)

- ea: `0x18000e0d8`
- end: `0x18000e112`
- name: `?RemoveAt@?$CSPList@PEAUSStrCost@CTnMultiResStringPackage@@PEAU12@@@QEAAXPEAX@Z`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009a44`
- `0x18000a614`
- `0x18000cf10`

## callees

- `0x18000e0d8`

## pseudocode

```c
_QWORD *__fastcall CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::RemoveAt(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // r8
  _QWORD *v3; // r8
  _QWORD *result; // rax

  v2 = *a2;
  if ( a2 == *(__int64 **)a1 )
    *(_QWORD *)a1 = v2;
  else
    *(_QWORD *)a2[1] = v2;
  v3 = (_QWORD *)a2[1];
  if ( a2 == *(__int64 **)(a1 + 8) )
    *(_QWORD *)(a1 + 8) = v3;
  else
    *(_QWORD *)(*a2 + 8) = v3;
  result = *(_QWORD **)(a1 + 24);
  *a2 = (__int64)result;
  --*(_DWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 24) = a2;
  return result;
}

```

## disassembly

```asm
0x18000e0d8  mov     r8, [rdx]
0x18000e0db  cmp     rdx, [rcx]
0x18000e0de  jnz     short loc_18000E0E5
0x18000e0e0  mov     [rcx], r8
0x18000e0e3  jmp     short loc_18000E0EC
0x18000e0e5  mov     rax, [rdx+8]
0x18000e0e9  mov     [rax], r8
0x18000e0ec  mov     r8, [rdx+8]
0x18000e0f0  cmp     rdx, [rcx+8]
0x18000e0f4  jnz     short loc_18000E0FC
0x18000e0f6  mov     [rcx+8], r8
0x18000e0fa  jmp     short loc_18000E103
0x18000e0fc  mov     rax, [rdx]
0x18000e0ff  mov     [rax+8], r8
0x18000e103  mov     rax, [rcx+18h]
0x18000e107  mov     [rdx], rax
0x18000e10a  dec     dword ptr [rcx+10h]
0x18000e10d  mov     [rcx+18h], rdx
0x18000e111  retn
```
