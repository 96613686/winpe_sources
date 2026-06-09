# WcpLoad(void)

- ea: `0x1800067ac`
- end: `0x180006aba`
- name: `?WcpLoad@@YAJXZ`
- size: `782`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180006c30`

## callees

- `0x180001de0`
- `0x1800067ac`
- `0x180010448`
- `0x18001b77a`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000690e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000690e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000686b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000686b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006936`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006956`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006976`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006996`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800069ba`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800069de`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006936`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006956`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006976`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006996`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800069ba`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800069de`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180006a66`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180006a66`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800068fc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800068fc`

## string_xrefs

- `0x1800068d4`: `wcp.dll`
- `0x18000698f`: `OpenExistingOfflineStore`

## pseudocode

```c
__int64 WcpLoad(void)
{
  LPCWSTR v0; // rdi
  HMODULE v1; // rbx
  signed int v2; // ebx
  signed int v3; // eax
  unsigned __int64 v4; // rax
  WCHAR *v5; // rdx
  WCHAR *v6; // rcx
  __int64 v7; // r8
  int v8; // eax
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  LPCWSTR lpLibFileName; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-D0h] BYREF

  v0 = 0;
  lpLibFileName = 0;
  if ( vhWcpModule
    || vpfnGetIdentityAuthority
    || vpfnGetSystemStore
    || vpfnOpenExistingOfflineStore
    || vpfnSetIsolationIMalloc
    || vpfnWcpInitialize
    || vpfnWcpShutdown )
  {
    v2 = -2147023649;
LABEL_35:
    if ( v0 )
      operator delete((void *)(v0 - 4));
    goto LABEL_37;
  }
  v1 = g_hInst;
  if ( !g_hInst )
    return (unsigned int)-2147023782;
  memset_0(Filename, 0, 0x208u);
  if ( GetModuleFileNameW(v1, Filename, 0x104u) )
  {
    v4 = Filename[0];
    v5 = Filename;
    if ( Filename[0] )
    {
      v6 = Filename;
      do
      {
        LOWORD(v4) = v4 - 47;
        if ( (unsigned __int16)v4 <= 0x2Du )
        {
          v7 = 0x200000000801LL;
          if ( _bittest64(&v7, v4) )
            v5 = v6 + 1;
        }
        v4 = *++v6;
      }
      while ( (_WORD)v4 );
    }
    *v5 = 0;
    v8 = SczAllocConcat2Sz(&lpLibFileName, Filename, L"wcp.dll");
    v0 = lpLibFileName;
    v2 = v8;
    if ( v8 >= 0 )
    {
      LibraryW = LoadLibraryW(lpLibFileName);
      vhWcpModule = LibraryW;
      if ( LibraryW
        && (vpfnSetIsolationIMalloc = (int (*)(struct IMalloc *))GetProcAddress(LibraryW, "SetIsolationIMalloc")) != 0
        && (vpfnGetIdentityAuthority = (int (*)(struct IIdentityAuthority **))GetProcAddress(
                                                                                vhWcpModule,
                                                                                "GetIdentityAuthority")) != 0
        && (vpfnGetSystemStore = (int (*)(unsigned int, const struct _GUID *, struct IUnknown **))GetProcAddress(
                                                                                                    vhWcpModule,
                                                                                                    "GetSystemStore")) != 0
        && (vpfnOpenExistingOfflineStore = (int (*)(unsigned int, const struct _OFFLINE_STORE_CREATION_PARAMETERS *, const struct _GUID *, struct IUnknown **, unsigned int *))GetProcAddress(vhWcpModule, "OpenExistingOfflineStore")) != 0
        && (vpfnWcpInitialize = (int (*)(unsigned __int64 *))GetProcAddress(vhWcpModule, "WcpInitialize")) != 0
        && (vpfnWcpShutdown = (void (*)(unsigned __int64))GetProcAddress(vhWcpModule, "WcpShutdown")) != 0 )
      {
        if ( vpfnWcpInitialize )
        {
          if ( !gulpWcpCookie )
          {
            lpLibFileName = 0;
            v2 = vpfnWcpInitialize((unsigned __int64 *)&lpLibFileName);
            if ( v2 >= 0 )
            {
              if ( _InterlockedCompareExchange64(
                     (volatile signed __int64 *)&gulpWcpCookie,
                     (signed __int64)lpLibFileName,
                     0) )
              {
                ((void (__fastcall *)(LPCWSTR))vpfnWcpShutdown)(lpLibFileName);
              }
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    goto LABEL_35;
  }
  v3 = GetLastError();
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
LABEL_37:
  if ( v2 < 0 && vhWcpModule )
  {
    FreeLibrary(vhWcpModule);
    vhWcpModule = 0;
    vpfnGetIdentityAuthority = 0;
    vpfnGetSystemStore = 0;
    vpfnOpenExistingOfflineStore = 0;
    vpfnSetIsolationIMalloc = 0;
    vpfnWcpInitialize = 0;
    vpfnWcpShutdown = 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800067ac  push    rbp
0x1800067ae  push    rbx
0x1800067af  push    rsi
0x1800067b0  push    rdi
0x1800067b1  lea     rbp, [rsp-158h]
0x1800067b9  sub     rsp, 258h
0x1800067c0  mov     rax, cs:__security_cookie
0x1800067c7  xor     rax, rsp
0x1800067ca  mov     [rbp+170h+var_30], rax
0x1800067d1  xor     esi, esi
0x1800067d3  cmp     cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * vhWcpModule
0x1800067da  mov     edi, esi
0x1800067dc  mov     [rsp+270h+lpLibFileName], rsi
0x1800067e1  jnz     loc_180006A43
0x1800067e7  cmp     cs:?vpfnGetIdentityAuthority@@3P6AJPEAPEAUIIdentityAuthority@@@ZEA, rsi; long (*vpfnGetIdentityAuthority)(IIdentityAuthority * *)
0x1800067ee  jnz     loc_180006A43
0x1800067f4  cmp     cs:?vpfnGetSystemStore@@3P6AJKAEBU_GUID@@PEAPEAUIUnknown@@@ZEA, rsi; long (*vpfnGetSystemStore)(ulong,_GUID const &,IUnknown * *)
0x1800067fb  jnz     loc_180006A43
0x180006801  cmp     cs:?vpfnOpenExistingOfflineStore@@3P6AJKPEBU_OFFLINE_STORE_CREATION_PARAMETERS@@AEBU_GUID@@PEAPEAUIUnknown@@PEAK@ZEA, rsi; long (*vpfnOpenExistingOfflineStore)(ulong,_OFFLINE_STORE_CREATION_PARAMETERS const *,_GUID const &,IUnknown * *,ulong *)
0x180006808  jnz     loc_180006A43
0x18000680e  cmp     cs:?vpfnSetIsolationIMalloc@@3P6AJPEAUIMalloc@@@ZEA, rsi; long (*vpfnSetIsolationIMalloc)(IMalloc *)
0x180006815  jnz     loc_180006A43
0x18000681b  cmp     cs:?vpfnWcpInitialize@@3P6AJPEA_K@ZEA, rsi; long (*vpfnWcpInitialize)(unsigned __int64 *)
0x180006822  jnz     loc_180006A43
0x180006828  cmp     cs:?vpfnWcpShutdown@@3P6AX_K@ZEA, rsi; void (*vpfnWcpShutdown)(unsigned __int64)
0x18000682f  jnz     loc_180006A43
0x180006835  mov     rbx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18000683c  test    rbx, rbx
0x18000683f  jnz     short loc_18000684B
0x180006841  mov     ebx, 8007045Ah
0x180006846  jmp     loc_180006A9D
0x18000684b  xor     edx, edx; Val
0x18000684d  lea     rcx, [rsp+270h+Filename]; void *
0x180006852  mov     r8d, 208h; Size
0x180006858  call    memset_0
0x18000685d  mov     r8d, 104h; nSize
0x180006863  lea     rdx, [rsp+270h+Filename]; lpFilename
0x180006868  mov     rcx, rbx; hModule
0x18000686b  call    cs:__imp_GetModuleFileNameW
0x180006871  test    eax, eax
0x180006873  jnz     short loc_180006893
0x180006875  call    cs:__imp_GetLastError
0x18000687b  mov     ebx, eax
0x18000687d  test    eax, eax
0x18000687f  jle     loc_180006A56
0x180006885  movzx   ebx, ax
0x180006888  or      ebx, 80070000h
0x18000688e  jmp     loc_180006A56
0x180006893  movzx   eax, [rsp+270h+Filename]
0x180006898  lea     rdx, [rsp+270h+Filename]
0x18000689d  test    ax, ax
0x1800068a0  jz      short loc_1800068D1
0x1800068a2  lea     rcx, [rsp+270h+Filename]
0x1800068a7  sub     ax, 2Fh ; '/'
0x1800068ab  cmp     ax, 2Dh ; '-'
0x1800068af  ja      short loc_1800068C5
0x1800068b1  mov     r8, 200000000801h
0x1800068bb  bt      r8, rax
0x1800068bf  jnb     short loc_1800068C5
0x1800068c1  lea     rdx, [rcx+2]
0x1800068c5  add     rcx, 2
0x1800068c9  movzx   eax, word ptr [rcx]
0x1800068cc  test    ax, ax
0x1800068cf  jnz     short loc_1800068A7
0x1800068d1  mov     [rdx], si
0x1800068d4  lea     r8, aWcpDll; "wcp.dll"
0x1800068db  lea     rdx, [rsp+270h+Filename]
0x1800068e0  lea     rcx, [rsp+270h+lpLibFileName]
0x1800068e5  call    SczAllocConcat2Sz
0x1800068ea  mov     rdi, [rsp+270h+lpLibFileName]
0x1800068ef  mov     ebx, eax
0x1800068f1  test    eax, eax
0x1800068f3  js      loc_180006A48
0x1800068f9  mov     rcx, rdi; lpLibFileName
0x1800068fc  call    cs:__imp_LoadLibraryW
0x180006902  mov     cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhWcpModule
0x180006909  test    rax, rax
0x18000690c  jnz     short loc_18000692C
0x18000690e  call    cs:__imp_GetLastError
0x180006914  mov     ebx, eax
0x180006916  test    eax, eax
0x180006918  jle     loc_180006A48
0x18000691e  movzx   ebx, ax
0x180006921  or      ebx, 80070000h
0x180006927  jmp     loc_180006A48
0x18000692c  lea     rdx, aSetisolationim; "SetIsolationIMalloc"
0x180006933  mov     rcx, rax; hModule
0x180006936  call    cs:__imp_GetProcAddress
0x18000693c  mov     cs:?vpfnSetIsolationIMalloc@@3P6AJPEAUIMalloc@@@ZEA, rax; long (*vpfnSetIsolationIMalloc)(IMalloc *)
0x180006943  test    rax, rax
0x180006946  jz      short loc_18000690E
0x180006948  mov     rcx, cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000694f  lea     rdx, aGetidentityaut; "GetIdentityAuthority"
0x180006956  call    cs:__imp_GetProcAddress
0x18000695c  mov     cs:?vpfnGetIdentityAuthority@@3P6AJPEAPEAUIIdentityAuthority@@@ZEA, rax; long (*vpfnGetIdentityAuthority)(IIdentityAuthority * *)
0x180006963  test    rax, rax
0x180006966  jz      short loc_18000690E
0x180006968  mov     rcx, cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000696f  lea     rdx, aGetsystemstore; "GetSystemStore"
0x180006976  call    cs:__imp_GetProcAddress
0x18000697c  mov     cs:?vpfnGetSystemStore@@3P6AJKAEBU_GUID@@PEAPEAUIUnknown@@@ZEA, rax; long (*vpfnGetSystemStore)(ulong,_GUID const &,IUnknown * *)
0x180006983  test    rax, rax
0x180006986  jz      short loc_18000690E
0x180006988  mov     rcx, cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000698f  lea     rdx, aOpenexistingof; "OpenExistingOfflineStore"
0x180006996  call    cs:__imp_GetProcAddress
0x18000699c  mov     cs:?vpfnOpenExistingOfflineStore@@3P6AJKPEBU_OFFLINE_STORE_CREATION_PARAMETERS@@AEBU_GUID@@PEAPEAUIUnknown@@PEAK@ZEA, rax; long (*vpfnOpenExistingOfflineStore)(ulong,_OFFLINE_STORE_CREATION_PARAMETERS const *,_GUID const &,IUnknown * *,ulong *)
0x1800069a3  test    rax, rax
0x1800069a6  jz      loc_18000690E
0x1800069ac  mov     rcx, cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA; hModule
0x1800069b3  lea     rdx, aWcpinitialize; "WcpInitialize"
0x1800069ba  call    cs:__imp_GetProcAddress
0x1800069c0  mov     cs:?vpfnWcpInitialize@@3P6AJPEA_K@ZEA, rax; long (*vpfnWcpInitialize)(unsigned __int64 *)
0x1800069c7  test    rax, rax
0x1800069ca  jz      loc_18000690E
0x1800069d0  mov     rcx, cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA; hModule
0x1800069d7  lea     rdx, aWcpshutdown; "WcpShutdown"
0x1800069de  call    cs:__imp_GetProcAddress
0x1800069e4  mov     cs:?vpfnWcpShutdown@@3P6AX_K@ZEA, rax; void (*vpfnWcpShutdown)(unsigned __int64)
0x1800069eb  test    rax, rax
0x1800069ee  jz      loc_18000690E
0x1800069f4  mov     rax, cs:?vpfnWcpInitialize@@3P6AJPEA_K@ZEA; long (*vpfnWcpInitialize)(unsigned __int64 *)
0x1800069fb  test    rax, rax
0x1800069fe  jz      short loc_180006A48
0x180006a00  cmp     cs:?gulpWcpCookie@@3_KA, rsi; unsigned __int64 gulpWcpCookie
0x180006a07  jnz     short loc_180006A48
0x180006a09  lea     rcx, [rsp+270h+lpLibFileName]
0x180006a0e  mov     [rsp+270h+lpLibFileName], rsi
0x180006a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a18  mov     ebx, eax
0x180006a1a  test    eax, eax
0x180006a1c  js      short loc_180006A48
0x180006a1e  mov     rcx, [rsp+270h+lpLibFileName]
0x180006a23  xor     eax, eax
0x180006a25  lock cmpxchg cs:?gulpWcpCookie@@3_KA, rcx; unsigned __int64 gulpWcpCookie
0x180006a2e  jz      short loc_180006A48
0x180006a30  mov     rcx, [rsp+270h+lpLibFileName]
0x180006a35  mov     rax, cs:?vpfnWcpShutdown@@3P6AX_K@ZEA; void (*vpfnWcpShutdown)(unsigned __int64)
0x180006a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a41  jmp     short loc_180006A48
0x180006a43  mov     ebx, 800704DFh
0x180006a48  test    rdi, rdi
0x180006a4b  jz      short loc_180006A56
0x180006a4d  lea     rcx, [rdi-8]; Block
0x180006a51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006a56  test    ebx, ebx
0x180006a58  jns     short loc_180006A9D
0x180006a5a  mov     rcx, cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x180006a61  test    rcx, rcx
0x180006a64  jz      short loc_180006A9D
0x180006a66  call    cs:__imp_FreeLibrary
0x180006a6c  mov     cs:?vhWcpModule@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * vhWcpModule
0x180006a73  mov     cs:?vpfnGetIdentityAuthority@@3P6AJPEAPEAUIIdentityAuthority@@@ZEA, rsi; long (*vpfnGetIdentityAuthority)(IIdentityAuthority * *)
0x180006a7a  mov     cs:?vpfnGetSystemStore@@3P6AJKAEBU_GUID@@PEAPEAUIUnknown@@@ZEA, rsi; long (*vpfnGetSystemStore)(ulong,_GUID const &,IUnknown * *)
0x180006a81  mov     cs:?vpfnOpenExistingOfflineStore@@3P6AJKPEBU_OFFLINE_STORE_CREATION_PARAMETERS@@AEBU_GUID@@PEAPEAUIUnknown@@PEAK@ZEA, rsi; long (*vpfnOpenExistingOfflineStore)(ulong,_OFFLINE_STORE_CREATION_PARAMETERS const *,_GUID const &,IUnknown * *,ulong *)
0x180006a88  mov     cs:?vpfnSetIsolationIMalloc@@3P6AJPEAUIMalloc@@@ZEA, rsi; long (*vpfnSetIsolationIMalloc)(IMalloc *)
0x180006a8f  mov     cs:?vpfnWcpInitialize@@3P6AJPEA_K@ZEA, rsi; long (*vpfnWcpInitialize)(unsigned __int64 *)
0x180006a96  mov     cs:?vpfnWcpShutdown@@3P6AX_K@ZEA, rsi; void (*vpfnWcpShutdown)(unsigned __int64)
0x180006a9d  mov     eax, ebx
0x180006a9f  mov     rcx, [rbp+170h+var_30]
0x180006aa6  xor     rcx, rsp; StackCookie
0x180006aa9  call    __security_check_cookie
0x180006aae  add     rsp, 258h
0x180006ab5  pop     rdi
0x180006ab6  pop     rsi
0x180006ab7  pop     rbx
0x180006ab8  pop     rbp
0x180006ab9  retn
```
