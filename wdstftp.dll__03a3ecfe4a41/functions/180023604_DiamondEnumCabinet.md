# DiamondEnumCabinet

- ea: `0x180023604`
- end: `0x180023939`
- name: `DiamondEnumCabinet`
- size: `821`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180018dfc`

## callees

- `0x180010508`
- `0x180022f44`
- `0x180023604`
- `0x1800403f4`
- `0x1800607b0`
- `0x180060e5a`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800236c1`
- `msvcrt!wcsrchr` at `0x1800236c1`
- `KERNEL32!HeapFree` at `0x18002386c`
- `KERNEL32!HeapFree` at `0x1800238a1`
- `KERNEL32!HeapFree` at `0x1800238c6`
- `KERNEL32!HeapFree` at `0x1800238eb`
- `KERNEL32!HeapFree` at `0x18002386c`
- `KERNEL32!HeapFree` at `0x1800238a1`
- `KERNEL32!HeapFree` at `0x1800238c6`
- `KERNEL32!HeapFree` at `0x1800238eb`
- `KERNEL32!HeapAlloc` at `0x180023667`
- `KERNEL32!HeapAlloc` at `0x180023667`
- `KERNEL32!GetLastError` at `0x180023804`
- `KERNEL32!GetLastError` at `0x180023841`
- `KERNEL32!GetLastError` at `0x180023804`
- `KERNEL32!GetLastError` at `0x180023841`
- `KERNEL32!SetLastError` at `0x180023835`
- `KERNEL32!SetLastError` at `0x1800238f9`
- `KERNEL32!SetLastError` at `0x180023835`
- `KERNEL32!SetLastError` at `0x1800238f9`
- `KERNEL32!GetProcessHeap` at `0x18002364d`
- `KERNEL32!GetProcessHeap` at `0x180023856`
- `KERNEL32!GetProcessHeap` at `0x18002388d`
- `KERNEL32!GetProcessHeap` at `0x1800238b2`
- `KERNEL32!GetProcessHeap` at `0x1800238d7`
- `KERNEL32!GetProcessHeap` at `0x18002364d`
- `KERNEL32!GetProcessHeap` at `0x180023856`
- `KERNEL32!GetProcessHeap` at `0x18002388d`
- `KERNEL32!GetProcessHeap` at `0x1800238b2`
- `KERNEL32!GetProcessHeap` at `0x1800238d7`
- `Cabinet!__imp_FDICreate` at `0x18002375b`
- `Cabinet!__imp_FDICreate` at `0x18002375b`
- `Cabinet!__imp_FDICopy` at `0x1800237f4`
- `Cabinet!__imp_FDICopy` at `0x1800237f4`
- `Cabinet!__imp_FDIDestroy` at `0x180023822`
- `Cabinet!__imp_FDIDestroy` at `0x180023822`

## pseudocode

```c
__int64 __fastcall DiamondEnumCabinet(STRSAFE_PCNZWCH pszSrc, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  CHAR *v6; // r15
  CHAR *v7; // r14
  HANDLE ProcessHeap; // rax
  DWORD LastError; // ebx
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  wchar_t *v12; // rax
  HFDI v13; // rbp
  HANDLE v14; // rax
  BOOL v15; // eax
  void *v16; // rcx
  HANDLE v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  _BYTE pvUser[8]; // [rsp+50h] [rbp-68h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-60h]
  __int64 (__fastcall *v23)(); // [rsp+60h] [rbp-58h]
  __int64 v24; // [rsp+68h] [rbp-50h]
  DWORD v25; // [rsp+70h] [rbp-48h]
  ERF perf; // [rsp+78h] [rbp-40h] BYREF

  v3 = 0;
  v6 = 0;
  v7 = 0;
  memset_0(pvUser, 0, 0x28u);
  ProcessHeap = GetProcessHeap();
  LastError = 8;
  v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x820u);
  v11 = v10;
  if ( !v10 )
  {
    LastError = 14;
    goto LABEL_26;
  }
  if ( !(unsigned int)WdsGetFileName(pszSrc, v10, 1040) )
    goto LABEL_25;
  v6 = (CHAR *)WimStrAnsi(v11);
  if ( !v6 )
    goto LABEL_25;
  if ( !pszSrc || (v12 = wcsrchr(pszSrc, 0x5Cu)) == 0 )
  {
    SetLastError(0x57u);
LABEL_25:
    LastError = GetLastError();
    goto LABEL_26;
  }
  if ( StringCchCopyNW(v11, 0x410u, pszSrc, v12 - pszSrc + 1) < 0 )
    goto LABEL_25;
  v7 = (CHAR *)WimStrAnsi(v11);
  if ( !v7 )
    goto LABEL_25;
  v13 = FDICreate(
          DiamondAlloc,
          DiamondFree,
          DiamondOpenFile,
          DiamondReadFile,
          DiamondWriteFile,
          DiamondCloseFile,
          DiamondSeekFile,
          -1,
          &perf);
  if ( v13 )
  {
    v24 = a3;
    v23 = DiamondCallback;
    if ( FDICopy(v13, v6, v7, 0, DiamondNotifyFunction, 0, pvUser) )
    {
      LastError = 0;
      if ( v25 )
        LastError = v25;
    }
    else
    {
      LastError = GetLastError();
    }
    FDIDestroy(v13);
  }
  else
  {
    if ( perf.erfOper )
    {
      switch ( perf.erfOper )
      {
        case 1:
          LastError = 2;
          goto LABEL_26;
        case 4:
          LastError = 1392;
          goto LABEL_26;
        case 5:
          goto LABEL_26;
        case 0xB:
          LastError = 1223;
          goto LABEL_26;
      }
    }
    LastError = 13;
  }
LABEL_26:
  if ( lpMem )
  {
    v14 = GetProcessHeap();
    v15 = HeapFree(v14, 0, lpMem);
    v16 = lpMem;
    if ( v15 )
      v16 = 0;
    lpMem = v16;
  }
  if ( v7 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v7);
  }
  if ( v6 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v6);
  }
  if ( v11 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v11);
  }
  SetLastError(LastError);
  LOBYTE(v3) = LastError == 0;
  return v3;
}

```

## disassembly

```asm
0x180023604  mov     [rsp+arg_8], rbx
0x180023609  mov     [rsp+arg_18], rbp
0x18002360e  push    rsi
0x18002360f  push    rdi
0x180023610  push    r12
0x180023612  push    r14
0x180023614  push    r15
0x180023616  sub     rsp, 90h
0x18002361d  mov     rax, cs:__security_cookie
0x180023624  xor     rax, rsp
0x180023627  mov     [rsp+0B8h+var_30], rax
0x18002362f  xor     edi, edi
0x180023631  mov     r12, r8
0x180023634  mov     rbp, rcx
0x180023637  xor     edx, edx; Val
0x180023639  lea     rcx, [rsp+0B8h+pvUser]; void *
0x18002363e  mov     r15d, edi
0x180023641  mov     r14d, edi
0x180023644  lea     r8d, [rdi+28h]; Size
0x180023648  call    memset_0
0x18002364d  call    cs:__imp_GetProcessHeap
0x180023654  nop     dword ptr [rax+rax+00h]
0x180023659  lea     ebx, [rdi+8]
0x18002365c  mov     r8d, 820h; dwBytes
0x180023662  mov     rcx, rax; hHeap
0x180023665  mov     edx, ebx; dwFlags
0x180023667  call    cs:__imp_HeapAlloc
0x18002366e  nop     dword ptr [rax+rax+00h]
0x180023673  mov     rsi, rax
0x180023676  test    rax, rax
0x180023679  jnz     short loc_180023683
0x18002367b  lea     ebx, [rdi+0Eh]
0x18002367e  jmp     loc_18002384F
0x180023683  mov     r8d, 410h
0x180023689  mov     rdx, rsi
0x18002368c  mov     rcx, rbp
0x18002368f  call    WdsGetFileName
0x180023694  test    eax, eax
0x180023696  jz      loc_180023841
0x18002369c  mov     rcx, rsi; lpWideCharStr
0x18002369f  call    WimStrAnsi
0x1800236a4  mov     r15, rax
0x1800236a7  test    rax, rax
0x1800236aa  jz      loc_180023841
0x1800236b0  test    rbp, rbp
0x1800236b3  jz      loc_180023830
0x1800236b9  mov     edx, 5Ch ; '\'; Ch
0x1800236be  mov     rcx, rbp; Str
0x1800236c1  call    cs:__imp_wcsrchr
0x1800236c8  nop     dword ptr [rax+rax+00h]
0x1800236cd  test    rax, rax
0x1800236d0  jz      loc_180023830
0x1800236d6  sub     rax, rbp
0x1800236d9  mov     r8, rbp; pszSrc
0x1800236dc  sar     rax, 1
0x1800236df  mov     edx, 410h; cchDest
0x1800236e4  mov     rcx, rsi; pszDest
0x1800236e7  lea     r9, [rax+1]; cchToCopy
0x1800236eb  call    StringCchCopyNW
0x1800236f0  test    eax, eax
0x1800236f2  js      loc_180023841
0x1800236f8  mov     rcx, rsi; lpWideCharStr
0x1800236fb  call    WimStrAnsi
0x180023700  mov     r14, rax
0x180023703  test    rax, rax
0x180023706  jz      loc_180023841
0x18002370c  lea     rax, [rsp+0B8h+var_40]
0x180023711  mov     [rsp+0B8h+perf], rax; perf
0x180023716  lea     r9, DiamondReadFile; pfnread
0x18002371d  or      [rsp+0B8h+var_80], 0FFFFFFFFh
0x180023722  lea     rax, DiamondSeekFile
0x180023729  mov     [rsp+0B8h+pfnseek], rax; pfnseek
0x18002372e  lea     r8, DiamondOpenFile; pfnopen
0x180023735  lea     rax, DiamondCloseFile
0x18002373c  mov     [rsp+0B8h+pfnclose], rax; pfnclose
0x180023741  lea     rdx, DiamondFree; pfnfree
0x180023748  lea     rax, DiamondWriteFile
0x18002374f  lea     rcx, DiamondAlloc; pfnalloc
0x180023756  mov     [rsp+0B8h+pfnwrite], rax; pfnwrite
0x18002375b  call    cs:__imp_FDICreate
0x180023762  nop     dword ptr [rax+rax+00h]
0x180023767  mov     rbp, rax
0x18002376a  test    rax, rax
0x18002376d  jnz     short loc_1800237BC
0x18002376f  mov     ecx, [rsp+0B8h+var_40.erfOper]
0x180023773  test    ecx, ecx
0x180023775  jz      short loc_1800237B2
0x180023777  sub     ecx, 1
0x18002377a  jz      short loc_1800237A8
0x18002377c  sub     ecx, 3
0x18002377f  jz      short loc_18002379E
0x180023781  sub     ecx, 1
0x180023784  jz      loc_18002384F
0x18002378a  sub     ecx, 3
0x18002378d  jz      short loc_1800237B2
0x18002378f  cmp     ecx, 3
0x180023792  jnz     short loc_1800237B2
0x180023794  mov     ebx, 4C7h
0x180023799  jmp     loc_18002384F
0x18002379e  mov     ebx, 570h
0x1800237a3  jmp     loc_18002384F
0x1800237a8  mov     ebx, 2
0x1800237ad  jmp     loc_18002384F
0x1800237b2  mov     ebx, 0Dh
0x1800237b7  jmp     loc_18002384F
0x1800237bc  lea     rax, DiamondCallback
0x1800237c3  mov     [rsp+0B8h+var_50], r12
0x1800237c8  mov     [rsp+0B8h+var_58], rax
0x1800237cd  xor     r9d, r9d; flags
0x1800237d0  lea     rax, [rsp+0B8h+pvUser]
0x1800237d5  mov     r8, r14; pszCabPath
0x1800237d8  mov     [rsp+0B8h+pfnseek], rax; pvUser
0x1800237dd  mov     rdx, r15; pszCabinet
0x1800237e0  lea     rax, DiamondNotifyFunction
0x1800237e7  mov     [rsp+0B8h+pfnclose], rdi; pfnfdid
0x1800237ec  mov     rcx, rbp; hfdi
0x1800237ef  mov     [rsp+0B8h+pfnwrite], rax; pfnfdin
0x1800237f4  call    cs:__imp_FDICopy
0x1800237fb  nop     dword ptr [rax+rax+00h]
0x180023800  test    eax, eax
0x180023802  jnz     short loc_180023814
0x180023804  call    cs:__imp_GetLastError
0x18002380b  nop     dword ptr [rax+rax+00h]
0x180023810  mov     ebx, eax
0x180023812  jmp     short loc_18002381F
0x180023814  cmp     [rsp+0B8h+var_48], edi
0x180023818  mov     ebx, edi
0x18002381a  cmovnz  ebx, [rsp+0B8h+var_48]
0x18002381f  mov     rcx, rbp; hfdi
0x180023822  call    cs:__imp_FDIDestroy
0x180023829  nop     dword ptr [rax+rax+00h]
0x18002382e  jmp     short loc_18002384F
0x180023830  mov     ecx, 57h ; 'W'; dwErrCode
0x180023835  call    cs:__imp_SetLastError
0x18002383c  nop     dword ptr [rax+rax+00h]
0x180023841  call    cs:__imp_GetLastError
0x180023848  nop     dword ptr [rax+rax+00h]
0x18002384d  mov     ebx, eax
0x18002384f  cmp     [rsp+0B8h+lpMem], rdi
0x180023854  jz      short loc_180023888
0x180023856  call    cs:__imp_GetProcessHeap
0x18002385d  nop     dword ptr [rax+rax+00h]
0x180023862  mov     r8, [rsp+0B8h+lpMem]; lpMem
0x180023867  xor     edx, edx; dwFlags
0x180023869  mov     rcx, rax; hHeap
0x18002386c  call    cs:__imp_HeapFree
0x180023873  nop     dword ptr [rax+rax+00h]
0x180023878  mov     rcx, [rsp+0B8h+lpMem]
0x18002387d  test    eax, eax
0x18002387f  cmovnz  rcx, rdi
0x180023883  mov     [rsp+0B8h+lpMem], rcx
0x180023888  test    r14, r14
0x18002388b  jz      short loc_1800238AD
0x18002388d  call    cs:__imp_GetProcessHeap
0x180023894  nop     dword ptr [rax+rax+00h]
0x180023899  mov     r8, r14; lpMem
0x18002389c  xor     edx, edx; dwFlags
0x18002389e  mov     rcx, rax; hHeap
0x1800238a1  call    cs:__imp_HeapFree
0x1800238a8  nop     dword ptr [rax+rax+00h]
0x1800238ad  test    r15, r15
0x1800238b0  jz      short loc_1800238D2
0x1800238b2  call    cs:__imp_GetProcessHeap
0x1800238b9  nop     dword ptr [rax+rax+00h]
0x1800238be  mov     r8, r15; lpMem
0x1800238c1  xor     edx, edx; dwFlags
0x1800238c3  mov     rcx, rax; hHeap
0x1800238c6  call    cs:__imp_HeapFree
0x1800238cd  nop     dword ptr [rax+rax+00h]
0x1800238d2  test    rsi, rsi
0x1800238d5  jz      short loc_1800238F7
0x1800238d7  call    cs:__imp_GetProcessHeap
0x1800238de  nop     dword ptr [rax+rax+00h]
0x1800238e3  mov     r8, rsi; lpMem
0x1800238e6  xor     edx, edx; dwFlags
0x1800238e8  mov     rcx, rax; hHeap
0x1800238eb  call    cs:__imp_HeapFree
0x1800238f2  nop     dword ptr [rax+rax+00h]
0x1800238f7  mov     ecx, ebx; dwErrCode
0x1800238f9  call    cs:__imp_SetLastError
0x180023900  nop     dword ptr [rax+rax+00h]
0x180023905  test    ebx, ebx
0x180023907  setz    dil
0x18002390b  mov     eax, edi
0x18002390d  mov     rcx, [rsp+0B8h+var_30]
0x180023915  xor     rcx, rsp; StackCookie
0x180023918  call    __security_check_cookie
0x18002391d  lea     r11, [rsp+0B8h+var_28]
0x180023925  mov     rbx, [r11+38h]
0x180023929  mov     rbp, [r11+48h]
0x18002392d  mov     rsp, r11
0x180023930  pop     r15
0x180023932  pop     r14
0x180023934  pop     r12
0x180023936  pop     rdi
0x180023937  pop     rsi
0x180023938  retn
```
