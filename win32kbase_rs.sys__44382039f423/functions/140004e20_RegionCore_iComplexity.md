# RegionCore_iComplexity

- ea: `0x140004e20`
- end: `0x140004e39`
- name: `RegionCore_iComplexity`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004e20`

## pseudocode

```c
__int64 __fastcall RegionCore_iComplexity(__int64 a1)
{
  __int64 result; // rax

  result = 1;
  if ( *(_DWORD *)(a1 + 24) != 1 )
    return 3 - (unsigned int)(*(_QWORD *)(a1 + 16) < 0xFu);
  return result;
}

```

## disassembly

```asm
0x140004e20  mov     eax, 1
0x140004e25  cmp     dword ptr [rcx+18h], 1
0x140004e29  jz      short locret_140004E38
0x140004e2b  cmp     qword ptr [rcx+10h], 0Fh
0x140004e30  mov     eax, 3
0x140004e35  sbb     eax, 0
0x140004e38  retn
```
