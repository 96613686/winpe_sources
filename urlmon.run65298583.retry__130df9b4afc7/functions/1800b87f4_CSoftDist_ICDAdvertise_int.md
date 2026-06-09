# CSoftDist::ICDAdvertise(int)

- ea: `0x1800b87f4`
- end: `0x1800b8de7`
- name: `?ICDAdvertise@CSoftDist@@AEAAJH@Z`
- size: `1523`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b7a58`

## callees

- `0x180030880`
- `0x180044b84`
- `0x18005cc10`
- `0x1800763a8`
- `0x1800b87f4`
- `0x1800b8df0`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b8875`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b8905`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b89e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b8bab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b8c33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b8875`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b8905`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b89e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b8bab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b8c33`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8980`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b89b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8a5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8af6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8c63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8cb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8d28`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8980`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b89b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8a5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8af6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8c63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8cb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b8d28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8d69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8d7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8da8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8dbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8d69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8d7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8da8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8dbc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800b8c7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800b8c7a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b88b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b893d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b8a1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b8beb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b88b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b893d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b8a1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b8beb`

## string_xrefs

- `0x1800b8c73`: `Precache`
- `0x1800b89a2`: `Installer`
- `0x1800b8993`: `MSICD`

## pseudocode

```c
__int64 __fastcall CSoftDist::ICDAdvertise(CSoftDist *this, int a2)
{
  BYTE *v3; // rdi
  LSTATUS v4; // eax
  signed int v5; // ebx
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
  LPCSTR lpSubKey; // [rsp+78h] [rbp-88h]
  BYTE *lpData; // [rsp+80h] [rbp-80h]
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
    v5 = Unicode2Ansi(*((LPCWCH *)this + 2));
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
                  v17 = Unicode2Ansi(*v16);
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
0x1800b87f4  push    rbp
0x1800b87f6  push    rbx
0x1800b87f7  push    rsi
0x1800b87f8  push    rdi
0x1800b87f9  push    r12
0x1800b87fb  push    r13
0x1800b87fd  push    r14
0x1800b87ff  push    r15
0x1800b8801  lea     rbp, [rsp-1D8h]
0x1800b8809  sub     rsp, 2D8h
0x1800b8810  mov     rax, cs:__security_cookie
0x1800b8817  xor     rax, rsp
0x1800b881a  mov     [rbp+210h+var_50], rax
0x1800b8821  xor     r12d, r12d
0x1800b8824  mov     dword ptr [rsp+310h+Data], edx
0x1800b8828  mov     r15, rcx
0x1800b882b  mov     [rsp+310h+hKey], r12
0x1800b8830  lea     rax, [rsp+310h+hKey]
0x1800b8835  mov     [rsp+310h+var_2C0], r12
0x1800b883a  mov     esi, 0F003Fh
0x1800b883f  mov     [rsp+310h+var_2A8], r12
0x1800b8844  mov     rbx, 0FFFFFFFF80000002h
0x1800b884b  mov     [rsp+310h+var_2B8], r12
0x1800b8850  mov     r9d, esi; samDesired
0x1800b8853  mov     [rbp+210h+var_288], r12
0x1800b8857  mov     rcx, rbx; hKey
0x1800b885a  mov     [rbp+210h+lpData], r12
0x1800b885e  xor     r8d, r8d; ulOptions
0x1800b8861  mov     [rsp+310h+lpSubKey], r12
0x1800b8866  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800b886d  mov     [rsp+310h+phkResult], rax; phkResult
0x1800b8872  mov     edi, r12d
0x1800b8875  call    cs:__imp_RegOpenKeyExA
0x1800b887b  mov     r14d, 2000000h
0x1800b8881  test    eax, eax
0x1800b8883  jz      short loc_1800B88D3
0x1800b8885  mov     [rsp+310h+lpdwDisposition], r12; lpdwDisposition
0x1800b888a  lea     rax, [rsp+310h+hKey]
0x1800b888f  mov     [rsp+310h+var_2D8], rax; phkResult
0x1800b8894  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800b889b  mov     [rsp+310h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800b88a0  xor     r9d, r9d; lpClass
0x1800b88a3  mov     [rsp+310h+samDesired], r14d; samDesired
0x1800b88a8  xor     r8d, r8d; Reserved
0x1800b88ab  mov     rcx, rbx; hKey
0x1800b88ae  mov     dword ptr [rsp+310h+phkResult], r12d; dwOptions
0x1800b88b3  call    cs:__imp_RegCreateKeyExA
0x1800b88b9  mov     ebx, eax
0x1800b88bb  test    eax, eax
0x1800b88bd  jz      short loc_1800B88D3
0x1800b88bf  jle     loc_1800B8D5F
0x1800b88c5  movzx   ebx, ax
0x1800b88c8  or      ebx, 80070000h
0x1800b88ce  jmp     loc_1800B8D5F
0x1800b88d3  mov     rcx, [r15+10h]; lpWideCharStr
0x1800b88d7  lea     rdx, [rsp+310h+lpSubKey]
0x1800b88dc  call    Unicode2Ansi
0x1800b88e1  mov     ebx, eax
0x1800b88e3  test    eax, eax
0x1800b88e5  js      loc_1800B8D41
0x1800b88eb  mov     rdx, [rsp+310h+lpSubKey]; lpSubKey
0x1800b88f0  lea     rax, [rsp+310h+var_2C0]
0x1800b88f5  mov     rcx, [rsp+310h+hKey]; hKey
0x1800b88fa  mov     r9d, esi; samDesired
0x1800b88fd  xor     r8d, r8d; ulOptions
0x1800b8900  mov     [rsp+310h+phkResult], rax; phkResult
0x1800b8905  call    cs:__imp_RegOpenKeyExA
0x1800b890b  test    eax, eax
0x1800b890d  jz      short loc_1800B894B
0x1800b890f  mov     rdx, [rsp+310h+lpSubKey]; lpSubKey
0x1800b8914  lea     rax, [rsp+310h+var_2C0]
0x1800b8919  mov     rcx, [rsp+310h+hKey]; hKey
0x1800b891e  xor     r9d, r9d; lpClass
0x1800b8921  mov     [rsp+310h+lpdwDisposition], r12; lpdwDisposition
0x1800b8926  xor     r8d, r8d; Reserved
0x1800b8929  mov     [rsp+310h+var_2D8], rax; phkResult
0x1800b892e  mov     [rsp+310h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800b8933  mov     [rsp+310h+samDesired], r14d; samDesired
0x1800b8938  mov     dword ptr [rsp+310h+phkResult], r12d; dwOptions
0x1800b893d  call    cs:__imp_RegCreateKeyExA
0x1800b8943  test    eax, eax
0x1800b8945  jnz     loc_1800B8D32
0x1800b894b  mov     rcx, [r15+38h]
0x1800b894f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b8953  lea     r13d, [rsi+2]
0x1800b8957  test    rcx, rcx
0x1800b895a  jz      short loc_1800B898E
0x1800b895c  mov     rax, rsi
0x1800b895f  inc     rax
0x1800b8962  cmp     [rcx+rax], r12b
0x1800b8966  jnz     short loc_1800B895F
0x1800b8968  inc     eax
0x1800b896a  mov     r9d, r13d; dwType
0x1800b896d  mov     [rsp+310h+samDesired], eax; cbData
0x1800b8971  xor     r8d, r8d; Reserved
0x1800b8974  mov     [rsp+310h+phkResult], rcx; lpData
0x1800b8979  xor     edx, edx; lpValueName
0x1800b897b  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800b8980  call    cs:__imp_RegSetValueExA
0x1800b8986  test    eax, eax
0x1800b8988  jnz     loc_1800B8D32
0x1800b898e  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800b8993  lea     rax, aMsicd; "MSICD"
0x1800b899a  mov     [rsp+310h+samDesired], 9; cbData
0x1800b89a2  lea     rdx, aInstaller; "Installer"
0x1800b89a9  mov     r9d, r13d; dwType
0x1800b89ac  mov     [rsp+310h+phkResult], rax; lpData
0x1800b89b1  xor     r8d, r8d; Reserved
0x1800b89b4  call    cs:__imp_RegSetValueExA
0x1800b89ba  test    eax, eax
0x1800b89bc  jnz     loc_1800B8D32
0x1800b89c2  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800b89c7  lea     rax, [rsp+310h+var_2A8]
0x1800b89cc  mov     r9d, 0F003Fh; samDesired
0x1800b89d2  mov     [rsp+310h+phkResult], rax; phkResult
0x1800b89d7  xor     r8d, r8d; ulOptions
0x1800b89da  lea     rdx, aDownloadinform; "DownloadInformation"
0x1800b89e1  call    cs:__imp_RegOpenKeyExA
0x1800b89e7  test    eax, eax
0x1800b89e9  jz      short loc_1800B8A29
0x1800b89eb  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800b89f0  lea     rax, [rsp+310h+var_2A8]
0x1800b89f5  mov     [rsp+310h+lpdwDisposition], r12; lpdwDisposition
0x1800b89fa  lea     rdx, aDownloadinform; "DownloadInformation"
0x1800b8a01  mov     [rsp+310h+var_2D8], rax; phkResult
0x1800b8a06  xor     r9d, r9d; lpClass
0x1800b8a09  mov     [rsp+310h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800b8a0e  xor     r8d, r8d; Reserved
0x1800b8a11  mov     [rsp+310h+samDesired], r14d; samDesired
0x1800b8a16  mov     dword ptr [rsp+310h+phkResult], r12d; dwOptions
0x1800b8a1b  call    cs:__imp_RegCreateKeyExA
0x1800b8a21  test    eax, eax
0x1800b8a23  jnz     loc_1800B8D32
0x1800b8a29  mov     rcx, [r15+30h]
0x1800b8a2d  test    rcx, rcx
0x1800b8a30  jz      short loc_1800B8A69
0x1800b8a32  mov     rax, rsi
0x1800b8a35  inc     rax
0x1800b8a38  cmp     [rcx+rax], r12b
0x1800b8a3c  jnz     short loc_1800B8A35
0x1800b8a3e  inc     eax
0x1800b8a40  lea     rdx, aCdf; "CDF"
0x1800b8a47  mov     [rsp+310h+samDesired], eax; cbData
0x1800b8a4b  mov     r9d, r13d; dwType
0x1800b8a4e  mov     [rsp+310h+phkResult], rcx; lpData
0x1800b8a53  xor     r8d, r8d; Reserved
0x1800b8a56  mov     rcx, [rsp+310h+var_2A8]; hKey
0x1800b8a5b  call    cs:__imp_RegSetValueExA
0x1800b8a61  test    eax, eax
0x1800b8a63  jnz     loc_1800B8D32
0x1800b8a69  mov     r14, [r15+58h]
0x1800b8a6d  mov     r12d, r13d
0x1800b8a70  test    r14, r14
0x1800b8a73  jz      loc_1800B8B57
0x1800b8a79  mov     r13, [r14]
0x1800b8a7c  mov     edx, 111h; unsigned __int64
0x1800b8a81  mov     rdi, [r14+10h]
0x1800b8a85  lea     rcx, [rbp+210h+ValueName]; char *
0x1800b8a8c  cmp     r12d, 1
0x1800b8a90  jg      short loc_1800B8AA0
0x1800b8a92  lea     r8, aCodebase_0; "CODEBASE"
0x1800b8a99  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800b8a9e  jmp     short loc_1800B8AB8
0x1800b8aa0  lea     r9, aCodebase_0; "CODEBASE"
0x1800b8aa7  mov     dword ptr [rsp+310h+phkResult], r12d
0x1800b8aac  lea     r8, aSD; "%s%d"
0x1800b8ab3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800b8ab8  mov     rcx, [rdi]; lpWideCharStr
0x1800b8abb  lea     rdx, [rbp+210h+lpData]
0x1800b8abf  call    Unicode2Ansi
0x1800b8ac4  mov     rdi, [rbp+210h+lpData]
0x1800b8ac8  test    eax, eax
0x1800b8aca  js      short loc_1800B8B4A
0x1800b8acc  mov     rax, rsi
0x1800b8acf  inc     rax
0x1800b8ad2  cmp     byte ptr [rdi+rax], 0
0x1800b8ad6  jnz     short loc_1800B8ACF
0x1800b8ad8  mov     rcx, [rsp+310h+var_2A8]; hKey
0x1800b8add  lea     rdx, [rbp+210h+ValueName]; lpValueName
0x1800b8ae4  mov     [rsp+310h+samDesired], eax; cbData
0x1800b8ae8  mov     r9d, 1; dwType
0x1800b8aee  xor     r8d, r8d; Reserved
0x1800b8af1  mov     [rsp+310h+phkResult], rdi; lpData
0x1800b8af6  call    cs:__imp_RegSetValueExA
0x1800b8afc  mov     r14d, eax
0x1800b8aff  test    eax, eax
0x1800b8b01  jnz     short loc_1800B8B21
0x1800b8b03  mov     r14, r13
0x1800b8b06  test    rdi, rdi
0x1800b8b09  jz      short loc_1800B8B19
0x1800b8b0b  mov     rcx, rdi; void *
0x1800b8b0e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b8b13  xor     edi, edi
0x1800b8b15  mov     [rbp+210h+lpData], rdi
0x1800b8b19  inc     r12d
0x1800b8b1c  jmp     loc_1800B8A70
0x1800b8b21  xor     r12d, r12d
0x1800b8b24  test    rdi, rdi
0x1800b8b27  jz      short loc_1800B8B34
0x1800b8b29  mov     rcx, rdi; void *
0x1800b8b2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b8b31  mov     edi, r12d
0x1800b8b34  test    r14d, r14d
0x1800b8b37  jg      short loc_1800B8B41
0x1800b8b39  mov     ebx, r14d
0x1800b8b3c  jmp     loc_1800B8D41
0x1800b8b41  movzx   ebx, r14w
0x1800b8b45  jmp     loc_1800B8D3B
0x1800b8b4a  mov     ebx, 8007000Eh
0x1800b8b4f  xor     r12d, r12d
0x1800b8b52  jmp     loc_1800B8D41
0x1800b8b57  movzx   ecx, word ptr [r15+1Ch]
0x1800b8b5c  lea     r8, aDDDD_0; "%d,%d,%d,%d"
0x1800b8b63  movzx   edx, word ptr [r15+1Eh]
0x1800b8b68  movzx   eax, word ptr [r15+18h]
0x1800b8b6d  movzx   r9d, word ptr [r15+1Ah]
0x1800b8b72  mov     dword ptr [rsp+310h+lpSecurityAttributes], ecx
0x1800b8b76  lea     rcx, [rbp+210h+var_280]; char *
0x1800b8b7a  mov     [rsp+310h+samDesired], edx
0x1800b8b7e  mov     edx, 104h; unsigned __int64
0x1800b8b83  mov     dword ptr [rsp+310h+phkResult], eax
0x1800b8b87  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800b8b8c  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800b8b91  lea     rax, [rsp+310h+var_2B8]
0x1800b8b96  mov     r9d, 0F003Fh; samDesired
0x1800b8b9c  mov     [rsp+310h+phkResult], rax; phkResult
0x1800b8ba1  xor     r8d, r8d; ulOptions
0x1800b8ba4  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800b8bab  call    cs:__imp_RegOpenKeyExA
0x1800b8bb1  xor     r12d, r12d
0x1800b8bb4  test    eax, eax
0x1800b8bb6  jz      short loc_1800B8BF9
0x1800b8bb8  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800b8bbd  lea     rax, [rsp+310h+var_2B8]
0x1800b8bc2  mov     [rsp+310h+lpdwDisposition], r12; lpdwDisposition
0x1800b8bc7  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800b8bce  mov     [rsp+310h+var_2D8], rax; phkResult
0x1800b8bd3  xor     r9d, r9d; lpClass
0x1800b8bd6  mov     [rsp+310h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800b8bdb  xor     r8d, r8d; Reserved
0x1800b8bde  mov     [rsp+310h+samDesired], 2000000h; samDesired
0x1800b8be6  mov     dword ptr [rsp+310h+phkResult], r12d; dwOptions
0x1800b8beb  call    cs:__imp_RegCreateKeyExA
0x1800b8bf1  test    eax, eax
0x1800b8bf3  jnz     loc_1800B8D32
0x1800b8bf9  mov     r13d, dword ptr [rsp+310h+Data]
0x1800b8bfe  test    r13d, r13d
0x1800b8c01  jnz     short loc_1800B8C15
0x1800b8c03  mov     rdx, [r15+48h]; char *
0x1800b8c07  mov     rcx, [rsp+310h+var_2B8]; HKEY
0x1800b8c0c  call    ?IsAbstractDifferent@@YAHPEAUHKEY__@@PEAD@Z; IsAbstractDifferent(HKEY__ *,char *)
0x1800b8c11  test    eax, eax
0x1800b8c13  jz      short loc_1800B8C80
0x1800b8c15  mov     rcx, [rsp+310h+var_2C0]; hKey
0x1800b8c1a  lea     rax, [rbp+210h+var_288]
0x1800b8c1e  mov     r9d, 2000000h; samDesired
0x1800b8c24  mov     [rsp+310h+phkResult], rax; phkResult
0x1800b8c29  xor     r8d, r8d; ulOptions
0x1800b8c2c  lea     rdx, aAdvertisedvers; "AdvertisedVersion"
0x1800b8c33  call    cs:__imp_RegOpenKeyExA
0x1800b8c39  test    eax, eax
0x1800b8c3b  jnz     short loc_1800B8C69
0x1800b8c3d  mov     rcx, [rbp+210h+var_288]; hKey
0x1800b8c41  lea     r9d, [rax+4]; dwType
0x1800b8c45  lea     rax, [rsp+310h+Data]
0x1800b8c4a  mov     [rsp+310h+samDesired], r9d; cbData
0x1800b8c4f  xor     r8d, r8d; Reserved
0x1800b8c52  mov     [rsp+310h+phkResult], rax; lpData
0x1800b8c57  lea     rdx, aAdstate; "AdState"
0x1800b8c5e  mov     dword ptr [rsp+310h+Data], r12d
0x1800b8c63  call    cs:__imp_RegSetValueExA
0x1800b8c69  test    r13d, r13d
0x1800b8c6c  jz      short loc_1800B8C80
0x1800b8c6e  mov     rcx, [rsp+310h+var_2B8]; hKey
0x1800b8c73  lea     rdx, aPrecache_0; "Precache"
0x1800b8c7a  call    cs:__imp_RegDeleteValueA
0x1800b8c80  lea     rcx, [rbp+210h+var_280]
0x1800b8c84  mov     rax, rsi
0x1800b8c87  inc     rax
0x1800b8c8a  cmp     [rcx+rax], r12b
0x1800b8c8e  jnz     short loc_1800B8C87
0x1800b8c90  mov     rcx, [rsp+310h+var_2B8]; hKey
0x1800b8c95  inc     eax
0x1800b8c97  mov     [rsp+310h+samDesired], eax; cbData
0x1800b8c9b  mov     r14d, 1
0x1800b8ca1  lea     rax, [rbp+210h+var_280]
0x1800b8ca5  mov     r9d, r14d; dwType
0x1800b8ca8  xor     r8d, r8d; Reserved
0x1800b8cab  mov     [rsp+310h+phkResult], rax; lpData
0x1800b8cb0  xor     edx, edx; lpValueName
0x1800b8cb2  call    cs:__imp_RegSetValueExA
0x1800b8cb8  test    eax, eax
0x1800b8cba  jnz     short loc_1800B8D32
0x1800b8cbc  mov     rcx, [r15+50h]
0x1800b8cc0  test    rcx, rcx
0x1800b8cc3  jz      short loc_1800B8CF8
0x1800b8cc5  mov     rax, rsi
0x1800b8cc8  inc     rax
0x1800b8ccb  cmp     [rcx+rax], r12b
0x1800b8ccf  jnz     short loc_1800B8CC8
  ... truncated ...
```
