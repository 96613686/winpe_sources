# WsImpersonateAndGetSessionId

- ea: `0x180008048`
- end: `0x1800081a9`
- name: `WsImpersonateAndGetSessionId`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008950`

## callees

- `0x180008048`
- `0x1800081b0`
- `0x180031878`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x1800080dc`
- `ntdll!NtOpenThreadToken` at `0x1800080dc`
- `ntdll!NtClose` at `0x180008131`
- `ntdll!NtClose` at `0x180008131`
- `ntdll!NtQueryInformationToken` at `0x180008115`
- `ntdll!NtQueryInformationToken` at `0x180008115`
- `RPCRT4!RpcImpersonateClient` at `0x18000806e`
- `RPCRT4!RpcImpersonateClient` at `0x18000806e`
- `RPCRT4!RpcRevertToSelf` at `0x180008147`
- `RPCRT4!RpcRevertToSelf` at `0x180008147`

## pseudocode

```c
__int64 __fastcall WsImpersonateAndGetSessionId(_DWORD *a1)
{
  RPC_STATUS v2; // eax
  int v3; // r8d
  int v5; // ebx
  unsigned int v6; // esi
  int v7; // ebx
  RPC_STATUS v8; // eax
  int v9; // r8d
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v2 = RpcImpersonateClient(0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v3, (unsigned int)"unknown", 0, v2);
    }
    return 5;
  }
  else
  {
    v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    v6 = NetpNtStatusToApiStatus(v5);
    if ( v5 >= 0 )
    {
      v7 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
      v6 = NetpNtStatusToApiStatus(v7);
      NtClose(TokenHandle);
      if ( v7 >= 0 )
        *a1 = TokenInformation;
    }
    v8 = RpcRevertToSelf();
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v9, (unsigned int)"unknown", 0, v8);
      }
      __fastfail(7u);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x180008048  push    rbx
0x18000804a  push    rsi
0x18000804b  push    rdi
0x18000804c  sub     rsp, 30h
0x180008050  mov     rdi, rcx
0x180008053  mov     [rsp+48h+TokenHandle], 0
0x18000805c  xor     ecx, ecx; BindingHandle
0x18000805e  mov     [rsp+48h+TokenInformation], 0
0x180008066  mov     [rsp+48h+arg_10], 0
0x18000806e  call    cs:__imp_RpcImpersonateClient
0x180008075  nop     dword ptr [rax+rax+00h]
0x18000807a  test    eax, eax
0x18000807c  jz      short loc_1800080C8
0x18000807e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180008085  lea     rdx, WPP_GLOBAL_Control
0x18000808c  cmp     rcx, rdx
0x18000808f  jz      short loc_1800080BE
0x180008091  test    byte ptr [rcx+1Ch], 4
0x180008095  jz      short loc_1800080BE
0x180008097  cmp     byte ptr [rcx+19h], 1
0x18000809b  jb      short loc_1800080BE
0x18000809d  mov     rcx, [rcx+10h]
0x1800080a1  lea     r9, aUnknown; "unknown"
0x1800080a8  mov     [rsp+48h+var_20], eax
0x1800080ac  mov     edx, 0Ah
0x1800080b1  mov     dword ptr [rsp+48h+ReturnLength], 0
0x1800080b9  call    WPP_SF_sdL
0x1800080be  mov     eax, 5
0x1800080c3  jmp     loc_1800081A0
0x1800080c8  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800080cd  mov     r8b, 1; OpenAsSelf
0x1800080d0  mov     edx, 8; DesiredAccess
0x1800080d5  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800080dc  call    cs:__imp_NtOpenThreadToken
0x1800080e3  nop     dword ptr [rax+rax+00h]
0x1800080e8  mov     ecx, eax; Status
0x1800080ea  mov     ebx, eax
0x1800080ec  call    NetpNtStatusToApiStatus
0x1800080f1  mov     esi, eax
0x1800080f3  test    ebx, ebx
0x1800080f5  js      short loc_180008147
0x1800080f7  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800080fc  lea     rax, [rsp+48h+arg_10]
0x180008101  mov     r9d, 4; TokenInformationLength
0x180008107  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000810c  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180008111  lea     edx, [r9+8]; TokenInformationClass
0x180008115  call    cs:__imp_NtQueryInformationToken
0x18000811c  nop     dword ptr [rax+rax+00h]
0x180008121  mov     ecx, eax; Status
0x180008123  mov     ebx, eax
0x180008125  call    NetpNtStatusToApiStatus
0x18000812a  mov     rcx, [rsp+48h+TokenHandle]; Handle
0x18000812f  mov     esi, eax
0x180008131  call    cs:__imp_NtClose
0x180008138  nop     dword ptr [rax+rax+00h]
0x18000813d  test    ebx, ebx
0x18000813f  js      short loc_180008147
0x180008141  mov     eax, [rsp+48h+TokenInformation]
0x180008145  mov     [rdi], eax
0x180008147  call    cs:__imp_RpcRevertToSelf
0x18000814e  nop     dword ptr [rax+rax+00h]
0x180008153  test    eax, eax
0x180008155  jz      short loc_18000819E
0x180008157  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000815e  lea     rdx, WPP_GLOBAL_Control
0x180008165  cmp     rcx, rdx
0x180008168  jz      short loc_180008197
0x18000816a  test    byte ptr [rcx+1Ch], 4
0x18000816e  jz      short loc_180008197
0x180008170  cmp     byte ptr [rcx+19h], 1
0x180008174  jb      short loc_180008197
0x180008176  mov     rcx, [rcx+10h]
0x18000817a  lea     r9, aUnknown; "unknown"
0x180008181  mov     [rsp+48h+var_20], eax
0x180008185  mov     edx, 0Bh
0x18000818a  mov     dword ptr [rsp+48h+ReturnLength], 0
0x180008192  call    WPP_SF_sdL
0x180008197  mov     ecx, 7
0x18000819c  int     29h; Win8: RtlFailFast(ecx)
0x18000819e  mov     eax, esi
0x1800081a0  add     rsp, 30h
0x1800081a4  pop     rdi
0x1800081a5  pop     rsi
0x1800081a6  pop     rbx
0x1800081a7  retn
```
