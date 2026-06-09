# CSoftDist::ICDAdvertise(int)

- ea: `0x1800c05b8`
- end: `0x1800c0c3e`
- name: `?ICDAdvertise@CSoftDist@@AEAAJH@Z`
- size: `1670`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800bf7c8`

## callees

- `0x18002fee0`
- `0x18004d7f0`
- `0x18005789c`
- `0x18007bcc8`
- `0x1800c05b8`
- `0x1800c0c44`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c0639`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c06d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c07c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c09af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c0a43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c0639`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c06d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c07c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c09af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c0a43`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c075c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0796`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c084f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c08f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0a79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0ad4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0b1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0b5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c075c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0796`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c084f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c08f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0a79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0ad4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0b1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c0b5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0ba1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0bbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0bd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0bf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0c0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0ba1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0bbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0bd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0bf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0c0c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800c0a96`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800c0a96`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c067d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c0713`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c0809`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c09f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c067d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c0713`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c0809`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c09f5`

## string_xrefs

- `0x1800c0a8f`: `Precache`
- `0x1800c0784`: `Installer`
- `0x1800c0775`: `MSICD`

## pseudocode

```c
__int64 __fastcall CSoftDist::ICDAdvertise(CSoftDist *this, int a2)
{
  BYTE *v3; // rdi
  LSTATUS v4; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  bool v7; // cc
  const BYTE *v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // rax
  const BYTE *v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // r14
  int v14; // r12d
  _QWORD *v15; // r13
  LPCWCH *v16; // rdi
  int v17; // eax
  __int64 v18; // rax
  LSTATUS v19; // r14d
  int v20; // ebx
  int v21; // r13d
  __int64 v22; // rax
  const BYTE *v23; // rcx
  __int64 v24; // rax
  const BYTE *v25; // rcx
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v28; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v30; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  LPCSTR lpSubKey; // [rsp+78h] [rbp-88h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp-80h] BYREF
  HKEY v34; // [rsp+88h] [rbp-78h] BYREF
  BYTE v35[272]; // [rsp+90h] [rbp-70h] BYREF
  CHAR ValueName[288]; // [rsp+1A0h] [rbp+A0h] BYREF

  *(_DWORD *)Data = a2;
  hKey = 0;
  phkResult = 0;
  v30 = 0;
  v28 = 0;
  v34 = 0;
  lpData = 0;
  lpSubKey = 0;
  v3 = 0;
  if ( RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Code Store Database\\Distribution Units",
         0,
         0xF003Fu,
         &hKey)
    && (v4 = RegCreateKeyExA(
               HKEY_LOCAL_MACHINE,
               "Software\\Microsoft\\Code Store Database\\Distribution Units",
               0,
               0,
               0,
               0x2000000u,
               0,
               &hKey,
               0),
        (v5 = v4) != 0) )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v5 = Unicode2Ansi(*((LPCWCH *)this + 2), (CHAR **)&lpSubKey);
    if ( v5 >= 0 )
    {
      if ( !RegOpenKeyExA(hKey, lpSubKey, 0, 0xF003Fu, &phkResult)
        || (v6 = RegCreateKeyExA(hKey, lpSubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0), v7 = v6 <= 0, !v6) )
      {
        v8 = (const BYTE *)*((_QWORD *)this + 7);
        v9 = -1;
        if ( !v8 )
          goto LABEL_76;
        v10 = -1;
        do
          ++v10;
        while ( v8[v10] );
        v6 = RegSetValueExA(phkResult, 0, 0, 1u, v8, v10 + 1);
        v7 = v6 <= 0;
        if ( !v6 )
        {
LABEL_76:
          v6 = RegSetValueExA(phkResult, "Installer", 0, 1u, "MSICD", 9u);
          v7 = v6 <= 0;
          if ( !v6 )
          {
            if ( !RegOpenKeyExA(phkResult, "DownloadInformation", 0, 0xF003Fu, &v30)
              || (v6 = RegCreateKeyExA(phkResult, "DownloadInformation", 0, 0, 0, 0x2000000u, 0, &v30, 0),
                  v7 = v6 <= 0,
                  !v6) )
            {
              v11 = (const BYTE *)*((_QWORD *)this + 6);
              if ( !v11 )
                goto LABEL_19;
              v12 = -1;
              do
                ++v12;
              while ( v11[v12] );
              v6 = RegSetValueExA(v30, "CDF", 0, 1u, v11, v12 + 1);
              v7 = v6 <= 0;
              if ( !v6 )
              {
LABEL_19:
                v13 = (_QWORD *)*((_QWORD *)this + 11);
                v14 = 1;
                while ( v13 )
                {
                  v15 = (_QWORD *)*v13;
                  v16 = (LPCWCH *)v13[2];
                  if ( v14 > 1 )
                    StringCchPrintfA(ValueName, 0x111u, "%s%d", "CODEBASE", v14);
                  else
                    StringCchCopyA(ValueName, 0x111u, "CODEBASE");
                  v17 = Unicode2Ansi(*v16, (CHAR **)&lpData);
                  v3 = lpData;
                  if ( v17 < 0 )
                  {
                    v5 = -2147024882;
                    goto LABEL_59;
                  }
                  v18 = -1;
                  do
                    ++v18;
                  while ( lpData[v18] );
                  v19 = RegSetValueExA(v30, ValueName, 0, 1u, lpData, v18);
                  if ( v19 )
                  {
                    if ( v3 )
                    {
                      operator delete(v3);
                      v3 = 0;
                    }
                    if ( v19 <= 0 )
                    {
                      v5 = v19;
                      goto LABEL_59;
                    }
                    v20 = (unsigned __int16)v19;
                    goto LABEL_58;
                  }
                  v13 = v15;
                  if ( v3 )
                  {
                    operator delete(v3);
                    v3 = 0;
                    lpData = 0;
                  }
                  ++v14;
                }
                StringCchPrintfA(
                  (char *)v35,
                  0x104u,
                  "%d,%d,%d,%d",
                  *((unsigned __int16 *)this + 13),
                  *((unsigned __int16 *)this + 12),
                  *((unsigned __int16 *)this + 15),
                  *((unsigned __int16 *)this + 14));
                if ( !RegOpenKeyExA(phkResult, "AvailableVersion", 0, 0xF003Fu, &v28)
                  || (v6 = RegCreateKeyExA(phkResult, "AvailableVersion", 0, 0, 0, 0x2000000u, 0, &v28, 0),
                      v7 = v6 <= 0,
                      !v6) )
                {
                  v21 = *(_DWORD *)Data;
                  if ( *(_DWORD *)Data || IsAbstractDifferent(v28, *((char **)this + 9)) )
                  {
                    if ( !RegOpenKeyExA(phkResult, "AdvertisedVersion", 0, 0x2000000u, &v34) )
                    {
                      *(_DWORD *)Data = 0;
                      RegSetValueExA(v34, "AdState", 0, 4u, Data, 4u);
                    }
                    if ( v21 )
                      RegDeleteValueA(v28, "Precache");
                  }
                  v22 = -1;
                  do
                    ++v22;
                  while ( v35[v22] );
                  v6 = RegSetValueExA(v28, 0, 0, 1u, v35, v22 + 1);
                  v7 = v6 <= 0;
                  if ( !v6 )
                  {
                    v23 = (const BYTE *)*((_QWORD *)this + 10);
                    if ( !v23 )
                      goto LABEL_52;
                    v24 = -1;
                    do
                      ++v24;
                    while ( v23[v24] );
                    v6 = RegSetValueExA(v28, "HREF", 0, 1u, v23, v24 + 1);
                    v7 = v6 <= 0;
                    if ( !v6 )
                    {
LABEL_52:
                      v25 = (const BYTE *)*((_QWORD *)this + 9);
                      if ( !v25 )
                        goto LABEL_59;
                      do
                        ++v9;
                      while ( v25[v9] );
                      v6 = RegSetValueExA(v28, "Abstract", 0, 1u, v25, v9 + 1);
                      v7 = v6 <= 0;
                      if ( !v6 )
                        goto LABEL_59;
                    }
                  }
                }
              }
            }
          }
        }
      }
      if ( v7 )
      {
        v5 = v6;
      }
      else
      {
        v20 = (unsigned __int16)v6;
LABEL_58:
        v5 = v20 | 0x80070000;
      }
    }
LABEL_59:
    if ( lpSubKey )
      operator delete((void *)lpSubKey);
    if ( v3 )
      operator delete(v3);
  }
  if ( v30 )
  {
    RegCloseKey(v30);
    v30 = 0;
  }
  if ( v28 )
  {
    RegCloseKey(v28);
    v28 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v34 )
    RegCloseKey(v34);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c05b8  push    rbp
0x1800c05ba  push    rbx
0x1800c05bb  push    rsi
0x1800c05bc  push    rdi
0x1800c05bd  push    r12
0x1800c05bf  push    r13
0x1800c05c1  push    r14
0x1800c05c3  push    r15
0x1800c05c5  lea     rbp, [rsp-1D8h]
0x1800c05cd  sub     rsp, 2D8h
0x1800c05d4  mov     rax, cs:__security_cookie
0x1800c05db  xor     rax, rsp
0x1800c05de  mov     [rbp+210h+var_50], rax
0x1800c05e5  xor     r12d, r12d
0x1800c05e8  mov     dword ptr [rsp+310h+Data], edx
0x1800c05ec  mov     r15, rcx
0x1800c05ef  mov     [rsp+310h+hKey], r12
0x1800c05f4  lea     rax, [rsp+310h+hKey]
0x1800c05f9  mov     [rsp+310h+var_2C0], r12
0x1800c05fe  mov     esi, 0F003Fh
0x1800c0603  mov     [rsp+310h+var_2A8], r12
0x1800c0608  mov     rbx, 0FFFFFFFF80000002h
0x1800c060f  mov     [rsp+310h+var_2B8], r12
0x1800c0614  mov     r9d, esi; samDesired
0x1800c0617  mov     [rbp+210h+var_288], r12
0x1800c061b  mov     rcx, rbx; hKey
0x1800c061e  mov     [rbp+210h+lpData], r12
0x1800c0622  xor     r8d, r8d; ulOptions
0x1800c0625  mov     [rsp+310h+lpSubKey], r12
0x1800c062a  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800c0631  mov     [rsp+310h+phkResult], rax; phkResult
0x1800c0636  mov     edi, r12d
0x1800c0639  call    cs:__imp_RegOpenKeyExA
0x1800c0640  nop     dword ptr [rax+rax+00h]
0x1800c0645  mov     r14d, 2000000h
0x1800c064b  test    eax, eax
0x1800c064d  jz      short loc_1800C06A3
0x1800c064f  mov     [rsp+310h+lpdwDisposition], r12; lpdwDisposition
0x1800c0654  lea     rax, [rsp+310h+hKey]
0x1800c0659  mov     [rsp+310h+var_2D8], rax; phkResult
0x1800c065e  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800c0665  mov     [rsp+310h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800c066a  xor     r9d, r9d; lpClass
0x1800c066d  mov     [rsp+310h+samDesired], r14d; samDesired
0x1800c0672  xor     r8d, r8d; Reserved
0x1800c0675  mov     rcx, rbx; hKey
0x1800c0678  mov     dword ptr [rsp+310h+phkResult], r12d; dwOptions
0x1800c067d  call    cs:__imp_RegCreateKeyExA
0x1800c0684  nop     dword ptr [rax+rax+00h]
0x1800c0689  mov     ebx, eax
0x1800c068b  test    eax, eax
0x1800c068d  jz      short loc_1800C06A3
0x1800c068f  jle     loc_1800C0B97
0x1800c0695  movzx   ebx, ax
0x1800c0698  or      ebx, 80070000h
0x1800c069e  jmp     loc_1800C0B97
0x1800c06a3  mov     rcx, [r15+10h]; lpWideCharStr
0x1800c06a7  lea     rdx, [rsp+310h+lpSubKey]
0x1800c06ac  call    Unicode2Ansi
0x1800c06b1  mov     ebx, eax
0x1800c06b3  test    eax, eax
0x1800c06b5  js      loc_1800C0B79
0x1800c06bb  mov     rdx, [rsp+310h+lpSubKey]; lpSubKey
0x1800c06c0  lea     rax, [rsp+310h+var_2C0]
0x1800c06c5  mov     rcx, [rsp+310h+hKey]; hKey
0x1800c06ca  mov     r9d, esi; samDesired
0x1800c06cd  xor     r8d, r8d; ulOptions
0x1800c06d0  mov     [rsp+310h+phkResult], rax; phkResult
0x1800c06d5  call    cs:__imp_RegOpenKeyExA
0x1800c06dc  nop     dword ptr [rax+rax+00h]
0x1800c06e1  test    eax, eax
0x1800c06e3  jz      short loc_1800C0727
0x1800c06e5  mov     rdx, [rsp+310h+lpSubKey]; lpSubKey
0x1800c06ea  lea     rax, [rsp+310h+var_2C0]
0x1800c06ef  mov     rcx, [rsp+310h+hKey]; hKey
0x1800c06f4  xor     r9d, r9d; lpClass
0x1800c06f7  mov     [rsp+310h+lpdwDisposition], r12; lpdwDisposition
0x1800c06fc  xor     r8d, r8d; Reserved
0x1800c06ff  mov     [rsp+310h+var_2D8], rax; phkResult
0x1800c0704  mov     [rsp+310h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800c0709  mov     [rsp+310h+samDesired], r14d; samDesired
0x1800c070e  mov     dword ptr [rsp+310h+phkResult], r12d; dwOptions
0x1800c0713  call    cs:__imp_RegCreateKeyExA
0x1800c071a  nop     dword ptr [rax+rax+00h]
0x1800c071f  test    eax, eax
0x1800c0721  jnz     loc_1800C0B6A
0x1800c0727  mov     rcx, [r15+38h]
0x1800c072b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800c072f  lea     r13d, [rsi+2]
0x1800c0733  test    rcx, rcx
0x1800c0736  jz      short loc_1800C0770
0x1800c0738  mov     rax, rsi
0x1800c073b  inc     rax
0x1800c073e  cmp     [rcx+rax], r12b
0x1800c0742  jnz     short loc_1800C073B
0x1800c0744  inc     eax
0x1800c0746  mov     r9d, r13d; dwType
0x1800c0749  mov     [rsp+310h+samDesired], eax; cbData
0x1800c074d  xor     r8d, r8d; Reserved
0x1800c0750  mov     [rsp+310h+phkResult], rcx; lpData
0x1800c0755  xor     edx, edx; lpValueName
0x1800c0757  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800c075c  call    cs:__imp_RegSetValueExA
0x1800c0763  nop     dword ptr [rax+rax+00h]
0x1800c0768  test    eax, eax
0x1800c076a  jnz     loc_1800C0B6A
0x1800c0770  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800c0775  lea     rax, aMsicd; "MSICD"
0x1800c077c  mov     [rsp+310h+samDesired], 9; cbData
0x1800c0784  lea     rdx, aInstaller; "Installer"
0x1800c078b  mov     r9d, r13d; dwType
0x1800c078e  mov     [rsp+310h+phkResult], rax; lpData
0x1800c0793  xor     r8d, r8d; Reserved
0x1800c0796  call    cs:__imp_RegSetValueExA
0x1800c079d  nop     dword ptr [rax+rax+00h]
0x1800c07a2  test    eax, eax
0x1800c07a4  jnz     loc_1800C0B6A
0x1800c07aa  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800c07af  lea     rax, [rsp+310h+var_2A8]
0x1800c07b4  mov     r9d, 0F003Fh; samDesired
0x1800c07ba  mov     [rsp+310h+phkResult], rax; phkResult
0x1800c07bf  xor     r8d, r8d; ulOptions
0x1800c07c2  lea     rdx, aDownloadinform; "DownloadInformation"
0x1800c07c9  call    cs:__imp_RegOpenKeyExA
0x1800c07d0  nop     dword ptr [rax+rax+00h]
0x1800c07d5  test    eax, eax
0x1800c07d7  jz      short loc_1800C081D
0x1800c07d9  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800c07de  lea     rax, [rsp+310h+var_2A8]
0x1800c07e3  mov     [rsp+310h+lpdwDisposition], r12; lpdwDisposition
0x1800c07e8  lea     rdx, aDownloadinform; "DownloadInformation"
0x1800c07ef  mov     [rsp+310h+var_2D8], rax; phkResult
0x1800c07f4  xor     r9d, r9d; lpClass
0x1800c07f7  mov     [rsp+310h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800c07fc  xor     r8d, r8d; Reserved
0x1800c07ff  mov     [rsp+310h+samDesired], r14d; samDesired
0x1800c0804  mov     dword ptr [rsp+310h+phkResult], r12d; dwOptions
0x1800c0809  call    cs:__imp_RegCreateKeyExA
0x1800c0810  nop     dword ptr [rax+rax+00h]
0x1800c0815  test    eax, eax
0x1800c0817  jnz     loc_1800C0B6A
0x1800c081d  mov     rcx, [r15+30h]
0x1800c0821  test    rcx, rcx
0x1800c0824  jz      short loc_1800C0863
0x1800c0826  mov     rax, rsi
0x1800c0829  inc     rax
0x1800c082c  cmp     [rcx+rax], r12b
0x1800c0830  jnz     short loc_1800C0829
0x1800c0832  inc     eax
0x1800c0834  lea     rdx, aCdf; "CDF"
0x1800c083b  mov     [rsp+310h+samDesired], eax; cbData
0x1800c083f  mov     r9d, r13d; dwType
0x1800c0842  mov     [rsp+310h+phkResult], rcx; lpData
0x1800c0847  xor     r8d, r8d; Reserved
0x1800c084a  mov     rcx, [rsp+310h+var_2A8]; hKey
0x1800c084f  call    cs:__imp_RegSetValueExA
0x1800c0856  nop     dword ptr [rax+rax+00h]
0x1800c085b  test    eax, eax
0x1800c085d  jnz     loc_1800C0B6A
0x1800c0863  mov     r14, [r15+58h]
0x1800c0867  mov     r12d, r13d
0x1800c086a  test    r14, r14
0x1800c086d  jz      loc_1800C095B
0x1800c0873  mov     r13, [r14]
0x1800c0876  mov     edx, 111h; unsigned __int64
0x1800c087b  mov     rdi, [r14+10h]
0x1800c087f  lea     rcx, [rbp+210h+ValueName]; char *
0x1800c0886  cmp     r12d, 1
0x1800c088a  jg      short loc_1800C089A
0x1800c088c  lea     r8, aCodebase_0; "CODEBASE"
0x1800c0893  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800c0898  jmp     short loc_1800C08B2
0x1800c089a  lea     r9, aCodebase_0; "CODEBASE"
0x1800c08a1  mov     dword ptr [rsp+310h+phkResult], r12d
0x1800c08a6  lea     r8, aSD; "%s%d"
0x1800c08ad  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800c08b2  mov     rcx, [rdi]; lpWideCharStr
0x1800c08b5  lea     rdx, [rbp+210h+lpData]
0x1800c08b9  call    Unicode2Ansi
0x1800c08be  mov     rdi, [rbp+210h+lpData]
0x1800c08c2  test    eax, eax
0x1800c08c4  js      loc_1800C094E
0x1800c08ca  mov     rax, rsi
0x1800c08cd  inc     rax
0x1800c08d0  cmp     byte ptr [rdi+rax], 0
0x1800c08d4  jnz     short loc_1800C08CD
0x1800c08d6  mov     rcx, [rsp+310h+var_2A8]; hKey
0x1800c08db  lea     rdx, [rbp+210h+ValueName]; lpValueName
0x1800c08e2  mov     [rsp+310h+samDesired], eax; cbData
0x1800c08e6  mov     r9d, 1; dwType
0x1800c08ec  xor     r8d, r8d; Reserved
0x1800c08ef  mov     [rsp+310h+phkResult], rdi; lpData
0x1800c08f4  call    cs:__imp_RegSetValueExA
0x1800c08fb  nop     dword ptr [rax+rax+00h]
0x1800c0900  mov     r14d, eax
0x1800c0903  test    eax, eax
0x1800c0905  jnz     short loc_1800C0925
0x1800c0907  mov     r14, r13
0x1800c090a  test    rdi, rdi
0x1800c090d  jz      short loc_1800C091D
0x1800c090f  mov     rcx, rdi; void *
0x1800c0912  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c0917  xor     edi, edi
0x1800c0919  mov     [rbp+210h+lpData], rdi
0x1800c091d  inc     r12d
0x1800c0920  jmp     loc_1800C086A
0x1800c0925  xor     r12d, r12d
0x1800c0928  test    rdi, rdi
0x1800c092b  jz      short loc_1800C0938
0x1800c092d  mov     rcx, rdi; void *
0x1800c0930  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c0935  mov     edi, r12d
0x1800c0938  test    r14d, r14d
0x1800c093b  jg      short loc_1800C0945
0x1800c093d  mov     ebx, r14d
0x1800c0940  jmp     loc_1800C0B79
0x1800c0945  movzx   ebx, r14w
0x1800c0949  jmp     loc_1800C0B73
0x1800c094e  mov     ebx, 8007000Eh
0x1800c0953  xor     r12d, r12d
0x1800c0956  jmp     loc_1800C0B79
0x1800c095b  movzx   ecx, word ptr [r15+1Ch]
0x1800c0960  lea     r8, aDDDD_0; "%d,%d,%d,%d"
0x1800c0967  movzx   edx, word ptr [r15+1Eh]
0x1800c096c  movzx   eax, word ptr [r15+18h]
0x1800c0971  movzx   r9d, word ptr [r15+1Ah]
0x1800c0976  mov     dword ptr [rsp+310h+lpSecurityAttributes], ecx
0x1800c097a  lea     rcx, [rbp+210h+var_280]; char *
0x1800c097e  mov     [rsp+310h+samDesired], edx
0x1800c0982  mov     edx, 104h; unsigned __int64
0x1800c0987  mov     dword ptr [rsp+310h+phkResult], eax
0x1800c098b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800c0990  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800c0995  lea     rax, [rsp+310h+var_2B8]
0x1800c099a  mov     r9d, 0F003Fh; samDesired
0x1800c09a0  mov     [rsp+310h+phkResult], rax; phkResult
0x1800c09a5  xor     r8d, r8d; ulOptions
0x1800c09a8  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800c09af  call    cs:__imp_RegOpenKeyExA
0x1800c09b6  nop     dword ptr [rax+rax+00h]
0x1800c09bb  xor     r12d, r12d
0x1800c09be  test    eax, eax
0x1800c09c0  jz      short loc_1800C0A09
0x1800c09c2  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800c09c7  lea     rax, [rsp+310h+var_2B8]
0x1800c09cc  mov     [rsp+310h+lpdwDisposition], r12; lpdwDisposition
0x1800c09d1  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800c09d8  mov     [rsp+310h+var_2D8], rax; phkResult
0x1800c09dd  xor     r9d, r9d; lpClass
0x1800c09e0  mov     [rsp+310h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800c09e5  xor     r8d, r8d; Reserved
0x1800c09e8  mov     [rsp+310h+samDesired], 2000000h; samDesired
0x1800c09f0  mov     dword ptr [rsp+310h+phkResult], r12d; dwOptions
0x1800c09f5  call    cs:__imp_RegCreateKeyExA
0x1800c09fc  nop     dword ptr [rax+rax+00h]
0x1800c0a01  test    eax, eax
0x1800c0a03  jnz     loc_1800C0B6A
0x1800c0a09  mov     r13d, dword ptr [rsp+310h+Data]
0x1800c0a0e  test    r13d, r13d
0x1800c0a11  jnz     short loc_1800C0A25
0x1800c0a13  mov     rdx, [r15+48h]; char *
0x1800c0a17  mov     rcx, [rsp+310h+var_2B8]; HKEY
0x1800c0a1c  call    ?IsAbstractDifferent@@YAHPEAUHKEY__@@PEAD@Z; IsAbstractDifferent(HKEY__ *,char *)
0x1800c0a21  test    eax, eax
0x1800c0a23  jz      short loc_1800C0AA2
0x1800c0a25  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800c0a2a  lea     rax, [rbp+210h+var_288]
0x1800c0a2e  mov     r9d, 2000000h; samDesired
0x1800c0a34  mov     [rsp+310h+phkResult], rax; phkResult
0x1800c0a39  xor     r8d, r8d; ulOptions
0x1800c0a3c  lea     rdx, aAdvertisedvers; "AdvertisedVersion"
0x1800c0a43  call    cs:__imp_RegOpenKeyExA
0x1800c0a4a  nop     dword ptr [rax+rax+00h]
0x1800c0a4f  test    eax, eax
0x1800c0a51  jnz     short loc_1800C0A85
0x1800c0a53  mov     rcx, [rbp+210h+var_288]; hKey
0x1800c0a57  lea     r9d, [rax+4]; dwType
0x1800c0a5b  lea     rax, [rsp+310h+Data]
0x1800c0a60  mov     [rsp+310h+samDesired], r9d; cbData
0x1800c0a65  xor     r8d, r8d; Reserved
0x1800c0a68  mov     [rsp+310h+phkResult], rax; lpData
0x1800c0a6d  lea     rdx, aAdstate; "AdState"
0x1800c0a74  mov     dword ptr [rsp+310h+Data], r12d
0x1800c0a79  call    cs:__imp_RegSetValueExA
0x1800c0a80  nop     dword ptr [rax+rax+00h]
0x1800c0a85  test    r13d, r13d
0x1800c0a88  jz      short loc_1800C0AA2
0x1800c0a8a  mov     rcx, [rsp+310h+var_2B8]; hKey
0x1800c0a8f  lea     rdx, aPrecache_0; "Precache"
0x1800c0a96  call    cs:__imp_RegDeleteValueA
0x1800c0a9d  nop     dword ptr [rax+rax+00h]
0x1800c0aa2  lea     rcx, [rbp+210h+var_280]
0x1800c0aa6  mov     rax, rsi
0x1800c0aa9  inc     rax
0x1800c0aac  cmp     [rcx+rax], r12b
0x1800c0ab0  jnz     short loc_1800C0AA9
0x1800c0ab2  mov     rcx, [rsp+310h+var_2B8]; hKey
0x1800c0ab7  inc     eax
0x1800c0ab9  mov     [rsp+310h+samDesired], eax; cbData
0x1800c0abd  mov     r14d, 1
  ... truncated ...
```
