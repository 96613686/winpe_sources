# CDeviceSettingsProvider::InitializeProcessInformation(ulong)

- ea: `0x1802d3f50`
- end: `0x1802d40fe`
- name: `?InitializeProcessInformation@CDeviceSettingsProvider@@AEAAJK@Z`
- size: `430`
- prototype: `int(CDeviceSettingsProvider *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802d3ea8`

## callees

- `0x180107164`
- `0x1801862cc`
- `0x1802d3f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d3fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d3fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d3fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d3fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d4098`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802d3f9d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802d3f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d4067`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d4075`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d4067`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d4075`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d40dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d40eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d40dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802d40eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802d4011`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802d4011`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d3fd1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d403f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d3fd1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802d403f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802d3f70`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802d3f70`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1802d408e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1802d408e`

## pseudocode

```c
__int64 __fastcall CDeviceSettingsProvider::InitializeProcessInformation(CDeviceSettingsProvider *this, DWORD a2)
{
  signed int Error; // ebx
  HANDLE v4; // rsi
  PSID *v5; // rdi
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  LPWSTR v9; // rax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp+40h] BYREF

  *((_DWORD *)this + 8) = a2;
  Error = 0;
  v4 = OpenProcess(0x400u, 0, a2);
  if ( !v4 )
    Error = ResultFromLastError();
  TokenHandle = 0;
  if ( Error >= 0 && !OpenProcessToken(v4, 8u, &TokenHandle) )
    Error = ResultFromLastError();
  v5 = 0;
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
        v5 = (PSID *)LocalAlloc(0, TokenInformationLength);
        if ( v5 )
        {
          if ( !GetTokenInformation(
                  TokenHandle,
                  TokenAppContainerSid,
                  v5,
                  TokenInformationLength,
                  &TokenInformationLength) )
          {
            v7 = GetLastError();
            Error = v7;
            if ( v7 > 0 )
              Error = (unsigned __int16)v7 | 0x80070000;
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
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 )
    CloseHandle(v4);
  StringSid = 0;
  if ( Error >= 0 )
  {
    if ( ConvertSidToStringSidW(*v5, &StringSid) )
      goto LABEL_29;
    v8 = GetLastError();
    Error = v8;
    if ( v8 > 0 )
      Error = (unsigned __int16)v8 | 0x80070000;
    if ( Error >= 0 )
    {
LABEL_29:
      v9 = StringSid;
      if ( !StringSid )
      {
        Error = -2147467261;
LABEL_32:
        if ( v9 )
          LocalFree(v9);
        goto LABEL_34;
      }
      Error = Windows::Internal::String::_InitializeHelper((HSTRING *)this + 3, StringSid);
    }
    v9 = StringSid;
    goto LABEL_32;
  }
LABEL_34:
  if ( v5 )
    LocalFree(v5);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802d3f50  push    rbp
0x1802d3f52  push    rbx
0x1802d3f53  push    rsi
0x1802d3f54  push    rdi
0x1802d3f55  push    r14
0x1802d3f57  mov     rbp, rsp
0x1802d3f5a  sub     rsp, 30h
0x1802d3f5e  mov     [rcx+20h], edx
0x1802d3f61  mov     r14, rcx
0x1802d3f64  mov     r8d, edx; dwProcessId
0x1802d3f67  mov     ecx, 400h; dwDesiredAccess
0x1802d3f6c  xor     edx, edx; bInheritHandle
0x1802d3f6e  xor     ebx, ebx
0x1802d3f70  call    cs:__imp_OpenProcess
0x1802d3f76  mov     rsi, rax
0x1802d3f79  test    rax, rax
0x1802d3f7c  jnz     short loc_1802D3F85
0x1802d3f7e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802d3f83  mov     ebx, eax
0x1802d3f85  mov     [rbp+TokenHandle], 0
0x1802d3f8d  test    ebx, ebx
0x1802d3f8f  js      short loc_1802D3FAE
0x1802d3f91  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1802d3f95  mov     edx, 8; DesiredAccess
0x1802d3f9a  mov     rcx, rsi; ProcessHandle
0x1802d3f9d  call    cs:__imp_OpenProcessToken
0x1802d3fa3  test    eax, eax
0x1802d3fa5  jnz     short loc_1802D3FAE
0x1802d3fa7  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802d3fac  mov     ebx, eax
0x1802d3fae  xor     edi, edi
0x1802d3fb0  test    ebx, ebx
0x1802d3fb2  js      loc_1802D405E
0x1802d3fb8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802d3fbc  lea     rax, [rbp+TokenInformationLength]
0x1802d3fc0  xor     r9d, r9d; TokenInformationLength
0x1802d3fc3  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1802d3fc8  xor     r8d, r8d; TokenInformation
0x1802d3fcb  mov     [rbp+TokenInformationLength], edi
0x1802d3fce  lea     edx, [rdi+1Fh]; TokenInformationClass
0x1802d3fd1  call    cs:__imp_GetTokenInformation
0x1802d3fd7  test    eax, eax
0x1802d3fd9  jnz     short loc_1802D3FFF
0x1802d3fdb  call    cs:__imp_GetLastError
0x1802d3fe1  cmp     eax, 7Ah ; 'z'
0x1802d3fe4  jz      short loc_1802D3FFF
0x1802d3fe6  call    cs:__imp_GetLastError
0x1802d3fec  mov     ebx, eax
0x1802d3fee  test    eax, eax
0x1802d3ff0  jle     short loc_1802D3FFB
0x1802d3ff2  movzx   ebx, ax
0x1802d3ff5  or      ebx, 80070000h
0x1802d3ffb  test    ebx, ebx
0x1802d3ffd  js      short loc_1802D405E
0x1802d3fff  cmp     [rbp+TokenInformationLength], 8
0x1802d4003  ja      short loc_1802D400C
0x1802d4005  mov     ebx, 80070057h
0x1802d400a  jmp     short loc_1802D405E
0x1802d400c  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1802d400f  xor     ecx, ecx; uFlags
0x1802d4011  call    cs:__imp_LocalAlloc
0x1802d4017  mov     rdi, rax
0x1802d401a  test    rax, rax
0x1802d401d  jnz     short loc_1802D4026
0x1802d401f  mov     ebx, 8007000Eh
0x1802d4024  jmp     short loc_1802D405E
0x1802d4026  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1802d402a  lea     rax, [rbp+TokenInformationLength]
0x1802d402e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802d4032  mov     r8, rdi; TokenInformation
0x1802d4035  mov     edx, 1Fh; TokenInformationClass
0x1802d403a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1802d403f  call    cs:__imp_GetTokenInformation
0x1802d4045  test    eax, eax
0x1802d4047  jnz     short loc_1802D405E
0x1802d4049  call    cs:__imp_GetLastError
0x1802d404f  mov     ebx, eax
0x1802d4051  test    eax, eax
0x1802d4053  jle     short loc_1802D405E
0x1802d4055  movzx   ebx, ax
0x1802d4058  or      ebx, 80070000h
0x1802d405e  mov     rcx, [rbp+TokenHandle]; hObject
0x1802d4062  test    rcx, rcx
0x1802d4065  jz      short loc_1802D406D
0x1802d4067  call    cs:__imp_CloseHandle
0x1802d406d  test    rsi, rsi
0x1802d4070  jz      short loc_1802D407B
0x1802d4072  mov     rcx, rsi; hObject
0x1802d4075  call    cs:__imp_CloseHandle
0x1802d407b  mov     [rbp+StringSid], 0
0x1802d4083  test    ebx, ebx
0x1802d4085  js      short loc_1802D40E3
0x1802d4087  mov     rcx, [rdi]; Sid
0x1802d408a  lea     rdx, [rbp+StringSid]; StringSid
0x1802d408e  call    cs:__imp_ConvertSidToStringSidW
0x1802d4094  test    eax, eax
0x1802d4096  jnz     short loc_1802D40B7
0x1802d4098  call    cs:__imp_GetLastError
0x1802d409e  mov     ebx, eax
0x1802d40a0  test    eax, eax
0x1802d40a2  jle     short loc_1802D40AD
0x1802d40a4  movzx   ebx, ax
0x1802d40a7  or      ebx, 80070000h
0x1802d40ad  test    ebx, ebx
0x1802d40af  jns     short loc_1802D40B7
0x1802d40b1  mov     rax, [rbp+StringSid]
0x1802d40b5  jmp     short loc_1802D40D5
0x1802d40b7  mov     rax, [rbp+StringSid]
0x1802d40bb  test    rax, rax
0x1802d40be  jz      short loc_1802D40D0
0x1802d40c0  lea     rcx, [r14+18h]; this
0x1802d40c4  mov     rdx, rax; unsigned __int16 *
0x1802d40c7  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1802d40cc  mov     ebx, eax
0x1802d40ce  jmp     short loc_1802D40B1
0x1802d40d0  mov     ebx, 80004003h
0x1802d40d5  test    rax, rax
0x1802d40d8  jz      short loc_1802D40E3
0x1802d40da  mov     rcx, rax; hMem
0x1802d40dd  call    cs:__imp_LocalFree
0x1802d40e3  test    rdi, rdi
0x1802d40e6  jz      short loc_1802D40F1
0x1802d40e8  mov     rcx, rdi; hMem
0x1802d40eb  call    cs:__imp_LocalFree
0x1802d40f1  mov     eax, ebx
0x1802d40f3  add     rsp, 30h
0x1802d40f7  pop     r14
0x1802d40f9  pop     rdi
0x1802d40fa  pop     rsi
0x1802d40fb  pop     rbx
0x1802d40fc  pop     rbp
0x1802d40fd  retn
```
