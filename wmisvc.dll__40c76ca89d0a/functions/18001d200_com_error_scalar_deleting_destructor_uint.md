# _com_error::`scalar deleting destructor'(uint)

- ea: `0x18001d200`
- end: `0x18001d230`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `48`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001d1b0`
- `0x18001d200`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001d21c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001d21c`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x18001d200  mov     [rsp+arg_0], rbx
0x18001d205  push    rdi
0x18001d206  sub     rsp, 20h
0x18001d20a  mov     ebx, edx
0x18001d20c  mov     rdi, rcx
0x18001d20f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x18001d214  test    bl, 1
0x18001d217  jz      short loc_18001D222
0x18001d219  mov     rcx, rdi
0x18001d21c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001d222  mov     rbx, [rsp+28h+arg_0]
0x18001d227  mov     rax, rdi
0x18001d22a  add     rsp, 20h
0x18001d22e  pop     rdi
0x18001d22f  retn
```
