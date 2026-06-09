# WpnGetCurrentProcessIntegrityLevel(ulong *)

- ea: `0x1800f59ec`
- end: `0x1800f5c7b`
- name: `?WpnGetCurrentProcessIntegrityLevel@@YAJPEAK@Z`
- size: `655`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180099b48`

## callees

- `0x18002ee38`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800f59ec`
- `0x1800f60e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5b35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5b35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f5b27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f5c40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f5b27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f5c40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f5c4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f5c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5abe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5abe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5c63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5c63`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800f5c36`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800f5c36`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f5aa7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f5bac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f5aa7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f5bac`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800f5c26`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800f5c26`

## string_xrefs

- `0x1800f5a2d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x1800f5ae4`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x1800f5b48`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x1800f5bd0`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
__int64 __fastcall WpnGetCurrentProcessIntegrityLevel(unsigned int *a1)
{
  int CurrentUserToken; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  HANDLE v7; // rcx
  signed int LastError; // eax
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v11; // rdi
  signed int v12; // eax
  PUCHAR SidSubAuthorityCount; // rax
  HANDLE v14; // rax
  int ReturnLength; // [rsp+20h] [rbp-18h]
  int ReturnLengtha; // [rsp+20h] [rbp-18h]
  int ReturnLengthb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  CurrentUserToken = GetCurrentUserToken(&TokenHandle);
  v3 = CurrentUserToken;
  if ( CurrentUserToken >= 0 )
  {
    v7 = TokenHandle;
    if ( !TokenHandle )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v7 = TokenHandle;
    }
    if ( GetTokenInformation(v7, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    else
      GetLastError();
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 == -2147024774 )
    {
      v9 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v11 = (PSID *)HeapAlloc(ProcessHeap, 0, v9);
      if ( v11 )
      {
        if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v11, TokenInformationLength, &TokenInformationLength) )
        {
          v3 = 0;
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v11);
          *a1 = *GetSidSubAuthority(*v11, (unsigned __int8)(*SidSubAuthorityCount - 1));
        }
        else
        {
          v12 = GetLastError();
          v3 = v12;
          if ( v12 > 0 )
            v3 = (unsigned __int16)v12 | 0x80070000;
          if ( (v3 & 0x80000000) == 0 )
            v3 = -2147467259;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA1,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
            (const char *)v3,
            ReturnLengthb);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids, v3);
        }
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v11);
      }
      else
      {
        v3 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x98,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
          (const char *)0x8007000ELL,
          ReturnLengtha);
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v5 = 13;
          v6 = 2147942414LL;
          goto LABEL_8;
        }
      }
    }
    else
    {
      if ( (v3 & 0x80000000) != 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x90,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
          (const char *)v3,
          ReturnLengtha);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v5 = 12;
        goto LABEL_7;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)CurrentUserToken,
      ReturnLength);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v5 = 10;
LABEL_7:
      v6 = v3;
LABEL_8:
      WPP_SF_d(v4[2], v5, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids, v6);
    }
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x1800f59ec  mov     rax, rsp
0x1800f59ef  mov     [rax+18h], rbx
0x1800f59f3  mov     [rax+20h], rsi
0x1800f59f7  push    rdi
0x1800f59f8  sub     rsp, 30h
0x1800f59fc  mov     qword ptr [rax+10h], 0
0x1800f5a04  mov     rsi, rcx
0x1800f5a07  mov     dword ptr [rax+8], 0
0x1800f5a0e  test    rcx, rcx
0x1800f5a11  jnz     short loc_1800F5A18
0x1800f5a13  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "nullptr != IntegrityLevel")
0x1800f5a18  lea     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800f5a1d  call    ?GetCurrentUserToken@@YAJPEAPEAX@Z; GetCurrentUserToken(void * *)
0x1800f5a22  mov     ebx, eax
0x1800f5a24  test    eax, eax
0x1800f5a26  jns     short loc_1800F5A7F
0x1800f5a28  mov     rcx, [rsp+38h]; this
0x1800f5a2d  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f5a34  mov     r9d, eax; char *
0x1800f5a37  mov     edx, 7Dh ; '}'; void *
0x1800f5a3c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f5a41  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f5a48  lea     rax, WPP_GLOBAL_Control
0x1800f5a4f  cmp     rcx, rax
0x1800f5a52  jz      loc_1800F5C54
0x1800f5a58  test    byte ptr [rcx+1Ch], 80h
0x1800f5a5c  jz      loc_1800F5C54
0x1800f5a62  mov     edx, 0Ah
0x1800f5a67  mov     r9d, ebx
0x1800f5a6a  mov     rcx, [rcx+10h]
0x1800f5a6e  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x1800f5a75  call    WPP_SF_d
0x1800f5a7a  jmp     loc_1800F5C54
0x1800f5a7f  mov     rcx, [rsp+38h+TokenHandle]
0x1800f5a84  test    rcx, rcx
0x1800f5a87  jnz     short loc_1800F5A93
0x1800f5a89  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "UserToken != NULL")
0x1800f5a8e  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800f5a93  xor     r9d, r9d; TokenInformationLength
0x1800f5a96  lea     rax, [rsp+38h+TokenInformationLength]
0x1800f5a9b  xor     r8d, r8d; TokenInformation
0x1800f5a9e  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800f5aa3  lea     edx, [r9+19h]; TokenInformationClass
0x1800f5aa7  call    cs:__imp_GetTokenInformation
0x1800f5aad  test    eax, eax
0x1800f5aaf  jz      short loc_1800F5AB8
0x1800f5ab1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "TokenILRetrieved == FALSE")
0x1800f5ab6  jmp     short loc_1800F5ABE
0x1800f5ab8  call    cs:__imp_GetLastError
0x1800f5abe  call    cs:__imp_GetLastError
0x1800f5ac4  mov     ebx, eax
0x1800f5ac6  test    eax, eax
0x1800f5ac8  jle     short loc_1800F5AD3
0x1800f5aca  movzx   ebx, ax
0x1800f5acd  or      ebx, 80070000h
0x1800f5ad3  cmp     ebx, 8007007Ah
0x1800f5ad9  jz      short loc_1800F5B23
0x1800f5adb  test    ebx, ebx
0x1800f5add  jns     short loc_1800F5AF8
0x1800f5adf  mov     rcx, [rsp+38h]; this
0x1800f5ae4  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f5aeb  mov     r9d, ebx; char *
0x1800f5aee  mov     edx, 90h; void *
0x1800f5af3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f5af8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f5aff  lea     rax, WPP_GLOBAL_Control
0x1800f5b06  cmp     rcx, rax
0x1800f5b09  jz      loc_1800F5C54
0x1800f5b0f  test    byte ptr [rcx+1Ch], 80h
0x1800f5b13  jz      loc_1800F5C54
0x1800f5b19  mov     edx, 0Ch
0x1800f5b1e  jmp     loc_1800F5A67
0x1800f5b23  mov     ebx, [rsp+38h+TokenInformationLength]
0x1800f5b27  call    cs:__imp_GetProcessHeap
0x1800f5b2d  mov     r8d, ebx; dwBytes
0x1800f5b30  xor     edx, edx; dwFlags
0x1800f5b32  mov     rcx, rax; hHeap
0x1800f5b35  call    cs:__imp_HeapAlloc
0x1800f5b3b  mov     rdi, rax
0x1800f5b3e  test    rax, rax
0x1800f5b41  jnz     short loc_1800F5B90
0x1800f5b43  mov     rcx, [rsp+38h]; this
0x1800f5b48  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f5b4f  mov     ebx, 8007000Eh
0x1800f5b54  mov     edx, 98h; void *
0x1800f5b59  mov     r9d, ebx; char *
0x1800f5b5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f5b61  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f5b68  lea     rax, WPP_GLOBAL_Control
0x1800f5b6f  cmp     rcx, rax
0x1800f5b72  jz      loc_1800F5C54
0x1800f5b78  test    byte ptr [rcx+1Ch], 80h
0x1800f5b7c  jz      loc_1800F5C54
0x1800f5b82  lea     edx, [rdi+0Dh]
0x1800f5b85  mov     r9d, 8007000Eh
0x1800f5b8b  jmp     loc_1800F5A6A
0x1800f5b90  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800f5b95  lea     rax, [rsp+38h+TokenInformationLength]
0x1800f5b9a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800f5b9f  mov     r8, rdi; TokenInformation
0x1800f5ba2  mov     edx, 19h; TokenInformationClass
0x1800f5ba7  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800f5bac  call    cs:__imp_GetTokenInformation
0x1800f5bb2  test    eax, eax
0x1800f5bb4  jnz     short loc_1800F5C21
0x1800f5bb6  call    cs:__imp_GetLastError
0x1800f5bbc  mov     ebx, eax
0x1800f5bbe  test    eax, eax
0x1800f5bc0  jle     short loc_1800F5BCB
0x1800f5bc2  movzx   ebx, ax
0x1800f5bc5  or      ebx, 80070000h
0x1800f5bcb  mov     rcx, [rsp+38h]; this
0x1800f5bd0  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f5bd7  test    ebx, ebx
0x1800f5bd9  mov     eax, 80004005h
0x1800f5bde  mov     edx, 0A1h; void *
0x1800f5be3  cmovns  ebx, eax
0x1800f5be6  mov     r9d, ebx; char *
0x1800f5be9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f5bee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f5bf5  lea     rax, WPP_GLOBAL_Control
0x1800f5bfc  cmp     rcx, rax
0x1800f5bff  jz      short loc_1800F5C40
0x1800f5c01  test    byte ptr [rcx+1Ch], 80h
0x1800f5c05  jz      short loc_1800F5C40
0x1800f5c07  mov     rcx, [rcx+10h]
0x1800f5c0b  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x1800f5c12  mov     edx, 0Eh
0x1800f5c17  mov     r9d, ebx
0x1800f5c1a  call    WPP_SF_d
0x1800f5c1f  jmp     short loc_1800F5C40
0x1800f5c21  mov     rcx, [rdi]; pSid
0x1800f5c24  xor     ebx, ebx
0x1800f5c26  call    cs:__imp_GetSidSubAuthorityCount
0x1800f5c2c  mov     cl, [rax]
0x1800f5c2e  dec     cl
0x1800f5c30  movzx   edx, cl; nSubAuthority
0x1800f5c33  mov     rcx, [rdi]; pSid
0x1800f5c36  call    cs:__imp_GetSidSubAuthority
0x1800f5c3c  mov     ecx, [rax]
0x1800f5c3e  mov     [rsi], ecx
0x1800f5c40  call    cs:__imp_GetProcessHeap
0x1800f5c46  mov     r8, rdi; lpMem
0x1800f5c49  xor     edx, edx; dwFlags
0x1800f5c4b  mov     rcx, rax; hHeap
0x1800f5c4e  call    cs:__imp_HeapFree
0x1800f5c54  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800f5c59  lea     rax, [rcx-1]
0x1800f5c5d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f5c61  ja      short loc_1800F5C69
0x1800f5c63  call    cs:__imp_CloseHandle
0x1800f5c69  mov     rsi, [rsp+38h+arg_18]
0x1800f5c6e  mov     eax, ebx
0x1800f5c70  mov     rbx, [rsp+38h+arg_10]
0x1800f5c75  add     rsp, 30h
0x1800f5c79  pop     rdi
0x1800f5c7a  retn
```
