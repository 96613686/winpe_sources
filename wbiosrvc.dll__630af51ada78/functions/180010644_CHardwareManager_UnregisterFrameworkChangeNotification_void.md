# CHardwareManager::UnregisterFrameworkChangeNotification(void *)

- ea: `0x180010644`
- end: `0x180010851`
- name: `?UnregisterFrameworkChangeNotification@CHardwareManager@@SAXPEAX@Z`
- size: `525`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001de40`
- `0x18001e644`

## callees

- `0x18000b760`
- `0x180010644`
- `0x180010bfc`
- `0x180011164`
- `0x1800119c4`
- `0x180020fe8`
- `0x18005dc5c`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010831`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010831`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010674`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010674`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010717`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010717`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010785`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010785`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800107d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800107f9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800107d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800107f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001073f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001073f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010803`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010803`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800107ad`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800107ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CHardwareManager::UnregisterFrameworkChangeNotification(unsigned __int64 a1)
{
  RTL_SRWLOCK *v2; // rsi
  __int64 *v3; // rdx
  __int64 *v4; // rcx
  __int64 *v5; // rdi
  __int64 *v6; // rax
  __int64 v7; // rax
  std::_Ref_count_base *v8; // r14
  struct CHardwareManager *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-69h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+38h] [rbp-61h] BYREF
  HANDLE hFile; // [rsp+40h] [rbp-59h] BYREF
  HANDLE *v15; // [rsp+48h] [rbp-51h]
  std::_Ref_count_base *v16; // [rsp+50h] [rbp-49h]
  PTP_TIMER pv; // [rsp+60h] [rbp-39h] BYREF
  char v18; // [rsp+68h] [rbp-31h]
  _BYTE v19[56]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+Fh]
  int Buffer; // [rsp+B0h] [rbp+17h] BYREF
  __int128 v22; // [rsp+B4h] [rbp+1Bh]

  v2 = (RTL_SRWLOCK *)((char *)CHardwareManager::Instance() + 8);
  AcquireSRWLockExclusive(v2);
  pftDueTime = (struct _FILETIME)v2;
  v3 = (__int64 *)*((_QWORD *)CHardwareManager::Instance() + 9);
  v4 = (__int64 *)v3[1];
  HIDWORD(v16) = 0;
  v5 = v3;
  if ( !*((_BYTE *)v4 + 25) )
  {
    do
    {
      if ( v4[4] >= a1 )
        v5 = v4;
      v6 = v4 + 2;
      if ( v4[4] >= a1 )
        v6 = v4;
      v4 = (__int64 *)*v6;
    }
    while ( !*(_BYTE *)(*v6 + 25) );
  }
  if ( *((_BYTE *)v5 + 25) || a1 < v5[4] )
    v5 = v3;
  if ( v5 != *((__int64 **)CHardwareManager::Instance() + 9) )
  {
    v7 = v5[6];
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    v15 = (HANDLE *)v5[5];
    v8 = (std::_Ref_count_base *)v5[6];
    v16 = v8;
    v9 = CHardwareManager::Instance();
    v10 = std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>::_Extract(
            (char *)v9 + 72,
            v5);
    std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>>>(
      v11,
      v10);
    v22 = 0;
    Buffer = 3;
    SetEvent(*v15);
    pv = 0;
    v18 = 0;
    v20 = 0;
    pv = CreateThreadpoolTimer(winbio::watchdog::TimerCallback, &pv, 0);
    hFile = v15[1];
    pftDueTime = (struct _FILETIME)&hFile;
    winbio::watchdog::SetTimeoutAction__lambda_3b9937ef79969652ae175142cbb18f7c___(&pv, &pftDueTime);
    v18 = 0;
    if ( pv )
    {
      pftDueTime = (struct _FILETIME)-20000000LL;
      SetThreadpoolTimer(pv, &pftDueTime, 0, 0);
    }
    NumberOfBytesWritten = 0;
    WriteFile(hFile, &Buffer, 0x14u, &NumberOfBytesWritten, 0);
    if ( pv )
    {
      SetThreadpoolTimer(pv, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(pv, 1);
      if ( pv )
      {
        SetThreadpoolTimer(pv, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(pv, 1);
        CloseThreadpoolTimer(pv);
        pv = 0;
      }
    }
    std::_Func_class<void,>::_Tidy(v19);
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x180010644  push    rbp
0x180010646  push    rbx
0x180010647  push    rsi
0x180010648  push    rdi
0x180010649  push    r14
0x18001064b  lea     rbp, [rsp-37h]
0x180010650  sub     rsp, 0D0h
0x180010657  mov     rax, cs:__security_cookie
0x18001065e  xor     rax, rsp
0x180010661  mov     [rbp+57h+var_28], rax
0x180010665  mov     rbx, rcx
0x180010668  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18001066d  lea     rsi, [rax+8]
0x180010671  mov     rcx, rsi; SRWLock
0x180010674  call    cs:__imp_AcquireSRWLockExclusive
0x18001067a  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rsi
0x18001067e  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180010683  mov     rdx, [rax+48h]
0x180010687  mov     rcx, [rdx+8]
0x18001068b  xor     eax, eax
0x18001068d  mov     [rbp+57h+var_9C], eax
0x180010690  mov     rdi, rdx
0x180010693  cmp     [rcx+19h], al
0x180010696  jnz     short loc_1800106B1
0x180010698  cmp     [rcx+20h], rbx
0x18001069c  cmovnb  rdi, rcx
0x1800106a0  lea     rax, [rcx+10h]
0x1800106a4  cmovnb  rax, rcx
0x1800106a8  mov     rcx, [rax]
0x1800106ab  cmp     byte ptr [rcx+19h], 0
0x1800106af  jz      short loc_180010698
0x1800106b1  cmp     byte ptr [rdi+19h], 0
0x1800106b5  jnz     short loc_1800106BD
0x1800106b7  cmp     rbx, [rdi+20h]
0x1800106bb  jnb     short loc_1800106C0
0x1800106bd  mov     rdi, rdx
0x1800106c0  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800106c5  cmp     rdi, [rax+48h]
0x1800106c9  jz      loc_180010829
0x1800106cf  mov     rax, [rdi+30h]
0x1800106d3  test    rax, rax
0x1800106d6  jz      short loc_1800106DC
0x1800106d8  lock inc dword ptr [rax+8]
0x1800106dc  mov     rbx, [rdi+28h]
0x1800106e0  mov     [rbp+57h+var_A8], rbx
0x1800106e4  mov     r14, [rdi+30h]
0x1800106e8  mov     [rbp-49h], r14
0x1800106ec  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800106f1  lea     rcx, [rax+48h]
0x1800106f5  mov     rdx, rdi
0x1800106f8  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>,std::_Iterator_base0>)
0x1800106fd  mov     rdx, rax
0x180010700  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>>>(std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>> &,std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *> *)
0x180010705  xorps   xmm0, xmm0
0x180010708  movdqu  [rbp+57h+var_3C], xmm0
0x18001070d  mov     [rbp+57h+Buffer], 3
0x180010714  mov     rcx, [rbx]; hEvent
0x180010717  call    cs:__imp_SetEvent
0x18001071d  mov     [rbp+57h+pv], 0
0x180010725  mov     [rbp+57h+var_88], 0
0x180010729  mov     [rbp+57h+var_48], 0
0x180010731  xor     r8d, r8d; pcbe
0x180010734  lea     rdx, [rbp+57h+pv]; pv
0x180010738  lea     rcx, ?TimerCallback@watchdog@winbio@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001073f  call    cs:__imp_CreateThreadpoolTimer
0x180010745  mov     [rbp+57h+pv], rax
0x180010749  mov     rax, [rbx+8]
0x18001074d  mov     [rbp+57h+hFile], rax
0x180010751  lea     rax, [rbp+57h+hFile]
0x180010755  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x180010759  lea     rdx, [rbp+57h+pftDueTime]
0x18001075d  lea     rcx, [rbp+57h+pv]
0x180010761  call    winbio__watchdog__SetTimeoutAction__lambda_3b9937ef79969652ae175142cbb18f7c___
0x180010766  mov     [rbp+57h+var_88], 0
0x18001076a  mov     rcx, [rbp+57h+pv]; pti
0x18001076e  test    rcx, rcx
0x180010771  jz      short loc_18001078B
0x180010773  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], 0FFFFFFFFFECED300h
0x18001077b  xor     r9d, r9d; msWindowLength
0x18001077e  xor     r8d, r8d; msPeriod
0x180010781  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x180010785  call    cs:__imp_SetThreadpoolTimer
0x18001078b  mov     [rbp+57h+NumberOfBytesWritten], 0
0x180010792  mov     [rsp+0F0h+lpOverlapped], 0; lpOverlapped
0x18001079b  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001079f  mov     r8d, 14h; nNumberOfBytesToWrite
0x1800107a5  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x1800107a9  mov     rcx, [rbp+57h+hFile]; hFile
0x1800107ad  call    cs:__imp_WriteFile
0x1800107b3  mov     rcx, [rbp+57h+pv]; pti
0x1800107b7  test    rcx, rcx
0x1800107ba  jz      short loc_180010811
0x1800107bc  xor     r9d, r9d; msWindowLength
0x1800107bf  xor     r8d, r8d; msPeriod
0x1800107c2  xor     edx, edx; pftDueTime
0x1800107c4  call    cs:__imp_SetThreadpoolTimer
0x1800107ca  mov     edx, 1; fCancelPendingCallbacks
0x1800107cf  mov     rcx, [rbp+57h+pv]; pti
0x1800107d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800107d9  mov     rcx, [rbp+57h+pv]; pti
0x1800107dd  test    rcx, rcx
0x1800107e0  jz      short loc_180010811
0x1800107e2  xor     r9d, r9d; msWindowLength
0x1800107e5  xor     r8d, r8d; msPeriod
0x1800107e8  xor     edx, edx; pftDueTime
0x1800107ea  call    cs:__imp_SetThreadpoolTimer
0x1800107f0  mov     edx, 1; fCancelPendingCallbacks
0x1800107f5  mov     rcx, [rbp+57h+pv]; pti
0x1800107f9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800107ff  mov     rcx, [rbp+57h+pv]; pti
0x180010803  call    cs:__imp_CloseThreadpoolTimer
0x180010809  mov     [rbp+57h+pv], 0
0x180010811  lea     rcx, [rbp+57h+var_80]
0x180010815  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001081a  nop
0x18001081b  test    r14, r14
0x18001081e  jz      short loc_180010829
0x180010820  mov     rcx, r14; this
0x180010823  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010828  nop
0x180010829  test    rsi, rsi
0x18001082c  jz      short loc_180010837
0x18001082e  mov     rcx, rsi; SRWLock
0x180010831  call    cs:__imp_ReleaseSRWLockExclusive
0x180010837  mov     rcx, [rbp+57h+var_28]
0x18001083b  xor     rcx, rsp; StackCookie
0x18001083e  call    __security_check_cookie
0x180010843  add     rsp, 0D0h
0x18001084a  pop     r14
0x18001084c  pop     rdi
0x18001084d  pop     rsi
0x18001084e  pop     rbx
0x18001084f  pop     rbp
0x180010850  retn
```
