# CThemeManagerAPIRequest::ImpersonateClientIfRequired(void)

- ea: `0x180002940`
- end: `0x180002ada`
- name: `?ImpersonateClientIfRequired@CThemeManagerAPIRequest@@AEAAJXZ`
- size: `410`
- prototype: `__int64 __fastcall(CThemeManagerAPIRequest *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800021d0`
- `0x180002270`
- `0x180002660`
- `0x180002b64`
- `0x18000acc0`
- `0x18000aefc`

## callees

- `0x180002940`
- `0x180004d10`
- `0x18000674c`
- `0x18000fa00`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180002a8b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180002a8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002a78`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002a78`
- `ntdll!NtOpenProcessToken` at `0x180002a2a`
- `ntdll!NtOpenProcessToken` at `0x180002a2a`
- `ntdll!NtOpenThreadToken` at `0x1800029d0`
- `ntdll!NtOpenThreadToken` at `0x1800029d0`
- `ntdll!NtOpenThread` at `0x1800029b5`
- `ntdll!NtOpenThread` at `0x1800029b5`
- `ntdll!NtOpenProcess` at `0x180002a0e`
- `ntdll!NtOpenProcess` at `0x180002a0e`
- `ntdll!NtClose` at `0x1800029dc`
- `ntdll!NtClose` at `0x180002a36`
- `ntdll!NtClose` at `0x1800029dc`
- `ntdll!NtClose` at `0x180002a36`

## pseudocode

```c
__int64 __fastcall CThemeManagerAPIRequest::ImpersonateClientIfRequired(CThemeManagerAPIRequest *this)
{
  void **v1; // rdi
  NTSTATUS v3; // ebx
  void *v4; // rcx
  void *ThreadHandle; // [rsp+30h] [rbp-19h] BYREF
  void *ProcessHandle; // [rsp+38h] [rbp-11h] BYREF
  _CLIENT_ID ClientId; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  __int64 v10; // [rsp+80h] [rbp+37h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v1 = (void **)((char *)this + 144);
  ThreadHandle = 0;
  *((_QWORD *)this + 18) = 0;
  ClientId.UniqueThread = (HANDLE)*((_QWORD *)this + 5);
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  ClientId.UniqueProcess = 0;
  v3 = NtOpenThread(&ThreadHandle, 0x40u, &ObjectAttributes, &ClientId);
  if ( v3 >= 0 )
  {
    v3 = NtOpenThreadToken(ThreadHandle, 0xEu, 0, v1);
    NtClose(ThreadHandle);
  }
  if ( v3 == -1073741700 )
  {
    *v1 = 0;
    ClientId.UniqueProcess = (HANDLE)*((_QWORD *)this + 4);
    ProcessHandle = 0;
    ClientId.UniqueThread = 0;
    v3 = NtOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
    if ( v3 < 0 )
      return (unsigned int)v3;
    v3 = NtOpenProcessToken(ProcessHandle, 0xEu, v1);
    NtClose(ProcessHandle);
  }
  if ( v3 < 0 )
    return (unsigned int)v3;
  v4 = *v1;
  LODWORD(ThreadHandle) = 0;
  v10 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( GetTokenInformation(v4, TokenStatistics, &ObjectAttributes, 0x38u, (PDWORD)&ThreadHandle)
    && ObjectAttributes.RootDirectory == (HANDLE)999 )
  {
    ReleaseHandle(v1);
    return 0;
  }
  if ( ImpersonateLoggedOnUser(*v1) )
    return 0;
  return CStatusCode::StatusCodeOfLastError();
}

```

## disassembly

```asm
0x180002940  mov     [rsp-8+arg_8], rbx
0x180002945  mov     [rsp-8+arg_10], rsi
0x18000294a  push    rbp
0x18000294b  push    rdi
0x18000294c  push    r14
0x18000294e  lea     rbp, [rsp-47h]
0x180002953  sub     rsp, 90h
0x18000295a  mov     rax, cs:__security_cookie
0x180002961  xor     rax, rsp
0x180002964  mov     [rbp+57h+var_18], rax
0x180002968  xor     r14d, r14d
0x18000296b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180002973  lea     rdi, [rcx+90h]
0x18000297a  mov     [rbp+57h+ThreadHandle], r14
0x18000297e  mov     [rdi], r14
0x180002981  lea     r9, [rbp+57h+ClientId]; ClientId
0x180002985  mov     rax, [rcx+28h]
0x180002989  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000298d  mov     rsi, rcx
0x180002990  mov     [rbp+57h+ClientId.UniqueThread], rax
0x180002994  xorps   xmm0, xmm0
0x180002997  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r14
0x18000299b  lea     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x18000299f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1800029a3  mov     edx, 40h ; '@'; DesiredAccess
0x1800029a8  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x1800029ac  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800029b1  mov     [rbp+57h+ClientId.UniqueProcess], r14
0x1800029b5  call    cs:__imp_NtOpenThread
0x1800029bb  mov     ebx, eax
0x1800029bd  test    eax, eax
0x1800029bf  js      short loc_1800029E2
0x1800029c1  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x1800029c5  mov     r9, rdi; TokenHandle
0x1800029c8  xor     r8d, r8d; OpenAsSelf
0x1800029cb  mov     edx, 0Eh; DesiredAccess
0x1800029d0  call    cs:__imp_NtOpenThreadToken
0x1800029d6  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x1800029da  mov     ebx, eax
0x1800029dc  call    cs:__imp_NtClose
0x1800029e2  cmp     ebx, 0C000007Ch
0x1800029e8  jnz     short loc_180002A3C
0x1800029ea  mov     [rdi], r14
0x1800029ed  lea     r9, [rbp+57h+ClientId]; ClientId
0x1800029f1  mov     rax, [rsi+20h]
0x1800029f5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800029f9  mov     edx, 400h; DesiredAccess
0x1800029fe  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x180002a02  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180002a06  mov     [rbp+57h+ProcessHandle], r14
0x180002a0a  mov     [rbp+57h+ClientId.UniqueThread], r14
0x180002a0e  call    cs:__imp_NtOpenProcess
0x180002a14  mov     ebx, eax
0x180002a16  test    eax, eax
0x180002a18  js      loc_180002ACF
0x180002a1e  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180002a22  mov     r8, rdi; TokenHandle
0x180002a25  mov     edx, 0Eh; DesiredAccess
0x180002a2a  call    cs:__imp_NtOpenProcessToken
0x180002a30  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x180002a34  mov     ebx, eax
0x180002a36  call    cs:__imp_NtClose
0x180002a3c  test    ebx, ebx
0x180002a3e  js      loc_180002ACF
0x180002a44  mov     rcx, [rdi]; TokenHandle
0x180002a47  lea     r8, [rbp+57h+ObjectAttributes]; TokenInformation
0x180002a4b  xorps   xmm0, xmm0
0x180002a4e  mov     dword ptr [rbp+57h+ThreadHandle], r14d
0x180002a52  xor     eax, eax
0x180002a54  mov     r9d, 38h ; '8'; TokenInformationLength
0x180002a5a  mov     [rbp+57h+var_20], rax
0x180002a5e  mov     edx, 0Ah; TokenInformationClass
0x180002a63  lea     rax, [rbp+57h+ThreadHandle]
0x180002a67  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180002a6c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180002a70  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180002a74  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002a78  call    cs:__imp_GetTokenInformation
0x180002a7e  test    eax, eax
0x180002a80  jz      short loc_180002A88
0x180002a82  cmp     dword ptr [rbp+57h+ObjectAttributes.RootDirectory+4], r14d
0x180002a86  jz      short loc_180002ABC
0x180002a88  mov     rcx, [rdi]; hToken
0x180002a8b  call    cs:__imp_ImpersonateLoggedOnUser
0x180002a91  test    eax, eax
0x180002a93  jz      short loc_180002AD3
0x180002a95  mov     eax, r14d
0x180002a98  mov     rcx, [rbp+57h+var_18]
0x180002a9c  xor     rcx, rsp; StackCookie
0x180002a9f  call    __security_check_cookie
0x180002aa4  lea     r11, [rsp+0A0h+var_10]
0x180002aac  mov     rbx, [r11+28h]
0x180002ab0  mov     rsi, [r11+30h]
0x180002ab4  mov     rsp, r11
0x180002ab7  pop     r14
0x180002ab9  pop     rdi
0x180002aba  pop     rbp
0x180002abb  retn
0x180002abc  cmp     dword ptr [rbp+57h+ObjectAttributes.RootDirectory], 3E7h
0x180002ac3  jnz     short loc_180002A88
0x180002ac5  mov     rcx, rdi
0x180002ac8  call    ReleaseHandle
0x180002acd  jmp     short loc_180002A95
0x180002acf  mov     eax, ebx
0x180002ad1  jmp     short loc_180002A98
0x180002ad3  call    ?StatusCodeOfLastError@CStatusCode@@SAJXZ; CStatusCode::StatusCodeOfLastError(void)
0x180002ad8  jmp     short loc_180002A98
```
