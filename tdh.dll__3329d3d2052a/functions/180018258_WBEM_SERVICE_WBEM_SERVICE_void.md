# WBEM_SERVICE::~WBEM_SERVICE(void)

- ea: `0x180018258`
- end: `0x180018288`
- name: `??1WBEM_SERVICE@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(WBEM_SERVICE *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014ff4`
- `0x1800172a0`
- `0x18001cdcc`
- `0x1800245f4`
- `0x1800247d0`
- `0x18002b2c0`
- `0x18002b380`
- `0x18002b4e0`
- `0x18004a3d2`
- `0x18004a6aa`
- `0x18004aa0c`

## callees

- `0x180018258`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001827b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001827b`

## pseudocode

```c
void __fastcall WBEM_SERVICE::~WBEM_SERVICE(WBEM_SERVICE *this)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_BYTE *)this + 8) )
    CoUninitialize();
}

```

## disassembly

```asm
0x180018258  push    rbx
0x18001825a  sub     rsp, 20h
0x18001825e  mov     rbx, rcx
0x180018261  mov     rcx, [rcx]
0x180018264  test    rcx, rcx
0x180018267  jz      short loc_180018275
0x180018269  mov     rax, [rcx]
0x18001826c  mov     rax, [rax+10h]
0x180018270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018275  cmp     byte ptr [rbx+8], 0
0x180018279  jz      short loc_180018282
0x18001827b  call    cs:__imp_CoUninitialize
0x180018281  nop
0x180018282  add     rsp, 20h
0x180018286  pop     rbx
0x180018287  retn
```
