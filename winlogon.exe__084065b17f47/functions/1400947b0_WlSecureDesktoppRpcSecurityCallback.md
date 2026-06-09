# WlSecureDesktoppRpcSecurityCallback

- ea: `0x1400947b0`
- end: `0x14009488c`
- name: `WlSecureDesktoppRpcSecurityCallback`
- size: `220`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400947b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009486a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009486a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140094842`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140094874`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140094842`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140094874`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1400947db`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1400947db`
- `RPCRT4!RpcImpersonateClient` at `0x1400947f3`
- `RPCRT4!RpcImpersonateClient` at `0x1400947f3`
- `ntdll!NtOpenThreadToken` at `0x140094816`
- `ntdll!NtOpenThreadToken` at `0x140094816`
- `ntdll!NtQueryInformationToken` at `0x140094838`
- `ntdll!NtQueryInformationToken` at `0x140094838`

## pseudocode

```c
__int64 __fastcall WlSecureDesktoppRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  int v2; // edi
  unsigned int IsClientLocal; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-8h] BYREF
  unsigned int ClientLocalFlag; // [rsp+60h] [rbp+20h] BYREF
  int TokenInformation; // [rsp+68h] [rbp+28h] BYREF

  v2 = 0;
  TokenHandle = 0;
  ClientLocalFlag = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( !IsClientLocal )
  {
    if ( ClientLocalFlag )
    {
      IsClientLocal = RpcImpersonateClient(0);
      if ( !IsClientLocal )
      {
        v2 = 1;
        IsClientLocal = 5;
        if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle) >= 0
          && NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) >= 0 )
        {
          RevertToSelf();
          v2 = 0;
          if ( NtCurrentPeb()->SessionId == TokenInformation )
            IsClientLocal = 0;
        }
      }
    }
    else
    {
      IsClientLocal = 5;
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
    RevertToSelf();
  return IsClientLocal;
}

```

## disassembly

```asm
0x1400947b0  mov     [rsp-8+arg_0], rbx
0x1400947b5  mov     [rsp-8+arg_8], rdi
0x1400947ba  push    rbp
0x1400947bb  mov     rbp, rsp
0x1400947be  sub     rsp, 40h
0x1400947c2  xor     edi, edi
0x1400947c4  mov     [rbp+TokenHandle], 0
0x1400947cc  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x1400947d0  mov     [rbp+ClientLocalFlag], edi
0x1400947d3  xor     ecx, ecx; BindingHandle
0x1400947d5  mov     [rbp+TokenInformation], edi
0x1400947d8  mov     [rbp+var_10], edi
0x1400947db  call    cs:__imp_I_RpcBindingIsClientLocal
0x1400947e1  mov     ebx, eax
0x1400947e3  test    eax, eax
0x1400947e5  jnz     short loc_140094861
0x1400947e7  cmp     [rbp+ClientLocalFlag], edi
0x1400947ea  jnz     short loc_1400947F1
0x1400947ec  lea     ebx, [rdi+5]
0x1400947ef  jmp     short loc_140094861
0x1400947f1  xor     ecx, ecx; BindingHandle
0x1400947f3  call    cs:__imp_RpcImpersonateClient
0x1400947f9  mov     ebx, eax
0x1400947fb  test    eax, eax
0x1400947fd  jnz     short loc_140094861
0x1400947ff  lea     edi, [rax+1]
0x140094802  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140094809  mov     r8b, dil; OpenAsSelf
0x14009480c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140094810  lea     edx, [rax+8]; DesiredAccess
0x140094813  lea     ebx, [rax+5]
0x140094816  call    cs:__imp_NtOpenThreadToken
0x14009481c  test    eax, eax
0x14009481e  js      short loc_140094861
0x140094820  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140094824  lea     rax, [rbp+var_10]
0x140094828  lea     r9d, [rdi+3]; TokenInformationLength
0x14009482c  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140094831  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140094835  lea     edx, [rdi+0Bh]; TokenInformationClass
0x140094838  call    cs:__imp_NtQueryInformationToken
0x14009483e  test    eax, eax
0x140094840  js      short loc_140094861
0x140094842  call    cs:__imp_RevertToSelf
0x140094848  mov     rdx, gs:60h
0x140094851  xor     ecx, ecx
0x140094853  mov     eax, [rbp+TokenInformation]
0x140094856  xor     edi, edi
0x140094858  cmp     [rdx+2C0h], eax
0x14009485e  cmovz   ebx, ecx
0x140094861  mov     rcx, [rbp+TokenHandle]; hObject
0x140094865  test    rcx, rcx
0x140094868  jz      short loc_140094870
0x14009486a  call    cs:__imp_CloseHandle
0x140094870  test    edi, edi
0x140094872  jz      short loc_14009487A
0x140094874  call    cs:__imp_RevertToSelf
0x14009487a  mov     rdi, [rsp+40h+arg_8]
0x14009487f  mov     eax, ebx
0x140094881  mov     rbx, [rsp+40h+arg_0]
0x140094886  add     rsp, 40h
0x14009488a  pop     rbp
0x14009488b  retn
```
