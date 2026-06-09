# DfsDsGetDcName

- ea: `0x180025bc0`
- end: `0x180025d5c`
- name: `DfsDsGetDcName`
- size: `412`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *, ULONG, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000cdf0`
- `0x180025bc0`
- `0x180033159`

## import_xrefs

- `ntdll!DbgPrint` at `0x180025c08`
- `ntdll!DbgPrint` at `0x180025c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025c3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025c3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025d30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025d30`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025d3f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025d3f`
- `RPCRT4!RpcServerTestCancel` at `0x180025be4`
- `RPCRT4!RpcServerTestCancel` at `0x180025be4`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025bf9`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025d49`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025bf9`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025d49`
- `logoncli!DsGetDcNameW` at `0x180025c93`
- `logoncli!DsGetDcNameW` at `0x180025c93`
- `netutils!NetApiBufferFree` at `0x180025d22`
- `netutils!NetApiBufferFree` at `0x180025d22`

## pseudocode

```c
RPC_STATUS __fastcall DfsDsGetDcName(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        unsigned __int16 *a3,
        ULONG a4,
        __int64 a5)
{
  WCHAR *v6; // rdi
  DWORD LastError; // ebx
  RPC_STATUS v10; // eax
  WCHAR *v11; // rax
  LPWSTR i; // r9
  __int64 v13; // rdx
  void *v14; // rcx
  __int64 v15; // r8
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+30h] [rbp-48h] BYREF

  DomainControllerInfo = 0;
  v6 = 0;
  if ( !RpcServerTestCancel(BindingHandle) )
  {
    LastError = 0;
    v10 = RpcAsyncAbortCall(pAsync, 0x71Au);
    DbgPrint("DfsGetDcName: RPC has been cancelled by client %X\n", v10);
    goto LABEL_22;
  }
  if ( !a5 )
  {
    LastError = 87;
    goto LABEL_22;
  }
  if ( a3 && *a3 )
  {
    v11 = (WCHAR *)LocalAlloc(0x40u, *a3 + 2LL);
    v6 = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      goto LABEL_22;
    }
    memcpy_s(v11, *a3 + 2LL, *((const void *const *)a3 + 1), *a3);
    v6[(unsigned __int64)*a3 >> 1] = 0;
  }
  LastError = DsGetDcNameW(0, v6, 0, 0, a4, &DomainControllerInfo);
  if ( !LastError )
  {
    for ( i = DomainControllerInfo->DomainControllerName; *i == 92; ++i )
      ;
    v13 = -1;
    do
      ++v13;
    while ( i[v13] );
    if ( (_WORD)v13 && i[(unsigned __int16)v13 - 1] == 46 )
    {
      i[(unsigned __int16)v13 - 1] = 0;
      LOWORD(v13) = v13 - 1;
    }
    if ( *(unsigned __int16 *)(a5 + 2) >= 2 * (unsigned __int64)(unsigned __int16)v13 + 2 )
    {
      v14 = *(void **)(a5 + 8);
      v15 = (unsigned __int16)(2 * v13);
      *(_WORD *)a5 = v15;
      memcpy_0(v14, i, v15 + 2);
    }
    else
    {
      LastError = 122;
    }
  }
LABEL_22:
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  if ( v6 )
    LocalFree(v6);
  if ( LastError )
    return RpcAsyncAbortCall(pAsync, LastError);
  else
    return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x180025bc0  push    rbx
0x180025bc2  push    rbp
0x180025bc3  push    rsi
0x180025bc4  push    rdi
0x180025bc5  push    r14
0x180025bc7  push    r15
0x180025bc9  sub     rsp, 48h
0x180025bcd  mov     rbp, rcx
0x180025bd0  xor     r15d, r15d
0x180025bd3  mov     rcx, rdx; BindingHandle
0x180025bd6  mov     [rsp+78h+var_48], r15
0x180025bdb  mov     edi, r15d
0x180025bde  mov     r14d, r9d
0x180025be1  mov     rbx, r8
0x180025be4  call    cs:__imp_RpcServerTestCancel
0x180025bea  test    eax, eax
0x180025bec  jnz     short loc_180025C13
0x180025bee  mov     edx, 71Ah; ExceptionCode
0x180025bf3  mov     rcx, rbp; pAsync
0x180025bf6  mov     ebx, r15d
0x180025bf9  call    cs:__imp_RpcAsyncAbortCall
0x180025bff  mov     edx, eax
0x180025c01  lea     rcx, aDfsgetdcnameRp; "DfsGetDcName: RPC has been cancelled by"...
0x180025c08  call    cs:__imp_DbgPrint
0x180025c0e  jmp     loc_180025D18
0x180025c13  mov     rsi, [rsp+78h+arg_20]
0x180025c1b  test    rsi, rsi
0x180025c1e  jnz     short loc_180025C28
0x180025c20  lea     ebx, [rsi+57h]
0x180025c23  jmp     loc_180025D18
0x180025c28  test    rbx, rbx
0x180025c2b  jz      short loc_180025C79
0x180025c2d  cmp     [rbx], r15w
0x180025c31  jbe     short loc_180025C79
0x180025c33  movzx   edx, word ptr [rbx]
0x180025c36  mov     ecx, 40h ; '@'; uFlags
0x180025c3b  add     rdx, 2; uBytes
0x180025c3f  call    cs:__imp_LocalAlloc
0x180025c45  mov     rdi, rax
0x180025c48  test    rax, rax
0x180025c4b  jnz     short loc_180025C5A
0x180025c4d  call    cs:__imp_GetLastError
0x180025c53  mov     ebx, eax
0x180025c55  jmp     loc_180025D18
0x180025c5a  movzx   r9d, word ptr [rbx]; SourceSize
0x180025c5e  mov     rcx, rdi; Destination
0x180025c61  mov     r8, [rbx+8]; Source
0x180025c65  lea     rdx, [r9+2]; DestinationSize
0x180025c69  call    memcpy_s
0x180025c6e  movzx   ecx, word ptr [rbx]
0x180025c71  shr     rcx, 1
0x180025c74  mov     [rdi+rcx*2], r15w
0x180025c79  lea     rax, [rsp+78h+var_48]
0x180025c7e  xor     r9d, r9d; SiteName
0x180025c81  mov     [rsp+78h+DomainControllerInfo], rax; DomainControllerInfo
0x180025c86  xor     r8d, r8d; DomainGuid
0x180025c89  mov     rdx, rdi; DomainName
0x180025c8c  mov     [rsp+78h+Flags], r14d; Flags
0x180025c91  xor     ecx, ecx; ComputerName
0x180025c93  call    cs:__imp_DsGetDcNameW
0x180025c99  mov     ebx, eax
0x180025c9b  test    eax, eax
0x180025c9d  jnz     short loc_180025D18
0x180025c9f  mov     rax, [rsp+78h+var_48]
0x180025ca4  mov     r9, [rax]
0x180025ca7  jmp     short loc_180025CAD
0x180025ca9  add     r9, 2
0x180025cad  cmp     word ptr [r9], 5Ch ; '\'
0x180025cb2  jz      short loc_180025CA9
0x180025cb4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180025cb8  inc     rdx
0x180025cbb  cmp     [r9+rdx*2], r15w
0x180025cc0  jnz     short loc_180025CB8
0x180025cc2  cmp     dx, 1
0x180025cc6  jb      short loc_180025CE2
0x180025cc8  movzx   ecx, dx
0x180025ccb  cmp     word ptr [r9+rcx*2-2], 2Eh ; '.'
0x180025cd2  jnz     short loc_180025CE2
0x180025cd4  mov     eax, 0FFFFh
0x180025cd9  mov     [r9+rcx*2-2], r15w
0x180025cdf  add     dx, ax
0x180025ce2  movzx   eax, dx
0x180025ce5  lea     rcx, ds:2[rax*2]
0x180025ced  movzx   eax, word ptr [rsi+2]
0x180025cf1  cmp     rax, rcx
0x180025cf4  jnb     short loc_180025CFD
0x180025cf6  mov     ebx, 7Ah ; 'z'
0x180025cfb  jmp     short loc_180025D18
0x180025cfd  mov     rcx, [rsi+8]; void *
0x180025d01  add     dx, dx
0x180025d04  movzx   r8d, dx
0x180025d08  mov     rdx, r9; Src
0x180025d0b  mov     [rsi], r8w
0x180025d0f  add     r8, 2; Size
0x180025d13  call    memcpy_0
0x180025d18  mov     rcx, [rsp+78h+var_48]; Buffer
0x180025d1d  test    rcx, rcx
0x180025d20  jz      short loc_180025D28
0x180025d22  call    cs:__imp_NetApiBufferFree
0x180025d28  test    rdi, rdi
0x180025d2b  jz      short loc_180025D36
0x180025d2d  mov     rcx, rdi; hMem
0x180025d30  call    cs:__imp_LocalFree
0x180025d36  mov     rcx, rbp; pAsync
0x180025d39  test    ebx, ebx
0x180025d3b  jnz     short loc_180025D47
0x180025d3d  xor     edx, edx; Reply
0x180025d3f  call    cs:__imp_RpcAsyncCompleteCall
0x180025d45  jmp     short loc_180025D4F
0x180025d47  mov     edx, ebx; ExceptionCode
0x180025d49  call    cs:__imp_RpcAsyncAbortCall
0x180025d4f  add     rsp, 48h
0x180025d53  pop     r15
0x180025d55  pop     r14
0x180025d57  pop     rdi
0x180025d58  pop     rsi
0x180025d59  pop     rbp
0x180025d5a  pop     rbx
0x180025d5b  retn
```
