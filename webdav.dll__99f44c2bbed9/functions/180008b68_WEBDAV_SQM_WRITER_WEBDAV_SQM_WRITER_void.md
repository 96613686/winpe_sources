# WEBDAV_SQM_WRITER::~WEBDAV_SQM_WRITER(void)

- ea: `0x180008b68`
- end: `0x180008be8`
- name: `??1WEBDAV_SQM_WRITER@@UEAA@XZ`
- size: `128`
- prototype: `void __fastcall(WEBDAV_SQM_WRITER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800090a0`

## callees

- `0x180008b68`
- `0x180015e10`
- `0x180015eb4`
- `0x180015f44`

## import_xrefs

- `msvcrt!_aligned_free` at `0x180008bd4`
- `msvcrt!_aligned_free` at `0x180008bd4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008b8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008b8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ba5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ba5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008b9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008b9b`

## pseudocode

```c
void __fastcall WEBDAV_SQM_WRITER::~WEBDAV_SQM_WRITER(WEBDAV_SQM_WRITER *this)
{
  struct _TP_TIMER *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &WEBDAV_SQM_WRITER::`vftable';
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 4), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 4));
    *((_QWORD *)this + 4) = 0;
    WEBDAV_SQM_WRITER::SampleRuntimeData(this);
    WEBDAV_SQM_WRITER::WriteRuntimeData(this);
    WEBDAV_SQM_WRITER::WriteTraceLoggingRuntimeData(this);
  }
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    _aligned_free(v3);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180008b68  push    rbx
0x180008b6a  sub     rsp, 20h
0x180008b6e  lea     rax, ??_7WEBDAV_SQM_WRITER@@6B@; const WEBDAV_SQM_WRITER::`vftable'
0x180008b75  mov     rbx, rcx
0x180008b78  mov     [rcx], rax
0x180008b7b  mov     rcx, [rcx+20h]; pti
0x180008b7f  test    rcx, rcx
0x180008b82  jz      short loc_180008BCB
0x180008b84  xor     r9d, r9d; msWindowLength
0x180008b87  xor     r8d, r8d; msPeriod
0x180008b8a  xor     edx, edx; pftDueTime
0x180008b8c  call    cs:__imp_SetThreadpoolTimer
0x180008b92  mov     rcx, [rbx+20h]; pti
0x180008b96  mov     edx, 1; fCancelPendingCallbacks
0x180008b9b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008ba1  mov     rcx, [rbx+20h]; pti
0x180008ba5  call    cs:__imp_CloseThreadpoolTimer
0x180008bab  mov     rcx, rbx; this
0x180008bae  mov     qword ptr [rbx+20h], 0
0x180008bb6  call    ?SampleRuntimeData@WEBDAV_SQM_WRITER@@QEAAXXZ; WEBDAV_SQM_WRITER::SampleRuntimeData(void)
0x180008bbb  mov     rcx, rbx; this
0x180008bbe  call    ?WriteRuntimeData@WEBDAV_SQM_WRITER@@QEAAXXZ; WEBDAV_SQM_WRITER::WriteRuntimeData(void)
0x180008bc3  mov     rcx, rbx; this
0x180008bc6  call    ?WriteTraceLoggingRuntimeData@WEBDAV_SQM_WRITER@@QEAAXXZ; WEBDAV_SQM_WRITER::WriteTraceLoggingRuntimeData(void)
0x180008bcb  mov     rcx, [rbx+8]; Block
0x180008bcf  test    rcx, rcx
0x180008bd2  jz      short loc_180008BE2
0x180008bd4  call    cs:__imp__aligned_free
0x180008bda  mov     qword ptr [rbx+8], 0
0x180008be2  add     rsp, 20h
0x180008be6  pop     rbx
0x180008be7  retn
```
