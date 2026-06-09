# CompareRoutine

- ea: `0x140006ab0`
- end: `0x140006ac5`
- name: `CompareRoutine`
- size: `21`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006ab0`

## pseudocode

```c
__int64 __fastcall CompareRoutine(struct _RTL_AVL_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  unsigned __int64 v3; // rcx
  __int64 result; // rax
  unsigned __int64 v5; // r8

  v3 = SecondStruct[1];
  result = 0;
  v5 = FirstStruct[1];
  if ( v5 >= v3 )
  {
    LOBYTE(result) = v5 == v3;
    return (unsigned int)(result + 1);
  }
  return result;
}

```

## disassembly

```asm
0x140006ab0  mov     rcx, [r8+8]
0x140006ab4  xor     eax, eax
0x140006ab6  mov     r8, [rdx+8]
0x140006aba  cmp     r8, rcx
0x140006abd  jb      short locret_140006AC4
0x140006abf  setz    al
0x140006ac2  inc     eax
0x140006ac4  retn
```
