# CSusLock::`vector deleting destructor'(uint)

- ea: `0x180016970`
- end: `0x1800169b3`
- name: `??_ECSusLock@@UEAAPEAXI@Z`
- size: `67`
- prototype: `void *__fastcall(CSusLock *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180016970`
- `0x180042a24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001698d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001698d`

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
0x180016970  mov     [rsp+arg_0], rbx
0x180016975  push    rdi
0x180016976  sub     rsp, 20h
0x18001697a  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x180016981  mov     rdi, rcx
0x180016984  mov     [rcx], rax
0x180016987  mov     ebx, edx
0x180016989  add     rcx, 8; lpCriticalSection
0x18001698d  call    cs:__imp_DeleteCriticalSection
0x180016993  test    bl, 1
0x180016996  jz      short loc_1800169A5
0x180016998  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18001699d  mov     rcx, rdi; void *
0x1800169a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800169a5  mov     rbx, [rsp+28h+arg_0]
0x1800169aa  mov     rax, rdi
0x1800169ad  add     rsp, 20h
0x1800169b1  pop     rdi
0x1800169b2  retn
```
