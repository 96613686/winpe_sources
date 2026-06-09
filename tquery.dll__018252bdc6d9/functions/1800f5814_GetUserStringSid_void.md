# GetUserStringSid(void)

- ea: `0x1800f5814`
- end: `0x1800f5a03`
- name: `?GetUserStringSid@@YAPEA_WXZ`
- size: `495`
- prototype: `wchar_t *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800f510c`

## callees

- `0x180038f08`
- `0x1800f5814`
- `0x180147154`
- `0x18016d2f0`
- `0x180188d90`
- `0x180189280`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f585b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f585b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f586d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f586d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f596e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f59c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f596e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f59c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f58a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f5915`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f58a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f5915`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800f595c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800f595c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f599a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f599a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPWSTR GetUserStringSid(void)
{
  HANDLE CurrentProcess; // rax
  void *v1; // rbx
  const char *v2; // r9
  const char *v3; // r9
  PSID v4; // rdi
  const char *v6; // r9
  LPWSTR v7; // rdi
  int ReturnLength; // [rsp+20h] [rbp-59h]
  DWORD v9; // [rsp+30h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-41h] BYREF
  LPWSTR StringSid[2]; // [rsp+40h] [rbp-39h] BYREF
  int v12; // [rsp+50h] [rbp-29h] BYREF
  LPVOID TokenInformation; // [rsp+58h] [rbp-21h]
  _BYTE v14[96]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v12 = 6;
  TokenInformation = v14;
  XGrowable<_TOKEN_USER,6>::SetSize(&v12);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  v1 = TokenHandle;
  StringSid[1] = (LPWSTR)TokenHandle;
  v9 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 16 * v12, &v9) )
  {
    if ( v9 <= 16 * v12 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1801,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        v2);
    if ( v9 + 15 < v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\internal\\include\\tgrow.hxx",
        v9 + 15 < v9 ? (const char *)0x80070216LL : 0,
        ReturnLength);
    XGrowable<_TOKEN_USER,6>::SetSize(&v12);
    if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 16 * v12, &v9) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17FC,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        v3);
  }
  v4 = *(PSID *)TokenInformation;
  if ( EqualSid(*(PSID *)TokenInformation, qword_1803663A8) )
  {
    if ( v1 )
      CloseHandle(v1);
    if ( TokenInformation != v14 )
      operator delete(TokenInformation);
    return 0;
  }
  else
  {
    StringSid[0] = 0;
    if ( !ConvertSidToStringSidW(v4, StringSid) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1813,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        v6);
    v7 = StringSid[0];
    if ( v1 )
      CloseHandle(v1);
    if ( TokenInformation != v14 )
      operator delete(TokenInformation);
    return v7;
  }
}

```

## disassembly

```asm
0x1800f5814  mov     [rsp-8+arg_0], rbx
0x1800f5819  mov     [rsp-8+arg_8], rdi
0x1800f581e  push    rbp
0x1800f581f  lea     rbp, [rsp-57h]
0x1800f5824  sub     rsp, 0D0h
0x1800f582b  mov     rax, cs:__security_cookie
0x1800f5832  xor     rax, rsp
0x1800f5835  mov     [rbp+57h+var_10], rax
0x1800f5839  mov     edx, 6
0x1800f583e  mov     [rbp+57h+var_80], edx
0x1800f5841  lea     rax, [rbp+57h+var_70]
0x1800f5845  mov     [rbp+57h+TokenInformation], rax
0x1800f5849  lea     rcx, [rbp+57h+var_80]
0x1800f584d  call    ?SetSize@?$XGrowable@U_TOKEN_USER@@$05@@QEAAPEAU_TOKEN_USER@@I@Z; XGrowable<_TOKEN_USER,6>::SetSize(uint)
0x1800f5852  nop
0x1800f5853  mov     [rbp+57h+TokenHandle], 0
0x1800f585b  call    cs:__imp_GetCurrentProcess
0x1800f5861  mov     rcx, rax; ProcessHandle
0x1800f5864  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800f5868  mov     edx, 8; DesiredAccess
0x1800f586d  call    cs:__imp_OpenProcessToken
0x1800f5873  mov     rbx, [rbp+57h+TokenHandle]
0x1800f5877  mov     [rbp+57h+var_88], rbx
0x1800f587b  mov     [rbp+57h+var_A0], 0
0x1800f5882  mov     r9d, [rbp+57h+var_80]
0x1800f5886  shl     r9d, 4; TokenInformationLength
0x1800f588a  lea     rax, [rbp+57h+var_A0]
0x1800f588e  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x1800f5893  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800f5897  mov     edi, 1
0x1800f589c  mov     edx, edi; TokenInformationClass
0x1800f589e  mov     rcx, rbx; TokenHandle
0x1800f58a1  call    cs:__imp_GetTokenInformation
0x1800f58a7  test    eax, eax
0x1800f58a9  jnz     loc_1800F594B
0x1800f58af  mov     eax, [rbp+57h+var_80]
0x1800f58b2  shl     eax, 4
0x1800f58b5  mov     ecx, [rbp+57h+var_A0]
0x1800f58b8  cmp     ecx, eax
0x1800f58ba  jbe     short loc_1800F5935
0x1800f58bc  lea     eax, [rcx+0Fh]
0x1800f58bf  or      edx, 0FFFFFFFFh
0x1800f58c2  cmp     eax, ecx
0x1800f58c4  cmovnb  edx, eax
0x1800f58c7  sbb     r9d, r9d
0x1800f58ca  and     r9d, 80070216h; char *
0x1800f58d1  mov     r10, [rbp+5Fh]
0x1800f58d5  cmp     eax, ecx
0x1800f58d7  jnb     short loc_1800F58EE
0x1800f58d9  lea     r8, aOnecoreuapBase_215; "onecoreuap\\base\\appmodel\\Search\\tqu"...
0x1800f58e0  mov     edx, 97h; void *
0x1800f58e5  mov     rcx, r10; this
0x1800f58e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f58ee  shr     edx, 4
0x1800f58f1  lea     rcx, [rbp+57h+var_80]
0x1800f58f5  call    ?SetSize@?$XGrowable@U_TOKEN_USER@@$05@@QEAAPEAU_TOKEN_USER@@I@Z; XGrowable<_TOKEN_USER,6>::SetSize(uint)
0x1800f58fa  mov     r9d, [rbp+57h+var_80]
0x1800f58fe  shl     r9d, 4; TokenInformationLength
0x1800f5902  lea     rax, [rbp+57h+var_A0]
0x1800f5906  mov     qword ptr [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800f590b  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800f590f  mov     edx, edi; TokenInformationClass
0x1800f5911  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800f5915  call    cs:__imp_GetTokenInformation
0x1800f591b  test    eax, eax
0x1800f591d  jnz     short loc_1800F594B
0x1800f591f  mov     rcx, [rbp+5Fh]; this
0x1800f5923  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f592a  mov     edx, 17FCh; void *
0x1800f592f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800f5935  mov     rcx, [rbp+5Fh]; this
0x1800f5939  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f5940  mov     edx, 1801h; void *
0x1800f5945  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800f594b  mov     rax, [rbp+57h+TokenInformation]
0x1800f594f  mov     rdi, [rax]
0x1800f5952  lea     rdx, qword_1803663A8; pSid2
0x1800f5959  mov     rcx, rdi; pSid1
0x1800f595c  call    cs:__imp_EqualSid
0x1800f5962  test    eax, eax
0x1800f5964  jz      short loc_1800F598B
0x1800f5966  test    rbx, rbx
0x1800f5969  jz      short loc_1800F5975
0x1800f596b  mov     rcx, rbx; hObject
0x1800f596e  call    cs:__imp_CloseHandle
0x1800f5974  nop
0x1800f5975  lea     rax, [rbp+57h+var_70]
0x1800f5979  mov     rcx, [rbp+57h+TokenInformation]; Block
0x1800f597d  cmp     rcx, rax
0x1800f5980  jz      short loc_1800F5987
0x1800f5982  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f5987  xor     eax, eax
0x1800f5989  jmp     short loc_1800F59E2
0x1800f598b  mov     [rbp+57h+StringSid], 0
0x1800f5993  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800f5997  mov     rcx, rdi; Sid
0x1800f599a  call    cs:__imp_ConvertSidToStringSidW
0x1800f59a0  test    eax, eax
0x1800f59a2  jnz     short loc_1800F59BA
0x1800f59a4  mov     rcx, [rbp+5Fh]; this
0x1800f59a8  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f59af  mov     edx, 1813h; void *
0x1800f59b4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800f59ba  mov     rdi, [rbp+57h+StringSid]
0x1800f59be  test    rbx, rbx
0x1800f59c1  jz      short loc_1800F59CD
0x1800f59c3  mov     rcx, rbx; hObject
0x1800f59c6  call    cs:__imp_CloseHandle
0x1800f59cc  nop
0x1800f59cd  lea     rax, [rbp+57h+var_70]
0x1800f59d1  mov     rcx, [rbp+57h+TokenInformation]; Block
0x1800f59d5  cmp     rcx, rax
0x1800f59d8  jz      short loc_1800F59DF
0x1800f59da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f59df  mov     rax, rdi
0x1800f59e2  mov     rcx, [rbp+57h+var_10]
0x1800f59e6  xor     rcx, rsp; StackCookie
0x1800f59e9  call    __security_check_cookie
0x1800f59ee  lea     r11, [rsp+0D0h+var_s0]
0x1800f59f6  mov     rbx, [r11+10h]
0x1800f59fa  mov     rdi, [r11+18h]
0x1800f59fe  mov     rsp, r11
0x1800f5a01  pop     rbp
0x1800f5a02  retn
```
