# WitnessUpcallServerSecurityCallback

- ea: `0x180034c30`
- end: `0x180034df5`
- name: `WitnessUpcallServerSecurityCallback`
- size: `453`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180024520`
- `0x180024550`
- `0x180034c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d45`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180034d35`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180034d35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034da6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034da6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034ca8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034ca8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034cc5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034cc5`
- `RPCRT4!RpcImpersonateClient` at `0x180034c51`
- `RPCRT4!RpcImpersonateClient` at `0x180034c51`
- `RPCRT4!RpcRevertToSelf` at `0x180034cd3`
- `RPCRT4!RpcRevertToSelf` at `0x180034cd3`

## pseudocode

```c
__int64 __fastcall WitnessUpcallServerSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int LastError; // ebx
  PVOID *v3; // rcx
  __int64 v4; // rdx
  HANDLE CurrentThread; // rax
  BOOL v6; // edi
  DWORD v7; // eax
  WINBOOL IsMember; // [rsp+40h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+20h] BYREF

  TokenHandle = 0;
  IsMember = 1;
  LastError = RpcImpersonateClient(0);
  if ( LastError )
  {
    v3 = (PVOID *)WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      v4 = 10;
LABEL_6:
      WPP_SF_(v3[2], v4, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids);
LABEL_20:
      v3 = (PVOID *)WPP_witness_GLOBAL_Control;
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    LastError = RpcRevertToSelf();
    if ( LastError )
    {
      v3 = (PVOID *)WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        v4 = 11;
        goto LABEL_6;
      }
    }
    else
    {
      if ( !v6 )
      {
        LastError = GetLastError();
        goto LABEL_20;
      }
      if ( CheckTokenMembership(TokenHandle, LocalSystem, &IsMember) )
      {
        LastError = IsMember != 1 ? 5 : 0;
        goto LABEL_20;
      }
      v7 = GetLastError();
      LastError = v7;
      v3 = (PVOID *)WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 12, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v7);
        goto LABEL_20;
      }
    }
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v3 = (PVOID *)WPP_witness_GLOBAL_Control;
  }
  if ( v3 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 3u )
    WPP_SF_d(v3[2], 13, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180034c30  mov     rax, rsp
0x180034c33  mov     [rax+8], rbx
0x180034c37  mov     [rax+10h], rbp
0x180034c3b  push    rdi
0x180034c3c  sub     rsp, 20h
0x180034c40  xor     ecx, ecx; BindingHandle
0x180034c42  mov     qword ptr [rax+20h], 0
0x180034c4a  mov     dword ptr [rax+18h], 1
0x180034c51  call    cs:__imp_RpcImpersonateClient
0x180034c58  nop     dword ptr [rax+rax+00h]
0x180034c5d  lea     rbp, WPP_witness_GLOBAL_Control
0x180034c64  mov     ebx, eax
0x180034c66  test    eax, eax
0x180034c68  jz      short loc_180034CA8
0x180034c6a  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034c71  cmp     rcx, rbp
0x180034c74  jz      loc_180034D99
0x180034c7a  test    byte ptr [rcx+1Ch], 1
0x180034c7e  jz      loc_180034D99
0x180034c84  cmp     byte ptr [rcx+19h], 1
0x180034c88  jb      loc_180034D99
0x180034c8e  mov     edx, 0Ah
0x180034c93  mov     rcx, [rcx+10h]
0x180034c97  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180034c9e  call    WPP_SF_
0x180034ca3  jmp     loc_180034D92
0x180034ca8  call    cs:__imp_GetCurrentThread
0x180034caf  nop     dword ptr [rax+rax+00h]
0x180034cb4  mov     edx, 8; DesiredAccess
0x180034cb9  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180034cbe  mov     rcx, rax; ThreadHandle
0x180034cc1  lea     r8d, [rdx-7]; OpenAsSelf
0x180034cc5  call    cs:__imp_OpenThreadToken
0x180034ccc  nop     dword ptr [rax+rax+00h]
0x180034cd1  mov     edi, eax
0x180034cd3  call    cs:__imp_RpcRevertToSelf
0x180034cda  nop     dword ptr [rax+rax+00h]
0x180034cdf  mov     ebx, eax
0x180034ce1  test    eax, eax
0x180034ce3  jz      short loc_180034D10
0x180034ce5  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034cec  cmp     rcx, rbp
0x180034cef  jz      loc_180034D99
0x180034cf5  test    byte ptr [rcx+1Ch], 1
0x180034cf9  jz      loc_180034D99
0x180034cff  cmp     byte ptr [rcx+19h], 1
0x180034d03  jb      loc_180034D99
0x180034d09  mov     edx, 0Bh
0x180034d0e  jmp     short loc_180034C93
0x180034d10  test    edi, edi
0x180034d12  jnz     short loc_180034D24
0x180034d14  call    cs:__imp_GetLastError
0x180034d1b  nop     dword ptr [rax+rax+00h]
0x180034d20  mov     ebx, eax
0x180034d22  jmp     short loc_180034D92
0x180034d24  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180034d29  lea     r8, [rsp+28h+IsMember]; IsMember
0x180034d2e  lea     rdx, LocalSystem; SidToCheck
0x180034d35  call    cs:__imp_CheckTokenMembership
0x180034d3c  nop     dword ptr [rax+rax+00h]
0x180034d41  test    eax, eax
0x180034d43  jnz     short loc_180034D85
0x180034d45  call    cs:__imp_GetLastError
0x180034d4c  nop     dword ptr [rax+rax+00h]
0x180034d51  mov     ebx, eax
0x180034d53  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034d5a  cmp     rcx, rbp
0x180034d5d  jz      short loc_180034D99
0x180034d5f  test    byte ptr [rcx+1Ch], 1
0x180034d63  jz      short loc_180034D99
0x180034d65  cmp     byte ptr [rcx+19h], 1
0x180034d69  jb      short loc_180034D99
0x180034d6b  mov     rcx, [rcx+10h]
0x180034d6f  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180034d76  mov     edx, 0Ch
0x180034d7b  mov     r9d, eax
0x180034d7e  call    WPP_SF_d
0x180034d83  jmp     short loc_180034D92
0x180034d85  mov     eax, [rsp+28h+IsMember]
0x180034d89  dec     eax
0x180034d8b  neg     eax
0x180034d8d  sbb     ebx, ebx
0x180034d8f  and     ebx, 5
0x180034d92  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034d99  mov     rax, [rsp+28h+TokenHandle]
0x180034d9e  test    rax, rax
0x180034da1  jz      short loc_180034DB9
0x180034da3  mov     rcx, rax; hObject
0x180034da6  call    cs:__imp_CloseHandle
0x180034dad  nop     dword ptr [rax+rax+00h]
0x180034db2  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034db9  cmp     rcx, rbp
0x180034dbc  jz      short loc_180034DE2
0x180034dbe  test    byte ptr [rcx+1Ch], 1
0x180034dc2  jz      short loc_180034DE2
0x180034dc4  cmp     byte ptr [rcx+19h], 3
0x180034dc8  jb      short loc_180034DE2
0x180034dca  mov     rcx, [rcx+10h]
0x180034dce  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180034dd5  mov     edx, 0Dh
0x180034dda  mov     r9d, ebx
0x180034ddd  call    WPP_SF_d
0x180034de2  mov     rbp, [rsp+28h+arg_8]
0x180034de7  mov     eax, ebx
0x180034de9  mov     rbx, [rsp+28h+arg_0]
0x180034dee  add     rsp, 20h
0x180034df2  pop     rdi
0x180034df3  retn
```
