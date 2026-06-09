# CInstClassFactory::GetKeyForNotifications(HKEY__ * *)

- ea: `0x18001f8a0`
- end: `0x18001fa9f`
- name: `?GetKeyForNotifications@CInstClassFactory@@AEAAJPEAPEAUHKEY__@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(CInstClassFactory *__hidden this, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f860`

## callees

- `0x180005540`
- `0x180005560`
- `0x180008320`
- `0x18000bf78`
- `0x18001f5a4`
- `0x18001f8a0`
- `0x1800207cc`

## import_xrefs

- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18001f908`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18001f908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fa20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fa20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f956`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f98f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f956`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f98f`

## string_xrefs

- `0x18001f918`: `Software\Classes\CLSID\%ls\Instance`

## pseudocode

```c
__int64 __fastcall CInstClassFactory::GetKeyForNotifications(CInstClassFactory *this, HKEY *a2)
{
  HKEY *v2; // rdi
  signed int v5; // ebx
  LSTATUS v6; // eax
  signed int v7; // esi
  LSTATUS v8; // eax
  bool v9; // sf
  HKEY v10; // rbx
  HKEY v11; // rcx
  HKEY v12; // rbx
  _BYTE v14[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v15; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[256]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = (HKEY *)((char *)this + 80);
  *a2 = 0;
  if ( *((_QWORD *)this + 10) )
  {
    v5 = -2147418113;
    goto LABEL_23;
  }
  SHStringFromGUIDW((char *)this + 40, v17, 39);
  v5 = StringCchPrintfW(SubKey, 0xFFu, L"Software\\Classes\\CLSID\\%ls\\Instance", v17);
  if ( v5 >= 0 )
  {
    phkResult[0] = 0;
    v6 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x10u, phkResult);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v15 = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x10u, &v15);
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 < 0 )
    {
      if ( v5 < 0 )
      {
LABEL_22:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
        goto LABEL_23;
      }
      v12 = *v2;
      if ( *v2 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v14);
        RegCloseKey(v12);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
      }
      v11 = v15;
    }
    else
    {
      v9 = v5 < 0;
      v10 = *v2;
      if ( !v9 )
      {
        if ( v10 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v14);
          RegCloseKey(v10);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
        }
        *v2 = 0;
        v11 = (HKEY)*((_QWORD *)this + 4);
        goto LABEL_21;
      }
      if ( v10 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v14);
        RegCloseKey(v10);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
      }
      v11 = phkResult[0];
    }
    *v2 = 0;
LABEL_21:
    v5 = SHRegDuplicateKey(v11, 16, v2);
    goto LABEL_22;
  }
LABEL_23:
  if ( *v2 )
    return (unsigned int)SHRegDuplicateKey(*v2, 16, a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001f8a0  mov     [rsp-8+arg_10], rbx
0x18001f8a5  mov     [rsp-8+arg_18], rsi
0x18001f8aa  push    rbp
0x18001f8ab  push    rdi
0x18001f8ac  push    r13
0x18001f8ae  push    r14
0x18001f8b0  push    r15
0x18001f8b2  lea     rbp, [rsp-1B0h]
0x18001f8ba  sub     rsp, 2B0h
0x18001f8c1  mov     rax, cs:__security_cookie
0x18001f8c8  xor     rax, rsp
0x18001f8cb  mov     [rbp+1D0h+var_30], rax
0x18001f8d2  lea     rdi, [rcx+50h]
0x18001f8d6  mov     qword ptr [rdx], 0
0x18001f8dd  cmp     qword ptr [rdi], 0
0x18001f8e1  mov     r15, rdx
0x18001f8e4  mov     r14, rcx
0x18001f8e7  mov     r13d, 10h
0x18001f8ed  jz      short loc_18001F8F9
0x18001f8ef  mov     ebx, 8000FFFFh
0x18001f8f4  jmp     loc_18001FA5D
0x18001f8f9  add     rcx, 28h ; '('
0x18001f8fd  lea     rdx, [rsp+2D0h+var_280]
0x18001f902  mov     r8d, 27h ; '''
0x18001f908  call    cs:__imp_SHStringFromGUIDW
0x18001f90e  lea     r9, [rsp+2D0h+var_280]
0x18001f913  mov     edx, 0FFh; unsigned __int64
0x18001f918  lea     r8, aSoftwareClasse; "Software\\Classes\\CLSID\\%ls\\Instance"
0x18001f91f  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x18001f923  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f928  mov     ebx, eax
0x18001f92a  test    eax, eax
0x18001f92c  js      loc_18001FA5D
0x18001f932  lea     rax, [rsp+2D0h+var_290]
0x18001f937  mov     [rsp+2D0h+var_290], 0
0x18001f940  mov     r9d, r13d; samDesired
0x18001f943  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18001f948  xor     r8d, r8d; ulOptions
0x18001f94b  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18001f94f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001f956  call    cs:__imp_RegOpenKeyExW
0x18001f95c  mov     esi, eax
0x18001f95e  test    eax, eax
0x18001f960  jle     short loc_18001F96B
0x18001f962  movzx   esi, ax
0x18001f965  or      esi, 80070000h
0x18001f96b  lea     rax, [rsp+2D0h+var_298]
0x18001f970  mov     [rsp+2D0h+var_298], 0
0x18001f979  mov     r9d, r13d; samDesired
0x18001f97c  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18001f981  xor     r8d, r8d; ulOptions
0x18001f984  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18001f988  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f98f  call    cs:__imp_RegOpenKeyExW
0x18001f995  mov     ebx, eax
0x18001f997  test    eax, eax
0x18001f999  jle     short loc_18001F9A4
0x18001f99b  movzx   ebx, ax
0x18001f99e  or      ebx, 80070000h
0x18001f9a4  test    esi, esi
0x18001f9a6  js      short loc_18001FA07
0x18001f9a8  test    ebx, ebx
0x18001f9aa  mov     rbx, [rdi]
0x18001f9ad  js      short loc_18001F9DE
0x18001f9af  test    rbx, rbx
0x18001f9b2  jz      short loc_18001F9D1
0x18001f9b4  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18001f9b9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001f9be  mov     rcx, rbx; hKey
0x18001f9c1  call    cs:__imp_RegCloseKey
0x18001f9c7  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18001f9cc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001f9d1  mov     qword ptr [rdi], 0
0x18001f9d8  mov     rcx, [r14+20h]
0x18001f9dc  jmp     short loc_18001FA3C
0x18001f9de  test    rbx, rbx
0x18001f9e1  jz      short loc_18001FA00
0x18001f9e3  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18001f9e8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001f9ed  mov     rcx, rbx; hKey
0x18001f9f0  call    cs:__imp_RegCloseKey
0x18001f9f6  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18001f9fb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001fa00  mov     rcx, [rsp+2D0h+var_290]
0x18001fa05  jmp     short loc_18001FA35
0x18001fa07  test    ebx, ebx
0x18001fa09  js      short loc_18001FA49
0x18001fa0b  mov     rbx, [rdi]
0x18001fa0e  test    rbx, rbx
0x18001fa11  jz      short loc_18001FA30
0x18001fa13  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18001fa18  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001fa1d  mov     rcx, rbx; hKey
0x18001fa20  call    cs:__imp_RegCloseKey
0x18001fa26  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18001fa2b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001fa30  mov     rcx, [rsp+2D0h+var_298]
0x18001fa35  mov     qword ptr [rdi], 0
0x18001fa3c  mov     r8, rdi
0x18001fa3f  mov     edx, r13d
0x18001fa42  call    SHRegDuplicateKey
0x18001fa47  mov     ebx, eax
0x18001fa49  lea     rcx, [rsp+2D0h+var_298]
0x18001fa4e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fa53  lea     rcx, [rsp+2D0h+var_290]
0x18001fa58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fa5d  mov     rcx, [rdi]
0x18001fa60  test    rcx, rcx
0x18001fa63  jz      short loc_18001FA72
0x18001fa65  mov     r8, r15
0x18001fa68  mov     edx, r13d
0x18001fa6b  call    SHRegDuplicateKey
0x18001fa70  mov     ebx, eax
0x18001fa72  mov     eax, ebx
0x18001fa74  mov     rcx, [rbp+1D0h+var_30]
0x18001fa7b  xor     rcx, rsp; StackCookie
0x18001fa7e  call    __security_check_cookie
0x18001fa83  lea     r11, [rsp+2D0h+var_20]
0x18001fa8b  mov     rbx, [r11+40h]
0x18001fa8f  mov     rsi, [r11+48h]
0x18001fa93  mov     rsp, r11
0x18001fa96  pop     r15
0x18001fa98  pop     r14
0x18001fa9a  pop     r13
0x18001fa9c  pop     rdi
0x18001fa9d  pop     rbp
0x18001fa9e  retn
```
