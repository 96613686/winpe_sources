# DfsDsGetDcName

- ea: `0x1800279e0`
- end: `0x180027bb9`
- name: `DfsDsGetDcName`
- size: `473`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE BindingHandle@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d998`
- `0x1800279e0`
- `0x180036191`

## import_xrefs

- `ntdll!DbgPrint` at `0x180027a34`
- `ntdll!DbgPrint` at `0x180027a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027a71`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027a71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027b7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027b7a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027b8f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027b8f`
- `RPCRT4!RpcServerTestCancel` at `0x180027a04`
- `RPCRT4!RpcServerTestCancel` at `0x180027a04`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027a1f`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027b9f`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027a1f`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027b9f`
- `logoncli!DsGetDcNameW` at `0x180027ad1`
- `logoncli!DsGetDcNameW` at `0x180027ad1`
- `netutils!NetApiBufferFree` at `0x180027b66`
- `netutils!NetApiBufferFree` at `0x180027b66`

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
0x1800279e0  push    rbx
0x1800279e2  push    rbp
0x1800279e3  push    rsi
0x1800279e4  push    rdi
0x1800279e5  push    r14
0x1800279e7  push    r15
0x1800279e9  sub     rsp, 48h
0x1800279ed  mov     rbp, rcx
0x1800279f0  xor     r15d, r15d
0x1800279f3  mov     rcx, rdx; BindingHandle
0x1800279f6  mov     [rsp+78h+var_48], r15
0x1800279fb  mov     edi, r15d
0x1800279fe  mov     r14d, r9d
0x180027a01  mov     rbx, r8
0x180027a04  call    cs:__imp_RpcServerTestCancel
0x180027a0b  nop     dword ptr [rax+rax+00h]
0x180027a10  test    eax, eax
0x180027a12  jnz     short loc_180027A45
0x180027a14  mov     edx, 71Ah; ExceptionCode
0x180027a19  mov     rcx, rbp; pAsync
0x180027a1c  mov     ebx, r15d
0x180027a1f  call    cs:__imp_RpcAsyncAbortCall
0x180027a26  nop     dword ptr [rax+rax+00h]
0x180027a2b  mov     edx, eax
0x180027a2d  lea     rcx, aDfsgetdcnameRp; "DfsGetDcName: RPC has been cancelled by"...
0x180027a34  call    cs:__imp_DbgPrint
0x180027a3b  nop     dword ptr [rax+rax+00h]
0x180027a40  jmp     loc_180027B5C
0x180027a45  mov     rsi, [rsp+78h+arg_20]
0x180027a4d  test    rsi, rsi
0x180027a50  jnz     short loc_180027A5A
0x180027a52  lea     ebx, [rsi+57h]
0x180027a55  jmp     loc_180027B5C
0x180027a5a  test    rbx, rbx
0x180027a5d  jz      short loc_180027AB7
0x180027a5f  cmp     [rbx], r15w
0x180027a63  jbe     short loc_180027AB7
0x180027a65  movzx   edx, word ptr [rbx]
0x180027a68  mov     ecx, 40h ; '@'; uFlags
0x180027a6d  add     rdx, 2; uBytes
0x180027a71  call    cs:__imp_LocalAlloc
0x180027a78  nop     dword ptr [rax+rax+00h]
0x180027a7d  mov     rdi, rax
0x180027a80  test    rax, rax
0x180027a83  jnz     short loc_180027A98
0x180027a85  call    cs:__imp_GetLastError
0x180027a8c  nop     dword ptr [rax+rax+00h]
0x180027a91  mov     ebx, eax
0x180027a93  jmp     loc_180027B5C
0x180027a98  movzx   r9d, word ptr [rbx]; SourceSize
0x180027a9c  mov     rcx, rdi; Destination
0x180027a9f  mov     r8, [rbx+8]; Source
0x180027aa3  lea     rdx, [r9+2]; DestinationSize
0x180027aa7  call    memcpy_s
0x180027aac  movzx   ecx, word ptr [rbx]
0x180027aaf  shr     rcx, 1
0x180027ab2  mov     [rdi+rcx*2], r15w
0x180027ab7  lea     rax, [rsp+78h+var_48]
0x180027abc  xor     r9d, r9d; SiteName
0x180027abf  mov     [rsp+78h+DomainControllerInfo], rax; DomainControllerInfo
0x180027ac4  xor     r8d, r8d; DomainGuid
0x180027ac7  mov     rdx, rdi; DomainName
0x180027aca  mov     [rsp+78h+Flags], r14d; Flags
0x180027acf  xor     ecx, ecx; ComputerName
0x180027ad1  call    cs:__imp_DsGetDcNameW
0x180027ad8  nop     dword ptr [rax+rax+00h]
0x180027add  mov     ebx, eax
0x180027adf  test    eax, eax
0x180027ae1  jnz     short loc_180027B5C
0x180027ae3  mov     rax, [rsp+78h+var_48]
0x180027ae8  mov     r9, [rax]
0x180027aeb  jmp     short loc_180027AF1
0x180027aed  add     r9, 2
0x180027af1  cmp     word ptr [r9], 5Ch ; '\'
0x180027af6  jz      short loc_180027AED
0x180027af8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180027afc  inc     rdx
0x180027aff  cmp     [r9+rdx*2], r15w
0x180027b04  jnz     short loc_180027AFC
0x180027b06  cmp     dx, 1
0x180027b0a  jb      short loc_180027B26
0x180027b0c  movzx   ecx, dx
0x180027b0f  cmp     word ptr [r9+rcx*2-2], 2Eh ; '.'
0x180027b16  jnz     short loc_180027B26
0x180027b18  mov     eax, 0FFFFh
0x180027b1d  mov     [r9+rcx*2-2], r15w
0x180027b23  add     dx, ax
0x180027b26  movzx   eax, dx
0x180027b29  lea     rcx, ds:2[rax*2]
0x180027b31  movzx   eax, word ptr [rsi+2]
0x180027b35  cmp     rax, rcx
0x180027b38  jnb     short loc_180027B41
0x180027b3a  mov     ebx, 7Ah ; 'z'
0x180027b3f  jmp     short loc_180027B5C
0x180027b41  mov     rcx, [rsi+8]; void *
0x180027b45  add     dx, dx
0x180027b48  movzx   r8d, dx
0x180027b4c  mov     rdx, r9; Src
0x180027b4f  mov     [rsi], r8w
0x180027b53  add     r8, 2; Size
0x180027b57  call    memcpy_0
0x180027b5c  mov     rcx, [rsp+78h+var_48]; Buffer
0x180027b61  test    rcx, rcx
0x180027b64  jz      short loc_180027B72
0x180027b66  call    cs:__imp_NetApiBufferFree
0x180027b6d  nop     dword ptr [rax+rax+00h]
0x180027b72  test    rdi, rdi
0x180027b75  jz      short loc_180027B86
0x180027b77  mov     rcx, rdi; hMem
0x180027b7a  call    cs:__imp_LocalFree
0x180027b81  nop     dword ptr [rax+rax+00h]
0x180027b86  mov     rcx, rbp; pAsync
0x180027b89  test    ebx, ebx
0x180027b8b  jnz     short loc_180027B9D
0x180027b8d  xor     edx, edx; Reply
0x180027b8f  call    cs:__imp_RpcAsyncCompleteCall
0x180027b96  nop     dword ptr [rax+rax+00h]
0x180027b9b  jmp     short loc_180027BAB
0x180027b9d  mov     edx, ebx; ExceptionCode
0x180027b9f  call    cs:__imp_RpcAsyncAbortCall
0x180027ba6  nop     dword ptr [rax+rax+00h]
0x180027bab  add     rsp, 48h
0x180027baf  pop     r15
0x180027bb1  pop     r14
0x180027bb3  pop     rdi
0x180027bb4  pop     rsi
0x180027bb5  pop     rbp
0x180027bb6  pop     rbx
0x180027bb7  retn
```
