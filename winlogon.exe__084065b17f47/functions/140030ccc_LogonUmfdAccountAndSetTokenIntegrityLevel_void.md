# LogonUmfdAccountAndSetTokenIntegrityLevel(void * *)

- ea: `0x140030ccc`
- end: `0x140030f1e`
- name: `?LogonUmfdAccountAndSetTokenIntegrityLevel@@YAJPEAPEAX@Z`
- size: `594`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140030590`

## callees

- `0x140030ccc`
- `0x140053720`
- `0x1400544e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030d7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030ed4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030ed4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030ee9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140030dc0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140030dc0`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x140030dd9`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x140030dd9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140030e26`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140030e26`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x140030ead`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x140030ead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030efe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030efe`
- `SspiCli!LogonUserExExW` at `0x140030d71`
- `SspiCli!LogonUserExExW` at `0x140030d71`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140030da5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140030da5`

## pseudocode

```c
__int64 __fastcall LogonUmfdAccountAndSetTokenIntegrityLevel(void **a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  DWORD LengthSid; // eax
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  __int128 TokenInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v11[24]; // [rsp+98h] [rbp-68h] BYREF
  struct _LUID_AND_ATTRIBUTES PrivilegesToDelete; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v13; // [rsp+BCh] [rbp-44h]
  __int64 v14; // [rsp+C8h] [rbp-38h]
  __int64 v15; // [rsp+D4h] [rbp-2Ch]
  __int64 v16; // [rsp+E0h] [rbp-20h]
  __int64 v17; // [rsp+ECh] [rbp-14h]
  __int64 v18; // [rsp+F8h] [rbp-8h]
  __int64 v19; // [rsp+104h] [rbp+4h]
  __int64 v20; // [rsp+110h] [rbp+10h]

  Sid = 0;
  TokenHandle = 0;
  hObject = 0;
  PrivilegesToDelete.Luid.LowPart = 0;
  TokenInformation = 0;
  memset_0(&PrivilegesToDelete.Luid.HighPart, 0, 0x68u);
  NewState = 0;
  memset(v11, 0, sizeof(v11));
  if ( !(unsigned int)LogonUserExExW(
                        &gwszUmfdAccountName,
                        L"Font Driver Host",
                        &pPassword,
                        2,
                        4,
                        0,
                        &TokenHandle,
                        0,
                        0,
                        0,
                        0) )
    goto LABEL_2;
  if ( !ConvertStringSidToSidW(L"LW", &Sid) )
    goto LABEL_2;
  *(_QWORD *)&TokenInformation = Sid;
  DWORD2(TokenInformation) = 32;
  LengthSid = GetLengthSid(Sid);
  if ( !SetTokenInformation(TokenHandle, TokenIntegrityLevel, &TokenInformation, LengthSid + 16) )
    goto LABEL_2;
  NewState.PrivilegeCount = 3;
  NewState.Privileges[0].Attributes = 2;
  NewState.Privileges[0].Luid = (LUID)30LL;
  *(_DWORD *)&v11[8] = 2;
  *(_QWORD *)v11 = 23;
  *(_DWORD *)&v11[20] = 2;
  *(_QWORD *)&v11[12] = 33;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x28u, 0, 0) )
    goto LABEL_2;
  PrivilegesToDelete.Luid = (LUID)3LL;
  v13 = 5;
  v14 = 12;
  v15 = 19;
  v16 = 29;
  v17 = 34;
  v18 = 21;
  v19 = 25;
  v20 = 36;
  if ( CreateRestrictedToken(TokenHandle, 0, 0, 0, 9u, &PrivilegesToDelete, 0, 0, &hObject) )
  {
    v3 = 0;
    *a1 = hObject;
    hObject = 0;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( Sid )
    LocalFree(Sid);
  return v3;
}

```

## disassembly

```asm
0x140030ccc  push    rbp
0x140030cce  push    rbx
0x140030ccf  push    rsi
0x140030cd0  push    rdi
0x140030cd1  lea     rbp, [rsp-38h]
0x140030cd6  sub     rsp, 138h
0x140030cdd  mov     rax, cs:__security_cookie
0x140030ce4  xor     rax, rsp
0x140030ce7  mov     [rbp+50h+var_30], rax
0x140030ceb  xor     esi, esi
0x140030ced  mov     rdi, rcx
0x140030cf0  xorps   xmm0, xmm0
0x140030cf3  mov     [rsp+150h+Sid], rsi
0x140030cf8  xor     edx, edx; Val
0x140030cfa  mov     [rsp+150h+TokenHandle], rsi
0x140030cff  lea     rcx, [rbp+50h+PrivilegesToDelete.Luid.HighPart]; void *
0x140030d03  mov     [rsp+150h+hObject], rsi
0x140030d08  lea     r8d, [rsi+68h]; Size
0x140030d0c  mov     [rbp+50h+PrivilegesToDelete.Luid.LowPart], esi
0x140030d0f  movdqu  [rsp+150h+TokenInformation], xmm0
0x140030d15  call    memset_0
0x140030d1a  mov     [rsp+150h+var_100], rsi
0x140030d1f  lea     ebx, [rsi+2]
0x140030d22  mov     [rsp+150h+var_108], rsi
0x140030d27  lea     r8, pPassword
0x140030d2e  mov     [rsp+150h+NewTokenHandle], rsi
0x140030d33  lea     rdx, aFontDriverHost; "Font Driver Host"
0x140030d3a  xor     eax, eax
0x140030d3c  mov     [rsp+150h+SidsToRestrict], rsi
0x140030d41  xorps   xmm0, xmm0
0x140030d44  mov     [rbp+50h+var_A8], rax
0x140030d48  lea     rax, [rsp+150h+TokenHandle]
0x140030d4d  mov     r9d, ebx
0x140030d50  mov     qword ptr [rsp+150h+RestrictedSidCount], rax
0x140030d55  lea     rcx, ?gwszUmfdAccountName@@3PAGA; ushort near * gwszUmfdAccountName
0x140030d5c  mov     [rsp+150h+ReturnLength], rsi
0x140030d61  mov     dword ptr [rsp+150h+PreviousState], 4
0x140030d69  movups  xmmword ptr [rbp+50h+NewState.PrivilegeCount], xmm0
0x140030d6d  movups  [rbp+50h+var_B8], xmm0
0x140030d71  call    cs:__imp_LogonUserExExW
0x140030d77  test    eax, eax
0x140030d79  jnz     short loc_140030D99
0x140030d7b  call    cs:__imp_GetLastError
0x140030d81  mov     ebx, eax
0x140030d83  test    eax, eax
0x140030d85  jle     loc_140030ECA
0x140030d8b  movzx   ebx, ax
0x140030d8e  or      ebx, 80070000h
0x140030d94  jmp     loc_140030ECA
0x140030d99  lea     rdx, [rsp+150h+Sid]; Sid
0x140030d9e  lea     rcx, StringSid; "LW"
0x140030da5  call    cs:__imp_ConvertStringSidToSidW
0x140030dab  test    eax, eax
0x140030dad  jz      short loc_140030D7B
0x140030daf  mov     rcx, [rsp+150h+Sid]; pSid
0x140030db4  mov     qword ptr [rsp+150h+TokenInformation], rcx
0x140030db9  mov     dword ptr [rbp+50h+TokenInformation+8], 20h ; ' '
0x140030dc0  call    cs:__imp_GetLengthSid
0x140030dc6  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x140030dcb  lea     r8, [rsp+150h+TokenInformation]; TokenInformation
0x140030dd0  mov     edx, 19h; TokenInformationClass
0x140030dd5  lea     r9d, [rax+10h]; TokenInformationLength
0x140030dd9  call    cs:__imp_SetTokenInformation
0x140030ddf  test    eax, eax
0x140030de1  jz      short loc_140030D7B
0x140030de3  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x140030de8  lea     r8, [rbp+50h+NewState]; NewState
0x140030dec  mov     [rsp+150h+ReturnLength], rsi; ReturnLength
0x140030df1  mov     r9d, 28h ; '('; BufferLength
0x140030df7  xor     edx, edx; DisableAllPrivileges
0x140030df9  mov     [rsp+150h+PreviousState], rsi; PreviousState
0x140030dfe  mov     [rbp+50h+NewState.PrivilegeCount], 3
0x140030e05  mov     [rbp+50h+NewState.Privileges.Attributes], ebx
0x140030e08  mov     qword ptr [rbp+50h+NewState.Privileges.Luid.LowPart], 1Eh
0x140030e10  mov     dword ptr [rbp+50h+var_B8+8], ebx
0x140030e13  mov     qword ptr [rbp+50h+var_B8], 17h
0x140030e1b  mov     dword ptr [rbp+50h+var_A8+4], ebx
0x140030e1e  mov     qword ptr [rbp+50h+var_B8+0Ch], 21h ; '!'
0x140030e26  call    cs:__imp_AdjustTokenPrivileges
0x140030e2c  test    eax, eax
0x140030e2e  jz      loc_140030D7B
0x140030e34  mov     rcx, [rsp+150h+TokenHandle]; ExistingTokenHandle
0x140030e39  lea     rax, [rsp+150h+hObject]
0x140030e3e  mov     [rsp+150h+NewTokenHandle], rax; NewTokenHandle
0x140030e43  xor     r9d, r9d; SidsToDisable
0x140030e46  mov     [rsp+150h+SidsToRestrict], rsi; SidsToRestrict
0x140030e4b  lea     rax, [rbp+50h+PrivilegesToDelete]
0x140030e4f  mov     [rsp+150h+RestrictedSidCount], esi; RestrictedSidCount
0x140030e53  xor     r8d, r8d; DisableSidCount
0x140030e56  mov     [rsp+150h+ReturnLength], rax; PrivilegesToDelete
0x140030e5b  xor     edx, edx; Flags
0x140030e5d  mov     dword ptr [rsp+150h+PreviousState], 9; DeletePrivilegeCount
0x140030e65  mov     qword ptr [rbp+50h+PrivilegesToDelete.Luid.LowPart], 3
0x140030e6d  mov     [rbp+50h+var_94], 5
0x140030e75  mov     [rbp+50h+var_88], 0Ch
0x140030e7d  mov     [rbp+50h+var_7C], 13h
0x140030e85  mov     [rbp+50h+var_70], 1Dh
0x140030e8d  mov     [rbp+50h+var_64], 22h ; '"'
0x140030e95  mov     [rbp+50h+var_58], 15h
0x140030e9d  mov     [rbp+50h+var_4C], 19h
0x140030ea5  mov     [rbp+50h+var_40], 24h ; '$'
0x140030ead  call    cs:__imp_CreateRestrictedToken
0x140030eb3  test    eax, eax
0x140030eb5  jz      loc_140030D7B
0x140030ebb  mov     rax, [rsp+150h+hObject]
0x140030ec0  mov     ebx, esi
0x140030ec2  mov     [rdi], rax
0x140030ec5  mov     [rsp+150h+hObject], rsi
0x140030eca  mov     rcx, [rsp+150h+TokenHandle]; hObject
0x140030ecf  test    rcx, rcx
0x140030ed2  jz      short loc_140030EDF
0x140030ed4  call    cs:__imp_CloseHandle
0x140030eda  mov     [rsp+150h+TokenHandle], rsi
0x140030edf  mov     rcx, [rsp+150h+hObject]; hObject
0x140030ee4  test    rcx, rcx
0x140030ee7  jz      short loc_140030EF4
0x140030ee9  call    cs:__imp_CloseHandle
0x140030eef  mov     [rsp+150h+hObject], rsi
0x140030ef4  mov     rcx, [rsp+150h+Sid]; hMem
0x140030ef9  test    rcx, rcx
0x140030efc  jz      short loc_140030F04
0x140030efe  call    cs:__imp_LocalFree
0x140030f04  mov     eax, ebx
0x140030f06  mov     rcx, [rbp+50h+var_30]
0x140030f0a  xor     rcx, rsp; StackCookie
0x140030f0d  call    __security_check_cookie
0x140030f12  add     rsp, 138h
0x140030f19  pop     rdi
0x140030f1a  pop     rsi
0x140030f1b  pop     rbx
0x140030f1c  pop     rbp
0x140030f1d  retn
```
