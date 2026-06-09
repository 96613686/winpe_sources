# PolicyManager::PolicyChangedCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800aab70`
- end: `0x1800aabf4`
- name: `?PolicyChangedCallback@PolicyManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `132`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x1800660ac`
- `0x1800aab70`
- `0x1800abd88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800aabb3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800aabb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aab88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aab88`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PolicyManager::PolicyChangedCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _BYTE *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  EvtException *v6; // [rsp+20h] [rbp-28h] BYREF
  _BYTE *v7; // [rsp+28h] [rbp-20h] BYREF
  char v8; // [rsp+30h] [rbp-18h]

  v7 = Context;
  AcquireSRWLockExclusive((PSRWLOCK)Context);
  v8 = 1;
  if ( Context[132] || (SetThreadpoolWait(*((PTP_WAIT *)Context + 6), *((HANDLE *)Context + 5), 0), WaitResult == 258) )
  {
    utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v7);
  }
  else
  {
    try
    {
      PolicyManager::Update(Context, (__int64)&v7);
      utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v7);
    }
    catch ( EvtException *v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids,
          *((unsigned int *)v6 + 6));
      }
    }
  }
}

```

## disassembly

```asm
0x1800aab70  mov     [rsp+arg_0], rbx
0x1800aab75  push    rdi
0x1800aab76  sub     rsp, 40h
0x1800aab7a  mov     edi, r9d
0x1800aab7d  mov     rbx, rdx
0x1800aab80  mov     [rsp+48h+var_20], rdx
0x1800aab85  mov     rcx, rdx; SRWLock
0x1800aab88  call    cs:__imp_AcquireSRWLockExclusive
0x1800aab8e  mov     [rsp+48h+var_18], 1
0x1800aab93  cmp     byte ptr [rbx+84h], 0
0x1800aab9a  jz      short loc_1800AABA8
0x1800aab9c  lea     rcx, [rsp+48h+var_20]
0x1800aaba1  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x1800aaba6  jmp     short loc_1800AABE8
0x1800aaba8  xor     r8d, r8d; pftTimeout
0x1800aabab  mov     rdx, [rbx+28h]; h
0x1800aabaf  mov     rcx, [rbx+30h]; pwa
0x1800aabb3  call    cs:__imp_SetThreadpoolWait
0x1800aabb9  cmp     edi, 102h
0x1800aabbf  jnz     short loc_1800AABCD
0x1800aabc1  lea     rcx, [rsp+48h+var_20]
0x1800aabc6  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x1800aabcb  jmp     short loc_1800AABE8
0x1800aabcd  lea     rdx, [rsp+48h+var_20]
0x1800aabd2  mov     rcx, rbx
0x1800aabd5  call    ?Update@PolicyManager@@AEAAXAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; PolicyManager::Update(utl::unique_lock<utl::shared_mutex> &)
0x1800aabda  nop
0x1800aabdb  lea     rcx, [rsp+48h+var_20]
0x1800aabe0  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x1800aabe5  nop
0x1800aabe6  jmp     short $+2
0x1800aabe8  mov     rbx, [rsp+48h+arg_0]
0x1800aabed  add     rsp, 40h
0x1800aabf1  pop     rdi
0x1800aabf2  retn
```
