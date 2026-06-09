# WorkThreadManager::CThread::RunCurrentTaskUnderLock(void)

- ea: `0x18002e910`
- end: `0x18002e9cc`
- name: `?RunCurrentTaskUnderLock@CThread@WorkThreadManager@@QEAAXXZ`
- size: `188`
- prototype: `void __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002b504`

## callees

- `0x18002e1a0`
- `0x18002e910`
- `0x1800362f8`
- `0x180078010`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18002e927`
- `KERNEL32!AcquireSRWLockShared` at `0x18002e927`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002e9bb`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002e9bb`
- `KERNEL32!GetCurrentThread` at `0x18002e9a0`
- `KERNEL32!GetCurrentThread` at `0x18002e9a0`
- `KERNEL32!SetThreadPriority` at `0x18002e9ad`
- `KERNEL32!SetThreadPriority` at `0x18002e9ad`

## pseudocode

```c
void __fastcall WorkThreadManager::CThread::RunCurrentTaskUnderLock(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  __int64 v3; // rcx
  PVOID Ptr; // rcx
  PVOID v5; // rcx
  HANDLE CurrentThread; // rax
  _DWORD v7[2]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+28h] [rbp-10h]

  v1 = this + 28;
  AcquireSRWLockShared(this + 28);
  if ( this[24].Ptr )
  {
    WorkThreadManager::CThread::AdjustThreadPriority(v3, v7, HIDWORD(this[18].Ptr));
    Ptr = this[24].Ptr;
    LODWORD(this[16].Ptr) = (HIDWORD(this[9].Ptr) | (LODWORD(this[9].Ptr) << 24) | 0x800000) + 1;
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 24LL))(Ptr);
    v5 = this[20].Ptr;
    LODWORD(this[16].Ptr) = (HIDWORD(this[9].Ptr) | (LODWORD(this[9].Ptr) << 24)) + 1;
    if ( v5 )
      SetEvent_0(v5);
    if ( v8 && v7[0] )
    {
      CurrentThread = GetCurrentThread();
      SetThreadPriority(CurrentThread, v7[1]);
    }
  }
  if ( v1 )
    ReleaseSRWLockShared(v1);
}

```

## disassembly

```asm
0x18002e910  mov     [rsp+arg_0], rbx
0x18002e915  push    rdi
0x18002e916  sub     rsp, 30h
0x18002e91a  lea     rdi, [rcx+0E0h]
0x18002e921  mov     rbx, rcx
0x18002e924  mov     rcx, rdi; SRWLock
0x18002e927  call    cs:__imp_AcquireSRWLockShared
0x18002e92d  cmp     qword ptr [rbx+0C0h], 0
0x18002e935  jz      short loc_18002E9B3
0x18002e937  mov     r8d, [rbx+94h]
0x18002e93e  lea     rdx, [rsp+38h+var_18]
0x18002e943  call    ?AdjustThreadPriority@CThread@WorkThreadManager@@QEAA@W4TaskOptions@Internal@Windows@@@Z; WorkThreadManager::CThread::AdjustThreadPriority(Windows::Internal::TaskOptions)
0x18002e948  mov     eax, [rbx+48h]
0x18002e94b  mov     rcx, [rbx+0C0h]
0x18002e952  shl     eax, 18h
0x18002e955  or      eax, [rbx+4Ch]
0x18002e958  bts     eax, 17h
0x18002e95c  inc     eax
0x18002e95e  mov     [rbx+80h], eax
0x18002e964  mov     rax, [rcx]
0x18002e967  mov     rax, [rax+18h]
0x18002e96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e970  mov     eax, [rbx+48h]
0x18002e973  mov     rcx, [rbx+0A0h]; hEvent
0x18002e97a  shl     eax, 18h
0x18002e97d  or      eax, [rbx+4Ch]
0x18002e980  inc     eax
0x18002e982  mov     [rbx+80h], eax
0x18002e988  test    rcx, rcx
0x18002e98b  jz      short loc_18002E992
0x18002e98d  call    SetEvent_0
0x18002e992  cmp     [rsp+38h+var_10], 0
0x18002e997  jz      short loc_18002E9B3
0x18002e999  cmp     [rsp+38h+var_18], 0
0x18002e99e  jz      short loc_18002E9B3
0x18002e9a0  call    cs:__imp_GetCurrentThread
0x18002e9a6  mov     edx, [rsp+38h+nPriority]; nPriority
0x18002e9aa  mov     rcx, rax; hThread
0x18002e9ad  call    cs:__imp_SetThreadPriority
0x18002e9b3  test    rdi, rdi
0x18002e9b6  jz      short loc_18002E9C1
0x18002e9b8  mov     rcx, rdi; SRWLock
0x18002e9bb  call    cs:__imp_ReleaseSRWLockShared
0x18002e9c1  mov     rbx, [rsp+38h+arg_0]
0x18002e9c6  add     rsp, 30h
0x18002e9ca  pop     rdi
0x18002e9cb  retn
```
