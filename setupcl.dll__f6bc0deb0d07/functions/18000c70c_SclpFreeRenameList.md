# SclpFreeRenameList

- ea: `0x18000c70c`
- end: `0x18000c733`
- name: `SclpFreeRenameList`
- size: `39`
- prototype: `BOOLEAN __fastcall(_QWORD **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000acec`
- `0x18000b21c`
- `0x18000b530`

## callees

- `0x18000c68c`
- `0x18000c70c`

## pseudocode

```c
BOOLEAN __fastcall SclpFreeRenameList(_QWORD **a1)
{
  _QWORD *i; // rcx
  BOOLEAN result; // al

  for ( i = *a1; i; i = *a1 )
  {
    *a1 = (_QWORD *)*i;
    result = SclpFreeRenameItem(i);
  }
  return result;
}

```

## disassembly

```asm
0x18000c70c  push    rbx
0x18000c70e  sub     rsp, 20h
0x18000c712  mov     rbx, rcx
0x18000c715  mov     rcx, [rcx]
0x18000c718  jmp     short loc_18000C728
0x18000c71a  mov     rax, [rcx]
0x18000c71d  mov     [rbx], rax
0x18000c720  call    SclpFreeRenameItem
0x18000c725  mov     rcx, [rbx]; P
0x18000c728  test    rcx, rcx
0x18000c72b  jnz     short loc_18000C71A
0x18000c72d  add     rsp, 20h
0x18000c731  pop     rbx
0x18000c732  retn
```
