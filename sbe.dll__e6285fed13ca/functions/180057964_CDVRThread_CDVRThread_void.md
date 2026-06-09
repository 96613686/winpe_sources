# CDVRThread::~CDVRThread(void)

- ea: `0x180057964`
- end: `0x1800579c1`
- name: `??1CDVRThread@@UEAA@XZ`
- size: `93`
- prototype: `void __fastcall(CDVRThread *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18003cbe0`
- `0x18003ce50`

## callees

- `0x18000716c`
- `0x180057964`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180057982`
- `KERNEL32!WaitForSingleObject` at `0x180057982`
- `KERNEL32!CloseHandle` at `0x18005798b`
- `KERNEL32!CloseHandle` at `0x18005798b`
- `KERNEL32!DeleteCriticalSection` at `0x180057995`
- `KERNEL32!DeleteCriticalSection` at `0x18005799f`
- `KERNEL32!DeleteCriticalSection` at `0x180057995`
- `KERNEL32!DeleteCriticalSection` at `0x18005799f`

## pseudocode

```c
void __fastcall CDVRThread::~CDVRThread(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rdi

  v2 = (void *)_InterlockedExchange64((volatile __int64 *)&this->SpinCount, 0);
  if ( v2 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    CloseHandle(v2);
  }
  DeleteCriticalSection(this + 2);
  DeleteCriticalSection(this + 1);
  CAMEvent::~CAMEvent((CAMEvent *)&this->OwningThread);
  CAMEvent::~CAMEvent((CAMEvent *)&this->LockCount);
}

```

## disassembly

```asm
0x180057964  mov     [rsp+arg_0], rbx
0x180057969  push    rdi
0x18005796a  sub     rsp, 20h
0x18005796e  xor     edi, edi
0x180057970  mov     rbx, rcx
0x180057973  xchg    rdi, [rcx+20h]
0x180057977  test    rdi, rdi
0x18005797a  jz      short loc_180057991
0x18005797c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005797f  mov     rcx, rdi; hHandle
0x180057982  call    cs:__imp_WaitForSingleObject
0x180057988  mov     rcx, rdi; hObject
0x18005798b  call    cs:__imp_CloseHandle
0x180057991  lea     rcx, [rbx+50h]; lpCriticalSection
0x180057995  call    cs:__imp_DeleteCriticalSection
0x18005799b  lea     rcx, [rbx+28h]; lpCriticalSection
0x18005799f  call    cs:__imp_DeleteCriticalSection
0x1800579a5  lea     rcx, [rbx+10h]; this
0x1800579a9  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800579ae  lea     rcx, [rbx+8]; this
0x1800579b2  mov     rbx, [rsp+28h+arg_0]
0x1800579b7  add     rsp, 20h
0x1800579bb  pop     rdi
0x1800579bc  jmp     ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
```
