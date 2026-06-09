# RPCFolderAccessCheck(ushort const *,ulong,bool)

- ea: `0x18002cdb0`
- end: `0x18002ce4e`
- name: `?RPCFolderAccessCheck@@YAJPEBGK_N@Z`
- size: `158`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD DesiredAccess, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800036a0`
- `0x180004a40`
- `0x180016040`

## callees

- `0x18002cad4`
- `0x18002cdb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002cdfb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002cdfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002cdde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002cdde`
- `RPCRT4!RpcRevertToSelf` at `0x18002ce09`
- `RPCRT4!RpcRevertToSelf` at `0x18002ce09`
- `RPCRT4!RpcImpersonateClient` at `0x18002cdc5`
- `RPCRT4!RpcImpersonateClient` at `0x18002cdc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce36`

## pseudocode

```c
__int64 __fastcall RPCFolderAccessCheck(LPCWSTR lpFileName, DWORD DesiredAccess)
{
  unsigned int v4; // edi
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  v4 = -2147024891;
  if ( !RpcImpersonateClient(0) )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    RpcRevertToSelf();
    if ( v6 )
      v4 = FolderAccessCheck(lpFileName, TokenHandle, DesiredAccess);
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
  }
  return v4;
}

```

## disassembly

```asm
0x18002cdb0  push    rbx
0x18002cdb2  push    rbp
0x18002cdb3  push    rsi
0x18002cdb4  push    rdi
0x18002cdb5  sub     rsp, 28h
0x18002cdb9  mov     rbp, rcx
0x18002cdbc  mov     esi, edx
0x18002cdbe  xor     ecx, ecx; BindingHandle
0x18002cdc0  mov     edi, 80070005h
0x18002cdc5  call    cs:__imp_RpcImpersonateClient
0x18002cdcc  nop     dword ptr [rax+rax+00h]
0x18002cdd1  test    eax, eax
0x18002cdd3  jnz     short loc_18002CE42
0x18002cdd5  mov     [rsp+48h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002cdde  call    cs:__imp_GetCurrentThread
0x18002cde5  nop     dword ptr [rax+rax+00h]
0x18002cdea  mov     edx, 8; DesiredAccess
0x18002cdef  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18002cdf4  mov     rcx, rax; ThreadHandle
0x18002cdf7  lea     r8d, [rdx-7]; OpenAsSelf
0x18002cdfb  call    cs:__imp_OpenThreadToken
0x18002ce02  nop     dword ptr [rax+rax+00h]
0x18002ce07  mov     ebx, eax
0x18002ce09  call    cs:__imp_RpcRevertToSelf
0x18002ce10  nop     dword ptr [rax+rax+00h]
0x18002ce15  test    ebx, ebx
0x18002ce17  jz      short loc_18002CE2B
0x18002ce19  mov     rdx, [rsp+48h+TokenHandle]; ClientToken
0x18002ce1e  mov     r8d, esi; DesiredAccess
0x18002ce21  mov     rcx, rbp; lpFileName
0x18002ce24  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x18002ce29  mov     edi, eax
0x18002ce2b  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18002ce30  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ce34  jz      short loc_18002CE42
0x18002ce36  call    cs:__imp_CloseHandle
0x18002ce3d  nop     dword ptr [rax+rax+00h]
0x18002ce42  mov     eax, edi
0x18002ce44  add     rsp, 28h
0x18002ce48  pop     rdi
0x18002ce49  pop     rsi
0x18002ce4a  pop     rbp
0x18002ce4b  pop     rbx
0x18002ce4c  retn
```
