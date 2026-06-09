# CMulticastSession::`scalar deleting destructor'(uint)

- ea: `0x18001a83c`
- end: `0x18001a8c7`
- name: `??_GCMulticastSession@@QEAAPEAXI@Z`
- size: `139`
- prototype: `void *__fastcall(CMulticastSession *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180004ff8`
- `0x1800197e0`

## callees

- `0x180008738`
- `0x18000c404`
- `0x18000c6c0`
- `0x18000cde0`
- `0x1800147e4`
- `0x180017254`
- `0x18001a9a8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001a8ab`
- `KERNEL32!DeleteCriticalSection` at `0x18001a8ab`

## pseudocode

```c
CMulticastSession *__fastcall CMulticastSession::`scalar deleting destructor'(CMulticastSession *this)
{
  *(_QWORD *)this = &CMulticastSession::`vftable';
  CMulticastSession::Shutdown(this);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)this + 16144);
  CApSrvDataState::~CApSrvDataState((CMulticastSession *)((char *)this + 14768));
  *((_QWORD *)this + 1825) = &CApSrvCIRState::`vftable';
  CApSrvCIRState::Shutdown((CMulticastSession *)((char *)this + 14600));
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)this + 14680);
  CApSrvCRR::Shutdown((CMulticastSession *)((char *)this + 14640));
  CTransportServer::~CTransportServer((CMulticastSession *)((char *)this + 312));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001a83c  mov     [rsp+arg_0], rbx
0x18001a841  push    rdi
0x18001a842  sub     rsp, 20h
0x18001a846  lea     rax, ??_7CMulticastSession@@6B@; const CMulticastSession::`vftable'
0x18001a84d  mov     rdi, rcx
0x18001a850  mov     [rcx], rax
0x18001a853  call    ?Shutdown@CMulticastSession@@QEAAKXZ; CMulticastSession::Shutdown(void)
0x18001a858  lea     rcx, [rdi+3F10h]
0x18001a85f  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x18001a864  lea     rcx, [rdi+39B0h]; this
0x18001a86b  call    ??1CApSrvDataState@@QEAA@XZ; CApSrvDataState::~CApSrvDataState(void)
0x18001a870  lea     rbx, [rdi+3908h]
0x18001a877  lea     rax, ??_7CApSrvCIRState@@6B@; const CApSrvCIRState::`vftable'
0x18001a87e  mov     rcx, rbx; this
0x18001a881  mov     [rbx], rax
0x18001a884  call    ?Shutdown@CApSrvCIRState@@QEAAKXZ; CApSrvCIRState::Shutdown(void)
0x18001a889  lea     rcx, [rbx+50h]
0x18001a88d  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x18001a892  lea     rcx, [rbx+28h]; this
0x18001a896  call    ?Shutdown@CApSrvCRR@@QEAAKXZ; CApSrvCRR::Shutdown(void)
0x18001a89b  lea     rcx, [rdi+138h]; this
0x18001a8a2  call    ??1CTransportServer@@QEAA@XZ; CTransportServer::~CTransportServer(void)
0x18001a8a7  lea     rcx, [rdi+8]; lpCriticalSection
0x18001a8ab  call    cs:__imp_DeleteCriticalSection
0x18001a8b1  mov     rcx, rdi; void *
0x18001a8b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a8b9  mov     rbx, [rsp+28h+arg_0]
0x18001a8be  mov     rax, rdi
0x18001a8c1  add     rsp, 20h
0x18001a8c5  pop     rdi
0x18001a8c6  retn
```
