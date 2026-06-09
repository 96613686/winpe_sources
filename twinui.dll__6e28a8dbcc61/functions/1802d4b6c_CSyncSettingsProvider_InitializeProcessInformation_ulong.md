# CSyncSettingsProvider::InitializeProcessInformation(ulong)

- ea: `0x1802d4b6c`
- end: `0x1802d4d30`
- name: `?InitializeProcessInformation@CSyncSettingsProvider@@AEAAJK@Z`
- size: `452`
- prototype: `int(CSyncSettingsProvider *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802d4a94`

## callees

- `0x18002769c`
- `0x18009f240`
- `0x180107164`
- `0x1801862cc`
- `0x1802d4b6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4cc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4cc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802d4bbe`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802d4bbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d4cfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d4cfd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802d4c32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802d4c32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d4bf2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d4c60`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d4bf2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d4c60`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802d4b8d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802d4b8d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1802d4cb7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1802d4cb7`

## pseudocode

```c
__int64 __fastcall CSyncSettingsProvider::InitializeProcessInformation(CSyncSettingsProvider *this, DWORD a2)
{
  signed int Error; // edi
  LPWSTR v4; // rdx
  void *v5; // rbx
  PSID *v6; // rbx
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h]
  __int64 v13; // [rsp+40h] [rbp-10h]
  void *TokenHandle; // [rsp+70h] [rbp+20h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp+28h] BYREF
  HANDLE v16; // [rsp+80h] [rbp+30h] BYREF

  *((_DWORD *)this + 8) = a2;
  Error = 0;
  v16 = OpenProcess(0x400u, 0, a2);
  v5 = v16;
  if ( !v16 )
    Error = ResultFromLastError();
  TokenHandle = 0;
  if ( Error >= 0 && !OpenProcessToken(v5, 8u, &TokenHandle) )
    Error = ResultFromLastError();
  v6 = 0;
  if ( Error >= 0 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
      goto LABEL_12;
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    if ( Error >= 0 )
    {
LABEL_12:
      if ( TokenInformationLength > 8 )
      {
        v6 = (PSID *)LocalAlloc(0, TokenInformationLength);
        if ( v6 )
        {
          if ( !GetTokenInformation(
                  TokenHandle,
                  TokenAppContainerSid,
                  v6,
                  TokenInformationLength,
                  &TokenInformationLength) )
          {
            v8 = GetLastError();
            Error = v8;
            if ( v8 > 0 )
              Error = (unsigned __int16)v8 | 0x80070000;
          }
        }
        else
        {
          Error = -2147024882;
        }
      }
      else
      {
        Error = -2147024809;
      }
    }
  }
  StringSid = 0;
  v12 = 0;
  v13 = 0;
  if ( Error >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid, v4);
    v12 = -1;
    v13 = -1;
    if ( ConvertSidToStringSidW(*v6, &StringSid) )
      goto LABEL_24;
    v9 = GetLastError();
    Error = v9;
    if ( v9 > 0 )
      Error = (unsigned __int16)v9 | 0x80070000;
    if ( Error >= 0 )
    {
LABEL_24:
      v4 = StringSid;
      if ( StringSid )
        Error = Windows::Internal::String::_InitializeHelper((HSTRING *)this + 3, StringSid);
      else
        Error = -2147467261;
    }
  }
  if ( v6 )
    LocalFree(v6);
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid, v4);
  CAutoHandle<void *>::~CAutoHandle<void *>(&TokenHandle);
  CAutoHandle<void *>::~CAutoHandle<void *>(&v16);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802d4b6c  mov     [rsp-18h+arg_18], rbx
0x1802d4b71  push    rbp
0x1802d4b72  push    rsi
0x1802d4b73  push    rdi
0x1802d4b74  mov     rbp, rsp
0x1802d4b77  sub     rsp, 50h
0x1802d4b7b  mov     [rcx+20h], edx
0x1802d4b7e  mov     rsi, rcx
0x1802d4b81  mov     r8d, edx; dwProcessId
0x1802d4b84  mov     ecx, 400h; dwDesiredAccess
0x1802d4b89  xor     edx, edx; bInheritHandle
0x1802d4b8b  xor     edi, edi
0x1802d4b8d  call    cs:__imp_OpenProcess
0x1802d4b93  mov     [rbp+arg_10], rax
0x1802d4b97  mov     rbx, rax
0x1802d4b9a  test    rax, rax
0x1802d4b9d  jnz     short loc_1802D4BA6
0x1802d4b9f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802d4ba4  mov     edi, eax
0x1802d4ba6  mov     [rbp+TokenHandle], 0
0x1802d4bae  test    edi, edi
0x1802d4bb0  js      short loc_1802D4BCF
0x1802d4bb2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1802d4bb6  mov     edx, 8; DesiredAccess
0x1802d4bbb  mov     rcx, rbx; ProcessHandle
0x1802d4bbe  call    cs:__imp_OpenProcessToken
0x1802d4bc4  test    eax, eax
0x1802d4bc6  jnz     short loc_1802D4BCF
0x1802d4bc8  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802d4bcd  mov     edi, eax
0x1802d4bcf  xor     ebx, ebx
0x1802d4bd1  test    edi, edi
0x1802d4bd3  js      loc_1802D4C7F
0x1802d4bd9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802d4bdd  lea     rax, [rbp+TokenInformationLength]
0x1802d4be1  xor     r9d, r9d; TokenInformationLength
0x1802d4be4  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1802d4be9  xor     r8d, r8d; TokenInformation
0x1802d4bec  mov     [rbp+TokenInformationLength], ebx
0x1802d4bef  lea     edx, [rbx+1Fh]; TokenInformationClass
0x1802d4bf2  call    cs:__imp_GetTokenInformation
0x1802d4bf8  test    eax, eax
0x1802d4bfa  jnz     short loc_1802D4C20
0x1802d4bfc  call    cs:__imp_GetLastError
0x1802d4c02  cmp     eax, 7Ah ; 'z'
0x1802d4c05  jz      short loc_1802D4C20
0x1802d4c07  call    cs:__imp_GetLastError
0x1802d4c0d  mov     edi, eax
0x1802d4c0f  test    eax, eax
0x1802d4c11  jle     short loc_1802D4C1C
0x1802d4c13  movzx   edi, ax
0x1802d4c16  or      edi, 80070000h
0x1802d4c1c  test    edi, edi
0x1802d4c1e  js      short loc_1802D4C7F
0x1802d4c20  cmp     [rbp+TokenInformationLength], 8
0x1802d4c24  ja      short loc_1802D4C2D
0x1802d4c26  mov     edi, 80070057h
0x1802d4c2b  jmp     short loc_1802D4C7F
0x1802d4c2d  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1802d4c30  xor     ecx, ecx; uFlags
0x1802d4c32  call    cs:__imp_LocalAlloc
0x1802d4c38  mov     rbx, rax
0x1802d4c3b  test    rax, rax
0x1802d4c3e  jnz     short loc_1802D4C47
0x1802d4c40  mov     edi, 8007000Eh
0x1802d4c45  jmp     short loc_1802D4C7F
0x1802d4c47  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1802d4c4b  lea     rax, [rbp+TokenInformationLength]
0x1802d4c4f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802d4c53  mov     r8, rbx; TokenInformation
0x1802d4c56  mov     edx, 1Fh; TokenInformationClass
0x1802d4c5b  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1802d4c60  call    cs:__imp_GetTokenInformation
0x1802d4c66  test    eax, eax
0x1802d4c68  jnz     short loc_1802D4C7F
0x1802d4c6a  call    cs:__imp_GetLastError
0x1802d4c70  mov     edi, eax
0x1802d4c72  test    eax, eax
0x1802d4c74  jle     short loc_1802D4C7F
0x1802d4c76  movzx   edi, ax
0x1802d4c79  or      edi, 80070000h
0x1802d4c7f  mov     [rbp+StringSid], 0
0x1802d4c87  mov     [rbp+var_18], 0
0x1802d4c8f  mov     [rbp+var_10], 0
0x1802d4c97  test    edi, edi
0x1802d4c99  js      short loc_1802D4CF5
0x1802d4c9b  lea     rcx, [rbp+StringSid]
0x1802d4c9f  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802d4ca4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802d4ca8  lea     rdx, [rbp+StringSid]; StringSid
0x1802d4cac  mov     [rbp+var_18], rax
0x1802d4cb0  mov     [rbp+var_10], rax
0x1802d4cb4  mov     rcx, [rbx]; Sid
0x1802d4cb7  call    cs:__imp_ConvertSidToStringSidW
0x1802d4cbd  test    eax, eax
0x1802d4cbf  jnz     short loc_1802D4CDA
0x1802d4cc1  call    cs:__imp_GetLastError
0x1802d4cc7  mov     edi, eax
0x1802d4cc9  test    eax, eax
0x1802d4ccb  jle     short loc_1802D4CD6
0x1802d4ccd  movzx   edi, ax
0x1802d4cd0  or      edi, 80070000h
0x1802d4cd6  test    edi, edi
0x1802d4cd8  js      short loc_1802D4CF5
0x1802d4cda  mov     rdx, [rbp+StringSid]; unsigned __int16 *
0x1802d4cde  test    rdx, rdx
0x1802d4ce1  jz      short loc_1802D4CF0
0x1802d4ce3  lea     rcx, [rsi+18h]; this
0x1802d4ce7  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1802d4cec  mov     edi, eax
0x1802d4cee  jmp     short loc_1802D4CF5
0x1802d4cf0  mov     edi, 80004003h
0x1802d4cf5  test    rbx, rbx
0x1802d4cf8  jz      short loc_1802D4D03
0x1802d4cfa  mov     rcx, rbx; hMem
0x1802d4cfd  call    cs:__imp_LocalFree
0x1802d4d03  lea     rcx, [rbp+StringSid]
0x1802d4d07  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802d4d0c  lea     rcx, [rbp+TokenHandle]
0x1802d4d10  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802d4d15  lea     rcx, [rbp+arg_10]
0x1802d4d19  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802d4d1e  mov     rbx, [rsp+50h+arg_18]
0x1802d4d26  mov     eax, edi
0x1802d4d28  add     rsp, 50h
0x1802d4d2c  pop     rdi
0x1802d4d2d  pop     rsi
0x1802d4d2e  pop     rbp
0x1802d4d2f  retn
```
