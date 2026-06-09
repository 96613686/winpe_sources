# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140014960`
- end: `0x140014b18`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140016524`

## callees

- `0x14000624e`
- `0x140006314`
- `0x140014960`
- `0x14001cc14`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140014a75`
- `KERNEL32!CreateThreadpoolTimer` at `0x140014a75`
- `KERNEL32!SetThreadpoolTimer` at `0x140014a9a`
- `KERNEL32!SetThreadpoolTimer` at `0x140014af2`
- `KERNEL32!SetThreadpoolTimer` at `0x140014a9a`
- `KERNEL32!SetThreadpoolTimer` at `0x140014af2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400149ad`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400149ad`
- `KERNEL32!CloseThreadpoolTimer` at `0x140014ab1`
- `KERNEL32!CloseThreadpoolTimer` at `0x140014ab1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140014b04`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140014b04`
- `KERNEL32!GetLastError` at `0x140014a5f`
- `KERNEL32!GetLastError` at `0x140014a87`
- `KERNEL32!GetLastError` at `0x140014a5f`
- `KERNEL32!GetLastError` at `0x140014a87`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140014aa8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140014aa8`
- `KERNEL32!SetLastError` at `0x140014ab9`
- `KERNEL32!SetLastError` at `0x140014ac6`
- `KERNEL32!SetLastError` at `0x140014ab9`
- `KERNEL32!SetLastError` at `0x140014ac6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014a11`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014a39`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014a11`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014a39`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  size_t v8; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
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
          if ( Ptr )
          {
            v12 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v12);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v13 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v13 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v13, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v7 = pv[5].Ptr;
    v8 = ((char *)pv[6].Ptr - (char *)v7) & -(__int64)(v7 < pv[6].Ptr);
    if ( v7 )
    {
      if ( v8 >= 0x10 )
      {
        *v7 = a2;
        v7[1] = 0;
        *((_QWORD *)v7 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v7, 0, v8);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x140014960  push    rbx
0x140014962  push    rbp
0x140014963  push    rsi
0x140014964  push    rdi
0x140014965  push    r14
0x140014967  push    r15
0x140014969  sub     rsp, 28h
0x14001496d  mov     rbp, r8
0x140014970  mov     r14d, edx
0x140014973  mov     rdi, rcx
0x140014976  mov     eax, [rcx]
0x140014978  test    eax, eax
0x14001497a  jz      loc_140014B0B
0x140014980  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140014987  jnz     loc_140014B0B
0x14001498d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140014994  test    rax, rax
0x140014997  jz      short loc_1400149A6
0x140014999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001499e  test    al, al
0x1400149a0  jnz     loc_140014B0B
0x1400149a6  lea     rsi, [rdi+8]
0x1400149aa  mov     rcx, rsi; SRWLock
0x1400149ad  call    cs:__imp_AcquireSRWLockExclusive
0x1400149b3  mov     eax, [rdi]
0x1400149b5  test    eax, eax
0x1400149b7  jz      loc_140014AFC
0x1400149bd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400149c4  jnz     loc_140014AFC
0x1400149ca  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400149d1  test    rax, rax
0x1400149d4  jz      short loc_1400149E3
0x1400149d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400149db  test    al, al
0x1400149dd  jnz     loc_140014AFC
0x1400149e3  xor     r15d, r15d
0x1400149e6  lea     edx, [r15+10h]; unsigned __int64
0x1400149ea  lea     rcx, [rdi+20h]; this
0x1400149ee  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400149f3  test    al, al
0x1400149f5  jz      short loc_140014A4F
0x1400149f7  mov     rcx, [rdi+28h]; void *
0x1400149fb  mov     rax, [rdi+30h]
0x1400149ff  sub     rax, rcx
0x140014a02  cmp     rcx, [rdi+30h]
0x140014a06  sbb     r8, r8
0x140014a09  and     r8, rax; Size
0x140014a0c  test    rcx, rcx
0x140014a0f  jnz     short loc_140014A1F
0x140014a11  call    cs:__imp__o__errno
0x140014a17  mov     dword ptr [rax], 16h
0x140014a1d  jmp     short loc_140014A45
0x140014a1f  cmp     r8, 10h
0x140014a23  jb      short loc_140014A32
0x140014a25  mov     [rcx], r14d
0x140014a28  mov     [rcx+4], r15d
0x140014a2c  mov     [rcx+8], rbp
0x140014a30  jmp     short loc_140014A4A
0x140014a32  xor     edx, edx; Val
0x140014a34  call    memset_0
0x140014a39  call    cs:__imp__o__errno
0x140014a3f  mov     dword ptr [rax], 22h ; '"'
0x140014a45  call    _invalid_parameter_noinfo
0x140014a4a  add     qword ptr [rdi+28h], 10h
0x140014a4f  cmp     [rdi+18h], r15b
0x140014a53  jnz     loc_140014AFC
0x140014a59  cmp     [rdi+10h], r15
0x140014a5d  jnz     short loc_140014ACC
0x140014a5f  call    cs:__imp_GetLastError
0x140014a65  mov     r14d, eax
0x140014a68  xor     r8d, r8d; pcbe
0x140014a6b  mov     rdx, rdi; pv
0x140014a6e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140014a75  call    cs:__imp_CreateThreadpoolTimer
0x140014a7b  mov     r15, rax
0x140014a7e  mov     rbp, [rdi+10h]
0x140014a82  test    rbp, rbp
0x140014a85  jz      short loc_140014ABF
0x140014a87  call    cs:__imp_GetLastError
0x140014a8d  mov     ebx, eax
0x140014a8f  xor     r9d, r9d; msWindowLength
0x140014a92  xor     r8d, r8d; msPeriod
0x140014a95  xor     edx, edx; pftDueTime
0x140014a97  mov     rcx, rbp; pti
0x140014a9a  call    cs:__imp_SetThreadpoolTimer
0x140014aa0  mov     edx, 1; fCancelPendingCallbacks
0x140014aa5  mov     rcx, rbp; pti
0x140014aa8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140014aae  mov     rcx, rbp; pti
0x140014ab1  call    cs:__imp_CloseThreadpoolTimer
0x140014ab7  mov     ecx, ebx; dwErrCode
0x140014ab9  call    cs:__imp_SetLastError
0x140014abf  mov     [rdi+10h], r15
0x140014ac3  mov     ecx, r14d; dwErrCode
0x140014ac6  call    cs:__imp_SetLastError
0x140014acc  mov     rcx, [rdi+10h]; pti
0x140014ad0  test    rcx, rcx
0x140014ad3  jz      short loc_140014AFC
0x140014ad5  mov     rax, 0FFFFFFFF4D2FA200h
0x140014adf  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x140014ae4  mov     r9d, 124F8h; msWindowLength
0x140014aea  xor     r8d, r8d; msPeriod
0x140014aed  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x140014af2  call    cs:__imp_SetThreadpoolTimer
0x140014af8  mov     byte ptr [rdi+18h], 1
0x140014afc  test    rsi, rsi
0x140014aff  jz      short loc_140014B0B
0x140014b01  mov     rcx, rsi; SRWLock
0x140014b04  call    cs:__imp_ReleaseSRWLockExclusive
0x140014b0a  nop
0x140014b0b  add     rsp, 28h
0x140014b0f  pop     r15
0x140014b11  pop     r14
0x140014b13  pop     rdi
0x140014b14  pop     rsi
0x140014b15  pop     rbp
0x140014b16  pop     rbx
0x140014b17  retn
```
