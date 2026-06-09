# CWcnWfdGoSession::~CWcnWfdGoSession(void)

- ea: `0x18004ef74`
- end: `0x18004efe1`
- name: `??1CWcnWfdGoSession@@UEAA@XZ`
- size: `109`
- prototype: `void __fastcall(CWcnWfdGoSession *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004eff0`

## callees

- `0x18000a5ac`
- `0x18004ef74`
- `0x180051934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004efb6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004efb6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004ef9e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004ef9e`

## pseudocode

```c
void __fastcall CWcnWfdGoSession::~CWcnWfdGoSession(CWcnWfdGoSession *this)
{
  struct _TP_WORK *v2; // rcx

  *(_QWORD *)this = &CWcnWfdGoSession::`vftable'{for `IWcnTransportSession'};
  *((_QWORD *)this + 4) = &CWcnWfdGoSession::`vftable'{for `IWcnSinkConsumer'};
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 32);
  if ( v2 )
  {
    CloseThreadpoolWork(v2);
    *((_QWORD *)this + 32) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  CSbSafeBuffer::~CSbSafeBuffer((CWcnWfdGoSession *)((char *)this + 200));
  CWcnEapReassembler::~CWcnEapReassembler((CWcnWfdGoSession *)((char *)this + 80));
  *(_QWORD *)this = &IWcnTransportSession::`vftable';
}

```

## disassembly

```asm
0x18004ef74  push    rbx
0x18004ef76  sub     rsp, 20h
0x18004ef7a  lea     rax, ??_7CWcnWfdGoSession@@6BIWcnTransportSession@@@; const CWcnWfdGoSession::`vftable'{for `IWcnTransportSession'}
0x18004ef81  mov     rbx, rcx
0x18004ef84  mov     [rcx], rax
0x18004ef87  lea     rax, ??_7CWcnWfdGoSession@@6BIWcnSinkConsumer@@@; const CWcnWfdGoSession::`vftable'{for `IWcnSinkConsumer'}
0x18004ef8e  mov     [rcx+20h], rax
0x18004ef92  mov     rcx, [rcx+100h]; pwk
0x18004ef99  test    rcx, rcx
0x18004ef9c  jz      short loc_18004EFAF
0x18004ef9e  call    cs:__imp_CloseThreadpoolWork
0x18004efa4  mov     qword ptr [rbx+100h], 0
0x18004efaf  lea     rcx, [rbx+108h]; lpCriticalSection
0x18004efb6  call    cs:__imp_DeleteCriticalSection
0x18004efbc  lea     rcx, [rbx+0C8h]; this
0x18004efc3  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004efc8  lea     rcx, [rbx+50h]; this
0x18004efcc  call    ??1CWcnEapReassembler@@QEAA@XZ; CWcnEapReassembler::~CWcnEapReassembler(void)
0x18004efd1  lea     rax, ??_7IWcnTransportSession@@6B@; const IWcnTransportSession::`vftable'
0x18004efd8  mov     [rbx], rax
0x18004efdb  add     rsp, 20h
0x18004efdf  pop     rbx
0x18004efe0  retn
```
