# std::bad_alloc::`vector deleting destructor'(uint)

- ea: `0x180002090`
- end: `0x1800020ca`
- name: `??_Ebad_alloc@std@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(std::bad_alloc *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002090`
- `0x180002106`

## import_xrefs

- `msvcrt!free` at `0x1800020b6`
- `msvcrt!free` at `0x1800020b6`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::`vector deleting destructor'(std::bad_alloc *this, char a2)
{
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  exception::~exception(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x180002090  mov     [rsp+arg_0], rbx
0x180002095  push    rdi
0x180002096  sub     rsp, 20h
0x18000209a  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800020a1  mov     ebx, edx
0x1800020a3  mov     [rcx], rax
0x1800020a6  mov     rdi, rcx
0x1800020a9  call    ??1exception@@UEAA@XZ_0; exception::~exception(void)
0x1800020ae  test    bl, 1
0x1800020b1  jz      short loc_1800020BC
0x1800020b3  mov     rcx, rdi; Block
0x1800020b6  call    cs:__imp_free
0x1800020bc  mov     rax, rdi
0x1800020bf  mov     rbx, [rsp+28h+arg_0]
0x1800020c4  add     rsp, 20h
0x1800020c8  pop     rdi
0x1800020c9  retn
```
