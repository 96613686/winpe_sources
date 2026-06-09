# FindAppActivationErrorHandler

- ea: `0x1800223e4`
- end: `0x180022653`
- name: `FindAppActivationErrorHandler`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037558`

## callees

- `0x1800223e4`
- `0x18002265c`
- `0x18002267c`
- `0x1800228e8`
- `0x18002b1b0`
- `0x180033d5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022526`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022577`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022526`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022577`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022496`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022496`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800225e2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800225e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
GUID *__fastcall FindAppActivationErrorHandler(GUID *a1, unsigned int a2)
{
  GUID *result; // rax
  int v4; // eax
  int v5; // eax
  const char *v6; // r9
  int ValueW; // eax
  HRESULT v8; // eax
  GUID v9; // xmm6
  int phkResult; // [rsp+20h] [rbp-D8h]
  int phkResulta; // [rsp+20h] [rbp-D8h]
  int phkResultb; // [rsp+20h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B0h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-A8h] BYREF
  WCHAR Value[16]; // [rsp+60h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( a2 == -2147023673 )
  {
    *a1 = GUID_NULL;
    return a1;
  }
  else
  {
    v4 = StringCchPrintfW(Value, 9u, L"%08x", a2);
    try
    {
      if ( v4 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB,
          (unsigned int)"onecore\\internal\\base\\inc\\appmodel\\execmodel\\AppActivationErrorHelper.h",
          (const char *)(unsigned int)v4,
          phkResult);
      hkey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      v5 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\AppActivationErrorHandlers",
             0,
             0x20119u,
             &hkey);
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      if ( v5 == -2147024894 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        *a1 = GUID_NULL;
        result = a1;
      }
      else
      {
        if ( v5 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16,
            (unsigned int)"onecore\\internal\\base\\inc\\appmodel\\execmodel\\AppActivationErrorHelper.h",
            (const char *)(unsigned int)v5,
            phkResulta);
        pcbData = 78;
        ValueW = RegGetValueW(hkey, 0, Value, 2u, 0, sz, &pcbData);
        if ( ValueW > 0 )
          ValueW = (unsigned __int16)ValueW | 0x80070000;
        if ( ValueW != -2147024894 )
          goto LABEL_19;
        pcbData = 78;
        ValueW = RegGetValueW(hkey, 0, 0, 2u, 0, sz, &pcbData);
        if ( ValueW > 0 )
          ValueW = (unsigned __int16)ValueW | 0x80070000;
        if ( ValueW == -2147024894 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          *a1 = GUID_NULL;
          result = a1;
        }
        else
        {
LABEL_19:
          if ( ValueW < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x28,
              (unsigned int)"onecore\\internal\\base\\inc\\appmodel\\execmodel\\AppActivationErrorHelper.h",
              (const char *)(unsigned int)ValueW,
              phkResultb);
          pclsid = 0;
          v8 = CLSIDFromString(sz, &pclsid);
          if ( v8 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2C,
              (unsigned int)"onecore\\internal\\base\\inc\\appmodel\\execmodel\\AppActivationErrorHelper.h",
              (const char *)(unsigned int)v8,
              phkResultb);
          v9 = pclsid;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          *a1 = v9;
          result = a1;
        }
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\internal\\base\\inc\\appmodel\\execmodel\\AppActivationErrorHelper.h",
        v6);
      result = a1;
      *a1 = GUID_NULL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800223e4  mov     rax, rsp
0x1800223e7  mov     [rax+8], rcx
0x1800223eb  push    rbx
0x1800223ec  sub     rsp, 0F0h
0x1800223f3  movaps  xmmword ptr [rax-18h], xmm6
0x1800223f7  mov     rax, cs:__security_cookie
0x1800223fe  xor     rax, rsp
0x180022401  mov     [rsp+0F8h+var_28], rax
0x180022409  mov     rbx, rcx
0x18002240c  cmp     edx, 800704C7h
0x180022412  jnz     short loc_180022427
0x180022414  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002241b  movdqu  xmmword ptr [rcx], xmm0
0x18002241f  mov     rax, rcx
0x180022422  jmp     loc_180022631
0x180022427  mov     r9d, edx
0x18002242a  lea     r8, a08x; "%08x"
0x180022431  mov     edx, 9; unsigned __int64
0x180022436  lea     rcx, [rsp+0F8h+Value]; unsigned __int16 *
0x18002243b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022440  mov     rcx, [rsp+0F8h]; this
0x180022448  test    eax, eax
0x18002244a  jns     short loc_180022460
0x18002244c  mov     r9d, eax; char *
0x18002244f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appmodel"...
0x180022456  mov     edx, 0Bh; void *
0x18002245b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022460  mov     [rsp+0F8h+hkey], 0
0x180022469  xor     edx, edx
0x18002246b  lea     rcx, [rsp+0F8h+hkey]
0x180022470  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180022475  lea     rax, [rsp+0F8h+hkey]
0x18002247a  mov     [rsp+0F8h+phkResult], rax; int
0x18002247f  mov     r9d, 20119h; samDesired
0x180022485  xor     r8d, r8d; ulOptions
0x180022488  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002248f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022496  call    cs:__imp_RegOpenKeyExW
0x18002249c  test    eax, eax
0x18002249e  jle     short loc_1800224A8
0x1800224a0  movzx   eax, ax
0x1800224a3  or      eax, 80070000h
0x1800224a8  cmp     eax, 80070002h
0x1800224ad  jnz     short loc_1800224CC
0x1800224af  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800224b6  lea     rcx, [rsp+0F8h+hkey]
0x1800224bb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800224c0  movdqu  xmmword ptr [rbx], xmm6
0x1800224c4  mov     rax, rbx
0x1800224c7  jmp     loc_180022631
0x1800224cc  mov     rcx, [rsp+0F8h]; this
0x1800224d4  test    eax, eax
0x1800224d6  jns     short loc_1800224EC
0x1800224d8  mov     r9d, eax; char *
0x1800224db  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appmodel"...
0x1800224e2  mov     edx, 16h; void *
0x1800224e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800224ec  mov     [rsp+0F8h+var_B8], 4Eh ; 'N'
0x1800224f4  lea     rax, [rsp+0F8h+var_B8]
0x1800224f9  mov     [rsp+0F8h+pcbData], rax; pcbData
0x1800224fe  lea     rax, [rsp+0F8h+sz]
0x180022506  mov     [rsp+0F8h+pvData], rax; pvData
0x18002250b  mov     [rsp+0F8h+phkResult], 0; int
0x180022514  mov     r9d, 2; dwFlags
0x18002251a  lea     r8, [rsp+0F8h+Value]; lpValue
0x18002251f  xor     edx, edx; lpSubKey
0x180022521  mov     rcx, [rsp+0F8h+hkey]; hkey
0x180022526  call    cs:__imp_RegGetValueW
0x18002252c  test    eax, eax
0x18002252e  jle     short loc_180022538
0x180022530  movzx   eax, ax
0x180022533  or      eax, 80070000h
0x180022538  cmp     eax, 80070002h
0x18002253d  jnz     short loc_1800225AD
0x18002253f  mov     [rsp+0F8h+var_B8], 4Eh ; 'N'
0x180022547  lea     rax, [rsp+0F8h+var_B8]
0x18002254c  mov     [rsp+0F8h+pcbData], rax; pcbData
0x180022551  lea     rax, [rsp+0F8h+sz]
0x180022559  mov     [rsp+0F8h+pvData], rax; pvData
0x18002255e  mov     [rsp+0F8h+phkResult], 0; pdwType
0x180022567  mov     r9d, 2; dwFlags
0x18002256d  xor     r8d, r8d; lpValue
0x180022570  xor     edx, edx; lpSubKey
0x180022572  mov     rcx, [rsp+0F8h+hkey]; hkey
0x180022577  call    cs:__imp_RegGetValueW
0x18002257d  test    eax, eax
0x18002257f  jle     short loc_180022589
0x180022581  movzx   eax, ax
0x180022584  or      eax, 80070000h
0x180022589  cmp     eax, 80070002h
0x18002258e  jnz     short loc_1800225AD
0x180022590  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180022597  lea     rcx, [rsp+0F8h+hkey]
0x18002259c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800225a1  movdqu  xmmword ptr [rbx], xmm6
0x1800225a5  mov     rax, rbx
0x1800225a8  jmp     loc_180022631
0x1800225ad  mov     rcx, [rsp+0F8h]; this
0x1800225b5  test    eax, eax
0x1800225b7  jns     short loc_1800225CD
0x1800225b9  mov     r9d, eax; char *
0x1800225bc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appmodel"...
0x1800225c3  mov     edx, 28h ; '('; void *
0x1800225c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800225cd  xorps   xmm0, xmm0
0x1800225d0  movups  xmmword ptr [rsp+0F8h+pclsid.Data1], xmm0
0x1800225d5  lea     rdx, [rsp+0F8h+pclsid]; pclsid
0x1800225da  lea     rcx, [rsp+0F8h+sz]; lpsz
0x1800225e2  call    cs:__imp_CLSIDFromString
0x1800225e8  mov     rcx, [rsp+0F8h]; this
0x1800225f0  test    eax, eax
0x1800225f2  jns     short loc_180022608
0x1800225f4  mov     r9d, eax; char *
0x1800225f7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appmodel"...
0x1800225fe  mov     edx, 2Ch ; ','; void *
0x180022603  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022608  movaps  xmm6, xmmword ptr [rsp+0F8h+pclsid.Data1]
0x18002260d  lea     rcx, [rsp+0F8h+hkey]
0x180022612  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022617  movdqu  xmmword ptr [rbx], xmm6
0x18002261b  mov     rax, rbx
0x18002261e  jmp     short loc_180022631
0x180022620  movups  xmm0, xmmword ptr [rsp+0F8h+pclsid.Data1]
0x180022625  mov     rax, [rsp+0F8h+arg_0]
0x18002262d  movdqu  xmmword ptr [rax], xmm0
0x180022631  mov     rcx, [rsp+0F8h+var_28]
0x180022639  xor     rcx, rsp; StackCookie
0x18002263c  call    __security_check_cookie
0x180022641  movaps  xmm6, [rsp+0F8h+var_18]
0x180022649  add     rsp, 0F0h
0x180022650  pop     rbx
0x180022651  retn
```
