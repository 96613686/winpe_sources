# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x18001ad50`
- end: `0x18001aecd`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `381`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014054`

## callees

- `0x180007568`
- `0x18001ad50`
- `0x18001b7b0`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18001ae1d`
- `ntdll!NtOpenProcessToken` at `0x18001ae1d`
- `ntdll!NtClose` at `0x18001ade8`
- `ntdll!NtClose` at `0x18001ae9c`
- `ntdll!NtClose` at `0x18001ade8`
- `ntdll!NtClose` at `0x18001ae9c`
- `ntdll!NtOpenThreadToken` at `0x18001ad8d`
- `ntdll!NtOpenThreadToken` at `0x18001ad8d`
- `ntdll!NtPrivilegeCheck` at `0x18001ae65`
- `ntdll!NtPrivilegeCheck` at `0x18001ae65`

## string_xrefs

- `0x18001adb8`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001adb1`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x18001ae31`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`
- `0x18001ae79`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
        Windows::WCP::Implementation::Rtl *this,
        bool *a2)
{
  __int64 v3; // rdx
  NTSTATUS v4; // ebx
  void *v6; // rcx
  char *v7; // rcx
  unsigned __int8 Result[8]; // [rsp+40h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+50h] [rbp-20h] BYREF

  *(_BYTE *)this = 0;
  TokenHandle = 0;
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -1073741700 )
    goto LABEL_3;
  v6 = TokenHandle;
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( v4 < 0 )
    {
LABEL_3:
      RtlReportErrorOrigination("Windows::WCP::Implementation::Rtl::CanSetSystemOwner", v3, (unsigned int)v4);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      return (unsigned int)v4;
    }
    v6 = TokenHandle;
  }
  Result[0] = 0;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  v4 = NtPrivilegeCheck(v6, &RequiredPrivileges, Result);
  if ( v4 < 0 )
    goto LABEL_3;
  v7 = (char *)TokenHandle;
  *(_BYTE *)this = Result[0] != 0;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v7) < 0 )
    __fastfail(7u);
  return 0;
}

```

## disassembly

```asm
0x18001ad50  mov     [rsp-8+arg_8], rbx
0x18001ad55  mov     [rsp-8+arg_10], rdi
0x18001ad5a  push    rbp
0x18001ad5b  mov     rbp, rsp
0x18001ad5e  sub     rsp, 70h
0x18001ad62  mov     rax, cs:__security_cookie
0x18001ad69  xor     rax, rsp
0x18001ad6c  mov     [rbp+var_8], rax
0x18001ad70  xor     r8d, r8d; OpenAsSelf
0x18001ad73  mov     byte ptr [rcx], 0
0x18001ad76  mov     rdi, rcx
0x18001ad79  mov     [rbp+TokenHandle], 0
0x18001ad81  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001ad85  lea     edx, [r8+8]; DesiredAccess
0x18001ad89  lea     rcx, [r8-2]; ThreadHandle
0x18001ad8d  call    cs:__imp_NtOpenThreadToken
0x18001ad93  mov     ebx, eax
0x18001ad95  mov     eax, 80000000h
0x18001ad9a  lea     ecx, [rbx+rax]
0x18001ad9d  test    eax, ecx
0x18001ad9f  jnz     short loc_18001AE00
0x18001ada1  cmp     ebx, 0C000007Ch
0x18001ada7  jz      short loc_18001AE00
0x18001ada9  mov     [rbp+var_40], 23Ah
0x18001adb1  lea     rax, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x18001adb8  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18001adbf  mov     [rbp+var_38], rax
0x18001adc3  mov     [rbp+var_50], rcx
0x18001adc7  mov     r8d, ebx
0x18001adca  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x18001add1  mov     [rbp+var_48], rcx
0x18001add5  call    RtlReportErrorOrigination
0x18001adda  mov     rcx, [rbp+TokenHandle]; Handle
0x18001adde  lea     rax, [rcx-1]
0x18001ade2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ade6  ja      short loc_18001ADF9
0x18001ade8  call    cs:__imp_NtClose
0x18001adee  test    eax, eax
0x18001adf0  jns     short loc_18001ADF9
0x18001adf2  mov     ecx, 7
0x18001adf7  int     29h; Win8: RtlFailFast(ecx)
0x18001adf9  mov     eax, ebx
0x18001adfb  jmp     loc_18001AEAF
0x18001ae00  mov     rcx, [rbp+TokenHandle]
0x18001ae04  lea     rax, [rcx+1]
0x18001ae08  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001ae0e  jnz     short loc_18001AE41
0x18001ae10  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001ae14  mov     edx, 8; DesiredAccess
0x18001ae19  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001ae1d  call    cs:__imp_NtOpenProcessToken
0x18001ae23  mov     ebx, eax
0x18001ae25  test    eax, eax
0x18001ae27  jns     short loc_18001AE3D
0x18001ae29  mov     [rbp+var_40], 242h
0x18001ae31  lea     rax, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x18001ae38  jmp     loc_18001ADB8
0x18001ae3d  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18001ae41  mov     eax, 1
0x18001ae46  mov     [rbp+Result], 0
0x18001ae4a  mov     [rbp+RequiredPrivileges.PrivilegeCount], eax
0x18001ae4d  lea     r8, [rbp+Result]; Result
0x18001ae51  mov     [rbp+RequiredPrivileges.Control], eax
0x18001ae54  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18001ae58  xor     eax, eax
0x18001ae5a  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x18001ae62  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x18001ae65  call    cs:__imp_NtPrivilegeCheck
0x18001ae6b  mov     ebx, eax
0x18001ae6d  test    eax, eax
0x18001ae6f  jns     short loc_18001AE85
0x18001ae71  mov     [rbp+var_40], 24Ah
0x18001ae79  lea     rax, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x18001ae80  jmp     loc_18001ADB8
0x18001ae85  cmp     [rbp+Result], 0
0x18001ae89  mov     rcx, [rbp+TokenHandle]; Handle
0x18001ae8d  setnz   al
0x18001ae90  mov     [rdi], al
0x18001ae92  lea     rax, [rcx-1]
0x18001ae96  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ae9a  ja      short loc_18001AEAD
0x18001ae9c  call    cs:__imp_NtClose
0x18001aea2  test    eax, eax
0x18001aea4  jns     short loc_18001AEAD
0x18001aea6  mov     ecx, 7
0x18001aeab  int     29h; Win8: RtlFailFast(ecx)
0x18001aead  xor     eax, eax
0x18001aeaf  mov     rcx, [rbp+var_8]
0x18001aeb3  xor     rcx, rsp; StackCookie
0x18001aeb6  call    __security_check_cookie
0x18001aebb  lea     r11, [rsp+70h+var_s0]
0x18001aec0  mov     rbx, [r11+18h]
0x18001aec4  mov     rdi, [r11+20h]
0x18001aec8  mov     rsp, r11
0x18001aecb  pop     rbp
0x18001aecc  retn
```
