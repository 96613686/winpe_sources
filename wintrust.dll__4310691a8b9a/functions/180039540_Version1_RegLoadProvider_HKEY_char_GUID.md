# Version1_RegLoadProvider(HKEY__ *,char *,_GUID *)

- ea: `0x180039540`
- end: `0x18003989b`
- name: `?Version1_RegLoadProvider@@YAPEAU_LOADED_PROVIDER_V1@@PEAUHKEY__@@PEADPEAU_GUID@@@Z`
- size: `859`
- prototype: `struct _LOADED_PROVIDER_V1 *__fastcall(HKEY hKey, LPCCH lpMultiByteStr, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000a410`

## callees

- `0x18002e590`
- `0x18002e5d0`
- `0x18002e5dc`
- `0x1800326fc`
- `0x180039540`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039747`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180039747`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003977b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003977b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003981e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003981e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039766`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180039736`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180039736`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180039697`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800396c5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180039697`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800396c5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180039758`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180039758`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800395b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003961a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003967a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800395b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003961a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003967a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800396ef`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800397a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800396ef`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800397a2`

## pseudocode

```c
struct _LOADED_PROVIDER_V1 *__fastcall Version1_RegLoadProvider(HKEY hKey, LPCCH lpMultiByteStr, struct _GUID *a3)
{
  const CHAR *v4; // r15
  signed int i; // ecx
  __int64 v7; // rax
  BYTE *lpData; // rax
  CHAR *v9; // rdi
  _DWORD *v10; // rbx
  WCHAR *v11; // r12
  char *v12; // r14
  DWORD v13; // eax
  DWORD v14; // r15d
  CHAR *v15; // rax
  CHAR *v16; // rsi
  unsigned int v17; // esi
  unsigned __int64 v18; // r13
  WCHAR *v19; // rax
  HMODULE Library; // rsi
  FARPROC ProcAddress; // r15
  int v22; // eax
  _DWORD *v23; // rax
  DWORD cbData; // [rsp+30h] [rbp-A9h] BYREF
  DWORD Type; // [rsp+34h] [rbp-A5h] BYREF
  LPCSTR lpString; // [rsp+38h] [rbp-A1h]
  __int64 v28; // [rsp+40h] [rbp-99h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-89h] BYREF
  _QWORD v30[19]; // [rsp+58h] [rbp-81h]

  lpString = lpMultiByteStr;
  v28 = 0;
  v4 = lpMultiByteStr;
  Type = 0;
  cbData = 160;
  if ( !RegQueryValueExA(hKey, "$ActionIDs", 0, &Type, Data, &cbData) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= (int)(cbData >> 4) )
        return 0;
      v7 = *(_QWORD *)&Data[16 * i] - *(_QWORD *)&a3->Data1;
      if ( !v7 )
        v7 = v30[2 * i] - *(_QWORD *)a3->Data4;
      if ( !v7 )
        break;
    }
    if ( RegQueryValueExA(hKey, "$DLL", 0, &Type, 0, &cbData) )
      return 0;
    lpData = (BYTE *)operator new[](++cbData);
    v9 = (CHAR *)lpData;
    if ( !lpData )
      return 0;
    v10 = 0;
    v11 = 0;
    v12 = 0;
    lpData[cbData - 1] = 0;
    if ( !RegQueryValueExA(hKey, "$DLL", 0, &Type, lpData, &cbData) )
    {
      if ( Type != 2 )
        goto LABEL_17;
      v13 = ExpandEnvironmentStringsA(v9, 0, 0);
      v14 = v13;
      if ( v13 )
      {
        v15 = (CHAR *)operator new[](v13);
        v16 = v15;
        if ( v15 )
        {
          if ( !ExpandEnvironmentStringsA(v9, v15, v14) )
          {
            operator delete(v16);
            goto LABEL_28;
          }
          operator delete(v9);
          v4 = lpString;
          v9 = v16;
LABEL_17:
          v17 = lstrlenA(v4) + 1;
          v18 = v17;
          v19 = (WCHAR *)operator new[](saturated_mul(v17, 2u));
          v11 = v19;
          if ( v19 )
          {
            MultiByteToWideChar(0, 0, v4, -1, v19, v17);
            Library = LoadLibraryExA(v9, 0, 0x800u);
            if ( Library || (Library = LoadLibraryA(v9)) != 0 )
            {
              ProcAddress = GetProcAddress(Library, "WinTrustProviderClientInitialize");
              if ( ProcAddress )
              {
                v12 = (char *)operator new[](v18);
                if ( v12 )
                {
                  v22 = lstrlenA(lpString);
                  StringCchCopyA(v12, v22, lpString);
                  v23 = operator new(0x38u);
                  v10 = v23;
                  if ( v23 )
                  {
                    v23[13] = 2;
                    *((_QWORD *)v23 + 4) = v12;
                    *(_QWORD *)v23 = 0;
                    v23[12] = 1;
                    *((_QWORD *)v23 + 1) = 0;
                    if ( ((unsigned int (__fastcall *)(__int64, void *, WCHAR *, __int64 *))ProcAddress)(
                           0x10000,
                           &WinTrustClientTPInfo,
                           v11,
                           &v28) == 1 )
                    {
                      v10[13] = 1;
                      *((_QWORD *)v10 + 2) = Library;
                      *((_QWORD *)v10 + 3) = v9;
                      *((_QWORD *)v10 + 5) = v28;
                      return (struct _LOADED_PROVIDER_V1 *)v10;
                    }
                    v10[13] = 3;
                  }
                }
              }
              FreeLibrary(Library);
            }
            else
            {
              GetLastError();
            }
            if ( !v9 )
              goto LABEL_29;
          }
        }
      }
    }
LABEL_28:
    operator delete(v9);
    if ( !v11 )
    {
LABEL_30:
      if ( v12 )
        operator delete(v12);
      if ( v10 )
        operator delete(v10);
      return 0;
    }
LABEL_29:
    operator delete(v11);
    goto LABEL_30;
  }
  return 0;
}

```

## disassembly

```asm
0x180039540  mov     [rsp-8+arg_10], rbx
0x180039545  push    rbp
0x180039546  push    rsi
0x180039547  push    rdi
0x180039548  push    r12
0x18003954a  push    r13
0x18003954c  push    r14
0x18003954e  push    r15
0x180039550  lea     rbp, [rsp-27h]
0x180039555  sub     rsp, 100h
0x18003955c  mov     rax, cs:__security_cookie
0x180039563  xor     rax, rsp
0x180039566  mov     [rbp+57h+var_40], rax
0x18003956a  lea     rax, [rsp+130h+cbData]
0x18003956f  mov     [rsp+130h+lpString], rdx
0x180039574  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180039579  lea     r9, [rsp+130h+Type]; lpType
0x18003957e  lea     rax, [rsp+130h+Data]
0x180039583  mov     [rsp+130h+var_F0], 0
0x18003958c  mov     rbx, r8
0x18003958f  mov     [rsp+130h+lpData], rax; lpData
0x180039594  mov     r15, rdx
0x180039597  mov     [rsp+130h+Type], 0
0x18003959f  xor     r8d, r8d; lpReserved
0x1800395a2  mov     [rsp+130h+cbData], 0A0h
0x1800395aa  lea     rdx, aActionids; "$ActionIDs"
0x1800395b1  mov     rsi, rcx
0x1800395b4  call    cs:__imp_RegQueryValueExA
0x1800395ba  test    eax, eax
0x1800395bc  jnz     loc_180039858
0x1800395c2  xor     ecx, ecx
0x1800395c4  mov     eax, [rsp+130h+cbData]
0x1800395c8  shr     eax, 4
0x1800395cb  cmp     ecx, eax
0x1800395cd  jge     loc_180039858
0x1800395d3  movsxd  rdx, ecx
0x1800395d6  add     rdx, rdx
0x1800395d9  mov     rax, qword ptr [rsp+rdx*8+130h+Data]
0x1800395de  sub     rax, [rbx]
0x1800395e1  jnz     short loc_1800395EC
0x1800395e3  mov     rax, [rsp+rdx*8+130h+var_D8]
0x1800395e8  sub     rax, [rbx+8]
0x1800395ec  test    rax, rax
0x1800395ef  jz      short loc_1800395F5
0x1800395f1  inc     ecx
0x1800395f3  jmp     short loc_1800395C4
0x1800395f5  lea     rax, [rsp+130h+cbData]
0x1800395fa  xor     r8d, r8d; lpReserved
0x1800395fd  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180039602  lea     r9, [rsp+130h+Type]; lpType
0x180039607  lea     rdx, aDll_0; "$DLL"
0x18003960e  mov     [rsp+130h+lpData], 0; lpData
0x180039617  mov     rcx, rsi; hKey
0x18003961a  call    cs:__imp_RegQueryValueExA
0x180039620  test    eax, eax
0x180039622  jnz     loc_180039858
0x180039628  mov     eax, [rsp+130h+cbData]
0x18003962c  inc     eax
0x18003962e  mov     ecx, eax; unsigned __int64
0x180039630  mov     [rsp+130h+cbData], eax
0x180039634  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180039639  mov     rdi, rax
0x18003963c  test    rax, rax
0x18003963f  jz      loc_180039858
0x180039645  mov     r8d, [rsp+130h+cbData]
0x18003964a  lea     r9, [rsp+130h+Type]; lpType
0x18003964f  xor     ebx, ebx
0x180039651  lea     rdx, aDll_0; "$DLL"
0x180039658  xor     r12d, r12d
0x18003965b  xor     r14d, r14d
0x18003965e  dec     r8d
0x180039661  mov     rcx, rsi; hKey
0x180039664  mov     [r8+rax], bl
0x180039668  lea     rax, [rsp+130h+cbData]
0x18003966d  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180039672  xor     r8d, r8d; lpReserved
0x180039675  mov     [rsp+130h+lpData], rdi; lpData
0x18003967a  call    cs:__imp_RegQueryValueExA
0x180039680  test    eax, eax
0x180039682  jnz     loc_180039829
0x180039688  cmp     [rsp+130h+Type], 2
0x18003968d  jnz     short loc_1800396EC
0x18003968f  xor     r8d, r8d; nSize
0x180039692  xor     edx, edx; lpDst
0x180039694  mov     rcx, rdi; lpSrc
0x180039697  call    cs:__imp_ExpandEnvironmentStringsA
0x18003969d  mov     r15d, eax
0x1800396a0  test    eax, eax
0x1800396a2  jz      loc_180039829
0x1800396a8  mov     ecx, r15d; unsigned __int64
0x1800396ab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800396b0  mov     rsi, rax
0x1800396b3  test    rax, rax
0x1800396b6  jz      loc_180039829
0x1800396bc  mov     r8d, r15d; nSize
0x1800396bf  mov     rdx, rax; lpDst
0x1800396c2  mov     rcx, rdi; lpSrc
0x1800396c5  call    cs:__imp_ExpandEnvironmentStringsA
0x1800396cb  test    eax, eax
0x1800396cd  jnz     short loc_1800396DC
0x1800396cf  mov     rcx, rsi; Block
0x1800396d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800396d7  jmp     loc_180039829
0x1800396dc  mov     rcx, rdi; Block
0x1800396df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800396e4  mov     r15, [rsp+130h+lpString]
0x1800396e9  mov     rdi, rsi
0x1800396ec  mov     rcx, r15; lpString
0x1800396ef  call    cs:__imp_lstrlenA
0x1800396f5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800396fc  lea     esi, [rax+1]
0x1800396ff  mov     eax, 2
0x180039704  mov     r13d, esi
0x180039707  mul     r13
0x18003970a  cmovb   rax, rcx
0x18003970e  mov     rcx, rax; unsigned __int64
0x180039711  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180039716  mov     r12, rax
0x180039719  test    rax, rax
0x18003971c  jz      loc_180039829
0x180039722  mov     dword ptr [rsp+130h+lpcbData], esi; cchWideChar
0x180039726  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003972a  mov     r8, r15; lpMultiByteStr
0x18003972d  mov     [rsp+130h+lpData], rax; lpWideCharStr
0x180039732  xor     edx, edx; dwFlags
0x180039734  xor     ecx, ecx; CodePage
0x180039736  call    cs:__imp_MultiByteToWideChar
0x18003973c  xor     edx, edx; hFile
0x18003973e  mov     r8d, 800h; dwFlags
0x180039744  mov     rcx, rdi; lpLibFileName
0x180039747  call    cs:__imp_LoadLibraryExA
0x18003974d  mov     rsi, rax
0x180039750  test    rax, rax
0x180039753  jnz     short loc_180039771
0x180039755  mov     rcx, rdi; lpLibFileName
0x180039758  call    cs:__imp_LoadLibraryA
0x18003975e  mov     rsi, rax
0x180039761  test    rax, rax
0x180039764  jnz     short loc_180039771
0x180039766  call    cs:__imp_GetLastError
0x18003976c  jmp     loc_180039824
0x180039771  lea     rdx, aWintrustprovid; "WinTrustProviderClientInitialize"
0x180039778  mov     rcx, rsi; hModule
0x18003977b  call    cs:__imp_GetProcAddress
0x180039781  mov     r15, rax
0x180039784  test    rax, rax
0x180039787  jz      loc_18003981B
0x18003978d  mov     rcx, r13; unsigned __int64
0x180039790  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180039795  mov     r14, rax
0x180039798  test    rax, rax
0x18003979b  jz      short loc_180039816
0x18003979d  mov     rcx, [rsp+130h+lpString]; lpString
0x1800397a2  call    cs:__imp_lstrlenA
0x1800397a8  mov     r8, [rsp+130h+lpString]; char *
0x1800397ad  mov     rcx, r14; char *
0x1800397b0  movsxd  rdx, eax; unsigned __int64
0x1800397b3  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800397b8  mov     ecx, 38h ; '8'; Size
0x1800397bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800397c2  mov     rbx, rax
0x1800397c5  test    rax, rax
0x1800397c8  jz      short loc_180039816
0x1800397ca  mov     dword ptr [rax+34h], 2
0x1800397d1  lea     r9, [rsp+130h+var_F0]
0x1800397d6  mov     [rax+20h], r14
0x1800397da  lea     rdx, ?WinTrustClientTPInfo@@3U_WINTRUST_CLIENT_TP_INFO@@A; _WINTRUST_CLIENT_TP_INFO WinTrustClientTPInfo
0x1800397e1  mov     qword ptr [rax], 0
0x1800397e8  mov     r13d, 1
0x1800397ee  mov     [rax+30h], r13d
0x1800397f2  mov     r8, r12
0x1800397f5  mov     qword ptr [rax+8], 0
0x1800397fd  mov     ecx, 10000h
0x180039802  mov     rax, r15
0x180039805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003980a  cmp     eax, r13d
0x18003980d  jz      short loc_180039881
0x18003980f  mov     dword ptr [rbx+34h], 3
0x180039816  test    rsi, rsi
0x180039819  jz      short loc_180039824
0x18003981b  mov     rcx, rsi; hLibModule
0x18003981e  call    cs:__imp_FreeLibrary
0x180039824  test    rdi, rdi
0x180039827  jz      short loc_180039836
0x180039829  mov     rcx, rdi; Block
0x18003982c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039831  test    r12, r12
0x180039834  jz      short loc_18003983E
0x180039836  mov     rcx, r12; Block
0x180039839  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003983e  test    r14, r14
0x180039841  jz      short loc_18003984B
0x180039843  mov     rcx, r14; Block
0x180039846  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003984b  test    rbx, rbx
0x18003984e  jz      short loc_180039858
0x180039850  mov     rcx, rbx; Block
0x180039853  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039858  xor     eax, eax
0x18003985a  mov     rcx, [rbp+57h+var_40]
0x18003985e  xor     rcx, rsp; StackCookie
0x180039861  call    __security_check_cookie
0x180039866  mov     rbx, [rsp+130h+arg_10]
0x18003986e  add     rsp, 100h
0x180039875  pop     r15
0x180039877  pop     r14
0x180039879  pop     r13
0x18003987b  pop     r12
0x18003987d  pop     rdi
0x18003987e  pop     rsi
0x18003987f  pop     rbp
0x180039880  retn
0x180039881  mov     [rbx+34h], r13d
0x180039885  mov     [rbx+10h], rsi
0x180039889  mov     [rbx+18h], rdi
0x18003988d  mov     rax, [rsp+130h+var_F0]
0x180039892  mov     [rbx+28h], rax
0x180039896  mov     rax, rbx
0x180039899  jmp     short loc_18003985A
```
