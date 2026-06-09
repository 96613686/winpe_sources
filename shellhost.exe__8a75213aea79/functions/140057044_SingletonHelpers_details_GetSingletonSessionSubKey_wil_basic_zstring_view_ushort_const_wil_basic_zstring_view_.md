# SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &,ulong)

- ea: `0x140057044`
- end: `0x14005713d`
- name: `?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@0K@Z`
- size: `249`
- prototype: `HKEY *__fastcall(HKEY *, __int64 *, HKEY *, REGSAM)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x140006ab0`
- `0x14000ab88`
- `0x140054d44`
- `0x14005ad28`
- `0x14005b34c`
- `0x14005bd30`

## callees

- `0x14005124c`
- `0x140052fe0`
- `0x140053000`
- `0x140054e24`
- `0x140057044`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400570ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400570ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400570df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400570df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY *__fastcall SingletonHelpers::details::GetSingletonSessionSubKey(HKEY *a1, __int64 *a2, HKEY *a3, REGSAM a4)
{
  unsigned int v6; // ecx
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-18h] BYREF
  __int64 v9; // [rsp+60h] [rbp-10h] BYREF
  const wchar_t *v10; // [rsp+68h] [rbp-8h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+20h] BYREF

  phkResult = *a3;
  v9 = *a2;
  v10 = L"Singletons";
  wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short const (&)[2],unsigned short const *,unsigned short const (&)[2],unsigned short const *>(
    (unsigned int)&lpSubKey,
    (unsigned int)&v10,
    (_DWORD)a3,
    (unsigned int)&v9);
  hKey = 0;
  if ( CreateShellSessionKey(v6, &hKey) < 0 )
  {
    *a1 = 0;
  }
  else
  {
    phkResult = 0;
    if ( (a4 & 6) != 0 )
      RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, a4, 0, &phkResult, 0);
    else
      RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
    *a1 = phkResult;
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
  return a1;
}

```

## disassembly

```asm
0x140057044  mov     [rsp-8+arg_0], rbx
0x140057049  mov     [rsp-8+arg_18], rdi
0x14005704e  push    rbp
0x14005704f  mov     rbp, rsp
0x140057052  sub     rsp, 70h
0x140057056  mov     rax, [r8]
0x140057059  mov     edi, r9d
0x14005705c  mov     [rbp+arg_8], rax
0x140057060  lea     r9, [rbp+var_10]
0x140057064  mov     rax, [rdx]
0x140057067  mov     rbx, rcx
0x14005706a  mov     [rbp+var_10], rax
0x14005706e  lea     rdx, [rbp+var_8]
0x140057072  mov     rax, cs:off_14006A550; "Singletons"
0x140057079  lea     rcx, [rbp+lpSubKey]
0x14005707d  mov     [rbp+var_8], rax
0x140057081  lea     rax, [rbp+arg_8]
0x140057085  mov     qword ptr [rsp+70h+samDesired], rax
0x14005708a  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGAEAY01$$CBGPEBGAEAY01$$CBGPEBG@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@$$QEAPEBGAEAY01$$CBG010@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const *,ushort const (&)[2],ushort const *,ushort const (&)[2],ushort const *>(ushort const * &&,ushort const (&)[2],ushort const * &&,ushort const (&)[2],ushort const * &&)
0x14005708f  lea     rdx, [rbp+hKey]; HKEY *
0x140057093  mov     [rbp+hKey], 0
0x14005709b  call    ?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z; CreateShellSessionKey(ulong,HKEY__ * *)
0x1400570a0  test    eax, eax
0x1400570a2  js      short loc_14005710F
0x1400570a4  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1400570a8  lea     rax, [rbp+arg_8]
0x1400570ac  mov     rcx, [rbp+hKey]; hKey
0x1400570b0  xor     r8d, r8d; ulOptions
0x1400570b3  mov     [rbp+arg_8], 0
0x1400570bb  test    dil, 6
0x1400570bf  jz      short loc_1400570E7
0x1400570c1  mov     [rsp+70h+lpdwDisposition], r8; lpdwDisposition
0x1400570c6  xor     r9d, r9d; lpClass
0x1400570c9  mov     [rsp+70h+phkResult], rax; phkResult
0x1400570ce  mov     [rsp+70h+lpSecurityAttributes], r8; lpSecurityAttributes
0x1400570d3  mov     [rsp+70h+samDesired], edi; samDesired
0x1400570d7  mov     [rsp+70h+dwOptions], 1; dwOptions
0x1400570df  call    cs:__imp_RegCreateKeyExW
0x1400570e5  jmp     short loc_1400570F5
0x1400570e7  mov     r9d, edi; samDesired
0x1400570ea  mov     qword ptr [rsp+70h+dwOptions], rax; phkResult
0x1400570ef  call    cs:__imp_RegOpenKeyExW
0x1400570f5  mov     rax, [rbp+arg_8]
0x1400570f9  lea     rcx, [rbp+arg_8]
0x1400570fd  mov     [rbx], rax
0x140057100  mov     [rbp+arg_8], 0
0x140057108  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14005710d  jmp     short loc_140057116
0x14005710f  mov     qword ptr [rbx], 0
0x140057116  lea     rcx, [rbp+hKey]
0x14005711a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14005711f  lea     rcx, [rbp+lpSubKey]
0x140057123  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140057128  lea     r11, [rsp+70h+var_s0]
0x14005712d  mov     rax, rbx
0x140057130  mov     rbx, [r11+10h]
0x140057134  mov     rdi, [r11+28h]
0x140057138  mov     rsp, r11
0x14005713b  pop     rbp
0x14005713c  retn
```
