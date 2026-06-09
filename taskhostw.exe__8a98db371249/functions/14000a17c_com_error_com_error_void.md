# _com_error::~_com_error(void)

- ea: `0x14000a17c`
- end: `0x14000a1b9`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a1c0`

## callees

- `0x14000a17c`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a1ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a1ad`

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
0x14000a17c  push    rbx
0x14000a17e  sub     rsp, 20h
0x14000a182  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14000a189  mov     rbx, rcx
0x14000a18c  mov     [rcx], rax
0x14000a18f  mov     rcx, [rcx+10h]
0x14000a193  test    rcx, rcx
0x14000a196  jz      short loc_14000A1A4
0x14000a198  mov     rax, [rcx]
0x14000a19b  mov     rax, [rax+10h]
0x14000a19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1a4  mov     rcx, [rbx+18h]; hMem
0x14000a1a8  test    rcx, rcx
0x14000a1ab  jz      short loc_14000A1B3
0x14000a1ad  call    cs:__imp_LocalFree
0x14000a1b3  add     rsp, 20h
0x14000a1b7  pop     rbx
0x14000a1b8  retn
```
