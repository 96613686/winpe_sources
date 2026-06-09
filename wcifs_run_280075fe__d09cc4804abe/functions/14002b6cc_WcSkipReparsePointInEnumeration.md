# WcSkipReparsePointInEnumeration

- ea: `0x14002b6cc`
- end: `0x14002b725`
- name: `WcSkipReparsePointInEnumeration`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400154ac`
- `0x140030708`

## callees

- `0x14001414c`
- `0x140014198`
- `0x14002b6cc`
- `0x14002b788`

## pseudocode

```c
char __fastcall WcSkipReparsePointInEnumeration(__int64 a1, unsigned int a2)
{
  __int64 EnumEntry; // rax
  __int64 v5; // r8
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  EnumEntry = WcGetEnumEntry(a1, *(_DWORD *)(a1 + 56), (unsigned int)&v9, (unsigned int)&v8, (__int64)&v7);
  if ( !EnumEntry
    || !(unsigned __int8)WcShouldSkipReparsePointInDirectoryEntry(*(unsigned int *)(a1 + 52), a2, v5, EnumEntry) )
  {
    return 0;
  }
  WcAdvanceNextEnumEntry(a1);
  return 1;
}

```

## disassembly

```asm
0x14002b6cc  mov     r11, rsp
0x14002b6cf  mov     [r11+10h], rbx
0x14002b6d3  push    rdi
0x14002b6d4  sub     rsp, 30h
0x14002b6d8  mov     edi, edx
0x14002b6da  lea     rax, [r11+8]
0x14002b6de  mov     edx, [rcx+38h]
0x14002b6e1  lea     r9, [r11+18h]
0x14002b6e5  lea     r8, [r11+20h]
0x14002b6e9  mov     [r11-18h], rax
0x14002b6ed  mov     rbx, rcx
0x14002b6f0  call    WcGetEnumEntry
0x14002b6f5  test    rax, rax
0x14002b6f8  jz      short loc_14002B70B
0x14002b6fa  mov     ecx, [rbx+34h]
0x14002b6fd  mov     r9, rax
0x14002b700  mov     edx, edi
0x14002b702  call    WcShouldSkipReparsePointInDirectoryEntry
0x14002b707  test    al, al
0x14002b709  jnz     short loc_14002B719
0x14002b70b  xor     al, al
0x14002b70d  mov     rbx, [rsp+38h+arg_8]
0x14002b712  add     rsp, 30h
0x14002b716  pop     rdi
0x14002b717  retn
0x14002b719  mov     rcx, rbx
0x14002b71c  call    WcAdvanceNextEnumEntry
0x14002b721  mov     al, 1
0x14002b723  jmp     short loc_14002B70D
```
