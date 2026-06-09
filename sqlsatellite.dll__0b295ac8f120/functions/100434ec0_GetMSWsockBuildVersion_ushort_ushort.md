# GetMSWsockBuildVersion(ushort *,ushort *)

- ea: `0x100434ec0`
- end: `0x10043523a`
- name: `?GetMSWsockBuildVersion@@YAKPEAG0@Z`
- size: `890`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x100435530`

## callees

- `0x10042b9b0`
- `0x100434ec0`
- `0x100486af0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x100434fdb`
- `KERNEL32!FreeLibrary` at `0x100435204`
- `KERNEL32!FreeLibrary` at `0x100434fdb`
- `KERNEL32!FreeLibrary` at `0x100435204`
- `KERNEL32!SetLastError` at `0x100434f26`
- `KERNEL32!SetLastError` at `0x100434f26`
- `KERNEL32!GetModuleFileNameW` at `0x100434fbd`
- `KERNEL32!GetModuleFileNameW` at `0x100434fbd`
- `KERNEL32!GetLastError` at `0x100434ff7`
- `KERNEL32!GetLastError` at `0x1004350f3`
- `KERNEL32!GetLastError` at `0x1004351bb`
- `KERNEL32!GetLastError` at `0x100434ff7`
- `KERNEL32!GetLastError` at `0x1004350f3`
- `KERNEL32!GetLastError` at `0x1004351bb`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100434f61`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100434f61`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043512f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100435177`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004351b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10043512f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100435177`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004351b3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043509b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043509b`
- `sqldk!SystemThread_TlsIndex` at `0x10043503e`
- `sqldk!SystemThread_TlsOffset` at `0x100435047`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100435062`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100435062`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x100434f49`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x100434f49`
- `VERSION!GetFileVersionInfoW` at `0x1004350e9`
- `VERSION!GetFileVersionInfoW` at `0x1004350e9`
- `VERSION!VerQueryValueW` at `0x10043514e`
- `VERSION!VerQueryValueW` at `0x10043514e`
- `VERSION!GetFileVersionInfoSizeW` at `0x100434feb`
- `VERSION!GetFileVersionInfoSizeW` at `0x100434feb`

## string_xrefs

- `0x100434f91`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100435024`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100435076`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004350c6`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100435120`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004351a4`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004351f5`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100434f8a`: `GetFullPathToSystemDLL`
- `0x1004351e3`: `GetFullPathToSystemDLL`
- `0x100434f78`: `ERR|SNICouldn't load system dll '%hs'.\n`
- `0x100434eea`: `mswsock.dll`
- `0x1004351d8`: `ERR|SNIInvalid length of path of system dll: '%hs', length: %d, %d{WINERR}.\n`

## pseudocode

```c
DWORD __fastcall GetMSWsockBuildVersion(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  const char *v3; // rax
  __int64 v6; // r8
  HMODULE v7; // rax
  HMODULE v8; // rdi
  DWORD result; // eax
  DWORD ModuleFileNameW; // eax
  DWORD v11; // esi
  DWORD FileVersionInfoSizeW; // eax
  unsigned __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rax
  void *v16; // rax
  void *v17; // rdi
  DWORD v18; // eax
  _WORD *v19; // rcx
  DWORD LastError; // eax
  __int64 v21; // [rsp+20h] [rbp-488h]
  __int64 v22; // [rsp+20h] [rbp-488h]
  DWORD dwHandle; // [rsp+40h] [rbp-468h] BYREF
  unsigned int puLen; // [rsp+44h] [rbp-464h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-460h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-458h] BYREF
  wchar_t v27[264]; // [rsp+260h] [rbp-248h] BYREF

  v2 = 0;
  dwHandle = 0;
  lpBuffer = 0;
  v3 = "mswsock.dll";
  v6 = 261;
  while ( *v3 )
  {
    ++v3;
    if ( !--v6 )
    {
      SetLastError(0x7Bu);
      goto LABEL_6;
    }
  }
  FastDBCSToUnicode(0, "mswsock.dll", -1, v27, 261);
  v7 = SOS_OS::SOSLoadLibraryW(v27, 1, 0, 0);
  v8 = v7;
  if ( !v7 )
  {
LABEL_6:
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\tcp.cpp",
        "GetFullPathToSystemDLL",
        1836,
        L"ERR|SNICouldn't load system dll '%hs'.\n",
        "mswsock.dll");
    return -1;
  }
  ModuleFileNameW = GetModuleFileNameW(v7, Filename, 0x104u);
  v11 = ModuleFileNameW;
  if ( ModuleFileNameW - 1 > 0x102 )
  {
    LastError = GetLastError();
    v2 = -1;
    if ( !LastError )
      LastError = -1;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\tcp.cpp",
        "GetFullPathToSystemDLL",
        1855,
        L"ERR|SNIInvalid length of path of system dll: '%hs', length: %d, %d{WINERR}.\n",
        "mswsock.dll",
        v11,
        LastError);
    FreeLibrary(v8);
    return v2;
  }
  Filename[ModuleFileNameW] = 0;
  FreeLibrary(v8);
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Filename, &dwHandle);
  v13 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
  {
    result = GetLastError();
    v2 = result;
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      return result;
    LODWORD(v21) = result;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "GetMSWsockBuildVersion",
      1893,
      L"ERR|SNIGetFileVersionInfoSize: %d{WINERR}.\n",
      v21);
    return v2;
  }
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
  }
  v16 = operator new[](
          v13,
          *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v15 + 992) + 56LL) + 8LL),
          1,
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          1897,
          6u);
  v17 = v16;
  if ( v16 )
  {
    if ( GetFileVersionInfoW(Filename, 0, v13, v16) )
    {
      if ( VerQueryValueW(v17, L"\\", &lpBuffer, &puLen) && puLen == 52 )
      {
        v19 = lpBuffer;
        *a1 = *((_WORD *)lpBuffer + 7);
        *a2 = v19[6];
        operator delete[](v17);
        return v2;
      }
      v2 = -1;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "GetMSWsockBuildVersion",
          1922,
          L"ERR|SNIVerQueryValue failed.\n");
    }
    else
    {
      v18 = GetLastError();
      v2 = v18;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v22) = v18;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "GetMSWsockBuildVersion",
          1910,
          L"ERR|SNIGetFileVersionInfo: %d{WINERR}.\n",
          v22);
        operator delete[](v17);
        return v2;
      }
    }
    operator delete[](v17);
    return v2;
  }
  if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "GetMSWsockBuildVersion",
      1902,
      L"ERR|SNIMemory allocation failed while allocating file version info buffer.\n");
  return 14;
}

```

## disassembly

```asm
0x100434ec0  push    rbx
0x100434ec2  push    rbp
0x100434ec3  push    r14
0x100434ec5  push    r15
0x100434ec7  sub     rsp, 488h
0x100434ece  mov     rax, cs:__security_cookie
0x100434ed5  xor     rax, rsp
0x100434ed8  mov     [rsp+4A8h+var_38], rax
0x100434ee0  xor     ebx, ebx
0x100434ee2  mov     [rsp+4A8h+var_28], rdi
0x100434eea  lea     rbp, aMswsockDll_0; "mswsock.dll"
0x100434ef1  mov     [rsp+4A8h+dwHandle], ebx
0x100434ef5  mov     [rsp+4A8h+lpBuffer], rbx
0x100434efa  mov     rax, rbp
0x100434efd  mov     r15, rdx
0x100434f00  mov     r14, rcx
0x100434f03  mov     r8d, 105h
0x100434f09  nop     dword ptr [rax+00000000h]
0x100434f10  cmp     [rax], bl
0x100434f12  jz      short loc_100434F2E
0x100434f14  inc     rax
0x100434f17  sub     r8, 1
0x100434f1b  jnz     short loc_100434F10
0x100434f1d  test    r8, r8
0x100434f20  jnz     short loc_100434F2E
0x100434f22  lea     ecx, [r8+7Bh]; dwErrCode
0x100434f26  call    cs:__imp_SetLastError
0x100434f2c  jmp     short loc_100434F6F
0x100434f2e  lea     r9, [rsp+4A8h+var_248]
0x100434f36  mov     dword ptr [rsp+4A8h+var_488], 105h
0x100434f3e  mov     r8d, 0FFFFFFFFh
0x100434f44  mov     rdx, rbp
0x100434f47  xor     ecx, ecx
0x100434f49  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x100434f4f  xor     r9d, r9d
0x100434f52  lea     rcx, [rsp+4A8h+var_248]
0x100434f5a  xor     r8d, r8d
0x100434f5d  lea     edx, [r9+1]
0x100434f61  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x100434f67  mov     rdi, rax
0x100434f6a  test    rax, rax
0x100434f6d  jnz     short loc_100434FA7
0x100434f6f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100434f76  jz      short loc_100434F9D
0x100434f78  lea     r9, aErrSnicouldnTL; "ERR|SNICouldn't load system dll '%hs'."...
0x100434f7f  mov     [rsp+4A8h+var_488], rbp
0x100434f84  mov     r8d, 72Ch; int
0x100434f8a  lea     rdx, aGetfullpathtos; "GetFullPathToSystemDLL"
0x100434f91  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100434f98  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100434f9d  mov     eax, 0FFFFFFFFh
0x100434fa2  jmp     loc_100435214
0x100434fa7  mov     r8d, 104h; nSize
0x100434fad  mov     [rsp+4A8h+arg_10], rsi
0x100434fb5  lea     rdx, [rsp+4A8h+Filename]; lpFilename
0x100434fba  mov     rcx, rdi; hModule
0x100434fbd  call    cs:__imp_GetModuleFileNameW
0x100434fc3  mov     esi, eax
0x100434fc5  lea     eax, [rsi-1]
0x100434fc8  cmp     eax, 102h
0x100434fcd  ja      loc_1004351BB
0x100434fd3  mov     rcx, rdi; hLibModule
0x100434fd6  mov     [rsp+rsi*2+4A8h+Filename], bx
0x100434fdb  call    cs:__imp_FreeLibrary
0x100434fe1  lea     rdx, [rsp+4A8h+dwHandle]; lpdwHandle
0x100434fe6  lea     rcx, [rsp+4A8h+Filename]; lptstrFilename
0x100434feb  call    cs:__imp_GetFileVersionInfoSizeW
0x100434ff1  mov     esi, eax
0x100434ff3  test    eax, eax
0x100434ff5  jnz     short loc_100435035
0x100434ff7  call    cs:__imp_GetLastError
0x100434ffd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435004  mov     ebx, eax
0x100435006  jz      loc_10043520C
0x10043500c  lea     r9, aErrSnigetfilev; "ERR|SNIGetFileVersionInfoSize: %d{WINER"...
0x100435013  mov     dword ptr [rsp+4A8h+var_488], eax
0x100435017  mov     r8d, 765h; int
0x10043501d  lea     rdx, aGetmswsockbuil; "GetMSWsockBuildVersion"
0x100435024  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x10043502b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100435030  jmp     loc_10043520A
0x100435035  mov     rdx, gs:58h
0x10043503e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100435045  mov     ecx, [rax]
0x100435047  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043504e  mov     edi, [rax]
0x100435050  add     rdi, [rdx+rcx*8]
0x100435054  mov     rax, [rdi+100h]
0x10043505b  test    rax, rax
0x10043505e  jnz     short loc_10043506F
0x100435060  xor     ecx, ecx
0x100435062  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100435068  mov     rax, [rdi+100h]
0x10043506f  mov     rax, [rax+3E0h]
0x100435076  lea     r9, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x10043507d  mov     byte ptr [rsp+4A8h+var_480], 6
0x100435082  mov     r8d, 1
0x100435088  mov     dword ptr [rsp+4A8h+var_488], 769h
0x100435090  mov     rcx, [rax+38h]
0x100435094  mov     rdx, [rcx+8]
0x100435098  mov     rcx, rsi
0x10043509b  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004350a1  mov     rdi, rax
0x1004350a4  test    rax, rax
0x1004350a7  jnz     short loc_1004350DC
0x1004350a9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004350b0  jz      short loc_1004350D2
0x1004350b2  lea     r9, aErrSnimemoryAl; "ERR|SNIMemory allocation failed while a"...
0x1004350b9  mov     r8d, 76Eh; int
0x1004350bf  lea     rdx, aGetmswsockbuil; "GetMSWsockBuildVersion"
0x1004350c6  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x1004350cd  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004350d2  mov     eax, 0Eh
0x1004350d7  jmp     loc_10043520C
0x1004350dc  mov     r9, rdi; lpData
0x1004350df  lea     rcx, [rsp+4A8h+Filename]; lptstrFilename
0x1004350e4  mov     r8d, esi; dwLen
0x1004350e7  xor     edx, edx; dwHandle
0x1004350e9  call    cs:__imp_GetFileVersionInfoW
0x1004350ef  test    eax, eax
0x1004350f1  jnz     short loc_10043513A
0x1004350f3  call    cs:__imp_GetLastError
0x1004350f9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435100  mov     ebx, eax
0x100435102  jz      loc_1004351B0
0x100435108  lea     r9, aErrSnigetfilev_0; "ERR|SNIGetFileVersionInfo: %d{WINERR}."...
0x10043510f  mov     dword ptr [rsp+4A8h+var_488], eax
0x100435113  mov     r8d, 776h; int
0x100435119  lea     rdx, aGetmswsockbuil; "GetMSWsockBuildVersion"
0x100435120  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100435127  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043512c  mov     rcx, rdi
0x10043512f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100435135  jmp     loc_10043520A
0x10043513a  lea     r9, [rsp+4A8h+puLen]; puLen
0x10043513f  mov     rcx, rdi; pBlock
0x100435142  lea     r8, [rsp+4A8h+lpBuffer]; lplpBuffer
0x100435147  lea     rdx, SubBlock; "\\"
0x10043514e  call    cs:__imp_VerQueryValueW
0x100435154  test    eax, eax
0x100435156  jz      short loc_100435182
0x100435158  cmp     [rsp+4A8h+puLen], 34h ; '4'
0x10043515d  jnz     short loc_100435182
0x10043515f  mov     rcx, [rsp+4A8h+lpBuffer]
0x100435164  movzx   eax, word ptr [rcx+0Eh]
0x100435168  mov     [r14], ax
0x10043516c  movzx   eax, word ptr [rcx+0Ch]
0x100435170  mov     rcx, rdi
0x100435173  mov     [r15], ax
0x100435177  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10043517d  jmp     loc_10043520A
0x100435182  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435189  mov     ebx, 0FFFFFFFFh
0x10043518e  jz      short loc_1004351B0
0x100435190  lea     r9, aErrSniverquery; "ERR|SNIVerQueryValue failed.\n"
0x100435197  mov     r8d, 782h; int
0x10043519d  lea     rdx, aGetmswsockbuil; "GetMSWsockBuildVersion"
0x1004351a4  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x1004351ab  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004351b0  mov     rcx, rdi
0x1004351b3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004351b9  jmp     short loc_10043520A
0x1004351bb  call    cs:__imp_GetLastError
0x1004351c1  test    eax, eax
0x1004351c3  mov     ebx, 0FFFFFFFFh
0x1004351c8  cmovz   eax, ebx
0x1004351cb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004351d2  jz      short loc_100435201
0x1004351d4  mov     [rsp+4A8h+var_478], eax
0x1004351d8  lea     r9, aErrSniinvalidL; "ERR|SNIInvalid length of path of system"...
0x1004351df  mov     [rsp+4A8h+var_480], esi
0x1004351e3  lea     rdx, aGetfullpathtos; "GetFullPathToSystemDLL"
0x1004351ea  mov     r8d, 73Fh; int
0x1004351f0  mov     [rsp+4A8h+var_488], rbp
0x1004351f5  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x1004351fc  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100435201  mov     rcx, rdi; hLibModule
0x100435204  call    cs:__imp_FreeLibrary
0x10043520a  mov     eax, ebx
0x10043520c  mov     rsi, [rsp+4A8h+arg_10]
0x100435214  mov     rdi, [rsp+4A8h+var_28]
0x10043521c  mov     rcx, [rsp+4A8h+var_38]
0x100435224  xor     rcx, rsp; StackCookie
0x100435227  call    __security_check_cookie
0x10043522c  add     rsp, 488h
0x100435233  pop     r15
0x100435235  pop     r14
0x100435237  pop     rbp
0x100435238  pop     rbx
0x100435239  retn
```
