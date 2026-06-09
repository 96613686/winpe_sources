# SpoolerLogonServiceAccount(void * *)

- ea: `0x14003e5e4`
- end: `0x14003e979`
- name: `?SpoolerLogonServiceAccount@@YAJPEAPEAX@Z`
- size: `917`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003e980`

## callees

- `0x14001748c`
- `0x14003e5e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003e941`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003e941`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003e7ef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003e7ef`
- `ntdll!RtlNtStatusToDosError` at `0x14003e7a5`
- `ntdll!RtlNtStatusToDosError` at `0x14003e7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e69c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e6bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e6f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e7c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e69c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e6bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e6f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e7c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e903`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e95a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e95a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003e92d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003e92d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003e790`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003e839`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003e790`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003e839`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x14003e73d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x14003e73d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14003e8f3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14003e8f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14003e6e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14003e6e1`
- `SspiCli!LogonUserExExW` at `0x14003e66a`
- `SspiCli!LogonUserExExW` at `0x14003e66a`

## string_xrefs

- `0x14003e618`: `RESTRICTED SERVICES`
- `0x14003e62e`: `PrintSpoolerService`
- `0x14003e689`: `Failed to logon spooler service account %d`
- `0x14003e690`: `SpoolerLogonServiceAccount`
- `0x14003e707`: `SpoolerLogonServiceAccount`
- `0x14003e763`: `SpoolerLogonServiceAccount`
- `0x14003e7db`: `SpoolerLogonServiceAccount`
- `0x14003e80a`: `SpoolerLogonServiceAccount`
- `0x14003e8c3`: `SpoolerLogonServiceAccount`
- `0x14003e700`: `Failed to convert IL SID %d`
- `0x14003e759`: `Failed to set token integrity level %d`
- `0x14003e7d4`: `Failed to get buffer size for token information %d`
- `0x14003e803`: `Failed to allocate memory for token privilege array`
- `0x14003e855`: `Failed to query token privileges %d`
- `0x14003e8bc`: `Service account is missing required privilege %ws`
- `0x14003e90f`: `Failed to set new token privileges %d`

## pseudocode

```c
DWORD __fastcall SpoolerLogonServiceAccount(void **a1)
{
  DWORD LastError; // eax
  DWORD v4; // eax
  struct _TOKEN_PRIVILEGES *v5; // rdi
  DWORD v6; // eax
  int v7; // ebx
  ULONG v8; // ebx
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD i; // ecx
  __int64 v12; // rax
  unsigned int v13; // ecx
  __int64 v14; // rdx
  DWORD v15; // eax
  __int128 TokenInformation; // [rsp+60h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+98h] [rbp+28h] BYREF
  HANDLE TokenHandle; // [rsp+A0h] [rbp+30h] BYREF
  PSID Sid; // [rsp+A8h] [rbp+38h] BYREF

  TokenHandle = 0;
  Sid = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  if ( !(unsigned int)LogonUserExExW(
                        L"PrintSpoolerService",
                        L"RESTRICTED SERVICES",
                        byte_1400A0BD0,
                        5,
                        4,
                        0,
                        &TokenHandle,
                        0,
                        0,
                        0,
                        0) )
  {
    LastError = GetLastError();
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "SpoolerLogonServiceAccount",
      L"Failed to logon spooler service account %d",
      LastError);
    if ( (int)GetLastError() > 0 )
      return (unsigned __int16)GetLastError() | 0xC0070000;
    else
      return GetLastError();
  }
  if ( !ConvertStringSidToSidW(L"HI", &Sid) )
  {
    v4 = GetLastError();
    SpoolerServiceTelemetry::WriteDbgTraceError("SpoolerLogonServiceAccount", L"Failed to convert IL SID %d", v4);
    return -1073281735;
  }
  v5 = 0;
  DWORD2(TokenInformation) = 32;
  *(_QWORD *)&TokenInformation = Sid;
  if ( SetTokenInformation(TokenHandle, TokenIntegrityLevel, &TokenInformation, 0x10u) )
  {
    if ( !GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) )
    {
      v8 = RtlNtStatusToDosError(-1073741789);
      if ( GetLastError() != v8 )
      {
        v7 = 0;
        v9 = GetLastError();
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "SpoolerLogonServiceAccount",
          L"Failed to get buffer size for token information %d",
          v9);
        goto LABEL_29;
      }
    }
    v5 = (struct _TOKEN_PRIVILEGES *)malloc(TokenInformationLength);
    if ( !v5 )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SpoolerLogonServiceAccount",
        L"Failed to allocate memory for token privilege array");
      v7 = -1073741801;
      goto LABEL_29;
    }
    if ( GetTokenInformation(TokenHandle, TokenPrivileges, v5, TokenInformationLength, &TokenInformationLength) )
    {
      for ( i = 0; i < v5->PrivilegeCount; v5->Privileges[v12].Attributes = 4 )
        v12 = i++;
      v13 = 0;
LABEL_20:
      v14 = 0;
      if ( v13 < 3 )
      {
        while ( (unsigned int)v14 < v5->PrivilegeCount )
        {
          if ( (struct SE_PRIVILEGE_INFO near *)v5->Privileges[v14].Luid == *(&g_aRequiredPrivileges + 2 * v13) )
          {
            v5->Privileges[v14].Attributes = 2;
            ++v13;
            goto LABEL_20;
          }
          v14 = (unsigned int)(v14 + 1);
        }
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "SpoolerLogonServiceAccount",
          L"Service account is missing required privilege %ws",
          *(&g_aRequiredPrivileges + 2 * v13 + 1));
        v7 = -1073281758;
        goto LABEL_29;
      }
      if ( AdjustTokenPrivileges(TokenHandle, 0, v5, TokenInformationLength, 0, 0) )
      {
        v7 = 0;
        *a1 = TokenHandle;
        goto LABEL_29;
      }
      v15 = GetLastError();
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SpoolerLogonServiceAccount",
        L"Failed to set new token privileges %d",
        v15);
    }
    else
    {
      v10 = GetLastError();
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SpoolerLogonServiceAccount",
        L"Failed to query token privileges %d",
        v10);
    }
  }
  else
  {
    v6 = GetLastError();
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "SpoolerLogonServiceAccount",
      L"Failed to set token integrity level %d",
      v6);
  }
  v7 = -1073282757;
LABEL_29:
  if ( Sid )
    LocalFree(Sid);
  if ( v5 )
    free(v5);
  if ( v7 && TokenHandle )
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x14003e5e4  mov     r11, rsp
0x14003e5e7  mov     [r11+8], rbx
0x14003e5eb  push    rbp
0x14003e5ec  push    rsi
0x14003e5ed  push    rdi
0x14003e5ee  mov     rbp, rsp
0x14003e5f1  sub     rsp, 70h
0x14003e5f5  mov     qword ptr [r11-38h], 0
0x14003e5fd  lea     rax, [rbp+TokenHandle]
0x14003e601  mov     qword ptr [r11-40h], 0
0x14003e609  lea     r8, byte_1400A0BD0
0x14003e610  mov     qword ptr [r11-48h], 0
0x14003e618  lea     rdx, SourceString; "RESTRICTED SERVICES"
0x14003e61f  mov     qword ptr [r11-50h], 0
0x14003e627  mov     rsi, rcx
0x14003e62a  mov     [r11-58h], rax
0x14003e62e  lea     rcx, aPrintspoolerse; "PrintSpoolerService"
0x14003e635  xorps   xmm0, xmm0
0x14003e638  mov     qword ptr [r11-60h], 0
0x14003e640  mov     r9d, 5
0x14003e646  mov     dword ptr [rsp+70h+ReturnLength], 4
0x14003e64e  mov     [rbp+TokenHandle], 0
0x14003e656  mov     [rbp+Sid], 0
0x14003e65e  movdqu  [rbp+TokenInformation], xmm0
0x14003e663  mov     [rbp+TokenInformationLength], 0
0x14003e66a  call    cs:__imp_LogonUserExExW
0x14003e671  nop     dword ptr [rax+rax+00h]
0x14003e676  test    eax, eax
0x14003e678  jnz     short loc_14003E6D6
0x14003e67a  call    cs:__imp_GetLastError
0x14003e681  nop     dword ptr [rax+rax+00h]
0x14003e686  mov     r8d, eax
0x14003e689  lea     rdx, aFailedToLogonS; "Failed to logon spooler service account"...
0x14003e690  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003e697  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003e69c  call    cs:__imp_GetLastError
0x14003e6a3  nop     dword ptr [rax+rax+00h]
0x14003e6a8  test    eax, eax
0x14003e6aa  jg      short loc_14003E6BD
0x14003e6ac  call    cs:__imp_GetLastError
0x14003e6b3  nop     dword ptr [rax+rax+00h]
0x14003e6b8  jmp     loc_14003E968
0x14003e6bd  call    cs:__imp_GetLastError
0x14003e6c4  nop     dword ptr [rax+rax+00h]
0x14003e6c9  movzx   eax, ax
0x14003e6cc  or      eax, 0C0070000h
0x14003e6d1  jmp     loc_14003E968
0x14003e6d6  lea     rdx, [rbp+Sid]; Sid
0x14003e6da  lea     rcx, StringSid; "HI"
0x14003e6e1  call    cs:__imp_ConvertStringSidToSidW
0x14003e6e8  nop     dword ptr [rax+rax+00h]
0x14003e6ed  test    eax, eax
0x14003e6ef  jnz     short loc_14003E71D
0x14003e6f1  call    cs:__imp_GetLastError
0x14003e6f8  nop     dword ptr [rax+rax+00h]
0x14003e6fd  mov     r8d, eax
0x14003e700  lea     rdx, aFailedToConver; "Failed to convert IL SID %d"
0x14003e707  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003e70e  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003e713  mov     eax, 0C0070539h
0x14003e718  jmp     loc_14003E968
0x14003e71d  mov     rax, [rbp+Sid]
0x14003e721  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14003e725  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003e729  xor     edi, edi
0x14003e72b  mov     dword ptr [rbp+TokenInformation+8], 20h ; ' '
0x14003e732  mov     qword ptr [rbp+TokenInformation], rax
0x14003e736  lea     r9d, [rdi+10h]; TokenInformationLength
0x14003e73a  lea     edx, [rdi+19h]; TokenInformationClass
0x14003e73d  call    cs:__imp_SetTokenInformation
0x14003e744  nop     dword ptr [rax+rax+00h]
0x14003e749  test    eax, eax
0x14003e74b  jnz     short loc_14003E779
0x14003e74d  call    cs:__imp_GetLastError
0x14003e754  nop     dword ptr [rax+rax+00h]
0x14003e759  lea     rdx, aFailedToSetTok; "Failed to set token integrity level %d"
0x14003e760  mov     r8d, eax
0x14003e763  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003e76a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003e76f  mov     ebx, 0C007013Bh
0x14003e774  jmp     loc_14003E924
0x14003e779  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003e77d  lea     rax, [rbp+TokenInformationLength]
0x14003e781  xor     r9d, r9d; TokenInformationLength
0x14003e784  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14003e789  xor     r8d, r8d; TokenInformation
0x14003e78c  lea     edx, [r9+3]; TokenInformationClass
0x14003e790  call    cs:__imp_GetTokenInformation
0x14003e797  nop     dword ptr [rax+rax+00h]
0x14003e79c  test    eax, eax
0x14003e79e  jnz     short loc_14003E7EC
0x14003e7a0  mov     ecx, 0C0000023h; Status
0x14003e7a5  call    cs:__imp_RtlNtStatusToDosError
0x14003e7ac  nop     dword ptr [rax+rax+00h]
0x14003e7b1  mov     ebx, eax
0x14003e7b3  call    cs:__imp_GetLastError
0x14003e7ba  nop     dword ptr [rax+rax+00h]
0x14003e7bf  cmp     eax, ebx
0x14003e7c1  jz      short loc_14003E7EC
0x14003e7c3  xor     ebx, ebx
0x14003e7c5  call    cs:__imp_GetLastError
0x14003e7cc  nop     dword ptr [rax+rax+00h]
0x14003e7d1  mov     r8d, eax
0x14003e7d4  lea     rdx, aFailedToGetBuf; "Failed to get buffer size for token inf"...
0x14003e7db  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003e7e2  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003e7e7  jmp     loc_14003E924
0x14003e7ec  mov     ecx, [rbp+TokenInformationLength]; Size
0x14003e7ef  call    cs:__imp_malloc
0x14003e7f6  nop     dword ptr [rax+rax+00h]
0x14003e7fb  mov     rdi, rax
0x14003e7fe  test    rax, rax
0x14003e801  jnz     short loc_14003E820
0x14003e803  lea     rdx, aFailedToAlloca_1; "Failed to allocate memory for token pri"...
0x14003e80a  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003e811  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003e816  mov     ebx, 0C0000017h
0x14003e81b  jmp     loc_14003E924
0x14003e820  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14003e824  lea     rax, [rbp+TokenInformationLength]
0x14003e828  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003e82c  mov     r8, rdi; TokenInformation
0x14003e82f  mov     edx, 3; TokenInformationClass
0x14003e834  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14003e839  call    cs:__imp_GetTokenInformation
0x14003e840  nop     dword ptr [rax+rax+00h]
0x14003e845  test    eax, eax
0x14003e847  jnz     short loc_14003E861
0x14003e849  call    cs:__imp_GetLastError
0x14003e850  nop     dword ptr [rax+rax+00h]
0x14003e855  lea     rdx, aFailedToQueryT; "Failed to query token privileges %d"
0x14003e85c  jmp     loc_14003E760
0x14003e861  xor     ecx, ecx
0x14003e863  cmp     [rdi], ecx
0x14003e865  jbe     short loc_14003E87D
0x14003e867  mov     eax, ecx
0x14003e869  inc     ecx
0x14003e86b  inc     rax
0x14003e86e  lea     rax, [rax+rax*2]
0x14003e872  mov     dword ptr [rdi+rax*4], 4
0x14003e879  cmp     ecx, [rdi]
0x14003e87b  jb      short loc_14003E867
0x14003e87d  xor     ecx, ecx
0x14003e87f  lea     r10, ?g_aRequiredPrivileges@@3PAUSE_PRIVILEGE_INFO@@A; SE_PRIVILEGE_INFO near * g_aRequiredPrivileges
0x14003e886  xor     edx, edx; DisableAllPrivileges
0x14003e888  cmp     ecx, 3
0x14003e88b  jnb     short loc_14003E8D6
0x14003e88d  mov     r8d, ecx
0x14003e890  add     r8, r8
0x14003e893  cmp     edx, [rdi]
0x14003e895  jnb     short loc_14003E8B7
0x14003e897  mov     rax, [r10+r8*8]
0x14003e89b  lea     r9, [rdx+rdx*2]
0x14003e89f  cmp     [rdi+r9*4+4], rax
0x14003e8a4  jz      short loc_14003E8AA
0x14003e8a6  inc     edx
0x14003e8a8  jmp     short loc_14003E893
0x14003e8aa  mov     dword ptr [rdi+r9*4+0Ch], 2
0x14003e8b3  inc     ecx
0x14003e8b5  jmp     short loc_14003E886
0x14003e8b7  mov     r8, [r10+r8*8+8]
0x14003e8bc  lea     rdx, aServiceAccount; "Service account is missing required pri"...
0x14003e8c3  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003e8ca  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003e8cf  mov     ebx, 0C0070522h
0x14003e8d4  jmp     short loc_14003E924
0x14003e8d6  mov     r9d, [rbp+TokenInformationLength]; BufferLength
0x14003e8da  mov     r8, rdi; NewState
0x14003e8dd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003e8e1  mov     [rsp+70h+var_48], 0; ReturnLength
0x14003e8ea  mov     [rsp+70h+ReturnLength], 0; PreviousState
0x14003e8f3  call    cs:__imp_AdjustTokenPrivileges
0x14003e8fa  nop     dword ptr [rax+rax+00h]
0x14003e8ff  test    eax, eax
0x14003e901  jnz     short loc_14003E91B
0x14003e903  call    cs:__imp_GetLastError
0x14003e90a  nop     dword ptr [rax+rax+00h]
0x14003e90f  lea     rdx, aFailedToSetNew; "Failed to set new token privileges %d"
0x14003e916  jmp     loc_14003E760
0x14003e91b  mov     rax, [rbp+TokenHandle]
0x14003e91f  xor     ebx, ebx
0x14003e921  mov     [rsi], rax
0x14003e924  mov     rcx, [rbp+Sid]; hMem
0x14003e928  test    rcx, rcx
0x14003e92b  jz      short loc_14003E939
0x14003e92d  call    cs:__imp_LocalFree
0x14003e934  nop     dword ptr [rax+rax+00h]
0x14003e939  test    rdi, rdi
0x14003e93c  jz      short loc_14003E94D
0x14003e93e  mov     rcx, rdi; Block
0x14003e941  call    cs:__imp_free
0x14003e948  nop     dword ptr [rax+rax+00h]
0x14003e94d  test    ebx, ebx
0x14003e94f  jz      short loc_14003E966
0x14003e951  mov     rcx, [rbp+TokenHandle]; hObject
0x14003e955  test    rcx, rcx
0x14003e958  jz      short loc_14003E966
0x14003e95a  call    cs:__imp_CloseHandle
0x14003e961  nop     dword ptr [rax+rax+00h]
0x14003e966  mov     eax, ebx
0x14003e968  mov     rbx, [rsp+70h+arg_0]
0x14003e970  add     rsp, 70h
0x14003e974  pop     rdi
0x14003e975  pop     rsi
0x14003e976  pop     rbp
0x14003e977  retn
```
