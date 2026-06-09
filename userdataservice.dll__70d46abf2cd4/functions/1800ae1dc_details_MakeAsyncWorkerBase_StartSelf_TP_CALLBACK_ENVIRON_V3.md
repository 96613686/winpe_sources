# details::MakeAsyncWorkerBase::StartSelf(_TP_CALLBACK_ENVIRON_V3 *)

- ea: `0x1800ae1dc`
- end: `0x1800ae326`
- name: `?StartSelf@MakeAsyncWorkerBase@details@@QEAAJPEAU_TP_CALLBACK_ENVIRON_V3@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(char *pv, struct _TP_CALLBACK_ENVIRON_V3 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180085d18`
- `0x180089b50`
- `0x1800ac25c`

## callees

- `0x180008f0c`
- `0x18001fd5c`
- `0x180021c40`
- `0x1800ae1dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800ae206`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800ae206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae2c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ae25d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ae25d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ae273`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ae273`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ae2b1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ae2b1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ae307`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ae307`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800ae244`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800ae244`

## pseudocode

```c
__int64 __fastcall details::MakeAsyncWorkerBase::StartSelf(char *pv, struct _TP_CALLBACK_ENVIRON_V3 *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  HANDLE CurrentThread; // rax
  signed int v8; // eax
  PTP_WORK ThreadpoolWork; // rax
  signed int v10; // eax
  struct _TP_CALLBACK_ENVIRON_V3 *v12; // [rsp+48h] [rbp+10h] BYREF

  v12 = a2;
  *((_QWORD *)pv + 1) = 0;
  if ( !GetModuleHandleExW(4u, (LPCWSTR)details::MakeAsyncWorkerBase::Execute, (HMODULE *)pv + 5) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = 1112;
LABEL_5:
    v6 = 0;
LABEL_6:
    Log_HREvent(v4, v6, "onecoreuap\\internal\\base\\inc\\WRLWinRTHelpers.h", v5);
    return v4;
  }
  v4 = CoIncrementMTAUsage(pv + 32);
  if ( (v4 & 0x80000000) != 0 )
  {
    v5 = 1114;
    v6 = 1;
    goto LABEL_6;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, (PHANDLE)pv + 3) )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 != 1008 )
    {
      if ( v8 )
      {
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0x80070000;
        v5 = 1123;
        goto LABEL_5;
      }
    }
  }
  ThreadpoolWork = CreateThreadpoolWork(details::MakeAsyncWorkerBase::Execute, pv, *((PTP_CALLBACK_ENVIRON *)pv + 1));
  v12 = (struct _TP_CALLBACK_ENVIRON_V3 *)ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    v12 = 0;
    tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>::reset(
      pv + 16,
      ThreadpoolWork);
    SubmitThreadpoolWork(*((PTP_WORK *)pv + 2));
    v4 = 0;
  }
  else
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    Log_HREvent(v4, 0, "onecoreuap\\internal\\base\\inc\\WRLWinRTHelpers.h", 1132);
  }
  tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>::_Delete(&v12);
  return v4;
}

```

## disassembly

```asm
0x1800ae1dc  mov     [rsp+arg_0], rbx
0x1800ae1e1  mov     [rsp+arg_8], rdx
0x1800ae1e6  push    rdi
0x1800ae1e7  sub     rsp, 30h
0x1800ae1eb  mov     rdi, rcx
0x1800ae1ee  mov     qword ptr [rcx+8], 0
0x1800ae1f6  lea     r8, [rcx+28h]; phModule
0x1800ae1fa  mov     ecx, 4; dwFlags
0x1800ae1ff  lea     rdx, ?Execute@MakeAsyncWorkerBase@details@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x1800ae206  call    cs:__imp_GetModuleHandleExW
0x1800ae20c  test    eax, eax
0x1800ae20e  jnz     short loc_1800AE240
0x1800ae210  call    cs:__imp_GetLastError
0x1800ae216  mov     ebx, eax
0x1800ae218  test    eax, eax
0x1800ae21a  jle     short loc_1800AE225
0x1800ae21c  movzx   ebx, ax
0x1800ae21f  or      ebx, 80070000h
0x1800ae225  mov     r9d, 458h
0x1800ae22b  xor     edx, edx
0x1800ae22d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\WRLWin"...
0x1800ae234  mov     ecx, ebx
0x1800ae236  call    Log_HREvent
0x1800ae23b  jmp     loc_1800AE319
0x1800ae240  lea     rcx, [rdi+20h]
0x1800ae244  call    cs:__imp_CoIncrementMTAUsage
0x1800ae24a  mov     ebx, eax
0x1800ae24c  test    eax, eax
0x1800ae24e  jns     short loc_1800AE25D
0x1800ae250  mov     r9d, 45Ah
0x1800ae256  mov     edx, 1
0x1800ae25b  jmp     short loc_1800AE22D
0x1800ae25d  call    cs:__imp_GetCurrentThread
0x1800ae263  mov     edx, 4; DesiredAccess
0x1800ae268  lea     r9, [rdi+18h]; TokenHandle
0x1800ae26c  mov     rcx, rax; ThreadHandle
0x1800ae26f  lea     r8d, [rdx-3]; OpenAsSelf
0x1800ae273  call    cs:__imp_OpenThreadToken
0x1800ae279  test    eax, eax
0x1800ae27b  jnz     short loc_1800AE2A3
0x1800ae27d  call    cs:__imp_GetLastError
0x1800ae283  mov     ebx, eax
0x1800ae285  cmp     eax, 3F0h
0x1800ae28a  jz      short loc_1800AE2A3
0x1800ae28c  test    eax, eax
0x1800ae28e  jz      short loc_1800AE2A3
0x1800ae290  jle     short loc_1800AE29B
0x1800ae292  movzx   ebx, ax
0x1800ae295  or      ebx, 80070000h
0x1800ae29b  mov     r9d, 463h
0x1800ae2a1  jmp     short loc_1800AE22B
0x1800ae2a3  mov     r8, [rdi+8]; pcbe
0x1800ae2a7  lea     rcx, ?Execute@MakeAsyncWorkerBase@details@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ae2ae  mov     rdx, rdi; pv
0x1800ae2b1  call    cs:__imp_CreateThreadpoolWork
0x1800ae2b7  mov     [rsp+38h+arg_8], rax
0x1800ae2bc  test    rax, rax
0x1800ae2bf  jnz     short loc_1800AE2EE
0x1800ae2c1  call    cs:__imp_GetLastError
0x1800ae2c7  mov     ebx, eax
0x1800ae2c9  test    eax, eax
0x1800ae2cb  jle     short loc_1800AE2D6
0x1800ae2cd  movzx   ebx, ax
0x1800ae2d0  or      ebx, 80070000h
0x1800ae2d6  mov     r9d, 46Ch
0x1800ae2dc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\WRLWin"...
0x1800ae2e3  xor     edx, edx
0x1800ae2e5  mov     ecx, ebx
0x1800ae2e7  call    Log_HREvent
0x1800ae2ec  jmp     short loc_1800AE30F
0x1800ae2ee  mov     rdx, rax
0x1800ae2f1  mov     [rsp+38h+arg_8], 0
0x1800ae2fa  lea     rcx, [rdi+10h]
0x1800ae2fe  call    ?reset@?$auto_xxx@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@QEAAXPEAU_TP_WORK@@@Z; tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>::reset(_TP_WORK *)
0x1800ae303  mov     rcx, [rdi+10h]; pwk
0x1800ae307  call    cs:__imp_SubmitThreadpoolWork
0x1800ae30d  xor     ebx, ebx
0x1800ae30f  lea     rcx, [rsp+38h+arg_8]
0x1800ae314  call    ?_Delete@?$auto_xxx@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>::_Delete(void)
0x1800ae319  mov     eax, ebx
0x1800ae31b  mov     rbx, [rsp+38h+arg_0]
0x1800ae320  add     rsp, 30h
0x1800ae324  pop     rdi
0x1800ae325  retn
```
