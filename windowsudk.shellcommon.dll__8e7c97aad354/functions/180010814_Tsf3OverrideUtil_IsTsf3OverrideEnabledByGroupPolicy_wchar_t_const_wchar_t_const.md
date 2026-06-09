# Tsf3OverrideUtil::IsTsf3OverrideEnabledByGroupPolicy(wchar_t const *,wchar_t const *)

- ea: `0x180010814`
- end: `0x180010939`
- name: `?IsTsf3OverrideEnabledByGroupPolicy@Tsf3OverrideUtil@@YA?AW4PolicyStatus@1@PEB_W0@Z`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800461d8`

## callees

- `0x18000fea0`
- `0x180010814`
- `0x180010940`
- `0x1803c3710`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010875`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010875`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800108fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800108fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010897`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010897`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180010845`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180010845`

## pseudocode

```c
__int64 __fastcall Tsf3OverrideUtil::IsTsf3OverrideEnabledByGroupPolicy(const WCHAR *a1, const WCHAR *a2)
{
  HKEY *v4; // rax
  unsigned int v5; // eax
  HKEY *v6; // rax
  BOOL v8; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  HKEY v11; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  DWORD Type; // [rsp+70h] [rbp+20h] BYREF
  int Data; // [rsp+78h] [rbp+28h] BYREF

  hKey[0] = 0;
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  v5 = RegOpenCurrentUser(0x20019u, v4);
  if ( v5 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\internal\\shell\\inc\\Tsf3OverrideUtil.h",
      (const char *)v5,
      phkResult);
  }
  else
  {
    v11 = 0;
    v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v11);
    if ( !RegOpenKeyExW(hKey[0], a1, 0, 0x20019u, v6) )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(v11, a2, 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      {
        v8 = Data != 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
        return (unsigned int)(v8 + 1);
      }
    }
    if ( v11 )
      RegCloseKey(v11);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return 0;
}

```

## disassembly

```asm
0x180010814  mov     [rsp-8+arg_0], rbx
0x180010819  mov     [rsp-8+arg_8], rdi
0x18001081e  push    rbp
0x18001081f  mov     rbp, rsp
0x180010822  sub     rsp, 50h
0x180010826  mov     rdi, rcx
0x180010829  mov     [rbp+hKey], 0
0x180010831  lea     rcx, [rbp+hKey]
0x180010835  mov     rbx, rdx
0x180010838  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001083d  mov     rdx, rax; phkResult
0x180010840  mov     ecx, 20019h; samDesired
0x180010845  call    cs:__imp_RegOpenCurrentUser
0x18001084b  test    eax, eax
0x18001084d  jnz     short loc_1800108AF
0x18001084f  lea     rcx, [rbp+var_18]
0x180010853  mov     [rbp+var_18], 0
0x18001085b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180010860  mov     rcx, [rbp+hKey]; hKey
0x180010864  mov     r9d, 20019h; samDesired
0x18001086a  xor     r8d, r8d; ulOptions
0x18001086d  mov     [rsp+50h+phkResult], rax; phkResult
0x180010872  mov     rdx, rdi; lpSubKey
0x180010875  call    cs:__imp_RegOpenKeyExW
0x18001087b  test    eax, eax
0x18001087d  jz      short loc_1800108C9
0x18001087f  mov     rcx, [rbp+var_18]; hKey
0x180010883  test    rcx, rcx
0x180010886  jz      short loc_18001088E
0x180010888  call    cs:__imp_RegCloseKey
0x18001088e  mov     rcx, [rbp+hKey]; hKey
0x180010892  test    rcx, rcx
0x180010895  jz      short loc_18001089D
0x180010897  call    cs:__imp_RegCloseKey
0x18001089d  xor     eax, eax
0x18001089f  mov     rbx, [rsp+50h+arg_0]
0x1800108a4  mov     rdi, [rsp+50h+arg_8]
0x1800108a9  add     rsp, 50h
0x1800108ad  pop     rbp
0x1800108ae  retn
0x1800108af  mov     rcx, [rbp+8]; this
0x1800108b3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\Tsf3Over"...
0x1800108ba  mov     r9d, eax; char *
0x1800108bd  mov     edx, 0FCh; void *
0x1800108c2  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800108c7  jmp     short loc_18001088E
0x1800108c9  mov     rcx, [rbp+var_18]; hKey
0x1800108cd  lea     rax, [rbp+cbData]
0x1800108d1  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800108d6  lea     r9, [rbp+Type]; lpType
0x1800108da  lea     rax, [rbp+Data]
0x1800108de  mov     [rbp+Type], 0
0x1800108e5  xor     r8d, r8d; lpReserved
0x1800108e8  mov     [rsp+50h+phkResult], rax; lpData
0x1800108ed  mov     rdx, rbx; lpValueName
0x1800108f0  mov     [rbp+Data], 0
0x1800108f7  mov     [rbp+cbData], 4
0x1800108fe  call    cs:__imp_RegQueryValueExW
0x180010904  test    eax, eax
0x180010906  jnz     loc_18001087F
0x18001090c  cmp     [rbp+Type], 4
0x180010910  jnz     loc_18001087F
0x180010916  mov     eax, [rbp+Data]
0x180010919  lea     rcx, [rbp+var_18]
0x18001091d  neg     eax
0x18001091f  sbb     ebx, ebx
0x180010921  neg     ebx
0x180010923  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010928  lea     rcx, [rbp+hKey]
0x18001092c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010931  lea     eax, [rbx+1]
0x180010934  jmp     loc_18001089F
```
