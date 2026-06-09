# Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)

- ea: `0x180068874`
- end: `0x180068b8a`
- name: `?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `790`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18003cf2c`
- `0x180094a90`
- `0x1800952b0`

## callees

- `0x180010f24`
- `0x180065be0`
- `0x180068874`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ab4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068975`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068ac7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068975`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068ac7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006896d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068abf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006896d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068abf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068b2a`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800688b6`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800689a1`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180068a0d`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800688b6`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1800689a1`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180068a0d`
- `WTSAPI32!WTSEnumerateSessionsExW` at `0x1800688f1`
- `WTSAPI32!WTSEnumerateSessionsExW` at `0x1800688f1`
- `WTSAPI32!WTSQueryUserToken` at `0x180068989`
- `WTSAPI32!WTSQueryUserToken` at `0x180068adb`
- `WTSAPI32!WTSQueryUserToken` at `0x180068989`
- `WTSAPI32!WTSQueryUserToken` at `0x180068adb`
- `WTSAPI32!WTSFreeMemory` at `0x1800689eb`
- `WTSAPI32!WTSFreeMemory` at `0x180068a5f`
- `WTSAPI32!WTSFreeMemory` at `0x1800689eb`
- `WTSAPI32!WTSFreeMemory` at `0x180068a5f`
- `WTSAPI32!WTSFreeMemoryExW` at `0x180068b15`
- `WTSAPI32!WTSFreeMemoryExW` at `0x180068b15`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1800689c8`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180068a36`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1800689c8`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180068a36`

## string_xrefs

- `0x180068b60`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\CallerToken.cpp`
- `0x180068b72`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\CallerToken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
WCHAR *__fastcall Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(WCHAR *a1)
{
  const char *v2; // r9
  int v3; // r15d
  int v4; // r12d
  DWORD v5; // r8d
  PWTS_SESSION_INFO_1W v6; // rdi
  struct _WTS_SESSION_INFO_1W *v7; // r13
  HANDLE v8; // r14
  DWORD LastError; // ebx
  DWORD SessionId; // ebx
  char v11; // bl
  DWORD v12; // ebx
  char v13; // bl
  ULONG v14; // edi
  HANDLE v15; // r14
  DWORD v16; // ebx
  const char *v17; // r9
  PWTS_SESSION_INFO_1W v18; // rdx
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+58h] [rbp-9h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-1h] BYREF
  LPWSTR ppBuffer; // [rsp+68h] [rbp+7h] BYREF
  DWORD NumberOfEntries; // [rsp+70h] [rbp+Fh] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+17h] BYREF
  DWORD pBytesReturned; // [rsp+80h] [rbp+1Fh] BYREF
  DWORD v26; // [rsp+84h] [rbp+23h] BYREF
  DWORD pLevel; // [rsp+88h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v21 = a1;
  if ( !IsApiSetImplemented("ext-ms-win-session-wtsapi32-l1-1-0") )
  {
    *(_QWORD *)a1 = 0;
    return a1;
  }
  hObject = 0;
  NumberOfEntries = 0;
  pLevel = 1;
  ppSessionInfo = 0;
  if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x43,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\CallerToken.cpp",
      v2);
  v3 = -1;
  v4 = -1;
  v5 = NumberOfEntries;
  v6 = ppSessionInfo;
  if ( !ppSessionInfo && NumberOfEntries )
    gsl::details::terminate((gsl::details *)0xFFFFFFFFLL);
  v7 = &ppSessionInfo[NumberOfEntries];
  if ( ppSessionInfo == v7 )
  {
LABEL_46:
    *(_QWORD *)a1 = 0;
    v18 = v6;
    goto LABEL_47;
  }
  while ( 1 )
  {
    if ( !v6->SessionId )
      goto LABEL_33;
    v8 = hObject;
    if ( hObject && hObject != (HANDLE)-1LL )
    {
      LastError = GetLastError();
      CloseHandle(v8);
      SetLastError(LastError);
    }
    hObject = 0;
    if ( !WTSQueryUserToken(v6->SessionId, &hObject) )
      goto LABEL_33;
    SessionId = v6->SessionId;
    if ( !IsApiSetImplemented("ext-ms-win-session-wtsapi32-l1-1-0") )
      break;
    ppBuffer = 0;
    pBytesReturned = 0;
    if ( !WTSQuerySessionInformationW(0, SessionId, WTSIsRemoteSession, &ppBuffer, &pBytesReturned) )
      break;
    if ( !pBytesReturned || (v11 = 1, *(_BYTE *)ppBuffer != 1) )
      v11 = 0;
    if ( ppBuffer )
      WTSFreeMemory(ppBuffer);
    if ( !v11 || v3 != -1 )
      break;
    v3 = v6->SessionId;
LABEL_33:
    if ( ++v6 == v7 )
      goto LABEL_36;
  }
  v12 = v6->SessionId;
  if ( !IsApiSetImplemented("ext-ms-win-session-wtsapi32-l1-1-0") )
    goto LABEL_31;
  v21 = 0;
  v26 = 0;
  if ( !WTSQuerySessionInformationW(0, v12, WTSSessionInfoEx, &v21, &v26) )
    goto LABEL_31;
  if ( !v26 || *(_DWORD *)v21 != 1 || (v13 = 1, *((_DWORD *)v21 + 4) != 1) )
    v13 = 0;
  if ( v21 )
    WTSFreeMemory(v21);
  if ( !v13 )
  {
LABEL_31:
    if ( v4 == -1 )
      v4 = v6->SessionId;
    goto LABEL_33;
  }
  v14 = v6->SessionId;
  if ( v14 != -1 )
    goto LABEL_40;
LABEL_36:
  if ( v4 == -1 )
  {
    if ( v3 == -1 )
    {
      v5 = NumberOfEntries;
      v6 = ppSessionInfo;
      goto LABEL_46;
    }
    v14 = v3;
  }
  else
  {
    v14 = v4;
  }
LABEL_40:
  v15 = hObject;
  if ( hObject && hObject != (HANDLE)-1LL )
  {
    v16 = GetLastError();
    CloseHandle(v15);
    SetLastError(v16);
  }
  hObject = 0;
  if ( !WTSQueryUserToken(v14, &hObject) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x81,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\CallerToken.cpp",
      v17);
  *(_QWORD *)a1 = hObject;
  hObject = 0;
  v5 = NumberOfEntries;
  v18 = ppSessionInfo;
LABEL_47:
  WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, v18, v5);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a1;
}

```

## disassembly

```asm
0x180068874  mov     rax, rsp
0x180068877  mov     [rax+10h], rbx
0x18006887b  mov     [rax+18h], rsi
0x18006887f  mov     [rax+20h], rdi
0x180068883  push    rbp
0x180068884  push    r12
0x180068886  push    r13
0x180068888  push    r14
0x18006888a  push    r15
0x18006888c  lea     rbp, [rax-5Fh]
0x180068890  sub     rsp, 90h
0x180068897  mov     rax, cs:__security_cookie
0x18006889e  xor     rax, rsp
0x1800688a1  mov     [rbp+57h+var_28], rax
0x1800688a5  mov     rsi, rcx
0x1800688a8  mov     [rbp+57h+var_58], rcx
0x1800688ac  xor     r14d, r14d
0x1800688af  lea     rcx, Contract; "ext-ms-win-session-wtsapi32-l1-1-0"
0x1800688b6  call    cs:__imp_IsApiSetImplemented
0x1800688bc  test    eax, eax
0x1800688be  jnz     short loc_1800688C8
0x1800688c0  mov     [rsi], r14
0x1800688c3  jmp     loc_180068B30
0x1800688c8  mov     [rbp+57h+hObject], r14
0x1800688cc  mov     [rbp+57h+NumberOfEntries], r14d
0x1800688d0  mov     [rbp+57h+pLevel], 1
0x1800688d7  mov     [rbp+57h+ppSessionInfo], r14
0x1800688db  lea     rax, [rbp+57h+NumberOfEntries]
0x1800688df  mov     [rsp+0B0h+pCount], rax; pCount
0x1800688e4  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x1800688e8  xor     r8d, r8d; Filter
0x1800688eb  lea     rdx, [rbp+57h+pLevel]; pLevel
0x1800688ef  xor     ecx, ecx; hServer
0x1800688f1  call    cs:__imp_WTSEnumerateSessionsExW
0x1800688f7  mov     rcx, [rbp+5Fh]; this
0x1800688fb  test    eax, eax
0x1800688fd  jz      loc_180068B72
0x180068903  lea     rax, [rbp+57h+ppSessionInfo]
0x180068907  mov     [rbp+57h+var_78], rax
0x18006890b  lea     rax, [rbp+57h+NumberOfEntries]
0x18006890f  mov     [rbp+57h+var_70], rax
0x180068913  mov     [rbp+57h+var_68], 1
0x180068917  or      ecx, 0FFFFFFFFh; this
0x18006891a  mov     r15d, ecx
0x18006891d  mov     r12d, ecx
0x180068920  mov     r8d, [rbp+57h+NumberOfEntries]
0x180068924  mov     eax, r8d
0x180068927  mov     rdi, [rbp+57h+ppSessionInfo]
0x18006892b  test    rdi, rdi
0x18006892e  jnz     short loc_180068939
0x180068930  test    r8d, r8d
0x180068933  jnz     loc_180068B84
0x180068939  imul    r13, rax, 38h ; '8'
0x18006893d  add     r13, rdi
0x180068940  cmp     rdi, r13
0x180068943  jz      loc_180068B0A
0x180068949  cmp     [rdi+8], r14d
0x18006894d  jz      loc_180068A7A
0x180068953  mov     r14, [rbp+57h+hObject]
0x180068957  test    r14, r14
0x18006895a  jz      short loc_18006897B
0x18006895c  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180068960  jz      short loc_18006897B
0x180068962  call    cs:__imp_GetLastError
0x180068968  mov     ebx, eax
0x18006896a  mov     rcx, r14; hObject
0x18006896d  call    cs:__imp_CloseHandle
0x180068973  mov     ecx, ebx; dwErrCode
0x180068975  call    cs:__imp_SetLastError
0x18006897b  xor     r14d, r14d
0x18006897e  mov     [rbp+57h+hObject], r14
0x180068982  lea     rdx, [rbp+57h+hObject]; phToken
0x180068986  mov     ecx, [rdi+8]; SessionId
0x180068989  call    cs:__imp_WTSQueryUserToken
0x18006898f  test    eax, eax
0x180068991  jz      loc_180068A77
0x180068997  mov     ebx, [rdi+8]
0x18006899a  lea     rcx, Contract; "ext-ms-win-session-wtsapi32-l1-1-0"
0x1800689a1  call    cs:__imp_IsApiSetImplemented
0x1800689a7  test    eax, eax
0x1800689a9  jz      short loc_180068A03
0x1800689ab  mov     [rbp+57h+ppBuffer], r14
0x1800689af  mov     [rbp+57h+pBytesReturned], r14d
0x1800689b3  lea     rax, [rbp+57h+pBytesReturned]
0x1800689b7  mov     [rsp+0B0h+pCount], rax; pBytesReturned
0x1800689bc  lea     r9, [rbp+57h+ppBuffer]; ppBuffer
0x1800689c0  lea     r8d, [r14+1Dh]; WTSInfoClass
0x1800689c4  mov     edx, ebx; SessionId
0x1800689c6  xor     ecx, ecx; hServer
0x1800689c8  call    cs:__imp_WTSQuerySessionInformationW
0x1800689ce  test    eax, eax
0x1800689d0  jz      short loc_180068A03
0x1800689d2  mov     rcx, [rbp+57h+ppBuffer]; pMemory
0x1800689d6  cmp     [rbp+57h+pBytesReturned], r14d
0x1800689da  jbe     short loc_1800689E3
0x1800689dc  cmp     byte ptr [rcx], 1
0x1800689df  mov     bl, 1
0x1800689e1  jz      short loc_1800689E6
0x1800689e3  mov     bl, r14b
0x1800689e6  test    rcx, rcx
0x1800689e9  jz      short loc_1800689F1
0x1800689eb  call    cs:__imp_WTSFreeMemory
0x1800689f1  test    bl, bl
0x1800689f3  jz      short loc_180068A03
0x1800689f5  or      ecx, 0FFFFFFFFh
0x1800689f8  cmp     r15d, ecx
0x1800689fb  jnz     short loc_180068A03
0x1800689fd  mov     r15d, [rdi+8]
0x180068a01  jmp     short loc_180068A7A
0x180068a03  mov     ebx, [rdi+8]
0x180068a06  lea     rcx, Contract; "ext-ms-win-session-wtsapi32-l1-1-0"
0x180068a0d  call    cs:__imp_IsApiSetImplemented
0x180068a13  test    eax, eax
0x180068a15  jz      short loc_180068A69
0x180068a17  mov     [rbp+57h+var_58], r14
0x180068a1b  mov     [rbp+57h+var_34], r14d
0x180068a1f  lea     rax, [rbp+57h+var_34]
0x180068a23  mov     [rsp+0B0h+pCount], rax; pBytesReturned
0x180068a28  lea     r9, [rbp+57h+var_58]; ppBuffer
0x180068a2c  mov     r8d, 19h; WTSInfoClass
0x180068a32  mov     edx, ebx; SessionId
0x180068a34  xor     ecx, ecx; hServer
0x180068a36  call    cs:__imp_WTSQuerySessionInformationW
0x180068a3c  test    eax, eax
0x180068a3e  jz      short loc_180068A69
0x180068a40  mov     rcx, [rbp+57h+var_58]; pMemory
0x180068a44  cmp     [rbp+57h+var_34], r14d
0x180068a48  jbe     short loc_180068A57
0x180068a4a  cmp     dword ptr [rcx], 1
0x180068a4d  jnz     short loc_180068A57
0x180068a4f  cmp     dword ptr [rcx+10h], 1
0x180068a53  mov     bl, 1
0x180068a55  jz      short loc_180068A5A
0x180068a57  mov     bl, r14b
0x180068a5a  test    rcx, rcx
0x180068a5d  jz      short loc_180068A65
0x180068a5f  call    cs:__imp_WTSFreeMemory
0x180068a65  test    bl, bl
0x180068a67  jnz     short loc_180068A89
0x180068a69  or      ecx, 0FFFFFFFFh
0x180068a6c  cmp     r12d, ecx
0x180068a6f  jnz     short loc_180068A7A
0x180068a71  mov     r12d, [rdi+8]
0x180068a75  jmp     short loc_180068A7A
0x180068a77  or      ecx, 0FFFFFFFFh
0x180068a7a  add     rdi, 38h ; '8'
0x180068a7e  cmp     rdi, r13
0x180068a81  jnz     loc_180068949
0x180068a87  jmp     short loc_180068A93
0x180068a89  mov     edi, [rdi+8]
0x180068a8c  or      ecx, 0FFFFFFFFh
0x180068a8f  cmp     edi, ecx
0x180068a91  jnz     short loc_180068AA5
0x180068a93  cmp     r12d, ecx
0x180068a96  jz      short loc_180068A9D
0x180068a98  mov     edi, r12d
0x180068a9b  jmp     short loc_180068AA5
0x180068a9d  cmp     r15d, ecx
0x180068aa0  jz      short loc_180068B02
0x180068aa2  mov     edi, r15d
0x180068aa5  mov     r14, [rbp+57h+hObject]
0x180068aa9  test    r14, r14
0x180068aac  jz      short loc_180068ACD
0x180068aae  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180068ab2  jz      short loc_180068ACD
0x180068ab4  call    cs:__imp_GetLastError
0x180068aba  mov     ebx, eax
0x180068abc  mov     rcx, r14; hObject
0x180068abf  call    cs:__imp_CloseHandle
0x180068ac5  mov     ecx, ebx; dwErrCode
0x180068ac7  call    cs:__imp_SetLastError
0x180068acd  mov     [rbp+57h+hObject], 0
0x180068ad5  lea     rdx, [rbp+57h+hObject]; phToken
0x180068ad9  mov     ecx, edi; SessionId
0x180068adb  call    cs:__imp_WTSQueryUserToken
0x180068ae1  mov     rcx, [rbp+5Fh]; this
0x180068ae5  test    eax, eax
0x180068ae7  jz      short loc_180068B60
0x180068ae9  mov     rax, [rbp+57h+hObject]
0x180068aed  mov     [rsi], rax
0x180068af0  mov     [rbp+57h+hObject], 0
0x180068af8  mov     r8d, [rbp+57h+NumberOfEntries]
0x180068afc  mov     rdx, [rbp+57h+ppSessionInfo]
0x180068b00  jmp     short loc_180068B10
0x180068b02  mov     r8d, [rbp+57h+NumberOfEntries]; NumberOfEntries
0x180068b06  mov     rdi, [rbp+57h+ppSessionInfo]
0x180068b0a  mov     [rsi], r14
0x180068b0d  mov     rdx, rdi; pMemory
0x180068b10  mov     ecx, 2; WTSTypeClass
0x180068b15  call    cs:__imp_WTSFreeMemoryExW
0x180068b1b  nop
0x180068b1c  mov     rcx, [rbp+57h+hObject]; hObject
0x180068b20  lea     rax, [rcx-1]
0x180068b24  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180068b28  ja      short loc_180068B30
0x180068b2a  call    cs:__imp_CloseHandle
0x180068b30  mov     rax, rsi
0x180068b33  mov     rcx, [rbp+57h+var_28]
0x180068b37  xor     rcx, rsp; StackCookie
0x180068b3a  call    __security_check_cookie
0x180068b3f  lea     r11, [rsp+0B0h+var_20]
0x180068b47  mov     rbx, [r11+38h]
0x180068b4b  mov     rsi, [r11+40h]
0x180068b4f  mov     rdi, [r11+48h]
0x180068b53  mov     rsp, r11
0x180068b56  pop     r15
0x180068b58  pop     r14
0x180068b5a  pop     r13
0x180068b5c  pop     r12
0x180068b5e  pop     rbp
0x180068b5f  retn
0x180068b60  lea     r8, aCW1SSrcOrchest_18; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180068b67  mov     edx, 81h; void *
0x180068b6c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180068b72  lea     r8, aCW1SSrcOrchest_18; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180068b79  mov     edx, 43h ; 'C'; void *
0x180068b7e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180068b84  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
