# CWcnWfdClientSession::~CWcnWfdClientSession(void)

- ea: `0x18004bcf0`
- end: `0x18004bd56`
- name: `??1CWcnWfdClientSession@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CWcnWfdClientSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004bd60`

## callees

- `0x18000a5ac`
- `0x18004bcf0`
- `0x1800504cc`
- `0x180051934`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004bd28`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004bd28`

## pseudocode

```c
void __fastcall CWcnWfdClientSession::~CWcnWfdClientSession(CWcnWfdClientSession *this)
{
  void *v2; // rcx
  struct _TP_WORK *v3; // rcx

  *(_QWORD *)this = &CWcnWfdClientSession::`vftable'{for `IWcnTransportSession'};
  *((_QWORD *)this + 4) = &CWcnWfdClientSession::`vftable'{for `IWcnSinkConsumer'};
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
    WcnWlanCloseHandle(v2);
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 19);
  if ( v3 )
    CloseThreadpoolWork(v3);
  CSbSafeBuffer::~CSbSafeBuffer((CWcnWfdClientSession *)((char *)this + 280));
  CWcnEapReassembler::~CWcnEapReassembler((CWcnWfdClientSession *)((char *)this + 160));
  *(_QWORD *)this = &IWcnTransportSession::`vftable';
}

```

## disassembly

```asm
0x18004bcf0  push    rbx
0x18004bcf2  sub     rsp, 20h
0x18004bcf6  lea     rax, ??_7CWcnWfdClientSession@@6BIWcnTransportSession@@@; const CWcnWfdClientSession::`vftable'{for `IWcnTransportSession'}
0x18004bcfd  mov     rbx, rcx
0x18004bd00  mov     [rcx], rax
0x18004bd03  lea     rax, ??_7CWcnWfdClientSession@@6BIWcnSinkConsumer@@@; const CWcnWfdClientSession::`vftable'{for `IWcnSinkConsumer'}
0x18004bd0a  mov     [rcx+20h], rax
0x18004bd0e  mov     rcx, [rcx+38h]; hClientHandle
0x18004bd12  test    rcx, rcx
0x18004bd15  jz      short loc_18004BD1C
0x18004bd17  call    ?WcnWlanCloseHandle@@YAJPEAX@Z; WcnWlanCloseHandle(void *)
0x18004bd1c  mov     rcx, [rbx+98h]; pwk
0x18004bd23  test    rcx, rcx
0x18004bd26  jz      short loc_18004BD2E
0x18004bd28  call    cs:__imp_CloseThreadpoolWork
0x18004bd2e  lea     rcx, [rbx+118h]; this
0x18004bd35  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004bd3a  lea     rcx, [rbx+0A0h]; this
0x18004bd41  call    ??1CWcnEapReassembler@@QEAA@XZ; CWcnEapReassembler::~CWcnEapReassembler(void)
0x18004bd46  lea     rax, ??_7IWcnTransportSession@@6B@; const IWcnTransportSession::`vftable'
0x18004bd4d  mov     [rbx], rax
0x18004bd50  add     rsp, 20h
0x18004bd54  pop     rbx
0x18004bd55  retn
```
