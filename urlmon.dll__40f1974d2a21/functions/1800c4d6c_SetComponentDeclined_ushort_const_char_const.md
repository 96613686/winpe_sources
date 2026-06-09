# SetComponentDeclined(ushort const *,char const *)

- ea: `0x1800c4d6c`
- end: `0x1800c503b`
- name: `?SetComponentDeclined@@YAJPEBGPEBD@Z`
- size: `719`
- prototype: `int(const unsigned __int16 *, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c531c`

## callees

- `0x180030880`
- `0x180058738`
- `0x18005cc10`
- `0x1800763a8`
- `0x1800c4d6c`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800c4e28`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800c4e28`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800c4e4f`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800c4e4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c4dfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c4f55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c4dfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c4f55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c5024`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c5024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4e19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4fbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4e19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4fbd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c4f9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c4f9c`

## string_xrefs

- `0x1800c4dca`: `Software\Microsoft\Windows\CurrentVersion\Internet Settings\Declined Components IE5`

## pseudocode

```c
__int64 __fastcall SetComponentDeclined(const unsigned __int16 *a1, const char *a2)
{
  signed int v3; // ebx
  int v4; // eax
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  char *v8; // [rsp+58h] [rbp-A8h]
  __int64 v9; // [rsp+60h] [rbp-A0h] BYREF
  struct IEUserBroker *v10; // [rsp+68h] [rbp-98h] BYREF
  __int64 v11; // [rsp+70h] [rbp-90h] BYREF
  CHAR SubKey[528]; // [rsp+80h] [rbp-80h] BYREF

  v8 = 0;
  hKey = 0;
  v3 = Unicode2Ansi(a1);
  if ( v3 >= 0 )
  {
    StringCchCopyA(
      SubKey,
      0x208u,
      "Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Declined Components IE5");
    if ( RegOpenKeyExA(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &hKey) )
    {
      v3 = 0;
      goto LABEL_17;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v4 = IsProtectedModeProcess();
    v3 = v4;
    if ( v4 )
    {
      if ( v4 != 1 )
        goto LABEL_17;
      StringCchCatA(SubKey, 0x208u, "\\");
      StringCchCatA(SubKey, 0x208u, v8);
      if ( RegOpenKeyExA(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &hKey)
        && (v5 = RegCreateKeyExA(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0), (v3 = v5) != 0) )
      {
        if ( v5 <= 0 )
          goto LABEL_17;
      }
      else
      {
        v3 = 0;
        v5 = RegSetValueExA(hKey, a2, 0, 1u, &Default, 1u);
        if ( !v5 )
          goto LABEL_17;
        if ( v5 <= 0 )
        {
          v3 = v5;
          goto LABEL_17;
        }
      }
      v3 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_17;
    }
    v11 = 0;
    v10 = 0;
    v3 = CoCreateUserBroker(&v10);
    if ( v3 >= 0 )
    {
      v9 = 0;
      v3 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v10 + 48LL))(
             v10,
             &CLSID_CShdocvwBroker,
             &IID_IUnknown,
             &v9);
      if ( v3 >= 0 )
      {
        v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
               v9,
               &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
               &v11);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, char *, const char *))(*(_QWORD *)v11 + 728LL))(v11, v8, a2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    operator delete(v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800c4d6c  mov     [rsp-8+arg_10], rbx
0x1800c4d71  mov     [rsp-8+arg_18], rsi
0x1800c4d76  push    rbp
0x1800c4d77  push    r12
0x1800c4d79  push    r13
0x1800c4d7b  lea     rbp, [rsp-1A0h]
0x1800c4d83  sub     rsp, 2A0h
0x1800c4d8a  mov     rax, cs:__security_cookie
0x1800c4d91  xor     rax, rsp
0x1800c4d94  mov     [rbp+1B0h+var_20], rax
0x1800c4d9b  mov     rsi, rdx
0x1800c4d9e  mov     [rsp+2B0h+var_258], 0
0x1800c4da7  lea     rdx, [rsp+2B0h+var_258]
0x1800c4dac  mov     [rsp+2B0h+hKey], 0
0x1800c4db5  call    Unicode2Ansi
0x1800c4dba  mov     ebx, eax
0x1800c4dbc  test    eax, eax
0x1800c4dbe  js      loc_1800C4FB3
0x1800c4dc4  mov     r13d, 208h
0x1800c4dca  lea     r8, aSoftwareMicros_102; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800c4dd1  mov     edx, r13d; unsigned __int64
0x1800c4dd4  lea     rcx, [rbp+1B0h+SubKey]; char *
0x1800c4dd8  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800c4ddd  lea     r10, [rsp+2B0h+hKey]
0x1800c4de2  mov     r12, 0FFFFFFFF80000001h
0x1800c4de9  mov     rcx, r12; hKey
0x1800c4dec  mov     [rsp+2B0h+phkResult], r10; phkResult
0x1800c4df1  mov     r9d, 20006h; samDesired
0x1800c4df7  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800c4dfb  xor     r8d, r8d; ulOptions
0x1800c4dfe  call    cs:__imp_RegOpenKeyExA
0x1800c4e04  test    eax, eax
0x1800c4e06  jz      short loc_1800C4E0F
0x1800c4e08  xor     ebx, ebx
0x1800c4e0a  jmp     loc_1800C4FB3
0x1800c4e0f  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800c4e14  test    rcx, rcx
0x1800c4e17  jz      short loc_1800C4E28
0x1800c4e19  call    cs:__imp_RegCloseKey
0x1800c4e1f  mov     [rsp+2B0h+hKey], 0
0x1800c4e28  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1800c4e2e  mov     ebx, eax
0x1800c4e30  test    eax, eax
0x1800c4e32  jnz     loc_1800C4F0E
0x1800c4e38  lea     rcx, [rsp+2B0h+var_248]
0x1800c4e3d  mov     [rsp+2B0h+var_240], 0
0x1800c4e46  mov     [rsp+2B0h+var_248], 0
0x1800c4e4f  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1800c4e55  mov     ebx, eax
0x1800c4e57  test    eax, eax
0x1800c4e59  js      loc_1800C4FB3
0x1800c4e5f  mov     rcx, [rsp+2B0h+var_248]
0x1800c4e64  lea     r9, [rsp+2B0h+var_250]
0x1800c4e69  mov     [rsp+2B0h+var_250], 0
0x1800c4e72  lea     r8, IID_IUnknown
0x1800c4e79  lea     rdx, CLSID_CShdocvwBroker
0x1800c4e80  mov     rax, [rcx]
0x1800c4e83  mov     rax, [rax+30h]
0x1800c4e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e8c  mov     ebx, eax
0x1800c4e8e  test    eax, eax
0x1800c4e90  js      short loc_1800C4EC1
0x1800c4e92  mov     rcx, [rsp+2B0h+var_250]
0x1800c4e97  lea     r8, [rsp+2B0h+var_240]
0x1800c4e9c  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1800c4ea3  mov     rax, [rcx]
0x1800c4ea6  mov     rax, [rax]
0x1800c4ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4eae  mov     rcx, [rsp+2B0h+var_250]
0x1800c4eb3  mov     ebx, eax
0x1800c4eb5  mov     rax, [rcx]
0x1800c4eb8  mov     rax, [rax+10h]
0x1800c4ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ec1  mov     rcx, [rsp+2B0h+var_248]
0x1800c4ec6  mov     rax, [rcx]
0x1800c4ec9  mov     rax, [rax+10h]
0x1800c4ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ed2  test    ebx, ebx
0x1800c4ed4  js      loc_1800C4FB3
0x1800c4eda  mov     rcx, [rsp+2B0h+var_240]
0x1800c4edf  mov     r8, rsi
0x1800c4ee2  mov     rdx, [rsp+2B0h+var_258]
0x1800c4ee7  mov     rax, [rcx]
0x1800c4eea  mov     rax, [rax+2D8h]
0x1800c4ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ef6  mov     rcx, [rsp+2B0h+var_240]
0x1800c4efb  mov     ebx, eax
0x1800c4efd  mov     rax, [rcx]
0x1800c4f00  mov     rax, [rax+10h]
0x1800c4f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4f09  jmp     loc_1800C4FB3
0x1800c4f0e  cmp     eax, 1
0x1800c4f11  jnz     loc_1800C4FB3
0x1800c4f17  lea     r8, asc_18012AFD0; "\\"
0x1800c4f1e  mov     rdx, r13; unsigned __int64
0x1800c4f21  lea     rcx, [rbp+1B0h+SubKey]; char *
0x1800c4f25  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800c4f2a  mov     r8, [rsp+2B0h+var_258]; char *
0x1800c4f2f  lea     rcx, [rbp+1B0h+SubKey]; char *
0x1800c4f33  mov     rdx, r13; unsigned __int64
0x1800c4f36  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800c4f3b  lea     rax, [rsp+2B0h+hKey]
0x1800c4f40  mov     r9d, 20006h; samDesired
0x1800c4f46  xor     r8d, r8d; ulOptions
0x1800c4f49  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800c4f4e  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800c4f52  mov     rcx, r12; hKey
0x1800c4f55  call    cs:__imp_RegOpenKeyExA
0x1800c4f5b  test    eax, eax
0x1800c4f5d  jz      loc_1800C4FFF
0x1800c4f63  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x1800c4f6c  lea     rax, [rsp+2B0h+hKey]
0x1800c4f71  mov     [rsp+2B0h+var_278], rax; phkResult
0x1800c4f76  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800c4f7a  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800c4f83  xor     r9d, r9d; lpClass
0x1800c4f86  mov     [rsp+2B0h+samDesired], 2000000h; samDesired
0x1800c4f8e  xor     r8d, r8d; Reserved
0x1800c4f91  mov     rcx, r12; hKey
0x1800c4f94  mov     dword ptr [rsp+2B0h+phkResult], 0; dwOptions
0x1800c4f9c  call    cs:__imp_RegCreateKeyExA
0x1800c4fa2  mov     ebx, eax
0x1800c4fa4  test    eax, eax
0x1800c4fa6  jz      short loc_1800C4FFF
0x1800c4fa8  jle     short loc_1800C4FB3
0x1800c4faa  movzx   ebx, ax
0x1800c4fad  or      ebx, 80070000h
0x1800c4fb3  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800c4fb8  test    rcx, rcx
0x1800c4fbb  jz      short loc_1800C4FC3
0x1800c4fbd  call    cs:__imp_RegCloseKey
0x1800c4fc3  cmp     [rsp+2B0h+var_258], 0
0x1800c4fc9  jz      short loc_1800C4FD5
0x1800c4fcb  mov     rcx, [rsp+2B0h+var_258]; void *
0x1800c4fd0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c4fd5  mov     eax, ebx
0x1800c4fd7  mov     rcx, [rbp+1B0h+var_20]
0x1800c4fde  xor     rcx, rsp; StackCookie
0x1800c4fe1  call    __security_check_cookie
0x1800c4fe6  lea     r11, [rsp+2B0h+var_10]
0x1800c4fee  mov     rbx, [r11+30h]
0x1800c4ff2  mov     rsi, [r11+38h]
0x1800c4ff6  mov     rsp, r11
0x1800c4ff9  pop     r13
0x1800c4ffb  pop     r12
0x1800c4ffd  pop     rbp
0x1800c4ffe  retn
0x1800c4fff  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800c5004  lea     rax, Default
0x1800c500b  xor     ebx, ebx
0x1800c500d  mov     [rsp+2B0h+samDesired], 1; cbData
0x1800c5015  xor     r8d, r8d; Reserved
0x1800c5018  mov     [rsp+2B0h+phkResult], rax; lpData
0x1800c501d  mov     rdx, rsi; lpValueName
0x1800c5020  lea     r9d, [rbx+1]; dwType
0x1800c5024  call    cs:__imp_RegSetValueExA
0x1800c502a  test    eax, eax
0x1800c502c  jz      short loc_1800C4FB3
0x1800c502e  jg      loc_1800C4FAA
0x1800c5034  mov     ebx, eax
0x1800c5036  jmp     loc_1800C4FB3
```
