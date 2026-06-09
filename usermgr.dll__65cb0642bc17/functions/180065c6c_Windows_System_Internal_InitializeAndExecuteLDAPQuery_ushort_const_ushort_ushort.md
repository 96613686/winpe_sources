# Windows::System::Internal::_InitializeAndExecuteLDAPQuery(ushort const *,ushort * *,ushort * *)

- ea: `0x180065c6c`
- end: `0x180065fa7`
- name: `?_InitializeAndExecuteLDAPQuery@Internal@System@Windows@@YAJPEBGPEAPEAG1@Z`
- size: `827`
- prototype: `__int64 __fastcall(PWSTR base, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d3828`

## callees

- `0x1800088e8`
- `0x180060524`
- `0x180065c6c`
- `0x1800d2154`
- `0x1800d31c8`
- `0x1800de450`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065cc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065d18`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065cc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d27`
- `netutils!NetApiBufferFree` at `0x180065f64`
- `netutils!NetApiBufferFree` at `0x180065f64`
- `logoncli!DsGetDcNameW` at `0x180065d80`
- `logoncli!DsGetDcNameW` at `0x180065d80`
- `WLDAP32!__imp_ldap_unbind` at `0x180065f5a`
- `WLDAP32!__imp_ldap_unbind` at `0x180065f5a`
- `WLDAP32!__imp_LdapGetLastError` at `0x180065db7`
- `WLDAP32!__imp_LdapGetLastError` at `0x180065db7`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180065dbf`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180065de5`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180065e14`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180065e7a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180065dbf`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180065de5`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180065e14`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180065e7a`
- `WLDAP32!__imp_ldap_msgfree` at `0x180065f51`
- `WLDAP32!__imp_ldap_msgfree` at `0x180065f51`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180065e0c`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180065e0c`
- `WLDAP32!__imp_ldap_connect` at `0x180065ddd`
- `WLDAP32!__imp_ldap_connect` at `0x180065ddd`
- `WLDAP32!__imp_ldap_initW` at `0x180065da4`
- `WLDAP32!__imp_ldap_initW` at `0x180065da4`
- `WLDAP32!__imp_ldap_search_sW` at `0x180065e72`
- `WLDAP32!__imp_ldap_search_sW` at `0x180065e72`

## string_xrefs

- `0x180065cf6`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x180065d4b`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x180065cbc`: `logoncli.dll`
- `0x180065d11`: `wldap32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::_InitializeAndExecuteLDAPQuery(
        PWSTR base,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  signed int v7; // eax
  signed int LDAPValue; // ebx
  signed int v9; // eax
  LDAP *v10; // rsi
  ULONG LastError; // eax
  signed int v12; // eax
  ULONG v13; // eax
  signed int v14; // eax
  ULONG v15; // eax
  signed int v16; // eax
  ULONG v17; // eax
  signed int v18; // eax
  __int64 v19; // rax
  unsigned __int16 *v20; // rax
  int Flags; // [rsp+20h] [rbp-69h]
  unsigned __int16 **Flagsa; // [rsp+20h] [rbp-69h]
  unsigned __int16 **Flagsb; // [rsp+20h] [rbp-69h]
  LDAPMessage *entry; // [rsp+40h] [rbp-49h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int16 v27[4]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v28; // [rsp+58h] [rbp-31h]
  __int64 v29; // [rsp+60h] [rbp-29h]
  unsigned __int16 v30[4]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v31; // [rsp+70h] [rbp-19h]
  __int64 v32; // [rsp+78h] [rbp-11h]
  HMODULE v33; // [rsp+80h] [rbp-9h] BYREF
  HMODULE Library; // [rsp+88h] [rbp-1h] BYREF
  PWSTR attrs; // [rsp+90h] [rbp+7h] BYREF
  PWSTR attr; // [rsp+98h] [rbp+Fh]
  __int64 v37; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( a2 )
    *(_QWORD *)a2 = 0;
  if ( a3 )
    *a3 = 0;
  Library = LoadLibraryExW(L"logoncli.dll", 0, 0x800u);
  if ( Library )
  {
    v33 = LoadLibraryExW(L"wldap32.dll", 0, 0x800u);
    if ( v33 )
    {
      DomainControllerInfo = 0;
      if ( DsGetDcNameW(0, 0, 0, 0, 0x40008000u, &DomainControllerInfo) )
      {
        LDAPValue = -2147467259;
      }
      else
      {
        v10 = ldap_initW((const PWSTR)DomainControllerInfo->DomainControllerName + 2, 0x185u);
        if ( v10 )
          goto LABEL_21;
        LastError = LdapGetLastError();
        v12 = LdapMapErrorToWin32(LastError);
        LDAPValue = v12;
        if ( v12 > 0 )
          LDAPValue = (unsigned __int16)v12 | 0x80070000;
        if ( LDAPValue >= 0 )
        {
LABEL_21:
          v13 = ldap_connect(v10, 0);
          v14 = LdapMapErrorToWin32(v13);
          LDAPValue = v14;
          if ( v14 > 0 )
            LDAPValue = (unsigned __int16)v14 | 0x80070000;
          if ( LDAPValue >= 0 )
          {
            v15 = ldap_bind_sW(v10, 0, 0, 0x486u);
            v16 = LdapMapErrorToWin32(v15);
            LDAPValue = v16;
            if ( v16 > 0 )
              LDAPValue = (unsigned __int16)v16 | 0x80070000;
            if ( LDAPValue >= 0 )
            {
              attrs = L"givenName";
              attr = L"sn";
              v37 = 0;
              entry = 0;
              v17 = ldap_search_sW(v10, base, 0, (const PWSTR)L"(objectClass=user)", &attrs, 0, &entry);
              v18 = LdapMapErrorToWin32(v17);
              LDAPValue = v18;
              if ( v18 > 0 )
                LDAPValue = (unsigned __int16)v18 | 0x80070000;
              if ( LDAPValue >= 0 )
              {
                *(_QWORD *)v30 = 0;
                v31 = 0;
                v32 = 0;
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v30);
                v31 = -1;
                v32 = -1;
                LDAPValue = Windows::System::Internal::_GetLDAPValue(v10, entry, attrs, v30, Flagsa);
                if ( LDAPValue >= 0 )
                {
                  *(_QWORD *)v27 = 0;
                  v28 = 0;
                  v29 = 0;
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v27);
                  v28 = -1;
                  v29 = -1;
                  LDAPValue = Windows::System::Internal::_GetLDAPValue(v10, entry, attr, v27, Flagsb);
                  if ( LDAPValue >= 0 )
                  {
                    if ( a2 )
                    {
                      v19 = *(_QWORD *)v30;
                      *(_QWORD *)v30 = 0;
                      v32 = 0;
                      v31 = 0;
                      *(_QWORD *)a2 = v19;
                    }
                    if ( a3 )
                    {
                      v20 = *(unsigned __int16 **)v27;
                      *(_QWORD *)v27 = 0;
                      v29 = 0;
                      v28 = 0;
                      *a3 = v20;
                    }
                  }
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v27);
                }
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v30);
              }
              if ( entry )
                ldap_msgfree(entry);
            }
          }
          ldap_unbind(v10);
        }
        NetApiBufferFree(DomainControllerInfo);
      }
    }
    else
    {
      v9 = GetLastError();
      LDAPValue = v9;
      if ( v9 > 0 )
        LDAPValue = (unsigned __int16)v9 | 0x80070000;
      if ( LDAPValue < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
          (const char *)(unsigned int)LDAPValue,
          Flags);
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v33);
  }
  else
  {
    v7 = GetLastError();
    LDAPValue = v7;
    if ( v7 > 0 )
      LDAPValue = (unsigned __int16)v7 | 0x80070000;
    if ( LDAPValue < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x398,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
        (const char *)(unsigned int)LDAPValue,
        Flags);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
  return (unsigned int)LDAPValue;
}

```

## disassembly

```asm
0x180065c6c  mov     [rsp-8+arg_18], rbx
0x180065c71  push    rbp
0x180065c72  push    rsi
0x180065c73  push    rdi
0x180065c74  push    r12
0x180065c76  push    r13
0x180065c78  push    r14
0x180065c7a  push    r15
0x180065c7c  lea     rbp, [rsp-27h]
0x180065c81  sub     rsp, 0B0h
0x180065c88  mov     rax, cs:__security_cookie
0x180065c8f  xor     rax, rsp
0x180065c92  mov     [rbp+57h+var_38], rax
0x180065c96  mov     r14, r8
0x180065c99  mov     r15, rdx
0x180065c9c  mov     r12, rcx
0x180065c9f  xor     r13d, r13d
0x180065ca2  test    rdx, rdx
0x180065ca5  jz      short loc_180065CAA
0x180065ca7  mov     [rdx], r13
0x180065caa  test    r14, r14
0x180065cad  jz      short loc_180065CB2
0x180065caf  mov     [r8], r13
0x180065cb2  mov     ebx, 800h
0x180065cb7  mov     r8d, ebx; dwFlags
0x180065cba  xor     edx, edx; hFile
0x180065cbc  lea     rcx, LibFileName; "logoncli.dll"
0x180065cc3  call    cs:__imp_LoadLibraryExW
0x180065cc9  mov     [rbp+57h+var_58], rax
0x180065ccd  test    rax, rax
0x180065cd0  jnz     short loc_180065D0C
0x180065cd2  call    cs:__imp_GetLastError
0x180065cd8  mov     ebx, eax
0x180065cda  test    eax, eax
0x180065cdc  jle     short loc_180065CE7
0x180065cde  movzx   ebx, ax
0x180065ce1  or      ebx, 80070000h
0x180065ce7  test    ebx, ebx
0x180065ce9  jns     loc_180065F75
0x180065cef  mov     rcx, [rbp+5Fh]; this
0x180065cf3  mov     r9d, ebx; char *
0x180065cf6  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x180065cfd  mov     edx, 398h; void *
0x180065d02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065d07  jmp     loc_180065F75
0x180065d0c  mov     r8d, ebx; dwFlags
0x180065d0f  xor     edx, edx; hFile
0x180065d11  lea     rcx, aWldap32Dll_0; "wldap32.dll"
0x180065d18  call    cs:__imp_LoadLibraryExW
0x180065d1e  mov     [rbp+57h+var_60], rax
0x180065d22  test    rax, rax
0x180065d25  jnz     short loc_180065D61
0x180065d27  call    cs:__imp_GetLastError
0x180065d2d  mov     ebx, eax
0x180065d2f  test    eax, eax
0x180065d31  jle     short loc_180065D3C
0x180065d33  movzx   ebx, ax
0x180065d36  or      ebx, 80070000h
0x180065d3c  test    ebx, ebx
0x180065d3e  jns     loc_180065F6B
0x180065d44  mov     rcx, [rbp+5Fh]; this
0x180065d48  mov     r9d, ebx; char *
0x180065d4b  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x180065d52  mov     edx, 39Ah; void *
0x180065d57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065d5c  jmp     loc_180065F6B
0x180065d61  mov     [rbp+57h+var_98], r13
0x180065d65  lea     rax, [rbp+57h+var_98]
0x180065d69  mov     [rsp+0E0h+DomainControllerInfo], rax; DomainControllerInfo
0x180065d6e  mov     [rsp+0E0h+Flags], 40008000h; Flags
0x180065d76  xor     r9d, r9d; SiteName
0x180065d79  xor     r8d, r8d; DomainGuid
0x180065d7c  xor     edx, edx; DomainName
0x180065d7e  xor     ecx, ecx; ComputerName
0x180065d80  call    cs:__imp_DsGetDcNameW
0x180065d86  test    eax, eax
0x180065d88  jz      short loc_180065D94
0x180065d8a  mov     ebx, 80004005h
0x180065d8f  jmp     loc_180065F6B
0x180065d94  mov     rax, [rbp+57h+var_98]
0x180065d98  mov     rcx, [rax]
0x180065d9b  add     rcx, 4; HostName
0x180065d9f  mov     edx, 185h; PortNumber
0x180065da4  call    cs:__imp_ldap_initW
0x180065daa  mov     rsi, rax
0x180065dad  mov     edi, 80070000h
0x180065db2  test    rax, rax
0x180065db5  jnz     short loc_180065DD8
0x180065db7  call    cs:__imp_LdapGetLastError
0x180065dbd  mov     ecx, eax; LdapError
0x180065dbf  call    cs:__imp_LdapMapErrorToWin32
0x180065dc5  mov     ebx, eax
0x180065dc7  test    eax, eax
0x180065dc9  jle     short loc_180065DD0
0x180065dcb  movzx   ebx, ax
0x180065dce  or      ebx, edi
0x180065dd0  test    ebx, ebx
0x180065dd2  js      loc_180065F60
0x180065dd8  xor     edx, edx; timeout
0x180065dda  mov     rcx, rsi; ld
0x180065ddd  call    cs:__imp_ldap_connect
0x180065de3  mov     ecx, eax; LdapError
0x180065de5  call    cs:__imp_LdapMapErrorToWin32
0x180065deb  mov     ebx, eax
0x180065ded  test    eax, eax
0x180065def  jle     short loc_180065DF6
0x180065df1  movzx   ebx, ax
0x180065df4  or      ebx, edi
0x180065df6  test    ebx, ebx
0x180065df8  js      loc_180065F57
0x180065dfe  mov     r9d, 486h; method
0x180065e04  xor     r8d, r8d; cred
0x180065e07  xor     edx, edx; dn
0x180065e09  mov     rcx, rsi; ld
0x180065e0c  call    cs:__imp_ldap_bind_sW
0x180065e12  mov     ecx, eax; LdapError
0x180065e14  call    cs:__imp_LdapMapErrorToWin32
0x180065e1a  mov     ebx, eax
0x180065e1c  test    eax, eax
0x180065e1e  jle     short loc_180065E25
0x180065e20  movzx   ebx, ax
0x180065e23  or      ebx, edi
0x180065e25  test    ebx, ebx
0x180065e27  js      loc_180065F57
0x180065e2d  lea     rax, aGivenname; "givenName"
0x180065e34  mov     [rbp+57h+attrs], rax
0x180065e38  lea     rax, aSn; "sn"
0x180065e3f  mov     [rbp+57h+attr], rax
0x180065e43  mov     [rbp+57h+var_40], r13
0x180065e47  mov     [rbp+57h+entry], r13
0x180065e4b  lea     rax, [rbp+57h+entry]
0x180065e4f  mov     [rsp+0E0h+res], rax; res
0x180065e54  mov     dword ptr [rsp+0E0h+DomainControllerInfo], r13d; attrsonly
0x180065e59  lea     rax, [rbp+57h+attrs]
0x180065e5d  mov     qword ptr [rsp+0E0h+Flags], rax; unsigned __int16 **
0x180065e62  lea     r9, filter; "(objectClass=user)"
0x180065e69  xor     r8d, r8d; scope
0x180065e6c  mov     rdx, r12; base
0x180065e6f  mov     rcx, rsi; ld
0x180065e72  call    cs:__imp_ldap_search_sW
0x180065e78  mov     ecx, eax; LdapError
0x180065e7a  call    cs:__imp_LdapMapErrorToWin32
0x180065e80  mov     ebx, eax
0x180065e82  test    eax, eax
0x180065e84  jle     short loc_180065E8B
0x180065e86  movzx   ebx, ax
0x180065e89  or      ebx, edi
0x180065e8b  test    ebx, ebx
0x180065e8d  js      loc_180065F48
0x180065e93  mov     qword ptr [rbp+57h+var_78], r13
0x180065e97  mov     [rbp+57h+var_70], r13
0x180065e9b  mov     [rbp+57h+var_68], r13
0x180065e9f  lea     rcx, [rbp+57h+var_78]
0x180065ea3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180065ea8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180065eac  mov     [rbp+57h+var_70], rdi
0x180065eb0  mov     [rbp+57h+var_68], rdi
0x180065eb4  lea     r9, [rbp+57h+var_78]; unsigned __int16 *
0x180065eb8  mov     r8, [rbp+57h+attrs]; attr
0x180065ebc  mov     rdx, [rbp+57h+entry]; entry
0x180065ec0  mov     rcx, rsi; ld
0x180065ec3  call    ?_GetLDAPValue@Internal@System@Windows@@YAJPEBUldap@@PEBUldapmsg@@PEBGPEAPEAG@Z; Windows::System::Internal::_GetLDAPValue(ldap const *,ldapmsg const *,ushort const *,ushort * *)
0x180065ec8  mov     ebx, eax
0x180065eca  test    eax, eax
0x180065ecc  js      short loc_180065F3F
0x180065ece  mov     qword ptr [rbp+57h+var_90], r13
0x180065ed2  mov     [rbp+57h+var_88], r13
0x180065ed6  mov     [rbp+57h+var_80], r13
0x180065eda  lea     rcx, [rbp+57h+var_90]
0x180065ede  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180065ee3  mov     [rbp+57h+var_88], rdi
0x180065ee7  mov     [rbp+57h+var_80], rdi
0x180065eeb  lea     r9, [rbp+57h+var_90]; unsigned __int16 *
0x180065eef  mov     r8, [rbp+57h+attr]; attr
0x180065ef3  mov     rdx, [rbp+57h+entry]; entry
0x180065ef7  mov     rcx, rsi; ld
0x180065efa  call    ?_GetLDAPValue@Internal@System@Windows@@YAJPEBUldap@@PEBUldapmsg@@PEBGPEAPEAG@Z; Windows::System::Internal::_GetLDAPValue(ldap const *,ldapmsg const *,ushort const *,ushort * *)
0x180065eff  mov     ebx, eax
0x180065f01  test    eax, eax
0x180065f03  js      short loc_180065F35
0x180065f05  test    r15, r15
0x180065f08  jz      short loc_180065F1D
0x180065f0a  mov     rax, qword ptr [rbp+57h+var_78]
0x180065f0e  mov     qword ptr [rbp+57h+var_78], r13
0x180065f12  mov     [rbp+57h+var_68], r13
0x180065f16  mov     [rbp+57h+var_70], r13
0x180065f1a  mov     [r15], rax
0x180065f1d  test    r14, r14
0x180065f20  jz      short loc_180065F35
0x180065f22  mov     rax, qword ptr [rbp+57h+var_90]
0x180065f26  mov     qword ptr [rbp+57h+var_90], r13
0x180065f2a  mov     [rbp+57h+var_80], r13
0x180065f2e  mov     [rbp+57h+var_88], r13
0x180065f32  mov     [r14], rax
0x180065f35  lea     rcx, [rbp+57h+var_90]
0x180065f39  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180065f3e  nop
0x180065f3f  lea     rcx, [rbp+57h+var_78]
0x180065f43  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180065f48  mov     rcx, [rbp+57h+entry]; res
0x180065f4c  test    rcx, rcx
0x180065f4f  jz      short loc_180065F57
0x180065f51  call    cs:__imp_ldap_msgfree
0x180065f57  mov     rcx, rsi; ld
0x180065f5a  call    cs:__imp_ldap_unbind
0x180065f60  mov     rcx, [rbp+57h+var_98]; Buffer
0x180065f64  call    cs:__imp_NetApiBufferFree
0x180065f6a  nop
0x180065f6b  lea     rcx, [rbp+57h+var_60]
0x180065f6f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180065f74  nop
0x180065f75  lea     rcx, [rbp+57h+var_58]
0x180065f79  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180065f7e  mov     eax, ebx
0x180065f80  mov     rcx, [rbp+57h+var_38]
0x180065f84  xor     rcx, rsp; StackCookie
0x180065f87  call    __security_check_cookie
0x180065f8c  mov     rbx, [rsp+0E0h+arg_18]
0x180065f94  add     rsp, 0B0h
0x180065f9b  pop     r15
0x180065f9d  pop     r14
0x180065f9f  pop     r13
0x180065fa1  pop     r12
0x180065fa3  pop     rdi
0x180065fa4  pop     rsi
0x180065fa5  pop     rbp
0x180065fa6  retn
```
