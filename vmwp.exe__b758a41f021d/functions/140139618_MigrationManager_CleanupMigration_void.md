# MigrationManager::CleanupMigration(void)

- ea: `0x140139618`
- end: `0x1401396f8`
- name: `?CleanupMigration@MigrationManager@@QEAAXXZ`
- size: `224`
- prototype: `void __fastcall(MigrationManager *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140058e1c`
- `0x1400b35a8`
- `0x140155270`
- `0x140155550`
- `0x14020e2bc`
- `0x140216f60`

## callees

- `0x140022548`
- `0x14003e2b8`
- `0x1400557e0`
- `0x140085634`
- `0x140139618`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1401396cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1401396cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140139631`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140139631`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140139651`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140139651`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MigrationManager::CleanupMigration(PTP_WAIT *this)
{
  SetThreadpoolWait(this[28], 0, 0);
  if ( !*((_DWORD *)this + 58) )
  {
    WaitForThreadpoolWaitCallbacks(this[28], 1);
    if ( !*((_DWORD *)this + 58) )
      Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)this);
  }
  *((_DWORD *)this + 53) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(this + 30);
  Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(this + 20));
  this[10] = 0;
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 44) = 0;
  Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(this + 13, 0);
  *((_DWORD *)this + 42) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 20);
  (*(void (__fastcall **)(PTP_WAIT))(*(_QWORD *)this[31] + 80LL))(this[31]);
}

```

## disassembly

```asm
0x140139618  mov     [rsp+arg_8], rbx
0x14013961d  push    rdi
0x14013961e  sub     rsp, 30h
0x140139622  mov     rdi, rcx
0x140139625  xor     r8d, r8d; pftTimeout
0x140139628  xor     edx, edx; h
0x14013962a  mov     rcx, [rcx+0E0h]; pwa
0x140139631  call    cs:__imp_SetThreadpoolWait
0x140139638  nop     dword ptr [rax+rax+00h]
0x14013963d  mov     eax, [rdi+0E8h]
0x140139643  test    eax, eax
0x140139645  jnz     short loc_14013966F
0x140139647  lea     edx, [rax+1]; fCancelPendingCallbacks
0x14013964a  mov     rcx, [rdi+0E0h]; pwa
0x140139651  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x140139658  nop     dword ptr [rax+rax+00h]
0x14013965d  mov     eax, [rdi+0E8h]
0x140139663  test    eax, eax
0x140139665  jnz     short loc_14013966F
0x140139667  mov     rcx, rdi; this
0x14013966a  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14013966f  mov     dword ptr [rdi+0D4h], 0
0x140139679  lea     rcx, [rdi+0F0h]
0x140139680  xor     edx, edx
0x140139682  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140139687  lea     rbx, [rdi+0A0h]
0x14013968e  mov     rcx, rbx; this
0x140139691  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140139696  mov     [rsp+38h+var_18], rbx
0x14013969b  mov     [rsp+38h+var_10], 1
0x1401396a0  mov     qword ptr [rdi+50h], 0
0x1401396a8  mov     dword ptr [rdi+58h], 0
0x1401396af  mov     dword ptr [rdi+0B0h], 0
0x1401396b9  lea     rcx, [rdi+68h]
0x1401396bd  xor     edx, edx
0x1401396bf  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x1401396c4  nop
0x1401396c5  mov     dword ptr [rbx+8], 0
0x1401396cc  mov     rcx, rbx; SRWLock
0x1401396cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1401396d6  nop     dword ptr [rax+rax+00h]
0x1401396db  mov     rcx, [rdi+0F8h]
0x1401396e2  mov     rax, [rcx]
0x1401396e5  mov     rax, [rax+50h]
0x1401396e9  mov     rbx, [rsp+38h+arg_8]
0x1401396ee  add     rsp, 30h
0x1401396f2  pop     rdi
0x1401396f3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
