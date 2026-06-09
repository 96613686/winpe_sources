# W3_STATIC_FILE_HANDLER::~W3_STATIC_FILE_HANDLER(void)

- ea: `0x180001c88`
- end: `0x180001cdb`
- name: `??1W3_STATIC_FILE_HANDLER@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(W3_STATIC_FILE_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001d90`

## callees

- `0x180001c88`
- `0x180007010`

## pseudocode

```c
void __fastcall W3_STATIC_FILE_HANDLER::~W3_STATIC_FILE_HANDLER(W3_STATIC_FILE_HANDLER *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &W3_STATIC_FILE_HANDLER::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180001c88  push    rbx
0x180001c8a  sub     rsp, 20h
0x180001c8e  lea     rax, ??_7W3_STATIC_FILE_HANDLER@@6B@; const W3_STATIC_FILE_HANDLER::`vftable'
0x180001c95  mov     rbx, rcx
0x180001c98  mov     [rcx], rax
0x180001c9b  mov     rcx, [rcx+10h]
0x180001c9f  test    rcx, rcx
0x180001ca2  jz      short loc_180001CB8
0x180001ca4  mov     rax, [rcx]
0x180001ca7  mov     rax, [rax+10h]
0x180001cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cb0  mov     qword ptr [rbx+10h], 0
0x180001cb8  mov     rcx, [rbx+8]
0x180001cbc  test    rcx, rcx
0x180001cbf  jz      short loc_180001CD5
0x180001cc1  mov     rax, [rcx]
0x180001cc4  mov     rax, [rax+10h]
0x180001cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ccd  mov     qword ptr [rbx+8], 0
0x180001cd5  add     rsp, 20h
0x180001cd9  pop     rbx
0x180001cda  retn
```
