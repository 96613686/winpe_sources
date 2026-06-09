# WitnessClientTestInterfaceSecurityCallback(void * *,void *)

- ea: `0x180033200`
- end: `0x180033343`
- name: `?WitnessClientTestInterfaceSecurityCallback@@YAJPEAPEAXPEAX@Z`
- size: `323`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180024520`
- `0x180024550`
- `0x180033200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800332f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800332f3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800332e3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800332e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033274`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033274`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033291`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033291`
- `RPCRT4!RpcImpersonateClient` at `0x18003321d`
- `RPCRT4!RpcImpersonateClient` at `0x18003321d`
- `RPCRT4!RpcRevertToSelf` at `0x1800332a1`
- `RPCRT4!RpcRevertToSelf` at `0x1800332a1`

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
0x180033200  mov     [rsp+arg_0], rbx
0x180033205  push    rsi
0x180033206  sub     rsp, 20h
0x18003320a  xor     ecx, ecx; BindingHandle
0x18003320c  mov     [rsp+28h+TokenHandle], 0
0x180033215  mov     [rsp+28h+IsMember], 1
0x18003321d  call    cs:__imp_RpcImpersonateClient
0x180033224  nop     dword ptr [rax+rax+00h]
0x180033229  lea     rsi, WPP_witness_GLOBAL_Control
0x180033230  mov     ebx, eax
0x180033232  test    eax, eax
0x180033234  jz      short loc_180033274
0x180033236  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18003323d  cmp     rcx, rsi
0x180033240  jz      loc_180033335
0x180033246  test    byte ptr [rcx+1Ch], 1
0x18003324a  jz      loc_18003330C
0x180033250  cmp     byte ptr [rcx+19h], 1
0x180033254  jb      loc_18003330C
0x18003325a  mov     edx, 0Bh
0x18003325f  mov     rcx, [rcx+10h]
0x180033263  lea     r8, WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids
0x18003326a  call    WPP_SF_
0x18003326f  jmp     loc_180033305
0x180033274  call    cs:__imp_GetCurrentThread
0x18003327b  nop     dword ptr [rax+rax+00h]
0x180033280  mov     edx, 8; DesiredAccess
0x180033285  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18003328a  mov     rcx, rax; ThreadHandle
0x18003328d  lea     r8d, [rdx-7]; OpenAsSelf
0x180033291  call    cs:__imp_OpenThreadToken
0x180033298  nop     dword ptr [rax+rax+00h]
0x18003329d  mov     [rsp+28h+IsMember], eax
0x1800332a1  call    cs:__imp_RpcRevertToSelf
0x1800332a8  nop     dword ptr [rax+rax+00h]
0x1800332ad  mov     ebx, eax
0x1800332af  test    eax, eax
0x1800332b1  jz      short loc_1800332D2
0x1800332b3  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800332ba  cmp     rcx, rsi
0x1800332bd  jz      short loc_180033335
0x1800332bf  test    byte ptr [rcx+1Ch], 1
0x1800332c3  jz      short loc_18003330C
0x1800332c5  cmp     byte ptr [rcx+19h], 1
0x1800332c9  jb      short loc_18003330C
0x1800332cb  mov     edx, 0Ch
0x1800332d0  jmp     short loc_18003325F
0x1800332d2  mov     rdx, cs:?g_AdminSid@@3PEAXEA; SidToCheck
0x1800332d9  lea     r8, [rsp+28h+IsMember]; IsMember
0x1800332de  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1800332e3  call    cs:__imp_CheckTokenMembership
0x1800332ea  nop     dword ptr [rax+rax+00h]
0x1800332ef  test    eax, eax
0x1800332f1  jnz     short loc_180033335
0x1800332f3  call    cs:__imp_GetLastError
0x1800332fa  nop     dword ptr [rax+rax+00h]
0x1800332ff  mov     ebx, eax
0x180033301  test    eax, eax
0x180033303  jz      short loc_180033335
0x180033305  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18003330c  cmp     rcx, rsi
0x18003330f  jz      short loc_180033335
0x180033311  test    byte ptr [rcx+1Ch], 1
0x180033315  jz      short loc_180033335
0x180033317  cmp     byte ptr [rcx+19h], 1
0x18003331b  jb      short loc_180033335
0x18003331d  mov     rcx, [rcx+10h]
0x180033321  lea     r8, WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids
0x180033328  mov     edx, 0Dh
0x18003332d  mov     r9d, ebx
0x180033330  call    WPP_SF_d
0x180033335  mov     eax, ebx
0x180033337  mov     rbx, [rsp+28h+arg_0]
0x18003333c  add     rsp, 20h
0x180033340  pop     rsi
0x180033341  retn
```
