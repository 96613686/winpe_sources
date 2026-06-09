# ATL::CAcl::`vector deleting destructor'(uint)

- ea: `0x1400094b0`
- end: `0x1400094ef`
- name: `??_ECAcl@ATL@@UEAAPEAXI@Z`
- size: `63`
- prototype: `void **__fastcall(void **this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400094b0`

## import_xrefs

- `msvcrt!free` at `0x1400094cd`
- `msvcrt!free` at `0x1400094cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400094db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400094db`

## pseudocode

```c
void **__fastcall ATL::CAcl::`vector deleting destructor'(void **this, char a2)
{
  *this = &ATL::CAcl::`vftable';
  free(this[1]);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400094b0  mov     [rsp+arg_0], rbx
0x1400094b5  push    rdi
0x1400094b6  sub     rsp, 20h
0x1400094ba  lea     rax, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x1400094c1  mov     rdi, rcx
0x1400094c4  mov     [rcx], rax
0x1400094c7  mov     ebx, edx
0x1400094c9  mov     rcx, [rcx+8]; Block
0x1400094cd  call    cs:__imp_free
0x1400094d3  test    bl, 1
0x1400094d6  jz      short loc_1400094E1
0x1400094d8  mov     rcx, rdi
0x1400094db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400094e1  mov     rbx, [rsp+28h+arg_0]
0x1400094e6  mov     rax, rdi
0x1400094e9  add     rsp, 20h
0x1400094ed  pop     rdi
0x1400094ee  retn
```
