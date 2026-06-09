# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000a158`
- end: `0x14000a2f2`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000be50`

## callees

- `0x1400027fe`
- `0x1400028b8`
- `0x14000a158`
- `0x14000c354`
- `0x140016010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000a29a`
- `KERNEL32!SetLastError` at `0x14000a2a7`
- `KERNEL32!SetLastError` at `0x14000a29a`
- `KERNEL32!SetLastError` at `0x14000a2a7`
- `KERNEL32!GetLastError` at `0x14000a240`
- `KERNEL32!GetLastError` at `0x14000a268`
- `KERNEL32!GetLastError` at `0x14000a240`
- `KERNEL32!GetLastError` at `0x14000a268`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a1a8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a1a8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a2df`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a2df`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a27b`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a2cd`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a27b`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a2cd`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000a292`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000a292`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a289`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a289`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000a256`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000a256`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a1ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a219`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a1ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a219`

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
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v16; // rbp
  PTP_TIMER v17; // r15
  DWORD v18; // ebx
  struct _TP_TIMER *v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  HIDWORD(v20) = a3;
  LODWORD(v20) = a2;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v20;
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
      v17 = ThreadpoolTimer;
      if ( v16 )
      {
        v18 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v18);
      }
      pv[7].Ptr = v17;
      SetLastError(LastError);
    }
    v19 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v19 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v19, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x14000a158  push    rbx
0x14000a15a  push    rbp
0x14000a15b  push    rsi
0x14000a15c  push    rdi
0x14000a15d  push    r14
0x14000a15f  push    r15
0x14000a161  sub     rsp, 38h
0x14000a165  cmp     byte ptr [rcx], 0
0x14000a168  mov     ebp, r9d
0x14000a16b  movzx   ebx, r8w
0x14000a16f  mov     r14d, edx
0x14000a172  mov     rdi, rcx
0x14000a175  jz      loc_14000A2E5
0x14000a17b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000a182  jnz     loc_14000A2E5
0x14000a188  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a18f  test    rax, rax
0x14000a192  jz      short loc_14000A1A1
0x14000a194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a199  test    al, al
0x14000a19b  jnz     loc_14000A2E5
0x14000a1a1  lea     rsi, [rdi+28h]
0x14000a1a5  mov     rcx, rsi; SRWLock
0x14000a1a8  call    cs:__imp_AcquireSRWLockExclusive
0x14000a1ae  xor     eax, eax
0x14000a1b0  mov     word ptr [rsp+68h+var_48+4], bx
0x14000a1b5  lea     rbx, [rdi+0E8h]
0x14000a1bc  mov     word ptr [rsp+68h+var_48+6], ax
0x14000a1c1  mov     rcx, rbx; this
0x14000a1c4  mov     dword ptr [rsp+68h+var_48], r14d
0x14000a1c9  lea     edx, [rax+0Ch]; unsigned __int64
0x14000a1cc  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000a1d1  test    al, al
0x14000a1d3  jz      short loc_14000A22F
0x14000a1d5  mov     rcx, [rbx+8]; void *
0x14000a1d9  mov     rax, [rbx+10h]
0x14000a1dd  sub     rax, rcx
0x14000a1e0  cmp     rcx, [rbx+10h]
0x14000a1e4  sbb     r8, r8
0x14000a1e7  and     r8, rax; Size
0x14000a1ea  test    rcx, rcx
0x14000a1ed  jnz     short loc_14000A1FD
0x14000a1ef  call    cs:__imp__o__errno
0x14000a1f5  mov     dword ptr [rax], 16h
0x14000a1fb  jmp     short loc_14000A225
0x14000a1fd  cmp     r8, 0Ch
0x14000a201  jb      short loc_14000A212
0x14000a203  movsd   xmm0, [rsp+68h+var_48]
0x14000a209  movsd   qword ptr [rcx], xmm0
0x14000a20d  mov     [rcx+8], ebp
0x14000a210  jmp     short loc_14000A22A
0x14000a212  xor     edx, edx; Val
0x14000a214  call    memset_0
0x14000a219  call    cs:__imp__o__errno
0x14000a21f  mov     dword ptr [rax], 22h ; '"'
0x14000a225  call    _invalid_parameter_noinfo
0x14000a22a  add     qword ptr [rbx+8], 0Ch
0x14000a22f  cmp     byte ptr [rdi+40h], 0
0x14000a233  jnz     loc_14000A2D7
0x14000a239  cmp     qword ptr [rdi+38h], 0
0x14000a23e  jnz     short loc_14000A2AD
0x14000a240  call    cs:__imp_GetLastError
0x14000a246  xor     r8d, r8d; pcbe
0x14000a249  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000a250  mov     rdx, rdi; pv
0x14000a253  mov     r14d, eax
0x14000a256  call    cs:__imp_CreateThreadpoolTimer
0x14000a25c  mov     rbp, [rdi+38h]
0x14000a260  mov     r15, rax
0x14000a263  test    rbp, rbp
0x14000a266  jz      short loc_14000A2A0
0x14000a268  call    cs:__imp_GetLastError
0x14000a26e  xor     r9d, r9d; msWindowLength
0x14000a271  xor     r8d, r8d; msPeriod
0x14000a274  xor     edx, edx; pftDueTime
0x14000a276  mov     rcx, rbp; pti
0x14000a279  mov     ebx, eax
0x14000a27b  call    cs:__imp_SetThreadpoolTimer
0x14000a281  mov     edx, 1; fCancelPendingCallbacks
0x14000a286  mov     rcx, rbp; pti
0x14000a289  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000a28f  mov     rcx, rbp; pti
0x14000a292  call    cs:__imp_CloseThreadpoolTimer
0x14000a298  mov     ecx, ebx; dwErrCode
0x14000a29a  call    cs:__imp_SetLastError
0x14000a2a0  mov     ecx, r14d; dwErrCode
0x14000a2a3  mov     [rdi+38h], r15
0x14000a2a7  call    cs:__imp_SetLastError
0x14000a2ad  mov     rcx, [rdi+38h]; pti
0x14000a2b1  test    rcx, rcx
0x14000a2b4  jz      short loc_14000A2D7
0x14000a2b6  mov     r9d, 4E2h; msWindowLength
0x14000a2bc  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000a2c5  xor     r8d, r8d; msPeriod
0x14000a2c8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000a2cd  call    cs:__imp_SetThreadpoolTimer
0x14000a2d3  mov     byte ptr [rdi+40h], 1
0x14000a2d7  test    rsi, rsi
0x14000a2da  jz      short loc_14000A2E5
0x14000a2dc  mov     rcx, rsi; SRWLock
0x14000a2df  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a2e5  add     rsp, 38h
0x14000a2e9  pop     r15
0x14000a2eb  pop     r14
0x14000a2ed  pop     rdi
0x14000a2ee  pop     rsi
0x14000a2ef  pop     rbp
0x14000a2f0  pop     rbx
0x14000a2f1  retn
```
