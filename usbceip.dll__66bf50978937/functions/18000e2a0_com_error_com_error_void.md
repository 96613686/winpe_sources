# _com_error::~_com_error(void)

- ea: `0x18000e2a0`
- end: `0x18000e2dd`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e2f0`

## callees

- `0x18000e2a0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e2d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e2d1`

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
0x18000e2a0  push    rbx
0x18000e2a2  sub     rsp, 20h
0x18000e2a6  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000e2ad  mov     rbx, rcx
0x18000e2b0  mov     [rcx], rax
0x18000e2b3  mov     rcx, [rcx+10h]
0x18000e2b7  test    rcx, rcx
0x18000e2ba  jz      short loc_18000E2C8
0x18000e2bc  mov     rax, [rcx]
0x18000e2bf  mov     rax, [rax+10h]
0x18000e2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2c8  mov     rcx, [rbx+18h]; hMem
0x18000e2cc  test    rcx, rcx
0x18000e2cf  jz      short loc_18000E2D7
0x18000e2d1  call    cs:__imp_LocalFree
0x18000e2d7  add     rsp, 20h
0x18000e2db  pop     rbx
0x18000e2dc  retn
```
