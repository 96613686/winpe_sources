# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180010440`
- end: `0x1800109e4`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1444`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013790`
- `0x180013890`

## callees

- `0x180003b70`
- `0x1800099ac`
- `0x180010440`
- `0x180010e78`
- `0x180014270`
- `0x180014300`
- `0x180015010`

## import_xrefs

- `msvcrt!strcat_s` at `0x1800106c4`
- `msvcrt!strcat_s` at `0x180010700`
- `msvcrt!strcat_s` at `0x18001082c`
- `msvcrt!strcat_s` at `0x180010868`
- `msvcrt!strcat_s` at `0x1800106c4`
- `msvcrt!strcat_s` at `0x180010700`
- `msvcrt!strcat_s` at `0x18001082c`
- `msvcrt!strcat_s` at `0x180010868`
- `msvcrt!strcpy_s` at `0x18001068c`
- `msvcrt!strcpy_s` at `0x1800107f4`
- `msvcrt!strcpy_s` at `0x18001068c`
- `msvcrt!strcpy_s` at `0x1800107f4`
- `msvcrt!free` at `0x180010969`
- `msvcrt!free` at `0x180010969`
- `msvcrt!malloc` at `0x18001061a`
- `msvcrt!malloc` at `0x18001061a`
- `ole32!StringFromGUID2` at `0x180010589`
- `ole32!StringFromGUID2` at `0x180010589`
- `ole32!CoCreateInstance` at `0x1800104e5`
- `ole32!CoCreateInstance` at `0x1800104e5`
- `KERNEL32!WideCharToMultiByte` at `0x18001065e`
- `KERNEL32!WideCharToMultiByte` at `0x18001065e`
- `ADVAPI32!RegOpenKeyExA` at `0x180010765`
- `ADVAPI32!RegOpenKeyExA` at `0x1800108b3`
- `ADVAPI32!RegOpenKeyExA` at `0x180010765`
- `ADVAPI32!RegOpenKeyExA` at `0x1800108b3`
- `ADVAPI32!RegQueryInfoKeyA` at `0x1800107aa`
- `ADVAPI32!RegQueryInfoKeyA` at `0x180010911`
- `ADVAPI32!RegQueryInfoKeyA` at `0x1800107aa`
- `ADVAPI32!RegQueryInfoKeyA` at `0x180010911`
- `ADVAPI32!RegCloseKey` at `0x1800107bb`
- `ADVAPI32!RegCloseKey` at `0x1800108cc`
- `ADVAPI32!RegCloseKey` at `0x180010921`
- `ADVAPI32!RegCloseKey` at `0x18001094d`
- `ADVAPI32!RegCloseKey` at `0x18001095b`
- `ADVAPI32!RegCloseKey` at `0x1800107bb`
- `ADVAPI32!RegCloseKey` at `0x1800108cc`
- `ADVAPI32!RegCloseKey` at `0x180010921`
- `ADVAPI32!RegCloseKey` at `0x18001094d`
- `ADVAPI32!RegCloseKey` at `0x18001095b`

## string_xrefs

- `0x18001067f`: `CLSID\`
- `0x1800107e6`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // ecx
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  __int64 cbMultiByte; // rsi
  _QWORD *v15; // rbx
  unsigned __int64 v16; // rax
  void *v17; // rsp
  CHAR *v18; // rdi
  _QWORD *v19; // rax
  const char *v20; // rsi
  errno_t v21; // eax
  errno_t v22; // eax
  errno_t v23; // eax
  HKEY v24; // r14
  HKEY v25; // rdi
  LSTATUS InfoKeyA; // r15d
  errno_t v27; // eax
  errno_t v28; // eax
  errno_t v29; // eax
  HKEY v30; // rdi
  LSTATUS v31; // esi
  void *v32; // rcx
  CHAR MultiByteStr[4]; // [rsp+60h] [rbp+0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+18h] BYREF
  _QWORD v37[3]; // [rsp+80h] [rbp+20h] BYREF
  __int128 v38; // [rsp+98h] [rbp+38h] BYREF
  char Destination[128]; // [rsp+B0h] [rbp+50h] BYREF
  WCHAR sz[64]; // [rsp+130h] [rbp+D0h] BYREF

  ppv = 0;
  v4 = a2;
  v38 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    return 0;
  }
  if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
LABEL_84:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( a3 )
        goto LABEL_84;
      StringFromGUID2(rguid, sz, 64);
      v13 = -1;
      do
        ++v13;
      while ( sz[v13] );
      cbMultiByte = 2LL * ((int)v13 + 1);
      if ( (unsigned __int64)(cbMultiByte + 0x80000000LL) > 0xFFFFFFFF )
        goto LABEL_84;
      v15 = 0;
      if ( (int)cbMultiByte <= 1024
        && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)cbMultiByte, v12) )
      {
        v16 = (int)cbMultiByte + 15LL;
        if ( v16 < (int)cbMultiByte )
          v16 = 0xFFFFFFFFFFFFFF0LL;
        v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
        v18 = MultiByteStr;
      }
      else
      {
        if ( (unsigned __int64)~(__int64)(int)cbMultiByte < 0x10 )
          ATL::AtlThrowImpl(-2147024809);
        v19 = malloc((int)cbMultiByte + 16LL);
        if ( v19 )
        {
          *v19 = 0;
          v18 = (CHAR *)(v19 + 2);
          v15 = v19;
        }
        else
        {
          v18 = 0;
        }
      }
      if ( v18 )
      {
        *v18 = 0;
        v20 = (const char *)((unsigned __int64)v18
                           & -(__int64)(WideCharToMultiByte(3u, 0, sz, -1, v18, cbMultiByte, 0, 0) != 0));
      }
      else
      {
        v20 = 0;
      }
      if ( !v20 )
        goto LABEL_83;
      v21 = strcpy_s(Destination, 0x80u, "CLSID\\");
      if ( v21 )
      {
        if ( v21 == 12 )
          goto LABEL_87;
        if ( v21 == 22 || v21 == 34 )
          goto LABEL_90;
        if ( v21 != 80 )
          goto LABEL_89;
      }
      v22 = strcat_s(Destination, 0x80u, v20);
      if ( v22 )
      {
        if ( v22 == 12 )
          goto LABEL_87;
        if ( v22 == 22 || v22 == 34 )
          goto LABEL_90;
        if ( v22 != 80 )
          goto LABEL_89;
      }
      v23 = strcat_s(Destination, 0x80u, "\\Required Categories");
      if ( v23 )
      {
        if ( v23 == 12 )
          goto LABEL_87;
        if ( v23 == 22 || v23 == 34 )
          goto LABEL_90;
        if ( v23 != 80 )
          goto LABEL_89;
      }
      v24 = HKEY_CLASSES_ROOT;
      v37[1] = 0;
      v37[0] = 0xFFFFFFFF80000000uLL;
      v37[2] = 0;
      *(_DWORD *)MultiByteStr = 0;
      phkResult = 0;
      if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
      {
        v25 = phkResult;
        InfoKeyA = RegQueryInfoKeyA(phkResult, 0, 0, 0, (LPDWORD)MultiByteStr, 0, 0, 0, 0, 0, 0, 0);
        if ( v25 )
          RegCloseKey(v25);
        if ( !InfoKeyA && !*(_DWORD *)MultiByteStr )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v37, Destination);
          v24 = (HKEY)v37[0];
        }
      }
      v27 = strcpy_s(Destination, 0x80u, "CLSID\\");
      if ( v27 )
      {
        if ( v27 == 12 )
          goto LABEL_87;
        if ( v27 == 22 || v27 == 34 )
          goto LABEL_90;
        if ( v27 != 80 )
          goto LABEL_89;
      }
      v28 = strcat_s(Destination, 0x80u, v20);
      if ( v28 )
      {
        if ( v28 == 12 )
          goto LABEL_87;
        if ( v28 == 22 || v28 == 34 )
          goto LABEL_90;
        if ( v28 != 80 )
          goto LABEL_89;
      }
      v29 = strcat_s(Destination, 0x80u, "\\Implemented Categories");
      if ( !v29 )
      {
LABEL_74:
        hKey = 0;
        if ( !RegOpenKeyExA(v24, Destination, 0, 0x20019u, &hKey) )
        {
          v30 = hKey;
          v31 = RegQueryInfoKeyA(hKey, 0, 0, 0, (LPDWORD)MultiByteStr, 0, 0, 0, 0, 0, 0, 0);
          if ( v30 )
            RegCloseKey(v30);
          if ( !v31 && !*(_DWORD *)MultiByteStr )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v37, Destination);
            v24 = (HKEY)v37[0];
          }
        }
        if ( v24 )
          RegCloseKey(v24);
LABEL_83:
        while ( v15 )
        {
          v32 = v15;
          v15 = (_QWORD *)*v15;
          free(v32);
        }
        goto LABEL_84;
      }
      if ( v29 != 12 )
      {
        if ( v29 != 22 && v29 != 34 )
        {
          if ( v29 == 80 )
            goto LABEL_74;
LABEL_89:
          ATL::AtlThrowImpl(-2147467259);
        }
LABEL_90:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_87:
      ATL::AtlThrowImpl(-2147024882);
    }
    v38 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v38);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v38);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v38)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v38);
    v8 = v7;
    if ( v7 < 0 )
      break;
LABEL_19:
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x180010440  push    rbp
0x180010442  push    rdi
0x180010443  push    r12
0x180010445  push    r14
0x180010447  push    r15
0x180010449  sub     rsp, 1C0h
0x180010450  lea     rbp, [rsp+60h]
0x180010455  mov     [rbp+180h+arg_10], rbx
0x18001045c  mov     [rbp+180h+arg_18], rsi
0x180010463  mov     rax, cs:__security_cookie
0x18001046a  xor     rax, rbp
0x18001046d  mov     [rbp+180h+var_30], rax
0x180010474  xor     r12d, r12d
0x180010477  xorps   xmm0, xmm0
0x18001047a  mov     [rbp+180h+var_178], r12
0x18001047e  mov     r14d, r8d
0x180010481  mov     rdi, rdx
0x180010484  mov     rbx, rcx
0x180010487  movups  [rbp+180h+var_148], xmm0
0x18001048b  test    rdx, rdx
0x18001048e  jz      loc_180010989
0x180010494  mov     eax, cs:GUID_NULL.Data1
0x18001049a  cmp     [rcx], eax
0x18001049c  jnz     short loc_1800104C3
0x18001049e  mov     eax, dword ptr cs:GUID_NULL.Data2
0x1800104a4  cmp     [rcx+4], eax
0x1800104a7  jnz     short loc_1800104C3
0x1800104a9  mov     eax, dword ptr cs:GUID_NULL.Data4
0x1800104af  cmp     [rcx+8], eax
0x1800104b2  jnz     short loc_1800104C3
0x1800104b4  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x1800104ba  cmp     [rcx+0Ch], eax
0x1800104bd  jz      loc_180010989
0x1800104c3  lea     rax, [rbp+180h+var_178]
0x1800104c7  mov     r15d, 1
0x1800104cd  mov     r8d, r15d; dwClsContext
0x1800104d0  mov     [rsp+1E0h+ppv], rax; ppv
0x1800104d5  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800104dc  xor     edx, edx; pUnkOuter
0x1800104de  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800104e5  call    cs:__imp_CoCreateInstance
0x1800104eb  test    eax, eax
0x1800104ed  js      loc_180010974
0x1800104f3  jmp     short loc_18001056C
0x1800104f5  mov     rax, [rdi+8]
0x1800104f9  lea     r9, [rbp+180h+var_148]
0x1800104fd  mov     r8d, r15d
0x180010500  mov     rdx, rbx
0x180010503  movups  xmm0, xmmword ptr [rax]
0x180010506  movdqu  [rbp+180h+var_148], xmm0
0x18001050b  test    r14d, r14d
0x18001050e  jz      short loc_18001054D
0x180010510  cmp     ecx, r15d
0x180010513  mov     rcx, [rbp+180h+var_178]
0x180010517  mov     rax, [rcx]
0x18001051a  jnz     short loc_180010522
0x18001051c  mov     rax, [rax+28h]
0x180010520  jmp     short loc_180010526
0x180010522  mov     rax, [rax+38h]
0x180010526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001052b  mov     esi, eax
0x18001052d  test    eax, eax
0x18001052f  jns     short loc_180010568
0x180010531  mov     rcx, [rbp+180h+var_178]
0x180010535  test    rcx, rcx
0x180010538  jz      short loc_180010546
0x18001053a  mov     rax, [rcx]
0x18001053d  mov     rax, [rax+10h]
0x180010541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010546  mov     eax, esi
0x180010548  jmp     loc_18001098B
0x18001054d  cmp     ecx, r15d
0x180010550  mov     rcx, [rbp+180h+var_178]
0x180010554  mov     rax, [rcx]
0x180010557  jnz     short loc_18001055F
0x180010559  mov     rax, [rax+30h]
0x18001055d  jmp     short loc_180010563
0x18001055f  mov     rax, [rax+40h]
0x180010563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010568  add     rdi, 10h
0x18001056c  mov     ecx, [rdi]
0x18001056e  test    ecx, ecx
0x180010570  jnz     short loc_1800104F5
0x180010572  test    r14d, r14d
0x180010575  jnz     loc_180010974
0x18001057b  lea     r8d, [rcx+40h]; cchMax
0x18001057f  mov     rcx, rbx; rguid
0x180010582  lea     rdx, [rbp+180h+sz]; lpsz
0x180010589  call    cs:__imp_StringFromGUID2
0x18001058f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180010593  lea     rcx, [rbp+180h+sz]
0x18001059a  mov     rax, r14
0x18001059d  inc     rax
0x1800105a0  cmp     [rcx+rax*2], r12w
0x1800105a5  jnz     short loc_18001059D
0x1800105a7  inc     eax
0x1800105a9  movsxd  rcx, eax
0x1800105ac  mov     eax, 80000000h
0x1800105b1  lea     rsi, [rcx+rcx]
0x1800105b5  mov     ecx, 0FFFFFFFFh
0x1800105ba  add     rax, rsi
0x1800105bd  cmp     rax, rcx
0x1800105c0  ja      loc_180010974
0x1800105c6  movsxd  rdi, esi
0x1800105c9  mov     rbx, r12
0x1800105cc  cmp     esi, 400h
0x1800105d2  jg      short loc_180010606
0x1800105d4  mov     rcx, rdi; this
0x1800105d7  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800105dc  test    al, al
0x1800105de  jz      short loc_180010606
0x1800105e0  lea     rax, [rdi+0Fh]
0x1800105e4  cmp     rax, rdi
0x1800105e7  ja      short loc_1800105F3
0x1800105e9  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800105f3  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800105f7  call    _alloca_probe
0x1800105fc  sub     rsp, rax
0x1800105ff  lea     rdi, [rsp+1E0h+MultiByteStr]
0x180010604  jmp     short loc_180010634
0x180010606  mov     rax, rdi
0x180010609  not     rax
0x18001060c  cmp     rax, 10h
0x180010610  jb      loc_1800109C3
0x180010616  lea     rcx, [rdi+10h]; Size
0x18001061a  call    cs:__imp_malloc
0x180010620  test    rax, rax
0x180010623  jnz     short loc_18001062A
0x180010625  mov     rdi, r12
0x180010628  jmp     short loc_180010634
0x18001062a  mov     [rax], r12
0x18001062d  lea     rdi, [rax+10h]
0x180010631  mov     rbx, rax
0x180010634  test    rdi, rdi
0x180010637  jz      short loc_18001066E
0x180010639  mov     [rsp+1E0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18001063e  lea     r8, [rbp+180h+sz]; lpWideCharStr
0x180010645  xor     edx, edx; dwFlags
0x180010647  mov     [rsp+1E0h+lpDefaultChar], r12; lpDefaultChar
0x18001064c  mov     [rsp+1E0h+cbMultiByte], esi; cbMultiByte
0x180010650  mov     r9d, r14d; cchWideChar
0x180010653  mov     [rdi], r12b
0x180010656  mov     [rsp+1E0h+ppv], rdi; lpMultiByteStr
0x18001065b  lea     ecx, [rdx+3]; CodePage
0x18001065e  call    cs:__imp_WideCharToMultiByte
0x180010664  neg     eax
0x180010666  sbb     rsi, rsi
0x180010669  and     rsi, rdi
0x18001066c  jmp     short loc_180010671
0x18001066e  mov     rsi, r12
0x180010671  test    rsi, rsi
0x180010674  jz      loc_18001096F
0x18001067a  mov     edi, 80h
0x18001067f  lea     r8, Source; "CLSID\\"
0x180010686  mov     edx, edi; SizeInBytes
0x180010688  lea     rcx, [rbp+180h+Destination]; Destination
0x18001068c  call    cs:__imp_strcpy_s
0x180010692  test    eax, eax
0x180010694  jz      short loc_1800106BA
0x180010696  cmp     eax, 0Ch
0x180010699  jz      loc_1800109B8
0x18001069f  cmp     eax, 16h
0x1800106a2  jz      loc_1800109D9
0x1800106a8  cmp     eax, 22h ; '"'
0x1800106ab  jz      loc_1800109D9
0x1800106b1  cmp     eax, 50h ; 'P'
0x1800106b4  jnz     loc_1800109CE
0x1800106ba  mov     r8, rsi; Source
0x1800106bd  lea     rcx, [rbp+180h+Destination]; Destination
0x1800106c1  mov     rdx, rdi; SizeInBytes
0x1800106c4  call    cs:__imp_strcat_s
0x1800106ca  test    eax, eax
0x1800106cc  jz      short loc_1800106F2
0x1800106ce  cmp     eax, 0Ch
0x1800106d1  jz      loc_1800109B8
0x1800106d7  cmp     eax, 16h
0x1800106da  jz      loc_1800109D9
0x1800106e0  cmp     eax, 22h ; '"'
0x1800106e3  jz      loc_1800109D9
0x1800106e9  cmp     eax, 50h ; 'P'
0x1800106ec  jnz     loc_1800109CE
0x1800106f2  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800106f9  mov     rdx, rdi; SizeInBytes
0x1800106fc  lea     rcx, [rbp+180h+Destination]; Destination
0x180010700  call    cs:__imp_strcat_s
0x180010706  test    eax, eax
0x180010708  jz      short loc_18001072E
0x18001070a  cmp     eax, 0Ch
0x18001070d  jz      loc_1800109B8
0x180010713  cmp     eax, 16h
0x180010716  jz      loc_1800109D9
0x18001071c  cmp     eax, 22h ; '"'
0x18001071f  jz      loc_1800109D9
0x180010725  cmp     eax, 50h ; 'P'
0x180010728  jnz     loc_1800109CE
0x18001072e  mov     r14, 0FFFFFFFF80000000h
0x180010735  mov     [rbp+180h+var_158], r12
0x180010739  lea     rax, [rbp+180h+phkResult]
0x18001073d  mov     [rbp+180h+var_160], r14
0x180010741  mov     rcx, r14; hKey
0x180010744  mov     [rbp+180h+var_150], r12
0x180010748  mov     r9d, 20019h; samDesired
0x18001074e  mov     dword ptr [rbp+180h+MultiByteStr], r12d
0x180010752  xor     r8d, r8d; ulOptions
0x180010755  mov     [rbp+180h+phkResult], r12
0x180010759  lea     rdx, [rbp+180h+Destination]; lpSubKey
0x18001075d  mov     [rsp+1E0h+ppv], rax; phkResult
0x180010762  mov     rdi, r12
0x180010765  call    cs:__imp_RegOpenKeyExA
0x18001076b  test    eax, eax
0x18001076d  jnz     short loc_1800107E0
0x18001076f  mov     rdi, [rbp+180h+phkResult]
0x180010773  lea     rax, [rbp+180h+MultiByteStr]
0x180010777  mov     [rsp+1E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001077c  xor     r9d, r9d; lpReserved
0x18001077f  mov     [rsp+1E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180010784  xor     r8d, r8d; lpcchClass
0x180010787  mov     [rsp+1E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18001078c  xor     edx, edx; lpClass
0x18001078e  mov     [rsp+1E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180010793  mov     rcx, rdi; hKey
0x180010796  mov     [rsp+1E0h+lpUsedDefaultChar], r12; lpcValues
0x18001079b  mov     [rsp+1E0h+lpDefaultChar], r12; lpcbMaxClassLen
0x1800107a0  mov     qword ptr [rsp+1E0h+cbMultiByte], r12; lpcbMaxSubKeyLen
0x1800107a5  mov     [rsp+1E0h+ppv], rax; lpcSubKeys
0x1800107aa  call    cs:__imp_RegQueryInfoKeyA
0x1800107b0  mov     r15d, eax
0x1800107b3  test    rdi, rdi
0x1800107b6  jz      short loc_1800107C4
0x1800107b8  mov     rcx, rdi; hKey
0x1800107bb  call    cs:__imp_RegCloseKey
0x1800107c1  mov     rdi, r12
0x1800107c4  test    r15d, r15d
0x1800107c7  jnz     short loc_1800107E0
0x1800107c9  cmp     dword ptr [rbp+180h+MultiByteStr], r12d
0x1800107cd  jnz     short loc_1800107E0
0x1800107cf  lea     rdx, [rbp+180h+Destination]; char *
0x1800107d3  lea     rcx, [rbp+180h+var_160]; this
0x1800107d7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::DeleteSubKey(char const *)
0x1800107dc  mov     r14, [rbp+180h+var_160]
0x1800107e0  mov     r15d, 80h
0x1800107e6  lea     r8, Source; "CLSID\\"
0x1800107ed  mov     edx, r15d; SizeInBytes
0x1800107f0  lea     rcx, [rbp+180h+Destination]; Destination
0x1800107f4  call    cs:__imp_strcpy_s
0x1800107fa  test    eax, eax
0x1800107fc  jz      short loc_180010822
0x1800107fe  cmp     eax, 0Ch
0x180010801  jz      loc_1800109B8
0x180010807  cmp     eax, 16h
0x18001080a  jz      loc_1800109D9
0x180010810  cmp     eax, 22h ; '"'
0x180010813  jz      loc_1800109D9
0x180010819  cmp     eax, 50h ; 'P'
0x18001081c  jnz     loc_1800109CE
0x180010822  mov     r8, rsi; Source
0x180010825  lea     rcx, [rbp+180h+Destination]; Destination
0x180010829  mov     rdx, r15; SizeInBytes
0x18001082c  call    cs:__imp_strcat_s
0x180010832  test    eax, eax
0x180010834  jz      short loc_18001085A
0x180010836  cmp     eax, 0Ch
0x180010839  jz      loc_1800109B8
0x18001083f  cmp     eax, 16h
0x180010842  jz      loc_1800109D9
0x180010848  cmp     eax, 22h ; '"'
0x18001084b  jz      loc_1800109D9
0x180010851  cmp     eax, 50h ; 'P'
0x180010854  jnz     loc_1800109CE
0x18001085a  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180010861  mov     rdx, r15; SizeInBytes
0x180010864  lea     rcx, [rbp+180h+Destination]; Destination
0x180010868  call    cs:__imp_strcat_s
0x18001086e  test    eax, eax
0x180010870  jz      short loc_180010896
0x180010872  cmp     eax, 0Ch
0x180010875  jz      loc_1800109B8
0x18001087b  cmp     eax, 16h
0x18001087e  jz      loc_1800109D9
0x180010884  cmp     eax, 22h ; '"'
0x180010887  jz      loc_1800109D9
0x18001088d  cmp     eax, 50h ; 'P'
0x180010890  jnz     loc_1800109CE
0x180010896  lea     rax, [rbp+180h+hKey]
0x18001089a  mov     [rbp+180h+hKey], r12
0x18001089e  mov     r9d, 20019h; samDesired
0x1800108a4  mov     [rsp+1E0h+ppv], rax; phkResult
0x1800108a9  xor     r8d, r8d; ulOptions
0x1800108ac  lea     rdx, [rbp+180h+Destination]; lpSubKey
0x1800108b0  mov     rcx, r14; hKey
0x1800108b3  call    cs:__imp_RegOpenKeyExA
0x1800108b9  test    eax, eax
0x1800108bb  jnz     loc_180010945
0x1800108c1  mov     eax, r12d
0x1800108c4  test    rdi, rdi
0x1800108c7  jz      short loc_1800108D2
0x1800108c9  mov     rcx, rdi; hKey
0x1800108cc  call    cs:__imp_RegCloseKey
0x1800108d2  mov     rdi, [rbp+180h+hKey]
0x1800108d6  test    eax, eax
  ... truncated ...
```
