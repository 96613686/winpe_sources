# NfsResMgrpResourceTableCompare

- ea: `0x1400139a0`
- end: `0x1400139b5`
- name: `NfsResMgrpResourceTableCompare`
- size: `21`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400139a0`

## pseudocode

```c
__int64 __fastcall NfsResMgrpResourceTableCompare(
        struct _RTL_AVL_TABLE *Table,
        _DWORD *FirstStruct,
        _DWORD *SecondStruct)
{
  int v3; // ecx
  __int64 result; // rax
  int v5; // r8d

  v3 = SecondStruct[6];
  result = 0;
  v5 = FirstStruct[6];
  if ( v5 >= v3 )
  {
    LOBYTE(result) = v5 <= v3;
    return (unsigned int)(result + 1);
  }
  return result;
}

```

## disassembly

```asm
0x1400139a0  mov     ecx, [r8+18h]
0x1400139a4  xor     eax, eax
0x1400139a6  mov     r8d, [rdx+18h]
0x1400139aa  cmp     r8d, ecx
0x1400139ad  jl      short locret_1400139B4
0x1400139af  setle   al
0x1400139b2  inc     eax
0x1400139b4  retn
```
