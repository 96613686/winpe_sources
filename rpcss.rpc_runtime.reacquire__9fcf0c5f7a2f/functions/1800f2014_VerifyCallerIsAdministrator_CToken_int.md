# VerifyCallerIsAdministrator(CToken *,int *)

- ea: `0x1800f2014`
- end: `0x1800f227f`
- name: `?VerifyCallerIsAdministrator@@YAJPEAVCToken@@PEAH@Z`
- size: `619`
- prototype: `int(struct CToken *, int *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f2320`
- `0x1800f27a0`
- `0x1800f28b0`
- `0x1800f32b0`
- `0x1800f33e0`
- `0x1800f34b0`

## callees

- `0x180025088`
- `0x180034260`
- `0x180074d98`
- `0x1800858f0`
- `0x1800b7ac0`
- `0x1800f2014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f216a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f216a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f215a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800f215a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800f2148`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800f2148`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f2082`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800f2082`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f20de`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f21b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f2204`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f20de`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f21b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f2204`

## string_xrefs

- `0x1800f211c`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x1800f223e`: `onecore\com\combase\rpcss\olescm\scmif.cxx`

## pseudocode

```c
__int64 __fastcall VerifyCallerIsAdministrator(HANDLE *a1, int *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  int v6; // r8d
  LPWSTR v7; // rcx
  BOOL v9; // ebx
  signed int v10; // eax
  LPWSTR v11; // rcx
  __int64 v12; // [rsp+30h] [rbp-50h]
  LPWSTR StringSid; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      return v5;
    StringSid = 0;
    ConvertSidToStringSidW((char *)a1 + 156, &StringSid);
    v6 = 1300;
LABEL_8:
    v7 = (LPWSTR)&Class;
    LODWORD(v12) = v5;
    if ( StringSid )
      v7 = StringSid;
    ComTraceMessageT<unsigned short *,long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmif.cxx",
      (unsigned int)"VerifyCallerIsAdministrator",
      v6,
      0,
      (__int64)L"%ws %!HRESULT!",
      v7,
      v12);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    return v5;
  }
  v9 = CheckTokenMembership(a1[9], SidToCheck, a2);
  FreeSid(SidToCheck);
  if ( !v9 )
  {
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      return v5;
    StringSid = 0;
    ConvertSidToStringSidW((char *)a1 + 156, &StringSid);
    v6 = 1312;
    goto LABEL_8;
  }
  if ( !*a2 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1)) )
  {
    StringSid = 0;
    ConvertSidToStringSidW((char *)a1 + 156, &StringSid);
    v11 = (LPWSTR)&Class;
    if ( StringSid )
      v11 = StringSid;
    ComTraceMessageT<unsigned short const *>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmif.cxx",
      (unsigned int)"VerifyCallerIsAdministrator",
      1317,
      1,
      (__int64)L"Not an admin %ws",
      v11);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  }
  return 0;
}

```

## disassembly

```asm
0x1800f2014  mov     r11, rsp
0x1800f2017  mov     [r11+18h], rbx
0x1800f201b  mov     [r11+20h], rsi
0x1800f201f  push    rbp
0x1800f2020  push    rdi
0x1800f2021  push    r14
0x1800f2023  mov     rbp, rsp
0x1800f2026  sub     rsp, 80h
0x1800f202d  mov     rax, cs:__security_cookie
0x1800f2034  xor     rax, rsp
0x1800f2037  mov     [rbp+var_8], rax
0x1800f203b  xor     r14d, r14d
0x1800f203e  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800f2044  lea     rax, [rbp+SidToCheck]
0x1800f2048  mov     [rbp+SidToCheck], r14
0x1800f204c  mov     [r11-48h], rax
0x1800f2050  mov     rdi, rdx
0x1800f2053  mov     [r11-50h], r14d
0x1800f2057  mov     rsi, rcx
0x1800f205a  mov     [r11-58h], r14d
0x1800f205e  lea     r8d, [r14+20h]; nSubAuthority0
0x1800f2062  mov     [r11-60h], r14d
0x1800f2066  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800f206a  mov     [r11-68h], r14d
0x1800f206e  mov     r9d, 220h; nSubAuthority1
0x1800f2074  mov     [r11-70h], r14d
0x1800f2078  mov     dl, 2; nSubAuthorityCount
0x1800f207a  mov     [r11-78h], r14d
0x1800f207e  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x1800f2082  call    cs:__imp_AllocateAndInitializeSid
0x1800f2089  nop     dword ptr [rax+rax+00h]
0x1800f208e  test    eax, eax
0x1800f2090  jnz     loc_1800F213D
0x1800f2096  call    cs:__imp_GetLastError
0x1800f209d  nop     dword ptr [rax+rax+00h]
0x1800f20a2  mov     ebx, eax
0x1800f20a4  test    eax, eax
0x1800f20a6  jle     short loc_1800F20B1
0x1800f20a8  movzx   ebx, ax
0x1800f20ab  or      ebx, 80070000h
0x1800f20b1  mov     eax, cs:dword_1801574B8
0x1800f20b7  test    eax, eax
0x1800f20b9  jnz     short loc_1800F20CF
0x1800f20bb  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1800f20c2  jz      short loc_1800F2136
0x1800f20c4  xor     ecx, ecx
0x1800f20c6  call    IsWppLevelEnabled
0x1800f20cb  test    al, al
0x1800f20cd  jz      short loc_1800F2136
0x1800f20cf  lea     rcx, [rsi+9Ch]; Sid
0x1800f20d6  mov     [rbp+StringSid], r14
0x1800f20da  lea     rdx, [rbp+StringSid]; StringSid
0x1800f20de  call    cs:__imp_ConvertSidToStringSidW
0x1800f20e5  nop     dword ptr [rax+rax+00h]
0x1800f20ea  mov     r8d, 514h
0x1800f20f0  mov     rax, [rbp+StringSid]
0x1800f20f4  lea     rcx, Class
0x1800f20fb  test    rax, rax
0x1800f20fe  mov     dword ptr [rsp+80h+var_50], ebx
0x1800f2102  lea     rdx, aVerifycalleris; "VerifyCallerIsAdministrator"
0x1800f2109  cmovnz  rcx, rax
0x1800f210d  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f2114  mov     [rsp+80h+var_58], rcx
0x1800f2119  xor     r9d, r9d
0x1800f211c  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f2123  mov     [rsp+80h+var_60], rax
0x1800f2128  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f212d  lea     rcx, [rbp+StringSid]
0x1800f2131  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f2136  mov     eax, ebx
0x1800f2138  jmp     loc_1800F225A
0x1800f213d  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800f2141  mov     r8, rdi; IsMember
0x1800f2144  mov     rcx, [rsi+48h]; TokenHandle
0x1800f2148  call    cs:__imp_CheckTokenMembership
0x1800f214f  nop     dword ptr [rax+rax+00h]
0x1800f2154  mov     rcx, [rbp+SidToCheck]; pSid
0x1800f2158  mov     ebx, eax
0x1800f215a  call    cs:__imp_FreeSid
0x1800f2161  nop     dword ptr [rax+rax+00h]
0x1800f2166  test    ebx, ebx
0x1800f2168  jnz     short loc_1800F21C9
0x1800f216a  call    cs:__imp_GetLastError
0x1800f2171  nop     dword ptr [rax+rax+00h]
0x1800f2176  mov     ebx, eax
0x1800f2178  test    eax, eax
0x1800f217a  jle     short loc_1800F2185
0x1800f217c  movzx   ebx, ax
0x1800f217f  or      ebx, 80070000h
0x1800f2185  mov     eax, cs:dword_1801574B8
0x1800f218b  test    eax, eax
0x1800f218d  jnz     short loc_1800F21A3
0x1800f218f  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1800f2196  jz      short loc_1800F2136
0x1800f2198  xor     ecx, ecx
0x1800f219a  call    IsWppLevelEnabled
0x1800f219f  test    al, al
0x1800f21a1  jz      short loc_1800F2136
0x1800f21a3  lea     rcx, [rsi+9Ch]; Sid
0x1800f21aa  mov     [rbp+StringSid], r14
0x1800f21ae  lea     rdx, [rbp+StringSid]; StringSid
0x1800f21b2  call    cs:__imp_ConvertSidToStringSidW
0x1800f21b9  nop     dword ptr [rax+rax+00h]
0x1800f21be  mov     r8d, 520h
0x1800f21c4  jmp     loc_1800F20F0
0x1800f21c9  cmp     [rdi], r14d
0x1800f21cc  jnz     loc_1800F2258
0x1800f21d2  mov     eax, cs:dword_1801574B8
0x1800f21d8  mov     ebx, 1
0x1800f21dd  test    eax, eax
0x1800f21df  jnz     short loc_1800F21F5
0x1800f21e1  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1800f21e8  jz      short loc_1800F2258
0x1800f21ea  mov     ecx, ebx
0x1800f21ec  call    IsWppLevelEnabled
0x1800f21f1  test    al, al
0x1800f21f3  jz      short loc_1800F2258
0x1800f21f5  lea     rcx, [rsi+9Ch]; Sid
0x1800f21fc  mov     [rbp+StringSid], r14
0x1800f2200  lea     rdx, [rbp+StringSid]; StringSid
0x1800f2204  call    cs:__imp_ConvertSidToStringSidW
0x1800f220b  nop     dword ptr [rax+rax+00h]
0x1800f2210  mov     rax, [rbp+StringSid]
0x1800f2214  lea     rcx, Class
0x1800f221b  test    rax, rax
0x1800f221e  lea     rdx, aVerifycalleris; "VerifyCallerIsAdministrator"
0x1800f2225  mov     r9d, ebx
0x1800f2228  mov     r8d, 525h
0x1800f222e  cmovnz  rcx, rax
0x1800f2232  lea     rax, aNotAnAdminWs; "Not an admin %ws"
0x1800f2239  mov     [rsp+80h+var_58], rcx
0x1800f223e  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f2245  mov     [rsp+80h+var_60], rax
0x1800f224a  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800f224f  lea     rcx, [rbp+StringSid]
0x1800f2253  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f2258  xor     eax, eax
0x1800f225a  mov     rcx, [rbp+var_8]
0x1800f225e  xor     rcx, rsp; StackCookie
0x1800f2261  call    __security_check_cookie
0x1800f2266  lea     r11, [rsp+80h+var_s0]
0x1800f226e  mov     rbx, [r11+30h]
0x1800f2272  mov     rsi, [r11+38h]
0x1800f2276  mov     rsp, r11
0x1800f2279  pop     r14
0x1800f227b  pop     rdi
0x1800f227c  pop     rbp
0x1800f227d  retn
```
