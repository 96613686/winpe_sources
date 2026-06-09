# SpoolerLogonServiceAccount(void * *)

- ea: `0x14003af60`
- end: `0x14003b276`
- name: `?SpoolerLogonServiceAccount@@YAJPEAPEAX@Z`
- size: `790`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003b27c`

## callees

- `0x1400160a0`
- `0x14003af60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003b24b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003b24b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003b11d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003b11d`
- `ntdll!RtlNtStatusToDosError` at `0x14003b0e5`
- `ntdll!RtlNtStatusToDosError` at `0x14003b0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003aff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b0f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b16b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003aff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b0f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b16b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b25e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b25e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b23d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b23d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003b0d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003b161`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003b0d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003b161`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x14003b08f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x14003b08f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14003b20f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14003b20f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14003b03f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14003b03f`
- `SspiCli!LogonUserExExW` at `0x14003afe6`
- `SspiCli!LogonUserExExW` at `0x14003afe6`

## string_xrefs

- `0x14003af94`: `RESTRICTED SERVICES`
- `0x14003afaa`: `PrintSpoolerService`
- `0x14003aff9`: `Failed to logon spooler service account %d`
- `0x14003b000`: `SpoolerLogonServiceAccount`
- `0x14003b059`: `SpoolerLogonServiceAccount`
- `0x14003b0a9`: `SpoolerLogonServiceAccount`
- `0x14003b109`: `SpoolerLogonServiceAccount`
- `0x14003b132`: `SpoolerLogonServiceAccount`
- `0x14003b1df`: `SpoolerLogonServiceAccount`
- `0x14003b052`: `Failed to convert IL SID %d`
- `0x14003b09f`: `Failed to set token integrity level %d`
- `0x14003b102`: `Failed to get buffer size for token information %d`
- `0x14003b12b`: `Failed to allocate memory for token privilege array`
- `0x14003b171`: `Failed to query token privileges %d`
- `0x14003b1d8`: `Service account is missing required privilege %ws`
- `0x14003b21f`: `Failed to set new token privileges %d`

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
                        byte_140099BF0,
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
0x14003af60  mov     r11, rsp
0x14003af63  mov     [r11+8], rbx
0x14003af67  push    rbp
0x14003af68  push    rsi
0x14003af69  push    rdi
0x14003af6a  mov     rbp, rsp
0x14003af6d  sub     rsp, 70h
0x14003af71  mov     qword ptr [r11-38h], 0
0x14003af79  lea     rax, [rbp+TokenHandle]
0x14003af7d  mov     qword ptr [r11-40h], 0
0x14003af85  lea     r8, byte_140099BF0
0x14003af8c  mov     qword ptr [r11-48h], 0
0x14003af94  lea     rdx, SourceString; "RESTRICTED SERVICES"
0x14003af9b  mov     qword ptr [r11-50h], 0
0x14003afa3  mov     rsi, rcx
0x14003afa6  mov     [r11-58h], rax
0x14003afaa  lea     rcx, aPrintspoolerse; "PrintSpoolerService"
0x14003afb1  xorps   xmm0, xmm0
0x14003afb4  mov     qword ptr [r11-60h], 0
0x14003afbc  mov     r9d, 5
0x14003afc2  mov     dword ptr [rsp+70h+ReturnLength], 4
0x14003afca  mov     [rbp+TokenHandle], 0
0x14003afd2  mov     [rbp+Sid], 0
0x14003afda  movdqu  [rbp+TokenInformation], xmm0
0x14003afdf  mov     [rbp+TokenInformationLength], 0
0x14003afe6  call    cs:__imp_LogonUserExExW
0x14003afec  test    eax, eax
0x14003afee  jnz     short loc_14003B034
0x14003aff0  call    cs:__imp_GetLastError
0x14003aff6  mov     r8d, eax
0x14003aff9  lea     rdx, aFailedToLogonS; "Failed to logon spooler service account"...
0x14003b000  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003b007  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b00c  call    cs:__imp_GetLastError
0x14003b012  test    eax, eax
0x14003b014  jg      short loc_14003B021
0x14003b016  call    cs:__imp_GetLastError
0x14003b01c  jmp     loc_14003B266
0x14003b021  call    cs:__imp_GetLastError
0x14003b027  movzx   eax, ax
0x14003b02a  or      eax, 0C0070000h
0x14003b02f  jmp     loc_14003B266
0x14003b034  lea     rdx, [rbp+Sid]; Sid
0x14003b038  lea     rcx, StringSid; "HI"
0x14003b03f  call    cs:__imp_ConvertStringSidToSidW
0x14003b045  test    eax, eax
0x14003b047  jnz     short loc_14003B06F
0x14003b049  call    cs:__imp_GetLastError
0x14003b04f  mov     r8d, eax
0x14003b052  lea     rdx, aFailedToConver; "Failed to convert IL SID %d"
0x14003b059  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003b060  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b065  mov     eax, 0C0070539h
0x14003b06a  jmp     loc_14003B266
0x14003b06f  mov     rax, [rbp+Sid]
0x14003b073  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14003b077  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003b07b  xor     edi, edi
0x14003b07d  mov     dword ptr [rbp+TokenInformation+8], 20h ; ' '
0x14003b084  mov     qword ptr [rbp+TokenInformation], rax
0x14003b088  lea     r9d, [rdi+10h]; TokenInformationLength
0x14003b08c  lea     edx, [rdi+19h]; TokenInformationClass
0x14003b08f  call    cs:__imp_SetTokenInformation
0x14003b095  test    eax, eax
0x14003b097  jnz     short loc_14003B0BF
0x14003b099  call    cs:__imp_GetLastError
0x14003b09f  lea     rdx, aFailedToSetTok; "Failed to set token integrity level %d"
0x14003b0a6  mov     r8d, eax
0x14003b0a9  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003b0b0  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b0b5  mov     ebx, 0C007013Bh
0x14003b0ba  jmp     loc_14003B234
0x14003b0bf  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003b0c3  lea     rax, [rbp+TokenInformationLength]
0x14003b0c7  xor     r9d, r9d; TokenInformationLength
0x14003b0ca  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14003b0cf  xor     r8d, r8d; TokenInformation
0x14003b0d2  lea     edx, [r9+3]; TokenInformationClass
0x14003b0d6  call    cs:__imp_GetTokenInformation
0x14003b0dc  test    eax, eax
0x14003b0de  jnz     short loc_14003B11A
0x14003b0e0  mov     ecx, 0C0000023h; Status
0x14003b0e5  call    cs:__imp_RtlNtStatusToDosError
0x14003b0eb  mov     ebx, eax
0x14003b0ed  call    cs:__imp_GetLastError
0x14003b0f3  cmp     eax, ebx
0x14003b0f5  jz      short loc_14003B11A
0x14003b0f7  xor     ebx, ebx
0x14003b0f9  call    cs:__imp_GetLastError
0x14003b0ff  mov     r8d, eax
0x14003b102  lea     rdx, aFailedToGetBuf; "Failed to get buffer size for token inf"...
0x14003b109  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003b110  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b115  jmp     loc_14003B234
0x14003b11a  mov     ecx, [rbp+TokenInformationLength]; Size
0x14003b11d  call    cs:__imp_malloc
0x14003b123  mov     rdi, rax
0x14003b126  test    rax, rax
0x14003b129  jnz     short loc_14003B148
0x14003b12b  lea     rdx, aFailedToAlloca_1; "Failed to allocate memory for token pri"...
0x14003b132  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003b139  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b13e  mov     ebx, 0C0000017h
0x14003b143  jmp     loc_14003B234
0x14003b148  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14003b14c  lea     rax, [rbp+TokenInformationLength]
0x14003b150  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003b154  mov     r8, rdi; TokenInformation
0x14003b157  mov     edx, 3; TokenInformationClass
0x14003b15c  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14003b161  call    cs:__imp_GetTokenInformation
0x14003b167  test    eax, eax
0x14003b169  jnz     short loc_14003B17D
0x14003b16b  call    cs:__imp_GetLastError
0x14003b171  lea     rdx, aFailedToQueryT; "Failed to query token privileges %d"
0x14003b178  jmp     loc_14003B0A6
0x14003b17d  xor     ecx, ecx
0x14003b17f  cmp     [rdi], ecx
0x14003b181  jbe     short loc_14003B199
0x14003b183  mov     eax, ecx
0x14003b185  inc     ecx
0x14003b187  inc     rax
0x14003b18a  lea     rax, [rax+rax*2]
0x14003b18e  mov     dword ptr [rdi+rax*4], 4
0x14003b195  cmp     ecx, [rdi]
0x14003b197  jb      short loc_14003B183
0x14003b199  xor     ecx, ecx
0x14003b19b  lea     r10, ?g_aRequiredPrivileges@@3PAUSE_PRIVILEGE_INFO@@A; SE_PRIVILEGE_INFO near * g_aRequiredPrivileges
0x14003b1a2  xor     edx, edx; DisableAllPrivileges
0x14003b1a4  cmp     ecx, 3
0x14003b1a7  jnb     short loc_14003B1F2
0x14003b1a9  mov     r8d, ecx
0x14003b1ac  add     r8, r8
0x14003b1af  cmp     edx, [rdi]
0x14003b1b1  jnb     short loc_14003B1D3
0x14003b1b3  mov     rax, [r10+r8*8]
0x14003b1b7  lea     r9, [rdx+rdx*2]
0x14003b1bb  cmp     [rdi+r9*4+4], rax
0x14003b1c0  jz      short loc_14003B1C6
0x14003b1c2  inc     edx
0x14003b1c4  jmp     short loc_14003B1AF
0x14003b1c6  mov     dword ptr [rdi+r9*4+0Ch], 2
0x14003b1cf  inc     ecx
0x14003b1d1  jmp     short loc_14003B1A2
0x14003b1d3  mov     r8, [r10+r8*8+8]
0x14003b1d8  lea     rdx, aServiceAccount; "Service account is missing required pri"...
0x14003b1df  lea     rcx, aSpoolerlogonse; "SpoolerLogonServiceAccount"
0x14003b1e6  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b1eb  mov     ebx, 0C0070522h
0x14003b1f0  jmp     short loc_14003B234
0x14003b1f2  mov     r9d, [rbp+TokenInformationLength]; BufferLength
0x14003b1f6  mov     r8, rdi; NewState
0x14003b1f9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003b1fd  mov     [rsp+70h+var_48], 0; ReturnLength
0x14003b206  mov     [rsp+70h+ReturnLength], 0; PreviousState
0x14003b20f  call    cs:__imp_AdjustTokenPrivileges
0x14003b215  test    eax, eax
0x14003b217  jnz     short loc_14003B22B
0x14003b219  call    cs:__imp_GetLastError
0x14003b21f  lea     rdx, aFailedToSetNew; "Failed to set new token privileges %d"
0x14003b226  jmp     loc_14003B0A6
0x14003b22b  mov     rax, [rbp+TokenHandle]
0x14003b22f  xor     ebx, ebx
0x14003b231  mov     [rsi], rax
0x14003b234  mov     rcx, [rbp+Sid]; hMem
0x14003b238  test    rcx, rcx
0x14003b23b  jz      short loc_14003B243
0x14003b23d  call    cs:__imp_LocalFree
0x14003b243  test    rdi, rdi
0x14003b246  jz      short loc_14003B251
0x14003b248  mov     rcx, rdi; Block
0x14003b24b  call    cs:__imp_free
0x14003b251  test    ebx, ebx
0x14003b253  jz      short loc_14003B264
0x14003b255  mov     rcx, [rbp+TokenHandle]; hObject
0x14003b259  test    rcx, rcx
0x14003b25c  jz      short loc_14003B264
0x14003b25e  call    cs:__imp_CloseHandle
0x14003b264  mov     eax, ebx
0x14003b266  mov     rbx, [rsp+70h+arg_0]
0x14003b26e  add     rsp, 70h
0x14003b272  pop     rdi
0x14003b273  pop     rsi
0x14003b274  pop     rbp
0x14003b275  retn
```
