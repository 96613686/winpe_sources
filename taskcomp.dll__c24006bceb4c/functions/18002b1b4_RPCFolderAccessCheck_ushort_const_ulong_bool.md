# RPCFolderAccessCheck(ushort const *,ulong,bool)

- ea: `0x18002b1b4`
- end: `0x18002b233`
- name: `?RPCFolderAccessCheck@@YAJPEBGK_N@Z`
- size: `127`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD DesiredAccess)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180003500`
- `0x180004820`
- `0x180015280`

## callees

- `0x18002af30`
- `0x18002b1b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b1f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b1f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b1dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b1dc`
- `RPCRT4!RpcRevertToSelf` at `0x18002b1fb`
- `RPCRT4!RpcRevertToSelf` at `0x18002b1fb`
- `RPCRT4!RpcImpersonateClient` at `0x18002b1c9`
- `RPCRT4!RpcImpersonateClient` at `0x18002b1c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b222`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002b1b4  push    rbx
0x18002b1b6  push    rbp
0x18002b1b7  push    rsi
0x18002b1b8  push    rdi
0x18002b1b9  sub     rsp, 28h
0x18002b1bd  mov     rbp, rcx
0x18002b1c0  mov     esi, edx
0x18002b1c2  xor     ecx, ecx; BindingHandle
0x18002b1c4  mov     edi, 80070005h
0x18002b1c9  call    cs:__imp_RpcImpersonateClient
0x18002b1cf  test    eax, eax
0x18002b1d1  jnz     short loc_18002B228
0x18002b1d3  mov     [rsp+48h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002b1dc  call    cs:__imp_GetCurrentThread
0x18002b1e2  mov     edx, 8; DesiredAccess
0x18002b1e7  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18002b1ec  mov     rcx, rax; ThreadHandle
0x18002b1ef  lea     r8d, [rdx-7]; OpenAsSelf
0x18002b1f3  call    cs:__imp_OpenThreadToken
0x18002b1f9  mov     ebx, eax
0x18002b1fb  call    cs:__imp_RpcRevertToSelf
0x18002b201  test    ebx, ebx
0x18002b203  jz      short loc_18002B217
0x18002b205  mov     rdx, [rsp+48h+TokenHandle]; ClientToken
0x18002b20a  mov     r8d, esi; DesiredAccess
0x18002b20d  mov     rcx, rbp; lpFileName
0x18002b210  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x18002b215  mov     edi, eax
0x18002b217  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18002b21c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b220  jz      short loc_18002B228
0x18002b222  call    cs:__imp_CloseHandle
0x18002b228  mov     eax, edi
0x18002b22a  add     rsp, 28h
0x18002b22e  pop     rdi
0x18002b22f  pop     rsi
0x18002b230  pop     rbp
0x18002b231  pop     rbx
0x18002b232  retn
```
