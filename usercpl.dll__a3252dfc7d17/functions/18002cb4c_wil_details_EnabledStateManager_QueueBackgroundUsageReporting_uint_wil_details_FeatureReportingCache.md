# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002cb4c`
- end: `0x18002ccdf`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002ce58`

## callees

- `0x180019324`
- `0x18002cb4c`
- `0x180078010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002cc0c`
- `msvcrt!memcpy_s` at `0x18002cc0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cccc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cccc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cb98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cb98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002cc70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002cc70`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002cc3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002cc3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002cc62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ccba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002cc62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ccba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002cc79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002cc79`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v9; // r15
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-40h]
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
      Source[0] = a2;
      Source[1] = 0;
      v13 = a3;
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
          v9 = ThreadpoolTimer;
          if ( Ptr )
          {
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = v9;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
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
0x18002cb4c  push    rbx
0x18002cb4e  push    rbp
0x18002cb4f  push    rsi
0x18002cb50  push    rdi
0x18002cb51  push    r14
0x18002cb53  push    r15
0x18002cb55  sub     rsp, 38h
0x18002cb59  mov     eax, [rcx]
0x18002cb5b  mov     rbx, r8
0x18002cb5e  mov     ebp, edx
0x18002cb60  mov     rdi, rcx
0x18002cb63  test    eax, eax
0x18002cb65  jz      loc_18002CCD2
0x18002cb6b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002cb72  jnz     loc_18002CCD2
0x18002cb78  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002cb7f  test    rax, rax
0x18002cb82  jz      short loc_18002CB91
0x18002cb84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb89  test    al, al
0x18002cb8b  jnz     loc_18002CCD2
0x18002cb91  lea     rsi, [rdi+8]
0x18002cb95  mov     rcx, rsi; SRWLock
0x18002cb98  call    cs:__imp_AcquireSRWLockExclusive
0x18002cb9e  mov     eax, [rdi]
0x18002cba0  test    eax, eax
0x18002cba2  jz      loc_18002CCC4
0x18002cba8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002cbaf  jnz     loc_18002CCC4
0x18002cbb5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002cbbc  test    rax, rax
0x18002cbbf  jz      short loc_18002CBCE
0x18002cbc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbc6  test    al, al
0x18002cbc8  jnz     loc_18002CCC4
0x18002cbce  xor     eax, eax
0x18002cbd0  mov     [rsp+68h+Source], ebp
0x18002cbd4  lea     rcx, [rdi+20h]; this
0x18002cbd8  mov     [rsp+68h+var_44], eax
0x18002cbdc  mov     [rsp+68h+var_40], rbx
0x18002cbe1  lea     ebp, [rax+10h]
0x18002cbe4  mov     edx, ebp; unsigned __int64
0x18002cbe6  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18002cbeb  test    al, al
0x18002cbed  jz      short loc_18002CC16
0x18002cbef  mov     rcx, [rdi+28h]; Destination
0x18002cbf3  lea     r8, [rsp+68h+Source]; Source
0x18002cbf8  mov     rax, [rdi+30h]
0x18002cbfc  mov     r9d, ebp; SourceSize
0x18002cbff  sub     rax, rcx
0x18002cc02  cmp     rcx, [rdi+30h]
0x18002cc06  sbb     rdx, rdx
0x18002cc09  and     rdx, rax; DestinationSize
0x18002cc0c  call    cs:__imp_memcpy_s
0x18002cc12  add     [rdi+28h], rbp
0x18002cc16  cmp     byte ptr [rdi+18h], 0
0x18002cc1a  jnz     loc_18002CCC4
0x18002cc20  cmp     qword ptr [rdi+10h], 0
0x18002cc25  jnz     short loc_18002CC94
0x18002cc27  call    cs:__imp_GetLastError
0x18002cc2d  xor     r8d, r8d; pcbe
0x18002cc30  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002cc37  mov     rdx, rdi; pv
0x18002cc3a  mov     r14d, eax
0x18002cc3d  call    cs:__imp_CreateThreadpoolTimer
0x18002cc43  mov     rbp, [rdi+10h]
0x18002cc47  mov     r15, rax
0x18002cc4a  test    rbp, rbp
0x18002cc4d  jz      short loc_18002CC87
0x18002cc4f  call    cs:__imp_GetLastError
0x18002cc55  xor     r9d, r9d; msWindowLength
0x18002cc58  xor     r8d, r8d; msPeriod
0x18002cc5b  xor     edx, edx; pftDueTime
0x18002cc5d  mov     rcx, rbp; pti
0x18002cc60  mov     ebx, eax
0x18002cc62  call    cs:__imp_SetThreadpoolTimer
0x18002cc68  mov     edx, 1; fCancelPendingCallbacks
0x18002cc6d  mov     rcx, rbp; pti
0x18002cc70  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002cc76  mov     rcx, rbp; pti
0x18002cc79  call    cs:__imp_CloseThreadpoolTimer
0x18002cc7f  mov     ecx, ebx; dwErrCode
0x18002cc81  call    cs:__imp_SetLastError
0x18002cc87  mov     ecx, r14d; dwErrCode
0x18002cc8a  mov     [rdi+10h], r15
0x18002cc8e  call    cs:__imp_SetLastError
0x18002cc94  mov     rcx, [rdi+10h]; pti
0x18002cc98  test    rcx, rcx
0x18002cc9b  jz      short loc_18002CCC4
0x18002cc9d  mov     rax, 0FFFFFFFF4D2FA200h
0x18002cca7  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18002ccac  mov     r9d, 124F8h; msWindowLength
0x18002ccb2  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18002ccb7  xor     r8d, r8d; msPeriod
0x18002ccba  call    cs:__imp_SetThreadpoolTimer
0x18002ccc0  mov     byte ptr [rdi+18h], 1
0x18002ccc4  test    rsi, rsi
0x18002ccc7  jz      short loc_18002CCD2
0x18002ccc9  mov     rcx, rsi; SRWLock
0x18002cccc  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ccd2  add     rsp, 38h
0x18002ccd6  pop     r15
0x18002ccd8  pop     r14
0x18002ccda  pop     rdi
0x18002ccdb  pop     rsi
0x18002ccdc  pop     rbp
0x18002ccdd  pop     rbx
0x18002ccde  retn
```
