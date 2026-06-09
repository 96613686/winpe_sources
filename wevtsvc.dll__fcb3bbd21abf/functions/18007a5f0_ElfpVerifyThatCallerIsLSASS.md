# ElfpVerifyThatCallerIsLSASS

- ea: `0x18007a5f0`
- end: `0x18007a928`
- name: `ElfpVerifyThatCallerIsLSASS`
- size: `824`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180017c44`

## callees

- `0x18003420c`
- `0x180066580`
- `0x18007a5f0`
- `0x180092008`
- `0x180092ee4`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800a7b60`
- `0x1800c5698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a7d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a7d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a83a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007a86a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007a86a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a80e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a80e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a77d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a77d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a792`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a792`
- `RPCRT4!RpcImpersonateClient` at `0x18007a75b`
- `RPCRT4!RpcImpersonateClient` at `0x18007a75b`
- `RPCRT4!RpcRevertToSelf` at `0x18007a79a`
- `RPCRT4!RpcRevertToSelf` at `0x18007a79a`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18007a625`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18007a625`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18007a6bf`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18007a6bf`

## pseudocode

```c
__int64 __fastcall ElfpVerifyThatCallerIsLSASS(signed __int64 a1)
{
  unsigned int IsClientLocal; // ebx
  _QWORD *v3; // r10
  __int64 v4; // rdx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  int LsassPid; // eax
  void **v9; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v12; // rdx
  unsigned int ClientLocalFlag; // [rsp+30h] [rbp-29h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-19h] BYREF

  ClientLocalFlag = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( IsClientLocal )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return IsClientLocal;
    }
    v4 = 15;
LABEL_6:
    WPP_SF_d(v3[2], v4, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids, IsClientLocal);
    return IsClientLocal;
  }
  if ( !ClientLocalFlag )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 5;
    }
    v7 = 16;
    goto LABEL_47;
  }
  ClientLocalFlag = 0;
  IsClientLocal = I_RpcBindingInqLocalClientPID(0, &ClientLocalFlag);
  if ( IsClientLocal )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return IsClientLocal;
    }
    v4 = 17;
    goto LABEL_6;
  }
  LsassPid = GetLsassPid();
  if ( ClientLocalFlag != LsassPid )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids,
        ClientLocalFlag,
        LsassPid);
    }
    return 5;
  }
  if ( !RpcImpersonateClient(0) )
  {
    TokenHandle = 0;
    v9 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    CurrentThread = GetCurrentThread();
    LODWORD(v9) = OpenThreadToken(CurrentThread, 8u, 1, v9);
    RpcRevertToSelf();
    if ( !(_DWORD)v9 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      LastError = GetLastError();
      v12 = 19;
LABEL_34:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids, LastError);
LABEL_40:
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
      return 5;
    }
    ClientLocalFlag = 0;
    memset_0(TokenInformation, 0, 0x54u);
    if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x54u, &ClientLocalFlag) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      LastError = GetLastError();
      v12 = 20;
      goto LABEL_34;
    }
    if ( !IsWellKnownSid(TokenInformation[0], WinLocalSystemSid) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids);
      }
      goto LABEL_40;
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
    if ( !_InterlockedCompareExchange64(&qword_180111970, a1, 0) )
      return 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 22;
LABEL_47:
      WPP_SF_(v6[2], v7, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids);
    }
  }
  return 5;
}

```

## disassembly

```asm
0x18007a5f0  mov     [rsp-8+arg_8], rbx
0x18007a5f5  mov     [rsp-8+arg_10], rdi
0x18007a5fa  push    rbp
0x18007a5fb  lea     rbp, [rsp-57h]
0x18007a600  sub     rsp, 0B0h
0x18007a607  mov     rax, cs:__security_cookie
0x18007a60e  xor     rax, rsp
0x18007a611  mov     [rbp+57h+var_10], rax
0x18007a615  mov     rdi, rcx
0x18007a618  mov     [rbp+57h+ClientLocalFlag], 0
0x18007a61f  xor     ecx, ecx; BindingHandle
0x18007a621  lea     rdx, [rbp+57h+ClientLocalFlag]; ClientLocalFlag
0x18007a625  call    cs:__imp_I_RpcBindingIsClientLocal
0x18007a62b  mov     ebx, eax
0x18007a62d  test    eax, eax
0x18007a62f  jz      short loc_18007A674
0x18007a631  mov     r10, cs:WPP_GLOBAL_Control
0x18007a638  lea     rcx, WPP_GLOBAL_Control
0x18007a63f  cmp     r10, rcx
0x18007a642  jz      short loc_18007A66D
0x18007a644  test    dword ptr [r10+1Ch], 1000h
0x18007a64c  jz      short loc_18007A66D
0x18007a64e  cmp     byte ptr [r10+19h], 2
0x18007a653  jb      short loc_18007A66D
0x18007a655  mov     edx, 0Fh
0x18007a65a  mov     rcx, [r10+10h]
0x18007a65e  lea     r8, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids
0x18007a665  mov     r9d, ebx
0x18007a668  call    WPP_SF_d
0x18007a66d  mov     eax, ebx
0x18007a66f  jmp     loc_18007A907
0x18007a674  cmp     [rbp+57h+ClientLocalFlag], 0
0x18007a678  jnz     short loc_18007A6B2
0x18007a67a  mov     rax, cs:WPP_GLOBAL_Control
0x18007a681  lea     rcx, WPP_GLOBAL_Control
0x18007a688  cmp     rax, rcx
0x18007a68b  jz      loc_18007A902
0x18007a691  test    dword ptr [rax+1Ch], 1000h
0x18007a698  jz      loc_18007A902
0x18007a69e  cmp     byte ptr [rax+19h], 2
0x18007a6a2  jb      loc_18007A902
0x18007a6a8  mov     edx, 10h
0x18007a6ad  jmp     loc_18007A8F2
0x18007a6b2  lea     rdx, [rbp+57h+ClientLocalFlag]; Pid
0x18007a6b6  mov     [rbp+57h+ClientLocalFlag], 0
0x18007a6bd  xor     ecx, ecx; Binding
0x18007a6bf  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18007a6c5  mov     ebx, eax
0x18007a6c7  test    eax, eax
0x18007a6c9  jz      short loc_18007A6FD
0x18007a6cb  mov     r10, cs:WPP_GLOBAL_Control
0x18007a6d2  lea     rcx, WPP_GLOBAL_Control
0x18007a6d9  cmp     r10, rcx
0x18007a6dc  jz      short loc_18007A66D
0x18007a6de  test    dword ptr [r10+1Ch], 1000h
0x18007a6e6  jz      short loc_18007A66D
0x18007a6e8  cmp     byte ptr [r10+19h], 2
0x18007a6ed  jb      loc_18007A66D
0x18007a6f3  mov     edx, 11h
0x18007a6f8  jmp     loc_18007A65A
0x18007a6fd  call    GetLsassPid
0x18007a702  mov     r9d, [rbp+57h+ClientLocalFlag]
0x18007a706  cmp     r9d, eax
0x18007a709  jz      short loc_18007A759
0x18007a70b  mov     r10, cs:WPP_GLOBAL_Control
0x18007a712  lea     rcx, WPP_GLOBAL_Control
0x18007a719  cmp     r10, rcx
0x18007a71c  jz      loc_18007A902
0x18007a722  test    dword ptr [r10+1Ch], 1000h
0x18007a72a  jz      loc_18007A902
0x18007a730  cmp     byte ptr [r10+19h], 2
0x18007a735  jb      loc_18007A902
0x18007a73b  mov     rcx, [r10+10h]
0x18007a73f  lea     r8, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids
0x18007a746  mov     edx, 12h
0x18007a74b  mov     dword ptr [rsp+0B0h+ReturnLength], eax
0x18007a74f  call    WPP_SF_DD
0x18007a754  jmp     loc_18007A902
0x18007a759  xor     ecx, ecx; BindingHandle
0x18007a75b  call    cs:__imp_RpcImpersonateClient
0x18007a761  test    eax, eax
0x18007a763  jnz     loc_18007A902
0x18007a769  lea     rcx, [rbp+57h+TokenHandle]
0x18007a76d  mov     [rbp+57h+TokenHandle], 0
0x18007a775  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18007a77a  mov     rbx, rax
0x18007a77d  call    cs:__imp_GetCurrentThread
0x18007a783  mov     edx, 8; DesiredAccess
0x18007a788  mov     r9, rbx; TokenHandle
0x18007a78b  mov     rcx, rax; ThreadHandle
0x18007a78e  lea     r8d, [rdx-7]; OpenAsSelf
0x18007a792  call    cs:__imp_OpenThreadToken
0x18007a798  mov     ebx, eax
0x18007a79a  call    cs:__imp_RpcRevertToSelf
0x18007a7a0  test    ebx, ebx
0x18007a7a2  jnz     short loc_18007A7DD
0x18007a7a4  mov     rax, cs:WPP_GLOBAL_Control
0x18007a7ab  lea     rcx, WPP_GLOBAL_Control
0x18007a7b2  cmp     rax, rcx
0x18007a7b5  jz      loc_18007A8A9
0x18007a7bb  test    dword ptr [rax+1Ch], 1000h
0x18007a7c2  jz      loc_18007A8A9
0x18007a7c8  cmp     byte ptr [rax+19h], 2
0x18007a7cc  jb      loc_18007A8A9
0x18007a7d2  call    cs:__imp_GetLastError
0x18007a7d8  lea     edx, [rbx+13h]
0x18007a7db  jmp     short loc_18007A843
0x18007a7dd  mov     ebx, 54h ; 'T'
0x18007a7e2  mov     [rbp+57h+ClientLocalFlag], 0
0x18007a7e9  mov     r8d, ebx; Size
0x18007a7ec  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18007a7f0  xor     edx, edx; Val
0x18007a7f2  call    memset_0
0x18007a7f7  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18007a7fb  lea     rax, [rbp+57h+ClientLocalFlag]
0x18007a7ff  mov     r9d, ebx; TokenInformationLength
0x18007a802  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18007a807  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18007a80b  lea     edx, [rbx-53h]; TokenInformationClass
0x18007a80e  call    cs:__imp_GetTokenInformation
0x18007a814  test    eax, eax
0x18007a816  jnz     short loc_18007A85F
0x18007a818  mov     rax, cs:WPP_GLOBAL_Control
0x18007a81f  lea     rcx, WPP_GLOBAL_Control
0x18007a826  cmp     rax, rcx
0x18007a829  jz      short loc_18007A8A9
0x18007a82b  test    dword ptr [rax+1Ch], 1000h
0x18007a832  jz      short loc_18007A8A9
0x18007a834  cmp     byte ptr [rax+19h], 2
0x18007a838  jb      short loc_18007A8A9
0x18007a83a  call    cs:__imp_GetLastError
0x18007a840  lea     edx, [rbx-40h]
0x18007a843  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a84a  lea     r8, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids
0x18007a851  mov     r9d, eax
0x18007a854  mov     rcx, [rcx+10h]
0x18007a858  call    WPP_SF_d
0x18007a85d  jmp     short loc_18007A8A9
0x18007a85f  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18007a863  mov     ebx, 16h
0x18007a868  mov     edx, ebx; WellKnownSidType
0x18007a86a  call    cs:__imp_IsWellKnownSid
0x18007a870  test    eax, eax
0x18007a872  jnz     short loc_18007A8B4
0x18007a874  mov     rax, cs:WPP_GLOBAL_Control
0x18007a87b  lea     rcx, WPP_GLOBAL_Control
0x18007a882  cmp     rax, rcx
0x18007a885  jz      short loc_18007A8A9
0x18007a887  test    dword ptr [rax+1Ch], 1000h
0x18007a88e  jz      short loc_18007A8A9
0x18007a890  cmp     byte ptr [rax+19h], 2
0x18007a894  jb      short loc_18007A8A9
0x18007a896  mov     rcx, [rax+10h]
0x18007a89a  lea     edx, [rbx-1]
0x18007a89d  lea     r8, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids
0x18007a8a4  call    WPP_SF_
0x18007a8a9  lea     rcx, [rbp+57h+TokenHandle]
0x18007a8ad  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007a8b2  jmp     short loc_18007A902
0x18007a8b4  lea     rcx, [rbp+57h+TokenHandle]
0x18007a8b8  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007a8bd  xor     eax, eax
0x18007a8bf  lock cmpxchg cs:qword_180111970, rdi
0x18007a8c8  jnz     short loc_18007A8CE
0x18007a8ca  xor     eax, eax
0x18007a8cc  jmp     short loc_18007A907
0x18007a8ce  mov     rax, cs:WPP_GLOBAL_Control
0x18007a8d5  lea     rcx, WPP_GLOBAL_Control
0x18007a8dc  cmp     rax, rcx
0x18007a8df  jz      short loc_18007A902
0x18007a8e1  test    dword ptr [rax+1Ch], 1000h
0x18007a8e8  jz      short loc_18007A902
0x18007a8ea  cmp     byte ptr [rax+19h], 2
0x18007a8ee  jb      short loc_18007A902
0x18007a8f0  mov     edx, ebx
0x18007a8f2  mov     rcx, [rax+10h]
0x18007a8f6  lea     r8, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids
0x18007a8fd  call    WPP_SF_
0x18007a902  mov     eax, 5
0x18007a907  mov     rcx, [rbp+57h+var_10]
0x18007a90b  xor     rcx, rsp; StackCookie
0x18007a90e  call    __security_check_cookie
0x18007a913  lea     r11, [rsp+0B0h+var_s0]
0x18007a91b  mov     rbx, [r11+18h]
0x18007a91f  mov     rdi, [r11+20h]
0x18007a923  mov     rsp, r11
0x18007a926  pop     rbp
0x18007a927  retn
```
