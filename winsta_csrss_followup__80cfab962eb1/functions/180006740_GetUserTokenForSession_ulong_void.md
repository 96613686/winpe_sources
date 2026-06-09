# GetUserTokenForSession(ulong,void * *)

- ea: `0x180006740`
- end: `0x180006b17`
- name: `?GetUserTokenForSession@@YAJKPEAPEAX@Z`
- size: `983`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800152d0`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800066d0`
- `0x180006740`
- `0x180007690`
- `0x180020c90`
- `0x1800249e8`
- `0x180024a1c`
- `0x18002e180`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006992`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006992`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006933`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006933`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ac6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a7d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180006a0e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180006a0e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006771`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a33`
- `RPCRT4!RpcBindingFree` at `0x180006948`
- `RPCRT4!RpcBindingFree` at `0x18000695e`
- `RPCRT4!RpcBindingFree` at `0x180006ae8`
- `RPCRT4!RpcBindingFree` at `0x180006afc`
- `RPCRT4!RpcBindingFree` at `0x180006948`
- `RPCRT4!RpcBindingFree` at `0x18000695e`
- `RPCRT4!RpcBindingFree` at `0x180006ae8`
- `RPCRT4!RpcBindingFree` at `0x180006afc`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003303e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003303e`
- `RPCRT4!NdrClientCall3` at `0x1800068bf`
- `RPCRT4!NdrClientCall3` at `0x1800068bf`

## string_xrefs

- `0x1800069ca`: `StringCchCopy failed: %x`
- `0x180006a00`: `Global\TermSrvReadyEvent`
- `0x1800068ee`: `RpcGetUserToken threw an exception: 0x%x`
- `0x180006a67`: `OpenEvent( Global\TermSrvReadyEvent ) failed: 0x%x`

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
      v9 = &dword_18003FF34;
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
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v5) == -2147023174 )
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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351D0, 0, 0, LSMBinding, a1, a2).Pointer;
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
0x180006740  mov     [rsp+arg_0], rbx
0x180006745  push    rsi
0x180006746  push    rdi
0x180006747  push    r12
0x180006749  push    r14
0x18000674b  push    r15
0x18000674d  sub     rsp, 50h
0x180006751  mov     r15, rdx
0x180006754  mov     r12d, ecx
0x180006757  cmp     cs:?g_ReadyEventHandle@@3PEAXEA, 0; void * g_ReadyEventHandle
0x18000675f  jz      loc_180006A00
0x180006765  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000676a  mov     rcx, cs:?g_ReadyEventHandle@@3PEAXEA; hHandle
0x180006771  call    cs:__imp_WaitForSingleObject
0x180006778  nop     dword ptr [rax+rax+00h]
0x18000677d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006784  mov     ecx, 40h ; '@'; unsigned __int64
0x180006789  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000678e  mov     rdi, rax
0x180006791  xor     ebx, ebx
0x180006793  mov     r14d, 1
0x180006799  test    rax, rax
0x18000679c  jz      loc_180006AAA
0x1800067a2  mov     [rax], rbx
0x1800067a5  mov     [rax+8], rbx
0x1800067a9  mov     [rax+10h], rbx
0x1800067ad  mov     [rax+18h], rbx
0x1800067b1  mov     [rax+20h], rbx
0x1800067b5  mov     [rax+28h], rbx
0x1800067b9  mov     [rax+30h], r14
0x1800067bd  mov     [rax+38h], rbx
0x1800067c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800067c8  mov     ecx, 2; unsigned __int64
0x1800067cd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800067d2  mov     r9, rax
0x1800067d5  mov     [rdi+28h], rax
0x1800067d9  test    rax, rax
0x1800067dc  jz      short loc_18000683C
0x1800067de  mov     ecx, 7FFFFFFEh
0x1800067e3  lea     rdx, dword_18003FF34
0x1800067ea  mov     r10d, r14d
0x1800067ed  nop     dword ptr [rax]
0x1800067f0  test    rcx, rcx
0x1800067f3  jz      short loc_180006811
0x1800067f5  movzx   eax, word ptr [rdx]
0x1800067f8  test    ax, ax
0x1800067fb  jz      short loc_180006811
0x1800067fd  add     rdx, 2
0x180006801  mov     [r9], ax
0x180006805  add     r9, 2
0x180006809  dec     rcx
0x18000680c  sub     r10, r14
0x18000680f  jnz     short loc_1800067F0
0x180006811  mov     esi, 8007007Ah
0x180006816  test    r10, r10
0x180006819  cmovnz  esi, ebx
0x18000681c  lea     rax, [r9-2]
0x180006820  cmovnz  rax, r9
0x180006824  mov     [rax], bx
0x180006827  jz      loc_1800069C0
0x18000682d  cmp     [rdi+18h], rbx
0x180006831  jnz     short loc_18000683C
0x180006833  cmp     [rdi+30h], ebx
0x180006836  jz      loc_1800069E0
0x18000683c  mov     [rsp+78h+var_40], rdi
0x180006841  test    rdi, rdi
0x180006844  jz      loc_180006AB7
0x18000684a  mov     [rsp+78h+arg_10], r14d
0x180006852  lea     rsi, [rdi+18h]
0x180006856  test    rdi, rdi
0x180006859  jz      loc_180006A44
0x18000685f  mov     rcx, rdi; Binding
0x180006862  cmp     qword ptr [rsi], 0
0x180006866  jz      loc_1800069B6
0x18000686c  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x180006871  mov     [rsp+78h+arg_18], rsi
0x180006879  test    rax, rax
0x18000687c  jz      loc_180006A7D
0x180006882  test    rdi, rdi
0x180006885  jz      short loc_18000689E
0x180006887  mov     rcx, rdi; Binding
0x18000688a  cmp     qword ptr [rsi], 0
0x18000688e  jz      short loc_180006897
0x180006890  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x180006895  jmp     short loc_1800068A1
0x180006897  call    ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x18000689c  jmp     short loc_1800068A1
0x18000689e  mov     rax, rbx
0x1800068a1  mov     [rsp+78h+var_38], rbx
0x1800068a6  mov     [rsp+78h+var_50], r15
0x1800068ab  mov     [rsp+78h+var_58], r12d
0x1800068b0  mov     r9, rax
0x1800068b3  xor     r8d, r8d; pReturnValue
0x1800068b6  xor     edx, edx; nProcNum
0x1800068b8  lea     rcx, stru_1800351D0; pProxyInfo
0x1800068bf  call    cs:__imp_NdrClientCall3
0x1800068c6  nop     dword ptr [rax+rax+00h]
0x1800068cb  mov     rbx, rax
0x1800068ce  mov     [rsp+78h+var_38], rax
0x1800068d3  mov     [rsp+78h+var_48], eax
0x1800068d7  jmp     short loc_180006914
0x1800068d9  test    eax, eax
0x1800068db  jle     short loc_1800068E5
0x1800068dd  movzx   eax, ax
0x1800068e0  or      eax, 80070000h
0x1800068e5  mov     ebx, eax
0x1800068e7  mov     [rsp+78h+var_48], eax
0x1800068eb  mov     r8d, eax
0x1800068ee  lea     rdx, aRpcgetusertoke; "RpcGetUserToken threw an exception: 0x%"...
0x1800068f5  mov     ecx, 8; int
0x1800068fa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800068ff  mov     rsi, [rsp+78h+arg_18]
0x180006907  mov     r14d, [rsp+78h+arg_10]
0x18000690f  mov     rdi, [rsp+78h+var_40]
0x180006914  test    r14d, r14d
0x180006917  jz      loc_18000699E
0x18000691d  test    rdi, rdi
0x180006920  jz      short loc_18000699E
0x180006922  mov     rcx, rdi; this
0x180006925  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000692a  mov     rcx, [rdi+28h]
0x18000692e  test    rcx, rcx
0x180006931  jz      short loc_18000693F
0x180006933  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000693a  nop     dword ptr [rax+rax+00h]
0x18000693f  cmp     qword ptr [rdi], 0
0x180006943  jz      short loc_180006954
0x180006945  mov     rcx, rdi; Binding
0x180006948  call    cs:__imp_RpcBindingFree
0x18000694f  nop     dword ptr [rax+rax+00h]
0x180006954  lea     rcx, [rdi+8]; Binding
0x180006958  cmp     qword ptr [rcx], 0
0x18000695c  jz      short loc_18000696A
0x18000695e  call    cs:__imp_RpcBindingFree
0x180006965  nop     dword ptr [rax+rax+00h]
0x18000696a  lea     rcx, [rdi+10h]; Binding
0x18000696e  cmp     qword ptr [rcx], 0
0x180006972  jnz     loc_180006AE8
0x180006978  cmp     qword ptr [rsi], 0
0x18000697c  jnz     loc_180006AF9
0x180006982  mov     rcx, [rdi+20h]; void *
0x180006986  test    rcx, rcx
0x180006989  jnz     loc_180006B0D
0x18000698f  mov     rcx, rdi
0x180006992  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006999  nop     dword ptr [rax+rax+00h]
0x18000699e  mov     eax, ebx
0x1800069a0  mov     rbx, [rsp+78h+arg_0]
0x1800069a8  add     rsp, 50h
0x1800069ac  pop     r15
0x1800069ae  pop     r14
0x1800069b0  pop     r12
0x1800069b2  pop     rdi
0x1800069b3  pop     rsi
0x1800069b4  retn
0x1800069b6  call    ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x1800069bb  jmp     loc_180006871
0x1800069c0  mov     ecx, esi; int
0x1800069c2  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800069c7  mov     r8d, esi
0x1800069ca  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x1800069d1  mov     ecx, 8; int
0x1800069d6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800069db  jmp     loc_18000683C
0x1800069e0  mov     rcx, rdi; this
0x1800069e3  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x1800069e8  cmp     eax, 800706BAh
0x1800069ed  jz      loc_180006AA1
0x1800069f3  mov     rcx, rdi; this
0x1800069f6  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x1800069fb  jmp     loc_18000683C
0x180006a00  lea     r8, Name; "Global\\TermSrvReadyEvent"
0x180006a07  xor     edx, edx; bInheritHandle
0x180006a09  mov     ecx, 100000h; dwDesiredAccess
0x180006a0e  call    cs:__imp_OpenEventW
0x180006a15  nop     dword ptr [rax+rax+00h]
0x180006a1a  mov     rcx, rax; hObject
0x180006a1d  test    rax, rax
0x180006a20  jz      short loc_180006A4C
0x180006a22  xor     eax, eax
0x180006a24  lock cmpxchg cs:?g_ReadyEventHandle@@3PEAXEA, rcx; void * g_ReadyEventHandle
0x180006a2d  jz      loc_180006765
0x180006a33  call    cs:__imp_CloseHandle
0x180006a3a  nop     dword ptr [rax+rax+00h]
0x180006a3f  jmp     loc_180006765
0x180006a44  mov     rax, rbx
0x180006a47  jmp     loc_180006871
0x180006a4c  call    cs:__imp_GetLastError
0x180006a53  nop     dword ptr [rax+rax+00h]
0x180006a58  test    eax, eax
0x180006a5a  jle     short loc_180006A64
0x180006a5c  movzx   eax, ax
0x180006a5f  or      eax, 80070000h
0x180006a64  mov     r8d, eax
0x180006a67  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\TermSrvReadyEvent ) "...
0x180006a6e  mov     ecx, 8; int
0x180006a73  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006a78  jmp     loc_18000677D
0x180006a7d  call    cs:__imp_GetLastError
0x180006a84  nop     dword ptr [rax+rax+00h]
0x180006a89  mov     ebx, eax
0x180006a8b  test    eax, eax
0x180006a8d  jle     loc_180006914
0x180006a93  movzx   ebx, ax
0x180006a96  or      ebx, 80070000h
0x180006a9c  jmp     loc_180006914
0x180006aa1  mov     [rdi+34h], r14d
0x180006aa5  jmp     loc_1800069F3
0x180006aaa  mov     rdi, rbx
0x180006aad  mov     [rsp+78h+var_40], rbx
0x180006ab2  jmp     loc_180006841
0x180006ab7  mov     r14d, ebx
0x180006aba  mov     [rsp+78h+arg_10], ebx
0x180006ac1  mov     ecx, 0Eh; dwErrCode
0x180006ac6  call    cs:__imp_SetLastError
0x180006acd  nop     dword ptr [rax+rax+00h]
0x180006ad2  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180006ad9  mov     ecx, 8; int
0x180006ade  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006ae3  jmp     loc_180006852
0x180006ae8  call    cs:__imp_RpcBindingFree
0x180006aef  nop     dword ptr [rax+rax+00h]
0x180006af4  jmp     loc_180006978
0x180006af9  mov     rcx, rsi; Binding
0x180006afc  call    cs:__imp_RpcBindingFree
0x180006b03  nop     dword ptr [rax+rax+00h]
0x180006b08  jmp     loc_180006982
0x180006b0d  call    ?Legacy_WinStationCloseServer@@YAEPEAX@Z; Legacy_WinStationCloseServer(void *)
0x180006b12  jmp     loc_18000698F
0x180033030  push    rbp
0x180033032  sub     rsp, 30h
0x180033036  mov     rbp, rdx
0x180033039  mov     rcx, [rcx]
0x18003303c  mov     ecx, [rcx]; ExceptionCode
0x18003303e  call    cs:__imp_I_RpcExceptionFilter
0x180033045  nop     dword ptr [rax+rax+00h]
0x18003304a  nop
0x18003304b  add     rsp, 30h
0x18003304f  pop     rbp
0x180033050  retn
```
