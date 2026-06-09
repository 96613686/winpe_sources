# CSoftDist::IsICDAdvertised(int *,int *)

- ea: `0x1800c17ac`
- end: `0x1800c1cfd`
- name: `?IsICDAdvertised@CSoftDist@@AEAAJPEAH0@Z`
- size: `1361`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800c2fa0`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x18007bcc8`
- `0x1800a3dc0`
- `0x1800c1550`
- `0x1800c178c`
- `0x1800c17ac`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c1868`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c18b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c1905`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c1977`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c1868`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c18b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c1905`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c1977`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c193d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c19b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1a05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1a39`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1a83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1ae4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1b2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1b6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1bb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1bf6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c193d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c19b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1a05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1a39`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1a83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1ae4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1b2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1b6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1bb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c1bf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1c73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1c8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1cc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1c73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1c8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1a93`

## string_xrefs

- `0x1800c1931`: `Precache`

## pseudocode

```c
__int64 __fastcall CSoftDist::IsICDAdvertised(CSoftDist *this, int *a2, int *a3)
{
  CHAR *v6; // rsi
  int v7; // ebx
  int IsAuthorizedCDF; // eax
  HKEY v9; // rcx
  char v10; // r9
  BYTE *v11; // rax
  signed int LastError; // eax
  BYTE *v13; // rax
  BYTE *v14; // rax
  char v15; // r9
  unsigned int v16; // edx
  unsigned int v17; // r8d
  DWORD lpcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY v21; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+54h] [rbp-ACh] BYREF
  HKEY v27; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  LPCSTR lpSubKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE v30[272]; // [rsp+70h] [rbp-90h] BYREF

  lpcbData = 260;
  *(_DWORD *)Data = 0;
  hKey = 0;
  phkResult = 0;
  v21 = 0;
  v6 = 0;
  v27 = 0;
  cbData = 4;
  Type = 0;
  v25 = 0;
  v26 = 0;
  lpSubKey = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 1;
    *(_DWORD *)Data = RegOpenKeyExA(
                        HKEY_LOCAL_MACHINE,
                        "Software\\Microsoft\\Code Store Database\\Distribution Units",
                        0,
                        0xF003Fu,
                        &hKey);
    if ( *(_DWORD *)Data )
    {
      v7 = 1;
      goto LABEL_39;
    }
    v7 = Unicode2Ansi(*((LPCWCH *)this + 2), (CHAR **)&lpSubKey);
    if ( v7 >= 0 )
    {
      v6 = (CHAR *)lpSubKey;
      if ( !RegOpenKeyExA(hKey, lpSubKey, 0, 0xF003Fu, &phkResult) )
      {
        IsAuthorizedCDF = CSoftDist::IsAuthorizedCDF(this, phkResult, 1);
        v9 = phkResult;
        *a3 = IsAuthorizedCDF;
        if ( !RegOpenKeyExA(v9, "AvailableVersion", 0, 0xF003Fu, &v21) )
        {
          if ( !RegQueryValueExA(v21, "Precache", 0, &Type, Data, &cbData) )
            *a2 = *(_DWORD *)Data >= 0;
          if ( !RegOpenKeyExA(phkResult, "AdvertisedVersion", 0, 0xF003Fu, &v27) )
          {
            lpcbData = 260;
            if ( !RegQueryValueExA(v27, 0, 0, &Type, v30, &lpcbData) )
              GetVersionFromString((LPCSTR)v30, (unsigned int *)this + 8, (unsigned int *)this + 9, v10);
            cbData = 4;
            RegQueryValueExA(v27, "AdState", 0, 0, (LPBYTE)this + 40, &cbData);
          }
          if ( !*((_QWORD *)this + 7) && !RegQueryValueExA(phkResult, 0, 0, &Type, 0, &lpcbData) )
          {
            v11 = (BYTE *)operator new(lpcbData);
            *((_QWORD *)this + 7) = v11;
            if ( !v11 )
            {
LABEL_18:
              v7 = -2147024882;
              goto LABEL_37;
            }
            if ( RegQueryValueExA(phkResult, 0, 0, &Type, v11, &lpcbData) )
              goto LABEL_20;
          }
          if ( !*((_QWORD *)this + 9) && !RegQueryValueExA(v21, "Abstract", 0, &Type, 0, &lpcbData) )
          {
            v13 = (BYTE *)operator new(lpcbData);
            *((_QWORD *)this + 9) = v13;
            if ( !v13 )
              goto LABEL_18;
            if ( RegQueryValueExA(v21, "Abstract", 0, &Type, v13, &lpcbData) )
              goto LABEL_20;
          }
          if ( !*((_QWORD *)this + 10) && !RegQueryValueExA(v21, "HREF", 0, &Type, 0, &lpcbData) )
          {
            v14 = (BYTE *)operator new(lpcbData);
            *((_QWORD *)this + 10) = v14;
            if ( !v14 )
              goto LABEL_18;
            if ( RegQueryValueExA(v21, "HREF", 0, &Type, v14, &lpcbData) )
            {
LABEL_20:
              LastError = GetLastError();
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
              goto LABEL_37;
            }
          }
          lpcbData = 260;
          if ( !RegQueryValueExA(v21, 0, 0, &Type, v30, &lpcbData)
            && (int)GetVersionFromString((LPCSTR)v30, &v25, &v26, v15) >= 0 )
          {
            v16 = v25;
            v17 = v26;
            if ( !*((_QWORD *)this + 3) )
            {
              *((_DWORD *)this + 6) = v25;
              *((_DWORD *)this + 7) = v17;
            }
            v7 = CSoftDist::IsCDFNewerVersion(this, v16, v17) != 0;
            goto LABEL_37;
          }
        }
      }
      v7 = 1;
      goto LABEL_37;
    }
    v6 = (CHAR *)lpSubKey;
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_37:
  if ( v6 )
    operator delete(v6);
LABEL_39:
  if ( v21 )
  {
    RegCloseKey(v21);
    v21 = 0;
  }
  if ( v27 )
  {
    RegCloseKey(v27);
    v27 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800c17ac  mov     [rsp-8+arg_18], rbx
0x1800c17b1  push    rbp
0x1800c17b2  push    rsi
0x1800c17b3  push    rdi
0x1800c17b4  push    r12
0x1800c17b6  push    r13
0x1800c17b8  push    r14
0x1800c17ba  push    r15
0x1800c17bc  lea     rbp, [rsp-90h]
0x1800c17c4  sub     rsp, 190h
0x1800c17cb  mov     rax, cs:__security_cookie
0x1800c17d2  xor     rax, rsp
0x1800c17d5  mov     [rbp+0C0h+var_40], rax
0x1800c17dc  xor     r12d, r12d
0x1800c17df  mov     [rsp+1C0h+var_190], 104h
0x1800c17e7  mov     dword ptr [rsp+1C0h+Data], r12d
0x1800c17ec  mov     r15, r8
0x1800c17ef  mov     [rsp+1C0h+hKey], r12
0x1800c17f4  mov     r14, rdx
0x1800c17f7  mov     [rsp+1C0h+var_178], r12
0x1800c17fc  mov     rdi, rcx
0x1800c17ff  mov     [rsp+1C0h+var_188], r12
0x1800c1804  mov     esi, r12d
0x1800c1807  mov     [rsp+1C0h+var_168], r12
0x1800c180c  mov     [rsp+1C0h+cbData], 4
0x1800c1814  mov     [rsp+1C0h+Type], r12d
0x1800c1819  mov     [rsp+1C0h+var_170], r12d
0x1800c181e  mov     [rsp+1C0h+var_16C], r12d
0x1800c1823  mov     [rsp+1C0h+lpSubKey], r12
0x1800c1828  test    rdx, rdx
0x1800c182b  jz      loc_1800C1C57
0x1800c1831  test    r8, r8
0x1800c1834  jz      loc_1800C1C57
0x1800c183a  mov     [rdx], r12d
0x1800c183d  lea     rax, [rsp+1C0h+hKey]
0x1800c1842  lea     r13d, [r12+1]
0x1800c1847  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c184c  mov     [r8], r13d
0x1800c184f  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800c1856  mov     esi, 0F003Fh
0x1800c185b  xor     r8d, r8d; ulOptions
0x1800c185e  mov     r9d, esi; samDesired
0x1800c1861  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c1868  call    cs:__imp_RegOpenKeyExA
0x1800c186f  nop     dword ptr [rax+rax+00h]
0x1800c1874  mov     dword ptr [rsp+1C0h+Data], eax
0x1800c1878  test    eax, eax
0x1800c187a  jz      short loc_1800C1884
0x1800c187c  mov     ebx, r13d
0x1800c187f  jmp     loc_1800C1C69
0x1800c1884  mov     rcx, [rdi+10h]; lpWideCharStr
0x1800c1888  lea     rdx, [rsp+1C0h+lpSubKey]
0x1800c188d  call    Unicode2Ansi
0x1800c1892  mov     ebx, eax
0x1800c1894  test    eax, eax
0x1800c1896  js      loc_1800C1C50
0x1800c189c  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800c18a1  lea     rax, [rsp+1C0h+var_178]
0x1800c18a6  mov     r9d, esi; samDesired
0x1800c18a9  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c18ae  mov     rsi, [rsp+1C0h+lpSubKey]
0x1800c18b3  xor     r8d, r8d; ulOptions
0x1800c18b6  mov     rdx, rsi; lpSubKey
0x1800c18b9  call    cs:__imp_RegOpenKeyExA
0x1800c18c0  nop     dword ptr [rax+rax+00h]
0x1800c18c5  test    eax, eax
0x1800c18c7  jz      short loc_1800C18D1
0x1800c18c9  mov     ebx, r13d
0x1800c18cc  jmp     loc_1800C1C5C
0x1800c18d1  mov     rdx, [rsp+1C0h+var_178]; HKEY
0x1800c18d6  mov     r8d, r13d; int
0x1800c18d9  mov     rcx, rdi; this
0x1800c18dc  call    ?IsAuthorizedCDF@CSoftDist@@AEAAHPEAUHKEY__@@H@Z; CSoftDist::IsAuthorizedCDF(HKEY__ *,int)
0x1800c18e1  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800c18e6  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800c18ed  mov     [r15], eax
0x1800c18f0  mov     ebx, 0F003Fh
0x1800c18f5  lea     rax, [rsp+1C0h+var_188]
0x1800c18fa  mov     r9d, ebx; samDesired
0x1800c18fd  xor     r8d, r8d; ulOptions
0x1800c1900  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c1905  call    cs:__imp_RegOpenKeyExA
0x1800c190c  nop     dword ptr [rax+rax+00h]
0x1800c1911  test    eax, eax
0x1800c1913  jnz     short loc_1800C18C9
0x1800c1915  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c191a  lea     rax, [rsp+1C0h+cbData]
0x1800c191f  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800c1924  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c1929  lea     rax, [rsp+1C0h+Data]
0x1800c192e  xor     r8d, r8d; lpReserved
0x1800c1931  lea     rdx, aPrecache_0; "Precache"
0x1800c1938  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800c193d  call    cs:__imp_RegQueryValueExA
0x1800c1944  nop     dword ptr [rax+rax+00h]
0x1800c1949  test    eax, eax
0x1800c194b  jnz     short loc_1800C195B
0x1800c194d  cmp     dword ptr [rsp+1C0h+Data], r12d
0x1800c1952  mov     eax, r12d
0x1800c1955  setnl   al
0x1800c1958  mov     [r14], eax
0x1800c195b  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800c1960  lea     rax, [rsp+1C0h+var_168]
0x1800c1965  mov     r9d, ebx; samDesired
0x1800c1968  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800c196d  xor     r8d, r8d; ulOptions
0x1800c1970  lea     rdx, aAdvertisedvers; "AdvertisedVersion"
0x1800c1977  call    cs:__imp_RegOpenKeyExA
0x1800c197e  nop     dword ptr [rax+rax+00h]
0x1800c1983  test    eax, eax
0x1800c1985  jnz     loc_1800C1A11
0x1800c198b  mov     rcx, [rsp+1C0h+var_168]; hKey
0x1800c1990  lea     rax, [rsp+1C0h+var_190]
0x1800c1995  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800c199a  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c199f  lea     rax, [rsp+1C0h+var_150]
0x1800c19a4  mov     [rsp+1C0h+var_190], 104h
0x1800c19ac  xor     r8d, r8d; lpReserved
0x1800c19af  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800c19b4  xor     edx, edx; lpValueName
0x1800c19b6  call    cs:__imp_RegQueryValueExA
0x1800c19bd  nop     dword ptr [rax+rax+00h]
0x1800c19c2  test    eax, eax
0x1800c19c4  jnz     short loc_1800C19D8
0x1800c19c6  lea     r8, [rdi+24h]; unsigned int *
0x1800c19ca  lea     rdx, [rdi+20h]; unsigned int *
0x1800c19ce  lea     rcx, [rsp+1C0h+var_150]; lpString1
0x1800c19d3  call    ?GetVersionFromString@@YAJPEBDPEAK1D@Z; GetVersionFromString(char const *,ulong *,ulong *,char)
0x1800c19d8  lea     rcx, [rsp+1C0h+cbData]
0x1800c19dd  mov     [rsp+1C0h+cbData], 4
0x1800c19e5  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x1800c19ea  lea     rax, [rdi+28h]
0x1800c19ee  mov     rcx, [rsp+1C0h+var_168]; hKey
0x1800c19f3  lea     rdx, aAdstate; "AdState"
0x1800c19fa  xor     r9d, r9d; lpType
0x1800c19fd  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800c1a02  xor     r8d, r8d; lpReserved
0x1800c1a05  call    cs:__imp_RegQueryValueExA
0x1800c1a0c  nop     dword ptr [rax+rax+00h]
0x1800c1a11  cmp     [rdi+38h], r12
0x1800c1a15  jnz     loc_1800C1AB7
0x1800c1a1b  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800c1a20  lea     rax, [rsp+1C0h+var_190]
0x1800c1a25  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800c1a2a  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c1a2f  xor     r8d, r8d; lpReserved
0x1800c1a32  mov     [rsp+1C0h+phkResult], r12; lpData
0x1800c1a37  xor     edx, edx; lpValueName
0x1800c1a39  call    cs:__imp_RegQueryValueExA
0x1800c1a40  nop     dword ptr [rax+rax+00h]
0x1800c1a45  test    eax, eax
0x1800c1a47  jnz     short loc_1800C1AB7
0x1800c1a49  mov     ecx, [rsp+1C0h+var_190]; Size
0x1800c1a4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c1a52  mov     [rdi+38h], rax
0x1800c1a56  test    rax, rax
0x1800c1a59  jnz     short loc_1800C1A65
0x1800c1a5b  mov     ebx, 8007000Eh
0x1800c1a60  jmp     loc_1800C1C5C
0x1800c1a65  lea     rcx, [rsp+1C0h+var_190]
0x1800c1a6a  xor     r8d, r8d; lpReserved
0x1800c1a6d  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x1800c1a72  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c1a77  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800c1a7c  xor     edx, edx; lpValueName
0x1800c1a7e  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800c1a83  call    cs:__imp_RegQueryValueExA
0x1800c1a8a  nop     dword ptr [rax+rax+00h]
0x1800c1a8f  test    eax, eax
0x1800c1a91  jz      short loc_1800C1AB7
0x1800c1a93  call    cs:__imp_GetLastError
0x1800c1a9a  nop     dword ptr [rax+rax+00h]
0x1800c1a9f  mov     ebx, eax
0x1800c1aa1  test    eax, eax
0x1800c1aa3  jle     loc_1800C1C5C
0x1800c1aa9  movzx   ebx, ax
0x1800c1aac  or      ebx, 80070000h
0x1800c1ab2  jmp     loc_1800C1C5C
0x1800c1ab7  cmp     [rdi+48h], r12
0x1800c1abb  jnz     loc_1800C1B41
0x1800c1ac1  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c1ac6  lea     rax, [rsp+1C0h+var_190]
0x1800c1acb  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800c1ad0  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c1ad5  xor     r8d, r8d; lpReserved
0x1800c1ad8  mov     [rsp+1C0h+phkResult], r12; lpData
0x1800c1add  lea     rdx, aAbstract_0; "Abstract"
0x1800c1ae4  call    cs:__imp_RegQueryValueExA
0x1800c1aeb  nop     dword ptr [rax+rax+00h]
0x1800c1af0  test    eax, eax
0x1800c1af2  jnz     short loc_1800C1B41
0x1800c1af4  mov     ecx, [rsp+1C0h+var_190]; Size
0x1800c1af8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c1afd  mov     [rdi+48h], rax
0x1800c1b01  test    rax, rax
0x1800c1b04  jz      loc_1800C1A5B
0x1800c1b0a  lea     rcx, [rsp+1C0h+var_190]
0x1800c1b0f  xor     r8d, r8d; lpReserved
0x1800c1b12  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x1800c1b17  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c1b1c  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c1b21  lea     rdx, aAbstract_0; "Abstract"
0x1800c1b28  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800c1b2d  call    cs:__imp_RegQueryValueExA
0x1800c1b34  nop     dword ptr [rax+rax+00h]
0x1800c1b39  test    eax, eax
0x1800c1b3b  jnz     loc_1800C1A93
0x1800c1b41  cmp     [rdi+50h], r12
0x1800c1b45  jnz     loc_1800C1BCB
0x1800c1b4b  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c1b50  lea     rax, [rsp+1C0h+var_190]
0x1800c1b55  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800c1b5a  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c1b5f  xor     r8d, r8d; lpReserved
0x1800c1b62  mov     [rsp+1C0h+phkResult], r12; lpData
0x1800c1b67  lea     rdx, aHref; "HREF"
0x1800c1b6e  call    cs:__imp_RegQueryValueExA
0x1800c1b75  nop     dword ptr [rax+rax+00h]
0x1800c1b7a  test    eax, eax
0x1800c1b7c  jnz     short loc_1800C1BCB
0x1800c1b7e  mov     ecx, [rsp+1C0h+var_190]; Size
0x1800c1b82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c1b87  mov     [rdi+50h], rax
0x1800c1b8b  test    rax, rax
0x1800c1b8e  jz      loc_1800C1A5B
0x1800c1b94  lea     rcx, [rsp+1C0h+var_190]
0x1800c1b99  xor     r8d, r8d; lpReserved
0x1800c1b9c  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x1800c1ba1  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c1ba6  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c1bab  lea     rdx, aHref; "HREF"
0x1800c1bb2  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800c1bb7  call    cs:__imp_RegQueryValueExA
0x1800c1bbe  nop     dword ptr [rax+rax+00h]
0x1800c1bc3  test    eax, eax
0x1800c1bc5  jnz     loc_1800C1A93
0x1800c1bcb  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c1bd0  lea     rax, [rsp+1C0h+var_190]
0x1800c1bd5  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800c1bda  lea     r9, [rsp+1C0h+Type]; lpType
0x1800c1bdf  lea     rax, [rsp+1C0h+var_150]
0x1800c1be4  mov     [rsp+1C0h+var_190], 104h
0x1800c1bec  xor     r8d, r8d; lpReserved
0x1800c1bef  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800c1bf4  xor     edx, edx; lpValueName
0x1800c1bf6  call    cs:__imp_RegQueryValueExA
0x1800c1bfd  nop     dword ptr [rax+rax+00h]
0x1800c1c02  test    eax, eax
0x1800c1c04  jnz     loc_1800C18C9
0x1800c1c0a  lea     r8, [rsp+1C0h+var_16C]; unsigned int *
0x1800c1c0f  lea     rdx, [rsp+1C0h+var_170]; unsigned int *
0x1800c1c14  lea     rcx, [rsp+1C0h+var_150]; lpString1
0x1800c1c19  call    ?GetVersionFromString@@YAJPEBDPEAK1D@Z; GetVersionFromString(char const *,ulong *,ulong *,char)
0x1800c1c1e  test    eax, eax
0x1800c1c20  js      loc_1800C18C9
0x1800c1c26  mov     eax, [rdi+1Ch]
0x1800c1c29  or      eax, [rdi+18h]
0x1800c1c2c  mov     edx, [rsp+1C0h+var_170]; unsigned int
0x1800c1c30  mov     r8d, [rsp+1C0h+var_16C]; unsigned int
0x1800c1c35  jnz     short loc_1800C1C3E
0x1800c1c37  mov     [rdi+18h], edx
0x1800c1c3a  mov     [rdi+1Ch], r8d
0x1800c1c3e  mov     rcx, rdi; this
0x1800c1c41  call    ?IsCDFNewerVersion@CSoftDist@@AEAAHKK@Z; CSoftDist::IsCDFNewerVersion(ulong,ulong)
0x1800c1c46  test    eax, eax
0x1800c1c48  mov     ebx, r12d
0x1800c1c4b  setnz   bl
0x1800c1c4e  jmp     short loc_1800C1C5C
0x1800c1c50  mov     rsi, [rsp+1C0h+lpSubKey]
0x1800c1c55  jmp     short loc_1800C1C5C
0x1800c1c57  mov     ebx, 80070057h
0x1800c1c5c  test    rsi, rsi
0x1800c1c5f  jz      short loc_1800C1C69
0x1800c1c61  mov     rcx, rsi; void *
0x1800c1c64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c1c69  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800c1c6e  test    rcx, rcx
0x1800c1c71  jz      short loc_1800C1C84
0x1800c1c73  call    cs:__imp_RegCloseKey
0x1800c1c7a  nop     dword ptr [rax+rax+00h]
0x1800c1c7f  mov     [rsp+1C0h+var_188], r12
0x1800c1c84  mov     rcx, [rsp+1C0h+var_168]; hKey
0x1800c1c89  test    rcx, rcx
0x1800c1c8c  jz      short loc_1800C1C9F
0x1800c1c8e  call    cs:__imp_RegCloseKey
0x1800c1c95  nop     dword ptr [rax+rax+00h]
0x1800c1c9a  mov     [rsp+1C0h+var_168], r12
0x1800c1c9f  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800c1ca4  test    rcx, rcx
0x1800c1ca7  jz      short loc_1800C1CBA
0x1800c1ca9  call    cs:__imp_RegCloseKey
0x1800c1cb0  nop     dword ptr [rax+rax+00h]
0x1800c1cb5  mov     [rsp+1C0h+hKey], r12
0x1800c1cba  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800c1cbf  test    rcx, rcx
0x1800c1cc2  jz      short loc_1800C1CD0
0x1800c1cc4  call    cs:__imp_RegCloseKey
0x1800c1ccb  nop     dword ptr [rax+rax+00h]
0x1800c1cd0  mov     eax, ebx
0x1800c1cd2  mov     rcx, [rbp+0C0h+var_40]
  ... truncated ...
```
