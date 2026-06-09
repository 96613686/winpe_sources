# GetProviderFriendlyName

- ea: `0x180031650`
- end: `0x1800319f4`
- name: `GetProviderFriendlyName`
- size: `932`
- prototype: `__int64 __fastcall(LPCWSTR lpString, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180032080`

## callees

- `0x180001600`
- `0x18001c854`
- `0x18001c8a4`
- `0x18002c8d4`
- `0x180031650`
- `0x18003dc84`
- `0x18003fb7c`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180031808`
- `KERNEL32!HeapAlloc` at `0x180031957`
- `KERNEL32!HeapAlloc` at `0x180031808`
- `KERNEL32!HeapAlloc` at `0x180031957`
- `KERNEL32!FreeLibrary` at `0x1800319d2`
- `KERNEL32!FreeLibrary` at `0x1800319d2`
- `KERNEL32!GetProcAddress` at `0x18003170e`
- `KERNEL32!GetProcAddress` at `0x180031747`
- `KERNEL32!GetProcAddress` at `0x180031773`
- `KERNEL32!GetProcAddress` at `0x18003170e`
- `KERNEL32!GetProcAddress` at `0x180031747`
- `KERNEL32!GetProcAddress` at `0x180031773`
- `KERNEL32!LoadLibraryW` at `0x1800316ab`
- `KERNEL32!LoadLibraryW` at `0x1800316ab`
- `KERNEL32!GetLastError` at `0x1800316b9`
- `KERNEL32!GetLastError` at `0x18003171e`
- `KERNEL32!GetLastError` at `0x18003175a`
- `KERNEL32!GetLastError` at `0x180031783`
- `KERNEL32!GetLastError` at `0x1800316b9`
- `KERNEL32!GetLastError` at `0x18003171e`
- `KERNEL32!GetLastError` at `0x18003175a`
- `KERNEL32!GetLastError` at `0x180031783`
- `KERNEL32!lstrlenW` at `0x180031920`
- `KERNEL32!lstrlenW` at `0x18003199b`
- `KERNEL32!lstrlenW` at `0x180031920`
- `KERNEL32!lstrlenW` at `0x18003199b`

## string_xrefs

- `0x1800316a4`: `Version.dll`
- `0x1800316bf`: `LoadLibrary('VERSION.DLL') failed! err=0x%08lx`
- `0x180031724`: `GetProcAddress('VERSION.DLL', 'GetFileVersionInfoW') failed! err=0x%08lx`
- `0x180031760`: `GetProcAddress('VERSION.DLL', 'GetFileVersionInfoSizeW') failed! err=0x%08lx`
- `0x180031789`: `GetProcAddress('VERSION.DLL', 'VerQueryValueW') failed! err=0x%08lx`

## pseudocode

```c
__int64 __fastcall GetProviderFriendlyName(LPCWSTR lpString, _QWORD *a2)
{
  void *v2; // rdi
  _QWORD *v3; // r12
  LPCWSTR v4; // rbx
  HMODULE LibraryW; // rax
  HMODULE v6; // r15
  DWORD LastError; // eax
  unsigned int v9; // esi
  char *v10; // r14
  DWORD v11; // eax
  __int64 (__fastcall *v12)(LPCWSTR, unsigned int *); // r13
  DWORD v13; // eax
  DWORD v14; // eax
  unsigned int v15; // r12d
  unsigned int v16; // r13d
  unsigned int (__fastcall *v17)(void *, wchar_t *, LPCWSTR *, int *); // r12
  int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // r13d
  char *v21; // rax
  char *v22; // r12
  int v23; // eax
  __int64 v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpStringa; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v27; // [rsp+40h] [rbp-C0h]
  unsigned int v28; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h]
  unsigned int v30; // [rsp+4Ch] [rbp-B4h]
  _QWORD *v31; // [rsp+50h] [rbp-B0h]
  FARPROC ProcAddress; // [rsp+58h] [rbp-A8h]
  FARPROC v33; // [rsp+60h] [rbp-A0h]
  FARPROC v34; // [rsp+68h] [rbp-98h]
  wchar_t pszDest[1024]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 0;
  v31 = a2;
  v28 = 0;
  v3 = a2;
  v25 = 0;
  v4 = lpString;
  lpStringa = 0;
  if ( !lpString || !a2 )
    return 0;
  LibraryW = LoadLibraryW(L"Version.dll");
  v6 = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    TRACELogPrint(65538, "LoadLibrary('VERSION.DLL') failed! err=0x%08lx", LastError);
    return 0;
  }
  v9 = 0;
  v10 = 0;
  ProcAddress = GetProcAddress(LibraryW, "GetFileVersionInfoW");
  if ( ProcAddress )
  {
    v34 = GetProcAddress(v6, "GetFileVersionInfoSizeW");
    v12 = (__int64 (__fastcall *)(LPCWSTR, unsigned int *))v34;
    if ( !v34 )
    {
      v13 = GetLastError();
      TRACELogPrint(65538, "GetProcAddress('VERSION.DLL', 'GetFileVersionInfoSizeW') failed! err=0x%08lx", v13);
      goto LABEL_43;
    }
    v33 = GetProcAddress(v6, "VerQueryValueW");
    if ( !v33 )
    {
      v14 = GetLastError();
      TRACELogPrint(65538, "GetProcAddress('VERSION.DLL', 'VerQueryValueW') failed! err=0x%08lx", v14);
      goto LABEL_43;
    }
    v15 = 0;
    v29 = 0;
    v27 = 0;
    while ( 1 )
    {
      if ( !*v4 )
      {
LABEL_42:
        v3 = v31;
        goto LABEL_43;
      }
      lpStringa = 0;
      v16 = v12(v4, &v28);
      if ( !v16 )
        break;
      if ( v16 > v15 )
      {
        if ( v2 )
          ServerFree(v2);
        v15 = v16 + 16;
        v27 = v16 + 16;
        v2 = HeapAlloc(ghTapisrvHeap, 8u, v16 + 16);
        if ( !v2 )
        {
          v27 = 0;
          goto LABEL_31;
        }
      }
      if ( !((unsigned int (__fastcall *)(LPCWSTR, _QWORD, _QWORD, void *))ProcAddress)(v4, v28, v15, v2) )
      {
        TRACELogPrint(65538, "GetFileVersionInfo failure for %S", v4);
        goto LABEL_31;
      }
      StringCbCopyW(pszDest, 0x800u, L"\\VarFileInfo\\Translation");
      v17 = (unsigned int (__fastcall *)(void *, wchar_t *, LPCWSTR *, int *))v33;
      if ( !((unsigned int (__fastcall *)(void *, wchar_t *, LPCWSTR *, int *))v33)(v2, pszDest, &lpStringa, &v25)
        || !v25 )
      {
        TRACELogPrint(65538, "ERROR:  VerQueryValue failure for %S on file %S", pszDest, v4);
        lpStringa = 0;
        goto LABEL_31;
      }
      LODWORD(v24) = lpStringa[1];
      StringCbPrintfW(pszDest, 0x800u, L"\\StringFileInfo\\%04x%04x\\FileDescription", *lpStringa, v24);
      if ( v17(v2, pszDest, &lpStringa, &v25) && v25 )
        goto LABEL_31;
      TRACELogPrint(65538, "ERROR:  VerQueryValue failure for %S on file %S", pszDest, v4);
LABEL_32:
      lpStringa = v4;
LABEL_33:
      v18 = lstrlenW(lpStringa);
      v19 = v29;
      v20 = 2 * v18 + 2;
      v30 = v9 + v20;
      if ( v9 + v20 > v29 )
      {
        v29 += 512;
        v21 = (char *)HeapAlloc(ghTapisrvHeap, 8u, v19 + 512);
        v22 = v21;
        if ( !v21 )
        {
          if ( v10 )
            ServerFree(v10);
          v9 = 0;
          goto LABEL_42;
        }
        if ( v9 )
        {
          memcpy_0(v21, v10, v9);
          ServerFree(v10);
        }
        v10 = v22;
      }
      memcpy_0(&v10[v9], lpStringa, v20);
      v9 = v30;
      v23 = lstrlenW(v4);
      v15 = v27;
      v12 = (__int64 (__fastcall *)(LPCWSTR, unsigned int *))v34;
      v4 += v23 + 1;
    }
    TRACELogPrint(65538, "GetFileVersionInfoSize failure for %S", v4);
LABEL_31:
    if ( lpStringa )
      goto LABEL_33;
    goto LABEL_32;
  }
  v11 = GetLastError();
  TRACELogPrint(65538, "GetProcAddress('VERSION.DLL', 'GetFileVersionInfoW') failed! err=0x%08lx", v11);
LABEL_43:
  FreeLibrary(v6);
  if ( v2 )
    ServerFree(v2);
  if ( v9 )
    *v3 = v10;
  return v9;
}

```

## disassembly

```asm
0x180031650  mov     [rsp-8+arg_10], rbx
0x180031655  push    rbp
0x180031656  push    rsi
0x180031657  push    rdi
0x180031658  push    r12
0x18003165a  push    r13
0x18003165c  push    r14
0x18003165e  push    r15
0x180031660  lea     rbp, [rsp-780h]
0x180031668  sub     rsp, 880h
0x18003166f  mov     rax, cs:__security_cookie
0x180031676  xor     rax, rsp
0x180031679  mov     [rbp+7B0h+var_40], rax
0x180031680  xor     edi, edi
0x180031682  mov     [rsp+8B0h+var_860], rdx
0x180031687  mov     [rsp+8B0h+var_86C], edi
0x18003168b  mov     r12, rdx
0x18003168e  mov     [rsp+8B0h+var_880], edi
0x180031692  mov     rbx, rcx
0x180031695  mov     [rsp+8B0h+lpString], rdi
0x18003169a  test    rcx, rcx
0x18003169d  jz      short loc_1800316D3
0x18003169f  test    rdx, rdx
0x1800316a2  jz      short loc_1800316D3
0x1800316a4  lea     rcx, LibFileName; "Version.dll"
0x1800316ab  call    cs:__imp_LoadLibraryW
0x1800316b1  mov     r15, rax
0x1800316b4  test    rax, rax
0x1800316b7  jnz     short loc_1800316FF
0x1800316b9  call    cs:__imp_GetLastError
0x1800316bf  lea     rdx, aLoadlibraryVer; "LoadLibrary('VERSION.DLL') failed! err="...
0x1800316c6  mov     ecx, 10002h
0x1800316cb  mov     r8d, eax
0x1800316ce  call    TRACELogPrint
0x1800316d3  xor     eax, eax
0x1800316d5  mov     rcx, [rbp+7B0h+var_40]
0x1800316dc  xor     rcx, rsp; StackCookie
0x1800316df  call    __security_check_cookie
0x1800316e4  mov     rbx, [rsp+8B0h+arg_10]
0x1800316ec  add     rsp, 880h
0x1800316f3  pop     r15
0x1800316f5  pop     r14
0x1800316f7  pop     r13
0x1800316f9  pop     r12
0x1800316fb  pop     rdi
0x1800316fc  pop     rsi
0x1800316fd  pop     rbp
0x1800316fe  retn
0x1800316ff  lea     rdx, ProcName; "GetFileVersionInfoW"
0x180031706  mov     rcx, r15; hModule
0x180031709  mov     esi, edi
0x18003170b  mov     r14, rdi
0x18003170e  call    cs:__imp_GetProcAddress
0x180031714  mov     [rsp+8B0h+var_858], rax
0x180031719  test    rax, rax
0x18003171c  jnz     short loc_18003173D
0x18003171e  call    cs:__imp_GetLastError
0x180031724  lea     rdx, aGetprocaddress; "GetProcAddress('VERSION.DLL', 'GetFileV"...
0x18003172b  mov     r8d, eax
0x18003172e  mov     ecx, 10002h
0x180031733  call    TRACELogPrint
0x180031738  jmp     loc_1800319CF
0x18003173d  lea     rdx, aGetfileversion_0; "GetFileVersionInfoSizeW"
0x180031744  mov     rcx, r15; hModule
0x180031747  call    cs:__imp_GetProcAddress
0x18003174d  mov     [rsp+8B0h+var_848], rax
0x180031752  mov     r13, rax
0x180031755  test    rax, rax
0x180031758  jnz     short loc_180031769
0x18003175a  call    cs:__imp_GetLastError
0x180031760  lea     rdx, aGetprocaddress_1; "GetProcAddress('VERSION.DLL', 'GetFileV"...
0x180031767  jmp     short loc_18003172B
0x180031769  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x180031770  mov     rcx, r15; hModule
0x180031773  call    cs:__imp_GetProcAddress
0x180031779  mov     [rsp+8B0h+var_850], rax
0x18003177e  test    rax, rax
0x180031781  jnz     short loc_180031792
0x180031783  call    cs:__imp_GetLastError
0x180031789  lea     rdx, aGetprocaddress_2; "GetProcAddress('VERSION.DLL', 'VerQuery"...
0x180031790  jmp     short loc_18003172B
0x180031792  xor     r12d, r12d
0x180031795  mov     [rsp+8B0h+var_868], esi
0x180031799  mov     [rsp+8B0h+var_870], r12d
0x18003179e  xor     eax, eax
0x1800317a0  cmp     ax, [rbx]
0x1800317a3  jz      loc_1800319CA
0x1800317a9  mov     [rsp+8B0h+lpString], rax
0x1800317ae  lea     rdx, [rsp+8B0h+var_86C]
0x1800317b3  mov     rax, r13
0x1800317b6  mov     rcx, rbx
0x1800317b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317be  mov     r13d, eax
0x1800317c1  test    eax, eax
0x1800317c3  jnz     short loc_1800317DE
0x1800317c5  lea     rdx, aGetfileversion_1; "GetFileVersionInfoSize failure for %S"
0x1800317cc  mov     r8, rbx
0x1800317cf  mov     ecx, 10002h
0x1800317d4  call    TRACELogPrint
0x1800317d9  jmp     loc_18003190E
0x1800317de  cmp     r13d, r12d
0x1800317e1  jbe     short loc_18003181F
0x1800317e3  test    rdi, rdi
0x1800317e6  jz      short loc_1800317F0
0x1800317e8  mov     rcx, rdi; lpMem
0x1800317eb  call    ServerFree
0x1800317f0  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800317f7  lea     r12d, [r13+10h]
0x1800317fb  mov     r8d, r12d; dwBytes
0x1800317fe  mov     edx, 8; dwFlags
0x180031803  mov     [rsp+8B0h+var_870], r12d
0x180031808  call    cs:__imp_HeapAlloc
0x18003180e  mov     rdi, rax
0x180031811  test    rax, rax
0x180031814  jnz     short loc_18003181F
0x180031816  mov     [rsp+8B0h+var_870], eax
0x18003181a  jmp     loc_18003190E
0x18003181f  mov     edx, [rsp+8B0h+var_86C]
0x180031823  mov     r9, rdi
0x180031826  mov     rax, [rsp+8B0h+var_858]
0x18003182b  mov     r8d, r12d
0x18003182e  mov     rcx, rbx
0x180031831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031836  test    eax, eax
0x180031838  jnz     short loc_180031843
0x18003183a  lea     rdx, aGetfileversion; "GetFileVersionInfo failure for %S"
0x180031841  jmp     short loc_1800317CC
0x180031843  mov     r13d, 800h
0x180031849  lea     r8, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x180031850  mov     edx, r13d; cbDest
0x180031853  lea     rcx, [rsp+8B0h+pszDest]; pszDest
0x180031858  call    StringCbCopyW
0x18003185d  mov     r12, [rsp+8B0h+var_850]
0x180031862  lea     r9, [rsp+8B0h+var_880]
0x180031867  mov     rax, r12
0x18003186a  lea     r8, [rsp+8B0h+lpString]
0x18003186f  lea     rdx, [rsp+8B0h+pszDest]
0x180031874  mov     rcx, rdi
0x180031877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003187c  test    eax, eax
0x18003187e  jz      short loc_1800318EC
0x180031880  cmp     [rsp+8B0h+var_880], 0
0x180031885  jz      short loc_1800318EC
0x180031887  mov     rax, [rsp+8B0h+lpString]
0x18003188c  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\FileDescrip"...
0x180031893  mov     edx, r13d; cbDest
0x180031896  movzx   ecx, word ptr [rax+2]
0x18003189a  movzx   r9d, word ptr [rax]
0x18003189e  mov     [rsp+8B0h+var_890], ecx
0x1800318a2  lea     rcx, [rsp+8B0h+pszDest]; pszDest
0x1800318a7  call    StringCbPrintfW
0x1800318ac  lea     r9, [rsp+8B0h+var_880]
0x1800318b1  mov     rcx, rdi
0x1800318b4  lea     r8, [rsp+8B0h+lpString]
0x1800318b9  mov     rax, r12
0x1800318bc  lea     rdx, [rsp+8B0h+pszDest]
0x1800318c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318c6  test    eax, eax
0x1800318c8  jz      short loc_1800318D1
0x1800318ca  cmp     [rsp+8B0h+var_880], 0
0x1800318cf  jnz     short loc_18003190E
0x1800318d1  mov     r9, rbx
0x1800318d4  lea     r8, [rsp+8B0h+pszDest]
0x1800318d9  lea     rdx, aErrorVerqueryv; "ERROR:  VerQueryValue failure for %S on"...
0x1800318e0  mov     ecx, 10002h
0x1800318e5  call    TRACELogPrint
0x1800318ea  jmp     short loc_180031916
0x1800318ec  mov     r9, rbx
0x1800318ef  lea     r8, [rsp+8B0h+pszDest]
0x1800318f4  lea     rdx, aErrorVerqueryv; "ERROR:  VerQueryValue failure for %S on"...
0x1800318fb  mov     ecx, 10002h
0x180031900  call    TRACELogPrint
0x180031905  mov     [rsp+8B0h+lpString], 0
0x18003190e  cmp     [rsp+8B0h+lpString], 0
0x180031914  jnz     short loc_18003191B
0x180031916  mov     [rsp+8B0h+lpString], rbx
0x18003191b  mov     rcx, [rsp+8B0h+lpString]; lpString
0x180031920  call    cs:__imp_lstrlenW
0x180031926  mov     ecx, [rsp+8B0h+var_868]
0x18003192a  lea     r13d, ds:2[rax*2]
0x180031932  lea     eax, [rsi+r13]
0x180031936  mov     [rsp+8B0h+var_864], eax
0x18003193a  cmp     eax, ecx
0x18003193c  jbe     short loc_180031982
0x18003193e  add     ecx, 200h
0x180031944  mov     edx, 8; dwFlags
0x180031949  mov     [rsp+8B0h+var_868], ecx
0x18003194d  mov     r8d, ecx; dwBytes
0x180031950  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180031957  call    cs:__imp_HeapAlloc
0x18003195d  mov     r12, rax
0x180031960  test    rax, rax
0x180031963  jz      short loc_1800319BB
0x180031965  test    esi, esi
0x180031967  jz      short loc_18003197F
0x180031969  mov     r8d, esi; Size
0x18003196c  mov     rdx, r14; Src
0x18003196f  mov     rcx, rax; void *
0x180031972  call    memcpy_0
0x180031977  mov     rcx, r14; lpMem
0x18003197a  call    ServerFree
0x18003197f  mov     r14, r12
0x180031982  mov     rdx, [rsp+8B0h+lpString]; Src
0x180031987  mov     ecx, esi
0x180031989  add     rcx, r14; void *
0x18003198c  mov     r8d, r13d; Size
0x18003198f  call    memcpy_0
0x180031994  mov     esi, [rsp+8B0h+var_864]
0x180031998  mov     rcx, rbx; lpString
0x18003199b  call    cs:__imp_lstrlenW
0x1800319a1  mov     r12d, [rsp+8B0h+var_870]
0x1800319a6  mov     r13, [rsp+8B0h+var_848]
0x1800319ab  movsxd  rcx, eax
0x1800319ae  lea     rbx, [rbx+rcx*2]
0x1800319b2  add     rbx, 2
0x1800319b6  jmp     loc_18003179E
0x1800319bb  test    r14, r14
0x1800319be  jz      short loc_1800319C8
0x1800319c0  mov     rcx, r14; lpMem
0x1800319c3  call    ServerFree
0x1800319c8  xor     esi, esi
0x1800319ca  mov     r12, [rsp+8B0h+var_860]
0x1800319cf  mov     rcx, r15; hLibModule
0x1800319d2  call    cs:__imp_FreeLibrary
0x1800319d8  test    rdi, rdi
0x1800319db  jz      short loc_1800319E5
0x1800319dd  mov     rcx, rdi; lpMem
0x1800319e0  call    ServerFree
0x1800319e5  test    esi, esi
0x1800319e7  jz      short loc_1800319ED
0x1800319e9  mov     [r12], r14
0x1800319ed  mov     eax, esi
0x1800319ef  jmp     loc_1800316D5
```
