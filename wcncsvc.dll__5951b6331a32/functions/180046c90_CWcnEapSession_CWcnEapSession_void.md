# CWcnEapSession::~CWcnEapSession(void)

- ea: `0x180046c90`
- end: `0x180046cf6`
- name: `??1CWcnEapSession@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CWcnEapSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180046d10`

## callees

- `0x18000a5ac`
- `0x180046c90`
- `0x1800504cc`
- `0x180051934`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046cc8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046cc8`

## pseudocode

```c
void __fastcall CWcnEapSession::~CWcnEapSession(CWcnEapSession *this)
{
  void *v2; // rcx
  struct _TP_WORK *v3; // rcx

  *(_QWORD *)this = &CWcnEapSession::`vftable'{for `IWcnTransportSession'};
  *((_QWORD *)this + 4) = &CWcnEapSession::`vftable'{for `IWcnSinkConsumer'};
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
    WcnWlanCloseHandle(v2);
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 20);
  if ( v3 )
    CloseThreadpoolWork(v3);
  CSbSafeBuffer::~CSbSafeBuffer((CWcnEapSession *)((char *)this + 288));
  CWcnEapReassembler::~CWcnEapReassembler((CWcnEapSession *)((char *)this + 168));
  *(_QWORD *)this = &IWcnTransportSession::`vftable';
}

```

## disassembly

```asm
0x180046c90  push    rbx
0x180046c92  sub     rsp, 20h
0x180046c96  lea     rax, ??_7CWcnEapSession@@6BIWcnTransportSession@@@; const CWcnEapSession::`vftable'{for `IWcnTransportSession'}
0x180046c9d  mov     rbx, rcx
0x180046ca0  mov     [rcx], rax
0x180046ca3  lea     rax, ??_7CWcnEapSession@@6BIWcnSinkConsumer@@@; const CWcnEapSession::`vftable'{for `IWcnSinkConsumer'}
0x180046caa  mov     [rcx+20h], rax
0x180046cae  mov     rcx, [rcx+38h]; hClientHandle
0x180046cb2  test    rcx, rcx
0x180046cb5  jz      short loc_180046CBC
0x180046cb7  call    ?WcnWlanCloseHandle@@YAJPEAX@Z; WcnWlanCloseHandle(void *)
0x180046cbc  mov     rcx, [rbx+0A0h]; pwk
0x180046cc3  test    rcx, rcx
0x180046cc6  jz      short loc_180046CCE
0x180046cc8  call    cs:__imp_CloseThreadpoolWork
0x180046cce  lea     rcx, [rbx+120h]; this
0x180046cd5  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180046cda  lea     rcx, [rbx+0A8h]; this
0x180046ce1  call    ??1CWcnEapReassembler@@QEAA@XZ; CWcnEapReassembler::~CWcnEapReassembler(void)
0x180046ce6  lea     rax, ??_7IWcnTransportSession@@6B@; const IWcnTransportSession::`vftable'
0x180046ced  mov     [rbx], rax
0x180046cf0  add     rsp, 20h
0x180046cf4  pop     rbx
0x180046cf5  retn
```
