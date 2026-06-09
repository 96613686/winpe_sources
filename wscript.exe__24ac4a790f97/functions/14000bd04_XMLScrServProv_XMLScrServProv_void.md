# XMLScrServProv::~XMLScrServProv(void)

- ea: `0x14000bd04`
- end: `0x14000bd2c`
- name: `??1XMLScrServProv@@AEAA@XZ`
- size: `40`
- prototype: `void __fastcall(XMLScrServProv *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000c690`

## callees

- `0x14000bd04`
- `0x140018010`

## pseudocode

```c
void __fastcall XMLScrServProv::~XMLScrServProv(XMLScrServProv *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &XMLScrServProv::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14000bd04  sub     rsp, 28h
0x14000bd08  lea     rax, ??_7XMLScrServProv@@6B@; const XMLScrServProv::`vftable'
0x14000bd0f  mov     [rcx], rax
0x14000bd12  mov     rcx, [rcx+8]
0x14000bd16  test    rcx, rcx
0x14000bd19  jz      short loc_14000BD27
0x14000bd1b  mov     rax, [rcx]
0x14000bd1e  mov     rax, [rax+10h]
0x14000bd22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd27  add     rsp, 28h
0x14000bd2b  retn
```
