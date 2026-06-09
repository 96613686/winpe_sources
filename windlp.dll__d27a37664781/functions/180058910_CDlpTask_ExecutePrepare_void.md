# CDlpTask::ExecutePrepare(void)

- ea: `0x180058910`
- end: `0x180058c21`
- name: `?ExecutePrepare@CDlpTask@@AEAAJXZ`
- size: `785`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180054950`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180058910`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180058947`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180058947`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180058b17`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180058b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005895a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005895a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058b21`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180058a1e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180058a1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058c09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058c09`

## string_xrefs

- `0x180058afe`: `Prepare thread has exited.`
- `0x180058a05`: `Waiting for prepare thread to exit.`
- `0x180058bce`: `CDlpTask::ExecutePrepare`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ExecutePrepare(CDlpTask *this)
{
  HANDLE Thread; // rax
  void *v3; // rbx
  signed int v4; // eax
  signed int v5; // edi
  __int64 v6; // rax
  __int64 v7; // rcx
  char *v8; // rsi
  __int64 v9; // rax
  DWORD v10; // eax
  signed int LastError; // eax
  __int64 v12; // rax
  signed int v13; // eax
  bool v14; // sf
  int v15; // eax
  __int64 v17; // [rsp+20h] [rbp-18h]
  __int64 v18; // [rsp+28h] [rbp-10h]
  DWORD ExitCode; // [rsp+48h] [rbp+10h] BYREF
  HANDLE v20; // [rsp+50h] [rbp+18h]

  ExitCode = 0;
  Thread = CreateThread(0, 0, CDlpTask::ExecutePrepareThreadProc, this, 0, 0);
  v3 = Thread;
  if ( Thread )
  {
    v20 = Thread;
    v8 = (char *)this + 176;
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8) )
    {
      v9 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
      CDlpLogT<CEmptyType>::DlpLogFormat(v9, 2, L"Waiting for prepare thread to exit.");
    }
    v10 = WaitForSingleObject(v3, 0xFFFFFFFF);
    if ( v10 )
    {
      if ( v10 != -1 )
      {
        v5 = -2147418113;
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8) )
          goto LABEL_43;
        v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
        v7 = 0;
        if ( !v6 )
          goto LABEL_42;
        LODWORD(v18) = -2147418113;
        LODWORD(v17) = 3194;
        goto LABEL_40;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8) )
        goto LABEL_43;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
      v7 = 0;
      if ( !v6 )
        goto LABEL_42;
      LODWORD(v18) = v5;
      LODWORD(v17) = 3189;
    }
    else
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8) )
      {
        v12 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
        CDlpLogT<CEmptyType>::DlpLogFormat(v12, 2, L"Prepare thread has exited.");
      }
      if ( GetExitCodeThread(v3, &ExitCode) )
      {
        v5 = ExitCode;
        v14 = (ExitCode & 0x80000000) != 0;
        if ( (int)ExitCode > 0 )
        {
          v5 = (unsigned __int16)ExitCode | 0x80070000;
          v14 = 1;
        }
        if ( !v14 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8) )
          goto LABEL_43;
        v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
        v7 = 0;
        if ( !v6 )
          goto LABEL_42;
        LODWORD(v18) = v5;
        LODWORD(v17) = 3185;
      }
      else
      {
        v13 = GetLastError();
        v5 = v13;
        if ( v13 )
        {
          if ( v13 > 0 )
            v5 = (unsigned __int16)v13 | 0x80070000;
        }
        else
        {
          v5 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8) )
          goto LABEL_43;
        v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
        v7 = 0;
        if ( v5 >= 0 || !v6 )
          goto LABEL_42;
        LODWORD(v18) = v5;
        LODWORD(v17) = 3184;
      }
    }
LABEL_40:
    v15 = CDlpLogT<CEmptyType>::DlpLogFormat(v6, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::ExecutePrepare", v17, v18);
    v7 = (unsigned int)v15;
    if ( v15 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15);
    goto LABEL_42;
  }
  v20 = 0;
  v4 = GetLastError();
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v5 = -2147467259;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v7 = 0;
    if ( v5 < 0 && v6 )
    {
      LODWORD(v18) = v5;
      LODWORD(v17) = 3170;
      goto LABEL_40;
    }
LABEL_42:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  }
LABEL_43:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( v3 )
    CloseHandle(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180058910  mov     rax, rsp
0x180058913  mov     [rax+8], rbx
0x180058917  mov     [rax+20h], rsi
0x18005891b  push    rdi
0x18005891c  sub     rsp, 30h
0x180058920  mov     rsi, rcx
0x180058923  mov     dword ptr [rax+10h], 0
0x18005892a  mov     qword ptr [rax-10h], 0
0x180058932  mov     dword ptr [rax-18h], 0
0x180058939  mov     r9, rcx; lpParameter
0x18005893c  lea     r8, ?ExecutePrepareThreadProc@CDlpTask@@SAKPEAX@Z; lpStartAddress
0x180058943  xor     edx, edx; dwStackSize
0x180058945  xor     ecx, ecx; lpThreadAttributes
0x180058947  call    cs:__imp_CreateThread
0x18005894d  mov     rbx, rax
0x180058950  test    rax, rax
0x180058953  jnz     short loc_1800589D3
0x180058955  mov     [rsp+38h+arg_10], rax
0x18005895a  call    cs:__imp_GetLastError
0x180058960  mov     edi, eax
0x180058962  test    eax, eax
0x180058964  jnz     short loc_18005896D
0x180058966  mov     edi, 80004005h
0x18005896b  jmp     short loc_180058978
0x18005896d  jle     short loc_180058978
0x18005896f  movzx   edi, ax
0x180058972  or      edi, 80070000h
0x180058978  mov     rax, [rsi+0B0h]
0x18005897f  lea     rcx, [rsi+0B0h]
0x180058986  mov     rax, [rax+10h]
0x18005898a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005898f  test    rax, rax
0x180058992  jz      loc_180058BF9
0x180058998  mov     rax, [rsi+0B0h]
0x18005899f  lea     rcx, [rsi+0B0h]
0x1800589a6  mov     rax, [rax+10h]
0x1800589aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589af  xor     ecx, ecx
0x1800589b1  test    edi, edi
0x1800589b3  jns     loc_180058BF4
0x1800589b9  test    rax, rax
0x1800589bc  jz      loc_180058BF4
0x1800589c2  mov     [rsp+38h+var_10], edi
0x1800589c6  mov     dword ptr [rsp+38h+var_18], 0C62h
0x1800589ce  jmp     loc_180058BCE
0x1800589d3  mov     [rsp+38h+arg_10], rbx
0x1800589d8  add     rsi, 0B0h
0x1800589df  mov     rax, [rsi]
0x1800589e2  mov     rcx, rsi
0x1800589e5  mov     rax, [rax+10h]
0x1800589e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589ee  test    rax, rax
0x1800589f1  jz      short loc_180058A16
0x1800589f3  mov     rax, [rsi]
0x1800589f6  mov     rcx, rsi
0x1800589f9  mov     rax, [rax+10h]
0x1800589fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a02  mov     rcx, rax
0x180058a05  lea     r8, aWaitingForPrep; "Waiting for prepare thread to exit."
0x180058a0c  mov     edx, 2
0x180058a11  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180058a16  or      edi, 0FFFFFFFFh
0x180058a19  mov     edx, edi; dwMilliseconds
0x180058a1b  mov     rcx, rbx; hHandle
0x180058a1e  call    cs:__imp_WaitForSingleObject
0x180058a24  test    eax, eax
0x180058a26  jz      loc_180058AD8
0x180058a2c  cmp     eax, edi
0x180058a2e  jz      short loc_180058A78
0x180058a30  mov     edi, 8000FFFFh
0x180058a35  mov     rax, [rsi]
0x180058a38  mov     rcx, rsi
0x180058a3b  mov     rax, [rax+10h]
0x180058a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a44  test    rax, rax
0x180058a47  jz      loc_180058BF9
0x180058a4d  mov     rax, [rsi]
0x180058a50  mov     rcx, rsi
0x180058a53  mov     rax, [rax+10h]
0x180058a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a5c  xor     ecx, ecx
0x180058a5e  test    rax, rax
0x180058a61  jz      loc_180058BF4
0x180058a67  mov     [rsp+38h+var_10], edi
0x180058a6b  mov     dword ptr [rsp+38h+var_18], 0C7Ah
0x180058a73  jmp     loc_180058BCE
0x180058a78  call    cs:__imp_GetLastError
0x180058a7e  mov     edi, eax
0x180058a80  test    eax, eax
0x180058a82  jle     short loc_180058A8D
0x180058a84  movzx   edi, ax
0x180058a87  or      edi, 80070000h
0x180058a8d  test    edi, edi
0x180058a8f  jns     loc_180058BF9
0x180058a95  mov     rax, [rsi]
0x180058a98  mov     rcx, rsi
0x180058a9b  mov     rax, [rax+10h]
0x180058a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058aa4  test    rax, rax
0x180058aa7  jz      loc_180058BF9
0x180058aad  mov     rax, [rsi]
0x180058ab0  mov     rcx, rsi
0x180058ab3  mov     rax, [rax+10h]
0x180058ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058abc  xor     ecx, ecx
0x180058abe  test    rax, rax
0x180058ac1  jz      loc_180058BF4
0x180058ac7  mov     [rsp+38h+var_10], edi
0x180058acb  mov     dword ptr [rsp+38h+var_18], 0C75h
0x180058ad3  jmp     loc_180058BCE
0x180058ad8  mov     rax, [rsi]
0x180058adb  mov     rcx, rsi
0x180058ade  mov     rax, [rax+10h]
0x180058ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ae7  test    rax, rax
0x180058aea  jz      short loc_180058B0F
0x180058aec  mov     rax, [rsi]
0x180058aef  mov     rcx, rsi
0x180058af2  mov     rax, [rax+10h]
0x180058af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058afb  mov     rcx, rax
0x180058afe  lea     r8, aPrepareThreadH; "Prepare thread has exited."
0x180058b05  mov     edx, 2
0x180058b0a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180058b0f  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x180058b14  mov     rcx, rbx; hThread
0x180058b17  call    cs:__imp_GetExitCodeThread
0x180058b1d  test    eax, eax
0x180058b1f  jnz     short loc_180058B83
0x180058b21  call    cs:__imp_GetLastError
0x180058b27  mov     edi, eax
0x180058b29  test    eax, eax
0x180058b2b  jnz     short loc_180058B34
0x180058b2d  mov     edi, 80004005h
0x180058b32  jmp     short loc_180058B3F
0x180058b34  jle     short loc_180058B3F
0x180058b36  movzx   edi, ax
0x180058b39  or      edi, 80070000h
0x180058b3f  mov     rax, [rsi]
0x180058b42  mov     rcx, rsi
0x180058b45  mov     rax, [rax+10h]
0x180058b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b4e  test    rax, rax
0x180058b51  jz      loc_180058BF9
0x180058b57  mov     rax, [rsi]
0x180058b5a  mov     rcx, rsi
0x180058b5d  mov     rax, [rax+10h]
0x180058b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b66  xor     ecx, ecx
0x180058b68  test    edi, edi
0x180058b6a  jns     loc_180058BF4
0x180058b70  test    rax, rax
0x180058b73  jz      short loc_180058BF4
0x180058b75  mov     [rsp+38h+var_10], edi
0x180058b79  mov     dword ptr [rsp+38h+var_18], 0C70h
0x180058b81  jmp     short loc_180058BCE
0x180058b83  mov     edi, [rsp+38h+ExitCode]
0x180058b87  test    edi, edi
0x180058b89  jle     short loc_180058B96
0x180058b8b  movzx   edi, di
0x180058b8e  or      edi, 80070000h
0x180058b94  test    edi, edi
0x180058b96  jns     short loc_180058BF9
0x180058b98  mov     rax, [rsi]
0x180058b9b  mov     rcx, rsi
0x180058b9e  mov     rax, [rax+10h]
0x180058ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ba7  test    rax, rax
0x180058baa  jz      short loc_180058BF9
0x180058bac  mov     rax, [rsi]
0x180058baf  mov     rcx, rsi
0x180058bb2  mov     rax, [rax+10h]
0x180058bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bbb  xor     ecx, ecx
0x180058bbd  test    rax, rax
0x180058bc0  jz      short loc_180058BF4
0x180058bc2  mov     [rsp+38h+var_10], edi
0x180058bc6  mov     dword ptr [rsp+38h+var_18], 0C71h
0x180058bce  lea     r9, aCdlptaskExecut; "CDlpTask::ExecutePrepare"
0x180058bd5  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180058bdc  mov     edx, 4
0x180058be1  mov     rcx, rax
0x180058be4  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180058be9  mov     ecx, eax
0x180058beb  test    eax, eax
0x180058bed  jns     short loc_180058BF4
0x180058bef  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180058bf4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180058bf9  mov     ecx, edi
0x180058bfb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180058c00  nop
0x180058c01  test    rbx, rbx
0x180058c04  jz      short loc_180058C0F
0x180058c06  mov     rcx, rbx; hObject
0x180058c09  call    cs:__imp_CloseHandle
0x180058c0f  mov     eax, edi
0x180058c11  mov     rbx, [rsp+38h+arg_0]
0x180058c16  mov     rsi, [rsp+38h+arg_18]
0x180058c1b  add     rsp, 30h
0x180058c1f  pop     rdi
0x180058c20  retn
```
