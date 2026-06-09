# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007e68`
- end: `0x180008003`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000bf70`

## callees

- `0x180002846`
- `0x1800028b4`
- `0x180007e68`
- `0x18000c82c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007eff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007f29`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007eff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007f29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007eb8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007eb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007faa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007fb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007faa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007fa2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007fa2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007f99`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007f99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007fdd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007fdd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007f66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007f66`

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
0x180007e68  push    rbx
0x180007e6a  push    rbp
0x180007e6b  push    rsi
0x180007e6c  push    rdi
0x180007e6d  push    r14
0x180007e6f  push    r15
0x180007e71  sub     rsp, 38h
0x180007e75  mov     ebp, r9d
0x180007e78  movzx   ebx, r8w
0x180007e7c  mov     r14d, edx
0x180007e7f  mov     rdi, rcx
0x180007e82  cmp     byte ptr [rcx], 0
0x180007e85  jz      loc_180007FF6
0x180007e8b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007e92  jnz     loc_180007FF6
0x180007e98  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007e9f  test    rax, rax
0x180007ea2  jz      short loc_180007EB1
0x180007ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea9  test    al, al
0x180007eab  jnz     loc_180007FF6
0x180007eb1  lea     rsi, [rdi+28h]
0x180007eb5  mov     rcx, rsi; SRWLock
0x180007eb8  call    cs:__imp_AcquireSRWLockExclusive
0x180007ebe  xor     eax, eax
0x180007ec0  mov     word ptr [rsp+68h+var_48+6], ax
0x180007ec5  mov     dword ptr [rsp+68h+var_48], r14d
0x180007eca  mov     word ptr [rsp+68h+var_48+4], bx
0x180007ecf  lea     rbx, [rdi+0E8h]
0x180007ed6  lea     edx, [rax+0Ch]; unsigned __int64
0x180007ed9  mov     rcx, rbx; this
0x180007edc  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007ee1  test    al, al
0x180007ee3  jz      short loc_180007F3F
0x180007ee5  mov     rcx, [rbx+8]; void *
0x180007ee9  mov     rax, [rbx+10h]
0x180007eed  sub     rax, rcx
0x180007ef0  cmp     rcx, [rbx+10h]
0x180007ef4  sbb     r8, r8
0x180007ef7  and     r8, rax; Size
0x180007efa  test    rcx, rcx
0x180007efd  jnz     short loc_180007F0D
0x180007eff  call    cs:__imp__o__errno
0x180007f05  mov     dword ptr [rax], 16h
0x180007f0b  jmp     short loc_180007F35
0x180007f0d  cmp     r8, 0Ch
0x180007f11  jb      short loc_180007F22
0x180007f13  movsd   xmm0, [rsp+68h+var_48]
0x180007f19  movsd   qword ptr [rcx], xmm0
0x180007f1d  mov     [rcx+8], ebp
0x180007f20  jmp     short loc_180007F3A
0x180007f22  xor     edx, edx; Val
0x180007f24  call    memset_0
0x180007f29  call    cs:__imp__o__errno
0x180007f2f  mov     dword ptr [rax], 22h ; '"'
0x180007f35  call    _invalid_parameter_noinfo
0x180007f3a  add     qword ptr [rbx+8], 0Ch
0x180007f3f  cmp     byte ptr [rdi+40h], 0
0x180007f43  jnz     loc_180007FE7
0x180007f49  cmp     qword ptr [rdi+38h], 0
0x180007f4e  jnz     short loc_180007FBD
0x180007f50  call    cs:__imp_GetLastError
0x180007f56  mov     r14d, eax
0x180007f59  xor     r8d, r8d; pcbe
0x180007f5c  mov     rdx, rdi; pv
0x180007f5f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007f66  call    cs:__imp_CreateThreadpoolTimer
0x180007f6c  mov     r15, rax
0x180007f6f  mov     rbp, [rdi+38h]
0x180007f73  test    rbp, rbp
0x180007f76  jz      short loc_180007FB0
0x180007f78  call    cs:__imp_GetLastError
0x180007f7e  mov     ebx, eax
0x180007f80  xor     r9d, r9d; msWindowLength
0x180007f83  xor     r8d, r8d; msPeriod
0x180007f86  xor     edx, edx; pftDueTime
0x180007f88  mov     rcx, rbp; pti
0x180007f8b  call    cs:__imp_SetThreadpoolTimer
0x180007f91  mov     edx, 1; fCancelPendingCallbacks
0x180007f96  mov     rcx, rbp; pti
0x180007f99  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007f9f  mov     rcx, rbp; pti
0x180007fa2  call    cs:__imp_CloseThreadpoolTimer
0x180007fa8  mov     ecx, ebx; dwErrCode
0x180007faa  call    cs:__imp_SetLastError
0x180007fb0  mov     [rdi+38h], r15
0x180007fb4  mov     ecx, r14d; dwErrCode
0x180007fb7  call    cs:__imp_SetLastError
0x180007fbd  mov     rcx, [rdi+38h]; pti
0x180007fc1  test    rcx, rcx
0x180007fc4  jz      short loc_180007FE7
0x180007fc6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180007fcf  mov     r9d, 4E2h; msWindowLength
0x180007fd5  xor     r8d, r8d; msPeriod
0x180007fd8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180007fdd  call    cs:__imp_SetThreadpoolTimer
0x180007fe3  mov     byte ptr [rdi+40h], 1
0x180007fe7  test    rsi, rsi
0x180007fea  jz      short loc_180007FF6
0x180007fec  mov     rcx, rsi; SRWLock
0x180007fef  call    cs:__imp_ReleaseSRWLockExclusive
0x180007ff5  nop
0x180007ff6  add     rsp, 38h
0x180007ffa  pop     r15
0x180007ffc  pop     r14
0x180007ffe  pop     rdi
0x180007fff  pop     rsi
0x180008000  pop     rbp
0x180008001  pop     rbx
0x180008002  retn
```
