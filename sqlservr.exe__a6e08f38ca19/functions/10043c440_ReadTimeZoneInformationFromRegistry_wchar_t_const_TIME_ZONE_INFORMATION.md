# ReadTimeZoneInformationFromRegistry(wchar_t const *,_TIME_ZONE_INFORMATION *)

- ea: `0x10043c440`
- end: `0x10043c7f5`
- name: `?ReadTimeZoneInformationFromRegistry@@YAJPEB_WPEAU_TIME_ZONE_INFORMATION@@@Z`
- size: `949`
- prototype: `__int64 __fastcall(const wchar_t *, struct _TIME_ZONE_INFORMATION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10043cc10`

## callees

- `0x100401580`
- `0x100402880`
- `0x10043c440`
- `0x1004534f8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x10043c7ca`
- `ADVAPI32!RegCloseKey` at `0x10043c7ca`
- `ADVAPI32!RegOpenKeyExW` at `0x10043c5b5`
- `ADVAPI32!RegOpenKeyExW` at `0x10043c5b5`
- `ADVAPI32!RegQueryValueExW` at `0x10043c5f1`
- `ADVAPI32!RegQueryValueExW` at `0x10043c623`
- `ADVAPI32!RegQueryValueExW` at `0x10043c657`
- `ADVAPI32!RegQueryValueExW` at `0x10043c689`
- `ADVAPI32!RegQueryValueExW` at `0x10043c6bd`
- `ADVAPI32!RegQueryValueExW` at `0x10043c6ef`
- `ADVAPI32!RegQueryValueExW` at `0x10043c725`
- `ADVAPI32!RegQueryValueExW` at `0x10043c5f1`
- `ADVAPI32!RegQueryValueExW` at `0x10043c623`
- `ADVAPI32!RegQueryValueExW` at `0x10043c657`
- `ADVAPI32!RegQueryValueExW` at `0x10043c689`
- `ADVAPI32!RegQueryValueExW` at `0x10043c6bd`
- `ADVAPI32!RegQueryValueExW` at `0x10043c6ef`
- `ADVAPI32!RegQueryValueExW` at `0x10043c725`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10043c793`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10043c793`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10043c79f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10043c79f`

## pseudocode

```c
__int64 __fastcall ReadTimeZoneInformationFromRegistry(const wchar_t *a1, struct _TIME_ZONE_INFORMATION *a2)
{
  WCHAR *v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // r8
  WCHAR *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  char *v11; // rbx
  WCHAR v12; // r8
  WCHAR *v13; // rax
  unsigned int v15; // ebx
  HKEY v16; // rsi
  HKEY v17; // rsi
  HKEY v18; // rsi
  SYSTEMTIME v19; // xmm0
  size_t v20; // r8
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v23; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v25; // [rsp+44h] [rbp-BCh] BYREF
  BYTE v26[56]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[57]; // [rsp+80h] [rbp-80h] BYREF
  char v28[398]; // [rsp+F2h] [rbp-Eh] BYREF
  BYTE Src[512]; // [rsp+280h] [rbp+180h] BYREF
  BYTE v30[512]; // [rsp+480h] [rbp+380h] BYREF
  BYTE Data[512]; // [rsp+680h] [rbp+580h] BYREF

  memset(v26, 0, 44);
  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones\\");
  v25 = 44;
  hKey = 0;
  memset_0(v28, 0, sizeof(v28));
  v4 = SubKey;
  v5 = 256;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  v6 = -2147024809;
  v7 = 256 - v5;
  if ( v5 )
  {
    v8 = &SubKey[v7];
    v9 = 256 - v7;
    if ( 256 != v7 )
    {
      v10 = 2147483646;
      v11 = (char *)((char *)a1 - (char *)v8);
      do
      {
        if ( !v10 )
          break;
        v12 = *(WCHAR *)((char *)v8 + (_QWORD)v11);
        if ( !v12 )
          break;
        *v8 = v12;
        --v10;
        ++v8;
        --v9;
      }
      while ( v9 );
    }
    v13 = v8 - 1;
    if ( v9 )
      v13 = v8;
    *v13 = 0;
    v6 = -2147024774;
    if ( v9 )
      v6 = 0;
  }
  if ( v6 )
    return 122;
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hKey);
  if ( !v15 )
  {
    v16 = hKey;
    v15 = RegQueryValueExW(hKey, L"Display", 0, 0, 0, &cbData);
    if ( !v15 )
      v15 = RegQueryValueExW(v16, L"Display", 0, 0, Data, &cbData);
    if ( !v15 )
    {
      v17 = hKey;
      v15 = RegQueryValueExW(hKey, L"Dlt", 0, 0, 0, &lpcbData);
      if ( !v15 )
        v15 = RegQueryValueExW(v17, L"Dlt", 0, 0, Src, &lpcbData);
      if ( !v15 )
      {
        v18 = hKey;
        v15 = RegQueryValueExW(hKey, L"Std", 0, 0, 0, &v23);
        if ( !v15 )
          v15 = RegQueryValueExW(v18, L"Std", 0, 0, v30, &v23);
        if ( !v15 )
        {
          v15 = RegQueryValueExW(hKey, L"TZI", 0, 0, v26, &v25);
          if ( !v15 )
          {
            v19 = *(SYSTEMTIME *)&v26[28];
            v20 = lpcbData;
            a2->Bias = *(_DWORD *)v26;
            a2->DaylightBias = *(_DWORD *)&v26[8];
            a2->StandardBias = *(_DWORD *)&v26[4];
            a2->DaylightDate = v19;
            a2->StandardDate = *(SYSTEMTIME *)&v26[12];
            if ( v20 )
            {
              if ( a2 == (struct _TIME_ZONE_INFORMATION *)-88LL )
              {
LABEL_32:
                *_errno() = 22;
                _invalid_parameter_noinfo();
                v15 = 122;
                goto LABEL_34;
              }
              memmove(a2->DaylightName, Src, v20);
            }
            if ( v23 )
            {
              if ( a2 != (struct _TIME_ZONE_INFORMATION *)-4LL )
              {
                memmove(a2->StandardName, v30, v23);
                goto LABEL_34;
              }
              goto LABEL_32;
            }
          }
        }
      }
    }
  }
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  return v15;
}

```

## disassembly

```asm
0x10043c440  mov     [rsp-8+arg_10], rbx
0x10043c445  push    rbp
0x10043c446  push    rdi
0x10043c447  push    r14
0x10043c449  lea     rbp, [rsp-790h]
0x10043c451  sub     rsp, 890h
0x10043c458  mov     rax, cs:__security_cookie
0x10043c45f  xor     rax, rsp
0x10043c462  mov     [rbp+7A0h+var_20], rax
0x10043c469  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x10043c470  xorps   xmm0, xmm0
0x10043c473  movups  xmmword ptr [rsp+8A0h+var_858], xmm0
0x10043c478  xor     eax, eax
0x10043c47a  mov     rdi, rdx
0x10043c47d  movups  [rsp+8A0h+var_848], xmm0
0x10043c482  mov     rbx, rcx
0x10043c485  mov     [rsp+8A0h+var_838], rax
0x10043c48a  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x10043c491  lea     rcx, [rbp+7A0h+var_7AE]; void *
0x10043c495  movaps  xmmword ptr [rbp+7A0h+SubKey], xmm0
0x10043c499  xor     r14d, r14d
0x10043c49c  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Windows NT\\CurrentVersion\\Time Zo"...
0x10043c4a3  xor     edx, edx; Val
0x10043c4a5  movaps  [rbp+7A0h+var_800], xmm0
0x10043c4a9  mov     r8d, 18Eh; Size
0x10043c4af  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "rrentVersion\\Time Zones\\"
0x10043c4b6  movaps  [rbp+7A0h+var_810], xmm1
0x10043c4ba  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ws NT\\CurrentVersion\\Time Zones\\"
0x10043c4c1  movaps  [rbp+7A0h+var_7E0], xmm0
0x10043c4c5  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+60h; "e Zones\\"
0x10043c4cc  mov     [rsp+8A0h+var_830], eax
0x10043c4d0  movzx   eax, word ptr cs:aSoftwareMicros+70h; ""
0x10043c4d7  movaps  [rbp+7A0h+var_7F0], xmm1
0x10043c4db  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "sion\\Time Zones\\"
0x10043c4e2  movaps  [rbp+7A0h+var_7C0], xmm0
0x10043c4e6  mov     [rsp+8A0h+var_85C], 2Ch ; ','
0x10043c4ee  mov     [rsp+8A0h+hKey], r14
0x10043c4f3  movaps  [rbp+7A0h+var_7D0], xmm1
0x10043c4f7  mov     [rbp+7A0h+var_7B0], ax
0x10043c4fb  call    memset_0
0x10043c500  mov     edx, 100h
0x10043c505  lea     rax, [rbp+7A0h+SubKey]
0x10043c509  mov     ecx, edx
0x10043c50b  nop     dword ptr [rax+rax+00h]
0x10043c510  cmp     [rax], r14w
0x10043c514  jz      short loc_10043C520
0x10043c516  add     rax, 2
0x10043c51a  sub     rcx, 1
0x10043c51e  jnz     short loc_10043C510
0x10043c520  mov     r8, rdx
0x10043c523  mov     eax, 80070057h
0x10043c528  sub     r8, rcx
0x10043c52b  test    rcx, rcx
0x10043c52e  cmovz   r8, r14
0x10043c532  cmovnz  eax, r14d
0x10043c536  jz      short loc_10043C589
0x10043c538  lea     rcx, [rbp+7A0h+SubKey]
0x10043c53c  lea     rcx, [rcx+r8*2]
0x10043c540  sub     rdx, r8
0x10043c543  jz      short loc_10043C571
0x10043c545  mov     eax, 7FFFFFFEh
0x10043c54a  sub     rbx, rcx
0x10043c54d  nop     dword ptr [rax]
0x10043c550  test    rax, rax
0x10043c553  jz      short loc_10043C571
0x10043c555  movzx   r8d, word ptr [rbx+rcx]
0x10043c55a  test    r8w, r8w
0x10043c55e  jz      short loc_10043C571
0x10043c560  mov     [rcx], r8w
0x10043c564  dec     rax
0x10043c567  add     rcx, 2
0x10043c56b  sub     rdx, 1
0x10043c56f  jnz     short loc_10043C550
0x10043c571  test    rdx, rdx
0x10043c574  lea     rax, [rcx-2]
0x10043c578  cmovnz  rax, rcx
0x10043c57c  mov     [rax], r14w
0x10043c580  mov     eax, 8007007Ah
0x10043c585  cmovnz  eax, r14d
0x10043c589  test    eax, eax
0x10043c58b  jz      short loc_10043C597
0x10043c58d  mov     eax, 7Ah ; 'z'
0x10043c592  jmp     loc_10043C7D2
0x10043c597  lea     rax, [rsp+8A0h+hKey]
0x10043c59c  mov     r9d, 20119h; samDesired
0x10043c5a2  xor     r8d, r8d; ulOptions
0x10043c5a5  mov     [rsp+8A0h+phkResult], rax; phkResult
0x10043c5aa  lea     rdx, [rbp+7A0h+SubKey]; lpSubKey
0x10043c5ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x10043c5b5  call    cs:__imp_RegOpenKeyExW
0x10043c5bb  mov     ebx, eax
0x10043c5bd  test    eax, eax
0x10043c5bf  jnz     loc_10043C7C0
0x10043c5c5  lea     rax, [rsp+8A0h+cbData]
0x10043c5ca  mov     [rsp+8A0h+arg_0], rsi
0x10043c5d2  mov     rsi, [rsp+8A0h+hKey]
0x10043c5d7  lea     rdx, ValueName; "Display"
0x10043c5de  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x10043c5e3  mov     rcx, rsi; hKey
0x10043c5e6  xor     r9d, r9d; lpType
0x10043c5e9  mov     [rsp+8A0h+phkResult], r14; lpData
0x10043c5ee  xor     r8d, r8d; lpReserved
0x10043c5f1  call    cs:__imp_RegQueryValueExW
0x10043c5f7  mov     ebx, eax
0x10043c5f9  test    eax, eax
0x10043c5fb  jnz     short loc_10043C62B
0x10043c5fd  lea     rax, [rsp+8A0h+cbData]
0x10043c602  xor     r9d, r9d; lpType
0x10043c605  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x10043c60a  lea     rdx, ValueName; "Display"
0x10043c611  lea     rax, [rbp+7A0h+Data]
0x10043c618  xor     r8d, r8d; lpReserved
0x10043c61b  mov     rcx, rsi; hKey
0x10043c61e  mov     [rsp+8A0h+phkResult], rax; lpData
0x10043c623  call    cs:__imp_RegQueryValueExW
0x10043c629  mov     ebx, eax
0x10043c62b  test    ebx, ebx
0x10043c62d  jnz     loc_10043C7B8
0x10043c633  mov     rsi, [rsp+8A0h+hKey]
0x10043c638  lea     rax, [rsp+8A0h+var_868]
0x10043c63d  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x10043c642  lea     rdx, aDlt; "Dlt"
0x10043c649  mov     rcx, rsi; hKey
0x10043c64c  mov     [rsp+8A0h+phkResult], r14; lpData
0x10043c651  xor     r9d, r9d; lpType
0x10043c654  xor     r8d, r8d; lpReserved
0x10043c657  call    cs:__imp_RegQueryValueExW
0x10043c65d  mov     ebx, eax
0x10043c65f  test    eax, eax
0x10043c661  jnz     short loc_10043C691
0x10043c663  lea     rax, [rsp+8A0h+var_868]
0x10043c668  xor     r9d, r9d; lpType
0x10043c66b  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x10043c670  lea     rdx, aDlt; "Dlt"
0x10043c677  lea     rax, [rbp+7A0h+Src]
0x10043c67e  xor     r8d, r8d; lpReserved
0x10043c681  mov     rcx, rsi; hKey
0x10043c684  mov     [rsp+8A0h+phkResult], rax; lpData
0x10043c689  call    cs:__imp_RegQueryValueExW
0x10043c68f  mov     ebx, eax
0x10043c691  test    ebx, ebx
0x10043c693  jnz     loc_10043C7B8
0x10043c699  mov     rsi, [rsp+8A0h+hKey]
0x10043c69e  lea     rax, [rsp+8A0h+var_864]
0x10043c6a3  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x10043c6a8  lea     rdx, aStd; "Std"
0x10043c6af  mov     rcx, rsi; hKey
0x10043c6b2  mov     [rsp+8A0h+phkResult], r14; lpData
0x10043c6b7  xor     r9d, r9d; lpType
0x10043c6ba  xor     r8d, r8d; lpReserved
0x10043c6bd  call    cs:__imp_RegQueryValueExW
0x10043c6c3  mov     ebx, eax
0x10043c6c5  test    eax, eax
0x10043c6c7  jnz     short loc_10043C6F7
0x10043c6c9  lea     rax, [rsp+8A0h+var_864]
0x10043c6ce  xor     r9d, r9d; lpType
0x10043c6d1  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x10043c6d6  lea     rdx, aStd; "Std"
0x10043c6dd  lea     rax, [rbp+7A0h+var_420]
0x10043c6e4  xor     r8d, r8d; lpReserved
0x10043c6e7  mov     rcx, rsi; hKey
0x10043c6ea  mov     [rsp+8A0h+phkResult], rax; lpData
0x10043c6ef  call    cs:__imp_RegQueryValueExW
0x10043c6f5  mov     ebx, eax
0x10043c6f7  test    ebx, ebx
0x10043c6f9  jnz     loc_10043C7B8
0x10043c6ff  mov     rcx, [rsp+8A0h+hKey]; hKey
0x10043c704  lea     rax, [rsp+8A0h+var_85C]
0x10043c709  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x10043c70e  lea     rdx, aTzi; "TZI"
0x10043c715  lea     rax, [rsp+8A0h+var_858]
0x10043c71a  xor     r9d, r9d; lpType
0x10043c71d  xor     r8d, r8d; lpReserved
0x10043c720  mov     [rsp+8A0h+phkResult], rax; lpData
0x10043c725  call    cs:__imp_RegQueryValueExW
0x10043c72b  mov     ebx, eax
0x10043c72d  test    eax, eax
0x10043c72f  jnz     loc_10043C7B8
0x10043c735  movups  xmm0, [rsp+8A0h+var_848+0Ch]
0x10043c73a  mov     eax, dword ptr [rsp+8A0h+var_858]
0x10043c73e  lea     rcx, [rdi+58h]; void *
0x10043c742  mov     r8d, [rsp+8A0h+var_868]; Size
0x10043c747  mov     [rdi], eax
0x10043c749  mov     eax, dword ptr [rsp+8A0h+var_858+8]
0x10043c74d  mov     [rdi+0A8h], eax
0x10043c753  mov     eax, dword ptr [rsp+8A0h+var_858+4]
0x10043c757  mov     [rdi+54h], eax
0x10043c75a  movups  xmmword ptr [rdi+98h], xmm0
0x10043c761  movups  xmm0, xmmword ptr [rsp+8A0h+var_858+0Ch]
0x10043c766  movups  xmmword ptr [rdi+44h], xmm0
0x10043c76a  test    r8, r8
0x10043c76d  jz      short loc_10043C780
0x10043c76f  test    rcx, rcx
0x10043c772  jz      short loc_10043C793
0x10043c774  lea     rdx, [rbp+7A0h+Src]; Src
0x10043c77b  call    memmove
0x10043c780  mov     r8d, [rsp+8A0h+var_864]; Size
0x10043c785  lea     rcx, [rdi+4]; void *
0x10043c789  test    r8, r8
0x10043c78c  jz      short loc_10043C7B8
0x10043c78e  test    rcx, rcx
0x10043c791  jnz     short loc_10043C7AC
0x10043c793  call    cs:__imp__errno
0x10043c799  mov     dword ptr [rax], 16h
0x10043c79f  call    cs:__imp__invalid_parameter_noinfo
0x10043c7a5  mov     ebx, 7Ah ; 'z'
0x10043c7aa  jmp     short loc_10043C7B8
0x10043c7ac  lea     rdx, [rbp+7A0h+var_420]; Src
0x10043c7b3  call    memmove
0x10043c7b8  mov     rsi, [rsp+8A0h+arg_0]
0x10043c7c0  mov     rcx, [rsp+8A0h+hKey]; hKey
0x10043c7c5  test    rcx, rcx
0x10043c7c8  jz      short loc_10043C7D0
0x10043c7ca  call    cs:__imp_RegCloseKey
0x10043c7d0  mov     eax, ebx
0x10043c7d2  mov     rcx, [rbp+7A0h+var_20]
0x10043c7d9  xor     rcx, rsp; StackCookie
0x10043c7dc  call    __security_check_cookie
0x10043c7e1  mov     rbx, [rsp+8A0h+arg_10]
0x10043c7e9  add     rsp, 890h
0x10043c7f0  pop     r14
0x10043c7f2  pop     rdi
0x10043c7f3  pop     rbp
0x10043c7f4  retn
```
