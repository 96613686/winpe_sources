# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008aac`
- end: `0x180008c47`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000aeb0`

## callees

- `0x18000218a`
- `0x1800021f4`
- `0x180008aac`
- `0x18000b74c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008b43`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008b6d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008b43`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008b6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bfb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bbc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008afc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008afc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c33`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008be6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008be6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008bdd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008bdd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bcf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008c21`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bcf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008c21`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008baa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008baa`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v16; // rbp
  DWORD v17; // ebx
  struct _TP_TIMER *v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v19) = a2;
  HIDWORD(v19) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v19;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11, v13) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v16 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v16 )
      {
        v17 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v17);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v18 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v18 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v18, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180008aac  push    rbx
0x180008aae  push    rbp
0x180008aaf  push    rsi
0x180008ab0  push    rdi
0x180008ab1  push    r14
0x180008ab3  push    r15
0x180008ab5  sub     rsp, 38h
0x180008ab9  mov     ebp, r9d
0x180008abc  movzx   ebx, r8w
0x180008ac0  mov     r14d, edx
0x180008ac3  mov     rdi, rcx
0x180008ac6  cmp     byte ptr [rcx], 0
0x180008ac9  jz      loc_180008C3A
0x180008acf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008ad6  jnz     loc_180008C3A
0x180008adc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008ae3  test    rax, rax
0x180008ae6  jz      short loc_180008AF5
0x180008ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aed  test    al, al
0x180008aef  jnz     loc_180008C3A
0x180008af5  lea     rsi, [rdi+28h]
0x180008af9  mov     rcx, rsi; SRWLock
0x180008afc  call    cs:__imp_AcquireSRWLockExclusive
0x180008b02  xor     eax, eax
0x180008b04  mov     word ptr [rsp+68h+var_48+6], ax
0x180008b09  mov     dword ptr [rsp+68h+var_48], r14d
0x180008b0e  mov     word ptr [rsp+68h+var_48+4], bx
0x180008b13  lea     rbx, [rdi+0E8h]
0x180008b1a  lea     edx, [rax+0Ch]; unsigned __int64
0x180008b1d  mov     rcx, rbx; this
0x180008b20  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008b25  test    al, al
0x180008b27  jz      short loc_180008B83
0x180008b29  mov     rcx, [rbx+8]; void *
0x180008b2d  mov     rax, [rbx+10h]
0x180008b31  sub     rax, rcx
0x180008b34  cmp     rcx, [rbx+10h]
0x180008b38  sbb     r8, r8
0x180008b3b  and     r8, rax; Size
0x180008b3e  test    rcx, rcx
0x180008b41  jnz     short loc_180008B51
0x180008b43  call    cs:__imp__o__errno
0x180008b49  mov     dword ptr [rax], 16h
0x180008b4f  jmp     short loc_180008B79
0x180008b51  cmp     r8, 0Ch
0x180008b55  jb      short loc_180008B66
0x180008b57  movsd   xmm0, [rsp+68h+var_48]
0x180008b5d  movsd   qword ptr [rcx], xmm0
0x180008b61  mov     [rcx+8], ebp
0x180008b64  jmp     short loc_180008B7E
0x180008b66  xor     edx, edx; Val
0x180008b68  call    memset_0
0x180008b6d  call    cs:__imp__o__errno
0x180008b73  mov     dword ptr [rax], 22h ; '"'
0x180008b79  call    _invalid_parameter_noinfo
0x180008b7e  add     qword ptr [rbx+8], 0Ch
0x180008b83  cmp     byte ptr [rdi+40h], 0
0x180008b87  jnz     loc_180008C2B
0x180008b8d  cmp     qword ptr [rdi+38h], 0
0x180008b92  jnz     short loc_180008C01
0x180008b94  call    cs:__imp_GetLastError
0x180008b9a  mov     r14d, eax
0x180008b9d  xor     r8d, r8d; pcbe
0x180008ba0  mov     rdx, rdi; pv
0x180008ba3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008baa  call    cs:__imp_CreateThreadpoolTimer
0x180008bb0  mov     r15, rax
0x180008bb3  mov     rbp, [rdi+38h]
0x180008bb7  test    rbp, rbp
0x180008bba  jz      short loc_180008BF4
0x180008bbc  call    cs:__imp_GetLastError
0x180008bc2  mov     ebx, eax
0x180008bc4  xor     r9d, r9d; msWindowLength
0x180008bc7  xor     r8d, r8d; msPeriod
0x180008bca  xor     edx, edx; pftDueTime
0x180008bcc  mov     rcx, rbp; pti
0x180008bcf  call    cs:__imp_SetThreadpoolTimer
0x180008bd5  mov     edx, 1; fCancelPendingCallbacks
0x180008bda  mov     rcx, rbp; pti
0x180008bdd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008be3  mov     rcx, rbp; pti
0x180008be6  call    cs:__imp_CloseThreadpoolTimer
0x180008bec  mov     ecx, ebx; dwErrCode
0x180008bee  call    cs:__imp_SetLastError
0x180008bf4  mov     [rdi+38h], r15
0x180008bf8  mov     ecx, r14d; dwErrCode
0x180008bfb  call    cs:__imp_SetLastError
0x180008c01  mov     rcx, [rdi+38h]; pti
0x180008c05  test    rcx, rcx
0x180008c08  jz      short loc_180008C2B
0x180008c0a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008c13  mov     r9d, 4E2h; msWindowLength
0x180008c19  xor     r8d, r8d; msPeriod
0x180008c1c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180008c21  call    cs:__imp_SetThreadpoolTimer
0x180008c27  mov     byte ptr [rdi+40h], 1
0x180008c2b  test    rsi, rsi
0x180008c2e  jz      short loc_180008C3A
0x180008c30  mov     rcx, rsi; SRWLock
0x180008c33  call    cs:__imp_ReleaseSRWLockExclusive
0x180008c39  nop
0x180008c3a  add     rsp, 38h
0x180008c3e  pop     r15
0x180008c40  pop     r14
0x180008c42  pop     rdi
0x180008c43  pop     rsi
0x180008c44  pop     rbp
0x180008c45  pop     rbx
0x180008c46  retn
```
