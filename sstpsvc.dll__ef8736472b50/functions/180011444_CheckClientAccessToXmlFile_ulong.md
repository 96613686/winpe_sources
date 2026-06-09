# CheckClientAccessToXmlFile(ulong)

- ea: `0x180011444`
- end: `0x1800117fb`
- name: `?CheckClientAccessToXmlFile@@YAHK@Z`
- size: `951`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014900`
- `0x180015500`

## callees

- `0x1800080dc`
- `0x1800089dc`
- `0x180008b90`
- `0x1800090c0`
- `0x180011444`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001179a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800117ae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001179a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800117ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001157b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001164e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001157b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001164e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117c5`
- `RPCRT4!RpcRevertToSelf` at `0x180011736`
- `RPCRT4!RpcRevertToSelf` at `0x180011736`
- `RPCRT4!RpcImpersonateClient` at `0x1800115f6`
- `RPCRT4!RpcImpersonateClient` at `0x1800115f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001161f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001161f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001163e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001163e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800116ca`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800116ca`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001156b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800115b2`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001156b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800115b2`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180011681`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180011681`

## string_xrefs

- `0x18001150b`: `CheckClientAccessToXmlFile: GetXmlFilePath failed with error %d`
- `0x1800115df`: `CheckClientAccessToXmlFile: GetFileSecurity method failed with error %d`
- `0x180011613`: `CheckClientAccess: RpcImpersonateClient failed with error %d`
- `0x18001166b`: `CheckClientAccess: OpenThreadToken failed with error %d`
- `0x1800116f3`: `CheckClientAccess: AccessCheck failed with error %d`
- `0x18001175a`: `CheckClientAccess: RpcRevertToSelf failed with error %d`

## pseudocode

```c
_BOOL8 __fastcall CheckClientAccessToXmlFile()
{
  void *v0; // rsi
  unsigned int XmlFilePath; // eax
  WCHAR *v2; // rdi
  DWORD LastError; // eax
  const wchar_t *v4; // rdx
  HANDLE CurrentThread; // rax
  unsigned int v6; // eax
  DWORD nLength; // [rsp+40h] [rbp-878h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-870h] BYREF
  BOOL AccessStatus; // [rsp+50h] [rbp-868h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-860h] BYREF
  DWORD GrantedAccess; // [rsp+60h] [rbp-858h] BYREF
  DWORD PrivilegeSetLength; // [rsp+64h] [rbp-854h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-850h] BYREF
  GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-840h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+88h] [rbp-830h] BYREF
  int v17; // [rsp+A0h] [rbp-818h] BYREF
  _BYTE v18[2044]; // [rsp+A4h] [rbp-814h] BYREF
  std::bad_alloc *v19; // [rsp+8A0h] [rbp-18h] BYREF

  AccessMask = 1179926;
  TokenHandle = (HANDLE)-1LL;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  AccessStatus = 0;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  GrantedAccess = 0;
  v0 = 0;
  nLength = 0;
  lpFileName = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  XmlFilePath = GetXmlFilePath((unsigned __int16 **)&lpFileName);
  if ( XmlFilePath )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"CheckClientAccessToXmlFile: GetXmlFilePath failed with error %d", XmlFilePath);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v17);
    }
LABEL_5:
    v2 = (WCHAR *)lpFileName;
    goto LABEL_27;
  }
  v2 = (WCHAR *)lpFileName;
  if ( GetFileSecurityW(lpFileName, 7u, 0, nLength, &nLength) )
    goto LABEL_14;
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    try
    {
      v0 = operator new[](nLength);
    }
    catch ( std::bad_alloc *v19 )
    {
      v0 = 0;
      goto LABEL_5;
    }
    if ( GetFileSecurityW(v2, 7u, v0, nLength, &nLength) )
    {
LABEL_14:
      LastError = RpcImpersonateClient(0);
      if ( LastError )
      {
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_27;
        v4 = L"CheckClientAccess: RpcImpersonateClient failed with error %d";
      }
      else
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || (LastError = GetLastError()) == 0 )
        {
          MapGenericMask(&AccessMask, &GenericMapping);
          if ( AccessCheck(
                 v0,
                 TokenHandle,
                 AccessMask,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus) )
          {
            goto LABEL_27;
          }
          LastError = GetLastError();
          if ( !LastError || (byte_18002E903 & 8) == 0 )
            goto LABEL_27;
          v4 = L"CheckClientAccess: AccessCheck failed with error %d";
        }
        else
        {
          if ( (byte_18002E903 & 8) == 0 )
            goto LABEL_27;
          v4 = L"CheckClientAccess: OpenThreadToken failed with error %d";
        }
      }
      goto LABEL_25;
    }
    LastError = GetLastError();
  }
  if ( !LastError )
    goto LABEL_14;
  if ( (byte_18002E903 & 8) == 0 )
    goto LABEL_27;
  v4 = L"CheckClientAccessToXmlFile: GetFileSecurity method failed with error %d";
LABEL_25:
  LOWORD(v17) = 0;
  FormatRRASErrorString(&v17, v4, LastError);
  if ( (byte_18002E903 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v17);
LABEL_27:
  v6 = RpcRevertToSelf();
  if ( v6 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"CheckClientAccess: RpcRevertToSelf failed with error %d", v6);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v17);
    }
  }
  if ( v0 )
    operator delete[](v0);
  if ( v2 )
    operator delete[](v2);
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  return AccessStatus;
}

```

## disassembly

```asm
0x180011444  mov     [rsp+arg_0], rbx
0x180011449  mov     [rsp+arg_8], rsi
0x18001144e  push    rdi
0x18001144f  sub     rsp, 8B0h
0x180011456  mov     rax, cs:__security_cookie
0x18001145d  xor     rax, rsp
0x180011460  mov     [rsp+8B8h+var_10], rax
0x180011468  mov     ecx, 120116h
0x18001146d  mov     [rsp+8B8h+AccessMask], ecx
0x180011471  mov     [rsp+8B8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001147a  xorps   xmm0, xmm0
0x18001147d  xor     eax, eax
0x18001147f  movups  xmmword ptr [rsp+8B8h+PrivilegeSet.PrivilegeCount], xmm0
0x180011487  mov     [rsp+8B8h+PrivilegeSet.Privilege.Attributes], eax
0x18001148e  mov     [rsp+8B8h+var_854], 14h
0x180011496  xor     ebx, ebx
0x180011498  mov     [rsp+8B8h+var_868], ebx
0x18001149c  mov     [rsp+8B8h+GenericMapping.GenericRead], 120089h
0x1800114a4  mov     [rsp+8B8h+GenericMapping.GenericWrite], ecx
0x1800114a8  mov     [rsp+8B8h+GenericMapping.GenericExecute], 1200A0h
0x1800114b3  mov     [rsp+8B8h+GenericMapping.GenericAll], 1F01FFh
0x1800114be  mov     [rsp+8B8h+var_858], ebx
0x1800114c2  mov     esi, ebx
0x1800114c4  mov     [rsp+8B8h+nLength], ebx
0x1800114c8  mov     [rsp+8B8h+lpFileName], rbx
0x1800114cd  mov     [rsp+8B8h+var_818], ebx
0x1800114d4  xor     edx, edx; Val
0x1800114d6  mov     r8d, 7FCh; Size
0x1800114dc  lea     rcx, [rsp+8B8h+var_814]; void *
0x1800114e4  call    memset_0
0x1800114e9  lea     rcx, [rsp+8B8h+lpFileName]; unsigned __int16 **
0x1800114ee  call    ?GetXmlFilePath@@YAKPEAPEAG@Z; GetXmlFilePath(ushort * *)
0x1800114f3  test    eax, eax
0x1800114f5  jz      short loc_18001154D
0x1800114f7  test    cs:byte_18002E903, 8
0x1800114fe  jz      short loc_180011543
0x180011500  mov     word ptr [rsp+8B8h+var_818], bx
0x180011508  mov     r8d, eax
0x18001150b  lea     rdx, aCheckclientacc_3; "CheckClientAccessToXmlFile: GetXmlFileP"...
0x180011512  lea     rcx, [rsp+8B8h+var_818]
0x18001151a  call    FormatRRASErrorString
0x18001151f  test    cs:byte_18002E903, 8
0x180011526  jz      short loc_180011543
0x180011528  lea     r8, [rsp+8B8h+var_818]
0x180011530  lea     rdx, RasSSTPSvcTraceError
0x180011537  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001153e  call    McTemplateU0z_EventWriteTransfer
0x180011543  mov     rdi, [rsp+8B8h+lpFileName]
0x180011548  jmp     loc_180011736
0x18001154d  lea     rax, [rsp+8B8h+nLength]
0x180011552  mov     [rsp+8B8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180011557  mov     r9d, [rsp+8B8h+nLength]; nLength
0x18001155c  xor     r8d, r8d; pSecurityDescriptor
0x18001155f  lea     edx, [r8+7]; RequestedInformation
0x180011563  mov     rdi, [rsp+8B8h+lpFileName]
0x180011568  mov     rcx, rdi; lpFileName
0x18001156b  call    cs:__imp_GetFileSecurityW
0x180011572  nop     dword ptr [rax+rax+00h]
0x180011577  test    eax, eax
0x180011579  jnz     short loc_1800115F4
0x18001157b  call    cs:__imp_GetLastError
0x180011582  nop     dword ptr [rax+rax+00h]
0x180011587  cmp     eax, 7Ah ; 'z'
0x18001158a  jnz     short loc_1800115CE
0x18001158c  mov     ecx, [rsp+8B8h+nLength]; unsigned __int64
0x180011590  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011595  mov     rsi, rax
0x180011598  lea     rax, [rsp+8B8h+nLength]
0x18001159d  mov     [rsp+8B8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800115a2  mov     r9d, [rsp+8B8h+nLength]; nLength
0x1800115a7  mov     r8, rsi; pSecurityDescriptor
0x1800115aa  mov     edx, 7; RequestedInformation
0x1800115af  mov     rcx, rdi; lpFileName
0x1800115b2  call    cs:__imp_GetFileSecurityW
0x1800115b9  nop     dword ptr [rax+rax+00h]
0x1800115be  test    eax, eax
0x1800115c0  jnz     short loc_1800115F4
0x1800115c2  call    cs:__imp_GetLastError
0x1800115c9  nop     dword ptr [rax+rax+00h]
0x1800115ce  test    eax, eax
0x1800115d0  jz      short loc_1800115F4
0x1800115d2  test    cs:byte_18002E903, 8
0x1800115d9  jz      loc_180011736
0x1800115df  lea     rdx, aCheckclientacc_4; "CheckClientAccessToXmlFile: GetFileSecu"...
0x1800115e6  jmp     loc_1800116FA
0x1800115eb  xor     ebx, ebx
0x1800115ed  mov     esi, ebx
0x1800115ef  jmp     loc_180011543
0x1800115f4  xor     ecx, ecx; BindingHandle
0x1800115f6  call    cs:__imp_RpcImpersonateClient
0x1800115fd  nop     dword ptr [rax+rax+00h]
0x180011602  test    eax, eax
0x180011604  jz      short loc_18001161F
0x180011606  test    cs:byte_18002E903, 8
0x18001160d  jz      loc_180011736
0x180011613  lea     rdx, aCheckclientacc_2; "CheckClientAccess: RpcImpersonateClient"...
0x18001161a  jmp     loc_1800116FA
0x18001161f  call    cs:__imp_GetCurrentThread
0x180011626  nop     dword ptr [rax+rax+00h]
0x18001162b  mov     rcx, rax; ThreadHandle
0x18001162e  lea     r9, [rsp+8B8h+TokenHandle]; TokenHandle
0x180011633  mov     edx, 0F01FFh; DesiredAccess
0x180011638  mov     r8d, 1; OpenAsSelf
0x18001163e  call    cs:__imp_OpenThreadToken
0x180011645  nop     dword ptr [rax+rax+00h]
0x18001164a  test    eax, eax
0x18001164c  jnz     short loc_180011677
0x18001164e  call    cs:__imp_GetLastError
0x180011655  nop     dword ptr [rax+rax+00h]
0x18001165a  test    eax, eax
0x18001165c  jz      short loc_180011677
0x18001165e  test    cs:byte_18002E903, 8
0x180011665  jz      loc_180011736
0x18001166b  lea     rdx, aCheckclientacc_0; "CheckClientAccess: OpenThreadToken fail"...
0x180011672  jmp     loc_1800116FA
0x180011677  lea     rdx, [rsp+8B8h+GenericMapping]; GenericMapping
0x18001167c  lea     rcx, [rsp+8B8h+AccessMask]; AccessMask
0x180011681  call    cs:__imp_MapGenericMask
0x180011688  nop     dword ptr [rax+rax+00h]
0x18001168d  lea     rax, [rsp+8B8h+var_868]
0x180011692  mov     [rsp+8B8h+AccessStatus], rax; AccessStatus
0x180011697  lea     rax, [rsp+8B8h+var_858]
0x18001169c  mov     [rsp+8B8h+GrantedAccess], rax; GrantedAccess
0x1800116a1  lea     rax, [rsp+8B8h+var_854]
0x1800116a6  mov     [rsp+8B8h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800116ab  lea     rax, [rsp+8B8h+PrivilegeSet]
0x1800116b3  mov     [rsp+8B8h+lpnLengthNeeded], rax; PrivilegeSet
0x1800116b8  lea     r9, [rsp+8B8h+GenericMapping]; GenericMapping
0x1800116bd  mov     r8d, [rsp+8B8h+AccessMask]; DesiredAccess
0x1800116c2  mov     rdx, [rsp+8B8h+TokenHandle]; ClientToken
0x1800116c7  mov     rcx, rsi; pSecurityDescriptor
0x1800116ca  call    cs:__imp_AccessCheck
0x1800116d1  nop     dword ptr [rax+rax+00h]
0x1800116d6  test    eax, eax
0x1800116d8  jnz     short loc_180011736
0x1800116da  call    cs:__imp_GetLastError
0x1800116e1  nop     dword ptr [rax+rax+00h]
0x1800116e6  test    eax, eax
0x1800116e8  jz      short loc_180011736
0x1800116ea  test    cs:byte_18002E903, 8
0x1800116f1  jz      short loc_180011736
0x1800116f3  lea     rdx, aCheckclientacc_1; "CheckClientAccess: AccessCheck failed w"...
0x1800116fa  mov     word ptr [rsp+8B8h+var_818], bx
0x180011702  mov     r8d, eax
0x180011705  lea     rcx, [rsp+8B8h+var_818]
0x18001170d  call    FormatRRASErrorString
0x180011712  test    cs:byte_18002E903, 8
0x180011719  jz      short loc_180011736
0x18001171b  lea     r8, [rsp+8B8h+var_818]
0x180011723  lea     rdx, RasSSTPSvcTraceError
0x18001172a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011731  call    McTemplateU0z_EventWriteTransfer
0x180011736  call    cs:__imp_RpcRevertToSelf
0x18001173d  nop     dword ptr [rax+rax+00h]
0x180011742  test    eax, eax
0x180011744  jz      short loc_180011792
0x180011746  test    cs:byte_18002E903, 8
0x18001174d  jz      short loc_180011792
0x18001174f  mov     word ptr [rsp+8B8h+var_818], bx
0x180011757  mov     r8d, eax
0x18001175a  lea     rdx, aCheckclientacc; "CheckClientAccess: RpcRevertToSelf fail"...
0x180011761  lea     rcx, [rsp+8B8h+var_818]
0x180011769  call    FormatRRASErrorString
0x18001176e  test    cs:byte_18002E903, 8
0x180011775  jz      short loc_180011792
0x180011777  lea     r8, [rsp+8B8h+var_818]
0x18001177f  lea     rdx, RasSSTPSvcTraceError
0x180011786  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001178d  call    McTemplateU0z_EventWriteTransfer
0x180011792  test    rsi, rsi
0x180011795  jz      short loc_1800117A6
0x180011797  mov     rcx, rsi
0x18001179a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800117a1  nop     dword ptr [rax+rax+00h]
0x1800117a6  test    rdi, rdi
0x1800117a9  jz      short loc_1800117BA
0x1800117ab  mov     rcx, rdi
0x1800117ae  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800117b5  nop     dword ptr [rax+rax+00h]
0x1800117ba  mov     rcx, [rsp+8B8h+TokenHandle]; hObject
0x1800117bf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800117c3  jz      short loc_1800117D1
0x1800117c5  call    cs:__imp_CloseHandle
0x1800117cc  nop     dword ptr [rax+rax+00h]
0x1800117d1  mov     eax, [rsp+8B8h+var_868]
0x1800117d5  mov     rcx, [rsp+8B8h+var_10]
0x1800117dd  xor     rcx, rsp; StackCookie
0x1800117e0  call    __security_check_cookie
0x1800117e5  lea     r11, [rsp+8B8h+var_8]
0x1800117ed  mov     rbx, [r11+10h]
0x1800117f1  mov     rsi, [r11+18h]
0x1800117f5  mov     rsp, r11
0x1800117f8  pop     rdi
0x1800117f9  retn
```
