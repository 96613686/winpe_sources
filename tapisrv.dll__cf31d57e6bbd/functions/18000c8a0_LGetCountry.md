# LGetCountry

- ea: `0x18000c8a0`
- end: `0x18000cd18`
- name: `LGetCountry`
- size: `1144`
- prototype: `void __fastcall(__int64, int *, unsigned int, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x180001600`
- `0x1800028cc`
- `0x180002b1c`
- `0x180006208`
- `0x18000c8a0`
- `0x18001a618`
- `0x18001c8a4`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cacb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cb0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cb23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cacb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cb0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cb23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca89`
- `RPCRT4!RpcRevertToSelf` at `0x18000c924`
- `RPCRT4!RpcRevertToSelf` at `0x18000cb8a`
- `RPCRT4!RpcRevertToSelf` at `0x18000cb92`
- `RPCRT4!RpcRevertToSelf` at `0x18000c924`
- `RPCRT4!RpcRevertToSelf` at `0x18000cb8a`
- `RPCRT4!RpcRevertToSelf` at `0x18000cb92`
- `RPCRT4!RpcImpersonateClient` at `0x18000c90e`
- `RPCRT4!RpcImpersonateClient` at `0x18000cb32`
- `RPCRT4!RpcImpersonateClient` at `0x18000c90e`
- `RPCRT4!RpcImpersonateClient` at `0x18000cb32`
- `KERNEL32!HeapAlloc` at `0x18000c98b`
- `KERNEL32!HeapAlloc` at `0x18000caa0`
- `KERNEL32!HeapAlloc` at `0x18000c98b`
- `KERNEL32!HeapAlloc` at `0x18000caa0`

## pseudocode

```c
void __fastcall LGetCountry(__int64 a1, int *a2, unsigned int a3, _DWORD *a4, _DWORD *a5)
{
  _DWORD *v7; // rbx
  unsigned int v8; // eax
  void *v9; // rcx
  _DWORD *v10; // rdi
  __int64 v11; // rsi
  int v12; // r9d
  unsigned int *i; // r13
  int v14; // eax
  unsigned int *v15; // rax
  unsigned int v16; // ebx
  __int64 v17; // r14
  unsigned int v18; // r14d
  __int64 v19; // rsi
  char *v20; // rbx
  __int64 v21; // rdi
  char *v22; // rbx
  _DWORD *v23; // rcx
  int v24; // eax
  unsigned int v25; // ebx
  _DWORD *v26; // rcx
  int v27; // r8d
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h]
  _DWORD *v31; // [rsp+48h] [rbp-B8h]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h]
  char *v33; // [rsp+58h] [rbp-A8h]
  _DWORD *v34; // [rsp+60h] [rbp-A0h]
  wchar_t Src[96]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[256]; // [rsp+130h] [rbp+30h] BYREF

  v34 = a5;
  if ( a2[5] > a3 )
    goto LABEL_29;
  if ( (unsigned int)a2[5] >= 0x18 )
  {
    BuildCountryListCache();
    if ( !a2[2] )
    {
      if ( !RpcImpersonateClient(0) )
      {
        v7 = (_DWORD *)BuildCountryList();
        RpcRevertToSelf();
        if ( v7 )
        {
          v8 = v7[1];
          if ( a2[5] < v8 )
          {
            a4[1] = v8;
            *((_QWORD *)a4 + 1) = 24;
            *((_QWORD *)a4 + 2) = 0;
          }
          else
          {
            memcpy_0(a4, v7, (unsigned int)v7[2]);
          }
          v9 = v7;
          *a5 = a4[2] + 60;
          *a4 = a2[5];
          goto LABEL_40;
        }
      }
LABEL_29:
      *a2 = -2147483576;
      return;
    }
    v31 = HeapAlloc(ghTapisrvHeap, 8u, 0x4CCu);
    v10 = v31;
    if ( !v31 )
    {
      TRACELogPrint(65538, "Alloc failed for countrylist");
      *a2 = -2147483580;
      goto LABEL_41;
    }
    v11 = gpCountryList;
    v12 = a2[2];
    v30 = gpCountryList;
    for ( i = (unsigned int *)(gpCountryList + 24); *i != v12 && i[2]; i += 11 )
      ;
    if ( *i != v12 )
    {
      TRACELogPrint(65538, "Invalid Countrycode (%ld) in lineGetCountry", v12);
      *a2 = -2147483614;
LABEL_39:
      v9 = v10;
LABEL_40:
      ServerFree(v9);
      goto LABEL_41;
    }
    v14 = a2[4];
    lpMem = 0;
    if ( v14 )
    {
      phkResult = 0;
      hKey = 0;
      StringCbPrintfW(pszDest, 0x200u, L"Country/region List\\%ld\\Exceptions\\%ld");
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
             0,
             0x20019u,
             &hKey)
        || RegOpenKeyExW(hKey, pszDest, 0, 0x20019u, &phkResult) )
      {
        v11 = gpCountryList;
        v30 = gpCountryList;
      }
      else
      {
        v15 = (unsigned int *)HeapAlloc(ghTapisrvHeap, 8u, 0x4CCu);
        lpMem = v15;
        if ( !v15 )
        {
          ServerFree(v10);
          RegCloseKey(hKey);
          RegCloseKey(phkResult);
          *a2 = -2147483580;
          return;
        }
        i = v15 + 6;
        v30 = (__int64)v15;
        v33 = (char *)(v15 + 17);
        v11 = (__int64)v15;
        FillupACountryEntry(phkResult);
        RegCloseKey(phkResult);
      }
      RegCloseKey(hKey);
    }
    v16 = *(_DWORD *)(i[4] + v11);
    if ( !RpcImpersonateClient(0) )
    {
      if ( (unsigned int)LoadCountryNameString(*i, v16, Src) )
      {
        RpcRevertToSelf();
        v17 = -1;
        do
          ++v17;
        while ( Src[v17] );
        v18 = 2 * v17 + 2;
        memcpy_0(v10 + 17, Src, v18);
        v10[9] = v18;
        v10[10] = 68;
        memcpy_0((char *)v10 + v18 + 68, (const void *)(v11 + i[6]), i[5]);
        v10[11] = i[5];
        v10[12] = v18 + 68;
        v19 = i[5];
        v20 = (char *)v10 + v18 + v19 + 68;
        memcpy_0(v20, (const void *)(v30 + i[8]), i[7]);
        v10[13] = i[7];
        v10[14] = v19 + v18 + 68;
        v21 = i[7];
        v22 = &v20[v21];
        memcpy_0(v22, (const void *)(v30 + i[10]), i[9]);
        v23 = v31;
        LODWORD(v22) = (_DWORD)v22 - (_DWORD)v31;
        v31[15] = i[9];
        v23[16] = (_DWORD)v22;
        v24 = v21 + i[9];
        v10 = v23;
        v25 = v19 + v24 + v18 + 68;
        if ( a2[5] < v25 )
        {
          *((_QWORD *)a4 + 1) = 24;
          *((_QWORD *)a4 + 2) = 0;
        }
        else
        {
          a4[2] = v25;
          a4[3] = 1;
          a4[4] = 44;
          a4[5] = 24;
          v23[6] = a2[2];
          v23[7] = i[1];
          v23[8] = i[2];
          memcpy_0(a4 + 6, v23 + 6, (unsigned int)a4[2] - 24LL);
        }
        v26 = v34;
        a4[1] = v25;
        *a4 = a2[5];
        *v26 = a4[2] + 60;
        if ( lpMem )
          ServerFree(lpMem);
        goto LABEL_39;
      }
      RpcRevertToSelf();
    }
    ServerFree(v10);
    goto LABEL_29;
  }
  *a2 = -2147483571;
LABEL_41:
  v27 = *a2;
  a2[5] = 0;
  TRACELogPrint(524290, "lineGetCountry: exit, result=x%x", v27);
}

```

## disassembly

```asm
0x18000c8a0  mov     [rsp-8+arg_0], rbx
0x18000c8a5  push    rbp
0x18000c8a6  push    rsi
0x18000c8a7  push    rdi
0x18000c8a8  push    r12
0x18000c8aa  push    r13
0x18000c8ac  push    r14
0x18000c8ae  push    r15
0x18000c8b0  lea     rbp, [rsp-240h]
0x18000c8b8  sub     rsp, 340h
0x18000c8bf  mov     rax, cs:__security_cookie
0x18000c8c6  xor     rax, rsp
0x18000c8c9  mov     [rbp+270h+var_40], rax
0x18000c8d0  mov     r15, r9
0x18000c8d3  mov     rdi, [rbp+270h+arg_20]
0x18000c8da  mov     r12, rdx
0x18000c8dd  mov     [rsp+370h+var_310], rdi
0x18000c8e2  cmp     [rdx+14h], r8d
0x18000c8e6  ja      loc_18000CB44
0x18000c8ec  xor     r14d, r14d
0x18000c8ef  cmp     dword ptr [rdx+14h], 18h
0x18000c8f3  jnb     short loc_18000C900
0x18000c8f5  mov     dword ptr [rdx], 8000004Dh
0x18000c8fb  jmp     loc_18000CCF9
0x18000c900  call    BuildCountryListCache
0x18000c905  cmp     [r12+8], r14d
0x18000c90a  jnz     short loc_18000C977
0x18000c90c  xor     ecx, ecx; BindingHandle
0x18000c90e  call    cs:__imp_RpcImpersonateClient
0x18000c914  test    eax, eax
0x18000c916  jnz     loc_18000CB44
0x18000c91c  call    BuildCountryList
0x18000c921  mov     rbx, rax
0x18000c924  call    cs:__imp_RpcRevertToSelf
0x18000c92a  test    rbx, rbx
0x18000c92d  jz      loc_18000CB44
0x18000c933  mov     eax, [rbx+4]
0x18000c936  cmp     [r12+14h], eax
0x18000c93b  jb      short loc_18000C94E
0x18000c93d  mov     r8d, [rbx+8]; Size
0x18000c941  mov     rdx, rbx; Src
0x18000c944  mov     rcx, r15; void *
0x18000c947  call    memcpy_0
0x18000c94c  jmp     short loc_18000C95E
0x18000c94e  mov     [r15+4], eax
0x18000c952  mov     qword ptr [r15+8], 18h
0x18000c95a  mov     [r15+10h], r14
0x18000c95e  mov     eax, [r15+8]
0x18000c962  mov     rcx, rbx
0x18000c965  add     eax, 3Ch ; '<'
0x18000c968  mov     [rdi], eax
0x18000c96a  mov     eax, [r12+14h]
0x18000c96f  mov     [r15], eax
0x18000c972  jmp     loc_18000CCF4
0x18000c977  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18000c97e  mov     ebx, 4CCh
0x18000c983  mov     r8d, ebx; dwBytes
0x18000c986  mov     edx, 8; dwFlags
0x18000c98b  call    cs:__imp_HeapAlloc
0x18000c991  mov     [rsp+370h+var_328], rax
0x18000c996  mov     rdi, rax
0x18000c999  test    rax, rax
0x18000c99c  jnz     short loc_18000C9BC
0x18000c99e  lea     rdx, aAllocFailedFor; "Alloc failed for countrylist"
0x18000c9a5  mov     ecx, 10002h
0x18000c9aa  call    TRACELogPrint
0x18000c9af  mov     dword ptr [r12], 80000044h
0x18000c9b7  jmp     loc_18000CCF9
0x18000c9bc  mov     rsi, cs:gpCountryList
0x18000c9c3  mov     r9d, [r12+8]
0x18000c9c8  mov     [rsp+370h+var_330], rsi
0x18000c9cd  lea     r13, [rsi+18h]
0x18000c9d1  jmp     short loc_18000C9DD
0x18000c9d3  cmp     [r13+8], r14d
0x18000c9d7  jz      short loc_18000C9E3
0x18000c9d9  add     r13, 2Ch ; ','
0x18000c9dd  cmp     [r13+0], r9d
0x18000c9e1  jnz     short loc_18000C9D3
0x18000c9e3  cmp     [r13+0], r9d
0x18000c9e7  jz      short loc_18000CA0A
0x18000c9e9  mov     r8d, r9d
0x18000c9ec  lea     rdx, aInvalidCountry; "Invalid Countrycode (%ld) in lineGetCou"...
0x18000c9f3  mov     ecx, 10002h
0x18000c9f8  call    TRACELogPrint
0x18000c9fd  mov     dword ptr [r12], 80000022h
0x18000ca05  jmp     loc_18000CCF1
0x18000ca0a  mov     eax, [r12+10h]
0x18000ca0f  mov     [rsp+370h+lpMem], r14
0x18000ca14  test    eax, eax
0x18000ca16  jz      loc_18000CB29
0x18000ca1c  lea     r8, aCountryRegionL; "Country/region List\\%ld\\Exceptions\\%"...
0x18000ca23  mov     [rsp+370h+var_340], r14
0x18000ca28  mov     edx, 200h; cbDest
0x18000ca2d  mov     [rsp+370h+hKey], r14
0x18000ca32  lea     rcx, [rbp+270h+pszDest]; pszDest
0x18000ca36  mov     dword ptr [rsp+370h+phkResult], eax
0x18000ca3a  call    StringCbPrintfW
0x18000ca3f  lea     rax, [rsp+370h+hKey]
0x18000ca44  mov     esi, 20019h
0x18000ca49  mov     r9d, esi; samDesired
0x18000ca4c  mov     [rsp+370h+phkResult], rax; phkResult
0x18000ca51  xor     r8d, r8d; ulOptions
0x18000ca54  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ca5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ca62  call    cs:__imp_RegOpenKeyExW
0x18000ca68  test    eax, eax
0x18000ca6a  jnz     loc_18000CB12
0x18000ca70  mov     rcx, [rsp+370h+hKey]; hKey
0x18000ca75  lea     rax, [rsp+370h+var_340]
0x18000ca7a  mov     r9d, esi; samDesired
0x18000ca7d  mov     [rsp+370h+phkResult], rax; phkResult
0x18000ca82  xor     r8d, r8d; ulOptions
0x18000ca85  lea     rdx, [rbp+270h+pszDest]; lpSubKey
0x18000ca89  call    cs:__imp_RegOpenKeyExW
0x18000ca8f  test    eax, eax
0x18000ca91  jnz     short loc_18000CB12
0x18000ca93  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18000ca9a  lea     edx, [rax+8]; dwFlags
0x18000ca9d  mov     r8, rbx; dwBytes
0x18000caa0  call    cs:__imp_HeapAlloc
0x18000caa6  mov     [rsp+370h+lpMem], rax
0x18000caab  mov     rbx, rax
0x18000caae  test    rax, rax
0x18000cab1  jnz     short loc_18000CADB
0x18000cab3  mov     rcx, rdi; lpMem
0x18000cab6  call    ServerFree
0x18000cabb  mov     rcx, [rsp+370h+hKey]; hKey
0x18000cac0  call    cs:__imp_RegCloseKey
0x18000cac6  mov     rcx, [rsp+370h+var_340]; hKey
0x18000cacb  call    cs:__imp_RegCloseKey
0x18000cad1  mov     dword ptr [r12], 80000044h
0x18000cad9  jmp     short loc_18000CB4C
0x18000cadb  mov     rcx, [rsp+370h+var_340]; hKey
0x18000cae0  lea     r13, [rax+18h]
0x18000cae4  add     rax, 44h ; 'D'
0x18000cae8  mov     [rsp+370h+var_330], rbx
0x18000caed  mov     r8, r13
0x18000caf0  mov     [rsp+370h+var_318], rax
0x18000caf5  lea     r9, [rsp+370h+var_318]
0x18000cafa  mov     rdx, rbx
0x18000cafd  mov     rsi, rbx
0x18000cb00  call    FillupACountryEntry
0x18000cb05  mov     rcx, [rsp+370h+var_340]; hKey
0x18000cb0a  call    cs:__imp_RegCloseKey
0x18000cb10  jmp     short loc_18000CB1E
0x18000cb12  mov     rsi, cs:gpCountryList
0x18000cb19  mov     [rsp+370h+var_330], rsi
0x18000cb1e  mov     rcx, [rsp+370h+hKey]; hKey
0x18000cb23  call    cs:__imp_RegCloseKey
0x18000cb29  mov     eax, [r13+10h]
0x18000cb2d  xor     ecx, ecx; BindingHandle
0x18000cb2f  mov     ebx, [rax+rsi]
0x18000cb32  call    cs:__imp_RpcImpersonateClient
0x18000cb38  test    eax, eax
0x18000cb3a  jz      short loc_18000CB76
0x18000cb3c  mov     rcx, rdi; lpMem
0x18000cb3f  call    ServerFree
0x18000cb44  mov     dword ptr [r12], 80000048h
0x18000cb4c  mov     rcx, [rbp+270h+var_40]
0x18000cb53  xor     rcx, rsp; StackCookie
0x18000cb56  call    __security_check_cookie
0x18000cb5b  mov     rbx, [rsp+370h+arg_0]
0x18000cb63  add     rsp, 340h
0x18000cb6a  pop     r15
0x18000cb6c  pop     r14
0x18000cb6e  pop     r13
0x18000cb70  pop     r12
0x18000cb72  pop     rdi
0x18000cb73  pop     rsi
0x18000cb74  pop     rbp
0x18000cb75  retn
0x18000cb76  mov     ecx, [r13+0]
0x18000cb7a  lea     r8, [rsp+370h+Src]
0x18000cb7f  mov     edx, ebx
0x18000cb81  call    LoadCountryNameString
0x18000cb86  test    eax, eax
0x18000cb88  jnz     short loc_18000CB92
0x18000cb8a  call    cs:__imp_RpcRevertToSelf
0x18000cb90  jmp     short loc_18000CB3C
0x18000cb92  call    cs:__imp_RpcRevertToSelf
0x18000cb98  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000cb9c  lea     rcx, [rsp+370h+Src]
0x18000cba1  xor     eax, eax
0x18000cba3  inc     r14
0x18000cba6  cmp     [rcx+r14*2], ax
0x18000cbab  jnz     short loc_18000CBA3
0x18000cbad  lea     r14d, ds:2[r14*2]
0x18000cbb5  mov     r8d, r14d; Size
0x18000cbb8  lea     rdx, [rsp+370h+Src]; Src
0x18000cbbd  lea     rcx, [rdi+44h]; void *
0x18000cbc1  mov     ebx, r14d
0x18000cbc4  call    memcpy_0
0x18000cbc9  lea     rcx, [rdi+44h]
0x18000cbcd  mov     [rdi+24h], r14d
0x18000cbd1  mov     eax, ecx
0x18000cbd3  add     rbx, rcx
0x18000cbd6  sub     eax, edi
0x18000cbd8  mov     rcx, rbx; void *
0x18000cbdb  mov     [rdi+28h], eax
0x18000cbde  mov     edx, [r13+18h]
0x18000cbe2  mov     r8d, [r13+14h]; Size
0x18000cbe6  add     rdx, rsi; Src
0x18000cbe9  call    memcpy_0
0x18000cbee  mov     eax, [r13+14h]
0x18000cbf2  mov     [rdi+2Ch], eax
0x18000cbf5  mov     eax, ebx
0x18000cbf7  sub     eax, edi
0x18000cbf9  mov     [rdi+30h], eax
0x18000cbfc  mov     esi, [r13+14h]
0x18000cc00  mov     edx, [r13+20h]
0x18000cc04  add     rbx, rsi
0x18000cc07  mov     r8d, [r13+1Ch]; Size
0x18000cc0b  mov     rcx, rbx; void *
0x18000cc0e  add     rdx, [rsp+370h+var_330]; Src
0x18000cc13  call    memcpy_0
0x18000cc18  mov     eax, [r13+1Ch]
0x18000cc1c  mov     [rdi+34h], eax
0x18000cc1f  mov     eax, ebx
0x18000cc21  sub     eax, edi
0x18000cc23  mov     [rdi+38h], eax
0x18000cc26  mov     edi, [r13+1Ch]
0x18000cc2a  mov     edx, [r13+28h]
0x18000cc2e  add     rbx, rdi
0x18000cc31  mov     r8d, [r13+24h]; Size
0x18000cc35  mov     rcx, rbx; void *
0x18000cc38  add     rdx, [rsp+370h+var_330]; Src
0x18000cc3d  call    memcpy_0
0x18000cc42  mov     rcx, [rsp+370h+var_328]
0x18000cc47  mov     eax, [r13+24h]
0x18000cc4b  sub     ebx, ecx
0x18000cc4d  mov     [rcx+3Ch], eax
0x18000cc50  mov     [rcx+40h], ebx
0x18000cc53  lea     ebx, [r14+44h]
0x18000cc57  mov     eax, [r13+24h]
0x18000cc5b  add     eax, edi
0x18000cc5d  mov     rdi, rcx
0x18000cc60  add     eax, esi
0x18000cc62  add     ebx, eax
0x18000cc64  cmp     [r12+14h], ebx
0x18000cc69  jb      short loc_18000CCB6
0x18000cc6b  mov     [r15+8], ebx
0x18000cc6f  lea     rdx, [rcx+18h]; Src
0x18000cc73  mov     dword ptr [r15+0Ch], 1
0x18000cc7b  mov     dword ptr [r15+10h], 2Ch ; ','
0x18000cc83  mov     dword ptr [r15+14h], 18h
0x18000cc8b  mov     eax, [r12+8]
0x18000cc90  mov     [rdx], eax
0x18000cc92  mov     eax, [r13+4]
0x18000cc96  mov     [rcx+1Ch], eax
0x18000cc99  mov     eax, [r13+8]
0x18000cc9d  mov     [rcx+20h], eax
0x18000cca0  lea     rcx, [r15+18h]; void *
0x18000cca4  mov     r8d, [r15+8]
0x18000cca8  sub     r8, 18h; Size
0x18000ccac  call    memcpy_0
0x18000ccb1  xor     r14d, r14d
0x18000ccb4  jmp     short loc_18000CCC5
0x18000ccb6  xor     r14d, r14d
0x18000ccb9  mov     qword ptr [r15+8], 18h
0x18000ccc1  mov     [r15+10h], r14
0x18000ccc5  mov     rcx, [rsp+370h+var_310]
0x18000ccca  mov     [r15+4], ebx
0x18000ccce  mov     eax, [r12+14h]
0x18000ccd3  mov     [r15], eax
0x18000ccd6  mov     eax, [r15+8]
0x18000ccda  add     eax, 3Ch ; '<'
0x18000ccdd  mov     [rcx], eax
0x18000ccdf  mov     rax, [rsp+370h+lpMem]
0x18000cce4  test    rax, rax
0x18000cce7  jz      short loc_18000CCF1
0x18000cce9  mov     rcx, rax; lpMem
0x18000ccec  call    ServerFree
0x18000ccf1  mov     rcx, rdi; lpMem
0x18000ccf4  call    ServerFree
0x18000ccf9  mov     r8d, [r12]
0x18000ccfd  lea     rdx, aLinegetcountry; "lineGetCountry: exit, result=x%x"
0x18000cd04  mov     ecx, 80002h
0x18000cd09  mov     [r12+14h], r14d
0x18000cd0e  call    TRACELogPrint
0x18000cd13  jmp     loc_18000CB4C
```
