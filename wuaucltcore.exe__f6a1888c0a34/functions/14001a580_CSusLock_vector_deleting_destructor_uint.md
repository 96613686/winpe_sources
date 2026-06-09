# CSusLock::`vector deleting destructor'(uint)

- ea: `0x14001a580`
- end: `0x14001a5c3`
- name: `??_ECSusLock@@UEAAPEAXI@Z`
- size: `67`
- prototype: `void *__fastcall(CSusLock *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x14001a580`
- `0x14001acf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001a59d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001a59d`

## pseudocode

```c
CSusLock *__fastcall CSusLock::`vector deleting destructor'(CSusLock *this, char a2)
{
  *(_QWORD *)this = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x30);
  return this;
}

```

## disassembly

```asm
0x14001a580  mov     [rsp+arg_0], rbx
0x14001a585  push    rdi
0x14001a586  sub     rsp, 20h
0x14001a58a  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x14001a591  mov     rdi, rcx
0x14001a594  mov     [rcx], rax
0x14001a597  mov     ebx, edx
0x14001a599  add     rcx, 8; lpCriticalSection
0x14001a59d  call    cs:__imp_DeleteCriticalSection
0x14001a5a3  test    bl, 1
0x14001a5a6  jz      short loc_14001A5B5
0x14001a5a8  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x14001a5ad  mov     rcx, rdi; void *
0x14001a5b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a5b5  mov     rbx, [rsp+28h+arg_0]
0x14001a5ba  mov     rax, rdi
0x14001a5bd  add     rsp, 20h
0x14001a5c1  pop     rdi
0x14001a5c2  retn
```
