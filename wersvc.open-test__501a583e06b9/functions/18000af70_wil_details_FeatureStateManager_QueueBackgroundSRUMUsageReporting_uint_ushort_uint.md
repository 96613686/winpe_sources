# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000af70`
- end: `0x18000b10b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011010`

## callees

- `0x18000355e`
- `0x1800035e8`
- `0x18000af70`
- `0x18001171c`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b007`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b031`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b007`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000afc0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000afc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b0a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b0a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b0aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b0aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b06e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b06e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b093`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b093`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0e5`

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
0x18000af70  push    rbx
0x18000af72  push    rbp
0x18000af73  push    rsi
0x18000af74  push    rdi
0x18000af75  push    r14
0x18000af77  push    r15
0x18000af79  sub     rsp, 38h
0x18000af7d  mov     ebp, r9d
0x18000af80  movzx   ebx, r8w
0x18000af84  mov     r14d, edx
0x18000af87  mov     rdi, rcx
0x18000af8a  cmp     byte ptr [rcx], 0
0x18000af8d  jz      loc_18000B0FE
0x18000af93  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000af9a  jnz     loc_18000B0FE
0x18000afa0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000afa7  test    rax, rax
0x18000afaa  jz      short loc_18000AFB9
0x18000afac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb1  test    al, al
0x18000afb3  jnz     loc_18000B0FE
0x18000afb9  lea     rsi, [rdi+28h]
0x18000afbd  mov     rcx, rsi; SRWLock
0x18000afc0  call    cs:__imp_AcquireSRWLockExclusive
0x18000afc6  xor     eax, eax
0x18000afc8  mov     word ptr [rsp+68h+var_48+6], ax
0x18000afcd  mov     dword ptr [rsp+68h+var_48], r14d
0x18000afd2  mov     word ptr [rsp+68h+var_48+4], bx
0x18000afd7  lea     rbx, [rdi+0E8h]
0x18000afde  lea     edx, [rax+0Ch]; unsigned __int64
0x18000afe1  mov     rcx, rbx; this
0x18000afe4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000afe9  test    al, al
0x18000afeb  jz      short loc_18000B047
0x18000afed  mov     rcx, [rbx+8]; void *
0x18000aff1  mov     rax, [rbx+10h]
0x18000aff5  sub     rax, rcx
0x18000aff8  cmp     rcx, [rbx+10h]
0x18000affc  sbb     r8, r8
0x18000afff  and     r8, rax; Size
0x18000b002  test    rcx, rcx
0x18000b005  jnz     short loc_18000B015
0x18000b007  call    cs:__imp__o__errno
0x18000b00d  mov     dword ptr [rax], 16h
0x18000b013  jmp     short loc_18000B03D
0x18000b015  cmp     r8, 0Ch
0x18000b019  jb      short loc_18000B02A
0x18000b01b  movsd   xmm0, [rsp+68h+var_48]
0x18000b021  movsd   qword ptr [rcx], xmm0
0x18000b025  mov     [rcx+8], ebp
0x18000b028  jmp     short loc_18000B042
0x18000b02a  xor     edx, edx; Val
0x18000b02c  call    memset_0
0x18000b031  call    cs:__imp__o__errno
0x18000b037  mov     dword ptr [rax], 22h ; '"'
0x18000b03d  call    _invalid_parameter_noinfo
0x18000b042  add     qword ptr [rbx+8], 0Ch
0x18000b047  cmp     byte ptr [rdi+40h], 0
0x18000b04b  jnz     loc_18000B0EF
0x18000b051  cmp     qword ptr [rdi+38h], 0
0x18000b056  jnz     short loc_18000B0C5
0x18000b058  call    cs:__imp_GetLastError
0x18000b05e  mov     r14d, eax
0x18000b061  xor     r8d, r8d; pcbe
0x18000b064  mov     rdx, rdi; pv
0x18000b067  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b06e  call    cs:__imp_CreateThreadpoolTimer
0x18000b074  mov     r15, rax
0x18000b077  mov     rbp, [rdi+38h]
0x18000b07b  test    rbp, rbp
0x18000b07e  jz      short loc_18000B0B8
0x18000b080  call    cs:__imp_GetLastError
0x18000b086  mov     ebx, eax
0x18000b088  xor     r9d, r9d; msWindowLength
0x18000b08b  xor     r8d, r8d; msPeriod
0x18000b08e  xor     edx, edx; pftDueTime
0x18000b090  mov     rcx, rbp; pti
0x18000b093  call    cs:__imp_SetThreadpoolTimer
0x18000b099  mov     edx, 1; fCancelPendingCallbacks
0x18000b09e  mov     rcx, rbp; pti
0x18000b0a1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b0a7  mov     rcx, rbp; pti
0x18000b0aa  call    cs:__imp_CloseThreadpoolTimer
0x18000b0b0  mov     ecx, ebx; dwErrCode
0x18000b0b2  call    cs:__imp_SetLastError
0x18000b0b8  mov     [rdi+38h], r15
0x18000b0bc  mov     ecx, r14d; dwErrCode
0x18000b0bf  call    cs:__imp_SetLastError
0x18000b0c5  mov     rcx, [rdi+38h]; pti
0x18000b0c9  test    rcx, rcx
0x18000b0cc  jz      short loc_18000B0EF
0x18000b0ce  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000b0d7  mov     r9d, 4E2h; msWindowLength
0x18000b0dd  xor     r8d, r8d; msPeriod
0x18000b0e0  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000b0e5  call    cs:__imp_SetThreadpoolTimer
0x18000b0eb  mov     byte ptr [rdi+40h], 1
0x18000b0ef  test    rsi, rsi
0x18000b0f2  jz      short loc_18000B0FE
0x18000b0f4  mov     rcx, rsi; SRWLock
0x18000b0f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b0fd  nop
0x18000b0fe  add     rsp, 38h
0x18000b102  pop     r15
0x18000b104  pop     r14
0x18000b106  pop     rdi
0x18000b107  pop     rsi
0x18000b108  pop     rbp
0x18000b109  pop     rbx
0x18000b10a  retn
```
