# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140008d70`
- end: `0x140008f02`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `402`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000a324`

## callees

- `0x140008d70`
- `0x14000c16c`
- `0x140015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140008dba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008dba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008eef`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008eef`
- `KERNEL32!SetThreadpoolTimer` at `0x140008e85`
- `KERNEL32!SetThreadpoolTimer` at `0x140008edd`
- `KERNEL32!SetThreadpoolTimer` at `0x140008e85`
- `KERNEL32!SetThreadpoolTimer` at `0x140008edd`
- `KERNEL32!CreateThreadpoolTimer` at `0x140008e60`
- `KERNEL32!CreateThreadpoolTimer` at `0x140008e60`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008e93`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008e93`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008e9c`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008e9c`
- `KERNEL32!GetLastError` at `0x140008e4a`
- `KERNEL32!GetLastError` at `0x140008e72`
- `KERNEL32!GetLastError` at `0x140008e4a`
- `KERNEL32!GetLastError` at `0x140008e72`
- `KERNEL32!SetLastError` at `0x140008ea4`
- `KERNEL32!SetLastError` at `0x140008eb1`
- `KERNEL32!SetLastError` at `0x140008ea4`
- `KERNEL32!SetLastError` at `0x140008eb1`
- `msvcrt!memcpy_s` at `0x140008e2f`
- `msvcrt!memcpy_s` at `0x140008e2f`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v8; // r15
  DWORD v9; // ebx
  struct _TP_TIMER *v10; // rcx
  _QWORD Source[9]; // [rsp+20h] [rbp-48h] BYREF
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = 58674884;
      Source[1] = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
      {
        memcpy_s(pv[5].Ptr, ((char *)pv[6].Ptr - (char *)pv[5].Ptr) & -(__int64)(pv[5].Ptr < pv[6].Ptr), Source, 0x10u);
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
      }
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          v8 = ThreadpoolTimer;
          if ( Ptr )
          {
            v9 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v9);
          }
          pv[2].Ptr = v8;
          SetLastError(LastError);
        }
        v10 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v10 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x140008d70  push    rbx
0x140008d72  push    rbp
0x140008d73  push    rsi
0x140008d74  push    rdi
0x140008d75  push    r14
0x140008d77  push    r15
0x140008d79  sub     rsp, 38h
0x140008d7d  mov     eax, [rcx]
0x140008d7f  mov     rbx, r8
0x140008d82  mov     rdi, rcx
0x140008d85  test    eax, eax
0x140008d87  jz      loc_140008EF5
0x140008d8d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008d94  jnz     loc_140008EF5
0x140008d9a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008da1  test    rax, rax
0x140008da4  jz      short loc_140008DB3
0x140008da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008dab  test    al, al
0x140008dad  jnz     loc_140008EF5
0x140008db3  lea     rsi, [rdi+8]
0x140008db7  mov     rcx, rsi; SRWLock
0x140008dba  call    cs:__imp_AcquireSRWLockExclusive
0x140008dc0  mov     eax, [rdi]
0x140008dc2  test    eax, eax
0x140008dc4  jz      loc_140008EE7
0x140008dca  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008dd1  jnz     loc_140008EE7
0x140008dd7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008dde  test    rax, rax
0x140008de1  jz      short loc_140008DF0
0x140008de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008de8  test    al, al
0x140008dea  jnz     loc_140008EE7
0x140008df0  mov     ebp, 10h
0x140008df5  mov     [rsp+68h+Source], 37F4EC4h
0x140008dfe  mov     edx, ebp; unsigned __int64
0x140008e00  mov     [rsp+68h+var_40], rbx
0x140008e05  lea     rcx, [rdi+20h]; this
0x140008e09  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008e0e  test    al, al
0x140008e10  jz      short loc_140008E39
0x140008e12  mov     rcx, [rdi+28h]; Destination
0x140008e16  lea     r8, [rsp+68h+Source]; Source
0x140008e1b  mov     rax, [rdi+30h]
0x140008e1f  mov     r9d, ebp; SourceSize
0x140008e22  sub     rax, rcx
0x140008e25  cmp     rcx, [rdi+30h]
0x140008e29  sbb     rdx, rdx
0x140008e2c  and     rdx, rax; DestinationSize
0x140008e2f  call    cs:__imp_memcpy_s
0x140008e35  add     [rdi+28h], rbp
0x140008e39  cmp     byte ptr [rdi+18h], 0
0x140008e3d  jnz     loc_140008EE7
0x140008e43  cmp     qword ptr [rdi+10h], 0
0x140008e48  jnz     short loc_140008EB7
0x140008e4a  call    cs:__imp_GetLastError
0x140008e50  xor     r8d, r8d; pcbe
0x140008e53  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140008e5a  mov     rdx, rdi; pv
0x140008e5d  mov     r14d, eax
0x140008e60  call    cs:__imp_CreateThreadpoolTimer
0x140008e66  mov     rbp, [rdi+10h]
0x140008e6a  mov     r15, rax
0x140008e6d  test    rbp, rbp
0x140008e70  jz      short loc_140008EAA
0x140008e72  call    cs:__imp_GetLastError
0x140008e78  xor     r9d, r9d; msWindowLength
0x140008e7b  xor     r8d, r8d; msPeriod
0x140008e7e  xor     edx, edx; pftDueTime
0x140008e80  mov     rcx, rbp; pti
0x140008e83  mov     ebx, eax
0x140008e85  call    cs:__imp_SetThreadpoolTimer
0x140008e8b  mov     edx, 1; fCancelPendingCallbacks
0x140008e90  mov     rcx, rbp; pti
0x140008e93  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008e99  mov     rcx, rbp; pti
0x140008e9c  call    cs:__imp_CloseThreadpoolTimer
0x140008ea2  mov     ecx, ebx; dwErrCode
0x140008ea4  call    cs:__imp_SetLastError
0x140008eaa  mov     ecx, r14d; dwErrCode
0x140008ead  mov     [rdi+10h], r15
0x140008eb1  call    cs:__imp_SetLastError
0x140008eb7  mov     rcx, [rdi+10h]; pti
0x140008ebb  test    rcx, rcx
0x140008ebe  jz      short loc_140008EE7
0x140008ec0  mov     rax, 0FFFFFFFF4D2FA200h
0x140008eca  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140008ecf  mov     r9d, 124F8h; msWindowLength
0x140008ed5  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x140008eda  xor     r8d, r8d; msPeriod
0x140008edd  call    cs:__imp_SetThreadpoolTimer
0x140008ee3  mov     byte ptr [rdi+18h], 1
0x140008ee7  test    rsi, rsi
0x140008eea  jz      short loc_140008EF5
0x140008eec  mov     rcx, rsi; SRWLock
0x140008eef  call    cs:__imp_ReleaseSRWLockExclusive
0x140008ef5  add     rsp, 38h
0x140008ef9  pop     r15
0x140008efb  pop     r14
0x140008efd  pop     rdi
0x140008efe  pop     rsi
0x140008eff  pop     rbp
0x140008f00  pop     rbx
0x140008f01  retn
```
