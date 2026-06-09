# WcSkipReparsePointInEnumeration

- ea: `0x14002b71c`
- end: `0x14002b775`
- name: `WcSkipReparsePointInEnumeration`
- size: `89`
- prototype: `char __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400154ac`
- `0x140030758`

## callees

- `0x14001414c`
- `0x140014198`
- `0x14002b71c`
- `0x14002b7d8`

## pseudocode

```c
char __fastcall WcSkipReparsePointInEnumeration(__int64 a1, int a2)
{
  int *EnumEntry; // rax
  __int64 v5; // r8
  int v7; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF
  int v9; // [rsp+58h] [rbp+20h] BYREF

  EnumEntry = WcGetEnumEntry(a1, *(_DWORD *)(a1 + 56), &v9, &v8, &v7);
  if ( !EnumEntry || !WcShouldSkipReparsePointInDirectoryEntry(*(_DWORD *)(a1 + 52), a2, v5, (__int64)EnumEntry) )
    return 0;
  WcAdvanceNextEnumEntry(a1);
  return 1;
}

```

## disassembly

```asm
0x14002b71c  mov     r11, rsp
0x14002b71f  mov     [r11+10h], rbx
0x14002b723  push    rdi
0x14002b724  sub     rsp, 30h
0x14002b728  mov     edi, edx
0x14002b72a  lea     rax, [r11+8]
0x14002b72e  mov     edx, [rcx+38h]
0x14002b731  lea     r9, [r11+18h]
0x14002b735  lea     r8, [r11+20h]
0x14002b739  mov     [r11-18h], rax
0x14002b73d  mov     rbx, rcx
0x14002b740  call    WcGetEnumEntry
0x14002b745  test    rax, rax
0x14002b748  jz      short loc_14002B75B
0x14002b74a  mov     ecx, [rbx+34h]
0x14002b74d  mov     r9, rax
0x14002b750  mov     edx, edi
0x14002b752  call    WcShouldSkipReparsePointInDirectoryEntry
0x14002b757  test    al, al
0x14002b759  jnz     short loc_14002B769
0x14002b75b  xor     al, al
0x14002b75d  mov     rbx, [rsp+38h+arg_8]
0x14002b762  add     rsp, 30h
0x14002b766  pop     rdi
0x14002b767  retn
0x14002b769  mov     rcx, rbx
0x14002b76c  call    WcAdvanceNextEnumEntry
0x14002b771  mov     al, 1
0x14002b773  jmp     short loc_14002B75D
```
