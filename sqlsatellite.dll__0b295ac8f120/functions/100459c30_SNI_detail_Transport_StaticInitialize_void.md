# SNI::detail::Transport::StaticInitialize(void)

- ea: `0x100459c30`
- end: `0x100459e82`
- name: `?StaticInitialize@Transport@detail@SNI@@SAKXZ`
- size: `594`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x100433d30`
- `0x100438340`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100459c30`
- `0x100459e90`
- `0x100486af0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x100459d07`
- `KERNEL32!SetLastError` at `0x100459d07`
- `KERNEL32!GetProcAddress` at `0x100459d92`
- `KERNEL32!GetProcAddress` at `0x100459d92`
- `KERNEL32!GetLastError` at `0x100459d59`
- `KERNEL32!GetLastError` at `0x100459dc7`
- `KERNEL32!GetLastError` at `0x100459d59`
- `KERNEL32!GetLastError` at `0x100459dc7`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100459d47`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100459d47`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x100459d32`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x100459d32`

## string_xrefs

- `0x100459ce6`: `kernel32.dll`
- `0x100459d29`: `kernel32.dll`
- `0x100459c5e`: `sql\common\dk\sni\src\transport.cpp`
- `0x100459d88`: `SetFileCompletionNotificationModes`
- `0x100459db1`: `ERR|SNIGetProcAddress for SetFileCompletionNotificationModes failed: %d.\n`
- `0x100459d6e`: `ERR|SNILoadLibrary for Kernel32 failed: %d.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SNI::detail::Transport::StaticInitialize(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  DWORD v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // rcx
  const CHAR *v7; // rax
  HMODULE v8; // rax
  DWORD LastError; // eax
  __int64 v11; // [rsp+20h] [rbp-268h]
  wchar_t v12[264]; // [rsp+60h] [rbp-228h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\transport.cpp",
      "SNI::detail::Transport::StaticInitialize",
      60,
      L"API|SNI\n");
  v4 = 0;
  v5 = ++SNI::detail::Transport::s_dwRefCount;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\transport.cpp",
      "SNI::detail::Transport::StaticInitialize",
      66,
      L"SNITransport ref-count: %d.\n",
      v5);
    v5 = SNI::detail::Transport::s_dwRefCount;
  }
  if ( v5 == 1 )
  {
    v6 = 261;
    v7 = "kernel32.dll";
    while ( *v7 )
    {
      ++v7;
      if ( !--v6 )
      {
        SetLastError(0x7Bu);
        SNI::detail::Transport::s_hKernel32 = 0;
        goto LABEL_11;
      }
    }
    FastDBCSToUnicode(0, "kernel32.dll", -1, v12, 261);
    v8 = SOS_OS::SOSLoadLibraryW(v12, 1, 0, 0);
    SNI::detail::Transport::s_hKernel32 = v8;
    if ( !v8 )
    {
LABEL_11:
      LastError = GetLastError();
      v4 = LastError;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v11) = LastError;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\transport.cpp",
          "SNI::detail::Transport::StaticInitialize",
          95,
          L"ERR|SNILoadLibrary for Kernel32 failed: %d.\n",
          v11);
      }
      goto LABEL_17;
    }
    SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes = (int (*)(void *, unsigned __int8))GetProcAddress(v8, "SetFileCompletionNotificationModes");
    if ( SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes )
      goto LABEL_20;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v11) = 0;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\transport.cpp",
        "SNI::detail::Transport::StaticInitialize",
        108,
        L"ERR|SNIGetProcAddress for SetFileCompletionNotificationModes failed: %d.\n",
        v11);
    }
    v4 = GetLastError();
LABEL_17:
    SNI::detail::Transport::StaticTerminate();
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v11) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\transport.cpp",
        "SNI::detail::Transport::StaticInitialize",
        125,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v11,
        0,
        v4);
    }
    SNISetLastError(0xAu, v4, 0xC3B4u);
  }
LABEL_20:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v11) = v4;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\transport.cpp",
      "SNI::detail::Transport::StaticInitialize",
      128,
      L"RET|SNI%d{BOOL}\n",
      v11);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\transport.cpp", "SNI::detail::Transport::StaticInitialize", 60, a4);
  return v4;
}

```

## disassembly

```asm
0x100459c30  mov     rax, rsp
0x100459c33  push    rdi
0x100459c34  sub     rsp, 280h
0x100459c3b  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x100459c44  mov     [rax+8], rbx
0x100459c48  mov     [rax+10h], rsi
0x100459c4c  mov     rax, cs:__security_cookie
0x100459c53  xor     rax, rsp
0x100459c56  mov     [rsp+288h+var_18], rax
0x100459c5e  lea     rdi, aSqlCommonDkSni_10; "sql\\common\\dk\\sni\\src\\transport.cp"...
0x100459c65  mov     [rsp+288h+var_240], rdi
0x100459c6a  lea     rsi, aSniDetailTrans_8; "SNI::detail::Transport::StaticInitializ"...
0x100459c71  mov     [rsp+288h+var_238], rsi
0x100459c76  mov     [rsp+288h+var_230], 3Ch ; '<'
0x100459c7e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100459c85  jz      short loc_100459C9F
0x100459c87  lea     r9, aApiSni_0; "API|SNI\n"
0x100459c8e  mov     r8d, 3Ch ; '<'; int
0x100459c94  mov     rdx, rsi; char *
0x100459c97  mov     rcx, rdi; char *
0x100459c9a  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100459c9f  xor     ebx, ebx
0x100459ca1  mov     eax, cs:?s_dwRefCount@Transport@detail@SNI@@0KA; ulong SNI::detail::Transport::s_dwRefCount
0x100459ca7  inc     eax
0x100459ca9  mov     cs:?s_dwRefCount@Transport@detail@SNI@@0KA, eax; ulong SNI::detail::Transport::s_dwRefCount
0x100459caf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100459cb6  jz      short loc_100459CD8
0x100459cb8  mov     dword ptr [rsp+288h+var_268], eax
0x100459cbc  lea     r9, aSnitransportRe; "SNITransport ref-count: %d.\n"
0x100459cc3  lea     r8d, [rbx+42h]; int
0x100459cc7  mov     rdx, rsi; char *
0x100459cca  mov     rcx, rdi; char *
0x100459ccd  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100459cd2  mov     eax, cs:?s_dwRefCount@Transport@detail@SNI@@0KA; ulong SNI::detail::Transport::s_dwRefCount
0x100459cd8  cmp     eax, 1
0x100459cdb  jnz     loc_100459E1B
0x100459ce1  mov     ecx, 105h
0x100459ce6  lea     rax, aKernel32Dll_0; "kernel32.dll"
0x100459ced  nop     dword ptr [rax]
0x100459cf0  cmp     [rax], bl
0x100459cf2  jz      short loc_100459D16
0x100459cf4  inc     rax
0x100459cf7  sub     rcx, 1
0x100459cfb  jnz     short loc_100459CF0
0x100459cfd  test    rcx, rcx
0x100459d00  jnz     short loc_100459D16
0x100459d02  mov     ecx, 7Bh ; '{'; dwErrCode
0x100459d07  call    cs:__imp_SetLastError
0x100459d0d  mov     cs:?s_hKernel32@Transport@detail@SNI@@0PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * SNI::detail::Transport::s_hKernel32
0x100459d14  jmp     short loc_100459D59
0x100459d16  mov     dword ptr [rsp+288h+var_268], 105h
0x100459d1e  lea     r9, [rsp+288h+var_228]
0x100459d23  mov     r8d, 0FFFFFFFFh
0x100459d29  lea     rdx, aKernel32Dll_0; "kernel32.dll"
0x100459d30  xor     ecx, ecx
0x100459d32  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x100459d38  xor     r9d, r9d
0x100459d3b  xor     r8d, r8d
0x100459d3e  lea     edx, [r9+1]
0x100459d42  lea     rcx, [rsp+288h+var_228]
0x100459d47  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x100459d4d  mov     cs:?s_hKernel32@Transport@detail@SNI@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * SNI::detail::Transport::s_hKernel32
0x100459d54  test    rax, rax
0x100459d57  jnz     short loc_100459D88
0x100459d59  call    cs:__imp_GetLastError
0x100459d5f  mov     ebx, eax
0x100459d61  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100459d68  jz      short loc_100459DCF
0x100459d6a  mov     dword ptr [rsp+288h+var_268], eax
0x100459d6e  lea     r9, aErrSniloadlibr_0; "ERR|SNILoadLibrary for Kernel32 failed:"...
0x100459d75  mov     r8d, 5Fh ; '_'; int
0x100459d7b  mov     rdx, rsi; char *
0x100459d7e  mov     rcx, rdi; char *
0x100459d81  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100459d86  jmp     short loc_100459DCF
0x100459d88  lea     rdx, aSetfilecomplet; "SetFileCompletionNotificationModes"
0x100459d8f  mov     rcx, rax; hModule
0x100459d92  call    cs:__imp_GetProcAddress
0x100459d98  mov     cs:?s_pfnWin32SetFileCompletionNotificationModes@Transport@detail@SNI@@0P6AHPEAXE@ZEA, rax; int (*SNI::detail::Transport::s_pfnWin32SetFileCompletionNotificationModes)(void *,uchar)
0x100459d9f  test    rax, rax
0x100459da2  jnz     short loc_100459E1B
0x100459da4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100459dab  jz      short loc_100459DC7
0x100459dad  mov     dword ptr [rsp+288h+var_268], ebx
0x100459db1  lea     r9, aErrSnigetproca_0; "ERR|SNIGetProcAddress for SetFileComple"...
0x100459db8  lea     r8d, [rax+6Ch]; int
0x100459dbc  mov     rdx, rsi; char *
0x100459dbf  mov     rcx, rdi; char *
0x100459dc2  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100459dc7  call    cs:__imp_GetLastError
0x100459dcd  mov     ebx, eax
0x100459dcf  call    ?StaticTerminate@Transport@detail@SNI@@SAXXZ; SNI::detail::Transport::StaticTerminate(void)
0x100459dd4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100459ddb  jz      short loc_100459E09
0x100459ddd  mov     [rsp+288h+var_258], ebx
0x100459de1  mov     [rsp+288h+var_260], 0
0x100459de9  mov     dword ptr [rsp+288h+var_268], 0Ah
0x100459df1  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100459df8  mov     r8d, 7Dh ; '}'; int
0x100459dfe  mov     rdx, rsi; char *
0x100459e01  mov     rcx, rdi; char *
0x100459e04  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100459e09  mov     r8d, 0C3B4h
0x100459e0f  mov     edx, ebx
0x100459e11  mov     ecx, 0Ah
0x100459e16  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100459e1b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100459e22  jz      short loc_100459E41
0x100459e24  mov     dword ptr [rsp+288h+var_268], ebx
0x100459e28  lea     r9, aRetSniDBool; "RET|SNI%d{BOOL}\n"
0x100459e2f  mov     r8d, 80h; int
0x100459e35  mov     rdx, rsi; char *
0x100459e38  mov     rcx, rdi; char *
0x100459e3b  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100459e40  nop
0x100459e41  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100459e48  jz      short loc_100459E5B
0x100459e4a  mov     r8d, 3Ch ; '<'; int
0x100459e50  mov     rdx, rsi; char *
0x100459e53  mov     rcx, rdi; char *
0x100459e56  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100459e5b  mov     eax, ebx
0x100459e5d  mov     rcx, [rsp+288h+var_18]
0x100459e65  xor     rcx, rsp; StackCookie
0x100459e68  call    __security_check_cookie
0x100459e6d  lea     r11, [rsp+288h+var_8]
0x100459e75  mov     rbx, [r11+10h]
0x100459e79  mov     rsi, [r11+18h]
0x100459e7d  mov     rsp, r11
0x100459e80  pop     rdi
0x100459e81  retn
```
