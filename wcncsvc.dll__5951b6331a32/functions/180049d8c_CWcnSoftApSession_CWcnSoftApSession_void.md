# CWcnSoftApSession::~CWcnSoftApSession(void)

- ea: `0x180049d8c`
- end: `0x180049de1`
- name: `??1CWcnSoftApSession@@UEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CWcnSoftApSession *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180049df0`

## callees

- `0x18000a5ac`
- `0x180049d8c`
- `0x180051934`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180049db6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180049db6`

## pseudocode

```c
void __fastcall CWcnSoftApSession::~CWcnSoftApSession(CWcnSoftApSession *this)
{
  struct _TP_WORK *v2; // rcx

  *(_QWORD *)this = &CWcnSoftApSession::`vftable'{for `IWcnTransportSession'};
  *((_QWORD *)this + 4) = &CWcnSoftApSession::`vftable'{for `IWcnSinkConsumer'};
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 32);
  if ( v2 )
    CloseThreadpoolWork(v2);
  CSbSafeBuffer::~CSbSafeBuffer((CWcnSoftApSession *)((char *)this + 200));
  CWcnEapReassembler::~CWcnEapReassembler((CWcnSoftApSession *)((char *)this + 80));
  *(_QWORD *)this = &IWcnTransportSession::`vftable';
}

```

## disassembly

```asm
0x180049d8c  push    rbx
0x180049d8e  sub     rsp, 20h
0x180049d92  lea     rax, ??_7CWcnSoftApSession@@6BIWcnTransportSession@@@; const CWcnSoftApSession::`vftable'{for `IWcnTransportSession'}
0x180049d99  mov     rbx, rcx
0x180049d9c  mov     [rcx], rax
0x180049d9f  lea     rax, ??_7CWcnSoftApSession@@6BIWcnSinkConsumer@@@; const CWcnSoftApSession::`vftable'{for `IWcnSinkConsumer'}
0x180049da6  mov     [rcx+20h], rax
0x180049daa  mov     rcx, [rcx+100h]; pwk
0x180049db1  test    rcx, rcx
0x180049db4  jz      short loc_180049DBC
0x180049db6  call    cs:__imp_CloseThreadpoolWork
0x180049dbc  lea     rcx, [rbx+0C8h]; this
0x180049dc3  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180049dc8  lea     rcx, [rbx+50h]; this
0x180049dcc  call    ??1CWcnEapReassembler@@QEAA@XZ; CWcnEapReassembler::~CWcnEapReassembler(void)
0x180049dd1  lea     rax, ??_7IWcnTransportSession@@6B@; const IWcnTransportSession::`vftable'
0x180049dd8  mov     [rbx], rax
0x180049ddb  add     rsp, 20h
0x180049ddf  pop     rbx
0x180049de0  retn
```
