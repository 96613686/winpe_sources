# LogAdapter::WdsLoader::~WdsLoader(void)

- ea: `0x180002794`
- end: `0x1800027fa`
- name: `??1WdsLoader@LogAdapter@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(LogAdapter::WdsLoader *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002694`

## callees

- `0x180002794`
- `0x180013350`
- `0x18001c010`

## import_xrefs

- `ntdll!LdrUnloadDll` at `0x1800027b5`
- `ntdll!LdrUnloadDll` at `0x1800027b5`

## pseudocode

```c
void __fastcall LogAdapter::WdsLoader::~WdsLoader(LogAdapter::WdsLoader *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  if ( *(_BYTE *)this )
    WdsUnload();
  v2 = (void *)_InterlockedExchange64(&qword_18002BB48, 0);
  if ( v2 && LdrUnloadDll(v2) < 0 )
    __fastfail(7u);
  _InterlockedExchange64(&qword_18002BB40, 0);
  v3 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
  if ( v3 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 504LL))(v3, 1);
  *(_BYTE *)this = 0;
}

```

## disassembly

```asm
0x180002794  push    rbx
0x180002796  sub     rsp, 20h
0x18000279a  cmp     byte ptr [rcx], 0
0x18000279d  mov     rbx, rcx
0x1800027a0  jz      short loc_1800027A7
0x1800027a2  call    ?WdsUnload@@YAXXZ; WdsUnload(void)
0x1800027a7  xor     ecx, ecx
0x1800027a9  xchg    rcx, cs:qword_18002BB48; BaseAddress
0x1800027b0  test    rcx, rcx
0x1800027b3  jz      short loc_1800027C6
0x1800027b5  call    cs:__imp_LdrUnloadDll
0x1800027bb  test    eax, eax
0x1800027bd  jns     short loc_1800027C6
0x1800027bf  mov     ecx, 7
0x1800027c4  int     29h; Win8: RtlFailFast(ecx)
0x1800027c6  xor     eax, eax
0x1800027c8  xor     ecx, ecx
0x1800027ca  xchg    rax, cs:qword_18002BB40
0x1800027d1  xchg    rcx, cs:?g_TracingStream@Rtl@Implementation@WCP@Windows@@3PEAVCBaseTracingStream@1234@EA; Windows::WCP::Implementation::Rtl::CBaseTracingStream * Windows::WCP::Implementation::Rtl::g_TracingStream
0x1800027d8  test    rcx, rcx
0x1800027db  jz      short loc_1800027F1
0x1800027dd  mov     rax, [rcx]
0x1800027e0  mov     edx, 1
0x1800027e5  mov     rax, [rax+1F8h]
0x1800027ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f1  mov     byte ptr [rbx], 0
0x1800027f4  add     rsp, 20h
0x1800027f8  pop     rbx
0x1800027f9  retn
```
