# CTransportServer::~CTransportServer(void)

- ea: `0x1800147e4`
- end: `0x1800148ab`
- name: `??1CTransportServer@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(CTransportServer *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001a83c`

## callees

- `0x180008738`
- `0x18000e2a0`
- `0x18000f5cc`
- `0x18001198c`
- `0x1800150c0`
- `0x180016454`
- `0x180016800`
- `0x18001ca50`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180014864`
- `KERNEL32!DeleteCriticalSection` at `0x180014864`
- `KERNEL32!DeleteCriticalSection` at `0x1800148a4`

## pseudocode

```c
void __fastcall CTransportServer::~CTransportServer(CTransportServer *this)
{
  CTransportServer::Shutdown((LPCRITICAL_SECTION)this);
  CMcTpConstructor::~CMcTpConstructor((CTransportServer *)((char *)this + 14136));
  CTpSrvDataState::~CTpSrvDataState((CTransportServer *)((char *)this + 13448));
  *((_QWORD *)this + 1659) = &CTpSrvQCCState::`vftable';
  CTpSrvQCR::Reset((CTransportServer *)((char *)this + 13320), 0);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)this + 13392);
  CTpSrvQCR::Reset((CTransportServer *)((char *)this + 13320), 0);
  *((_QWORD *)this + 1658) = &CTpSrvPreStartState::`vftable';
  CTpSrvSharedAddress::Shutdown((CTransportServer *)((char *)this + 13184));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 13216));
  CTpSrvKickDemote::~CTpSrvKickDemote((CTransportServer *)((char *)this + 5320));
  CTpSrvClients::Shutdown((CTransportServer *)((char *)this + 2440));
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)this + 2520);
  CTimer<CMulticastServer>::~CTimer<CMulticastServer>((__int64)this + 2456);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800147e4  mov     [rsp+arg_0], rbx
0x1800147e9  push    rdi
0x1800147ea  sub     rsp, 20h
0x1800147ee  mov     rdi, rcx
0x1800147f1  call    ?Shutdown@CTransportServer@@QEAAKXZ; CTransportServer::Shutdown(void)
0x1800147f6  lea     rcx, [rdi+3738h]; this
0x1800147fd  call    ??1CMcTpConstructor@@QEAA@XZ; CMcTpConstructor::~CMcTpConstructor(void)
0x180014802  lea     rcx, [rdi+3488h]; this
0x180014809  call    ??1CTpSrvDataState@@QEAA@XZ; CTpSrvDataState::~CTpSrvDataState(void)
0x18001480e  lea     rax, ??_7CTpSrvQCCState@@6B@; const CTpSrvQCCState::`vftable'
0x180014815  xor     edx, edx; unsigned __int64
0x180014817  lea     rbx, [rdi+3408h]
0x18001481e  mov     [rdi+33D8h], rax
0x180014825  mov     rcx, rbx; this
0x180014828  call    ?Reset@CTpSrvQCR@@QEAAX_K@Z; CTpSrvQCR::Reset(unsigned __int64)
0x18001482d  lea     rcx, [rdi+3450h]
0x180014834  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x180014839  xor     edx, edx; unsigned __int64
0x18001483b  mov     rcx, rbx; this
0x18001483e  call    ?Reset@CTpSrvQCR@@QEAAX_K@Z; CTpSrvQCR::Reset(unsigned __int64)
0x180014843  lea     rax, ??_7CTpSrvPreStartState@@6B@; const CTpSrvPreStartState::`vftable'
0x18001484a  lea     rbx, [rdi+3380h]
0x180014851  mov     [rdi+33D0h], rax
0x180014858  mov     rcx, rbx; this
0x18001485b  call    ?Shutdown@CTpSrvSharedAddress@@QEAAKXZ; CTpSrvSharedAddress::Shutdown(void)
0x180014860  lea     rcx, [rbx+20h]; lpCriticalSection
0x180014864  call    cs:__imp_DeleteCriticalSection
0x18001486a  lea     rcx, [rdi+14C8h]; this
0x180014871  call    ??1CTpSrvKickDemote@@QEAA@XZ; CTpSrvKickDemote::~CTpSrvKickDemote(void)
0x180014876  lea     rbx, [rdi+988h]
0x18001487d  mov     rcx, rbx; this
0x180014880  call    ?Shutdown@CTpSrvClients@@QEAAKXZ; CTpSrvClients::Shutdown(void)
0x180014885  lea     rcx, [rbx+50h]
0x180014889  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x18001488e  lea     rcx, [rbx+10h]
0x180014892  call    ??1?$CTimer@VCMulticastServer@@@@QEAA@XZ; CTimer<CMulticastServer>::~CTimer<CMulticastServer>(void)
0x180014897  mov     rcx, rdi
0x18001489a  mov     rbx, [rsp+28h+arg_0]
0x18001489f  add     rsp, 20h
0x1800148a3  pop     rdi
0x1800148a4  jmp     cs:__imp_DeleteCriticalSection
```
