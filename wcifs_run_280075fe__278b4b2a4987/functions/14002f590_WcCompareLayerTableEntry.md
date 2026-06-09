# WcCompareLayerTableEntry

- ea: `0x14002f590`
- end: `0x14002f5c7`
- name: `WcCompareLayerTableEntry`
- size: `55`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400085e0`
- `0x14002f590`

## pseudocode

```c
__int64 __fastcall WcCompareLayerTableEntry(
        struct _RTL_AVL_TABLE *Table,
        const void **FirstStruct,
        const void **SecondStruct)
{
  int v3; // edx
  __int64 result; // rax

  v3 = memcmp(*FirstStruct, *SecondStruct, 0x10u);
  if ( v3 > 0 )
    return 1;
  result = 2;
  if ( v3 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14002f590  sub     rsp, 28h
0x14002f594  mov     rcx, [rdx]; Buf1
0x14002f597  mov     rax, r8
0x14002f59a  mov     r8d, 10h; Size
0x14002f5a0  mov     rdx, [rax]; Buf2
0x14002f5a3  call    memcmp
0x14002f5a8  mov     edx, eax
0x14002f5aa  test    eax, eax
0x14002f5ac  jle     short loc_14002F5B9
0x14002f5ae  mov     eax, 1
0x14002f5b3  add     rsp, 28h
0x14002f5b7  retn
0x14002f5b9  xor     ecx, ecx
0x14002f5bb  mov     eax, 2
0x14002f5c0  test    edx, edx
0x14002f5c2  cmovs   eax, ecx
0x14002f5c5  jmp     short loc_14002F5B3
```
