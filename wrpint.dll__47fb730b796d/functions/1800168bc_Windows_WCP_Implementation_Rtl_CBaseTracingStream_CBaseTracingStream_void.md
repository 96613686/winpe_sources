# Windows::WCP::Implementation::Rtl::CBaseTracingStream::~CBaseTracingStream(void)

- ea: `0x1800168bc`
- end: `0x18001691e`
- name: `??1CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAA@XZ`
- size: `98`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016930`

## callees

- `0x1800168bc`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800168fe`
- `ntdll!RtlDeleteCriticalSection` at `0x1800168fe`
- `ntdll!RtlRaiseStatus` at `0x18001690a`
- `ntdll!RtlRaiseStatus` at `0x18001690a`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::~CBaseTracingStream(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this)
{
  bool v1; // zf
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  int v4; // eax

  v1 = *((_BYTE *)this + 16) == 0;
  *(_QWORD *)this = &Windows::WCP::Implementation::Rtl::CBaseTracingStream::`vftable';
  if ( !v1 )
  {
    v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
    if ( v3 )
      (**v3)(v3, 1);
  }
  if ( *((_BYTE *)this + 2184) )
  {
    v4 = RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 2144));
    if ( v4 < 0 )
      RtlRaiseStatus(v4);
    *((_BYTE *)this + 2184) = 0;
  }
}

```

## disassembly

```asm
0x1800168bc  push    rbx
0x1800168be  sub     rsp, 20h
0x1800168c2  cmp     byte ptr [rcx+10h], 0
0x1800168c6  lea     rax, ??_7CBaseTracingStream@Rtl@Implementation@WCP@Windows@@6B@; const Windows::WCP::Implementation::Rtl::CBaseTracingStream::`vftable'
0x1800168cd  mov     [rcx], rax
0x1800168d0  mov     rbx, rcx
0x1800168d3  jz      short loc_1800168EE
0x1800168d5  mov     rcx, [rcx+8]
0x1800168d9  test    rcx, rcx
0x1800168dc  jz      short loc_1800168EE
0x1800168de  mov     rax, [rcx]
0x1800168e1  mov     edx, 1
0x1800168e6  mov     rax, [rax]
0x1800168e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168ee  cmp     byte ptr [rbx+888h], 0
0x1800168f5  jz      short loc_180016918
0x1800168f7  lea     rcx, [rbx+860h]; CriticalSection
0x1800168fe  call    cs:__imp_RtlDeleteCriticalSection
0x180016904  test    eax, eax
0x180016906  jns     short loc_180016911
0x180016908  mov     ecx, eax; Status
0x18001690a  call    cs:__imp_RtlRaiseStatus
0x180016910  int     3; Trap to Debugger
0x180016911  mov     byte ptr [rbx+888h], 0
0x180016918  add     rsp, 20h
0x18001691c  pop     rbx
0x18001691d  retn
```
