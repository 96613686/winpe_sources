# CObjectPathParser::ident_becomes_ns(void)

- ea: `0x180014ce8`
- end: `0x180014d20`
- name: `?ident_becomes_ns@CObjectPathParser@@AEAAHXZ`
- size: `56`
- prototype: `__int64 __fastcall(ParsedObjectPath **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800150f0`

## callees

- `0x180014660`
- `0x180014ce8`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014d0b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014d0b`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::ident_becomes_ns(ParsedObjectPath **this)
{
  __int64 result; // rax

  if ( !(unsigned int)ParsedObjectPath::AddNamespace(this[3], (const unsigned __int16 *)*this) )
    return 3;
  CWin32DefaultArena::WbemMemFree(*this);
  result = 0;
  *this = 0;
  return result;
}

```

## disassembly

```asm
0x180014ce8  push    rbx
0x180014cea  sub     rsp, 20h
0x180014cee  mov     rdx, [rcx]; unsigned __int16 *
0x180014cf1  mov     rbx, rcx
0x180014cf4  mov     rcx, [rcx+18h]; this
0x180014cf8  call    ?AddNamespace@ParsedObjectPath@@QEAAHPEBG@Z; ParsedObjectPath::AddNamespace(ushort const *)
0x180014cfd  test    eax, eax
0x180014cff  jnz     short loc_180014D08
0x180014d01  mov     eax, 3
0x180014d06  jmp     short loc_180014D1A
0x180014d08  mov     rcx, [rbx]
0x180014d0b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014d11  xor     eax, eax
0x180014d13  mov     qword ptr [rbx], 0
0x180014d1a  add     rsp, 20h
0x180014d1e  pop     rbx
0x180014d1f  retn
```
