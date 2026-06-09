# LoadWSAPoll(int (**)(pollfd * const,ulong,int),HINSTANCE__ * *)

- ea: `0x100435240`
- end: `0x100435527`
- name: `?LoadWSAPoll@@YAKPEAP6AHQEAUpollfd@@KH@ZPEAPEAUHINSTANCE__@@@Z`
- size: `743`
- prototype: `unsigned int __fastcall(int (**)(struct pollfd *const, unsigned int, int), HINSTANCE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100438340`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100435240`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x100435305`
- `KERNEL32!LoadLibraryExA` at `0x100435305`
- `KERNEL32!FreeLibrary` at `0x10043547d`
- `KERNEL32!FreeLibrary` at `0x10043547d`
- `KERNEL32!SetLastError` at `0x10043536c`
- `KERNEL32!SetLastError` at `0x10043536c`
- `KERNEL32!GetProcAddress` at `0x1004353e9`
- `KERNEL32!GetProcAddress` at `0x1004353e9`
- `KERNEL32!GetLastError` at `0x100435313`
- `KERNEL32!GetLastError` at `0x100435395`
- `KERNEL32!GetLastError` at `0x1004353fb`
- `KERNEL32!GetLastError` at `0x100435487`
- `KERNEL32!GetLastError` at `0x100435313`
- `KERNEL32!GetLastError` at `0x100435395`
- `KERNEL32!GetLastError` at `0x1004353fb`
- `KERNEL32!GetLastError` at `0x100435487`

## string_xrefs

- `0x1004352ab`: `sql\common\dk\sni\src\sni.cpp`
- `0x1004352e0`: `API|SNIszDllFileName: '%hs'\n`
- `0x100435328`: `ERR|SNILoadLibrary: %d{WINERR}\n`
- `0x10043526d`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004353b0`: `ERR|SNISNILoadSystemLibA for WS2_32.dll failed: %d{WINERR}.\n`
- `0x1004352cb`: `ws2_32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LoadWSAPoll(int (**a1)(struct pollfd *const, unsigned int, int), HINSTANCE *a2)
{
  DWORD v4; // edi
  HMODULE Library; // rbx
  const wchar_t *v6; // r9
  DWORD LastError; // eax
  DWORD v8; // eax
  DWORD v9; // ebx
  int v10; // r8d
  int (*ProcAddress)(struct pollfd *const, unsigned int, int); // rax
  const wchar_t *v12; // r9
  DWORD v13; // eax
  __int64 v15; // [rsp+20h] [rbp-88h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "LoadWSAPoll", 1943, L"API|SNI");
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNILoadSystemLibA",
      8200,
      L"API|SNIszDllFileName: '%hs'\n",
      "ws2_32.dll");
  v4 = 0;
  Library = LoadLibraryExA("ws2_32.dll", 0, 0x800u);
  if ( !Library )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v15) = LastError;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNILoadSystemLibA",
        8215,
        L"ERR|SNILoadLibrary: %d{WINERR}\n",
        v15);
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNILoadSystemLibA",
      8221,
      L"RET|SNI%p{HMODULE}\n",
      Library);
  if ( v4 )
    SetLastError(v4);
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNILoadSystemLibA", 8200, v6);
  *a2 = Library;
  if ( Library )
  {
    ProcAddress = (int (*)(struct pollfd *const, unsigned int, int))GetProcAddress(Library, "WSAPoll");
    *a1 = ProcAddress;
    if ( ProcAddress )
    {
      v9 = 0;
      goto LABEL_30;
    }
    v9 = GetLastError();
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v15) = v9;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\tcp.cpp",
        "LoadWSAPoll",
        1959,
        L"ERR|SNIGetProcAddress for WSAPoll failed: %d{WINERR}.\n",
        v15);
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        v10 = 1960;
        goto LABEL_22;
      }
    }
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v15) = v8;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\tcp.cpp",
        "LoadWSAPoll",
        1950,
        L"ERR|SNISNILoadSystemLibA for WS2_32.dll failed: %d{WINERR}.\n",
        v15);
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        v10 = 1951;
LABEL_22:
        LODWORD(v15) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "LoadWSAPoll",
          v10,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v15,
          0,
          v9);
      }
    }
  }
  SNISetLastError(7u, v9, 0xC3B4u);
  if ( v9 && *a2 )
  {
    if ( !FreeLibrary(*a2) )
    {
      v13 = GetLastError();
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v15) = v13;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "LoadWSAPoll",
          1972,
          L"ERR|SNIFreeLibrary for ws2_32 failed: %d{WINERR}.\n",
          v15);
      }
    }
    *a2 = 0;
    *a1 = 0;
  }
LABEL_30:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v15) = v9;
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "LoadWSAPoll", 1977, L"RET|SNI%d{WINERR}\n", v15);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "LoadWSAPoll", 1943, v12);
  return v9;
}

```

## disassembly

```asm
0x100435240  mov     rax, rsp
0x100435243  push    rdi
0x100435244  push    r12
0x100435246  push    r13
0x100435248  push    r14
0x10043524a  push    r15
0x10043524c  sub     rsp, 80h
0x100435253  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x10043525b  mov     [rax+8], rbx
0x10043525f  mov     [rax+10h], rbp
0x100435263  mov     [rax+18h], rsi
0x100435267  mov     rsi, rdx
0x10043526a  mov     r14, rcx
0x10043526d  lea     rbp, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100435274  mov     [rax-60h], rbp
0x100435278  lea     r15, aLoadwsapoll; "LoadWSAPoll"
0x10043527f  mov     [rax-58h], r15
0x100435283  mov     dword ptr [rax-50h], 797h
0x10043528a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435291  jz      short loc_1004352AB
0x100435293  lea     r9, aApiSni; "API|SNI"
0x10043529a  mov     r8d, 797h; int
0x1004352a0  mov     rdx, r15; char *
0x1004352a3  mov     rcx, rbp; char *
0x1004352a6  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004352ab  lea     r12, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x1004352b2  mov     [rsp+0A8h+var_48], r12
0x1004352b7  lea     r13, aSniloadsysteml; "SNILoadSystemLibA"
0x1004352be  mov     [rsp+0A8h+var_40], r13
0x1004352c3  mov     [rsp+0A8h+var_38], 2008h
0x1004352cb  lea     rbx, aWs232Dll_0; "ws2_32.dll"
0x1004352d2  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004352d9  jz      short loc_1004352F8
0x1004352db  mov     [rsp+0A8h+var_88], rbx
0x1004352e0  lea     r9, aApiSniszdllfil; "API|SNIszDllFileName: '%hs'\n"
0x1004352e7  mov     r8d, 2008h; int
0x1004352ed  mov     rdx, r13; char *
0x1004352f0  mov     rcx, r12; char *
0x1004352f3  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004352f8  xor     edi, edi
0x1004352fa  xor     edx, edx; hFile
0x1004352fc  mov     r8d, 800h; dwFlags
0x100435302  mov     rcx, rbx; lpLibFileName
0x100435305  call    cs:__imp_LoadLibraryExA
0x10043530b  mov     rbx, rax
0x10043530e  test    rax, rax
0x100435311  jnz     short loc_100435340
0x100435313  call    cs:__imp_GetLastError
0x100435319  mov     edi, eax
0x10043531b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435322  jz      short loc_100435340
0x100435324  mov     dword ptr [rsp+0A8h+var_88], eax
0x100435328  lea     r9, aErrSniloadlibr; "ERR|SNILoadLibrary: %d{WINERR}\n"
0x10043532f  mov     r8d, 2017h; int
0x100435335  mov     rdx, r13; char *
0x100435338  mov     rcx, r12; char *
0x10043533b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100435340  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435347  jz      short loc_100435366
0x100435349  mov     [rsp+0A8h+var_88], rbx
0x10043534e  lea     r9, aRetSniPHmodule; "RET|SNI%p{HMODULE}\n"
0x100435355  mov     r8d, 201Dh; int
0x10043535b  mov     rdx, r13; char *
0x10043535e  mov     rcx, r12; char *
0x100435361  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100435366  test    edi, edi
0x100435368  jz      short loc_100435373
0x10043536a  mov     ecx, edi; dwErrCode
0x10043536c  call    cs:__imp_SetLastError
0x100435372  nop
0x100435373  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043537a  jz      short loc_10043538D
0x10043537c  mov     r8d, 2008h; int
0x100435382  mov     rdx, r13; char *
0x100435385  mov     rcx, r12; char *
0x100435388  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043538d  mov     [rsi], rbx
0x100435390  test    rbx, rbx
0x100435393  jnz     short loc_1004353DF
0x100435395  call    cs:__imp_GetLastError
0x10043539b  mov     ebx, eax
0x10043539d  mov     ecx, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004353a3  test    cl, 2
0x1004353a6  jz      loc_10043545F
0x1004353ac  mov     dword ptr [rsp+0A8h+var_88], eax
0x1004353b0  lea     r9, aErrSnisniloads; "ERR|SNISNILoadSystemLibA for WS2_32.dll"...
0x1004353b7  mov     r8d, 79Eh; int
0x1004353bd  mov     rdx, r15; char *
0x1004353c0  mov     rcx, rbp; char *
0x1004353c3  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004353c8  mov     ecx, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004353ce  test    cl, 2
0x1004353d1  jz      loc_10043545F
0x1004353d7  mov     r8d, 79Fh
0x1004353dd  jmp     short loc_100435439
0x1004353df  lea     rdx, aWsapoll; "WSAPoll"
0x1004353e6  mov     rcx, rbx; hModule
0x1004353e9  call    cs:__imp_GetProcAddress
0x1004353ef  mov     [r14], rax
0x1004353f2  test    rax, rax
0x1004353f5  jnz     loc_1004354C2
0x1004353fb  call    cs:__imp_GetLastError
0x100435401  mov     ebx, eax
0x100435403  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435409  test    al, 2
0x10043540b  jz      short loc_10043545F
0x10043540d  mov     dword ptr [rsp+0A8h+var_88], ebx
0x100435411  lea     r9, aErrSnigetproca; "ERR|SNIGetProcAddress for WSAPoll faile"...
0x100435418  mov     r8d, 7A7h; int
0x10043541e  mov     rdx, r15; char *
0x100435421  mov     rcx, rbp; char *
0x100435424  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100435429  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043542f  test    al, 2
0x100435431  jz      short loc_10043545F
0x100435433  mov     r8d, 7A8h; int
0x100435439  mov     [rsp+0A8h+var_78], ebx
0x10043543d  mov     [rsp+0A8h+var_80], 0
0x100435445  mov     dword ptr [rsp+0A8h+var_88], 7
0x10043544d  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100435454  mov     rdx, r15; char *
0x100435457  mov     rcx, rbp; char *
0x10043545a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043545f  mov     r8d, 0C3B4h
0x100435465  mov     edx, ebx
0x100435467  mov     ecx, 7
0x10043546c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100435471  test    ebx, ebx
0x100435473  jz      short loc_1004354C4
0x100435475  mov     rcx, [rsi]; hLibModule
0x100435478  test    rcx, rcx
0x10043547b  jz      short loc_1004354C4
0x10043547d  call    cs:__imp_FreeLibrary
0x100435483  test    eax, eax
0x100435485  jnz     short loc_1004354B2
0x100435487  call    cs:__imp_GetLastError
0x10043548d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100435494  jz      short loc_1004354B2
0x100435496  mov     dword ptr [rsp+0A8h+var_88], eax
0x10043549a  lea     r9, aErrSnifreelibr; "ERR|SNIFreeLibrary for ws2_32 failed: %"...
0x1004354a1  mov     r8d, 7B4h; int
0x1004354a7  mov     rdx, r15; char *
0x1004354aa  mov     rcx, rbp; char *
0x1004354ad  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004354b2  mov     qword ptr [rsi], 0
0x1004354b9  mov     qword ptr [r14], 0
0x1004354c0  jmp     short loc_1004354C4
0x1004354c2  xor     ebx, ebx
0x1004354c4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004354cb  jz      short loc_1004354EA
0x1004354cd  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1004354d1  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004354d8  mov     r8d, 7B9h; int
0x1004354de  mov     rdx, r15; char *
0x1004354e1  mov     rcx, rbp; char *
0x1004354e4  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004354e9  nop
0x1004354ea  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004354f1  jz      short loc_100435504
0x1004354f3  mov     r8d, 797h; int
0x1004354f9  mov     rdx, r15; char *
0x1004354fc  mov     rcx, rbp; char *
0x1004354ff  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100435504  mov     eax, ebx
0x100435506  lea     r11, [rsp+0A8h+var_28]
0x10043550e  mov     rbx, [r11+30h]
0x100435512  mov     rbp, [r11+38h]
0x100435516  mov     rsi, [r11+40h]
0x10043551a  mov     rsp, r11
0x10043551d  pop     r15
0x10043551f  pop     r14
0x100435521  pop     r13
0x100435523  pop     r12
0x100435525  pop     rdi
0x100435526  retn
```
