# _com_error::`scalar deleting destructor'(uint)

- ea: `0x14000a1c0`
- end: `0x14000a1f0`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `48`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000a17c`
- `0x14000a1c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000a1dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a1dc`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000a1c0  mov     [rsp+arg_0], rbx
0x14000a1c5  push    rdi
0x14000a1c6  sub     rsp, 20h
0x14000a1ca  mov     ebx, edx
0x14000a1cc  mov     rdi, rcx
0x14000a1cf  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x14000a1d4  test    bl, 1
0x14000a1d7  jz      short loc_14000A1E2
0x14000a1d9  mov     rcx, rdi
0x14000a1dc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000a1e2  mov     rbx, [rsp+28h+arg_0]
0x14000a1e7  mov     rax, rdi
0x14000a1ea  add     rsp, 20h
0x14000a1ee  pop     rdi
0x14000a1ef  retn
```
