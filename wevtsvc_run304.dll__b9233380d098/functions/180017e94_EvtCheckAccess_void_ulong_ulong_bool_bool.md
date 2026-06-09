# EvtCheckAccess(void *,ulong,ulong &,bool,bool)

- ea: `0x180017e94`
- end: `0x180018275`
- name: `?EvtCheckAccess@@YA_NPEAXKAEAK_N2@Z`
- size: `993`
- prototype: `bool __usercall@<al>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, DWORD DesiredAccess@<edx>, LPDWORD GrantedAccess@<r8>, bool@<r9b>, bool)`
- caller_count: `10`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017c44`
- `0x18003db90`
- `0x18003f180`
- `0x1800414c0`
- `0x18005ffc0`
- `0x180062640`
- `0x18006a5e0`
- `0x18007a540`
- `0x1800b4e00`
- `0x1800b51a0`

## callees

- `0x180017e94`
- `0x18003420c`
- `0x180066510`
- `0x1800665b4`
- `0x180092008`
- `0x18009aee0`
- `0x1800bb9e4`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018000`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180017f6e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180017f6e`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x1800180c0`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x1800180c0`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180017fd0`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180017fd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017ee4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017f2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017ee4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017f2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017efb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017f45`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017efb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017f45`
- `RPCRT4!RpcImpersonateClient` at `0x180017f07`
- `RPCRT4!RpcImpersonateClient` at `0x18001807b`
- `RPCRT4!RpcImpersonateClient` at `0x180017f07`
- `RPCRT4!RpcImpersonateClient` at `0x18001807b`
- `RPCRT4!RpcRevertToSelf` at `0x180017f4d`
- `RPCRT4!RpcRevertToSelf` at `0x1800180c6`
- `RPCRT4!RpcRevertToSelf` at `0x180017f4d`
- `RPCRT4!RpcRevertToSelf` at `0x1800180c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall EvtCheckAccess(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        DWORD DesiredAccess,
        LPDWORD GrantedAccess,
        char a4,
        bool a5)
{
  HANDLE CurrentThread; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  void *v12; // rcx
  HANDLE v13; // rax
  BOOL v14; // ebx
  int v15; // edx
  WINBOOL v16; // edx
  char v17; // bl
  DWORD LastError; // ebx
  WINBOOL AccessStatus; // [rsp+60h] [rbp-61h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-59h] BYREF
  WINBOOL bSaclPresent; // [rsp+70h] [rbp-51h] BYREF
  __int128 pExceptionObject; // [rsp+78h] [rbp-49h] BYREF
  __int64 v24; // [rsp+88h] [rbp-39h]
  int v25; // [rsp+90h] [rbp-31h]
  int v26; // [rsp+94h] [rbp-2Dh]
  int v27; // [rsp+98h] [rbp-29h]
  WINBOOL bSaclDefaulted; // [rsp+A0h] [rbp-21h] BYREF
  WINBOOL pfGenerateOnClose; // [rsp+A4h] [rbp-1Dh] BYREF
  DWORD PrivilegeSetLength; // [rsp+A8h] [rbp-19h] BYREF
  PACL pSacl; // [rsp+B0h] [rbp-11h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+B8h] [rbp-9h] BYREF

  bSaclPresent = 0;
  bSaclDefaulted = 0;
  pSacl = 0;
  pfGenerateOnClose = 0;
  if ( !SecurityDescriptor )
    return 1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v10 = RpcImpersonateClient(0);
    v11 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2df56633cb49330cd5d73caae7a84fcf_Traceguids, v10);
      }
      pExceptionObject = 0;
      v24 = 0;
      v25 = v11;
      v26 = -1;
      v27 = 66;
      throw (EvtException *)&pExceptionObject;
    }
    v12 = TokenHandle;
    TokenHandle = 0;
    if ( (unsigned __int64)v12 + 1 > 1 )
      CloseHandle(v12);
    v13 = GetCurrentThread();
    v14 = OpenThreadToken(v13, 8u, 1, &TokenHandle);
    RpcRevertToSelf();
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_2df56633cb49330cd5d73caae7a84fcf_Traceguids, 1287);
      }
      pExceptionObject = 0;
      v24 = 0;
      v25 = 1287;
      v26 = -1;
      v27 = 78;
      throw (EvtException *)&pExceptionObject;
    }
  }
  AccessStatus = 0;
  if ( GetSecurityDescriptorSacl(SecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) && bSaclPresent )
  {
    AutoRevertPrivilege::AutoRevertPrivilege((AutoRevertPrivilege *)&pExceptionObject, v15);
    RpcImpersonateClient(0);
    AccessCheckAndAuditAlarmW(
      L"EventLog",
      TokenHandle,
      (LPWSTR)L"Channel",
      0,
      SecurityDescriptor,
      DesiredAccess,
      &GenericMapping,
      0,
      GrantedAccess,
      &AccessStatus,
      &pfGenerateOnClose);
    RpcRevertToSelf();
    if ( (_BYTE)v24 )
      AutoRevertPrivilege::EnableOrDisablePrivilege((AutoRevertPrivilege *)&pExceptionObject, 0);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&pExceptionObject);
  }
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  v16 = AccessStatus;
  if ( !AccessStatus )
  {
    if ( !AccessCheck(
            SecurityDescriptor,
            TokenHandle,
            DesiredAccess,
            &GenericMapping,
            &PrivilegeSet,
            &PrivilegeSetLength,
            GrantedAccess,
            &AccessStatus) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_2df56633cb49330cd5d73caae7a84fcf_Traceguids, LastError);
      }
      pExceptionObject = 0;
      v24 = 0;
      v25 = LastError;
      v26 = -1;
      v27 = 143;
      throw (EvtException *)&pExceptionObject;
    }
    v16 = AccessStatus;
  }
  if ( a4 && !v16 && (DesiredAccess == 1 || DesiredAccess - 4 <= 1) )
  {
    if ( (unsigned __int8)EvtPrivCheck(8, TokenHandle) )
    {
      v16 = 1;
      AccessStatus = 1;
    }
    else
    {
      v16 = AccessStatus;
    }
  }
  if ( a5 )
  {
    if ( v16 )
      goto LABEL_15;
    if ( (DesiredAccess & 1) == 0 )
    {
LABEL_25:
      v17 = 0;
      goto LABEL_16;
    }
    if ( (unsigned __int8)EvtPrivCheck(17, TokenHandle) )
    {
      v16 = 1;
      AccessStatus = 1;
    }
    else
    {
      v16 = AccessStatus;
    }
  }
  if ( !v16 )
    goto LABEL_25;
LABEL_15:
  v17 = 1;
LABEL_16:
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  return v17;
}

```

## disassembly

```asm
0x180017e94  push    rbp
0x180017e96  push    rbx
0x180017e97  push    rsi
0x180017e98  push    rdi
0x180017e99  push    r12
0x180017e9b  push    r14
0x180017e9d  push    r15
0x180017e9f  lea     rbp, [rsp-1Fh]
0x180017ea4  sub     rsp, 0E0h
0x180017eab  mov     rax, cs:__security_cookie
0x180017eb2  xor     rax, rsp
0x180017eb5  mov     [rbp+4Fh+var_40], rax
0x180017eb9  mov     r14b, r9b
0x180017ebc  mov     r15, r8
0x180017ebf  mov     edi, edx
0x180017ec1  mov     rsi, rcx
0x180017ec4  xor     r12d, r12d
0x180017ec7  mov     [rbp+4Fh+bSaclPresent], r12d
0x180017ecb  mov     [rbp+4Fh+bSaclDefaulted], r12d
0x180017ecf  mov     [rbp+4Fh+pSacl], r12
0x180017ed3  mov     [rbp+4Fh+var_6C], r12d
0x180017ed7  test    rcx, rcx
0x180017eda  jz      loc_180018066
0x180017ee0  mov     [rbp+4Fh+TokenHandle], r12
0x180017ee4  call    cs:__imp_GetCurrentThread
0x180017eea  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x180017eee  lea     edx, [r12+8]; DesiredAccess
0x180017ef3  lea     r8d, [r12+1]; OpenAsSelf
0x180017ef8  mov     rcx, rax; ThreadHandle
0x180017efb  call    cs:__imp_OpenThreadToken
0x180017f01  test    eax, eax
0x180017f03  jnz     short loc_180017F5B
0x180017f05  xor     ecx, ecx; BindingHandle
0x180017f07  call    cs:__imp_RpcImpersonateClient
0x180017f0d  mov     ebx, eax
0x180017f0f  test    eax, eax
0x180017f11  jnz     loc_1800180E4
0x180017f17  mov     rcx, [rbp+4Fh+TokenHandle]; hObject
0x180017f1b  mov     [rbp+4Fh+TokenHandle], r12
0x180017f1f  lea     rax, [rcx+1]
0x180017f23  cmp     rax, 1
0x180017f27  jbe     short loc_180017F2F
0x180017f29  call    cs:__imp_CloseHandle
0x180017f2f  call    cs:__imp_GetCurrentThread
0x180017f35  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x180017f39  mov     edx, 8; DesiredAccess
0x180017f3e  lea     r8d, [rdx-7]; OpenAsSelf
0x180017f42  mov     rcx, rax; ThreadHandle
0x180017f45  call    cs:__imp_OpenThreadToken
0x180017f4b  mov     ebx, eax
0x180017f4d  call    cs:__imp_RpcRevertToSelf
0x180017f53  test    ebx, ebx
0x180017f55  jz      loc_18001814E
0x180017f5b  mov     [rbp+4Fh+var_B0], r12d
0x180017f5f  lea     r9, [rbp+4Fh+bSaclDefaulted]; lpbSaclDefaulted
0x180017f63  lea     r8, [rbp+4Fh+pSacl]; pSacl
0x180017f67  lea     rdx, [rbp+4Fh+bSaclPresent]; lpbSaclPresent
0x180017f6b  mov     rcx, rsi; pSecurityDescriptor
0x180017f6e  call    cs:__imp_GetSecurityDescriptorSacl
0x180017f74  lea     rbx, GenericMapping
0x180017f7b  test    eax, eax
0x180017f7d  jz      short loc_180017F89
0x180017f7f  cmp     [rbp+4Fh+bSaclPresent], r12d
0x180017f83  jnz     loc_180018070
0x180017f89  xorps   xmm0, xmm0
0x180017f8c  xor     eax, eax
0x180017f8e  movups  xmmword ptr [rbp+4Fh+var_58.PrivilegeCount], xmm0
0x180017f92  mov     [rbp+4Fh+var_58.Privilege.Attributes], eax
0x180017f95  mov     [rbp+4Fh+var_68], 14h
0x180017f9c  mov     edx, [rbp+4Fh+var_B0]
0x180017f9f  test    edx, edx
0x180017fa1  jnz     short loc_180017FE1
0x180017fa3  lea     rax, [rbp+4Fh+var_B0]
0x180017fa7  mov     [rsp+110h+AccessStatus], rax; AccessStatus
0x180017fac  mov     [rsp+110h+GrantedAccess], r15; GrantedAccess
0x180017fb1  lea     rax, [rbp+4Fh+var_68]
0x180017fb5  mov     [rsp+110h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180017fba  lea     rax, [rbp+4Fh+var_58]
0x180017fbe  mov     [rsp+110h+PrivilegeSet], rax; PrivilegeSet
0x180017fc3  mov     r9, rbx; GenericMapping
0x180017fc6  mov     r8d, edi; DesiredAccess
0x180017fc9  mov     rdx, [rbp+4Fh+TokenHandle]; ClientToken
0x180017fcd  mov     rcx, rsi; pSecurityDescriptor
0x180017fd0  call    cs:__imp_AccessCheck
0x180017fd6  test    eax, eax
0x180017fd8  jz      loc_1800181CB
0x180017fde  mov     edx, [rbp+4Fh+var_B0]
0x180017fe1  test    r14b, r14b
0x180017fe4  jnz     short loc_180018026
0x180017fe6  cmp     [rbp+4Fh+arg_20], r12b
0x180017fea  jnz     short loc_18001806A
0x180017fec  test    edx, edx
0x180017fee  jz      short loc_180018061
0x180017ff0  mov     bl, 1
0x180017ff2  mov     rcx, [rbp+4Fh+TokenHandle]; hObject
0x180017ff6  lea     rdx, [rcx+1]
0x180017ffa  cmp     rdx, 1
0x180017ffe  jbe     short loc_180018006
0x180018000  call    cs:__imp_CloseHandle
0x180018006  mov     al, bl
0x180018008  mov     rcx, [rbp+4Fh+var_40]
0x18001800c  xor     rcx, rsp; StackCookie
0x18001800f  call    __security_check_cookie
0x180018014  add     rsp, 0E0h
0x18001801b  pop     r15
0x18001801d  pop     r14
0x18001801f  pop     r12
0x180018021  pop     rdi
0x180018022  pop     rsi
0x180018023  pop     rbx
0x180018024  pop     rbp
0x180018025  retn
0x180018026  test    edx, edx
0x180018028  jnz     short loc_180017FE6
0x18001802a  cmp     edi, 1
0x18001802d  jz      short loc_180018037
0x18001802f  lea     eax, [rdi-4]
0x180018032  cmp     eax, 1
0x180018035  ja      short loc_180017FE6
0x180018037  mov     rdx, [rbp+4Fh+TokenHandle]
0x18001803b  mov     ecx, 8
0x180018040  call    EvtPrivCheck
0x180018045  test    al, al
0x180018047  jz      loc_180018245
0x18001804d  mov     edx, 1
0x180018052  mov     [rbp+4Fh+var_B0], edx
0x180018055  jmp     short loc_180017FE6
0x180018057  test    dil, 1
0x18001805b  jnz     loc_18001824D
0x180018061  mov     bl, r12b
0x180018064  jmp     short loc_180017FF2
0x180018066  mov     al, 1
0x180018068  jmp     short loc_180018008
0x18001806a  test    edx, edx
0x18001806c  jnz     short loc_180017FF0
0x18001806e  jmp     short loc_180018057
0x180018070  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180018074  call    ??0AutoRevertPrivilege@@QEAA@J@Z; AutoRevertPrivilege::AutoRevertPrivilege(long)
0x180018079  xor     ecx, ecx; BindingHandle
0x18001807b  call    cs:__imp_RpcImpersonateClient
0x180018081  lea     rax, [rbp+4Fh+var_6C]
0x180018085  mov     [rsp+110h+pfGenerateOnClose], rax; pfGenerateOnClose
0x18001808a  lea     rax, [rbp+4Fh+var_B0]
0x18001808e  mov     [rsp+110h+var_C8], rax; AccessStatus
0x180018093  mov     [rsp+110h+var_D0], r15; GrantedAccess
0x180018098  mov     dword ptr [rsp+110h+AccessStatus], r12d; ObjectCreation
0x18001809d  mov     [rsp+110h+GrantedAccess], rbx; GenericMapping
0x1800180a2  mov     dword ptr [rsp+110h+PrivilegeSetLength], edi; DesiredAccess
0x1800180a6  mov     [rsp+110h+PrivilegeSet], rsi; SecurityDescriptor
0x1800180ab  xor     r9d, r9d; ObjectName
0x1800180ae  lea     r8, ObjectTypeName; "Channel"
0x1800180b5  mov     rdx, [rbp+4Fh+TokenHandle]; HandleId
0x1800180b9  lea     rcx, SubsystemName; "EventLog"
0x1800180c0  call    cs:__imp_AccessCheckAndAuditAlarmW
0x1800180c6  call    cs:__imp_RpcRevertToSelf
0x1800180cc  cmp     byte ptr [rbp+4Fh+var_88], r12b
0x1800180d0  jnz     loc_1800181BB
0x1800180d6  lea     rcx, [rbp+4Fh+pExceptionObject]
0x1800180da  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800180df  jmp     loc_180017F89
0x1800180e4  lea     rcx, WPP_GLOBAL_Control
0x1800180eb  mov     r10, cs:WPP_GLOBAL_Control
0x1800180f2  cmp     r10, rcx
0x1800180f5  jz      short loc_180018120
0x1800180f7  test    dword ptr [r10+1Ch], 8000000h
0x1800180ff  jz      short loc_180018120
0x180018101  cmp     byte ptr [r10+19h], 2
0x180018106  jb      short loc_180018120
0x180018108  mov     edx, 0Ah
0x18001810d  mov     r9d, ebx
0x180018110  lea     r8, WPP_2df56633cb49330cd5d73caae7a84fcf_Traceguids
0x180018117  mov     rcx, [r10+10h]
0x18001811b  call    WPP_SF_d
0x180018120  xorps   xmm0, xmm0
0x180018123  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x180018128  mov     [rbp+4Fh+var_88], r12
0x18001812c  mov     [rbp+4Fh+var_80], ebx
0x18001812f  mov     [rbp+4Fh+var_7C], 0FFFFFFFFh
0x180018136  mov     [rbp+4Fh+var_78], 42h ; 'B'
0x18001813d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180018144  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180018148  call    _CxxThrowException_0
0x18001814e  lea     rcx, WPP_GLOBAL_Control
0x180018155  mov     edi, 507h
0x18001815a  mov     rax, cs:WPP_GLOBAL_Control
0x180018161  cmp     rax, rcx
0x180018164  jz      short loc_18001818D
0x180018166  test    dword ptr [rax+1Ch], 8000000h
0x18001816d  jz      short loc_18001818D
0x18001816f  cmp     byte ptr [rax+19h], 2
0x180018173  jb      short loc_18001818D
0x180018175  mov     edx, 0Bh
0x18001817a  mov     r9d, edi
0x18001817d  lea     r8, WPP_2df56633cb49330cd5d73caae7a84fcf_Traceguids
0x180018184  mov     rcx, [rax+10h]
0x180018188  call    WPP_SF_d
0x18001818d  xorps   xmm0, xmm0
0x180018190  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x180018195  mov     [rbp+4Fh+var_88], r12
0x180018199  mov     [rbp+4Fh+var_80], edi
0x18001819c  mov     [rbp+4Fh+var_7C], 0FFFFFFFFh
0x1800181a3  mov     [rbp+4Fh+var_78], 4Eh ; 'N'
0x1800181aa  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800181b1  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800181b5  call    _CxxThrowException_0
0x1800181bb  xor     edx, edx; bool
0x1800181bd  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x1800181c1  call    ?EnableOrDisablePrivilege@AutoRevertPrivilege@@AEAA_N_N@Z; AutoRevertPrivilege::EnableOrDisablePrivilege(bool)
0x1800181c6  jmp     loc_1800180D6
0x1800181cb  call    cs:__imp_GetLastError
0x1800181d1  mov     ebx, eax
0x1800181d3  mov     edi, 507h
0x1800181d8  test    eax, eax
0x1800181da  cmovz   ebx, edi
0x1800181dd  lea     rcx, WPP_GLOBAL_Control
0x1800181e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800181eb  cmp     rax, rcx
0x1800181ee  jz      short loc_180018217
0x1800181f0  test    dword ptr [rax+1Ch], 8000000h
0x1800181f7  jz      short loc_180018217
0x1800181f9  cmp     byte ptr [rax+19h], 2
0x1800181fd  jb      short loc_180018217
0x1800181ff  mov     edx, 0Ch
0x180018204  mov     r9d, ebx
0x180018207  lea     r8, WPP_2df56633cb49330cd5d73caae7a84fcf_Traceguids
0x18001820e  mov     rcx, [rax+10h]
0x180018212  call    WPP_SF_d
0x180018217  xorps   xmm0, xmm0
0x18001821a  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x18001821f  mov     [rbp+4Fh+var_88], r12
0x180018223  mov     [rbp+4Fh+var_80], ebx
0x180018226  mov     [rbp+4Fh+var_7C], 0FFFFFFFFh
0x18001822d  mov     [rbp+4Fh+var_78], 8Fh
0x180018234  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001823b  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18001823f  call    _CxxThrowException_0
0x180018245  mov     edx, [rbp+4Fh+var_B0]
0x180018248  jmp     loc_180017FE6
0x18001824d  mov     rdx, [rbp+4Fh+TokenHandle]
0x180018251  mov     ecx, 11h
0x180018256  call    EvtPrivCheck
0x18001825b  test    al, al
0x18001825d  jz      short loc_18001826C
0x18001825f  mov     edx, 1
0x180018264  mov     [rbp+4Fh+var_B0], edx
0x180018267  jmp     loc_180017FEC
0x18001826c  mov     edx, [rbp+4Fh+var_B0]
0x18001826f  jmp     loc_180017FEC
```
