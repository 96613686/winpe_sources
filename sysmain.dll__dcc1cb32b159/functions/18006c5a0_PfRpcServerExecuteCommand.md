# PfRpcServerExecuteCommand

- ea: `0x18006c5a0`
- end: `0x18006c9b6`
- name: `PfRpcServerExecuteCommand`
- size: `1046`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18003df58`
- `0x180050744`
- `0x18005c148`
- `0x18005de88`
- `0x18005ffe4`
- `0x180065b58`
- `0x180069fa4`
- `0x18006c5a0`
- `0x18006f414`
- `0x180072808`
- `0x180078746`
- `0x180080fb8`
- `0x180096d40`
- `0x1800a8d1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c986`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c869`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c853`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c736`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c736`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c9a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c9a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c5f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c5f7`
- `RPCRT4!RpcImpersonateClient` at `0x18006c843`
- `RPCRT4!RpcImpersonateClient` at `0x18006c843`
- `RPCRT4!RpcRevertToSelf` at `0x18006c87b`
- `RPCRT4!RpcRevertToSelf` at `0x18006c886`
- `RPCRT4!RpcRevertToSelf` at `0x18006c87b`
- `RPCRT4!RpcRevertToSelf` at `0x18006c886`

## pseudocode

```c
__int64 __fastcall PfRpcServerExecuteCommand(RPC_BINDING_HANDLE BindingHandle, void *a2, _DWORD *a3)
{
  _DWORD *v4; // rdi
  unsigned int LastError; // ebx
  _DWORD *v8; // rax
  int *v9; // r14
  int v10; // ecx
  char v11; // bl
  int v12; // ecx
  unsigned int v13; // eax
  int v14; // r8d
  int v15; // r9d
  _DWORD *v16; // rdx
  __int64 v17; // rcx
  HANDLE CurrentThread; // rax
  unsigned int v19; // eax
  bool v20; // zf
  __int64 v21; // rcx
  bool v22; // zf
  __int64 v23; // rcx
  void *TokenHandle; // [rsp+40h] [rbp-48h] BYREF
  int v26; // [rsp+A8h] [rbp+20h] BYREF

  v26 = 0;
  v4 = 0;
  TokenHandle = 0;
  LastError = PfRpcServerSecurityCheckClient(BindingHandle, &v26);
  if ( LastError )
    goto LABEL_72;
  if ( *a3 < 0x18u )
  {
LABEL_3:
    LastError = 11;
    goto LABEL_72;
  }
  v8 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, (unsigned int)*a3);
  v4 = v8;
  if ( !v8 )
  {
    LastError = 8;
    goto LABEL_72;
  }
  memcpy_0(v8, a2, (unsigned int)*a3);
  v9 = v4 + 1;
  if ( (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1600LL) & 0xC00u) < 0x800 )
  {
    v10 = *v9;
    if ( (*v9 & 0x800000) == 0
      || v10 != 92274688
      && v10 != 109051905
      && (unsigned int)(v10 - 109051908) > 2
      && (unsigned int)(v10 - 75497473) > 3 )
    {
      LastError = 21;
      goto LABEL_72;
    }
  }
  v11 = v26;
  if ( (v26 & 1) != 0 && (*v9 & 0x800000) == 0 || (*v9 & 0x800000) != 0 && (HIBYTE(*v9) & (unsigned __int8)v26) == 0 )
    goto LABEL_15;
  if ( (unsigned int)PfSvServiceCommandVerify(v4, (unsigned int)*a3, 0) )
    goto LABEL_3;
  v12 = *v9;
  if ( (*v9 & 0x800000) == 0 )
  {
    if ( v12 == 0x8000 )
    {
      LastError = (v11 & 6) != 0 ? 1058 : 5;
      goto LABEL_72;
    }
    if ( v12 == 0x200000 )
    {
      if ( v4[2] == 2 )
        v22 = (v11 & 6) == 0;
      else
        v22 = (v11 & 4) == 0;
      if ( !v22 )
      {
        v23 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 3824LL);
        if ( !v23 )
          goto LABEL_45;
        v19 = RdBtRpcProcessCommand(v23, v4, (unsigned int)*a3);
        v20 = v4[2] == 2;
        goto LABEL_52;
      }
    }
    else if ( (v11 & 4) != 0 )
    {
      v17 = *(_QWORD *)&PfSvcGlobals;
      v16 = v4;
      goto LABEL_70;
    }
LABEL_15:
    LastError = 5;
    goto LABEL_72;
  }
  if ( v12 == 75497473 )
  {
    v13 = PfSvBootResPriPrefetch();
LABEL_71:
    LastError = v13;
    goto LABEL_72;
  }
  if ( v12 != 75497474 )
  {
    switch ( v12 )
    {
      case 75497476:
        v4[6] = (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 324LL) >> 9) & 1;
        goto LABEL_30;
      case 75497475:
      case 109051910:
        if ( !*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4088LL) )
        {
          LastError = 197;
          goto LABEL_72;
        }
        v20 = v12 == 75497475;
        v21 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4088LL);
        if ( v20 )
          PfIuRpcUptimeStatsQuery(v21, v4);
        else
          PfIuRpcHistoryGet(v21, v4);
LABEL_30:
        memcpy_0(a2, v4, (unsigned int)*a3);
        LastError = 0;
        goto LABEL_72;
      case 109051905:
      case 109051908:
        LastError = PfApRpcProcessExitCommand(v4);
        if ( LastError )
          goto LABEL_72;
        v12 = *v9;
        if ( *v9 == 109051908 )
        {
LABEL_37:
          memcpy_0(a2, v4, (unsigned int)*a3);
          goto LABEL_72;
        }
        break;
    }
    if ( v12 == 92274688 || (unsigned int)(v12 - 109051904) <= 1 || v12 == 75497472 || v12 == 109051907 )
      goto LABEL_44;
    v20 = v12 == 109051909;
    v16 = v4;
    v17 = *(_QWORD *)&PfSvcGlobals;
    if ( v20 )
    {
      LastError = PfSvCriticalAppAdd(*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4096LL), v4);
      if ( LastError )
        goto LABEL_72;
LABEL_44:
      if ( !*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4056LL) )
      {
LABEL_45:
        LastError = 1058;
        goto LABEL_72;
      }
      if ( *v9 != 75497472 )
      {
        LastError = RpcImpersonateClient(BindingHandle);
        if ( LastError )
          goto LABEL_72;
        CurrentThread = GetCurrentThread();
        if ( !OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
        {
          LastError = GetLastError();
          RpcRevertToSelf();
          goto LABEL_72;
        }
        RpcRevertToSelf();
      }
      v19 = PfApRpcProcessCommand(*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4056LL), v4, TokenHandle);
      v20 = v19 == 0;
LABEL_52:
      LastError = v19;
      if ( !v20 )
        goto LABEL_72;
      goto LABEL_37;
    }
LABEL_70:
    v13 = PfSvServiceCommandSend(v17 + 1616, v16, (unsigned int)*a3);
    goto LABEL_71;
  }
  LastError = PfSvGetPrefetchServiceThreadPrivileges(1);
  if ( !LastError )
  {
    if ( (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 324LL) & 0x800) != 0 )
      LastError = PfsPfnsQuerySetPriority(8, 8, v14, v15, (__int64)PfSvStandbyCoolingCallback, 0, 1);
    else
      LastError = 197;
    RevertToSelf();
  }
LABEL_72:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v4);
  return LastError;
}

```

## disassembly

```asm
0x18006c5a0  mov     rax, rsp
0x18006c5a3  push    rbx
0x18006c5a4  push    rbp
0x18006c5a5  push    rsi
0x18006c5a6  push    rdi
0x18006c5a7  push    r14
0x18006c5a9  push    r15
0x18006c5ab  sub     rsp, 58h
0x18006c5af  mov     rbp, rdx
0x18006c5b2  mov     dword ptr [rax+20h], 0
0x18006c5b9  xor     edi, edi
0x18006c5bb  lea     rdx, [rax+20h]
0x18006c5bf  mov     [rax-48h], rdi
0x18006c5c3  mov     rsi, r8
0x18006c5c6  mov     r15, rcx
0x18006c5c9  call    PfRpcServerSecurityCheckClient
0x18006c5ce  mov     ebx, eax
0x18006c5d0  test    eax, eax
0x18006c5d2  jnz     loc_18006C97C
0x18006c5d8  cmp     dword ptr [rsi], 18h
0x18006c5db  jnb     short loc_18006C5E7
0x18006c5dd  mov     ebx, 0Bh
0x18006c5e2  jmp     loc_18006C97C
0x18006c5e7  mov     rcx, cs:PfSvcGlobals
0x18006c5ee  xor     edx, edx; dwFlags
0x18006c5f0  mov     r8d, [rsi]; dwBytes
0x18006c5f3  mov     rcx, [rcx+58h]; hHeap
0x18006c5f7  call    cs:__imp_HeapAlloc
0x18006c5fd  mov     rdi, rax
0x18006c600  test    rax, rax
0x18006c603  jnz     short loc_18006C60D
0x18006c605  lea     ebx, [rax+8]
0x18006c608  jmp     loc_18006C97C
0x18006c60d  mov     r8d, [rsi]; Size
0x18006c610  mov     rdx, rbp; Src
0x18006c613  mov     rcx, rdi; void *
0x18006c616  call    memcpy_0
0x18006c61b  mov     rax, cs:PfSvcGlobals
0x18006c622  lea     r14, [rdi+4]
0x18006c626  mov     edx, 800000h
0x18006c62b  mov     ecx, [rax+640h]
0x18006c631  and     ecx, 0C00h
0x18006c637  cmp     ecx, 800h
0x18006c63d  jnb     short loc_18006C676
0x18006c63f  mov     ecx, [r14]
0x18006c642  test    edx, ecx
0x18006c644  jz      short loc_18006C66C
0x18006c646  cmp     ecx, 5800000h
0x18006c64c  jz      short loc_18006C676
0x18006c64e  cmp     ecx, 6800001h
0x18006c654  jz      short loc_18006C676
0x18006c656  lea     eax, [rcx-6800004h]
0x18006c65c  cmp     eax, 2
0x18006c65f  jbe     short loc_18006C676
0x18006c661  lea     eax, [rcx-4800001h]
0x18006c667  cmp     eax, 3
0x18006c66a  jbe     short loc_18006C676
0x18006c66c  mov     ebx, 15h
0x18006c671  jmp     loc_18006C97C
0x18006c676  mov     ebx, [rsp+88h+arg_18]
0x18006c67d  test    bl, 1
0x18006c680  jz      short loc_18006C691
0x18006c682  test    [r14], edx
0x18006c685  jnz     short loc_18006C691
0x18006c687  mov     ebx, 5
0x18006c68c  jmp     loc_18006C97C
0x18006c691  mov     eax, [r14]
0x18006c694  test    edx, eax
0x18006c696  jz      short loc_18006C69F
0x18006c698  shr     eax, 18h
0x18006c69b  test    bl, al
0x18006c69d  jz      short loc_18006C687
0x18006c69f  mov     edx, [rsi]
0x18006c6a1  xor     r8d, r8d
0x18006c6a4  mov     rcx, rdi
0x18006c6a7  call    PfSvServiceCommandVerify
0x18006c6ac  test    eax, eax
0x18006c6ae  jnz     loc_18006C5DD
0x18006c6b4  mov     ecx, [r14]
0x18006c6b7  bt      ecx, 17h
0x18006c6bb  jnb     loc_18006C8F1
0x18006c6c1  cmp     ecx, 4800001h
0x18006c6c7  jnz     short loc_18006C6D3
0x18006c6c9  call    PfSvBootResPriPrefetch
0x18006c6ce  jmp     loc_18006C97A
0x18006c6d3  cmp     ecx, 4800002h
0x18006c6d9  jnz     short loc_18006C741
0x18006c6db  mov     ecx, 1
0x18006c6e0  call    PfSvGetPrefetchServiceThreadPrivileges
0x18006c6e5  mov     ebx, eax
0x18006c6e7  test    eax, eax
0x18006c6e9  jnz     loc_18006C97C
0x18006c6ef  mov     rax, cs:PfSvcGlobals
0x18006c6f6  test    dword ptr [rax+144h], 800h
0x18006c700  jz      short loc_18006C731
0x18006c702  mov     ebx, 8
0x18006c707  mov     [rsp+88h+var_58], 1
0x18006c70f  lea     rax, PfSvStandbyCoolingCallback
0x18006c716  mov     [rsp+88h+var_60], 0
0x18006c71f  mov     edx, ebx
0x18006c721  mov     [rsp+88h+var_68], rax
0x18006c726  mov     ecx, ebx
0x18006c728  call    PfsPfnsQuerySetPriority
0x18006c72d  mov     ebx, eax
0x18006c72f  jmp     short loc_18006C736
0x18006c731  mov     ebx, 0C5h
0x18006c736  call    cs:__imp_RevertToSelf
0x18006c73c  jmp     loc_18006C97C
0x18006c741  cmp     ecx, 4800004h
0x18006c747  jnz     short loc_18006C774
0x18006c749  mov     rax, cs:PfSvcGlobals
0x18006c750  mov     ecx, [rax+144h]
0x18006c756  shr     ecx, 9
0x18006c759  and     ecx, 1
0x18006c75c  mov     [rdi+18h], ecx
0x18006c75f  mov     r8d, [rsi]; Size
0x18006c762  mov     rdx, rdi; Src
0x18006c765  mov     rcx, rbp; void *
0x18006c768  call    memcpy_0
0x18006c76d  xor     ebx, ebx
0x18006c76f  jmp     loc_18006C97C
0x18006c774  mov     edx, 4800003h
0x18006c779  cmp     ecx, edx
0x18006c77b  jz      loc_18006C8B6
0x18006c781  cmp     ecx, 6800006h
0x18006c787  jz      loc_18006C8B6
0x18006c78d  cmp     ecx, 6800001h
0x18006c793  jz      short loc_18006C79D
0x18006c795  cmp     ecx, 6800004h
0x18006c79b  jnz     short loc_18006C7CD
0x18006c79d  mov     rcx, rdi
0x18006c7a0  call    PfApRpcProcessExitCommand
0x18006c7a5  mov     ebx, eax
0x18006c7a7  test    eax, eax
0x18006c7a9  jnz     loc_18006C97C
0x18006c7af  mov     ecx, [r14]
0x18006c7b2  cmp     ecx, 6800004h
0x18006c7b8  jnz     short loc_18006C7CD
0x18006c7ba  mov     r8d, [rsi]; Size
0x18006c7bd  mov     rdx, rdi; Src
0x18006c7c0  mov     rcx, rbp; void *
0x18006c7c3  call    memcpy_0
0x18006c7c8  jmp     loc_18006C97C
0x18006c7cd  cmp     ecx, 5800000h
0x18006c7d3  jz      short loc_18006C81C
0x18006c7d5  lea     eax, [rcx-6800000h]
0x18006c7db  cmp     eax, 1
0x18006c7de  jbe     short loc_18006C81C
0x18006c7e0  cmp     ecx, 4800000h
0x18006c7e6  jz      short loc_18006C81C
0x18006c7e8  cmp     ecx, 6800003h
0x18006c7ee  jz      short loc_18006C81C
0x18006c7f0  cmp     ecx, 6800005h
0x18006c7f6  mov     rdx, rdi
0x18006c7f9  mov     rcx, cs:PfSvcGlobals
0x18006c800  jnz     loc_18006C96B
0x18006c806  mov     rcx, [rcx+1000h]
0x18006c80d  call    PfSvCriticalAppAdd
0x18006c812  mov     ebx, eax
0x18006c814  test    eax, eax
0x18006c816  jnz     loc_18006C97C
0x18006c81c  mov     rax, cs:PfSvcGlobals
0x18006c823  cmp     qword ptr [rax+0FD8h], 0
0x18006c82b  jnz     short loc_18006C837
0x18006c82d  mov     ebx, 422h
0x18006c832  jmp     loc_18006C97C
0x18006c837  cmp     dword ptr [r14], 4800000h
0x18006c83e  jz      short loc_18006C88C
0x18006c840  mov     rcx, r15; BindingHandle
0x18006c843  call    cs:__imp_RpcImpersonateClient
0x18006c849  mov     ebx, eax
0x18006c84b  test    eax, eax
0x18006c84d  jnz     loc_18006C97C
0x18006c853  call    cs:__imp_GetCurrentThread
0x18006c859  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x18006c85e  xor     r8d, r8d; OpenAsSelf
0x18006c861  mov     rcx, rax; ThreadHandle
0x18006c864  mov     edx, 20008h; DesiredAccess
0x18006c869  call    cs:__imp_OpenThreadToken
0x18006c86f  test    eax, eax
0x18006c871  jnz     short loc_18006C886
0x18006c873  call    cs:__imp_GetLastError
0x18006c879  mov     ebx, eax
0x18006c87b  call    cs:__imp_RpcRevertToSelf
0x18006c881  jmp     loc_18006C97C
0x18006c886  call    cs:__imp_RpcRevertToSelf
0x18006c88c  mov     rcx, cs:PfSvcGlobals
0x18006c893  mov     rdx, rdi
0x18006c896  mov     r8, [rsp+88h+TokenHandle]
0x18006c89b  mov     rcx, [rcx+0FD8h]
0x18006c8a2  call    PfApRpcProcessCommand
0x18006c8a7  test    eax, eax
0x18006c8a9  mov     ebx, eax
0x18006c8ab  jnz     loc_18006C97C
0x18006c8b1  jmp     loc_18006C7BA
0x18006c8b6  mov     rax, cs:PfSvcGlobals
0x18006c8bd  mov     r8, [rax+0FF8h]
0x18006c8c4  test    r8, r8
0x18006c8c7  jnz     short loc_18006C8D3
0x18006c8c9  mov     ebx, 0C5h
0x18006c8ce  jmp     loc_18006C97C
0x18006c8d3  cmp     ecx, edx
0x18006c8d5  mov     rdx, rdi
0x18006c8d8  mov     rcx, r8
0x18006c8db  jnz     short loc_18006C8E7
0x18006c8dd  call    PfIuRpcUptimeStatsQuery
0x18006c8e2  jmp     loc_18006C75F
0x18006c8e7  call    PfIuRpcHistoryGet
0x18006c8ec  jmp     loc_18006C75F
0x18006c8f1  cmp     ecx, 8000h
0x18006c8f7  jnz     short loc_18006C90E
0x18006c8f9  and     bl, 6
0x18006c8fc  neg     bl
0x18006c8fe  mov     ebx, 5
0x18006c903  sbb     eax, eax
0x18006c905  and     eax, 41Dh
0x18006c90a  add     ebx, eax
0x18006c90c  jmp     short loc_18006C97C
0x18006c90e  cmp     ecx, 200000h
0x18006c914  jnz     short loc_18006C958
0x18006c916  cmp     dword ptr [rdi+8], 2
0x18006c91a  jnz     short loc_18006C953
0x18006c91c  test    bl, 6
0x18006c91f  jz      loc_18006C687
0x18006c925  mov     rax, cs:PfSvcGlobals
0x18006c92c  mov     rcx, [rax+0EF0h]
0x18006c933  test    rcx, rcx
0x18006c936  jz      loc_18006C82D
0x18006c93c  mov     r8d, [rsi]
0x18006c93f  xor     r9d, r9d
0x18006c942  mov     rdx, rdi
0x18006c945  call    RdBtRpcProcessCommand
0x18006c94a  cmp     dword ptr [rdi+8], 2
0x18006c94e  jmp     loc_18006C8A9
0x18006c953  test    bl, 4
0x18006c956  jmp     short loc_18006C91F
0x18006c958  test    bl, 4
0x18006c95b  jz      loc_18006C687
0x18006c961  mov     rcx, cs:PfSvcGlobals
0x18006c968  mov     rdx, rdi
0x18006c96b  mov     r8d, [rsi]
0x18006c96e  add     rcx, 650h
0x18006c975  call    PfSvServiceCommandSend
0x18006c97a  mov     ebx, eax
0x18006c97c  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x18006c981  test    rcx, rcx
0x18006c984  jz      short loc_18006C98C
0x18006c986  call    cs:__imp_CloseHandle
0x18006c98c  test    rdi, rdi
0x18006c98f  jz      short loc_18006C9A7
0x18006c991  mov     rcx, cs:PfSvcGlobals
0x18006c998  mov     r8, rdi; lpMem
0x18006c99b  xor     edx, edx; dwFlags
0x18006c99d  mov     rcx, [rcx+58h]; hHeap
0x18006c9a1  call    cs:__imp_HeapFree
0x18006c9a7  mov     eax, ebx
0x18006c9a9  add     rsp, 58h
0x18006c9ad  pop     r15
0x18006c9af  pop     r14
0x18006c9b1  pop     rdi
0x18006c9b2  pop     rsi
0x18006c9b3  pop     rbp
0x18006c9b4  pop     rbx
0x18006c9b5  retn
```
