# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180015fc0`
- end: `0x18001601a`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `90`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180015fc0`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016006`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016006`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ff7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ff7`

## pseudocode

```c
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
0x180015fc0  mov     [rsp+arg_0], rbx
0x180015fc5  push    rdi
0x180015fc6  sub     rsp, 20h
0x180015fca  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180015fd1  mov     rbx, rcx
0x180015fd4  mov     [rcx], rax
0x180015fd7  mov     edi, edx
0x180015fd9  mov     rcx, [rcx+10h]
0x180015fdd  test    rcx, rcx
0x180015fe0  jz      short loc_180015FEE
0x180015fe2  mov     rax, [rcx]
0x180015fe5  mov     rax, [rax+10h]
0x180015fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fee  mov     rcx, [rbx+18h]; hMem
0x180015ff2  test    rcx, rcx
0x180015ff5  jz      short loc_180015FFD
0x180015ff7  call    cs:__imp_LocalFree
0x180015ffd  test    dil, 1
0x180016001  jz      short loc_18001600C
0x180016003  mov     rcx, rbx
0x180016006  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001600c  mov     rax, rbx
0x18001600f  mov     rbx, [rsp+28h+arg_0]
0x180016014  add     rsp, 20h
0x180016018  pop     rdi
0x180016019  retn
```
