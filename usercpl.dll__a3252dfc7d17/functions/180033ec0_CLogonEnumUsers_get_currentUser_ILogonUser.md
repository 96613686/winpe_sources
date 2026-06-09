# CLogonEnumUsers::get_currentUser(ILogonUser * *)

- ea: `0x180033ec0`
- end: `0x180033fec`
- name: `?get_currentUser@CLogonEnumUsers@@UEAAJPEAPEAUILogonUser@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CLogonEnumUsers *__hidden this, struct ILogonUser **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180033318`
- `0x180033ec0`
- `0x1800772c0`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180033f2d`
- `SHLWAPI!StrChrW` at `0x180033f2d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033f5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033f5e`
- `SspiCli!GetUserNameExW` at `0x180033f15`
- `SspiCli!GetUserNameExW` at `0x180033f81`
- `SspiCli!GetUserNameExW` at `0x180033f15`
- `SspiCli!GetUserNameExW` at `0x180033f81`

## string_xrefs

- `0x180033f4f`: `AzureAD`

## pseudocode

```c
__int64 __fastcall CLogonEnumUsers::get_currentUser(CLogonEnumUsers *this, struct ILogonUser **a2)
{
  int UserByDomainAndName; // ebx
  PWSTR v5; // rax
  PWSTR v6; // r14
  ULONG nSize[4]; // [rsp+30h] [rbp-498h] BYREF
  WCHAR NameBuffer[280]; // [rsp+40h] [rbp-488h] BYREF
  WCHAR v10[280]; // [rsp+270h] [rbp-258h] BYREF

  *a2 = 0;
  if ( *((_DWORD *)this + 23) )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    nSize[0] = 273;
    UserByDomainAndName = -2147467259;
    if ( GetUserNameExW(NameSamCompatible, NameBuffer, nSize) )
    {
      v5 = StrChrW(NameBuffer, 0x5Cu);
      v6 = v5;
      if ( v5 )
      {
        *v5 = 0;
        if ( CompareStringOrdinal(L"AzureAD", -1, NameBuffer, -1, 1) != 2 )
          return (unsigned int)CLogonEnumUsers::_GetUserByDomainAndName(this, NameBuffer, v6 + 1, a2);
        nSize[0] = 273;
        if ( !GetUserNameExW(NameUserPrincipal, v10, nSize) )
          return (unsigned int)CLogonEnumUsers::_GetUserByDomainAndName(this, NameBuffer, v6 + 1, a2);
        UserByDomainAndName = CLogonEnumUsers::_GetUserByDomainAndName(this, NameBuffer, v10, a2);
        if ( UserByDomainAndName < 0 )
          return (unsigned int)CLogonEnumUsers::_GetUserByDomainAndName(this, NameBuffer, v6 + 1, a2);
      }
    }
  }
  return (unsigned int)UserByDomainAndName;
}

```

## disassembly

```asm
0x180033ec0  mov     [rsp+arg_10], rbx
0x180033ec5  push    rsi
0x180033ec6  push    rdi
0x180033ec7  push    r14
0x180033ec9  sub     rsp, 4B0h
0x180033ed0  mov     rax, cs:__security_cookie
0x180033ed7  xor     rax, rsp
0x180033eda  mov     [rsp+4C8h+var_28], rax
0x180033ee2  mov     qword ptr [rdx], 0
0x180033ee9  mov     rsi, rdx
0x180033eec  cmp     dword ptr [rcx+5Ch], 0
0x180033ef0  mov     rdi, rcx
0x180033ef3  jnz     loc_180033FC1
0x180033ef9  lea     r8, [rsp+4C8h+nSize]; nSize
0x180033efe  mov     [rsp+4C8h+nSize], 111h
0x180033f06  lea     rdx, [rsp+4C8h+NameBuffer]; lpNameBuffer
0x180033f0b  mov     ecx, 2; NameFormat
0x180033f10  mov     ebx, 80004005h
0x180033f15  call    cs:__imp_GetUserNameExW
0x180033f1b  test    al, al
0x180033f1d  jz      loc_180033FC6
0x180033f23  mov     edx, 5Ch ; '\'; wMatch
0x180033f28  lea     rcx, [rsp+4C8h+NameBuffer]; pszStart
0x180033f2d  call    cs:__imp_StrChrW
0x180033f33  mov     r14, rax
0x180033f36  test    rax, rax
0x180033f39  jz      loc_180033FC6
0x180033f3f  xor     ecx, ecx
0x180033f41  mov     [rsp+4C8h+bIgnoreCase], 1; bIgnoreCase
0x180033f49  or      edx, 0FFFFFFFFh; cchCount1
0x180033f4c  mov     [rax], cx
0x180033f4f  lea     rcx, String1; "AzureAD"
0x180033f56  mov     r9d, edx; cchCount2
0x180033f59  lea     r8, [rsp+4C8h+NameBuffer]; lpString2
0x180033f5e  call    cs:__imp_CompareStringOrdinal
0x180033f64  cmp     eax, 2
0x180033f67  jnz     short loc_180033FA9
0x180033f69  lea     r8, [rsp+4C8h+nSize]; nSize
0x180033f6e  mov     [rsp+4C8h+nSize], 111h
0x180033f76  lea     rdx, [rsp+4C8h+var_258]; lpNameBuffer
0x180033f7e  lea     ecx, [rax+6]; NameFormat
0x180033f81  call    cs:__imp_GetUserNameExW
0x180033f87  test    al, al
0x180033f89  jz      short loc_180033FA9
0x180033f8b  mov     r9, rsi; struct ILogonUser **
0x180033f8e  lea     r8, [rsp+4C8h+var_258]; unsigned __int16 *
0x180033f96  lea     rdx, [rsp+4C8h+NameBuffer]; lpString1
0x180033f9b  mov     rcx, rdi; this
0x180033f9e  call    ?_GetUserByDomainAndName@CLogonEnumUsers@@AEAAJPEBG0PEAPEAUILogonUser@@@Z; CLogonEnumUsers::_GetUserByDomainAndName(ushort const *,ushort const *,ILogonUser * *)
0x180033fa3  mov     ebx, eax
0x180033fa5  test    eax, eax
0x180033fa7  jns     short loc_180033FC6
0x180033fa9  lea     r8, [r14+2]; unsigned __int16 *
0x180033fad  mov     r9, rsi; struct ILogonUser **
0x180033fb0  lea     rdx, [rsp+4C8h+NameBuffer]; lpString1
0x180033fb5  mov     rcx, rdi; this
0x180033fb8  call    ?_GetUserByDomainAndName@CLogonEnumUsers@@AEAAJPEBG0PEAPEAUILogonUser@@@Z; CLogonEnumUsers::_GetUserByDomainAndName(ushort const *,ushort const *,ILogonUser * *)
0x180033fbd  mov     ebx, eax
0x180033fbf  jmp     short loc_180033FC6
0x180033fc1  mov     ebx, 80070057h
0x180033fc6  mov     eax, ebx
0x180033fc8  mov     rcx, [rsp+4C8h+var_28]
0x180033fd0  xor     rcx, rsp; StackCookie
0x180033fd3  call    __security_check_cookie
0x180033fd8  mov     rbx, [rsp+4C8h+arg_10]
0x180033fe0  add     rsp, 4B0h
0x180033fe7  pop     r14
0x180033fe9  pop     rdi
0x180033fea  pop     rsi
0x180033feb  retn
```
