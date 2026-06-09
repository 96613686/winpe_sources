# WwanSvcUpdated(_GUID &)

- ea: `0x1800636b4`
- end: `0x1800638a0`
- name: `?WwanSvcUpdated@@YAHAEAU_GUID@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005d40c`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x18000f068`
- `0x180013288`
- `0x180013588`
- `0x18001375c`
- `0x180014154`
- `0x18006132c`
- `0x1800636b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800636f9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800636f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800637a3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800637a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063864`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063864`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800637ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800637ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180063859`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180063859`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180063714`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180063714`

## string_xrefs

- `0x18006371a`: `\wwansvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WwanSvcUpdated(GUID *rguid)
{
  unsigned int v2; // ebx
  const WCHAR *v3; // rax
  __int64 v5; // rax
  BYTE *v6; // rcx
  __int64 v7; // rax
  int v8; // r8d
  int v9; // edx
  const BYTE *v10; // rax
  DWORD v11; // r8d
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v14[16]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v15[32]; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[64]; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR sz[48]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pszPath[264]; // [rsp+140h] [rbp+40h] BYREF

  memset_0(sz, 0, 0x5Eu);
  StringFromGUID2(rguid, sz, 47);
  SHGetFolderPathW(0, 37, 0, 0, pszPath);
  StringCchCatW(pszPath, 0x105u, L"\\wwansvc.dll");
  std::wstring::wstring((__int64)v15, (__int64)L"Software\\Microsoft\\WwanSvc\\");
  std::wstring::append(v15, sz);
  cbData = 50;
  GetWwanSvcVer(v14, pszPath);
  v2 = 0;
  hKey = 0;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0xF013Fu, 0, &hKey, 0) )
  {
    std::wstring::_Tidy_deallocate(v14);
    std::wstring::_Tidy_deallocate(v15);
    return 0;
  }
  else
  {
    if ( RegQueryValueExW(hKey, L"Version", 0, 0, Data, &cbData) )
      goto LABEL_8;
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
    v6 = Data;
    v7 = v5 - (_QWORD)Data;
    do
    {
      v8 = *(unsigned __int16 *)&v6[v7];
      v9 = *(unsigned __int16 *)v6 - v8;
      if ( v9 )
        break;
      v6 += 2;
    }
    while ( v8 );
    if ( v9 )
    {
LABEL_8:
      v10 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
      v2 = 1;
      RegSetValueExW(hKey, L"Version", 0, 1u, v10, v11);
    }
    RegCloseKey(hKey);
    std::wstring::_Tidy_deallocate(v14);
    std::wstring::_Tidy_deallocate(v15);
    return v2;
  }
}

```

## disassembly

```asm
0x1800636b4  mov     [rsp-8+arg_8], rbx
0x1800636b9  push    rbp
0x1800636ba  lea     rbp, [rsp-260h]
0x1800636c2  sub     rsp, 360h
0x1800636c9  mov     rax, cs:__security_cookie
0x1800636d0  xor     rax, rsp
0x1800636d3  mov     [rbp+260h+var_10], rax
0x1800636da  mov     rbx, rcx
0x1800636dd  xor     edx, edx; Val
0x1800636df  lea     r8d, [rdx+5Eh]; Size
0x1800636e3  lea     rcx, [rbp+260h+sz]; void *
0x1800636e7  call    memset_0
0x1800636ec  mov     r8d, 2Fh ; '/'; cchMax
0x1800636f2  lea     rdx, [rbp+260h+sz]; lpsz
0x1800636f6  mov     rcx, rbx; rguid
0x1800636f9  call    cs:__imp_StringFromGUID2
0x1800636ff  lea     rax, [rbp+260h+var_220]
0x180063703  mov     [rsp+360h+pszPath], rax; pszPath
0x180063708  xor     r9d, r9d; dwFlags
0x18006370b  xor     r8d, r8d; hToken
0x18006370e  lea     edx, [r9+25h]; csidl
0x180063712  xor     ecx, ecx; hwnd
0x180063714  call    cs:__imp_SHGetFolderPathW
0x18006371a  lea     r8, aWwansvcDll_0; "\\wwansvc.dll"
0x180063721  mov     edx, 105h; unsigned __int64
0x180063726  lea     rcx, [rbp+260h+var_220]; unsigned __int16 *
0x18006372a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006372f  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\WwanSvc\\"
0x180063736  lea     rcx, [rbp+260h+var_2E0]
0x18006373a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006373f  nop
0x180063740  lea     rdx, [rbp+260h+sz]
0x180063744  lea     rcx, [rbp+260h+var_2E0]
0x180063748  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18006374d  mov     [rsp+360h+cbData], 32h ; '2'
0x180063755  lea     rdx, [rbp+260h+var_220]
0x180063759  lea     rcx, [rsp+360h+var_300]
0x18006375e  call    ?GetWwanSvcVer@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG@Z; GetWwanSvcVer(ushort *)
0x180063763  xor     ebx, ebx
0x180063765  mov     [rsp+360h+hKey], rbx
0x18006376a  lea     rcx, [rbp+260h+var_2E0]
0x18006376e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063773  mov     rdx, rax; lpSubKey
0x180063776  mov     [rsp+360h+lpdwDisposition], rbx; lpdwDisposition
0x18006377b  lea     rax, [rsp+360h+hKey]
0x180063780  mov     [rsp+360h+phkResult], rax; phkResult
0x180063785  mov     [rsp+360h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18006378a  mov     [rsp+360h+samDesired], 0F013Fh; samDesired
0x180063792  mov     dword ptr [rsp+360h+pszPath], ebx; dwOptions
0x180063796  xor     r9d, r9d; lpClass
0x180063799  xor     r8d, r8d; Reserved
0x18006379c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800637a3  call    cs:__imp_RegCreateKeyExW
0x1800637a9  test    eax, eax
0x1800637ab  jz      short loc_1800637C8
0x1800637ad  lea     rcx, [rsp+360h+var_300]
0x1800637b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800637b7  nop
0x1800637b8  lea     rcx, [rbp+260h+var_2E0]
0x1800637bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800637c1  xor     eax, eax
0x1800637c3  jmp     loc_180063880
0x1800637c8  lea     rax, [rsp+360h+cbData]
0x1800637cd  mov     qword ptr [rsp+360h+samDesired], rax; lpcbData
0x1800637d2  lea     rax, [rbp+260h+Data]
0x1800637d6  mov     [rsp+360h+pszPath], rax; lpData
0x1800637db  xor     r9d, r9d; lpType
0x1800637de  xor     r8d, r8d; lpReserved
0x1800637e1  lea     rdx, aVersion; "Version"
0x1800637e8  mov     rcx, [rsp+360h+hKey]; hKey
0x1800637ed  call    cs:__imp_RegQueryValueExW
0x1800637f3  test    eax, eax
0x1800637f5  jnz     short loc_180063822
0x1800637f7  lea     rcx, [rsp+360h+var_300]
0x1800637fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063801  lea     rcx, [rbp+260h+Data]
0x180063805  sub     rax, rcx
0x180063808  movzx   edx, word ptr [rcx]
0x18006380b  movzx   r8d, word ptr [rcx+rax]
0x180063810  sub     edx, r8d
0x180063813  jnz     short loc_18006381E
0x180063815  add     rcx, 2
0x180063819  test    r8d, r8d
0x18006381c  jnz     short loc_180063808
0x18006381e  test    edx, edx
0x180063820  jz      short loc_18006385F
0x180063822  mov     eax, [rsp+360h+var_2F0]
0x180063826  lea     r8d, ds:2[rax*2]
0x18006382e  lea     rcx, [rsp+360h+var_300]
0x180063833  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063838  mov     [rsp+360h+samDesired], r8d; cbData
0x18006383d  mov     [rsp+360h+pszPath], rax; lpData
0x180063842  mov     ebx, 1
0x180063847  mov     r9d, ebx; dwType
0x18006384a  xor     r8d, r8d; Reserved
0x18006384d  lea     rdx, aVersion; "Version"
0x180063854  mov     rcx, [rsp+360h+hKey]; hKey
0x180063859  call    cs:__imp_RegSetValueExW
0x18006385f  mov     rcx, [rsp+360h+hKey]; hKey
0x180063864  call    cs:__imp_RegCloseKey
0x18006386a  lea     rcx, [rsp+360h+var_300]
0x18006386f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063874  nop
0x180063875  lea     rcx, [rbp+260h+var_2E0]
0x180063879  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006387e  mov     eax, ebx
0x180063880  mov     rcx, [rbp+260h+var_10]
0x180063887  xor     rcx, rsp; StackCookie
0x18006388a  call    __security_check_cookie
0x18006388f  mov     rbx, [rsp+360h+arg_8]
0x180063897  add     rsp, 360h
0x18006389e  pop     rbp
0x18006389f  retn
```
