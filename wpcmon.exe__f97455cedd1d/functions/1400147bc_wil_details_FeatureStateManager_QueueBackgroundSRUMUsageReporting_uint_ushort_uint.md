# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400147bc`
- end: `0x140014957`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400190b0`

## callees

- `0x14000624e`
- `0x140006314`
- `0x1400147bc`
- `0x14001cc14`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1400148ba`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400148ba`
- `KERNEL32!SetThreadpoolTimer` at `0x1400148df`
- `KERNEL32!SetThreadpoolTimer` at `0x140014931`
- `KERNEL32!SetThreadpoolTimer` at `0x1400148df`
- `KERNEL32!SetThreadpoolTimer` at `0x140014931`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001480c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001480c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400148f6`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400148f6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140014943`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140014943`
- `KERNEL32!GetLastError` at `0x1400148a4`
- `KERNEL32!GetLastError` at `0x1400148cc`
- `KERNEL32!GetLastError` at `0x1400148a4`
- `KERNEL32!GetLastError` at `0x1400148cc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400148ed`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400148ed`
- `KERNEL32!SetLastError` at `0x1400148fe`
- `KERNEL32!SetLastError` at `0x14001490b`
- `KERNEL32!SetLastError` at `0x1400148fe`
- `KERNEL32!SetLastError` at `0x14001490b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014853`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001487d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014853`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001487d`

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
0x1400147bc  push    rbx
0x1400147be  push    rbp
0x1400147bf  push    rsi
0x1400147c0  push    rdi
0x1400147c1  push    r14
0x1400147c3  push    r15
0x1400147c5  sub     rsp, 38h
0x1400147c9  mov     ebp, r9d
0x1400147cc  movzx   ebx, r8w
0x1400147d0  mov     r14d, edx
0x1400147d3  mov     rdi, rcx
0x1400147d6  cmp     byte ptr [rcx], 0
0x1400147d9  jz      loc_14001494A
0x1400147df  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400147e6  jnz     loc_14001494A
0x1400147ec  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400147f3  test    rax, rax
0x1400147f6  jz      short loc_140014805
0x1400147f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400147fd  test    al, al
0x1400147ff  jnz     loc_14001494A
0x140014805  lea     rsi, [rdi+28h]
0x140014809  mov     rcx, rsi; SRWLock
0x14001480c  call    cs:__imp_AcquireSRWLockExclusive
0x140014812  xor     eax, eax
0x140014814  mov     word ptr [rsp+68h+var_48+6], ax
0x140014819  mov     dword ptr [rsp+68h+var_48], r14d
0x14001481e  mov     word ptr [rsp+68h+var_48+4], bx
0x140014823  lea     rbx, [rdi+0E8h]
0x14001482a  lea     edx, [rax+0Ch]; unsigned __int64
0x14001482d  mov     rcx, rbx; this
0x140014830  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140014835  test    al, al
0x140014837  jz      short loc_140014893
0x140014839  mov     rcx, [rbx+8]; void *
0x14001483d  mov     rax, [rbx+10h]
0x140014841  sub     rax, rcx
0x140014844  cmp     rcx, [rbx+10h]
0x140014848  sbb     r8, r8
0x14001484b  and     r8, rax; Size
0x14001484e  test    rcx, rcx
0x140014851  jnz     short loc_140014861
0x140014853  call    cs:__imp__o__errno
0x140014859  mov     dword ptr [rax], 16h
0x14001485f  jmp     short loc_140014889
0x140014861  cmp     r8, 0Ch
0x140014865  jb      short loc_140014876
0x140014867  movsd   xmm0, [rsp+68h+var_48]
0x14001486d  movsd   qword ptr [rcx], xmm0
0x140014871  mov     [rcx+8], ebp
0x140014874  jmp     short loc_14001488E
0x140014876  xor     edx, edx; Val
0x140014878  call    memset_0
0x14001487d  call    cs:__imp__o__errno
0x140014883  mov     dword ptr [rax], 22h ; '"'
0x140014889  call    _invalid_parameter_noinfo
0x14001488e  add     qword ptr [rbx+8], 0Ch
0x140014893  cmp     byte ptr [rdi+40h], 0
0x140014897  jnz     loc_14001493B
0x14001489d  cmp     qword ptr [rdi+38h], 0
0x1400148a2  jnz     short loc_140014911
0x1400148a4  call    cs:__imp_GetLastError
0x1400148aa  mov     r14d, eax
0x1400148ad  xor     r8d, r8d; pcbe
0x1400148b0  mov     rdx, rdi; pv
0x1400148b3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400148ba  call    cs:__imp_CreateThreadpoolTimer
0x1400148c0  mov     r15, rax
0x1400148c3  mov     rbp, [rdi+38h]
0x1400148c7  test    rbp, rbp
0x1400148ca  jz      short loc_140014904
0x1400148cc  call    cs:__imp_GetLastError
0x1400148d2  mov     ebx, eax
0x1400148d4  xor     r9d, r9d; msWindowLength
0x1400148d7  xor     r8d, r8d; msPeriod
0x1400148da  xor     edx, edx; pftDueTime
0x1400148dc  mov     rcx, rbp; pti
0x1400148df  call    cs:__imp_SetThreadpoolTimer
0x1400148e5  mov     edx, 1; fCancelPendingCallbacks
0x1400148ea  mov     rcx, rbp; pti
0x1400148ed  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400148f3  mov     rcx, rbp; pti
0x1400148f6  call    cs:__imp_CloseThreadpoolTimer
0x1400148fc  mov     ecx, ebx; dwErrCode
0x1400148fe  call    cs:__imp_SetLastError
0x140014904  mov     [rdi+38h], r15
0x140014908  mov     ecx, r14d; dwErrCode
0x14001490b  call    cs:__imp_SetLastError
0x140014911  mov     rcx, [rdi+38h]; pti
0x140014915  test    rcx, rcx
0x140014918  jz      short loc_14001493B
0x14001491a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140014923  mov     r9d, 4E2h; msWindowLength
0x140014929  xor     r8d, r8d; msPeriod
0x14001492c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140014931  call    cs:__imp_SetThreadpoolTimer
0x140014937  mov     byte ptr [rdi+40h], 1
0x14001493b  test    rsi, rsi
0x14001493e  jz      short loc_14001494A
0x140014940  mov     rcx, rsi; SRWLock
0x140014943  call    cs:__imp_ReleaseSRWLockExclusive
0x140014949  nop
0x14001494a  add     rsp, 38h
0x14001494e  pop     r15
0x140014950  pop     r14
0x140014952  pop     rdi
0x140014953  pop     rsi
0x140014954  pop     rbp
0x140014955  pop     rbx
0x140014956  retn
```
