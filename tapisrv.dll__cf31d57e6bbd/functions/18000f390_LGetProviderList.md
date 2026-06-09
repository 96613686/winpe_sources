# LGetProviderList

- ea: `0x18000f390`
- end: `0x18000f690`
- name: `LGetProviderList`
- size: `768`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x180001600`
- `0x18000f390`
- `0x18001c8a4`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f64f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f64f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f45e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f45e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f497`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f541`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f5bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f497`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f541`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f5bd`
- `KERNEL32!HeapAlloc` at `0x18000f4b5`
- `KERNEL32!HeapAlloc` at `0x18000f4b5`
- `KERNEL32!lstrlenW` at `0x18000f554`
- `KERNEL32!lstrlenW` at `0x18000f554`

## pseudocode

```c
__int64 __fastcall LGetProviderList(__int64 a1, _DWORD *a2, unsigned int a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax
  unsigned int v6; // r13d
  unsigned int v7; // r12d
  _DWORD *v9; // rdi
  int v10; // ebx
  BYTE *v11; // r15
  unsigned int v12; // r14d
  char *v13; // rdi
  int v14; // eax
  __int64 v15; // rbx
  LPBYTE v16; // rcx
  int v17; // eax
  int v18; // edx
  int v19; // ecx
  _DWORD *v20; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-81h]
  BYTE *phkResulta; // [rsp+20h] [rbp-81h]
  BYTE Data[4]; // [rsp+30h] [rbp-71h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-6Dh] BYREF
  DWORD Type; // [rsp+38h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-61h] BYREF
  DWORD lpcbData[2]; // [rsp+48h] [rbp-59h] BYREF
  LPBYTE lpData; // [rsp+50h] [rbp-51h]
  _DWORD *v29; // [rsp+58h] [rbp-49h]
  __int64 v30; // [rsp+60h] [rbp-41h]
  wchar_t pszDest[32]; // [rsp+70h] [rbp-31h] BYREF

  result = a5;
  v6 = 0;
  v7 = a2[3];
  v29 = a2;
  v9 = a2;
  v30 = a5;
  *(_DWORD *)Data = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( v7 <= a3 )
  {
    if ( a2[2] == 65539
      || a2[2] == 65540
      || a2[2] == 0x20000
      || a2[2] == 131073
      || a2[2] == 131074
      || (unsigned int)(a2[2] - 196608) < 2 )
    {
      if ( v7 >= 0x18 )
      {
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Providers",
                0,
                0xF003Fu,
                &hKey) )
        {
          cbData = 4;
          *(_DWORD *)Data = 0;
          RegQueryValueExW(hKey, L"NumProviders", 0, &Type, Data, &cbData);
        }
        v10 = *(_DWORD *)Data + 2;
        v11 = (BYTE *)HeapAlloc(ghTapisrvHeap, 8u, 0x208u);
        if ( v11 )
        {
          v12 = 12 * v10;
          lpData = (LPBYTE)(a4 + 24);
          *(_QWORD *)lpcbData = a4 + (unsigned int)(12 * v10);
          if ( *(_DWORD *)Data )
          {
            v13 = (char *)(a4 + (unsigned int)(12 * v10));
            do
            {
              lpcbData[0] = 0;
              LODWORD(phkResult) = v6;
              StringCbPrintfW(pszDest, 0x40u, L"%s%d", L"ProviderFilename", phkResult);
              lpcbData[0] = 520;
              if ( RegQueryValueExW(hKey, pszDest, 0, &Type, v11, lpcbData) )
                *(_WORD *)v11 = 0;
              v14 = lstrlenW((LPCWSTR)v11);
              v12 += 2 * v14 + 2;
              v15 = (unsigned int)(2 * v14 + 2);
              if ( v7 >= v12 )
              {
                LODWORD(phkResult) = v6;
                StringCbPrintfW(pszDest, 0x40u, L"%s%d", L"ProviderID", phkResult);
                cbData = 4;
                phkResulta = lpData;
                *(_DWORD *)lpData = 0;
                RegQueryValueExW(hKey, pszDest, 0, &Type, phkResulta, &cbData);
                v16 = lpData;
                *((_DWORD *)lpData + 1) = v15;
                *((_DWORD *)v16 + 2) = (_DWORD)v13 - a4;
                memcpy_0(v13, v11, (unsigned int)v15);
                v13 += v15;
                lpData += 12;
              }
              ++v6;
            }
            while ( v6 < *(_DWORD *)Data );
            v9 = v29;
          }
          ServerFree(v11);
          *(_DWORD *)a4 = v7;
          *(_DWORD *)(a4 + 4) = v12;
          if ( v7 < v12 )
          {
            v18 = 0;
            *(_DWORD *)(a4 + 12) = 0;
            v19 = 0;
            v12 = 24;
          }
          else
          {
            v17 = *(_DWORD *)Data;
            v18 = 24;
            *(_DWORD *)(a4 + 12) = *(_DWORD *)Data;
            v19 = 12 * v17;
          }
          *(_DWORD *)(a4 + 16) = v19;
          v20 = (_DWORD *)v30;
          *(_DWORD *)(a4 + 8) = v12;
          *(_DWORD *)(a4 + 20) = v18;
          v9[3] = 0;
          *v20 = *(_DWORD *)(a4 + 8) + 60;
          RegCloseKey(hKey);
        }
        else
        {
          *v9 = -2147483580;
        }
      }
      else
      {
        *a2 = -2147483571;
      }
    }
    else
    {
      *a2 = -2147483636;
    }
    return TRACELogPrint(524290, "lineGetProviderList: exit, result=x%x", *v9);
  }
  else
  {
    *a2 = -2147483576;
  }
  return result;
}

```

## disassembly

```asm
0x18000f390  mov     [rsp-8+arg_0], rbx
0x18000f395  push    rbp
0x18000f396  push    rsi
0x18000f397  push    rdi
0x18000f398  push    r12
0x18000f39a  push    r13
0x18000f39c  push    r14
0x18000f39e  push    r15
0x18000f3a0  lea     rbp, [rsp-1Fh]
0x18000f3a5  sub     rsp, 0C0h
0x18000f3ac  mov     rax, cs:__security_cookie
0x18000f3b3  xor     rax, rsp
0x18000f3b6  mov     [rbp+4Fh+var_40], rax
0x18000f3ba  mov     rax, [rbp+4Fh+arg_20]
0x18000f3be  xor     r13d, r13d
0x18000f3c1  mov     r12d, [rdx+0Ch]
0x18000f3c5  mov     rsi, r9
0x18000f3c8  mov     [rbp+4Fh+var_98], rdx
0x18000f3cc  mov     rdi, rdx
0x18000f3cf  mov     [rbp+4Fh+var_90], rax
0x18000f3d3  mov     dword ptr [rbp+4Fh+Data], r13d
0x18000f3d7  mov     [rbp+4Fh+hKey], r13
0x18000f3db  mov     [rbp+4Fh+cbData], r13d
0x18000f3df  mov     [rbp+4Fh+Type], r13d
0x18000f3e3  cmp     r12d, r8d
0x18000f3e6  jbe     short loc_18000F3F3
0x18000f3e8  mov     dword ptr [rdx], 80000048h
0x18000f3ee  jmp     loc_18000F669
0x18000f3f3  mov     ecx, [rdx+8]
0x18000f3f6  sub     ecx, 10003h
0x18000f3fc  jz      short loc_18000F42D
0x18000f3fe  sub     ecx, 1
0x18000f401  jz      short loc_18000F42D
0x18000f403  sub     ecx, 0FFFCh
0x18000f409  jz      short loc_18000F42D
0x18000f40b  sub     ecx, 1
0x18000f40e  jz      short loc_18000F42D
0x18000f410  sub     ecx, 1
0x18000f413  jz      short loc_18000F42D
0x18000f415  sub     ecx, 0FFFEh
0x18000f41b  jz      short loc_18000F42D
0x18000f41d  cmp     ecx, 1
0x18000f420  jz      short loc_18000F42D
0x18000f422  mov     dword ptr [rdx], 8000000Ch
0x18000f428  jmp     loc_18000F655
0x18000f42d  cmp     r12d, 18h
0x18000f431  jnb     short loc_18000F43E
0x18000f433  mov     dword ptr [rdx], 8000004Dh
0x18000f439  jmp     loc_18000F655
0x18000f43e  lea     rax, [rbp+4Fh+hKey]
0x18000f442  mov     r9d, 0F003Fh; samDesired
0x18000f448  xor     r8d, r8d; ulOptions
0x18000f44b  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18000f450  lea     rdx, gszRegKeyProviders; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000f457  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f45e  call    cs:__imp_RegOpenKeyExW
0x18000f464  test    eax, eax
0x18000f466  jnz     short loc_18000F49D
0x18000f468  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000f46c  lea     rax, [rbp+4Fh+cbData]
0x18000f470  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18000f475  lea     r9, [rbp+4Fh+Type]; lpType
0x18000f479  lea     rax, [rbp+4Fh+Data]
0x18000f47d  mov     [rbp+4Fh+cbData], 4
0x18000f484  xor     r8d, r8d; lpReserved
0x18000f487  mov     [rsp+0F0h+phkResult], rax; lpData
0x18000f48c  lea     rdx, gszNumProviders; "NumProviders"
0x18000f493  mov     dword ptr [rbp+4Fh+Data], r13d
0x18000f497  call    cs:__imp_RegQueryValueExW
0x18000f49d  mov     ebx, dword ptr [rbp+4Fh+Data]
0x18000f4a0  mov     edx, 8; dwFlags
0x18000f4a5  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18000f4ac  mov     r8d, 208h; dwBytes
0x18000f4b2  add     ebx, 2
0x18000f4b5  call    cs:__imp_HeapAlloc
0x18000f4bb  mov     r15, rax
0x18000f4be  test    rax, rax
0x18000f4c1  jnz     short loc_18000F4CE
0x18000f4c3  mov     dword ptr [rdi], 80000044h
0x18000f4c9  jmp     loc_18000F655
0x18000f4ce  lea     r14d, [rbx+rbx*2]
0x18000f4d2  shl     r14d, 2
0x18000f4d6  lea     rcx, [rsi+18h]
0x18000f4da  mov     eax, r14d
0x18000f4dd  add     rax, rsi
0x18000f4e0  mov     [rbp+4Fh+lpData], rcx
0x18000f4e4  mov     qword ptr [rbp+4Fh+var_A8], rax
0x18000f4e8  cmp     dword ptr [rbp+4Fh+Data], r13d
0x18000f4ec  jbe     loc_18000F5F8
0x18000f4f2  mov     rdi, rax
0x18000f4f5  lea     r9, gszProviderFilename; "ProviderFilename"
0x18000f4fc  mov     [rbp+4Fh+var_A8], 0
0x18000f503  lea     r8, aSD; "%s%d"
0x18000f50a  mov     dword ptr [rsp+0F0h+phkResult], r13d
0x18000f50f  mov     edx, 40h ; '@'; cbDest
0x18000f514  lea     rcx, [rbp+4Fh+pszDest]; pszDest
0x18000f518  call    StringCbPrintfW
0x18000f51d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000f521  lea     rax, [rbp+4Fh+var_A8]
0x18000f525  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18000f52a  lea     r9, [rbp+4Fh+Type]; lpType
0x18000f52e  xor     r8d, r8d; lpReserved
0x18000f531  mov     [rsp+0F0h+phkResult], r15; lpData
0x18000f536  lea     rdx, [rbp+4Fh+pszDest]; lpValueName
0x18000f53a  mov     [rbp+4Fh+var_A8], 208h
0x18000f541  call    cs:__imp_RegQueryValueExW
0x18000f547  test    eax, eax
0x18000f549  jz      short loc_18000F551
0x18000f54b  xor     eax, eax
0x18000f54d  mov     [r15], ax
0x18000f551  mov     rcx, r15; lpString
0x18000f554  call    cs:__imp_lstrlenW
0x18000f55a  lea     r14d, [r14+rax*2]
0x18000f55e  add     r14d, 2
0x18000f562  lea     ebx, ds:2[rax*2]
0x18000f569  cmp     r12d, r14d
0x18000f56c  jb      short loc_18000F5E7
0x18000f56e  lea     r9, gszProviderID; "ProviderID"
0x18000f575  mov     dword ptr [rsp+0F0h+phkResult], r13d
0x18000f57a  lea     r8, aSD; "%s%d"
0x18000f581  mov     edx, 40h ; '@'; cbDest
0x18000f586  lea     rcx, [rbp+4Fh+pszDest]; pszDest
0x18000f58a  call    StringCbPrintfW
0x18000f58f  mov     rax, [rbp+4Fh+lpData]
0x18000f593  lea     rcx, [rbp+4Fh+cbData]
0x18000f597  mov     [rsp+0F0h+lpcbData], rcx; lpcbData
0x18000f59c  lea     r9, [rbp+4Fh+Type]; lpType
0x18000f5a0  mov     [rbp+4Fh+cbData], 4
0x18000f5a7  lea     rdx, [rbp+4Fh+pszDest]; lpValueName
0x18000f5ab  xor     r8d, r8d; lpReserved
0x18000f5ae  mov     [rsp+0F0h+phkResult], rax; lpData
0x18000f5b3  mov     dword ptr [rax], 0
0x18000f5b9  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000f5bd  call    cs:__imp_RegQueryValueExW
0x18000f5c3  mov     rcx, [rbp+4Fh+lpData]
0x18000f5c7  mov     eax, edi
0x18000f5c9  sub     eax, esi
0x18000f5cb  mov     r8d, ebx; Size
0x18000f5ce  mov     rdx, r15; Src
0x18000f5d1  mov     [rcx+4], ebx
0x18000f5d4  mov     [rcx+8], eax
0x18000f5d7  mov     rcx, rdi; void *
0x18000f5da  call    memcpy_0
0x18000f5df  add     rdi, rbx
0x18000f5e2  add     [rbp+4Fh+lpData], 0Ch
0x18000f5e7  inc     r13d
0x18000f5ea  cmp     r13d, dword ptr [rbp+4Fh+Data]
0x18000f5ee  jb      loc_18000F4F5
0x18000f5f4  mov     rdi, [rbp+4Fh+var_98]
0x18000f5f8  mov     rcx, r15; lpMem
0x18000f5fb  call    ServerFree
0x18000f600  mov     [rsi], r12d
0x18000f603  mov     [rsi+4], r14d
0x18000f607  cmp     r12d, r14d
0x18000f60a  jb      short loc_18000F61F
0x18000f60c  mov     eax, dword ptr [rbp+4Fh+Data]
0x18000f60f  mov     edx, 18h
0x18000f614  mov     [rsi+0Ch], eax
0x18000f617  lea     ecx, [rax+rax*2]
0x18000f61a  shl     ecx, 2
0x18000f61d  jmp     short loc_18000F62E
0x18000f61f  xor     edx, edx
0x18000f621  mov     dword ptr [rsi+0Ch], 0
0x18000f628  xor     ecx, ecx
0x18000f62a  lea     r14d, [rdx+18h]
0x18000f62e  mov     [rsi+10h], ecx
0x18000f631  mov     rcx, [rbp+4Fh+var_90]
0x18000f635  mov     [rsi+8], r14d
0x18000f639  mov     [rsi+14h], edx
0x18000f63c  mov     dword ptr [rdi+0Ch], 0
0x18000f643  mov     eax, [rsi+8]
0x18000f646  add     eax, 3Ch ; '<'
0x18000f649  mov     [rcx], eax
0x18000f64b  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000f64f  call    cs:__imp_RegCloseKey
0x18000f655  mov     r8d, [rdi]
0x18000f658  lea     rdx, aLinegetprovide; "lineGetProviderList: exit, result=x%x"
0x18000f65f  mov     ecx, 80002h
0x18000f664  call    TRACELogPrint
0x18000f669  mov     rcx, [rbp+4Fh+var_40]
0x18000f66d  xor     rcx, rsp; StackCookie
0x18000f670  call    __security_check_cookie
0x18000f675  mov     rbx, [rsp+0F0h+arg_0]
0x18000f67d  add     rsp, 0C0h
0x18000f684  pop     r15
0x18000f686  pop     r14
0x18000f688  pop     r13
0x18000f68a  pop     r12
0x18000f68c  pop     rdi
0x18000f68d  pop     rsi
0x18000f68e  pop     rbp
0x18000f68f  retn
```
