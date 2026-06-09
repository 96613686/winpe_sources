# _com_error::`scalar deleting destructor'(uint)

- ea: `0x1800141a0`
- end: `0x1800141ff`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `95`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000213c`
- `0x1800141a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800141d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800141d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  __int64 v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    LocalFree(v5);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800141a0  mov     [rsp+arg_0], rbx
0x1800141a5  push    rdi
0x1800141a6  sub     rsp, 20h
0x1800141aa  mov     edi, edx
0x1800141ac  mov     rbx, rcx
0x1800141af  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800141b6  mov     [rcx], rax
0x1800141b9  mov     rcx, [rcx+10h]
0x1800141bd  test    rcx, rcx
0x1800141c0  jz      short loc_1800141CE
0x1800141c2  mov     rax, [rcx]
0x1800141c5  mov     rax, [rax+10h]
0x1800141c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141ce  mov     rcx, [rbx+18h]; hMem
0x1800141d2  test    rcx, rcx
0x1800141d5  jz      short loc_1800141DE
0x1800141d7  call    cs:__imp_LocalFree
0x1800141dd  nop
0x1800141de  test    dil, 1
0x1800141e2  jz      short loc_1800141F1
0x1800141e4  mov     edx, 20h ; ' '
0x1800141e9  mov     rcx, rbx; Block
0x1800141ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800141f1  mov     rax, rbx
0x1800141f4  mov     rbx, [rsp+28h+arg_0]
0x1800141f9  add     rsp, 20h
0x1800141fd  pop     rdi
0x1800141fe  retn
```
