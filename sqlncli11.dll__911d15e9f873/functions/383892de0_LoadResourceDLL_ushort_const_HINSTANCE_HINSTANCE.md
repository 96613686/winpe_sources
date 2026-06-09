# LoadResourceDLL(ushort const *,HINSTANCE__ *,HINSTANCE__ * *)

- ea: `0x383892de0`
- end: `0x38389312f`
- name: `?LoadResourceDLL@@YAJPEBGPEAUHINSTANCE__@@PEAPEAU1@@Z`
- size: `847`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HINSTANCE, HINSTANCE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x383893ff0`

## callees

- `0x38387da60`
- `0x383892de0`
- `0x383893160`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x38391afe0`
- `0x3839adac0`

## import_xrefs

- `MSVCR100!_wmakepath_s` at `0x383892fb1`
- `MSVCR100!_wmakepath_s` at `0x383893066`
- `MSVCR100!_wmakepath_s` at `0x3838f3783`
- `MSVCR100!_wmakepath_s` at `0x3838f37f0`
- `MSVCR100!_wmakepath_s` at `0x3838f3832`
- `MSVCR100!_wmakepath_s` at `0x383892fb1`
- `MSVCR100!_wmakepath_s` at `0x383893066`
- `MSVCR100!_wmakepath_s` at `0x3838f3783`
- `MSVCR100!_wmakepath_s` at `0x3838f37f0`
- `MSVCR100!_wmakepath_s` at `0x3838f3832`
- `MSVCR100!_wsplitpath_s` at `0x383892f0b`
- `MSVCR100!_wsplitpath_s` at `0x383892f39`
- `MSVCR100!_wsplitpath_s` at `0x383892f0b`
- `MSVCR100!_wsplitpath_s` at `0x383892f39`
- `KERNEL32!GetModuleFileNameW` at `0x383892ece`
- `KERNEL32!GetModuleFileNameW` at `0x383892ece`
- `KERNEL32!GetLastError` at `0x3838f36d3`
- `KERNEL32!GetLastError` at `0x3838f389c`
- `KERNEL32!GetLastError` at `0x3838f36d3`
- `KERNEL32!GetLastError` at `0x3838f389c`
- `KERNEL32!GetSystemDefaultLCID` at `0x3838f3740`
- `KERNEL32!GetSystemDefaultLCID` at `0x3838f3740`
- `KERNEL32!LoadLibraryExW` at `0x383892fe6`
- `KERNEL32!LoadLibraryExW` at `0x383893075`
- `KERNEL32!LoadLibraryExW` at `0x3838f3792`
- `KERNEL32!LoadLibraryExW` at `0x3838f37ff`
- `KERNEL32!LoadLibraryExW` at `0x3838f3842`
- `KERNEL32!LoadLibraryExW` at `0x3838f3869`
- `KERNEL32!LoadLibraryExW` at `0x383892fe6`
- `KERNEL32!LoadLibraryExW` at `0x383893075`
- `KERNEL32!LoadLibraryExW` at `0x3838f3792`
- `KERNEL32!LoadLibraryExW` at `0x3838f37ff`
- `KERNEL32!LoadLibraryExW` at `0x3838f3842`
- `KERNEL32!LoadLibraryExW` at `0x3838f3869`
- `KERNEL32!GetUserDefaultLCID` at `0x383892f66`
- `KERNEL32!GetUserDefaultLCID` at `0x383893023`
- `KERNEL32!GetUserDefaultLCID` at `0x383892f66`
- `KERNEL32!GetUserDefaultLCID` at `0x383893023`

## pseudocode

```c
__int64 __fastcall LoadResourceDLL(const unsigned __int16 *a1, HINSTANCE a2, HINSTANCE *a3)
{
  HMODULE v3; // r15
  wchar_t *v4; // rdi
  wchar_t *Filename; // rbp
  wchar_t *Ext; // r14
  unsigned __int16 *v7; // rbx
  WCHAR *v8; // rsi
  wchar_t *v9; // r13
  __int64 v10; // rbx
  LCID UserDefaultLCID; // eax
  unsigned __int64 v12; // rdx
  DWORD v13; // r8d
  unsigned __int16 *v14; // rax
  HMODULE Library; // rax
  __int64 v16; // rbx
  LCID v17; // eax
  unsigned int v18; // ebx
  __int64 v20; // rdx
  DWORD LastError; // eax
  __int64 v22; // rbx
  LCID SystemDefaultLCID; // eax
  __int64 v24; // rax
  unsigned __int16 *v25; // rbx
  __int64 v26; // [rsp+90h] [rbp+8h] BYREF
  unsigned __int16 *v27; // [rsp+98h] [rbp+10h]

  v26 = -1;
  v3 = g_hinstance;
  if ( (bidGblFlags & 4) != 0 && off_383B4AD38[0] )
    bidScopeEnterW(&v26, off_383B4AD38[0], L"SQLNCLIR11.RLL", g_hinstance);
  v4 = 0;
  Filename = 0;
  Ext = 0;
  v7 = 0;
  v8 = (WCHAR *)((__int64 (__fastcall *)(struct IMalloc *, __int64, HINSTANCE *))g_pMO->lpVtbl[1].Free)(g_pMO, 520, a3);
  if ( !v8 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v18 = bidTraceHR(off_383B434E8[0], 118793, 2147942414LL);
    else
      v18 = -2147024882;
    goto LABEL_37;
  }
  v9 = (wchar_t *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, 6);
  if ( !v9 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_47;
    v20 = 125961;
LABEL_46:
    v18 = bidTraceHR(off_383B434E8[0], v20, 2147942414LL);
    goto LABEL_29;
  }
  v4 = (wchar_t *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, 512);
  if ( !v4 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_47;
    v20 = 133129;
    goto LABEL_46;
  }
  Filename = (wchar_t *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, 512);
  if ( !Filename )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_47;
    v20 = 140297;
    goto LABEL_46;
  }
  Ext = (wchar_t *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, 512);
  if ( !Ext )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v20 = 147465;
      goto LABEL_46;
    }
LABEL_47:
    v18 = -2147024882;
    goto LABEL_29;
  }
  if ( v3 )
  {
    if ( !GetModuleFileNameW(v3, v8, 0x103u) )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B4A1C8[0] )
      {
        LastError = GetLastError();
        bidTraceW(off_383B434E8[0], 161792, off_383B4A1C8[0], LastError);
      }
      goto LABEL_57;
    }
    v8[259] = 0;
    _wsplitpath_s(v8, v9, 3u, v4, 0x100u, 0, 0, 0, 0);
    _wsplitpath_s(L"SQLNCLIR11.RLL", 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
    v10 = -1;
    do
      ++v10;
    while ( v4[v10] );
    v27 = &v4[v10];
    if ( g_fIsEmbeddedSNAC )
    {
      StringCchCopyW(&v4[v10], 256 - v10, L"Resources\\");
      v7 = v27;
    }
    else
    {
      UserDefaultLCID = GetUserDefaultLCID();
      if ( UserDefaultLCID == 3076 )
        UserDefaultLCID = 1028;
      v12 = 256 - v10;
      v7 = v27;
      StringCchPrintfW(v27, v12, L"Resources\\%lu\\", UserDefaultLCID);
    }
    _wmakepath_s(v8, 0x104u, v9, v4, Filename, Ext);
  }
  v13 = 10;
  if ( g_osviEx.dwMajorVersion >= 6 )
    v13 = 42;
  v14 = L"SQLNCLIR11.RLL";
  if ( v3 )
    v14 = v8;
  v27 = v14;
  Library = LoadLibraryExW(v14, 0, v13);
  g_hinstance_language = Library;
  if ( g_fIsEmbeddedSNAC && !Library )
  {
LABEL_57:
    v18 = -2147467259;
    goto LABEL_29;
  }
  if ( !v3 )
    goto LABEL_70;
  if ( !Library )
  {
    *v7 = 0;
    v16 = -1;
    do
      ++v16;
    while ( v4[v16] );
    v17 = GetUserDefaultLCID();
    if ( v17 == 3076 )
      v17 = 1028;
    StringCchPrintfW(&v4[v16], 256 - v16, L"%lu\\", v17);
    _wmakepath_s(v8, 0x104u, v9, v4, Filename, Ext);
    g_hinstance_language = LoadLibraryExW(v8, 0, 8u);
    if ( !g_hinstance_language )
    {
      v4[v16] = 0;
      v22 = -1;
      do
        ++v22;
      while ( v4[v22] );
      SystemDefaultLCID = GetSystemDefaultLCID();
      if ( SystemDefaultLCID == 3076 )
        SystemDefaultLCID = 1028;
      StringCchPrintfW(&v4[v22], 256 - v22, L"%lu\\", SystemDefaultLCID);
      _wmakepath_s(v8, 0x104u, v9, v4, Filename, Ext);
      g_hinstance_language = LoadLibraryExW(v8, 0, 8u);
      if ( !g_hinstance_language )
      {
        v4[v22] = 0;
        v24 = -1;
        do
          ++v24;
        while ( v4[v24] );
        v25 = &v4[v24];
        StringCchCatW(v25, 256 - v24, L"1033");
        _wmakepath_s(v8, 0x104u, v9, v4, Filename, Ext);
        g_hinstance_language = LoadLibraryExW(v8, 0, 8u);
        if ( !g_hinstance_language )
        {
          *v25 = 0;
          _wmakepath_s(v8, 0x104u, v9, v4, Filename, Ext);
          Library = LoadLibraryExW(v8, 0, 8u);
          g_hinstance_language = Library;
LABEL_70:
          if ( !Library )
          {
            g_hinstance_language = LoadLibraryExW(L"SQLNCLIR11.RLL", 0, 0);
            if ( !g_hinstance_language )
            {
              if ( (bidGblFlags & 2) != 0 && off_383B4A1C0[0] )
              {
                GetLastError();
                bidTraceW(off_383B434E8[0], 358400, off_383B4A1C0[0], v27);
              }
              goto LABEL_57;
            }
          }
        }
      }
    }
  }
  v18 = 0;
LABEL_29:
  ((void (__fastcall *)(struct IMalloc *, WCHAR *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v8);
  if ( v9 )
    ((void (__fastcall *)(struct IMalloc *, wchar_t *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v9);
  if ( v4 )
    ((void (__fastcall *)(struct IMalloc *, wchar_t *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v4);
  if ( Ext )
    ((void (__fastcall *)(struct IMalloc *, wchar_t *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, Ext);
  if ( Filename )
    ((void (__fastcall *)(struct IMalloc *, wchar_t *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, Filename);
LABEL_37:
  if ( v26 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return v18;
}

```

## disassembly

```asm
0x383892de0  mov     r11, rsp
0x383892de3  mov     [r11+18h], rbx
0x383892de7  push    rbp
0x383892de8  push    rsi
0x383892de9  push    rdi
0x383892dea  push    r12
0x383892dec  push    r13
0x383892dee  push    r14
0x383892df0  push    r15
0x383892df2  sub     rsp, 50h
0x383892df6  or      qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x383892dfb  mov     r15, cs:?g_hinstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance
0x383892e02  xor     r12d, r12d
0x383892e05  test    byte ptr cs:_bidGblFlags, 4
0x383892e0c  jnz     loc_3838F35FC
0x383892e12  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383892e19  mov     edx, 208h
0x383892e1e  mov     rdi, r12
0x383892e21  mov     rax, [rcx]
0x383892e24  mov     rbp, r12
0x383892e27  mov     r14, r12
0x383892e2a  mov     rbx, r12
0x383892e2d  call    qword ptr [rax+70h]
0x383892e30  mov     rsi, rax
0x383892e33  test    rax, rax
0x383892e36  jz      loc_3838F362C
0x383892e3c  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383892e43  mov     edx, 6
0x383892e48  mov     rax, [rcx]
0x383892e4b  call    qword ptr [rax+70h]
0x383892e4e  mov     r13, rax
0x383892e51  test    rax, rax
0x383892e54  jz      loc_3838F365D
0x383892e5a  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383892e61  mov     edx, 200h
0x383892e66  mov     rax, [rcx]
0x383892e69  call    qword ptr [rax+70h]
0x383892e6c  mov     rdi, rax
0x383892e6f  test    rax, rax
0x383892e72  jz      loc_3838F368E
0x383892e78  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383892e7f  mov     edx, 200h
0x383892e84  mov     rax, [rcx]
0x383892e87  call    qword ptr [rax+70h]
0x383892e8a  mov     rbp, rax
0x383892e8d  test    rax, rax
0x383892e90  jz      loc_3838F369E
0x383892e96  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383892e9d  mov     edx, 200h
0x383892ea2  mov     rax, [rcx]
0x383892ea5  call    qword ptr [rax+70h]
0x383892ea8  mov     r14, rax
0x383892eab  test    rax, rax
0x383892eae  jz      loc_3838F36AE
0x383892eb4  mov     r12d, 100h
0x383892eba  test    r15, r15
0x383892ebd  jz      loc_383892FB7
0x383892ec3  lea     r8d, [r12+3]; nSize
0x383892ec8  mov     rdx, rsi; lpFilename
0x383892ecb  mov     rcx, r15; hModule
0x383892ece  call    cs:__imp_GetModuleFileNameW
0x383892ed4  test    eax, eax
0x383892ed6  jz      loc_3838F36BE
0x383892edc  mov     [rsp+88h+ExtCount], rbx; ExtCount
0x383892ee1  mov     [rsp+88h+Ext], rbx; Ext
0x383892ee6  mov     [rsp+88h+FilenameCount], rbx; FilenameCount
0x383892eeb  mov     r9, rdi; Dir
0x383892eee  mov     r8d, 3; DriveCount
0x383892ef4  mov     rdx, r13; Drive
0x383892ef7  mov     rcx, rsi; FullPath
0x383892efa  mov     [rsp+88h+Filename], rbx; Filename
0x383892eff  mov     [rsi+206h], bx
0x383892f06  mov     [rsp+88h+DirCount], r12; DirCount
0x383892f0b  call    cs:__imp__wsplitpath_s
0x383892f11  mov     [rsp+88h+ExtCount], r12; ExtCount
0x383892f16  mov     [rsp+88h+Ext], r14; Ext
0x383892f1b  mov     [rsp+88h+FilenameCount], r12; FilenameCount
0x383892f20  lea     rcx, aSqlnclir11Rll; "SQLNCLIR11.RLL"
0x383892f27  xor     r9d, r9d; Dir
0x383892f2a  xor     r8d, r8d; DriveCount
0x383892f2d  xor     edx, edx; Drive
0x383892f2f  mov     [rsp+88h+Filename], rbp; Filename
0x383892f34  mov     [rsp+88h+DirCount], rbx; DirCount
0x383892f39  call    cs:__imp__wsplitpath_s
0x383892f3f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x383892f43  xor     ecx, ecx
0x383892f45  inc     rbx
0x383892f48  cmp     [rdi+rbx*2], cx
0x383892f4c  jnz     short loc_383892F45
0x383892f4e  cmp     cs:?g_fIsEmbeddedSNAC@@3_NA, cl; bool g_fIsEmbeddedSNAC
0x383892f54  lea     rax, [rdi+rbx*2]
0x383892f58  mov     [rsp+88h+arg_8], rax
0x383892f60  jnz     loc_3838F36FE
0x383892f66  call    cs:__imp_GetUserDefaultLCID
0x383892f6c  mov     ecx, 404h
0x383892f71  mov     rdx, r12
0x383892f74  cmp     eax, 0C04h
0x383892f79  lea     r8, aResourcesLu; "Resources\\%lu\\"
0x383892f80  cmovz   eax, ecx
0x383892f83  sub     rdx, rbx; unsigned __int64
0x383892f86  mov     rbx, [rsp+88h+arg_8]
0x383892f8e  mov     rcx, rbx; unsigned __int16 *
0x383892f91  mov     r9d, eax
0x383892f94  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x383892f99  mov     r9, rdi; Dir
0x383892f9c  mov     r8, r13; Drive
0x383892f9f  mov     edx, 104h; BufferCount
0x383892fa4  mov     rcx, rsi; Buffer
0x383892fa7  mov     [rsp+88h+Filename], r14; Ext
0x383892fac  mov     [rsp+88h+DirCount], rbp; Filename
0x383892fb1  call    cs:__imp__wmakepath_s
0x383892fb7  cmp     cs:?g_osviEx@@3U_OSVERSIONINFOEXW@@A.dwMajorVersion, 6; _OSVERSIONINFOEXW g_osviEx ...
0x383892fbe  mov     eax, 2Ah ; '*'
0x383892fc3  lea     r8d, [rax-20h]
0x383892fc7  cmovnb  r8d, eax; dwFlags
0x383892fcb  lea     rax, aSqlnclir11Rll; "SQLNCLIR11.RLL"
0x383892fd2  test    r15, r15
0x383892fd5  cmovnz  rax, rsi
0x383892fd9  xor     edx, edx; hFile
0x383892fdb  mov     rcx, rax; lpLibFileName
0x383892fde  mov     [rsp+88h+arg_8], rax
0x383892fe6  call    cs:__imp_LoadLibraryExW
0x383892fec  xor     ecx, ecx
0x383892fee  cmp     cs:?g_fIsEmbeddedSNAC@@3_NA, cl; bool g_fIsEmbeddedSNAC
0x383892ff4  mov     cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstance_language
0x383892ffb  jnz     loc_3838F3720
0x383893001  test    r15, r15
0x383893004  jz      loc_3838F3851
0x38389300a  test    rax, rax
0x38389300d  jnz     short loc_38389308D
0x38389300f  mov     [rbx], cx
0x383893012  or      rbx, 0FFFFFFFFFFFFFFFFh
0x383893016  inc     rbx
0x383893019  cmp     [rdi+rbx*2], cx
0x38389301d  jnz     short loc_383893016
0x38389301f  lea     r15, [rdi+rbx*2]
0x383893023  call    cs:__imp_GetUserDefaultLCID
0x383893029  mov     ecx, 404h
0x38389302e  cmp     eax, 0C04h
0x383893033  mov     rdx, r12
0x383893036  lea     r8, aLu; "%lu\\"
0x38389303d  cmovz   eax, ecx
0x383893040  sub     rdx, rbx; unsigned __int64
0x383893043  mov     rcx, r15; unsigned __int16 *
0x383893046  mov     r9d, eax
0x383893049  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x38389304e  mov     r9, rdi; Dir
0x383893051  mov     r8, r13; Drive
0x383893054  mov     edx, 104h; BufferCount
0x383893059  mov     rcx, rsi; Buffer
0x38389305c  mov     [rsp+88h+Filename], r14; Ext
0x383893061  mov     [rsp+88h+DirCount], rbp; Filename
0x383893066  call    cs:__imp__wmakepath_s
0x38389306c  xor     edx, edx; hFile
0x38389306e  lea     r8d, [rdx+8]; dwFlags
0x383893072  mov     rcx, rsi; lpLibFileName
0x383893075  call    cs:__imp_LoadLibraryExW
0x38389307b  xor     ecx, ecx
0x38389307d  mov     cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstance_language
0x383893084  test    rax, rax
0x383893087  jz      loc_3838F372B
0x38389308d  xor     r12d, r12d
0x383893090  mov     ebx, r12d
0x383893093  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x38389309a  mov     rdx, rsi
0x38389309d  mov     rax, [rcx]
0x3838930a0  call    qword ptr [rax+80h]
0x3838930a6  test    r13, r13
0x3838930a9  jz      short loc_3838930BE
0x3838930ab  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838930b2  mov     rdx, r13
0x3838930b5  mov     rax, [rcx]
0x3838930b8  call    qword ptr [rax+80h]
0x3838930be  test    rdi, rdi
0x3838930c1  jz      short loc_3838930D6
0x3838930c3  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838930ca  mov     rdx, rdi
0x3838930cd  mov     rax, [rcx]
0x3838930d0  call    qword ptr [rax+80h]
0x3838930d6  test    r14, r14
0x3838930d9  jz      short loc_3838930EE
0x3838930db  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838930e2  mov     rdx, r14
0x3838930e5  mov     rax, [rcx]
0x3838930e8  call    qword ptr [rax+80h]
0x3838930ee  test    rbp, rbp
0x3838930f1  jz      short loc_383893106
0x3838930f3  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838930fa  mov     rdx, rbp
0x3838930fd  mov     rax, [rcx]
0x383893100  call    qword ptr [rax+80h]
0x383893106  cmp     [rsp+88h+arg_0], 0FFFFFFFFFFFFFFFFh
0x38389310f  jnz     loc_3838F38CB
0x383893115  mov     eax, ebx
0x383893117  mov     rbx, [rsp+88h+arg_10]
0x38389311f  add     rsp, 50h
0x383893123  pop     r15
0x383893125  pop     r14
0x383893127  pop     r13
0x383893129  pop     r12
0x38389312b  pop     rdi
0x38389312c  pop     rsi
0x38389312d  pop     rbp
0x38389312e  retn
0x3838f35fc  mov     rax, cs:off_383B4AD38; "<LoadResourceDLL|SNAC|MSDATL> resFileNa"...
0x3838f3603  test    rax, rax
0x3838f3606  jz      loc_383892E12
0x3838f360c  mov     rdx, cs:off_383B4AD38; "<LoadResourceDLL|SNAC|MSDATL> resFileNa"...
0x3838f3613  lea     r8, aSqlnclir11Rll; "SQLNCLIR11.RLL"
0x3838f361a  lea     rcx, [r11+8]
0x3838f361e  mov     r9, r15
0x3838f3621  call    _bidScopeEnterW
0x3838f3626  nop
0x3838f3627  jmp     loc_383892E12
0x3838f362c  test    byte ptr cs:_bidGblFlags, 2
0x3838f3633  jz      short loc_3838F3653
0x3838f3635  mov     rcx, cs:off_383B434E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f363c  mov     edx, 1D009h
0x3838f3641  mov     r8d, 8007000Eh
0x3838f3647  call    _bidTraceHR
0x3838f364c  mov     ebx, eax
0x3838f364e  jmp     loc_383893106
0x3838f3653  mov     ebx, 8007000Eh
0x3838f3658  jmp     loc_383893106
0x3838f365d  test    byte ptr cs:_bidGblFlags, 2
0x3838f3664  jz      short loc_3838F3684
0x3838f3666  mov     edx, 1EC09h
0x3838f366b  mov     rcx, cs:off_383B434E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f3672  mov     r8d, 8007000Eh
0x3838f3678  call    _bidTraceHR
0x3838f367d  mov     ebx, eax
0x3838f367f  jmp     loc_383893093
0x3838f3684  mov     ebx, 8007000Eh
0x3838f3689  jmp     loc_383893093
0x3838f368e  test    byte ptr cs:_bidGblFlags, 2
0x3838f3695  jz      short loc_3838F3684
0x3838f3697  mov     edx, 20809h
0x3838f369c  jmp     short loc_3838F366B
0x3838f369e  test    byte ptr cs:_bidGblFlags, 2
0x3838f36a5  jz      short loc_3838F3684
0x3838f36a7  mov     edx, 22409h
0x3838f36ac  jmp     short loc_3838F366B
0x3838f36ae  test    byte ptr cs:_bidGblFlags, 2
0x3838f36b5  jz      short loc_3838F3684
0x3838f36b7  mov     edx, 24009h
0x3838f36bc  jmp     short loc_3838F366B
0x3838f36be  test    byte ptr cs:_bidGblFlags, 2
0x3838f36c5  jz      short loc_3838F36F4
0x3838f36c7  mov     rax, cs:off_383B4A1C8; "<LoadResourceDLL|ERR|SNAC|MSDATL> GetMo"...
0x3838f36ce  test    rax, rax
0x3838f36d1  jz      short loc_3838F36F4
0x3838f36d3  call    cs:__imp_GetLastError
0x3838f36d9  mov     r8, cs:off_383B4A1C8; "<LoadResourceDLL|ERR|SNAC|MSDATL> GetMo"...
0x3838f36e0  mov     rcx, cs:off_383B434E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f36e7  mov     r9d, eax
0x3838f36ea  mov     edx, 27800h
0x3838f36ef  call    _bidTraceW
0x3838f36f4  mov     ebx, 80004005h
0x3838f36f9  jmp     loc_383893093
0x3838f36fe  mov     rdx, r12
0x3838f3701  lea     r8, aResources; "Resources\\"
0x3838f3708  mov     rcx, rax; unsigned __int16 *
0x3838f370b  sub     rdx, rbx; unsigned __int64
0x3838f370e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x3838f3713  mov     rbx, [rsp+88h+arg_8]
0x3838f371b  jmp     loc_383892F99
0x3838f3720  test    rax, rax
0x3838f3723  jnz     loc_383893001
0x3838f3729  jmp     short loc_3838F36F4
0x3838f372b  mov     [r15], cx
0x3838f372f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x3838f3733  inc     rbx
0x3838f3736  cmp     [rdi+rbx*2], cx
0x3838f373a  jnz     short loc_3838F3733
0x3838f373c  lea     r15, [rdi+rbx*2]
0x3838f3740  call    cs:__imp_GetSystemDefaultLCID
0x3838f3746  mov     ecx, 404h
0x3838f374b  cmp     eax, 0C04h
0x3838f3750  mov     rdx, r12
0x3838f3753  lea     r8, aLu; "%lu\\"
0x3838f375a  cmovz   eax, ecx
0x3838f375d  sub     rdx, rbx; unsigned __int64
0x3838f3760  mov     rcx, r15; unsigned __int16 *
0x3838f3763  mov     r9d, eax
0x3838f3766  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x3838f376b  mov     r9, rdi; Dir
0x3838f376e  mov     r8, r13; Drive
0x3838f3771  mov     edx, 104h; BufferCount
0x3838f3776  mov     rcx, rsi; Buffer
0x3838f3779  mov     [rsp+88h+Filename], r14; Ext
0x3838f377e  mov     [rsp+88h+DirCount], rbp; Filename
0x3838f3783  call    cs:__imp__wmakepath_s
0x3838f3789  xor     edx, edx; hFile
0x3838f378b  lea     r8d, [rdx+8]; dwFlags
0x3838f378f  mov     rcx, rsi; lpLibFileName
0x3838f3792  call    cs:__imp_LoadLibraryExW
0x3838f3798  xor     ecx, ecx
0x3838f379a  mov     cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstance_language
0x3838f37a1  test    rax, rax
0x3838f37a4  jnz     loc_38389308D
  ... truncated ...
```
