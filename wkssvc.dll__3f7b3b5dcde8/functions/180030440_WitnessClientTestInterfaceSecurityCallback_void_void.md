# WitnessClientTestInterfaceSecurityCallback(void * *,void *)

- ea: `0x180030440`
- end: `0x18003055b`
- name: `?WitnessClientTestInterfaceSecurityCallback@@YAJPEAPEAXPEAX@Z`
- size: `283`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180022b54`
- `0x180022b7c`
- `0x180030440`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030512`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180030508`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180030508`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800304ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800304ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800304c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800304c2`
- `RPCRT4!RpcImpersonateClient` at `0x18003045d`
- `RPCRT4!RpcImpersonateClient` at `0x18003045d`
- `RPCRT4!RpcRevertToSelf` at `0x1800304cc`
- `RPCRT4!RpcRevertToSelf` at `0x1800304cc`

## pseudocode

```c
__int64 __fastcall WitnessClientTestInterfaceSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  DWORD LastError; // ebx
  PVOID *v3; // rcx
  __int64 v4; // rdx
  HANDLE CurrentThread; // rax
  WINBOOL IsMember; // [rsp+40h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+20h] BYREF

  TokenHandle = 0;
  IsMember = 1;
  LastError = RpcImpersonateClient(0);
  if ( LastError )
  {
    v3 = (PVOID *)WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control == &WPP_witness_GLOBAL_Control )
      return LastError;
    if ( (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) == 0 || !*((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      goto LABEL_15;
    v4 = 11;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    IsMember = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    LastError = RpcRevertToSelf();
    if ( !LastError )
    {
      if ( CheckTokenMembership(TokenHandle, g_AdminSid, &IsMember) )
        return LastError;
      LastError = GetLastError();
      if ( !LastError )
        return LastError;
      goto LABEL_14;
    }
    v3 = (PVOID *)WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control == &WPP_witness_GLOBAL_Control )
      return LastError;
    if ( (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) == 0 || !*((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      goto LABEL_15;
    v4 = 12;
  }
  WPP_SF_(v3[2], v4, WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids);
LABEL_14:
  v3 = (PVOID *)WPP_witness_GLOBAL_Control;
LABEL_15:
  if ( v3 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) )
    WPP_SF_d(v3[2], 13, WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180030440  mov     [rsp+arg_0], rbx
0x180030445  push    rsi
0x180030446  sub     rsp, 20h
0x18003044a  xor     ecx, ecx; BindingHandle
0x18003044c  mov     [rsp+28h+TokenHandle], 0
0x180030455  mov     [rsp+28h+IsMember], 1
0x18003045d  call    cs:__imp_RpcImpersonateClient
0x180030463  lea     rsi, WPP_witness_GLOBAL_Control
0x18003046a  mov     ebx, eax
0x18003046c  test    eax, eax
0x18003046e  jz      short loc_1800304AB
0x180030470  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180030477  cmp     rcx, rsi
0x18003047a  jz      loc_18003054E
0x180030480  test    byte ptr [rcx+1Ch], 1
0x180030484  jz      loc_180030525
0x18003048a  cmp     byte ptr [rcx+19h], 1
0x18003048e  jb      loc_180030525
0x180030494  mov     edx, 0Bh
0x180030499  mov     rcx, [rcx+10h]
0x18003049d  lea     r8, WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids
0x1800304a4  call    WPP_SF_
0x1800304a9  jmp     short loc_18003051E
0x1800304ab  call    cs:__imp_GetCurrentThread
0x1800304b1  mov     edx, 8; DesiredAccess
0x1800304b6  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800304bb  mov     rcx, rax; ThreadHandle
0x1800304be  lea     r8d, [rdx-7]; OpenAsSelf
0x1800304c2  call    cs:__imp_OpenThreadToken
0x1800304c8  mov     [rsp+28h+IsMember], eax
0x1800304cc  call    cs:__imp_RpcRevertToSelf
0x1800304d2  mov     ebx, eax
0x1800304d4  test    eax, eax
0x1800304d6  jz      short loc_1800304F7
0x1800304d8  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800304df  cmp     rcx, rsi
0x1800304e2  jz      short loc_18003054E
0x1800304e4  test    byte ptr [rcx+1Ch], 1
0x1800304e8  jz      short loc_180030525
0x1800304ea  cmp     byte ptr [rcx+19h], 1
0x1800304ee  jb      short loc_180030525
0x1800304f0  mov     edx, 0Ch
0x1800304f5  jmp     short loc_180030499
0x1800304f7  mov     rdx, cs:?g_AdminSid@@3PEAXEA; SidToCheck
0x1800304fe  lea     r8, [rsp+28h+IsMember]; IsMember
0x180030503  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180030508  call    cs:__imp_CheckTokenMembership
0x18003050e  test    eax, eax
0x180030510  jnz     short loc_18003054E
0x180030512  call    cs:__imp_GetLastError
0x180030518  mov     ebx, eax
0x18003051a  test    eax, eax
0x18003051c  jz      short loc_18003054E
0x18003051e  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180030525  cmp     rcx, rsi
0x180030528  jz      short loc_18003054E
0x18003052a  test    byte ptr [rcx+1Ch], 1
0x18003052e  jz      short loc_18003054E
0x180030530  cmp     byte ptr [rcx+19h], 1
0x180030534  jb      short loc_18003054E
0x180030536  mov     rcx, [rcx+10h]
0x18003053a  lea     r8, WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids
0x180030541  mov     edx, 0Dh
0x180030546  mov     r9d, ebx
0x180030549  call    WPP_SF_d
0x18003054e  mov     eax, ebx
0x180030550  mov     rbx, [rsp+28h+arg_0]
0x180030555  add     rsp, 20h
0x180030559  pop     rsi
0x18003055a  retn
```
