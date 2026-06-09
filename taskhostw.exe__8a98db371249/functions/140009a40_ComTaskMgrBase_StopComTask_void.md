# ComTaskMgrBase::StopComTask(void * *)

- ea: `0x140009a40`
- end: `0x140009ab0`
- name: `?StopComTask@ComTaskMgrBase@@UEAAJPEAPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(ComTaskMgrBase *this, ComTaskHost **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004cf0`
- `0x140006f60`
- `0x140009a40`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::StopComTask(ComTaskMgrBase *this, ComTaskHost **a2)
{
  unsigned int v3; // ebx
  __int32 v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  _InterlockedExchange(&v5, 0);
  _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
  _InterlockedExchange(&v5, _InterlockedCompareExchange(&dword_1400159E4, 0, 0) != 0);
  if ( _InterlockedCompareExchange(&v5, 0, 0) )
    v3 = ComTaskHost::Stop(*a2);
  else
    v3 = -2147024255;
  ShutdownGuard::~ShutdownGuard((ShutdownGuard *)&v5);
  *a2 = 0;
  return v3;
}

```

## disassembly

```asm
0x140009a40  mov     [rsp+arg_0], rbx
0x140009a45  push    rdi
0x140009a46  sub     rsp, 20h
0x140009a4a  mov     rdi, rdx
0x140009a4d  mov     [rsp+28h+arg_8], 0
0x140009a55  xor     eax, eax
0x140009a57  xchg    eax, [rsp+28h+arg_8]
0x140009a5b  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x140009a62  xor     ecx, ecx
0x140009a64  xor     eax, eax
0x140009a66  lock cmpxchg cs:dword_1400159E4, ecx
0x140009a6e  setnz   cl
0x140009a71  xchg    ecx, [rsp+28h+arg_8]
0x140009a75  xor     ecx, ecx
0x140009a77  xor     eax, eax
0x140009a79  lock cmpxchg [rsp+28h+arg_8], ecx
0x140009a7f  jz      short loc_140009A8D
0x140009a81  mov     rcx, [rdx]; this
0x140009a84  call    ?Stop@ComTaskHost@@QEAAJXZ; ComTaskHost::Stop(void)
0x140009a89  mov     ebx, eax
0x140009a8b  jmp     short loc_140009A92
0x140009a8d  mov     ebx, 80070281h
0x140009a92  lea     rcx, [rsp+28h+arg_8]; this
0x140009a97  call    ??1ShutdownGuard@@QEAA@XZ; ShutdownGuard::~ShutdownGuard(void)
0x140009a9c  mov     qword ptr [rdi], 0
0x140009aa3  mov     eax, ebx
0x140009aa5  mov     rbx, [rsp+28h+arg_0]
0x140009aaa  add     rsp, 20h
0x140009aae  pop     rdi
0x140009aaf  retn
```
