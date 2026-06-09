# CExtensionPersistentHandlers::LoadFromRegistry(ushort const *)

- ea: `0x18000e2b0`
- end: `0x18000e803`
- name: `?LoadFromRegistry@CExtensionPersistentHandlers@@UEAAJPEBG@Z`
- size: `1363`
- prototype: `int(CExtensionPersistentHandlers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800104f0`

## callees

- `0x180005cc0`
- `0x1800095c0`
- `0x18000e2b0`
- `0x18001f014`

## import_xrefs

- `SHELL32!__imp_GUIDFromStringW` at `0x18000e4a7`
- `SHELL32!__imp_GUIDFromStringW` at `0x18000e523`
- `SHELL32!__imp_GUIDFromStringW` at `0x18000e784`
- `SHELL32!__imp_GUIDFromStringW` at `0x18000e4a7`
- `SHELL32!__imp_GUIDFromStringW` at `0x18000e523`
- `SHELL32!__imp_GUIDFromStringW` at `0x18000e784`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e342`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e36c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e3bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e60f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e6f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e342`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e36c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e3bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e60f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e6f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e67f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e79d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e7ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e67f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e79d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e7ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e475`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e4ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e56e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e659`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e73b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e475`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e4ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e56e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e659`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e73b`

## string_xrefs

- `0x18000e5cc`: `%ws\CLSID`
- `0x18000e6ad`: `CLSID\%ws\PersistentHandler`

## pseudocode

```c
__int64 __fastcall CExtensionPersistentHandlers::LoadFromRegistry(
        CExtensionPersistentHandlers *this,
        const unsigned __int16 *a2)
{
  char *v2; // r13
  int v5; // ebx
  bool v6; // cc
  LSTATUS v7; // eax
  HKEY v8; // rcx
  LSTATUS ValueW; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  __int16 v12; // cx
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  unsigned int v15; // edi
  __int16 v16; // ax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  unsigned int v19; // edx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  _WORD pvData[40]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v26[40]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v27[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SubKey[256]; // [rsp+310h] [rbp+210h] BYREF

  v2 = (char *)this + 44;
  hKey = 0;
  *(GUID *)((char *)this + 8) = GUID_NULL;
  *((_DWORD *)this + 10) = 0;
  *(GUID *)((char *)this + 24) = GUID_NULL;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 15) = 1;
  *(GUID *)((char *)this + 44) = GUID_NULL;
  v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, a2, 0, 0x2001Fu, &hKey);
  if ( v5 != 5 )
  {
    *((_DWORD *)this + 15) = 0;
LABEL_5:
    hkey = 0;
    v6 = v5 <= 0;
    if ( v5 )
      goto LABEL_13;
    goto LABEL_6;
  }
  v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, a2, 0, 0x20019u, &hKey);
  if ( v5 )
    goto LABEL_5;
  *((_DWORD *)this + 15) = 1;
  hkey = 0;
LABEL_6:
  v7 = RegOpenKeyExW(hKey, L"PersistentHandler", 0, 0x2001Fu, &hkey);
  v5 = v7;
  switch ( v7 )
  {
    case 2:
      v5 = 0;
      goto LABEL_15;
    case 0:
      *((_DWORD *)this + 15) = 0;
      goto LABEL_15;
    case 5:
      v8 = hKey;
      *((_DWORD *)this + 15) = 1;
      v5 = RegOpenKeyExW(v8, L"PersistentHandler", 0, 0x20019u, &hkey);
      break;
  }
  v6 = v5 <= 0;
LABEL_13:
  if ( !v6 )
    v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_15:
  if ( v5 < 0 )
    goto LABEL_69;
  v5 = StrDupUsingNew(a2, (unsigned __int16 **)this + 8);
  if ( v5 < 0 )
    goto LABEL_69;
  if ( !hkey )
    goto LABEL_31;
  pcbData = 78;
  ValueW = RegGetValueW(hkey, 0, 0, 2u, 0, pvData, &pcbData);
  v5 = ValueW;
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      v5 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v5 != -2147024894 )
  {
    if ( v5 < 0 )
      goto LABEL_69;
    if ( !(unsigned int)GUIDFromStringW(pvData, (char *)this + 8) )
      goto LABEL_68;
  }
  pcbData = 78;
  v10 = RegGetValueW(hkey, 0, L"OriginalPersistentHandler", 2u, 0, pvData, &pcbData);
  v5 = v10;
  if ( v10 )
  {
    pvData[0] = 0;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( v5 != -2147024894 )
  {
    if ( v5 < 0 )
      goto LABEL_69;
    *((_DWORD *)this + 10) = 1;
    if ( !(unsigned int)GUIDFromStringW(pvData, (char *)this + 24) )
      v5 = -2147024883;
LABEL_31:
    if ( v5 < 0 )
      goto LABEL_69;
  }
  v27[0] = 0;
  pcbData = 520;
  v11 = RegGetValueW(hKey, 0, 0, 2u, 0, v27, &pcbData);
  v5 = v11;
  if ( v11 )
  {
    v12 = 0;
    v27[0] = 0;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    v12 = v27[0];
  }
  v26[0] = 0;
  if ( v5 == -2147024894 )
  {
    v5 = 0;
    v27[0] = 0;
    v12 = 0;
  }
  else if ( v5 < 0 )
  {
    goto LABEL_51;
  }
  if ( v12 )
  {
    v5 = StringCchPrintfW(SubKey, 0xFFu, L"%ws\\CLSID", v27);
    if ( v5 >= 0 )
    {
      phkResult = 0;
      v13 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult);
      v5 = v13;
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      if ( v5 < 0 )
      {
        if ( v5 == -2147024894 )
        {
          v16 = 0;
          v26[0] = 0;
          pvData[0] = 0;
          v5 = 0;
          goto LABEL_52;
        }
      }
      else
      {
        pcbData = 78;
        v14 = RegGetValueW(phkResult, 0, 0, 2u, 0, v26, &pcbData);
        v15 = v14;
        if ( v14 )
        {
          v26[0] = 0;
          if ( v14 > 0 )
            v15 = (unsigned __int16)v14 | 0x80070000;
        }
        if ( v15 == -2147024894 )
          v26[0] = 0;
        RegCloseKey(phkResult);
        v5 = 0;
        if ( v15 != -2147024894 )
          v5 = v15;
      }
    }
  }
LABEL_51:
  v16 = 0;
  pvData[0] = 0;
  if ( v5 < 0 )
    goto LABEL_69;
LABEL_52:
  if ( v26[0] )
  {
    v5 = StringCchPrintfW(SubKey, 0xFFu, L"CLSID\\%ws\\PersistentHandler", v26);
    if ( v5 < 0 )
      goto LABEL_69;
    phkResult = 0;
    v17 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult);
    v5 = v17;
    if ( v17 > 0 )
      v5 = (unsigned __int16)v17 | 0x80070000;
    if ( v5 < 0 )
    {
      if ( v5 == -2147024894 )
        v5 = 0;
      goto LABEL_69;
    }
    pcbData = 78;
    v18 = RegGetValueW(phkResult, 0, 0, 2u, 0, pvData, &pcbData);
    v19 = v18;
    if ( v18 )
    {
      pvData[0] = 0;
      if ( v18 > 0 )
        v19 = (unsigned __int16)v18 | 0x80070000;
    }
    if ( v19 == -2147024894 )
      pvData[0] = 0;
    v5 = 0;
    if ( v19 != -2147024894 )
      v5 = v19;
    RegCloseKey(phkResult);
    if ( v5 < 0 )
      goto LABEL_69;
    v16 = pvData[0];
  }
  if ( v16 && !(unsigned int)GUIDFromStringW(pvData, v2) )
LABEL_68:
    v5 = -2147024883;
LABEL_69:
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e2b0  mov     [rsp-8+arg_10], rbx
0x18000e2b5  push    rbp
0x18000e2b6  push    rsi
0x18000e2b7  push    rdi
0x18000e2b8  push    r12
0x18000e2ba  push    r13
0x18000e2bc  push    r14
0x18000e2be  push    r15
0x18000e2c0  lea     rbp, [rsp-420h]
0x18000e2c8  sub     rsp, 520h
0x18000e2cf  mov     rax, cs:__security_cookie
0x18000e2d6  xor     rax, rsp
0x18000e2d9  mov     [rbp+450h+var_40], rax
0x18000e2e0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e2e7  xor     eax, eax
0x18000e2e9  lea     r13, [rcx+2Ch]
0x18000e2ed  mov     [rsp+550h+hKey], rax
0x18000e2f2  mov     rdi, rcx
0x18000e2f5  movdqu  xmmword ptr [rcx+8], xmm0
0x18000e2fa  mov     r9d, 2001Fh; samDesired
0x18000e300  xor     r8d, r8d; ulOptions
0x18000e303  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e30a  mov     [rcx+28h], eax
0x18000e30d  mov     rsi, rdx
0x18000e310  movdqu  xmmword ptr [rcx+18h], xmm0
0x18000e315  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e31c  mov     [rcx+40h], rax
0x18000e320  mov     [rcx+48h], rax
0x18000e324  lea     rax, [rsp+550h+hKey]
0x18000e329  mov     dword ptr [rcx+3Ch], 1
0x18000e330  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000e337  movdqu  xmmword ptr [r13+0], xmm0
0x18000e33d  mov     [rsp+550h+phkResult], rax; phkResult
0x18000e342  call    cs:__imp_RegOpenKeyExW
0x18000e348  mov     ebx, eax
0x18000e34a  cmp     eax, 5
0x18000e34d  jnz     short loc_18000E38A
0x18000e34f  lea     rax, [rsp+550h+hKey]
0x18000e354  mov     r9d, 20019h; samDesired
0x18000e35a  xor     r8d, r8d; ulOptions
0x18000e35d  mov     [rsp+550h+phkResult], rax; phkResult
0x18000e362  mov     rdx, rsi; lpSubKey
0x18000e365  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000e36c  call    cs:__imp_RegOpenKeyExW
0x18000e372  mov     ebx, eax
0x18000e374  test    eax, eax
0x18000e376  jnz     short loc_18000E391
0x18000e378  mov     dword ptr [rdi+3Ch], 1
0x18000e37f  mov     [rsp+550h+hkey], 0
0x18000e388  jmp     short loc_18000E39E
0x18000e38a  mov     dword ptr [rdi+3Ch], 0
0x18000e391  mov     [rsp+550h+hkey], 0
0x18000e39a  test    ebx, ebx
0x18000e39c  jnz     short loc_18000E40C
0x18000e39e  mov     rcx, [rsp+550h+hKey]; hKey
0x18000e3a3  lea     rax, [rsp+550h+hkey]
0x18000e3a8  mov     r9d, 2001Fh; samDesired
0x18000e3ae  mov     [rsp+550h+phkResult], rax; phkResult
0x18000e3b3  xor     r8d, r8d; ulOptions
0x18000e3b6  lea     rdx, aPersistenthand; "PersistentHandler"
0x18000e3bd  call    cs:__imp_RegOpenKeyExW
0x18000e3c3  mov     ebx, eax
0x18000e3c5  cmp     eax, 2
0x18000e3c8  jnz     short loc_18000E3CE
0x18000e3ca  xor     ebx, ebx
0x18000e3cc  jmp     short loc_18000E417
0x18000e3ce  test    eax, eax
0x18000e3d0  jnz     short loc_18000E3D7
0x18000e3d2  mov     [rdi+3Ch], eax
0x18000e3d5  jmp     short loc_18000E417
0x18000e3d7  cmp     eax, 5
0x18000e3da  jnz     short loc_18000E40A
0x18000e3dc  mov     rcx, [rsp+550h+hKey]; hKey
0x18000e3e1  lea     rax, [rsp+550h+hkey]
0x18000e3e6  mov     r9d, 20019h; samDesired
0x18000e3ec  mov     [rsp+550h+phkResult], rax; phkResult
0x18000e3f1  xor     r8d, r8d; ulOptions
0x18000e3f4  mov     dword ptr [rdi+3Ch], 1
0x18000e3fb  lea     rdx, aPersistenthand; "PersistentHandler"
0x18000e402  call    cs:__imp_RegOpenKeyExW
0x18000e408  mov     ebx, eax
0x18000e40a  test    ebx, ebx
0x18000e40c  jle     short loc_18000E417
0x18000e40e  movzx   ebx, bx
0x18000e411  or      ebx, 80070000h
0x18000e417  test    ebx, ebx
0x18000e419  js      loc_18000E793
0x18000e41f  lea     rdx, [rdi+40h]; unsigned __int16 **
0x18000e423  mov     rcx, rsi; unsigned __int16 *
0x18000e426  call    ?StrDupUsingNew@@YAJPEBGPEAPEAG@Z; StrDupUsingNew(ushort const *,ushort * *)
0x18000e42b  xor     esi, esi
0x18000e42d  mov     ebx, eax
0x18000e42f  test    eax, eax
0x18000e431  js      loc_18000E793
0x18000e437  mov     rcx, [rsp+550h+hkey]; hkey
0x18000e43c  mov     r14d, 80070002h
0x18000e442  test    rcx, rcx
0x18000e445  jz      loc_18000E532
0x18000e44b  lea     rax, [rsp+550h+var_510]
0x18000e450  mov     [rsp+550h+var_510], 4Eh ; 'N'
0x18000e458  mov     [rsp+550h+pcbData], rax; pcbData
0x18000e45d  lea     r9d, [rsi+2]; dwFlags
0x18000e461  lea     rax, [rsp+550h+var_4F0]
0x18000e466  xor     r8d, r8d; lpValue
0x18000e469  mov     [rsp+550h+pvData], rax; pvData
0x18000e46e  xor     edx, edx; lpSubKey
0x18000e470  mov     [rsp+550h+phkResult], rsi; pdwType
0x18000e475  call    cs:__imp_RegGetValueW
0x18000e47b  mov     ebx, eax
0x18000e47d  test    eax, eax
0x18000e47f  jz      short loc_18000E491
0x18000e481  mov     [rsp+550h+var_4F0], si
0x18000e486  jle     short loc_18000E491
0x18000e488  movzx   ebx, ax
0x18000e48b  or      ebx, 80070000h
0x18000e491  cmp     ebx, r14d
0x18000e494  jz      short loc_18000E4B5
0x18000e496  test    ebx, ebx
0x18000e498  js      loc_18000E793
0x18000e49e  lea     rdx, [rdi+8]
0x18000e4a2  lea     rcx, [rsp+550h+var_4F0]
0x18000e4a7  call    cs:__imp_GUIDFromStringW
0x18000e4ad  test    eax, eax
0x18000e4af  jz      loc_18000E78E
0x18000e4b5  mov     rcx, [rsp+550h+hkey]; hkey
0x18000e4ba  lea     rax, [rsp+550h+var_510]
0x18000e4bf  mov     [rsp+550h+pcbData], rax; pcbData
0x18000e4c4  lea     r8, aOriginalpersis; "OriginalPersistentHandler"
0x18000e4cb  lea     rax, [rsp+550h+var_4F0]
0x18000e4d0  mov     [rsp+550h+var_510], 4Eh ; 'N'
0x18000e4d8  mov     [rsp+550h+pvData], rax; pvData
0x18000e4dd  mov     r9d, 2; dwFlags
0x18000e4e3  xor     edx, edx; lpSubKey
0x18000e4e5  mov     [rsp+550h+phkResult], rsi; pdwType
0x18000e4ea  call    cs:__imp_RegGetValueW
0x18000e4f0  mov     ebx, eax
0x18000e4f2  test    eax, eax
0x18000e4f4  jz      short loc_18000E506
0x18000e4f6  mov     [rsp+550h+var_4F0], si
0x18000e4fb  jle     short loc_18000E506
0x18000e4fd  movzx   ebx, ax
0x18000e500  or      ebx, 80070000h
0x18000e506  cmp     ebx, r14d
0x18000e509  jz      short loc_18000E53A
0x18000e50b  test    ebx, ebx
0x18000e50d  js      loc_18000E793
0x18000e513  lea     rdx, [rdi+18h]
0x18000e517  mov     dword ptr [rdi+28h], 1
0x18000e51e  lea     rcx, [rsp+550h+var_4F0]
0x18000e523  call    cs:__imp_GUIDFromStringW
0x18000e529  test    eax, eax
0x18000e52b  jnz     short loc_18000E532
0x18000e52d  mov     ebx, 8007000Dh
0x18000e532  test    ebx, ebx
0x18000e534  js      loc_18000E793
0x18000e53a  mov     rcx, [rsp+550h+hKey]; hkey
0x18000e53f  lea     rax, [rsp+550h+var_510]
0x18000e544  mov     [rsp+550h+pcbData], rax; pcbData
0x18000e549  mov     r9d, 2; dwFlags
0x18000e54f  lea     rax, [rbp+450h+var_450]
0x18000e553  mov     [rbp+450h+var_450], si
0x18000e557  mov     [rsp+550h+pvData], rax; pvData
0x18000e55c  xor     r8d, r8d; lpValue
0x18000e55f  xor     edx, edx; lpSubKey
0x18000e561  mov     [rsp+550h+phkResult], rsi; pdwType
0x18000e566  mov     [rsp+550h+var_510], 208h
0x18000e56e  call    cs:__imp_RegGetValueW
0x18000e574  mov     ebx, eax
0x18000e576  test    eax, eax
0x18000e578  jz      short loc_18000E590
0x18000e57a  mov     ecx, esi
0x18000e57c  mov     [rbp+450h+var_450], cx
0x18000e580  jle     short loc_18000E594
0x18000e582  movzx   ebx, ax
0x18000e585  mov     r15d, 80070000h
0x18000e58b  or      ebx, r15d
0x18000e58e  jmp     short loc_18000E59A
0x18000e590  movzx   ecx, [rbp+450h+var_450]
0x18000e594  mov     r15d, 80070000h
0x18000e59a  mov     [rbp+450h+var_4A0], si
0x18000e59e  mov     r12d, 0FFh
0x18000e5a4  cmp     ebx, r14d
0x18000e5a7  jnz     short loc_18000E5B4
0x18000e5a9  mov     ebx, esi
0x18000e5ab  mov     [rbp+450h+var_450], si
0x18000e5af  movzx   ecx, si
0x18000e5b2  jmp     short loc_18000E5BC
0x18000e5b4  test    ebx, ebx
0x18000e5b6  js      loc_18000E68D
0x18000e5bc  test    cx, cx
0x18000e5bf  jz      loc_18000E68D
0x18000e5c5  lea     r9, [rbp+450h+var_450]
0x18000e5c9  mov     rdx, r12; unsigned __int64
0x18000e5cc  lea     r8, aWsClsid; "%ws\\CLSID"
0x18000e5d3  lea     rcx, [rbp+450h+SubKey]; unsigned __int16 *
0x18000e5da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e5df  mov     ebx, eax
0x18000e5e1  test    eax, eax
0x18000e5e3  js      loc_18000E68D
0x18000e5e9  lea     rax, [rsp+550h+var_508]
0x18000e5ee  mov     [rsp+550h+var_508], rsi
0x18000e5f3  mov     r9d, 20019h; samDesired
0x18000e5f9  mov     [rsp+550h+phkResult], rax; phkResult
0x18000e5fe  xor     r8d, r8d; ulOptions
0x18000e601  lea     rdx, [rbp+450h+SubKey]; lpSubKey
0x18000e608  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000e60f  call    cs:__imp_RegOpenKeyExW
0x18000e615  mov     ebx, eax
0x18000e617  test    eax, eax
0x18000e619  jle     short loc_18000E621
0x18000e61b  movzx   ebx, ax
0x18000e61e  or      ebx, r15d
0x18000e621  test    ebx, ebx
0x18000e623  js      loc_18000E7DF
0x18000e629  mov     rcx, [rsp+550h+var_508]; hkey
0x18000e62e  lea     rax, [rsp+550h+var_510]
0x18000e633  mov     [rsp+550h+pcbData], rax; pcbData
0x18000e638  mov     r9d, 2; dwFlags
0x18000e63e  lea     rax, [rbp+450h+var_4A0]
0x18000e642  mov     [rsp+550h+var_510], 4Eh ; 'N'
0x18000e64a  mov     [rsp+550h+pvData], rax; pvData
0x18000e64f  xor     r8d, r8d; lpValue
0x18000e652  xor     edx, edx; lpSubKey
0x18000e654  mov     [rsp+550h+phkResult], rsi; pdwType
0x18000e659  call    cs:__imp_RegGetValueW
0x18000e65f  mov     edi, eax
0x18000e661  test    eax, eax
0x18000e663  jz      short loc_18000E671
0x18000e665  mov     [rbp+450h+var_4A0], si
0x18000e669  jle     short loc_18000E671
0x18000e66b  movzx   edi, ax
0x18000e66e  or      edi, r15d
0x18000e671  cmp     edi, r14d
0x18000e674  jnz     short loc_18000E67A
0x18000e676  mov     [rbp+450h+var_4A0], si
0x18000e67a  mov     rcx, [rsp+550h+var_508]; hKey
0x18000e67f  call    cs:__imp_RegCloseKey
0x18000e685  cmp     edi, r14d
0x18000e688  mov     ebx, esi
0x18000e68a  cmovnz  ebx, edi
0x18000e68d  mov     eax, esi
0x18000e68f  mov     [rsp+550h+var_4F0], ax
0x18000e694  test    ebx, ebx
0x18000e696  js      loc_18000E793
0x18000e69c  cmp     [rbp+450h+var_4A0], si
0x18000e6a0  jz      loc_18000E777
0x18000e6a6  lea     r9, [rbp+450h+var_4A0]
0x18000e6aa  mov     rdx, r12; unsigned __int64
0x18000e6ad  lea     r8, aClsidWsPersist; "CLSID\\%ws\\PersistentHandler"
0x18000e6b4  lea     rcx, [rbp+450h+SubKey]; unsigned __int16 *
0x18000e6bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e6c0  mov     ebx, eax
0x18000e6c2  test    eax, eax
0x18000e6c4  js      loc_18000E793
0x18000e6ca  lea     rax, [rsp+550h+var_508]
0x18000e6cf  mov     [rsp+550h+var_508], rsi
0x18000e6d4  mov     r9d, 20019h; samDesired
0x18000e6da  mov     [rsp+550h+phkResult], rax; phkResult
0x18000e6df  xor     r8d, r8d; ulOptions
0x18000e6e2  lea     rdx, [rbp+450h+SubKey]; lpSubKey
0x18000e6e9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000e6f0  call    cs:__imp_RegOpenKeyExW
0x18000e6f6  mov     ebx, eax
0x18000e6f8  test    eax, eax
0x18000e6fa  jle     short loc_18000E702
0x18000e6fc  movzx   ebx, ax
0x18000e6ff  or      ebx, r15d
0x18000e702  test    ebx, ebx
0x18000e704  js      loc_18000E7FA
0x18000e70a  mov     rcx, [rsp+550h+var_508]; hkey
0x18000e70f  lea     rax, [rsp+550h+var_510]
0x18000e714  mov     [rsp+550h+pcbData], rax; pcbData
0x18000e719  mov     r9d, 2; dwFlags
0x18000e71f  lea     rax, [rsp+550h+var_4F0]
0x18000e724  mov     [rsp+550h+var_510], 4Eh ; 'N'
0x18000e72c  mov     [rsp+550h+pvData], rax; pvData
0x18000e731  xor     r8d, r8d; lpValue
0x18000e734  xor     edx, edx; lpSubKey
0x18000e736  mov     [rsp+550h+phkResult], rsi; pdwType
0x18000e73b  call    cs:__imp_RegGetValueW
0x18000e741  mov     edx, eax
0x18000e743  test    eax, eax
0x18000e745  jz      short loc_18000E754
0x18000e747  mov     [rsp+550h+var_4F0], si
0x18000e74c  jle     short loc_18000E754
0x18000e74e  movzx   edx, ax
0x18000e751  or      edx, r15d
0x18000e754  cmp     edx, r14d
0x18000e757  jnz     short loc_18000E75E
0x18000e759  mov     [rsp+550h+var_4F0], si
0x18000e75e  mov     rcx, [rsp+550h+var_508]; hKey
0x18000e763  mov     ebx, esi
0x18000e765  cmovnz  ebx, edx
0x18000e768  call    cs:__imp_RegCloseKey
0x18000e76e  test    ebx, ebx
0x18000e770  js      short loc_18000E793
0x18000e772  movzx   eax, [rsp+550h+var_4F0]
0x18000e777  test    ax, ax
0x18000e77a  jz      short loc_18000E793
0x18000e77c  mov     rdx, r13
  ... truncated ...
```
