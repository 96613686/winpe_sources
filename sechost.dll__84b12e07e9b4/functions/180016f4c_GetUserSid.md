# _GetUserSid

- ea: `0x180016f4c`
- end: `0x18001705f`
- name: `_GetUserSid`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180015980`

## callees

- `0x180016f4c`
- `0x18004f902`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180016fc1`
- `ntdll!NtOpenProcessToken` at `0x180016fc1`
- `ntdll!NtQueryInformationToken` at `0x180016fee`
- `ntdll!NtQueryInformationToken` at `0x180016fee`
- `ntdll!NtClose` at `0x180017038`
- `ntdll!NtClose` at `0x180017038`
- `ntdll!NtOpenThreadToken` at `0x180016fa5`
- `ntdll!NtOpenThreadToken` at `0x180016fa5`
- `ntdll!RtlLengthSid` at `0x180017000`
- `ntdll!RtlLengthSid` at `0x180017015`
- `ntdll!RtlLengthSid` at `0x180017000`
- `ntdll!RtlLengthSid` at `0x180017015`

## pseudocode

```c
__int64 __fastcall GetUserSid(ULONG *a1, void *a2)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  ULONG v6; // ebx
  ULONG v7; // eax
  PSID v8; // rdx
  void *TokenHandle; // [rsp+30h] [rbp-39h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-31h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-29h] BYREF

  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  TokenHandle = 0;
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  v5 = v4;
  if ( v4 == -1073741700 )
  {
    v5 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( v5 < 0 )
      goto LABEL_9;
  }
  else if ( v4 )
  {
    goto LABEL_9;
  }
  v5 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength);
  if ( !v5 )
  {
    v6 = *a1;
    if ( RtlLengthSid(TokenInformation[0]) <= v6 )
    {
      v7 = RtlLengthSid(TokenInformation[0]);
      v8 = TokenInformation[0];
      *a1 = v7;
      memcpy_0(a2, v8, v7);
      v5 = 0;
    }
    else
    {
      v5 = -2147483643;
    }
  }
LABEL_9:
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016f4c  mov     [rsp-8+arg_10], rbx
0x180016f51  push    rbp
0x180016f52  push    rsi
0x180016f53  push    rdi
0x180016f54  lea     rbp, [rsp-47h]
0x180016f59  sub     rsp, 0B0h
0x180016f60  mov     rax, cs:__security_cookie
0x180016f67  xor     rax, rsp
0x180016f6a  mov     [rbp+57h+var_20], rax
0x180016f6e  mov     rsi, rdx
0x180016f71  mov     rdi, rcx
0x180016f74  xor     edx, edx; Val
0x180016f76  lea     rcx, [rbp+57h+TokenInformation]; void *
0x180016f7a  lea     r8d, [rdx+58h]; Size
0x180016f7e  call    memset_0
0x180016f83  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180016f87  mov     [rbp+57h+var_88], 0
0x180016f8e  mov     r8b, 1; OpenAsSelf
0x180016f91  mov     [rbp+57h+TokenHandle], 0
0x180016f99  mov     edx, 8; DesiredAccess
0x180016f9e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180016fa5  call    cs:__imp_NtOpenThreadToken
0x180016fab  mov     ebx, eax
0x180016fad  cmp     eax, 0C000007Ch
0x180016fb2  jnz     short loc_180016FCF
0x180016fb4  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180016fb8  mov     edx, 8; DesiredAccess
0x180016fbd  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180016fc1  call    cs:__imp_NtOpenProcessToken
0x180016fc7  mov     ebx, eax
0x180016fc9  test    eax, eax
0x180016fcb  jns     short loc_180016FD3
0x180016fcd  jmp     short loc_18001702F
0x180016fcf  test    eax, eax
0x180016fd1  jnz     short loc_18001702F
0x180016fd3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180016fd7  lea     rax, [rbp+57h+var_88]
0x180016fdb  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180016fe1  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180016fe6  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180016fea  lea     edx, [r9-57h]; TokenInformationClass
0x180016fee  call    cs:__imp_NtQueryInformationToken
0x180016ff4  mov     ebx, eax
0x180016ff6  test    eax, eax
0x180016ff8  jnz     short loc_18001702F
0x180016ffa  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x180016ffe  mov     ebx, [rdi]
0x180017000  call    cs:__imp_RtlLengthSid
0x180017006  cmp     eax, ebx
0x180017008  jbe     short loc_180017011
0x18001700a  mov     ebx, 80000005h
0x18001700f  jmp     short loc_18001702F
0x180017011  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x180017015  call    cs:__imp_RtlLengthSid
0x18001701b  mov     rdx, [rbp+57h+TokenInformation]; Src
0x18001701f  mov     rcx, rsi; void *
0x180017022  mov     r8d, eax; Size
0x180017025  mov     [rdi], r8d
0x180017028  call    memcpy_0
0x18001702d  xor     ebx, ebx
0x18001702f  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180017033  test    rcx, rcx
0x180017036  jz      short loc_18001703E
0x180017038  call    cs:__imp_NtClose
0x18001703e  mov     eax, ebx
0x180017040  mov     rcx, [rbp+57h+var_20]
0x180017044  xor     rcx, rsp; StackCookie
0x180017047  call    __security_check_cookie
0x18001704c  mov     rbx, [rsp+0C0h+arg_10]
0x180017054  add     rsp, 0B0h
0x18001705b  pop     rdi
0x18001705c  pop     rsi
0x18001705d  pop     rbp
0x18001705e  retn
```
