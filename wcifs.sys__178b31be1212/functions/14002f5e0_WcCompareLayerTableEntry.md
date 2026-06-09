# WcCompareLayerTableEntry

- ea: `0x14002f5e0`
- end: `0x14002f617`
- name: `WcCompareLayerTableEntry`
- size: `55`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, const void **FirstStruct, const void **SecondStruct)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400085e0`
- `0x14002f5e0`

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
0x14002f5e0  sub     rsp, 28h
0x14002f5e4  mov     rcx, [rdx]; Buf1
0x14002f5e7  mov     rax, r8
0x14002f5ea  mov     r8d, 10h; Size
0x14002f5f0  mov     rdx, [rax]; Buf2
0x14002f5f3  call    memcmp
0x14002f5f8  mov     edx, eax
0x14002f5fa  test    eax, eax
0x14002f5fc  jle     short loc_14002F609
0x14002f5fe  mov     eax, 1
0x14002f603  add     rsp, 28h
0x14002f607  retn
0x14002f609  xor     ecx, ecx
0x14002f60b  mov     eax, 2
0x14002f610  test    edx, edx
0x14002f612  cmovs   eax, ecx
0x14002f615  jmp     short loc_14002F603
```
