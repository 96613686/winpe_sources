# CSrchAdminSSO::s_ReindexProfile(void *)

- ea: `0x18002eed0`
- end: `0x18002f068`
- name: `?s_ReindexProfile@CSrchAdminSSO@@CAKPEAX@Z`
- size: `408`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003ea4`
- `0x180005cc0`
- `0x18000957c`
- `0x1800231a4`
- `0x18002eed0`
- `0x180032010`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18002ef27`
- `SHELL32!SHGetKnownFolderPath` at `0x18002ef27`
- `SHLWAPI!PathAppendW` at `0x18002ef61`
- `SHLWAPI!PathAppendW` at `0x18002ef61`
- `SHLWAPI!__imp_SHGlobalCounterIncrement` at `0x18002ef07`
- `SHLWAPI!__imp_SHGlobalCounterIncrement` at `0x18002ef07`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002f02a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002f02a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ef8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ef8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f005`

## pseudocode

```c
__int64 __fastcall CSrchAdminSSO::s_ReindexProfile(void *a1)
{
  int v1; // edi
  HRESULT v2; // ebx
  const unsigned __int16 *v3; // rdx
  HKEY v4; // rcx
  const unsigned __int16 *v5; // r8
  __int64 v6; // r9
  __int64 result; // rax
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  PWSTR ppszPath; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = SHCoInitialize();
  SHGlobalCounterIncrement((LPCWSTR)0x33);
  ppszPath = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_Profile, 0, 0, &ppszPath);
  if ( v2 >= 0 )
  {
    v2 = StringCchCopyW(pszPath, 0x104u, ppszPath);
    if ( v2 >= 0 )
    {
      PathAppendW(pszPath, L"*");
      ppv = 0;
      v2 = CoCreateInstance(&CLSID_CSearchManager, 0, 0x15u, &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69, &ppv);
      if ( v2 >= 0 )
      {
        *(_QWORD *)Data = 0;
        v2 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, BYTE *))(*(_QWORD *)ppv + 80LL))(
               ppv,
               L"SystemIndex",
               Data);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)Data + 72LL))(*(_QWORD *)Data, pszPath);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Data + 16LL))(*(_QWORD *)Data);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    CoTaskMemFree(ppszPath);
    if ( v2 >= 0 )
    {
      *(_DWORD *)Data = 1;
      _RegSetKeyValueWithSDDL(v4, v3, v5, v6, Data);
    }
  }
  if ( !v1 )
    CoUninitialize();
  result = (unsigned __int16)v2;
  if ( (v2 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v2;
  return result;
}

```

## disassembly

```asm
0x18002eed0  mov     [rsp-8+arg_0], rbx
0x18002eed5  mov     [rsp-8+arg_8], rdi
0x18002eeda  push    rbp
0x18002eedb  lea     rbp, [rsp-180h]
0x18002eee3  sub     rsp, 280h
0x18002eeea  mov     rax, cs:__security_cookie
0x18002eef1  xor     rax, rsp
0x18002eef4  mov     [rbp+180h+var_10], rax
0x18002eefb  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x18002ef00  mov     ecx, 33h ; '3'; pszPath
0x18002ef05  mov     edi, eax
0x18002ef07  call    cs:__imp_SHGlobalCounterIncrement
0x18002ef0d  lea     r9, [rsp+280h+ppszPath]; ppszPath
0x18002ef12  mov     [rsp+280h+ppszPath], 0
0x18002ef1b  xor     r8d, r8d; hToken
0x18002ef1e  lea     rcx, FOLDERID_Profile; rfid
0x18002ef25  xor     edx, edx; dwFlags
0x18002ef27  call    cs:__imp_SHGetKnownFolderPath
0x18002ef2d  mov     ebx, eax
0x18002ef2f  test    eax, eax
0x18002ef31  js      loc_18002F026
0x18002ef37  mov     r8, [rsp+280h+ppszPath]; unsigned __int16 *
0x18002ef3c  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x18002ef41  mov     edx, 104h; unsigned __int64
0x18002ef46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ef4b  mov     ebx, eax
0x18002ef4d  test    eax, eax
0x18002ef4f  js      loc_18002F000
0x18002ef55  lea     rdx, pszSrch; "*"
0x18002ef5c  lea     rcx, [rsp+280h+pszPath]; pszPath
0x18002ef61  call    cs:__imp_PathAppendW
0x18002ef67  xor     edx, edx; pUnkOuter
0x18002ef69  mov     [rsp+280h+var_238], 0
0x18002ef72  lea     rax, [rsp+280h+var_238]
0x18002ef77  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x18002ef7e  mov     [rsp+280h+ppv], rax; ppv
0x18002ef83  lea     rcx, CLSID_CSearchManager; rclsid
0x18002ef8a  lea     r8d, [rdx+15h]; dwClsContext
0x18002ef8e  call    cs:__imp_CoCreateInstance
0x18002ef94  mov     ebx, eax
0x18002ef96  test    eax, eax
0x18002ef98  js      short loc_18002F000
0x18002ef9a  mov     rcx, [rsp+280h+var_238]
0x18002ef9f  lea     r8, [rsp+280h+Data]
0x18002efa4  mov     qword ptr [rsp+280h+Data], 0
0x18002efad  lea     rdx, aSystemindex; "SystemIndex"
0x18002efb4  mov     rax, [rcx]
0x18002efb7  mov     rax, [rax+50h]
0x18002efbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efc0  mov     ebx, eax
0x18002efc2  test    eax, eax
0x18002efc4  js      short loc_18002EFEF
0x18002efc6  mov     rcx, qword ptr [rsp+280h+Data]
0x18002efcb  lea     rdx, [rsp+280h+pszPath]
0x18002efd0  mov     rax, [rcx]
0x18002efd3  mov     rax, [rax+48h]
0x18002efd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efdc  mov     rcx, qword ptr [rsp+280h+Data]
0x18002efe1  mov     ebx, eax
0x18002efe3  mov     rax, [rcx]
0x18002efe6  mov     rax, [rax+10h]
0x18002efea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efef  mov     rcx, [rsp+280h+var_238]
0x18002eff4  mov     rax, [rcx]
0x18002eff7  mov     rax, [rax+10h]
0x18002effb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f000  mov     rcx, [rsp+280h+ppszPath]; pv
0x18002f005  call    cs:__imp_CoTaskMemFree
0x18002f00b  test    ebx, ebx
0x18002f00d  js      short loc_18002F026
0x18002f00f  lea     rax, [rsp+280h+Data]
0x18002f014  mov     dword ptr [rsp+280h+Data], 1
0x18002f01c  mov     [rsp+280h+ppv], rax; lpData
0x18002f021  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x18002f026  test    edi, edi
0x18002f028  jnz     short loc_18002F030
0x18002f02a  call    cs:__imp_CoUninitialize
0x18002f030  mov     ecx, ebx
0x18002f032  movzx   eax, bx
0x18002f035  and     ecx, 1FFF0000h
0x18002f03b  cmp     ecx, 70000h
0x18002f041  cmovnz  eax, ebx
0x18002f044  mov     rcx, [rbp+180h+var_10]
0x18002f04b  xor     rcx, rsp; StackCookie
0x18002f04e  call    __security_check_cookie
0x18002f053  lea     r11, [rsp+280h+var_s0]
0x18002f05b  mov     rbx, [r11+10h]
0x18002f05f  mov     rdi, [r11+18h]
0x18002f063  mov     rsp, r11
0x18002f066  pop     rbp
0x18002f067  retn
```
