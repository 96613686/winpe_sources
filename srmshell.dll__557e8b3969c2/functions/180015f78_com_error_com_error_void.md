# _com_error::~_com_error(void)

- ea: `0x180015f78`
- end: `0x180015fb5`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015f78`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015fa9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015fa9`

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
0x180015f78  push    rbx
0x180015f7a  sub     rsp, 20h
0x180015f7e  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180015f85  mov     rbx, rcx
0x180015f88  mov     [rcx], rax
0x180015f8b  mov     rcx, [rcx+10h]
0x180015f8f  test    rcx, rcx
0x180015f92  jz      short loc_180015FA0
0x180015f94  mov     rax, [rcx]
0x180015f97  mov     rax, [rax+10h]
0x180015f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fa0  mov     rcx, [rbx+18h]; hMem
0x180015fa4  test    rcx, rcx
0x180015fa7  jz      short loc_180015FAF
0x180015fa9  call    cs:__imp_LocalFree
0x180015faf  add     rsp, 20h
0x180015fb3  pop     rbx
0x180015fb4  retn
```
