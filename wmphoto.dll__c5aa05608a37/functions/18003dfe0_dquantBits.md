# dquantBits

- ea: `0x18003dfe0`
- end: `0x18003dffe`
- name: `dquantBits`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180031110`
- `0x180032914`
- `0x18003f294`
- `0x180042088`
- `0x180042294`

## callees

- `0x18003dfe0`

## pseudocode

```c
char __fastcall dquantBits(unsigned __int8 a1)
{
  char result; // al

  result = 2;
  if ( a1 < 2u )
    return 0;
  if ( a1 < 4u )
    return 1;
  if ( a1 >= 6u )
    return 4 - (a1 < 0xAu);
  return result;
}

```

## disassembly

```asm
0x18003dfe0  mov     al, 2
0x18003dfe2  cmp     cl, al
0x18003dfe4  jnb     short loc_18003DFE9
0x18003dfe6  xor     al, al
0x18003dfe8  retn
0x18003dfe9  cmp     cl, 4
0x18003dfec  jnb     short loc_18003DFF1
0x18003dfee  mov     al, 1
0x18003dff0  retn
0x18003dff1  cmp     cl, 6
0x18003dff4  jb      short locret_18003DFFD
0x18003dff6  cmp     cl, 0Ah
0x18003dff9  sbb     al, al
0x18003dffb  add     al, 4
0x18003dffd  retn
```
