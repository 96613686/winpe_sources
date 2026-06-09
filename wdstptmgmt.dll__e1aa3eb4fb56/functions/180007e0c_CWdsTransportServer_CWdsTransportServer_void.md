# CWdsTransportServer::~CWdsTransportServer(void)

- ea: `0x180007e0c`
- end: `0x180007e43`
- name: `??1CWdsTransportServer@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(CWdsTransportServer *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007d58`
- `0x180007da4`
- `0x1800089a4`

## callees

- `0x180002bc4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007e19`
- `KERNEL32!DeleteCriticalSection` at `0x180007e19`
- `WdsCommonLib!??1CWinsockInitializer@@QEAA@XZ` at `0x180007e29`
- `WdsCommonLib!??1CWinsockInitializer@@QEAA@XZ` at `0x180007e29`

## pseudocode

```c
void __fastcall CWdsTransportServer::~CWdsTransportServer(CWdsTransportServer *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  CWinsockInitializer::~CWinsockInitializer((CWdsTransportServer *)((char *)this + 64));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CWdsTransportServer *)((char *)this + 16));
}

```

## disassembly

```asm
0x180007e0c  push    rbx
0x180007e0e  sub     rsp, 20h
0x180007e12  mov     rbx, rcx
0x180007e15  add     rcx, 48h ; 'H'; lpCriticalSection
0x180007e19  call    cs:__imp_DeleteCriticalSection
0x180007e20  nop     dword ptr [rax+rax+00h]
0x180007e25  lea     rcx, [rbx+40h]
0x180007e29  call    cs:__imp_??1CWinsockInitializer@@QEAA@XZ; CWinsockInitializer::~CWinsockInitializer(void)
0x180007e30  nop     dword ptr [rax+rax+00h]
0x180007e35  lea     rcx, [rbx+10h]; this
0x180007e39  add     rsp, 20h
0x180007e3d  pop     rbx
0x180007e3e  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
