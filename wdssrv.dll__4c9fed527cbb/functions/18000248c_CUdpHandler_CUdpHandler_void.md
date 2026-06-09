# CUdpHandler::~CUdpHandler(void)

- ea: `0x18000248c`
- end: `0x1800024e0`
- name: `??1CUdpHandler@@UEAA@XZ`
- size: `84`
- prototype: `void __fastcall(CUdpHandler *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002530`
- `0x1800135e8`

## callees

- `0x1800033c0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800024b3`
- `KERNEL32!DeleteCriticalSection` at `0x1800024c3`
- `KERNEL32!DeleteCriticalSection` at `0x1800024b3`
- `KERNEL32!DeleteCriticalSection` at `0x1800024c3`

## pseudocode

```c
void __fastcall CUdpHandler::~CUdpHandler(CUdpHandler *this)
{
  *(_QWORD *)this = &CUdpHandler::`vftable'{for `IEndpointHandler'};
  *((_QWORD *)this + 2) = &CUdpHandler::`vftable'{for `IInterfaceMonitorChange'};
  CUdpHandler::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  *(_QWORD *)this = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x18000248c  push    rbx
0x18000248e  sub     rsp, 20h
0x180002492  lea     rax, ??_7CUdpHandler@@6BIEndpointHandler@@@; const CUdpHandler::`vftable'{for `IEndpointHandler'}
0x180002499  mov     rbx, rcx
0x18000249c  mov     [rcx], rax
0x18000249f  lea     rax, ??_7CUdpHandler@@6BIInterfaceMonitorChange@@@; const CUdpHandler::`vftable'{for `IInterfaceMonitorChange'}
0x1800024a6  mov     [rcx+10h], rax
0x1800024aa  call    ?Shutdown@CUdpHandler@@UEAAKXZ; CUdpHandler::Shutdown(void)
0x1800024af  lea     rcx, [rbx+68h]; lpCriticalSection
0x1800024b3  call    cs:__imp_DeleteCriticalSection
0x1800024ba  nop     dword ptr [rax+rax+00h]
0x1800024bf  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800024c3  call    cs:__imp_DeleteCriticalSection
0x1800024ca  nop     dword ptr [rax+rax+00h]
0x1800024cf  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x1800024d6  mov     [rbx], rax
0x1800024d9  add     rsp, 20h
0x1800024dd  pop     rbx
0x1800024de  retn
```
