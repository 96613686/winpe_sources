# GetUserTokenForSession(ulong,void * *)

- ea: `0x1800083b0`
- end: `0x180008731`
- name: `?GetUserTokenForSession@@YAJKPEAPEAX@Z`
- size: `897`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800142c0`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008340`
- `0x1800083b0`
- `0x180008f10`
- `0x18001f5f8`
- `0x1800230b8`
- `0x1800230ec`
- `0x18002bf2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800085dd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800085dd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008590`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086af`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180008652`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180008652`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800083e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800083e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008671`
- `RPCRT4!RpcBindingFree` at `0x18000859f`
- `RPCRT4!RpcBindingFree` at `0x1800085af`
- `RPCRT4!RpcBindingFree` at `0x18000870e`
- `RPCRT4!RpcBindingFree` at `0x18000871c`
- `RPCRT4!RpcBindingFree` at `0x18000859f`
- `RPCRT4!RpcBindingFree` at `0x1800085af`
- `RPCRT4!RpcBindingFree` at `0x18000870e`
- `RPCRT4!RpcBindingFree` at `0x18000871c`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003031e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003031e`
- `RPCRT4!NdrClientCall3` at `0x180008526`
- `RPCRT4!NdrClientCall3` at `0x180008526`

## string_xrefs

- `0x18000860e`: `StringCchCopy failed: %x`
- `0x180008644`: `Global\TermSrvReadyEvent`
- `0x18000854f`: `RpcGetUserToken threw an exception: 0x%x`
- `0x180008699`: `OpenEvent( Global\TermSrvReadyEvent ) failed: 0x%x`

## pseudocode

```c
__int64 __fastcall GetUserTokenForSession(int a1, void **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  int v6; // r14d
  _WORD *v7; // r9
  __int64 v8; // rcx
  int *v9; // rdx
  __int64 v10; // r10
  __int16 v11; // ax
  int v12; // esi
  _WORD *v13; // rax
  RPC_BINDING_HANDLE *v14; // rsi
  void *UnifiedRpcBinding; // rax
  void *LSMBinding; // rax
  unsigned int Pointer; // ebx
  void *v18; // rcx
  void *v19; // rcx
  HANDLE v21; // rax
  signed int LastError; // eax
  signed int v23; // eax

  if ( g_ReadyEventHandle )
  {
LABEL_2:
    WaitForSingleObject(g_ReadyEventHandle, 0xFFFFFFFF);
    goto LABEL_3;
  }
  v21 = OpenEventW(0x100000u, 0, L"Global\\TermSrvReadyEvent");
  if ( v21 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_ReadyEventHandle, (signed __int64)v21, 0) )
      CloseHandle(v21);
    goto LABEL_2;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  _DbgPrintMessage(8, "OpenEvent( Global\\TermSrvReadyEvent ) failed: 0x%x", LastError);
LABEL_3:
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v6 = 1;
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
    v4[3] = 0;
    v4[4] = 0;
    v4[5] = 0;
    v4[6] = 1;
    v4[7] = 0;
    v7 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v5[5] = v7;
    if ( v7 )
    {
      v8 = 2147483646;
      v9 = &dword_18003D0CC;
      v10 = 1;
      do
      {
        if ( !v8 )
          break;
        v11 = *(_WORD *)v9;
        if ( !*(_WORD *)v9 )
          break;
        v9 = (int *)((char *)v9 + 2);
        *v7++ = v11;
        --v8;
        --v10;
      }
      while ( v10 );
      v12 = -2147024774;
      if ( v10 )
        v12 = 0;
      v13 = v7 - 1;
      if ( v10 )
        v13 = v7;
      *v13 = 0;
      if ( v10 )
      {
        if ( !v5[3] && !*((_DWORD *)v5 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v5) == -2147023174 )
            *((_DWORD *)v5 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v5);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v12);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v12);
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( !v5 )
  {
    v6 = 0;
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  v14 = (RPC_BINDING_HANDLE *)(v5 + 3);
  if ( v5 )
  {
    if ( *v14 )
      UnifiedRpcBinding = CPublicBinding::GetUnifiedRpcBinding((CPublicBinding *)v5);
    else
      UnifiedRpcBinding = CPublicBinding::GetLSMBinding((RPC_BINDING_HANDLE *)v5);
  }
  else
  {
    UnifiedRpcBinding = 0;
  }
  if ( UnifiedRpcBinding )
  {
    if ( v5 )
    {
      if ( *v14 )
        LSMBinding = CPublicBinding::GetUnifiedRpcBinding((CPublicBinding *)v5);
      else
        LSMBinding = CPublicBinding::GetLSMBinding((RPC_BINDING_HANDLE *)v5);
    }
    else
    {
      LSMBinding = 0;
    }
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800321A0, 0, 0, LSMBinding, a1, a2).Pointer;
  }
  else
  {
    v23 = GetLastError();
    Pointer = v23;
    if ( v23 > 0 )
      Pointer = (unsigned __int16)v23 | 0x80070000;
  }
  if ( v6 && v5 )
  {
    CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v5);
    v18 = (void *)v5[5];
    if ( v18 )
      operator delete[](v18);
    if ( *v5 )
      RpcBindingFree((RPC_BINDING_HANDLE *)v5);
    if ( v5[1] )
      RpcBindingFree((RPC_BINDING_HANDLE *)v5 + 1);
    if ( v5[2] )
      RpcBindingFree((RPC_BINDING_HANDLE *)v5 + 2);
    if ( *v14 )
      RpcBindingFree(v14);
    v19 = (void *)v5[4];
    if ( v19 )
      Legacy_WinStationCloseServer(v19);
    operator delete(v5);
  }
  return Pointer;
}

```

## disassembly

```asm
0x1800083b0  mov     [rsp+arg_0], rbx
0x1800083b5  push    rsi
0x1800083b6  push    rdi
0x1800083b7  push    r12
0x1800083b9  push    r14
0x1800083bb  push    r15
0x1800083bd  sub     rsp, 50h
0x1800083c1  mov     r15, rdx
0x1800083c4  mov     r12d, ecx
0x1800083c7  cmp     cs:?g_ReadyEventHandle@@3PEAXEA, 0; void * g_ReadyEventHandle
0x1800083cf  jz      loc_180008644
0x1800083d5  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800083da  mov     rcx, cs:?g_ReadyEventHandle@@3PEAXEA; hHandle
0x1800083e1  call    cs:__imp_WaitForSingleObject
0x1800083e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800083ee  mov     ecx, 40h ; '@'; unsigned __int64
0x1800083f3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800083f8  mov     rdi, rax
0x1800083fb  xor     ebx, ebx
0x1800083fd  mov     r14d, 1
0x180008403  test    rax, rax
0x180008406  jz      loc_1800086D6
0x18000840c  mov     [rax], rbx
0x18000840f  mov     [rax+8], rbx
0x180008413  mov     [rax+10h], rbx
0x180008417  mov     [rax+18h], rbx
0x18000841b  mov     [rax+20h], rbx
0x18000841f  mov     [rax+28h], rbx
0x180008423  mov     [rax+30h], r14
0x180008427  mov     [rax+38h], rbx
0x18000842b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008432  mov     ecx, 2; unsigned __int64
0x180008437  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000843c  mov     r9, rax
0x18000843f  mov     [rdi+28h], rax
0x180008443  test    rax, rax
0x180008446  jz      short loc_1800084A3
0x180008448  mov     ecx, 7FFFFFFEh
0x18000844d  lea     rdx, dword_18003D0CC
0x180008454  mov     r10d, r14d
0x180008457  test    rcx, rcx
0x18000845a  jz      short loc_180008478
0x18000845c  movzx   eax, word ptr [rdx]
0x18000845f  test    ax, ax
0x180008462  jz      short loc_180008478
0x180008464  add     rdx, 2
0x180008468  mov     [r9], ax
0x18000846c  add     r9, 2
0x180008470  dec     rcx
0x180008473  sub     r10, r14
0x180008476  jnz     short loc_180008457
0x180008478  mov     esi, 8007007Ah
0x18000847d  test    r10, r10
0x180008480  cmovnz  esi, ebx
0x180008483  lea     rax, [r9-2]
0x180008487  cmovnz  rax, r9
0x18000848b  mov     [rax], bx
0x18000848e  jz      loc_180008604
0x180008494  cmp     [rdi+18h], rbx
0x180008498  jnz     short loc_1800084A3
0x18000849a  cmp     [rdi+30h], ebx
0x18000849d  jz      loc_180008624
0x1800084a3  mov     [rsp+78h+var_40], rdi
0x1800084a8  test    rdi, rdi
0x1800084ab  jz      loc_1800086E3
0x1800084b1  mov     [rsp+78h+arg_10], r14d
0x1800084b9  lea     rsi, [rdi+18h]
0x1800084bd  test    rdi, rdi
0x1800084c0  jz      loc_18000867C
0x1800084c6  mov     rcx, rdi; Binding
0x1800084c9  cmp     qword ptr [rsi], 0
0x1800084cd  jz      loc_1800085FA
0x1800084d3  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x1800084d8  mov     [rsp+78h+arg_18], rsi
0x1800084e0  test    rax, rax
0x1800084e3  jz      loc_1800086AF
0x1800084e9  test    rdi, rdi
0x1800084ec  jz      short loc_180008505
0x1800084ee  mov     rcx, rdi; Binding
0x1800084f1  cmp     qword ptr [rsi], 0
0x1800084f5  jz      short loc_1800084FE
0x1800084f7  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x1800084fc  jmp     short loc_180008508
0x1800084fe  call    ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x180008503  jmp     short loc_180008508
0x180008505  mov     rax, rbx
0x180008508  mov     [rsp+78h+var_38], rbx
0x18000850d  mov     [rsp+78h+var_50], r15
0x180008512  mov     [rsp+78h+var_58], r12d
0x180008517  mov     r9, rax
0x18000851a  xor     r8d, r8d; pReturnValue
0x18000851d  xor     edx, edx; nProcNum
0x18000851f  lea     rcx, stru_1800321A0; pProxyInfo
0x180008526  call    cs:__imp_NdrClientCall3
0x18000852c  mov     rbx, rax
0x18000852f  mov     [rsp+78h+var_38], rax
0x180008534  mov     [rsp+78h+var_48], eax
0x180008538  jmp     short loc_180008575
0x18000853a  test    eax, eax
0x18000853c  jle     short loc_180008546
0x18000853e  movzx   eax, ax
0x180008541  or      eax, 80070000h
0x180008546  mov     ebx, eax
0x180008548  mov     [rsp+78h+var_48], eax
0x18000854c  mov     r8d, eax
0x18000854f  lea     rdx, aRpcgetusertoke; "RpcGetUserToken threw an exception: 0x%"...
0x180008556  mov     ecx, 8; int
0x18000855b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008560  mov     rsi, [rsp+78h+arg_18]
0x180008568  mov     r14d, [rsp+78h+arg_10]
0x180008570  mov     rdi, [rsp+78h+var_40]
0x180008575  test    r14d, r14d
0x180008578  jz      short loc_1800085E3
0x18000857a  test    rdi, rdi
0x18000857d  jz      short loc_1800085E3
0x18000857f  mov     rcx, rdi; this
0x180008582  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180008587  mov     rcx, [rdi+28h]
0x18000858b  test    rcx, rcx
0x18000858e  jz      short loc_180008596
0x180008590  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008596  cmp     qword ptr [rdi], 0
0x18000859a  jz      short loc_1800085A5
0x18000859c  mov     rcx, rdi; Binding
0x18000859f  call    cs:__imp_RpcBindingFree
0x1800085a5  lea     rcx, [rdi+8]; Binding
0x1800085a9  cmp     qword ptr [rcx], 0
0x1800085ad  jz      short loc_1800085B5
0x1800085af  call    cs:__imp_RpcBindingFree
0x1800085b5  lea     rcx, [rdi+10h]; Binding
0x1800085b9  cmp     qword ptr [rcx], 0
0x1800085bd  jnz     loc_18000870E
0x1800085c3  cmp     qword ptr [rsi], 0
0x1800085c7  jnz     loc_180008719
0x1800085cd  mov     rcx, [rdi+20h]; void *
0x1800085d1  test    rcx, rcx
0x1800085d4  jnz     loc_180008727
0x1800085da  mov     rcx, rdi
0x1800085dd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800085e3  mov     eax, ebx
0x1800085e5  mov     rbx, [rsp+78h+arg_0]
0x1800085ed  add     rsp, 50h
0x1800085f1  pop     r15
0x1800085f3  pop     r14
0x1800085f5  pop     r12
0x1800085f7  pop     rdi
0x1800085f8  pop     rsi
0x1800085f9  retn
0x1800085fa  call    ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x1800085ff  jmp     loc_1800084D8
0x180008604  mov     ecx, esi; int
0x180008606  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000860b  mov     r8d, esi
0x18000860e  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180008615  mov     ecx, 8; int
0x18000861a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000861f  jmp     loc_1800084A3
0x180008624  mov     rcx, rdi; this
0x180008627  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000862c  cmp     eax, 800706BAh
0x180008631  jz      loc_1800086CD
0x180008637  mov     rcx, rdi; this
0x18000863a  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000863f  jmp     loc_1800084A3
0x180008644  lea     r8, Name; "Global\\TermSrvReadyEvent"
0x18000864b  xor     edx, edx; bInheritHandle
0x18000864d  mov     ecx, 100000h; dwDesiredAccess
0x180008652  call    cs:__imp_OpenEventW
0x180008658  mov     rcx, rax; hObject
0x18000865b  test    rax, rax
0x18000865e  jz      short loc_180008684
0x180008660  xor     eax, eax
0x180008662  lock cmpxchg cs:?g_ReadyEventHandle@@3PEAXEA, rcx; void * g_ReadyEventHandle
0x18000866b  jz      loc_1800083D5
0x180008671  call    cs:__imp_CloseHandle
0x180008677  jmp     loc_1800083D5
0x18000867c  mov     rax, rbx
0x18000867f  jmp     loc_1800084D8
0x180008684  call    cs:__imp_GetLastError
0x18000868a  test    eax, eax
0x18000868c  jle     short loc_180008696
0x18000868e  movzx   eax, ax
0x180008691  or      eax, 80070000h
0x180008696  mov     r8d, eax
0x180008699  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\TermSrvReadyEvent ) "...
0x1800086a0  mov     ecx, 8; int
0x1800086a5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800086aa  jmp     loc_1800083E7
0x1800086af  call    cs:__imp_GetLastError
0x1800086b5  mov     ebx, eax
0x1800086b7  test    eax, eax
0x1800086b9  jle     loc_180008575
0x1800086bf  movzx   ebx, ax
0x1800086c2  or      ebx, 80070000h
0x1800086c8  jmp     loc_180008575
0x1800086cd  mov     [rdi+34h], r14d
0x1800086d1  jmp     loc_180008637
0x1800086d6  mov     rdi, rbx
0x1800086d9  mov     [rsp+78h+var_40], rbx
0x1800086de  jmp     loc_1800084A8
0x1800086e3  mov     r14d, ebx
0x1800086e6  mov     [rsp+78h+arg_10], ebx
0x1800086ed  mov     ecx, 0Eh; dwErrCode
0x1800086f2  call    cs:__imp_SetLastError
0x1800086f8  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800086ff  mov     ecx, 8; int
0x180008704  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008709  jmp     loc_1800084B9
0x18000870e  call    cs:__imp_RpcBindingFree
0x180008714  jmp     loc_1800085C3
0x180008719  mov     rcx, rsi; Binding
0x18000871c  call    cs:__imp_RpcBindingFree
0x180008722  jmp     loc_1800085CD
0x180008727  call    ?Legacy_WinStationCloseServer@@YAEPEAX@Z; Legacy_WinStationCloseServer(void *)
0x18000872c  jmp     loc_1800085DA
0x180030310  push    rbp
0x180030312  sub     rsp, 30h
0x180030316  mov     rbp, rdx
0x180030319  mov     rcx, [rcx]
0x18003031c  mov     ecx, [rcx]; ExceptionCode
0x18003031e  call    cs:__imp_I_RpcExceptionFilter
0x180030324  nop
0x180030325  add     rsp, 30h
0x180030329  pop     rbp
0x18003032a  retn
```
