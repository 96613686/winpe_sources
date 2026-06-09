# SHGetObjectCompatFlags

- ea: `0x1800068a0`
- end: `0x180006ab7`
- name: `SHGetObjectCompatFlags`
- size: `535`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800068a0`
- `0x180006ac0`
- `0x18004bd74`
- `0x180066910`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006aac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006aac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800069cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800069cc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006986`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006986`

## string_xrefs

- `0x180006996`: `SOFTWARE\Microsoft\Windows\CurrentVersion\ShellCompatibility\Objects\%s`

## pseudocode

```c
__int64 __fastcall SHGetObjectCompatFlags(__int64 (__fastcall ***a1)(_QWORD, GUID *, HKEY *), GUID *a2)
{
  unsigned int v2; // edi
  __int64 (__fastcall **v4)(_QWORD, GUID *, HKEY *); // rax
  int (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rax
  int v6; // ebx
  void (*v7)(void); // rax
  GUID **i; // rdx
  __int64 v9; // rax
  unsigned int MappedFlags; // ebx
  const struct FLAGMAP *v11; // rdx
  unsigned int v12; // r8d
  void **j; // rax
  __int64 v15; // rcx
  __int64 (__fastcall **v16)(_QWORD, GUID *, HKEY *); // rax
  HKEY hKey; // [rsp+30h] [rbp-298h] BYREF
  __int64 v18; // [rsp+38h] [rbp-290h] BYREF
  GUID rguid; // [rsp+40h] [rbp-288h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-228h] BYREF

  v2 = 0;
  if ( a1 )
  {
    v4 = *a1;
    v18 = 0;
    v5 = (int (__fastcall *)(_QWORD, GUID *, __int64 *))*v4;
    rguid = GUID_NULL;
    if ( v5(a1, &GUID_0000010c_0000_0000_c000_000000000046, &v18) < 0 )
    {
      v16 = *a1;
      hKey = 0;
      v6 = (*v16)(a1, &GUID_000214ea_0000_0000_c000_000000000046, &hKey);
      if ( v6 < 0 )
      {
LABEL_5:
        if ( v6 < 0 )
          return v2;
        goto LABEL_6;
      }
      v6 = (*(__int64 (__fastcall **)(HKEY, GUID *))(*(_QWORD *)hKey + 24LL))(hKey, &rguid);
      v7 = *(void (**)(void))(*(_QWORD *)hKey + 16LL);
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v18 + 24LL))(v18, &rguid);
      v7 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
    }
    v7();
    goto LABEL_5;
  }
  if ( !a2 )
    return v2;
  rguid = *a2;
LABEL_6:
  for ( i = off_1800DE130; i != (GUID **)&g_hWindowsPolicies_LegacyRegistryLocationToMatchSHRestricted; ++i )
  {
    v9 = *(_QWORD *)&rguid.Data1 - *(_QWORD *)&(*i)->Data1;
    if ( *(_QWORD *)&rguid.Data1 == *(_QWORD *)&(*i)->Data1 )
      v9 = *(_QWORD *)rguid.Data4 - *(_QWORD *)(*i)->Data4;
    if ( !v9 )
      return v2;
  }
  for ( j = (void **)&off_180096060; j != &CRemoteTask::`vftable'; j += 2 )
  {
    v15 = *(_QWORD *)&rguid.Data1 - *(_QWORD *)*j;
    if ( *(_QWORD *)&rguid.Data1 == *(_QWORD *)*j )
      v15 = *(_QWORD *)rguid.Data4 - *((_QWORD *)*j + 1);
    if ( !v15 )
    {
      v2 = *((_DWORD *)j + 2);
      break;
    }
  }
  MappedFlags = 0;
  hKey = 0;
  StringFromGUID2(&rguid, sz, 39);
  StringCchPrintfW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ShellCompatibility\\Objects\\%s", sz);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    MappedFlags = _GetMappedFlags(hKey, v11, v12);
    RegCloseKey(hKey);
  }
  v2 |= MappedFlags;
  return v2;
}

```

## disassembly

```asm
0x1800068a0  mov     [rsp+arg_10], rbx
0x1800068a5  push    rdi
0x1800068a6  sub     rsp, 2C0h
0x1800068ad  mov     rax, cs:__security_cookie
0x1800068b4  xor     rax, rsp
0x1800068b7  mov     [rsp+2C8h+var_18], rax
0x1800068bf  xor     edi, edi
0x1800068c1  mov     rbx, rcx
0x1800068c4  test    rcx, rcx
0x1800068c7  jz      loc_180006A37
0x1800068cd  mov     rax, [rcx]
0x1800068d0  lea     r8, [rsp+2C8h+var_290]
0x1800068d5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800068dc  lea     rdx, _GUID_0000010c_0000_0000_c000_000000000046
0x1800068e3  mov     [rsp+2C8h+var_290], rdi
0x1800068e8  mov     rax, [rax]
0x1800068eb  movups  xmmword ptr [rsp+2C8h+rguid.Data1], xmm0
0x1800068f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f5  test    eax, eax
0x1800068f7  js      loc_180006A49
0x1800068fd  mov     rcx, [rsp+2C8h+var_290]
0x180006902  lea     rdx, [rsp+2C8h+rguid]
0x180006907  mov     rax, [rcx]
0x18000690a  mov     rax, [rax+18h]
0x18000690e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006913  mov     rcx, [rsp+2C8h+var_290]
0x180006918  mov     ebx, eax
0x18000691a  mov     rax, [rcx]
0x18000691d  mov     rax, [rax+10h]
0x180006921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006926  test    ebx, ebx
0x180006928  js      loc_1800069DC
0x18000692e  mov     r8, qword ptr [rsp+2C8h+rguid.Data4]
0x180006933  lea     rdx, off_1800DE130
0x18000693a  mov     r9, qword ptr [rsp+2C8h+rguid.Data1]
0x18000693f  lea     r10, ?g_hWindowsPolicies_LegacyRegistryLocationToMatchSHRestricted@@3USHPOLICYTABLE_@@A; SHPOLICYTABLE_ g_hWindowsPolicies_LegacyRegistryLocationToMatchSHRestricted
0x180006946  cmp     rdx, r10
0x180006949  jz      loc_1800069FF
0x18000694f  mov     rcx, [rdx]
0x180006952  mov     rax, r9
0x180006955  sub     rax, [rcx]
0x180006958  jnz     short loc_180006961
0x18000695a  mov     rax, r8
0x18000695d  sub     rax, [rcx+8]
0x180006961  test    rax, rax
0x180006964  jz      short loc_1800069DC
0x180006966  add     rdx, 8
0x18000696a  jmp     short loc_180006946
0x18000696c  mov     edi, [rax+8]
0x18000696f  xor     ebx, ebx
0x180006971  lea     rdx, [rsp+2C8h+sz]; lpsz
0x180006976  mov     r8d, 27h ; '''; cchMax
0x18000697c  mov     [rsp+2C8h+hKey], rbx
0x180006981  lea     rcx, [rsp+2C8h+rguid]; rguid
0x180006986  call    cs:__imp_StringFromGUID2
0x18000698c  lea     r9, [rsp+2C8h+sz]
0x180006991  mov     edx, 104h; unsigned __int64
0x180006996  lea     r8, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000699d  lea     rcx, [rsp+2C8h+SubKey]; unsigned __int16 *
0x1800069a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800069aa  lea     rax, [rsp+2C8h+hKey]
0x1800069af  mov     r9d, 1; samDesired
0x1800069b5  xor     r8d, r8d; ulOptions
0x1800069b8  mov     [rsp+2C8h+phkResult], rax; phkResult
0x1800069bd  lea     rdx, [rsp+2C8h+SubKey]; lpSubKey
0x1800069c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800069cc  call    cs:__imp_RegOpenKeyExW
0x1800069d2  test    eax, eax
0x1800069d4  jz      loc_180006A9B
0x1800069da  or      edi, ebx
0x1800069dc  mov     eax, edi
0x1800069de  mov     rcx, [rsp+2C8h+var_18]
0x1800069e6  xor     rcx, rsp; StackCookie
0x1800069e9  call    __security_check_cookie
0x1800069ee  mov     rbx, [rsp+2C8h+arg_10]
0x1800069f6  add     rsp, 2C0h
0x1800069fd  pop     rdi
0x1800069fe  retn
0x1800069ff  lea     rax, off_180096060
0x180006a06  lea     r10, ??_7CRemoteTask@@6B@; const CRemoteTask::`vftable'
0x180006a0d  cmp     rax, r10
0x180006a10  jz      loc_18000696F
0x180006a16  mov     rdx, [rax]
0x180006a19  mov     rcx, r9
0x180006a1c  sub     rcx, [rdx]
0x180006a1f  jnz     short loc_180006A28
0x180006a21  mov     rcx, r8
0x180006a24  sub     rcx, [rdx+8]
0x180006a28  test    rcx, rcx
0x180006a2b  jz      loc_18000696C
0x180006a31  add     rax, 10h
0x180006a35  jmp     short loc_180006A0D
0x180006a37  test    rdx, rdx
0x180006a3a  jz      short loc_1800069DC
0x180006a3c  movups  xmm0, xmmword ptr [rdx]
0x180006a3f  movups  xmmword ptr [rsp+2C8h+rguid.Data1], xmm0
0x180006a44  jmp     loc_18000692E
0x180006a49  mov     rax, [rbx]
0x180006a4c  lea     r8, [rsp+2C8h+hKey]
0x180006a51  lea     rdx, _GUID_000214ea_0000_0000_c000_000000000046
0x180006a58  mov     [rsp+2C8h+hKey], rdi
0x180006a5d  mov     rcx, rbx
0x180006a60  mov     rax, [rax]
0x180006a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a68  mov     ebx, eax
0x180006a6a  test    eax, eax
0x180006a6c  js      loc_180006926
0x180006a72  mov     rcx, [rsp+2C8h+hKey]
0x180006a77  lea     rdx, [rsp+2C8h+rguid]
0x180006a7c  mov     rax, [rcx]
0x180006a7f  mov     rax, [rax+18h]
0x180006a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a88  mov     rcx, [rsp+2C8h+hKey]
0x180006a8d  mov     ebx, eax
0x180006a8f  mov     rdx, [rcx]
0x180006a92  mov     rax, [rdx+10h]
0x180006a96  jmp     loc_180006921
0x180006a9b  mov     rcx, [rsp+2C8h+hKey]; hkey
0x180006aa0  call    ?_GetMappedFlags@@YAKPEAUHKEY__@@PEBUFLAGMAP@@K@Z; _GetMappedFlags(HKEY__ *,FLAGMAP const *,ulong)
0x180006aa5  mov     rcx, [rsp+2C8h+hKey]; hKey
0x180006aaa  mov     ebx, eax
0x180006aac  call    cs:__imp_RegCloseKey
0x180006ab2  jmp     loc_1800069DA
```
