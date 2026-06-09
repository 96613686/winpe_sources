# GetSystemApplicationDataKey(HSTRING__ *,HKEY__ * *)

- ea: `0x180066cfc`
- end: `0x180066eb2`
- name: `?GetSystemApplicationDataKey@@YAJPEAUHSTRING__@@PEAPEAUHKEY__@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(HSTRING, HKEY *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180064140`
- `0x180065450`
- `0x18007da9c`
- `0x1800d7608`

## callees

- `0x180004f08`
- `0x180010c04`
- `0x18001d10c`
- `0x180066cfc`
- `0x180066eb8`
- `0x180066ed8`
- `0x180067258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066d88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066e19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066e19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066d10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066e68`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180066d20`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180066d20`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180066d48`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180066dc2`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180066d48`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180066dc2`

## string_xrefs

- `0x180066d56`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180066dd0`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180066e27`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180066e76`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetSystemApplicationDataKey(HSTRING a1, HKEY *a2)
{
  PCWSTR StringRawBuffer; // rax
  WCHAR *v5; // rbx
  const char *v6; // r9
  unsigned int LastError; // edi
  unsigned int v8; // eax
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v15; // [rsp+80h] [rbp+30h] BYREF
  HKEY v16; // [rsp+88h] [rbp+38h] BYREF

  StringRawBuffer = WindowsGetStringRawBuffer(a1, 0);
  hKey = 0;
  v12 = OpenStateExplicit(-4, StringRawBuffer);
  v15 = 0;
  if ( (unsigned int)GetSystemAppDataKey(v12, 0, 0, &v15) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v12);
    return 2147549183LL;
  }
  if ( GetLastError() == 122 && v15 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      pv,
      0,
      v15);
    v5 = (WCHAR *)pv[0];
    if ( (unsigned int)GetSystemAppDataKey(v12, &hKey, pv[0], &v15) )
    {
      v16 = 0;
      v8 = RegOpenKeyExW(hKey, v5, 0, 0x20019u, &v16);
      if ( !v8 )
      {
        *a2 = v16;
        v16 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
        if ( v5 )
          CoTaskMemFree(v5);
        LastError = 0;
        goto LABEL_15;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x40,
                    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
                    (const char *)v8,
                    phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3D,
                    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
                    v6);
    }
    if ( v5 )
      CoTaskMemFree(v5);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      phkResult);
    LastError = -2147418113;
  }
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v12);
  return LastError;
}

```

## disassembly

```asm
0x180066cfc  mov     [rsp-18h+arg_0], rbx
0x180066d01  push    rbp
0x180066d02  push    rsi
0x180066d03  push    rdi
0x180066d04  mov     rbp, rsp
0x180066d07  sub     rsp, 50h
0x180066d0b  mov     rsi, rdx
0x180066d0e  xor     edx, edx; length
0x180066d10  call    cs:__imp_WindowsGetStringRawBuffer
0x180066d16  mov     rdx, rax
0x180066d19  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x180066d20  call    cs:__imp_OpenStateExplicit
0x180066d26  lea     r9, [rbp+arg_10]
0x180066d2a  mov     [rbp+hKey], 0
0x180066d32  mov     rcx, rax
0x180066d35  mov     [rbp+var_18], rax
0x180066d39  xor     r8d, r8d
0x180066d3c  mov     [rbp+arg_10], 0
0x180066d43  xor     edx, edx
0x180066d45  mov     rdi, rax
0x180066d48  call    cs:__imp_GetSystemAppDataKey
0x180066d4e  test    eax, eax
0x180066d50  jz      short loc_180066D88
0x180066d52  mov     rcx, [rbp+18h]; this
0x180066d56  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066d5d  mov     ebx, 8000FFFFh
0x180066d62  mov     edx, 38h ; '8'; void *
0x180066d67  mov     r9d, ebx; char *
0x180066d6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066d6f  lea     rcx, [rbp+hKey]
0x180066d73  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180066d78  lea     rcx, [rbp+var_18]
0x180066d7c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180066d81  mov     eax, ebx
0x180066d83  jmp     loc_180066EA5
0x180066d88  call    cs:__imp_GetLastError
0x180066d8e  cmp     eax, 7Ah ; 'z'
0x180066d91  jnz     loc_180066E72
0x180066d97  mov     eax, [rbp+arg_10]
0x180066d9a  test    eax, eax
0x180066d9c  jz      loc_180066E72
0x180066da2  mov     r8d, eax
0x180066da5  lea     rcx, [rbp+pv]
0x180066da9  xor     edx, edx
0x180066dab  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180066db0  mov     rbx, [rbp+pv]
0x180066db4  lea     r9, [rbp+arg_10]
0x180066db8  mov     r8, rbx
0x180066dbb  lea     rdx, [rbp+hKey]
0x180066dbf  mov     rcx, rdi
0x180066dc2  call    cs:__imp_GetSystemAppDataKey
0x180066dc8  test    eax, eax
0x180066dca  jnz     short loc_180066DF8
0x180066dcc  mov     rcx, [rbp+18h]; this
0x180066dd0  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066dd7  lea     edx, [rax+3Dh]; void *
0x180066dda  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180066ddf  mov     edi, eax
0x180066de1  test    rbx, rbx
0x180066de4  jz      loc_180066E91
0x180066dea  mov     rcx, rbx; pv
0x180066ded  call    cs:__imp_CoTaskMemFree
0x180066df3  jmp     loc_180066E91
0x180066df8  mov     rcx, [rbp+hKey]; hKey
0x180066dfc  lea     rax, [rbp+arg_18]
0x180066e00  mov     r9d, 20019h; samDesired
0x180066e06  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x180066e0b  xor     r8d, r8d; ulOptions
0x180066e0e  mov     [rbp+arg_18], 0
0x180066e16  mov     rdx, rbx; lpSubKey
0x180066e19  call    cs:__imp_RegOpenKeyExW
0x180066e1f  test    eax, eax
0x180066e21  jz      short loc_180066E48
0x180066e23  mov     rcx, [rbp+18h]; this
0x180066e27  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066e2e  mov     r9d, eax; char *
0x180066e31  mov     edx, 40h ; '@'; void *
0x180066e36  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180066e3b  lea     rcx, [rbp+arg_18]
0x180066e3f  mov     edi, eax
0x180066e41  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180066e46  jmp     short loc_180066DE1
0x180066e48  mov     rax, [rbp+arg_18]
0x180066e4c  lea     rcx, [rbp+arg_18]
0x180066e50  mov     [rsi], rax
0x180066e53  mov     [rbp+arg_18], 0
0x180066e5b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180066e60  test    rbx, rbx
0x180066e63  jz      short loc_180066E6E
0x180066e65  mov     rcx, rbx; pv
0x180066e68  call    cs:__imp_CoTaskMemFree
0x180066e6e  xor     edi, edi
0x180066e70  jmp     short loc_180066E91
0x180066e72  mov     rcx, [rbp+18h]; this
0x180066e76  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180066e7d  mov     ebx, 8000FFFFh
0x180066e82  mov     edx, 3Ah ; ':'; void *
0x180066e87  mov     r9d, ebx; char *
0x180066e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066e8f  mov     edi, ebx
0x180066e91  lea     rcx, [rbp+hKey]
0x180066e95  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180066e9a  lea     rcx, [rbp+var_18]
0x180066e9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180066ea3  mov     eax, edi
0x180066ea5  mov     rbx, [rsp+50h+arg_0]
0x180066eaa  add     rsp, 50h
0x180066eae  pop     rdi
0x180066eaf  pop     rsi
0x180066eb0  pop     rbp
0x180066eb1  retn
```
