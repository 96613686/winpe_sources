# _com_error::~_com_error(void)

- ea: `0x180041240`
- end: `0x18004127d`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180041290`
- `0x180056cb4`
- `0x180056d8d`
- `0x180056dee`
- `0x180056e82`
- `0x1800571af`

## callees

- `0x180041240`
- `0x180058010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180041271`
- `KERNEL32!LocalFree` at `0x180041271`

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
0x180041240  push    rbx
0x180041242  sub     rsp, 20h
0x180041246  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18004124d  mov     rbx, rcx
0x180041250  mov     [rcx], rax
0x180041253  mov     rcx, [rcx+10h]
0x180041257  test    rcx, rcx
0x18004125a  jz      short loc_180041268
0x18004125c  mov     rax, [rcx]
0x18004125f  mov     rax, [rax+10h]
0x180041263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041268  mov     rcx, [rbx+18h]; hMem
0x18004126c  test    rcx, rcx
0x18004126f  jz      short loc_180041277
0x180041271  call    cs:__imp_LocalFree
0x180041277  add     rsp, 20h
0x18004127b  pop     rbx
0x18004127c  retn
```
