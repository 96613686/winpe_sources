# VerifyCallerIsAdministrator(CToken *,int *)

- ea: `0x1800ea6a8`
- end: `0x1800ea8e2`
- name: `?VerifyCallerIsAdministrator@@YAJPEAVCToken@@PEAH@Z`
- size: `570`
- prototype: `int(struct CToken *, int *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ea980`
- `0x1800eae00`
- `0x1800eaf10`
- `0x1800eb8f0`
- `0x1800eba20`
- `0x1800ebaf0`

## callees

- `0x18002f058`
- `0x180034540`
- `0x180070740`
- `0x18008150c`
- `0x1800b27e0`
- `0x1800ea6a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea7e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea7e0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ea7d6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ea7d6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ea7ca`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ea7ca`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800ea716`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800ea716`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea766`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea822`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea86e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea766`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea822`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea86e`

## string_xrefs

- `0x1800ea79e`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x1800ea8a2`: `onecore\com\combase\rpcss\olescm\scmif.cxx`

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
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      return v5;
    StringSid = 0;
    ConvertSidToStringSidW((char *)a1 + 156, &StringSid);
    v6 = 1312;
    goto LABEL_8;
  }
  if ( !*a2 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1)) )
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
0x1800ea6a8  mov     r11, rsp
0x1800ea6ab  mov     [r11+18h], rbx
0x1800ea6af  mov     [r11+20h], rsi
0x1800ea6b3  push    rbp
0x1800ea6b4  push    rdi
0x1800ea6b5  push    r14
0x1800ea6b7  mov     rbp, rsp
0x1800ea6ba  sub     rsp, 80h
0x1800ea6c1  mov     rax, cs:__security_cookie
0x1800ea6c8  xor     rax, rsp
0x1800ea6cb  mov     [rbp+var_8], rax
0x1800ea6cf  xor     r14d, r14d
0x1800ea6d2  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800ea6d8  lea     rax, [rbp+SidToCheck]
0x1800ea6dc  mov     [rbp+SidToCheck], r14
0x1800ea6e0  mov     [r11-48h], rax
0x1800ea6e4  mov     rdi, rdx
0x1800ea6e7  mov     [r11-50h], r14d
0x1800ea6eb  mov     rsi, rcx
0x1800ea6ee  mov     [r11-58h], r14d
0x1800ea6f2  lea     r8d, [r14+20h]; nSubAuthority0
0x1800ea6f6  mov     [r11-60h], r14d
0x1800ea6fa  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800ea6fe  mov     [r11-68h], r14d
0x1800ea702  mov     r9d, 220h; nSubAuthority1
0x1800ea708  mov     [r11-70h], r14d
0x1800ea70c  mov     dl, 2; nSubAuthorityCount
0x1800ea70e  mov     [r11-78h], r14d
0x1800ea712  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x1800ea716  call    cs:__imp_AllocateAndInitializeSid
0x1800ea71c  test    eax, eax
0x1800ea71e  jnz     loc_1800EA7BF
0x1800ea724  call    cs:__imp_GetLastError
0x1800ea72a  mov     ebx, eax
0x1800ea72c  test    eax, eax
0x1800ea72e  jle     short loc_1800EA739
0x1800ea730  movzx   ebx, ax
0x1800ea733  or      ebx, 80070000h
0x1800ea739  mov     eax, cs:dword_18014E4B8
0x1800ea73f  test    eax, eax
0x1800ea741  jnz     short loc_1800EA757
0x1800ea743  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1800ea74a  jz      short loc_1800EA7B8
0x1800ea74c  xor     ecx, ecx
0x1800ea74e  call    IsWppLevelEnabled
0x1800ea753  test    al, al
0x1800ea755  jz      short loc_1800EA7B8
0x1800ea757  lea     rcx, [rsi+9Ch]; Sid
0x1800ea75e  mov     [rbp+StringSid], r14
0x1800ea762  lea     rdx, [rbp+StringSid]; StringSid
0x1800ea766  call    cs:__imp_ConvertSidToStringSidW
0x1800ea76c  mov     r8d, 514h
0x1800ea772  mov     rax, [rbp+StringSid]
0x1800ea776  lea     rcx, Class
0x1800ea77d  test    rax, rax
0x1800ea780  mov     dword ptr [rsp+80h+var_50], ebx
0x1800ea784  lea     rdx, aVerifycalleris; "VerifyCallerIsAdministrator"
0x1800ea78b  cmovnz  rcx, rax
0x1800ea78f  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800ea796  mov     [rsp+80h+var_58], rcx
0x1800ea79b  xor     r9d, r9d
0x1800ea79e  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ea7a5  mov     [rsp+80h+var_60], rax
0x1800ea7aa  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800ea7af  lea     rcx, [rbp+StringSid]
0x1800ea7b3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ea7b8  mov     eax, ebx
0x1800ea7ba  jmp     loc_1800EA8BE
0x1800ea7bf  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800ea7c3  mov     r8, rdi; IsMember
0x1800ea7c6  mov     rcx, [rsi+48h]; TokenHandle
0x1800ea7ca  call    cs:__imp_CheckTokenMembership
0x1800ea7d0  mov     rcx, [rbp+SidToCheck]; pSid
0x1800ea7d4  mov     ebx, eax
0x1800ea7d6  call    cs:__imp_FreeSid
0x1800ea7dc  test    ebx, ebx
0x1800ea7de  jnz     short loc_1800EA833
0x1800ea7e0  call    cs:__imp_GetLastError
0x1800ea7e6  mov     ebx, eax
0x1800ea7e8  test    eax, eax
0x1800ea7ea  jle     short loc_1800EA7F5
0x1800ea7ec  movzx   ebx, ax
0x1800ea7ef  or      ebx, 80070000h
0x1800ea7f5  mov     eax, cs:dword_18014E4B8
0x1800ea7fb  test    eax, eax
0x1800ea7fd  jnz     short loc_1800EA813
0x1800ea7ff  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1800ea806  jz      short loc_1800EA7B8
0x1800ea808  xor     ecx, ecx
0x1800ea80a  call    IsWppLevelEnabled
0x1800ea80f  test    al, al
0x1800ea811  jz      short loc_1800EA7B8
0x1800ea813  lea     rcx, [rsi+9Ch]; Sid
0x1800ea81a  mov     [rbp+StringSid], r14
0x1800ea81e  lea     rdx, [rbp+StringSid]; StringSid
0x1800ea822  call    cs:__imp_ConvertSidToStringSidW
0x1800ea828  mov     r8d, 520h
0x1800ea82e  jmp     loc_1800EA772
0x1800ea833  cmp     [rdi], r14d
0x1800ea836  jnz     loc_1800EA8BC
0x1800ea83c  mov     eax, cs:dword_18014E4B8
0x1800ea842  mov     ebx, 1
0x1800ea847  test    eax, eax
0x1800ea849  jnz     short loc_1800EA85F
0x1800ea84b  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1800ea852  jz      short loc_1800EA8BC
0x1800ea854  mov     ecx, ebx
0x1800ea856  call    IsWppLevelEnabled
0x1800ea85b  test    al, al
0x1800ea85d  jz      short loc_1800EA8BC
0x1800ea85f  lea     rcx, [rsi+9Ch]; Sid
0x1800ea866  mov     [rbp+StringSid], r14
0x1800ea86a  lea     rdx, [rbp+StringSid]; StringSid
0x1800ea86e  call    cs:__imp_ConvertSidToStringSidW
0x1800ea874  mov     rax, [rbp+StringSid]
0x1800ea878  lea     rcx, Class
0x1800ea87f  test    rax, rax
0x1800ea882  lea     rdx, aVerifycalleris; "VerifyCallerIsAdministrator"
0x1800ea889  mov     r9d, ebx
0x1800ea88c  mov     r8d, 525h
0x1800ea892  cmovnz  rcx, rax
0x1800ea896  lea     rax, aNotAnAdminWs; "Not an admin %ws"
0x1800ea89d  mov     [rsp+80h+var_58], rcx
0x1800ea8a2  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ea8a9  mov     [rsp+80h+var_60], rax
0x1800ea8ae  call    ??$ComTraceMessageT@PEBG@@YAXPEBD0HW4TraceLevel@@PEBG2@Z; ComTraceMessageT<ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *)
0x1800ea8b3  lea     rcx, [rbp+StringSid]
0x1800ea8b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ea8bc  xor     eax, eax
0x1800ea8be  mov     rcx, [rbp+var_8]
0x1800ea8c2  xor     rcx, rsp; StackCookie
0x1800ea8c5  call    __security_check_cookie
0x1800ea8ca  lea     r11, [rsp+80h+var_s0]
0x1800ea8d2  mov     rbx, [r11+30h]
0x1800ea8d6  mov     rsi, [r11+38h]
0x1800ea8da  mov     rsp, r11
0x1800ea8dd  pop     r14
0x1800ea8df  pop     rdi
0x1800ea8e0  pop     rbp
0x1800ea8e1  retn
```
