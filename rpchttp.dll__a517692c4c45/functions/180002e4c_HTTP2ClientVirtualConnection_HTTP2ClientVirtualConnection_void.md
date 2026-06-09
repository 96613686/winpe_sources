# HTTP2ClientVirtualConnection::~HTTP2ClientVirtualConnection(void)

- ea: `0x180002e4c`
- end: `0x180002f20`
- name: `??1HTTP2ClientVirtualConnection@@UEAA@XZ`
- size: `212`
- prototype: `void __fastcall(HTTP2ClientVirtualConnection *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800033a0`
- `0x180007bb0`
- `0x18000c1a0`

## callees

- `0x180002e4c`
- `0x180003250`
- `0x18000a5dc`
- `0x18000aa98`
- `0x18000aac4`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180002efb`
- `ntdll!RtlDeleteCriticalSection` at `0x180002f08`
- `ntdll!RtlDeleteCriticalSection` at `0x180002efb`
- `ntdll!RtlDeleteCriticalSection` at `0x180002f08`

## pseudocode

```c
void __fastcall HTTP2ClientVirtualConnection::~HTTP2ClientVirtualConnection(HTTP2ClientVirtualConnection *this)
{
  HTTPResolverHint *v2; // rbx

  v2 = (HTTP2ClientVirtualConnection *)((char *)this + 448);
  *(_QWORD *)this = &HTTP2ClientVirtualConnection::`vftable';
  HTTPResolverHint::FreeHTTPProxy((HTTP2ClientVirtualConnection *)((char *)this + 448));
  HTTPResolverHint::FreeRpcProxy(v2);
  HTTPResolverHint::FreeRpcServer(v2);
  if ( *((_QWORD *)this + 53) )
  {
    (*((void (**)(void))pRuntimeImportTable + 62))();
    *((_QWORD *)this + 53) = 0;
  }
  if ( *((_QWORD *)this + 55) )
  {
    (*((void (**)(void))pRuntimeImportTable + 62))();
    *((_QWORD *)this + 55) = 0;
  }
  (*((void (__fastcall **)(HTTP2ClientVirtualConnection *, _QWORD))pRuntimeImportTable + 76))(
    this,
    *((_QWORD *)this + 77));
  *((_QWORD *)this + 77) = 0;
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)this + 7);
  HTTP2VirtualConnection::~HTTP2VirtualConnection(this);
}

```

## disassembly

```asm
0x180002e4c  mov     [rsp+arg_0], rbx
0x180002e51  push    rdi
0x180002e52  sub     rsp, 20h
0x180002e56  lea     rax, ??_7HTTP2ClientVirtualConnection@@6B@; const HTTP2ClientVirtualConnection::`vftable'
0x180002e5d  mov     rdi, rcx
0x180002e60  lea     rbx, [rcx+1C0h]
0x180002e67  mov     [rcx], rax
0x180002e6a  mov     rcx, rbx; this
0x180002e6d  call    ?FreeHTTPProxy@HTTPResolverHint@@QEAAXXZ; HTTPResolverHint::FreeHTTPProxy(void)
0x180002e72  mov     rcx, rbx; this
0x180002e75  call    ?FreeRpcProxy@HTTPResolverHint@@QEAAXXZ; HTTPResolverHint::FreeRpcProxy(void)
0x180002e7a  mov     rcx, rbx; this
0x180002e7d  call    ?FreeRpcServer@HTTPResolverHint@@QEAAXXZ; HTTPResolverHint::FreeRpcServer(void)
0x180002e82  mov     rcx, [rdi+1A8h]
0x180002e89  xor     ebx, ebx
0x180002e8b  test    rcx, rcx
0x180002e8e  jz      short loc_180002EAA
0x180002e90  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180002e97  mov     rax, [rax+1F0h]
0x180002e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea3  mov     [rdi+1A8h], rbx
0x180002eaa  mov     rcx, [rdi+1B8h]
0x180002eb1  test    rcx, rcx
0x180002eb4  jz      short loc_180002ED0
0x180002eb6  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180002ebd  mov     rax, [rax+1F0h]
0x180002ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec9  mov     [rdi+1B8h], rbx
0x180002ed0  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180002ed7  mov     rcx, rdi
0x180002eda  mov     rdx, [rdi+268h]
0x180002ee1  mov     rax, [rax+260h]
0x180002ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eed  lea     rcx, [rdi+148h]; CriticalSection
0x180002ef4  mov     [rdi+268h], rbx
0x180002efb  call    cs:__imp_RtlDeleteCriticalSection
0x180002f01  lea     rcx, [rdi+118h]; CriticalSection
0x180002f08  call    cs:__imp_RtlDeleteCriticalSection
0x180002f0e  mov     rcx, rdi; this
0x180002f11  mov     rbx, [rsp+28h+arg_0]
0x180002f16  add     rsp, 20h
0x180002f1a  pop     rdi
0x180002f1b  jmp     ??1HTTP2VirtualConnection@@UEAA@XZ; HTTP2VirtualConnection::~HTTP2VirtualConnection(void)
```
