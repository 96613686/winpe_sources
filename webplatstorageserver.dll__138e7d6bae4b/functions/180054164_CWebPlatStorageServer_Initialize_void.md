# CWebPlatStorageServer::Initialize(void)

- ea: `0x180054164`
- end: `0x1800543ce`
- name: `?Initialize@CWebPlatStorageServer@@AEAAJXZ`
- size: `618`
- prototype: `__int64 __fastcall(CWebPlatStorageServer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180046d54`

## callees

- `0x180054164`
- `0x180080fb0`
- `0x180081b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800541b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800541b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800541ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800541ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800541d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005423d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005426f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005428b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800541d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005423d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005426f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005428b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800542d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800542d3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180054303`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180054339`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005436f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180054303`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180054339`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005436f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800542ee`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180054324`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005435a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800542ee`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180054324`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005435a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054214`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054214`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWebPlatStorageServer::Initialize(CWebPlatStorageServer *this)
{
  HANDLE CurrentProcess; // rax
  signed int v3; // eax
  signed int v4; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  PSID *v10; // rbx
  BOOL v11; // eax
  BOOL v12; // eax
  DWORD cbSid; // [rsp+38h] [rbp-21h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-1Dh] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-9h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    v10 = (PSID *)((char *)this + 56);
    if ( !GetTokenInformation(TokenHandle, TokenUser, (char *)this + 56, 0x58u, &ReturnLength) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_4;
    }
    if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      goto LABEL_4;
    }
    v11 = EqualSid(pSid, *v10);
    *((_DWORD *)this + 13) = v11;
    if ( !v11 )
    {
      cbSid = 68;
      if ( !CreateWellKnownSid(WinLocalServiceSid, 0, pSid, &cbSid) )
      {
        v8 = GetLastError();
        v4 = v8;
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0x80070000;
        goto LABEL_4;
      }
      v12 = EqualSid(pSid, *v10);
      *((_DWORD *)this + 13) = v12;
      if ( !v12 )
      {
        cbSid = 68;
        if ( !CreateWellKnownSid(WinNetworkServiceSid, 0, pSid, &cbSid) )
        {
          v9 = GetLastError();
          v4 = v9;
          if ( v9 > 0 )
            v4 = (unsigned __int16)v9 | 0x80070000;
          goto LABEL_4;
        }
        *((_DWORD *)this + 13) = EqualSid(pSid, *v10);
      }
    }
    *((_QWORD *)this + 18) = v10;
    v4 = 0;
    goto LABEL_8;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
LABEL_4:
  if ( v4 >= 0 )
    v4 = -2147418113;
  if ( this != (CWebPlatStorageServer *)-56LL )
    memset_0((char *)this + 56, 0, 0x58u);
LABEL_8:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180054164  mov     [rsp-8+arg_8], rbx
0x180054169  mov     [rsp-8+arg_10], rdi
0x18005416e  push    rbp
0x18005416f  lea     rbp, [rsp-57h]
0x180054174  sub     rsp, 0B0h
0x18005417b  mov     rax, cs:__security_cookie
0x180054182  xor     rax, rsp
0x180054185  mov     [rbp+57h+var_10], rax
0x180054189  xor     edx, edx; Val
0x18005418b  mov     [rbp+57h+var_7C], 0
0x180054192  mov     rdi, rcx
0x180054195  mov     [rbp+57h+TokenHandle], 0
0x18005419d  lea     rcx, [rbp+57h+pSid]; void *
0x1800541a1  mov     [rbp+57h+var_74], 0
0x1800541a8  lea     r8d, [rdx+44h]; Size
0x1800541ac  call    memset_0
0x1800541b1  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800541b8  call    cs:__imp_GetCurrentProcess
0x1800541be  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800541c2  mov     edx, 20008h; DesiredAccess
0x1800541c7  mov     rcx, rax; ProcessHandle
0x1800541ca  call    cs:__imp_OpenProcessToken
0x1800541d0  test    eax, eax
0x1800541d2  jnz     loc_1800542B5
0x1800541d8  call    cs:__imp_GetLastError
0x1800541de  mov     ebx, eax
0x1800541e0  test    eax, eax
0x1800541e2  jg      loc_1800542A7
0x1800541e8  mov     [rbp+57h+var_7C], 12Ch
0x1800541ef  mov     eax, 8000FFFFh
0x1800541f4  test    ebx, ebx
0x1800541f6  cmovns  ebx, eax
0x1800541f9  mov     eax, 38h ; '8'
0x1800541fe  lea     rcx, [rdi+rax]; void *
0x180054202  test    rcx, rcx
0x180054205  jnz     loc_1800543BE
0x18005420b  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18005420f  test    rcx, rcx
0x180054212  jz      short loc_18005421A
0x180054214  call    cs:__imp_CloseHandle
0x18005421a  mov     eax, ebx
0x18005421c  mov     rcx, [rbp+57h+var_10]
0x180054220  xor     rcx, rsp; StackCookie
0x180054223  call    __security_check_cookie
0x180054228  lea     r11, [rsp+0B0h+var_s0]
0x180054230  mov     rbx, [r11+18h]
0x180054234  mov     rdi, [r11+20h]
0x180054238  mov     rsp, r11
0x18005423b  pop     rbp
0x18005423c  retn
0x18005423d  call    cs:__imp_GetLastError
0x180054243  mov     ebx, eax
0x180054245  test    eax, eax
0x180054247  jg      loc_180054386
0x18005424d  mov     [rbp+57h+var_7C], 12Dh
0x180054254  jmp     short loc_1800541EF
0x180054256  call    cs:__imp_GetLastError
0x18005425c  mov     ebx, eax
0x18005425e  test    eax, eax
0x180054260  jg      loc_180054394
0x180054266  mov     [rbp+57h+var_7C], 133h
0x18005426d  jmp     short loc_1800541EF
0x18005426f  call    cs:__imp_GetLastError
0x180054275  mov     ebx, eax
0x180054277  test    eax, eax
0x180054279  jg      loc_1800543A2
0x18005427f  mov     [rbp+57h+var_7C], 13Ch
0x180054286  jmp     loc_1800541EF
0x18005428b  call    cs:__imp_GetLastError
0x180054291  mov     ebx, eax
0x180054293  test    eax, eax
0x180054295  jg      loc_1800543B0
0x18005429b  mov     [rbp+57h+var_7C], 145h
0x1800542a2  jmp     loc_1800541EF
0x1800542a7  movzx   ebx, ax
0x1800542aa  or      ebx, 80070000h
0x1800542b0  jmp     loc_1800541E8
0x1800542b5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800542b9  lea     rax, [rbp+57h+var_74]
0x1800542bd  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800542c3  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800542c8  lea     rbx, [rdi+38h]
0x1800542cc  mov     r8, rbx; TokenInformation
0x1800542cf  lea     edx, [r9-57h]; TokenInformationClass
0x1800542d3  call    cs:__imp_GetTokenInformation
0x1800542d9  test    eax, eax
0x1800542db  jz      loc_18005423D
0x1800542e1  xor     edx, edx; DomainSid
0x1800542e3  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800542e7  lea     r8, [rbp+57h+pSid]; pSid
0x1800542eb  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800542ee  call    cs:__imp_CreateWellKnownSid
0x1800542f4  test    eax, eax
0x1800542f6  jz      loc_180054256
0x1800542fc  mov     rdx, [rbx]; pSid2
0x1800542ff  lea     rcx, [rbp+57h+pSid]; pSid1
0x180054303  call    cs:__imp_EqualSid
0x180054309  mov     [rdi+34h], eax
0x18005430c  test    eax, eax
0x18005430e  jnz     short loc_180054378
0x180054310  lea     r9, [rbp+57h+cbSid]; cbSid
0x180054314  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18005431b  lea     r8, [rbp+57h+pSid]; pSid
0x18005431f  xor     edx, edx; DomainSid
0x180054321  lea     ecx, [rax+17h]; WellKnownSidType
0x180054324  call    cs:__imp_CreateWellKnownSid
0x18005432a  test    eax, eax
0x18005432c  jz      loc_18005426F
0x180054332  mov     rdx, [rbx]; pSid2
0x180054335  lea     rcx, [rbp+57h+pSid]; pSid1
0x180054339  call    cs:__imp_EqualSid
0x18005433f  mov     [rdi+34h], eax
0x180054342  test    eax, eax
0x180054344  jnz     short loc_180054378
0x180054346  lea     r9, [rbp+57h+cbSid]; cbSid
0x18005434a  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180054351  lea     r8, [rbp+57h+pSid]; pSid
0x180054355  xor     edx, edx; DomainSid
0x180054357  lea     ecx, [rax+18h]; WellKnownSidType
0x18005435a  call    cs:__imp_CreateWellKnownSid
0x180054360  test    eax, eax
0x180054362  jz      loc_18005428B
0x180054368  mov     rdx, [rbx]; pSid2
0x18005436b  lea     rcx, [rbp+57h+pSid]; pSid1
0x18005436f  call    cs:__imp_EqualSid
0x180054375  mov     [rdi+34h], eax
0x180054378  mov     [rdi+90h], rbx
0x18005437f  xor     ebx, ebx
0x180054381  jmp     loc_18005420B
0x180054386  movzx   ebx, ax
0x180054389  or      ebx, 80070000h
0x18005438f  jmp     loc_18005424D
0x180054394  movzx   ebx, ax
0x180054397  or      ebx, 80070000h
0x18005439d  jmp     loc_180054266
0x1800543a2  movzx   ebx, ax
0x1800543a5  or      ebx, 80070000h
0x1800543ab  jmp     loc_18005427F
0x1800543b0  movzx   ebx, ax
0x1800543b3  or      ebx, 80070000h
0x1800543b9  jmp     loc_18005429B
0x1800543be  xor     edx, edx; Val
0x1800543c0  lea     r8d, [rdx+58h]; Size
0x1800543c4  call    memset_0
0x1800543c9  jmp     loc_18005420B
```
