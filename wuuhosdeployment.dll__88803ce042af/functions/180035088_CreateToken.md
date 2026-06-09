# CreateToken

- ea: `0x180035088`
- end: `0x180035435`
- name: `CreateToken`
- size: `941`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003543c`

## callees

- `0x180003950`
- `0x180003974`
- `0x18000e4d4`
- `0x180035088`
- `0x180036960`
- `0x180042630`
- `0x180043160`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035376`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035363`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800350d3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800350d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800350c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800350c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003536e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003538f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003536e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003538f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035406`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800351ce`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800351ce`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180035174`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800352b7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180035174`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800352b7`

## string_xrefs

- `0x180035282`: `SeSecurityPrivilege`
- `0x180035250`: `User token must have at least one privilege`
- `0x18003529c`: `SeRestorePrivilege`
- `0x180035290`: `SeBackupPrivilege`
- `0x1800350f8`: `SeIncreaseWorkingSetPrivilege`
- `0x1800350e7`: `SeShutdownPrivilege`
- `0x180035112`: `SeTakeOwnershipPrivilege`
- `0x180035103`: `SeIncreaseQuotaPrivilege`
- `0x180035128`: `SeDebugPrivilege`
- `0x18003511d`: `SeIncreaseBasePriorityPrivilege`
- `0x18003513e`: `SeImpersonatePrivilege`
- `0x180035133`: `SeRemoteShutdownPrivilege`
- `0x180035154`: `SeCreateGlobalPrivilege`
- `0x180035149`: `SeDelegateSessionUserImpersonatePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CreateToken(void **a1)
{
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  struct _LUID_AND_ATTRIBUTES *v6; // rdi
  const char *v7; // r9
  int LastError; // edi
  int token_information; // eax
  void *v10; // rcx
  _DWORD *v11; // rbx
  unsigned __int64 v12; // rdi
  const char *v13; // r9
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  void *v17; // rdi
  char *v18; // rcx
  HANDLE v19; // rsi
  DWORD v20; // ebx
  int DeletePrivilegeCount; // [rsp+20h] [rbp-E0h]
  const char *PrivilegesToDelete; // [rsp+28h] [rbp-D8h]
  _BYTE v24[8]; // [rsp+50h] [rbp-B0h]
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR v26[4]; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpName[10]; // [rsp+80h] [rbp-80h]
  HANDLE hObject; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE TokenHandle[5]; // [rsp+D8h] [rbp-28h] BYREF
  struct _LUID_AND_ATTRIBUTES Luid[10]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  TokenHandle[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xBu, TokenHandle) )
  {
    lpName[0] = L"SeShutdownPrivilege";
    lpName[1] = L"SeIncreaseWorkingSetPrivilege";
    lpName[2] = L"SeIncreaseQuotaPrivilege";
    lpName[3] = L"SeTakeOwnershipPrivilege";
    lpName[4] = L"SeIncreaseBasePriorityPrivilege";
    lpName[5] = L"SeDebugPrivilege";
    lpName[6] = L"SeRemoteShutdownPrivilege";
    lpName[7] = L"SeImpersonatePrivilege";
    lpName[8] = L"SeDelegateSessionUserImpersonatePrivilege";
    lpName[9] = L"SeCreateGlobalPrivilege";
    memset(Luid, 0, sizeof(Luid));
    v5 = 0;
    v6 = Luid;
    do
    {
      if ( !LookupPrivilegeValueW(0, lpName[v5], &v6->Luid) )
      {
        v4 = 170;
        goto LABEL_39;
      }
      ++v5;
      ++v6;
    }
    while ( v5 < 0xA );
    hObject = 0;
    if ( !CreateRestrictedToken(TokenHandle[0], 0, 0, 0, 0xAu, Luid, 0, 0, &hObject) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xB6,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
                    v7);
LABEL_37:
      v18 = (char *)hObject;
LABEL_33:
      if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v18);
      goto LABEL_40;
    }
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_PRIVILEGES,0>(&Block, hObject);
    LastError = token_information;
    if ( token_information >= 0 )
    {
      v11 = Block;
      if ( *(_DWORD *)Block )
      {
        v12 = 0;
        v26[0] = L"SeSecurityPrivilege";
        v26[1] = L"SeBackupPrivilege";
        v26[2] = L"SeRestorePrivilege";
        while ( LookupPrivilegeValueW(0, v26[v12], (PLUID)&TokenHandle[v12 + 1]) )
        {
          v24[v12++] = 0;
          if ( v12 >= 3 )
          {
            v14 = 0;
            v15 = 0;
            if ( *v11 )
            {
              while ( 2 )
              {
                v16 = 0;
                while ( v24[v16]
                     || v11[3 * v15 + 1] != LODWORD(TokenHandle[v16 + 1])
                     || v11[3 * v15 + 2] != HIDWORD(TokenHandle[v16 + 1]) )
                {
                  if ( (unsigned __int64)++v16 >= 3 )
                    goto LABEL_26;
                }
                ++v14;
                v24[v16] = 1;
                if ( v14 == 2 )
                {
                  operator delete(v11);
                  goto LABEL_29;
                }
LABEL_26:
                v15 = (unsigned int)(v15 + 1);
                if ( (unsigned int)v15 < *v11 )
                  continue;
                break;
              }
            }
            LastError = -2145112065;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x85,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
              (const char *)0x80242FFFLL,
              DeletePrivilegeCount);
            goto LABEL_13;
          }
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x6A,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
                      v13);
        operator delete(v11);
        if ( LastError < 0 )
          goto LABEL_36;
LABEL_29:
        v17 = *a1;
        v18 = 0;
        v19 = hObject;
        hObject = 0;
        if ( v17 && v17 != (void *)-1LL )
        {
          v20 = GetLastError();
          CloseHandle(v17);
          SetLastError(v20);
          v18 = (char *)hObject;
        }
        *a1 = v19;
        LastError = 0;
        goto LABEL_33;
      }
      LastError = -2145112065;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x58,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
        (const char *)0x80242FFFLL,
        (int)"User token must have at least one privilege",
        PrivilegesToDelete);
LABEL_13:
      v10 = v11;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
        (const char *)(unsigned int)token_information,
        DeletePrivilegeCount);
      v10 = Block;
      if ( !Block )
      {
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
          (const char *)(unsigned int)LastError,
          DeletePrivilegeCount);
        goto LABEL_37;
      }
    }
    operator delete(v10);
    goto LABEL_36;
  }
  v4 = 140;
LABEL_39:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v4,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
                v3);
LABEL_40:
  if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(TokenHandle[0]);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180035088  mov     [rsp-8+arg_8], rbx
0x18003508d  mov     [rsp-8+arg_10], rsi
0x180035092  push    rbp
0x180035093  push    rdi
0x180035094  push    r14
0x180035096  lea     rbp, [rsp-90h]
0x18003509e  sub     rsp, 190h
0x1800350a5  mov     rax, cs:__security_cookie
0x1800350ac  xor     rax, rsp
0x1800350af  mov     [rbp+0A0h+var_20], rax
0x1800350b6  mov     r14, rcx
0x1800350b9  mov     [rbp+0A0h+TokenHandle], 0
0x1800350c1  call    cs:__imp_GetCurrentProcess
0x1800350c7  lea     r8, [rbp+0A0h+TokenHandle]; TokenHandle
0x1800350cb  mov     edx, 0Bh; DesiredAccess
0x1800350d0  mov     rcx, rax; ProcessHandle
0x1800350d3  call    cs:__imp_OpenProcessToken
0x1800350d9  test    eax, eax
0x1800350db  jnz     short loc_1800350E7
0x1800350dd  mov     edx, 8Ch
0x1800350e2  jmp     loc_1800353E3
0x1800350e7  lea     rax, aSeshutdownpriv; "SeShutdownPrivilege"
0x1800350ee  xor     edx, edx; Val
0x1800350f0  mov     [rbp+0A0h+lpName], rax
0x1800350f4  lea     rcx, [rbp+0A0h+Luid]; void *
0x1800350f8  lea     rax, aSeincreasework; "SeIncreaseWorkingSetPrivilege"
0x1800350ff  mov     [rbp+0A0h+var_118], rax
0x180035103  lea     rax, aSeincreasequot; "SeIncreaseQuotaPrivilege"
0x18003510a  mov     [rbp+0A0h+var_110], rax
0x18003510e  lea     r8d, [rdx+78h]; Size
0x180035112  lea     rax, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x180035119  mov     [rbp+0A0h+var_108], rax
0x18003511d  lea     rax, aSeincreasebase; "SeIncreaseBasePriorityPrivilege"
0x180035124  mov     [rbp+0A0h+var_100], rax
0x180035128  lea     rax, aSedebugprivile; "SeDebugPrivilege"
0x18003512f  mov     [rbp+0A0h+var_F8], rax
0x180035133  lea     rax, aSeremoteshutdo; "SeRemoteShutdownPrivilege"
0x18003513a  mov     [rbp+0A0h+var_F0], rax
0x18003513e  lea     rax, aSeimpersonatep; "SeImpersonatePrivilege"
0x180035145  mov     [rbp+0A0h+var_E8], rax
0x180035149  lea     rax, aSedelegatesess; "SeDelegateSessionUserImpersonatePrivile"...
0x180035150  mov     [rbp+0A0h+var_E0], rax
0x180035154  lea     rax, aSecreateglobal; "SeCreateGlobalPrivilege"
0x18003515b  mov     [rbp+0A0h+var_D8], rax
0x18003515f  call    memset
0x180035164  xor     ebx, ebx
0x180035166  lea     rdi, [rbp+0A0h+Luid]
0x18003516a  mov     rdx, [rbp+rbx*8+0A0h+lpName]; lpName
0x18003516f  mov     r8, rdi; lpLuid
0x180035172  xor     ecx, ecx; lpSystemName
0x180035174  call    cs:__imp_LookupPrivilegeValueW
0x18003517a  test    eax, eax
0x18003517c  jz      loc_1800353DE
0x180035182  inc     rbx
0x180035185  add     rdi, 0Ch
0x180035189  cmp     rbx, 0Ah
0x18003518d  jb      short loc_18003516A
0x18003518f  mov     rcx, [rbp+0A0h+TokenHandle]; ExistingTokenHandle
0x180035193  lea     rax, [rbp+0A0h+hObject]
0x180035197  mov     [rsp+1A0h+NewTokenHandle], rax; NewTokenHandle
0x18003519c  xor     r9d, r9d; SidsToDisable
0x18003519f  mov     [rsp+1A0h+SidsToRestrict], 0; SidsToRestrict
0x1800351a8  lea     rax, [rbp+0A0h+Luid]
0x1800351ac  mov     [rsp+1A0h+RestrictedSidCount], 0; RestrictedSidCount
0x1800351b4  xor     r8d, r8d; DisableSidCount
0x1800351b7  mov     [rsp+1A0h+PrivilegesToDelete], rax; char *
0x1800351bc  xor     edx, edx; Flags
0x1800351be  mov     [rsp+1A0h+DeletePrivilegeCount], 0Ah; int
0x1800351c6  mov     [rbp+0A0h+hObject], 0
0x1800351ce  call    cs:__imp_CreateRestrictedToken
0x1800351d4  test    eax, eax
0x1800351d6  jnz     short loc_1800351F7
0x1800351d8  mov     rcx, [rbp+0A8h]; this
0x1800351df  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800351e6  mov     edx, 0B6h; void *
0x1800351eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800351f0  mov     edi, eax
0x1800351f2  jmp     loc_1800353D8
0x1800351f7  mov     rdx, [rbp+0A0h+hObject]
0x1800351fb  lea     rcx, [rsp+1A0h+Block]
0x180035200  mov     [rsp+1A0h+Block], 0
0x180035209  call    ??$get_token_information_nothrow@U_TOKEN_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_PRIVILEGES,wil::details::token_info_deleter> &,void *)
0x18003520e  mov     edi, eax
0x180035210  test    eax, eax
0x180035212  jns     short loc_18003523F
0x180035214  mov     rcx, [rbp+0A8h]; this
0x18003521b  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035222  mov     r9d, eax; char *
0x180035225  mov     edx, 55h ; 'U'; void *
0x18003522a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003522f  mov     rcx, [rsp+1A0h+Block]
0x180035234  test    rcx, rcx
0x180035237  jz      loc_1800353BD
0x18003523d  jmp     short loc_180035278
0x18003523f  mov     rbx, [rsp+1A0h+Block]
0x180035244  cmp     dword ptr [rbx], 0
0x180035247  jnz     short loc_180035282
0x180035249  mov     rcx, [rbp+0A8h]; this
0x180035250  lea     rax, aUserTokenMustH; "User token must have at least one privi"...
0x180035257  mov     edi, 80242FFFh
0x18003525c  mov     qword ptr [rsp+1A0h+DeletePrivilegeCount], rax; int
0x180035261  mov     r9d, edi; char *
0x180035264  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003526b  mov     edx, 58h ; 'X'; void *
0x180035270  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035275  mov     rcx, rbx; Block
0x180035278  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003527d  jmp     loc_1800353BD
0x180035282  lea     rax, aSesecuritypriv; "SeSecurityPrivilege"
0x180035289  xor     edi, edi
0x18003528b  mov     [rsp+1A0h+var_140], rax
0x180035290  lea     rax, aSebackupprivil; "SeBackupPrivilege"
0x180035297  mov     [rsp+1A0h+var_138], rax
0x18003529c  lea     rax, aSerestoreprivi; "SeRestorePrivilege"
0x1800352a3  mov     [rsp+1A0h+var_130], rax
0x1800352a8  mov     rdx, [rsp+rdi*8+1A0h+var_140]; lpName
0x1800352ad  lea     r8, [rbp+0A0h+var_C0]
0x1800352b1  lea     r8, [r8+rdi*8]; lpLuid
0x1800352b5  xor     ecx, ecx; lpSystemName
0x1800352b7  call    cs:__imp_LookupPrivilegeValueW
0x1800352bd  test    eax, eax
0x1800352bf  jz      loc_180035397
0x1800352c5  mov     [rsp+rdi+1A0h+var_150], 0
0x1800352ca  inc     rdi
0x1800352cd  cmp     rdi, 3
0x1800352d1  jb      short loc_1800352A8
0x1800352d3  xor     r8d, r8d
0x1800352d6  xor     edx, edx
0x1800352d8  cmp     [rbx], edx
0x1800352da  jbe     short loc_18003531E
0x1800352dc  xor     ecx, ecx
0x1800352de  cmp     [rsp+rcx+1A0h+var_150], 0
0x1800352e3  jnz     short loc_1800352FF
0x1800352e5  mov     eax, [rbp+rcx*8+0A0h+var_C0]
0x1800352e9  lea     r9, [rdx+rdx*2]
0x1800352ed  cmp     [rbx+r9*4+4], eax
0x1800352f2  jnz     short loc_1800352FF
0x1800352f4  mov     eax, [rbp+rcx*8+0A0h+var_BC]
0x1800352f8  cmp     [rbx+r9*4+8], eax
0x1800352fd  jz      short loc_18003530A
0x1800352ff  inc     rcx
0x180035302  cmp     rcx, 3
0x180035306  jb      short loc_1800352DE
0x180035308  jmp     short loc_180035318
0x18003530a  inc     r8
0x18003530d  mov     [rsp+rcx+1A0h+var_150], 1
0x180035312  cmp     r8, 2
0x180035316  jz      short loc_180035343
0x180035318  inc     edx
0x18003531a  cmp     edx, [rbx]
0x18003531c  jb      short loc_1800352DC
0x18003531e  mov     rcx, [rbp+0A8h]; this
0x180035325  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003532c  mov     edi, 80242FFFh
0x180035331  mov     edx, 85h; void *
0x180035336  mov     r9d, edi; char *
0x180035339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003533e  jmp     loc_180035275
0x180035343  mov     rcx, rbx; Block
0x180035346  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003534b  mov     rdi, [r14]
0x18003534e  xor     ecx, ecx
0x180035350  mov     rsi, [rbp+0A0h+hObject]
0x180035354  mov     [rbp+0A0h+hObject], rcx
0x180035358  test    rdi, rdi
0x18003535b  jz      short loc_180035380
0x18003535d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180035361  jz      short loc_180035380
0x180035363  call    cs:__imp_GetLastError
0x180035369  mov     rcx, rdi; hObject
0x18003536c  mov     ebx, eax
0x18003536e  call    cs:__imp_CloseHandle
0x180035374  mov     ecx, ebx; dwErrCode
0x180035376  call    cs:__imp_SetLastError
0x18003537c  mov     rcx, [rbp+0A0h+hObject]; hObject
0x180035380  mov     [r14], rsi
0x180035383  xor     edi, edi
0x180035385  lea     rax, [rcx-1]
0x180035389  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003538d  ja      short loc_1800353F8
0x18003538f  call    cs:__imp_CloseHandle
0x180035395  jmp     short loc_1800353F8
0x180035397  mov     rcx, [rbp+0A8h]; this
0x18003539e  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800353a5  mov     edx, 6Ah ; 'j'; void *
0x1800353aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800353af  mov     rcx, rbx; Block
0x1800353b2  mov     edi, eax
0x1800353b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800353b9  test    edi, edi
0x1800353bb  jns     short loc_18003534B
0x1800353bd  mov     rcx, [rbp+0A8h]; this
0x1800353c4  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800353cb  mov     r9d, edi; char *
0x1800353ce  mov     edx, 0B8h; void *
0x1800353d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800353d8  mov     rcx, [rbp+0A0h+hObject]
0x1800353dc  jmp     short loc_180035385
0x1800353de  mov     edx, 0AAh; void *
0x1800353e3  mov     rcx, [rbp+0A8h]; this
0x1800353ea  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800353f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800353f6  mov     edi, eax
0x1800353f8  mov     rcx, [rbp+0A0h+TokenHandle]; hObject
0x1800353fc  lea     rdx, [rcx-1]
0x180035400  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180035404  ja      short loc_18003540C
0x180035406  call    cs:__imp_CloseHandle
0x18003540c  mov     eax, edi
0x18003540e  mov     rcx, [rbp+0A0h+var_20]
0x180035415  xor     rcx, rsp; StackCookie
0x180035418  call    __security_check_cookie
0x18003541d  lea     r11, [rsp+1A0h+var_10]
0x180035425  mov     rbx, [r11+28h]
0x180035429  mov     rsi, [r11+30h]
0x18003542d  mov     rsp, r11
0x180035430  pop     r14
0x180035432  pop     rdi
0x180035433  pop     rbp
0x180035434  retn
```
