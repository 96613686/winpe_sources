# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800369c8`
- end: `0x180036b63`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800391b0`

## callees

- `0x1800053be`
- `0x1800054e4`
- `0x1800369c8`
- `0x18003983c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180036a5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180036a89`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180036a5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180036a89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036a18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036a18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036b4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036b4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036b0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036b17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036b0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ad8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036af9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036af9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180036b02`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180036b02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036aeb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036b3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036aeb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036b3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180036ac6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180036ac6`

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
0x1800369c8  push    rbx
0x1800369ca  push    rbp
0x1800369cb  push    rsi
0x1800369cc  push    rdi
0x1800369cd  push    r14
0x1800369cf  push    r15
0x1800369d1  sub     rsp, 38h
0x1800369d5  mov     ebp, r9d
0x1800369d8  movzx   ebx, r8w
0x1800369dc  mov     r14d, edx
0x1800369df  mov     rdi, rcx
0x1800369e2  cmp     byte ptr [rcx], 0
0x1800369e5  jz      loc_180036B56
0x1800369eb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800369f2  jnz     loc_180036B56
0x1800369f8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800369ff  test    rax, rax
0x180036a02  jz      short loc_180036A11
0x180036a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a09  test    al, al
0x180036a0b  jnz     loc_180036B56
0x180036a11  lea     rsi, [rdi+28h]
0x180036a15  mov     rcx, rsi; SRWLock
0x180036a18  call    cs:__imp_AcquireSRWLockExclusive
0x180036a1e  xor     eax, eax
0x180036a20  mov     word ptr [rsp+68h+var_48+6], ax
0x180036a25  mov     dword ptr [rsp+68h+var_48], r14d
0x180036a2a  mov     word ptr [rsp+68h+var_48+4], bx
0x180036a2f  lea     rbx, [rdi+0E8h]
0x180036a36  lea     edx, [rax+0Ch]; unsigned __int64
0x180036a39  mov     rcx, rbx; this
0x180036a3c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180036a41  test    al, al
0x180036a43  jz      short loc_180036A9F
0x180036a45  mov     rcx, [rbx+8]; void *
0x180036a49  mov     rax, [rbx+10h]
0x180036a4d  sub     rax, rcx
0x180036a50  cmp     rcx, [rbx+10h]
0x180036a54  sbb     r8, r8
0x180036a57  and     r8, rax; Size
0x180036a5a  test    rcx, rcx
0x180036a5d  jnz     short loc_180036A6D
0x180036a5f  call    cs:__imp__o__errno
0x180036a65  mov     dword ptr [rax], 16h
0x180036a6b  jmp     short loc_180036A95
0x180036a6d  cmp     r8, 0Ch
0x180036a71  jb      short loc_180036A82
0x180036a73  movsd   xmm0, [rsp+68h+var_48]
0x180036a79  movsd   qword ptr [rcx], xmm0
0x180036a7d  mov     [rcx+8], ebp
0x180036a80  jmp     short loc_180036A9A
0x180036a82  xor     edx, edx; Val
0x180036a84  call    memset_0
0x180036a89  call    cs:__imp__o__errno
0x180036a8f  mov     dword ptr [rax], 22h ; '"'
0x180036a95  call    _invalid_parameter_noinfo
0x180036a9a  add     qword ptr [rbx+8], 0Ch
0x180036a9f  cmp     byte ptr [rdi+40h], 0
0x180036aa3  jnz     loc_180036B47
0x180036aa9  cmp     qword ptr [rdi+38h], 0
0x180036aae  jnz     short loc_180036B1D
0x180036ab0  call    cs:__imp_GetLastError
0x180036ab6  mov     r14d, eax
0x180036ab9  xor     r8d, r8d; pcbe
0x180036abc  mov     rdx, rdi; pv
0x180036abf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180036ac6  call    cs:__imp_CreateThreadpoolTimer
0x180036acc  mov     r15, rax
0x180036acf  mov     rbp, [rdi+38h]
0x180036ad3  test    rbp, rbp
0x180036ad6  jz      short loc_180036B10
0x180036ad8  call    cs:__imp_GetLastError
0x180036ade  mov     ebx, eax
0x180036ae0  xor     r9d, r9d; msWindowLength
0x180036ae3  xor     r8d, r8d; msPeriod
0x180036ae6  xor     edx, edx; pftDueTime
0x180036ae8  mov     rcx, rbp; pti
0x180036aeb  call    cs:__imp_SetThreadpoolTimer
0x180036af1  mov     edx, 1; fCancelPendingCallbacks
0x180036af6  mov     rcx, rbp; pti
0x180036af9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180036aff  mov     rcx, rbp; pti
0x180036b02  call    cs:__imp_CloseThreadpoolTimer
0x180036b08  mov     ecx, ebx; dwErrCode
0x180036b0a  call    cs:__imp_SetLastError
0x180036b10  mov     [rdi+38h], r15
0x180036b14  mov     ecx, r14d; dwErrCode
0x180036b17  call    cs:__imp_SetLastError
0x180036b1d  mov     rcx, [rdi+38h]; pti
0x180036b21  test    rcx, rcx
0x180036b24  jz      short loc_180036B47
0x180036b26  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180036b2f  mov     r9d, 4E2h; msWindowLength
0x180036b35  xor     r8d, r8d; msPeriod
0x180036b38  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180036b3d  call    cs:__imp_SetThreadpoolTimer
0x180036b43  mov     byte ptr [rdi+40h], 1
0x180036b47  test    rsi, rsi
0x180036b4a  jz      short loc_180036B56
0x180036b4c  mov     rcx, rsi; SRWLock
0x180036b4f  call    cs:__imp_ReleaseSRWLockExclusive
0x180036b55  nop
0x180036b56  add     rsp, 38h
0x180036b5a  pop     r15
0x180036b5c  pop     r14
0x180036b5e  pop     rdi
0x180036b5f  pop     rsi
0x180036b60  pop     rbp
0x180036b61  pop     rbx
0x180036b62  retn
```
