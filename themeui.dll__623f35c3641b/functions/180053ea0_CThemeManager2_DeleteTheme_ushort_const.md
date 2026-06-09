# CThemeManager2::DeleteTheme(ushort const *)

- ea: `0x180053ea0`
- end: `0x180054067`
- name: `?DeleteTheme@CThemeManager2@@UEAAJPEBG@Z`
- size: `455`
- prototype: `int(CThemeManager2 *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180053ea0`
- `0x180060374`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180053ecd`
- `SHELL32!SHCreateItemFromParsingName` at `0x180053ecd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053f45`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053f45`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005402f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005402f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054039`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005401e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005401e`
- `USER32!SendNotifyMessageW` at `0x180053fbf`
- `USER32!SendNotifyMessageW` at `0x180053fbf`

## string_xrefs

- `0x180054010`: `Software\Microsoft\Windows\CurrentVersion\Themes\InstalledThemes\SQM`

## pseudocode

```c
__int64 __fastcall CThemeManager2::DeleteTheme(CThemeManager2 *this, const unsigned __int16 *a2)
{
  HRESULT Instance; // ebx
  void *v5; // rcx
  __int64 result; // rax
  void *ppv; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  void *v9; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  Instance = SHCreateItemFromParsingName(a2, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( Instance < 0 )
    goto LABEL_19;
  v9 = 0;
  if ( !IsThemePack(a2) )
  {
    v9 = ppv;
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 8LL))(ppv);
    goto LABEL_6;
  }
  Instance = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)ppv + 32LL))(ppv, &v9);
  if ( Instance >= 0 )
  {
LABEL_6:
    hKey = 0;
    Instance = CoCreateInstance(
                 &CLSID_FileOperation,
                 0,
                 1u,
                 &GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8,
                 (LPVOID *)&hKey);
    if ( Instance >= 0 )
    {
      if ( *((_BYTE *)this + 2361) )
        (*(void (__fastcall **)(HKEY, __int64))(*(_QWORD *)hKey + 40LL))(hKey, 1556);
      Instance = (*(__int64 (__fastcall **)(HKEY, void *, _QWORD))(*(_QWORD *)hKey + 144LL))(hKey, v9, 0);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)hKey + 168LL))(hKey);
        if ( Instance >= 0 )
          SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"WindowsThemeElement");
      }
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
    }
    v5 = v9;
    v9 = 0;
    if ( v5 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    if ( Instance >= 0 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\InstalledThemes\\SQM",
              0,
              0x20006u,
              &hKey) )
      {
        RegDeleteValueW(hKey, a2);
        RegCloseKey(hKey);
      }
    }
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_19:
  result = 0;
  if ( Instance != -2144927744 )
    return (unsigned int)Instance;
  return result;
}

```

## disassembly

```asm
0x180053ea0  mov     [rsp-18h+arg_0], rbx
0x180053ea5  push    rbp
0x180053ea6  push    rsi
0x180053ea7  push    rdi
0x180053ea8  mov     rbp, rsp
0x180053eab  sub     rsp, 40h
0x180053eaf  mov     rdi, rdx
0x180053eb2  mov     [rbp+ppv], 0
0x180053eba  mov     rsi, rcx
0x180053ebd  lea     r9, [rbp+ppv]; ppv
0x180053ec1  mov     rcx, rdi; pszPath
0x180053ec4  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180053ecb  xor     edx, edx; pbc
0x180053ecd  call    cs:__imp_SHCreateItemFromParsingName
0x180053ed3  mov     ebx, eax
0x180053ed5  test    eax, eax
0x180053ed7  js      loc_18005404F
0x180053edd  mov     rcx, rdi; unsigned __int16 *
0x180053ee0  mov     [rbp+arg_18], 0
0x180053ee8  call    ?IsThemePack@@YA_NPEBG@Z; IsThemePack(ushort const *)
0x180053eed  mov     rcx, [rbp+ppv]
0x180053ef1  test    al, al
0x180053ef3  jz      short loc_180053F10
0x180053ef5  mov     rax, [rcx]
0x180053ef8  lea     rdx, [rbp+arg_18]
0x180053efc  mov     rax, [rax+20h]
0x180053f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f05  mov     ebx, eax
0x180053f07  test    eax, eax
0x180053f09  jns     short loc_180053F20
0x180053f0b  jmp     loc_18005403F
0x180053f10  mov     [rbp+arg_18], rcx
0x180053f14  mov     rax, [rcx]
0x180053f17  mov     rax, [rax+8]
0x180053f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f20  xor     edx, edx; pUnkOuter
0x180053f22  mov     [rbp+hKey], 0
0x180053f2a  lea     rax, [rbp+hKey]
0x180053f2e  lea     r9, _GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8; riid
0x180053f35  mov     [rsp+40h+phkResult], rax; ppv
0x180053f3a  lea     rcx, CLSID_FileOperation; rclsid
0x180053f41  lea     r8d, [rdx+1]; dwClsContext
0x180053f45  call    cs:__imp_CoCreateInstance
0x180053f4b  mov     ebx, eax
0x180053f4d  test    eax, eax
0x180053f4f  js      loc_180053FD5
0x180053f55  cmp     byte ptr [rsi+939h], 0
0x180053f5c  jz      short loc_180053F73
0x180053f5e  mov     rcx, [rbp+hKey]
0x180053f62  mov     edx, 614h
0x180053f67  mov     rax, [rcx]
0x180053f6a  mov     rax, [rax+28h]
0x180053f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f73  mov     rcx, [rbp+hKey]
0x180053f77  xor     r8d, r8d
0x180053f7a  mov     rdx, [rbp+arg_18]
0x180053f7e  mov     rax, [rcx]
0x180053f81  mov     rax, [rax+90h]
0x180053f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f8d  mov     ebx, eax
0x180053f8f  test    eax, eax
0x180053f91  js      short loc_180053FC5
0x180053f93  mov     rcx, [rbp+hKey]
0x180053f97  mov     rax, [rcx]
0x180053f9a  mov     rax, [rax+0A8h]
0x180053fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fa6  mov     ebx, eax
0x180053fa8  test    eax, eax
0x180053faa  js      short loc_180053FC5
0x180053fac  xor     r8d, r8d; wParam
0x180053faf  lea     r9, lParam; "WindowsThemeElement"
0x180053fb6  mov     ecx, 0FFFFh; hWnd
0x180053fbb  lea     edx, [r8+1Ah]; Msg
0x180053fbf  call    cs:__imp_SendNotifyMessageW
0x180053fc5  mov     rcx, [rbp+hKey]
0x180053fc9  mov     rax, [rcx]
0x180053fcc  mov     rax, [rax+10h]
0x180053fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fd5  mov     rcx, [rbp+arg_18]
0x180053fd9  mov     [rbp+arg_18], 0
0x180053fe1  test    rcx, rcx
0x180053fe4  jz      short loc_180053FF2
0x180053fe6  mov     rax, [rcx]
0x180053fe9  mov     rax, [rax+10h]
0x180053fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ff2  test    ebx, ebx
0x180053ff4  js      short loc_18005403F
0x180053ff6  lea     rax, [rbp+hKey]
0x180053ffa  mov     [rbp+hKey], 0
0x180054002  mov     r9d, 20006h; samDesired
0x180054008  mov     [rsp+40h+phkResult], rax; phkResult
0x18005400d  xor     r8d, r8d; ulOptions
0x180054010  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180054017  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005401e  call    cs:__imp_RegOpenKeyExW
0x180054024  test    eax, eax
0x180054026  jnz     short loc_18005403F
0x180054028  mov     rcx, [rbp+hKey]; hKey
0x18005402c  mov     rdx, rdi; lpValueName
0x18005402f  call    cs:__imp_RegDeleteValueW
0x180054035  mov     rcx, [rbp+hKey]; hKey
0x180054039  call    cs:__imp_RegCloseKey
0x18005403f  mov     rcx, [rbp+ppv]
0x180054043  mov     rax, [rcx]
0x180054046  mov     rax, [rax+10h]
0x18005404a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005404f  xor     eax, eax
0x180054051  cmp     ebx, 80270000h
0x180054057  cmovnz  eax, ebx
0x18005405a  mov     rbx, [rsp+40h+arg_0]
0x18005405f  add     rsp, 40h
0x180054063  pop     rdi
0x180054064  pop     rsi
0x180054065  pop     rbp
0x180054066  retn
```
