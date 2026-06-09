# GetCallerInformationFromToken(void *,_BASIC_CALLER_INFORMATION *,_EXTENDED_CALLER_INFORMATION *)

- ea: `0x18000a4a0`
- end: `0x18000aaeb`
- name: `?GetCallerInformationFromToken@@YAJPEAXPEAU_BASIC_CALLER_INFORMATION@@PEAU_EXTENDED_CALLER_INFORMATION@@@Z`
- size: `1611`
- prototype: `__int64 __fastcall(HANDLE ClientToken, struct _BASIC_CALLER_INFORMATION *, struct _EXTENDED_CALLER_INFORMATION *)`
- caller_count: `19`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008630`
- `0x18000c8d4`
- `0x18000c988`
- `0x180025cf4`
- `0x18003a088`
- `0x18004180c`
- `0x180042820`
- `0x1800458e0`
- `0x180048bc0`
- `0x180064d8c`
- `0x180066e60`
- `0x180067f60`
- `0x180069a44`
- `0x180069d4c`
- `0x18007ecf0`
- `0x1800949c0`
- `0x1800ca320`
- `0x1800cce54`
- `0x1800ccf40`

## callees

- `0x1800088e8`
- `0x18000a4a0`
- `0x18000ab00`
- `0x18000ab90`
- `0x18000ac00`
- `0x18000acdc`
- `0x18000c4f0`
- `0x18004a9cc`
- `0x18004e508`
- `0x18004e58c`
- `0x180061e1c`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a5af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a5d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a7db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a995`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a5af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a5d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a7db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a995`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18000a66c`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18000a66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a860`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a9e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a9e3`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000a574`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000a9ba`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000a574`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000a9ba`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000a807`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000a964`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000a807`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000a964`
- `ntdll!RtlIsMultiSessionSku` at `0x18000a81a`
- `ntdll!RtlIsMultiSessionSku` at `0x18000a81a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000a6cc`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000a6cc`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000a8c7`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000a8c7`

## string_xrefs

- `0x18000aa14`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x18000aa42`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x18000a4f6`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a89d`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a8e8`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a905`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a91f`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a939`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000aa6f`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000aab7`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a76a`: `xboxAccessoryManagement`
- `0x18000a876`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x18000a9f6`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`

## pseudocode

```c
__int64 __fastcall GetCallerInformationFromToken(
        HANDLE ClientToken,
        struct _BASIC_CALLER_INFORMATION *a2,
        struct _EXTENDED_CALLER_INFORMATION *a3)
{
  unsigned __int64 v3; // rbp
  struct _BASIC_CALLER_INFORMATION *v5; // rbx
  bool HasPrivilege; // al
  DWORD *v8; // r14
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  void *v12; // rdx
  const char *v13; // r9
  int v14; // eax
  DWORD CurrentProcessId; // eax
  unsigned __int8 v17; // zf
  __int64 v18; // r13
  char v21; // al
  DWORD v22; // eax
  int LastError; // eax
  unsigned int PackageFullNameFromToken; // eax
  const char *v26; // r9
  bool v28; // sf
  unsigned int v29; // eax
  int ReturnLength; // [rsp+20h] [rbp-60h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-60h]
  unsigned int ReturnLengthb; // [rsp+20h] [rbp-60h]
  unsigned int ReturnLengthc; // [rsp+20h] [rbp-60h]
  unsigned __int8 v34[4]; // [rsp+80h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+F8h]

  v3 = (unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x14) = 0;
  v5 = a2;
  if ( a2 )
  {
    if ( a3 )
LABEL_3:
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        (const char *)0x80004003LL,
        ReturnLength);
  }
  else if ( !a3 )
  {
    goto LABEL_3;
  }
  if ( !a2 )
    v5 = a3;
  *(_WORD *)v5 = 256;
  *((_BYTE *)v5 + 12) = 0;
  *((_DWORD *)v5 + 2) = -1;
  *((_BYTE *)v5 + 1) = IsTokenAppContainer(ClientToken);
  HasPrivilege = DoesTokenHasPrivilege(ClientToken, 7u);
  v8 = (DWORD *)((char *)v5 + 4);
  *((_DWORD *)v5 + 1) = 0;
  *(_BYTE *)v5 = HasPrivilege;
  *((_DWORD *)v5 + 32) = DoesTokenHasPrivilege(ClientToken, 0x1Du);
  *((_BYTE *)v5 + 12) = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  if ( !(unsigned int)CheckTokenCapability(ClientToken, &CapMumaSidBuffer, v3 + 16) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x184,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                  v9);
LABEL_42:
    if ( LastError < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        (const char *)(unsigned int)LastError,
        ReturnLength);
    goto LABEL_10;
  }
  if ( *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) )
  {
LABEL_9:
    *((_BYTE *)v5 + 12) = 1;
    goto LABEL_10;
  }
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0) = 0;
  *(_BYTE *)v3 = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
  v18 = -6;
  if ( ClientToken )
    v18 = (__int64)ClientToken;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0) = 0;
  if ( !GetTokenInformation((HANDLE)v18, TokenIsAppContainer, (LPVOID)(v3 + 8), 4u, (PDWORD)(v3 + 12)) )
    goto LABEL_40;
  if ( !*(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
  {
    if ( !(unsigned int)CheckTokenMembershipEx(
                          v18,
                          &CapMumaGroupSidBuffer,
                          *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                          v3 + 4) )
      goto LABEL_40;
    if ( !*(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
    {
      if ( !(unsigned __int8)RtlIsMultiSessionSku()
        && !(unsigned int)CheckTokenMembershipEx(
                            v18,
                            &DefaultAliasWellKnownSid,
                            *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                            v3 + 4) )
      {
        goto LABEL_40;
      }
      if ( !*(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
        goto LABEL_56;
    }
  }
  if ( !*(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 8) )
  {
LABEL_36:
    v21 = 1;
    *(_BYTE *)v3 = 1;
    goto LABEL_37;
  }
  if ( (unsigned int)CheckTokenCapability(v18, &CapMumaSidBuffer, v3 + 4) )
  {
    if ( *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
      goto LABEL_36;
LABEL_56:
    v21 = 0;
    goto LABEL_37;
  }
LABEL_40:
  v22 = GetLastError();
  if ( v22 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x18D,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                  (const char *)v22,
                  ReturnLengthb);
    goto LABEL_42;
  }
  v21 = *(_BYTE *)v3;
LABEL_37:
  if ( *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) || v21 )
    goto LABEL_9;
LABEL_10:
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
  if ( !GetTokenInformation(ClientToken, TokenSessionId, (char *)v5 + 8, 4u, (PDWORD)(v3 + 12)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v10);
  if ( !GetTokenInformation(ClientToken, TokenUser, (char *)v5 + 32, 0x54u, (PDWORD)(v3 + 20)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v11);
  v12 = (void *)*((_QWORD *)v5 + 4);
  *((_QWORD *)v5 + 15) = v12;
  *((_BYTE *)v5 + 2) = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0) = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 20;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0) = 0;
  if ( !v12 )
  {
    if ( !GetTokenInformation(ClientToken, TokenUser, (LPVOID)(v3 + 32), 0x54u, (PDWORD)(v3 + 12)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v26);
    v12 = *(void **)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
  }
  if ( !AccessCheckByType(
          qword_18010A700,
          v12,
          ClientToken,
          1u,
          0,
          0,
          (PGENERIC_MAPPING)&GenericMapping,
          (PPRIVILEGE_SET)(v3 + 160),
          (LPDWORD)(v3 + 4),
          (LPDWORD)(v3 + 8),
          (LPBOOL)(v3 + 16)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v13);
  if ( *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10)
    && (*(_BYTE *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 8) & 1) != 0 )
  {
    *((_BYTE *)v5 + 2) = 1;
  }
  if ( v5 == (struct _BASIC_CALLER_INFORMATION *)-4LL )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.cpp",
      (const char *)0x80004003LL,
      ReturnLengtha);
    goto LABEL_21;
  }
  *v8 = 0;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 3;
  *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x24) = 112;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 0;
  *(_OWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = 0;
  v14 = RpcServerInqCallAttributesW(0, (void *)(v3 + 32));
  if ( !v14 )
  {
    CurrentProcessId = *(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60);
LABEL_20:
    *v8 = CurrentProcessId;
    goto LABEL_21;
  }
  if ( v14 == 1725 )
  {
    CurrentProcessId = GetCurrentProcessId();
    goto LABEL_20;
  }
  v28 = v14 < 0;
  if ( v14 > 0 )
  {
    v14 = (unsigned __int16)v14 | 0x80070000;
    v28 = v14 < 0;
  }
  if ( v28 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.cpp",
      (const char *)(unsigned int)v14,
      ReturnLengtha);
LABEL_21:
  if ( !*((_BYTE *)v5 + 1)
    || (*(_DWORD *)(((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 128,
        PackageFullNameFromToken = GetPackageFullNameFromToken(ClientToken, (UINT32 *)(v3 + 12), (PWSTR)v5 + 66),
        PackageFullNameFromToken == 15700) )
  {
    *((_WORD *)v5 + 66) = 0;
  }
  else if ( PackageFullNameFromToken )
  {
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)PackageFullNameFromToken,
      ReturnLengtha);
  }
  if ( a3 )
  {
    v17 = (_BYTE)word_180148290 == 0;
    *(_BYTE *)v3 = 0;
    if ( SeAllowSessionImpersonation )
    {
      v29 = CheckTokenForAccessThroughCapability(
              ClientToken,
              0,
              &CapSessionImpersonationGroupSidBuffer,
              &CapSessionImpersonationSidBuffer,
              v17,
              0,
              (unsigned __int8 *)((unsigned __int64)v34 & 0xFFFFFFFFFFFFFFE0uLL));
      if ( v29 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1FF,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          (const char *)v29,
          ReturnLengthc);
      if ( *(_BYTE *)v3 )
        *((_BYTE *)a3 + 416) = 1;
    }
    *((_BYTE *)a3 + 417) = (int)CapabilityAccessCheck(ClientToken, L"userSigninSupport") >= 0;
    *((_BYTE *)a3 + 418) = (int)CapabilityAccessCheck(ClientToken, L"shellExperience") >= 0;
    *((_BYTE *)a3 + 419) = (int)CapabilityAccessCheck(ClientToken, L"xboxAccessoryManagement") >= 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a4a0  mov     [rsp-8+arg_18], rbx
0x18000a4a5  push    rbp
0x18000a4a6  push    rsi
0x18000a4a7  push    rdi
0x18000a4a8  push    r12
0x18000a4aa  push    r13
0x18000a4ac  push    r14
0x18000a4ae  push    r15
0x18000a4b0  sub     rsp, 140h
0x18000a4b7  lea     rbp, [rsp+80h]
0x18000a4bf  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18000a4c3  mov     rax, cs:__security_cookie
0x18000a4ca  xor     rax, rsp
0x18000a4cd  mov     [rbp+0F0h+var_38], rax
0x18000a4d4  xor     r12d, r12d
0x18000a4d7  mov     rsi, r8
0x18000a4da  mov     [rbp+0F0h+var_DC], r12d
0x18000a4de  mov     rbx, rdx
0x18000a4e1  mov     rdi, rcx
0x18000a4e4  test    rdx, rdx
0x18000a4e7  jnz     short loc_18000A50E
0x18000a4e9  test    r8, r8
0x18000a4ec  jnz     short loc_18000A513
0x18000a4ee  mov     rcx, [rsp+178h]; this
0x18000a4f6  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000a4fd  mov     r9d, 80004003h; char *
0x18000a503  mov     edx, 1CCh; void *
0x18000a508  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a50e  test    rsi, rsi
0x18000a511  jnz     short loc_18000A4EE
0x18000a513  test    rbx, rbx
0x18000a516  cmovz   rbx, rsi
0x18000a51a  mov     word ptr [rbx], 100h
0x18000a51f  mov     [rbx+0Ch], r12b
0x18000a523  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18000a52a  call    ?IsTokenAppContainer@@YA_NPEAX@Z; IsTokenAppContainer(void *)
0x18000a52f  mov     edx, 7; unsigned int
0x18000a534  mov     [rbx+1], al
0x18000a537  mov     rcx, rdi; void *
0x18000a53a  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x18000a53f  lea     r14, [rbx+4]
0x18000a543  mov     edx, 1Dh; unsigned int
0x18000a548  mov     rcx, rdi; void *
0x18000a54b  mov     [r14], r12d
0x18000a54e  mov     [rbx], al
0x18000a550  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x18000a555  movzx   eax, al
0x18000a558  lea     r8, [rbp+0F0h+var_E0]
0x18000a55c  mov     [rbx+80h], eax
0x18000a562  lea     rdx, ?CapMumaSidBuffer@@3PAEA; uchar near * CapMumaSidBuffer
0x18000a569  mov     rcx, rdi
0x18000a56c  mov     [rbx+0Ch], r12b
0x18000a570  mov     [rbp+0F0h+var_E0], r12d
0x18000a574  call    cs:__imp_CheckTokenCapability
0x18000a57a  test    eax, eax
0x18000a57c  jz      loc_18000A9EE
0x18000a582  cmp     [rbp+0F0h+var_E0], r12d
0x18000a586  jz      loc_18000A791
0x18000a58c  mov     byte ptr [rbx+0Ch], 1
0x18000a590  lea     rax, [rbp+0F0h+packageFullNameLength]
0x18000a594  mov     [rbp+0F0h+packageFullNameLength], r12d
0x18000a598  mov     r9d, 4; TokenInformationLength
0x18000a59e  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x18000a5a3  lea     r8, [rbx+8]; TokenInformation
0x18000a5a7  mov     edx, 0Ch; TokenInformationClass
0x18000a5ac  mov     rcx, rdi; TokenHandle
0x18000a5af  call    cs:__imp_GetTokenInformation
0x18000a5b5  test    eax, eax
0x18000a5b7  jz      loc_18000A8FD
0x18000a5bd  lea     rax, [rbp+0F0h+var_DC]
0x18000a5c1  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000a5c7  lea     r8, [rbx+20h]; TokenInformation
0x18000a5cb  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x18000a5d0  mov     edx, 1; TokenInformationClass
0x18000a5d5  mov     rcx, rdi; TokenHandle
0x18000a5d8  call    cs:__imp_GetTokenInformation
0x18000a5de  test    eax, eax
0x18000a5e0  jz      loc_18000A917
0x18000a5e6  mov     rdx, [rbx+20h]; PrincipalSelfSid
0x18000a5ea  xor     eax, eax
0x18000a5ec  mov     [rbx+78h], rdx
0x18000a5f0  xorps   xmm0, xmm0
0x18000a5f3  mov     [rbx+2], al
0x18000a5f6  mov     [rbp+0F0h+var_50.Privilege.Attributes], eax
0x18000a5fc  mov     [rbp+0F0h+TokenInformation], r12d
0x18000a600  mov     [rbp+0F0h+var_E0], r12d
0x18000a604  mov     [rbp+0F0h+var_EC], 14h
0x18000a60b  mov     [rbp+0F0h+packageFullNameLength], r12d
0x18000a60f  movups  xmmword ptr [rbp+0F0h+var_50.PrivilegeCount], xmm0
0x18000a616  test    rdx, rdx
0x18000a619  jz      loc_18000A97A
0x18000a61f  lea     rax, [rbp+0F0h+var_E0]
0x18000a623  mov     r9d, 1; DesiredAccess
0x18000a629  mov     [rsp+170h+AccessStatus], rax; AccessStatus
0x18000a62e  lea     rcx, qword_18010A700; pSecurityDescriptor
0x18000a635  lea     rax, [rbp+0F0h+TokenInformation]
0x18000a639  mov     r8, rdi; ClientToken
0x18000a63c  mov     [rsp+170h+GrantedAccess], rax; GrantedAccess
0x18000a641  lea     rax, [rbp+0F0h+var_EC]
0x18000a645  mov     [rsp+170h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000a64a  lea     rax, [rbp+0F0h+var_50]
0x18000a651  mov     [rsp+170h+PrivilegeSet], rax; PrivilegeSet
0x18000a656  lea     rax, GenericMapping
0x18000a65d  mov     [rsp+170h+GenericMapping], rax; GenericMapping
0x18000a662  mov     [rsp+170h+ObjectTypeListLength], r12d; ObjectTypeListLength
0x18000a667  mov     [rsp+170h+ReturnLength], r12; int
0x18000a66c  call    cs:__imp_AccessCheckByType
0x18000a672  test    eax, eax
0x18000a674  jz      loc_18000A931
0x18000a67a  cmp     [rbp+0F0h+var_E0], 0
0x18000a67e  jz      short loc_18000A68A
0x18000a680  test    byte ptr [rbp+0F0h+TokenInformation], 1
0x18000a684  jz      short loc_18000A68A
0x18000a686  mov     byte ptr [rbx+2], 1
0x18000a68a  test    r14, r14
0x18000a68d  jz      loc_18000AA0C
0x18000a693  xorps   xmm0, xmm0
0x18000a696  mov     [r14], r12d
0x18000a699  lea     rdx, [rbp+0F0h+RpcCallAttributes]; RpcCallAttributes
0x18000a69d  mov     dword ptr [rbp+0F0h+RpcCallAttributes], 3
0x18000a6a4  xor     ecx, ecx; ClientBinding
0x18000a6a6  mov     dword ptr [rbp+0F0h+RpcCallAttributes+4], 70h ; 'p'
0x18000a6ad  movups  [rbp+0F0h+var_C8], xmm0
0x18000a6b1  movups  [rbp+0F0h+var_B8], xmm0
0x18000a6b5  movups  [rbp+0F0h+var_A8], xmm0
0x18000a6b9  movups  [rbp+0F0h+var_98], xmm0
0x18000a6bd  movups  [rbp+0F0h+var_88], xmm0
0x18000a6c1  movups  [rbp+0F0h+var_78], xmm0
0x18000a6c5  movups  [rbp+0F0h+var_68], xmm0
0x18000a6cc  call    cs:__imp_RpcServerInqCallAttributesW
0x18000a6d2  test    eax, eax
0x18000a6d4  jnz     loc_18000A9DC
0x18000a6da  mov     eax, dword ptr [rbp+0F0h+var_98+8]
0x18000a6dd  mov     [r14], eax
0x18000a6e0  cmp     byte ptr [rbx+1], 0
0x18000a6e4  jnz     loc_18000A8B2
0x18000a6ea  mov     [rbx+84h], r12w
0x18000a6f2  test    rsi, rsi
0x18000a6f5  jnz     short loc_18000A723
0x18000a6f7  xor     eax, eax
0x18000a6f9  mov     rcx, [rbp+0F0h+var_38]
0x18000a700  xor     rcx, rsp; StackCookie
0x18000a703  call    __security_check_cookie
0x18000a708  mov     rbx, [rsp+170h+arg_18]
0x18000a710  add     rsp, 140h
0x18000a717  pop     r15
0x18000a719  pop     r14
0x18000a71b  pop     r13
0x18000a71d  pop     r12
0x18000a71f  pop     rdi
0x18000a720  pop     rsi
0x18000a721  pop     rbp
0x18000a722  retn
0x18000a723  cmp     byte ptr cs:word_180148290, 0
0x18000a72a  mov     [rbp+0F0h+var_F0], 0
0x18000a72e  setz    al
0x18000a731  cmp     cs:?SeAllowSessionImpersonation@@3KA, 0; ulong SeAllowSessionImpersonation
0x18000a738  jnz     loc_18000AA81
0x18000a73e  lea     rdx, aUsersigninsupp; "userSigninSupport"
0x18000a745  mov     rcx, rdi; void *
0x18000a748  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x18000a74d  shr     eax, 1Fh
0x18000a750  lea     rdx, aShellexperienc; "shellExperience"
0x18000a757  xor     al, 1
0x18000a759  mov     rcx, rdi; void *
0x18000a75c  mov     [rsi+1A1h], al
0x18000a762  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x18000a767  shr     eax, 1Fh
0x18000a76a  lea     rdx, aXboxaccessorym; "xboxAccessoryManagement"
0x18000a771  xor     al, 1
0x18000a773  mov     rcx, rdi; void *
0x18000a776  mov     [rsi+1A2h], al
0x18000a77c  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x18000a781  shr     eax, 1Fh
0x18000a784  xor     al, 1
0x18000a786  mov     [rsi+1A3h], al
0x18000a78c  jmp     loc_18000A6F7
0x18000a791  xor     eax, eax
0x18000a793  mov     [rbp+0F0h+var_EC], r12d
0x18000a797  mov     [rbp+0F0h+var_50.Privilege.Attributes], eax
0x18000a79d  lea     r8, [rbp+0F0h+TokenInformation]; TokenInformation
0x18000a7a1  mov     [rbp+0F0h+var_F0], al
0x18000a7a4  xorps   xmm0, xmm0
0x18000a7a7  lea     rax, [rbp+0F0h+packageFullNameLength]
0x18000a7ab  mov     [rbp+0F0h+TokenInformation], r12d
0x18000a7af  test    rdi, rdi
0x18000a7b2  mov     [rbp+0F0h+packageFullNameLength], r12d
0x18000a7b6  mov     r13, 0FFFFFFFFFFFFFFFAh
0x18000a7bd  mov     [rsp+170h+ReturnLength], rax; int
0x18000a7c2  cmovnz  r13, rdi
0x18000a7c6  mov     r9d, 4; TokenInformationLength
0x18000a7cc  mov     rcx, r13; TokenHandle
0x18000a7cf  mov     edx, 1Dh; TokenInformationClass
0x18000a7d4  movups  xmmword ptr [rbp+0F0h+var_50.PrivilegeCount], xmm0
0x18000a7db  call    cs:__imp_GetTokenInformation
0x18000a7e1  mov     r12d, eax
0x18000a7e4  test    eax, eax
0x18000a7e6  jz      short loc_18000A860
0x18000a7e8  cmp     [rbp+0F0h+var_EC], 0
0x18000a7ec  jnz     short loc_18000A832
0x18000a7ee  xor     r8d, r8d
0x18000a7f1  lea     r9, [rbp+0F0h+var_EC]
0x18000a7f5  cmp     [rbp+0F0h+TokenInformation], r8d
0x18000a7f9  lea     rdx, ?CapMumaGroupSidBuffer@@3PAEA; uchar near * CapMumaGroupSidBuffer
0x18000a800  mov     rcx, r13
0x18000a803  setnz   r8b
0x18000a807  call    cs:__imp_CheckTokenMembershipEx
0x18000a80d  mov     r12d, eax
0x18000a810  test    eax, eax
0x18000a812  jz      short loc_18000A860
0x18000a814  cmp     [rbp+0F0h+var_EC], 0
0x18000a818  jnz     short loc_18000A832
0x18000a81a  call    cs:__imp_RtlIsMultiSessionSku
0x18000a820  test    al, al
0x18000a822  jz      loc_18000A94B
0x18000a828  cmp     [rbp+0F0h+var_EC], 0
0x18000a82c  jz      loc_18000A9D5
0x18000a832  cmp     [rbp+0F0h+TokenInformation], 0
0x18000a836  jnz     loc_18000A9AC
0x18000a83c  mov     al, 1
0x18000a83e  mov     [rbp+0F0h+var_F0], al
0x18000a841  test    r12d, r12d
0x18000a844  jz      short loc_18000A860
0x18000a846  xor     r12d, r12d
0x18000a849  cmp     [rbp+0F0h+var_E0], r12d
0x18000a84d  jnz     loc_18000A58C
0x18000a853  test    al, al
0x18000a855  jz      loc_18000A590
0x18000a85b  jmp     loc_18000A58C
0x18000a860  call    cs:__imp_GetLastError
0x18000a866  test    eax, eax
0x18000a868  jz      loc_18000AACC
0x18000a86e  mov     rcx, [rsp+178h]; this
0x18000a876  lea     r8, aOnecoreDsSecur_79; "onecore\\ds\\security\\umstartup\\aulog"...
0x18000a87d  mov     r9d, eax; char *
0x18000a880  mov     edx, 18Dh; void *
0x18000a885  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a88a  xor     r12d, r12d
0x18000a88d  test    eax, eax
0x18000a88f  jns     loc_18000A590
0x18000a895  mov     rcx, [rsp+178h]; this
0x18000a89d  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000a8a4  mov     r9d, eax; char *
0x18000a8a7  mov     edx, 1E0h; void *
0x18000a8ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a8b2  lea     r8, [rbx+84h]; packageFullName
0x18000a8b9  mov     [rbp+0F0h+packageFullNameLength], 80h
0x18000a8c0  lea     rdx, [rbp+0F0h+packageFullNameLength]; packageFullNameLength
0x18000a8c4  mov     rcx, rdi; token
0x18000a8c7  call    cs:__imp_GetPackageFullNameFromToken
0x18000a8cd  cmp     eax, 3D54h
0x18000a8d2  jz      loc_18000A6EA
0x18000a8d8  test    eax, eax
0x18000a8da  jz      loc_18000A6F2
0x18000a8e0  mov     rcx, [rsp+178h]; this
0x18000a8e8  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000a8ef  mov     r9d, eax; char *
0x18000a8f2  mov     edx, 1F3h; void *
0x18000a8f7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a8fd  mov     rcx, [rsp+178h]; this
0x18000a905  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000a90c  mov     edx, 1AEh; void *
0x18000a911  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a917  mov     rcx, [rsp+178h]; this
0x18000a91f  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000a926  mov     edx, 1E2h; void *
0x18000a92b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a931  mov     rcx, [rsp+178h]; this
0x18000a939  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000a940  mov     edx, 119h; void *
0x18000a945  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a94b  xor     r8d, r8d
0x18000a94e  lea     r9, [rbp+0F0h+var_EC]
0x18000a952  cmp     [rbp+0F0h+TokenInformation], r8d
0x18000a956  lea     rdx, ?DefaultAliasWellKnownSid@@3PAEA; uchar near * DefaultAliasWellKnownSid
0x18000a95d  mov     rcx, r13
0x18000a960  setnz   r8b
0x18000a964  call    cs:__imp_CheckTokenMembershipEx
0x18000a96a  mov     r12d, eax
0x18000a96d  test    eax, eax
0x18000a96f  jnz     loc_18000A828
0x18000a975  jmp     loc_18000A860
0x18000a97a  lea     rax, [rbp+0F0h+packageFullNameLength]
0x18000a97e  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000a984  lea     r8, [rbp+0F0h+RpcCallAttributes]; TokenInformation
0x18000a988  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x18000a98d  mov     edx, 1; TokenInformationClass
0x18000a992  mov     rcx, rdi; TokenHandle
0x18000a995  call    cs:__imp_GetTokenInformation
0x18000a99b  test    eax, eax
0x18000a99d  jz      loc_18000AA67
0x18000a9a3  mov     rdx, [rbp+0F0h+RpcCallAttributes]
0x18000a9a7  jmp     loc_18000A61F
0x18000a9ac  lea     r8, [rbp+0F0h+var_EC]
0x18000a9b0  mov     rcx, r13
0x18000a9b3  lea     rdx, ?CapMumaSidBuffer@@3PAEA; uchar near * CapMumaSidBuffer
0x18000a9ba  call    cs:__imp_CheckTokenCapability
0x18000a9c0  mov     r12d, eax
0x18000a9c3  test    eax, eax
0x18000a9c5  jz      loc_18000A860
  ... truncated ...
```
