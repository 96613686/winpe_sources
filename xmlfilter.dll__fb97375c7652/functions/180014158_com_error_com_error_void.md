# _com_error::~_com_error(void)

- ea: `0x180014158`
- end: `0x180014196`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014158`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014189`

## pseudocode

```c
void __fastcall _com_error::~_com_error(_com_error *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x180014158  push    rbx
0x18001415a  sub     rsp, 20h
0x18001415e  mov     rbx, rcx
0x180014161  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180014168  mov     [rcx], rax
0x18001416b  mov     rcx, [rcx+10h]
0x18001416f  test    rcx, rcx
0x180014172  jz      short loc_180014180
0x180014174  mov     rax, [rcx]
0x180014177  mov     rax, [rax+10h]
0x18001417b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014180  mov     rcx, [rbx+18h]; hMem
0x180014184  test    rcx, rcx
0x180014187  jz      short loc_180014190
0x180014189  call    cs:__imp_LocalFree
0x18001418f  nop
0x180014190  add     rsp, 20h
0x180014194  pop     rbx
0x180014195  retn
```
