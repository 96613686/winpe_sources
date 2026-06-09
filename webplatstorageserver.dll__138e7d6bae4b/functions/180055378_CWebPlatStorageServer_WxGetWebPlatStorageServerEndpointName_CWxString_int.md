# CWebPlatStorageServer::WxGetWebPlatStorageServerEndpointName(CWxString *,int)

- ea: `0x180055378`
- end: `0x180055508`
- name: `?WxGetWebPlatStorageServerEndpointName@CWebPlatStorageServer@@AEAAJPEAVCWxString@@H@Z`
- size: `400`
- prototype: `__int64 __fastcall(CWebPlatStorageServer *this, struct CWxString *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054c54`

## callees

- `0x180046f04`
- `0x180055378`
- `0x18006ce4c`
- `0x180080fb0`
- `0x180081b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800553d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800553d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800553e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800553e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005547b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005547b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055437`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800554cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800554cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800554e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800554e3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180055471`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180055471`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWebPlatStorageServer::WxGetWebPlatStorageServerEndpointName(
        CWebPlatStorageServer *this,
        struct CWxString *a2)
{
  HANDLE CurrentProcess; // rax
  signed int v4; // eax
  signed int v5; // ebx
  signed int v6; // eax
  signed int LastError; // eax
  LPWSTR StringSid; // [rsp+38h] [rbp-31h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-19h] BYREF

  StringSid = 0;
  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  if ( a2 )
    CWxString::Empty(a2);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    {
      if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
      {
        v5 = CWxString::Set(a2, L"webplatstorage_{7329ea82-0845-4e4c-bd18-02b67ac065cc}_", StringSid);
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147418113;
      }
    }
    else
    {
      v6 = GetLastError();
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147418113;
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147418113;
  }
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180055378  mov     [rsp-8+arg_0], rbx
0x18005537d  push    rbp
0x18005537e  lea     rbp, [rsp-57h]
0x180055383  sub     rsp, 0C0h
0x18005538a  mov     rax, cs:__security_cookie
0x180055391  xor     rax, rsp
0x180055394  mov     [rbp+57h+var_10], rax
0x180055398  mov     rbx, rdx
0x18005539b  mov     [rbp+57h+var_8C], 0
0x1800553a2  mov     [rbp+57h+StringSid], 0
0x1800553aa  mov     [rbp+57h+TokenHandle], 0
0x1800553b2  xor     edx, edx; Val
0x1800553b4  lea     r8d, [rdx+58h]; Size
0x1800553b8  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1800553bc  call    memset_0
0x1800553c1  mov     [rbp+57h+var_80], 0
0x1800553c8  test    rbx, rbx
0x1800553cb  jz      short loc_1800553D5
0x1800553cd  mov     rcx, rbx; this
0x1800553d0  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1800553d5  call    cs:__imp_GetCurrentProcess
0x1800553db  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800553df  mov     edx, 20008h; DesiredAccess
0x1800553e4  mov     rcx, rax; ProcessHandle
0x1800553e7  call    cs:__imp_OpenProcessToken
0x1800553ed  test    eax, eax
0x1800553ef  jnz     short loc_18005541C
0x1800553f1  call    cs:__imp_GetLastError
0x1800553f7  mov     ebx, eax
0x1800553f9  test    eax, eax
0x1800553fb  jle     short loc_180055406
0x1800553fd  movzx   ebx, ax
0x180055400  or      ebx, 80070000h
0x180055406  mov     eax, 8000FFFFh
0x18005540b  test    ebx, ebx
0x18005540d  cmovns  ebx, eax
0x180055410  mov     [rbp+57h+var_8C], 220h
0x180055417  jmp     loc_1800554C3
0x18005541c  lea     rax, [rbp+57h+var_80]
0x180055420  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180055425  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18005542b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18005542f  lea     edx, [r9-57h]; TokenInformationClass
0x180055433  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180055437  call    cs:__imp_GetTokenInformation
0x18005543d  test    eax, eax
0x18005543f  jnz     short loc_180055469
0x180055441  call    cs:__imp_GetLastError
0x180055447  mov     ebx, eax
0x180055449  test    eax, eax
0x18005544b  jle     short loc_180055456
0x18005544d  movzx   ebx, ax
0x180055450  or      ebx, 80070000h
0x180055456  mov     eax, 8000FFFFh
0x18005545b  test    ebx, ebx
0x18005545d  cmovns  ebx, eax
0x180055460  mov     [rbp+57h+var_8C], 221h
0x180055467  jmp     short loc_1800554C3
0x180055469  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18005546d  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x180055471  call    cs:__imp_ConvertSidToStringSidW
0x180055477  test    eax, eax
0x180055479  jnz     short loc_1800554A3
0x18005547b  call    cs:__imp_GetLastError
0x180055481  mov     ebx, eax
0x180055483  test    eax, eax
0x180055485  jle     short loc_180055490
0x180055487  movzx   ebx, ax
0x18005548a  or      ebx, 80070000h
0x180055490  mov     eax, 8000FFFFh
0x180055495  test    ebx, ebx
0x180055497  cmovns  ebx, eax
0x18005549a  mov     [rbp+57h+var_8C], 223h
0x1800554a1  jmp     short loc_1800554C3
0x1800554a3  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x1800554a7  lea     rdx, aWebplatstorage_2; "webplatstorage_{7329ea82-0845-4e4c-bd18"...
0x1800554ae  mov     rcx, rbx; this
0x1800554b1  call    ?Set@CWxString@@QEAAJPEBG0@Z; CWxString::Set(ushort const *,ushort const *)
0x1800554b6  mov     ebx, eax
0x1800554b8  test    eax, eax
0x1800554ba  jns     short loc_1800554C3
0x1800554bc  mov     [rbp+57h+var_8C], 227h
0x1800554c3  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800554c7  test    rcx, rcx
0x1800554ca  jz      short loc_1800554DA
0x1800554cc  call    cs:__imp_LocalFree
0x1800554d2  mov     [rbp+57h+StringSid], 0
0x1800554da  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800554de  test    rcx, rcx
0x1800554e1  jz      short loc_1800554E9
0x1800554e3  call    cs:__imp_CloseHandle
0x1800554e9  mov     eax, ebx
0x1800554eb  mov     rcx, [rbp+57h+var_10]
0x1800554ef  xor     rcx, rsp; StackCookie
0x1800554f2  call    __security_check_cookie
0x1800554f7  mov     rbx, [rsp+0C0h+arg_0]
0x1800554ff  add     rsp, 0C0h
0x180055506  pop     rbp
0x180055507  retn
```
