# CTpUtils::GetXblSandboxId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800394d4`
- end: `0x1800396b3`
- name: `?GetXblSandboxId@CTpUtils@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022e44`

## callees

- `0x180008e38`
- `0x18000cf50`
- `0x18000d40c`
- `0x18000da00`
- `0x18000db80`
- `0x1800394d4`
- `0x180039760`
- `0x180040bfc`
- `0x180053300`
- `0x180053d3c`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003953b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003953b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039591`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039591`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180039516`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180039516`

## string_xrefs

- `0x180039534`: `XboxLiveTitleId.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTpUtils::GetXblSandboxId(void *a1)
{
  HMODULE Library; // rax
  signed int String; // ebx
  FARPROC ProcAddress; // rbx
  int v5; // eax
  HMODULE v7; // [rsp+40h] [rbp-59h] BYREF
  __int64 v8; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v9[56]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v10[24]; // [rsp+A8h] [rbp+Fh] BYREF
  wchar_t v11[8]; // [rsp+C0h] [rbp+27h] BYREF
  __int128 v12; // [rsp+D0h] [rbp+37h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v8);
  LODWORD(v7) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v7, 0);
  if ( (_DWORD)v7 == 5 )
  {
    Library = LoadLibraryExW(L"XboxLiveTitleId.dll", 0, 0x800u);
    v7 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetSystemXboxLiveInfo");
      if ( ProcAddress )
      {
        memset_0(v9, 0, 0x48u);
        v5 = ((__int64 (__fastcall *)(__int64, _BYTE *))ProcAddress)(1, v9);
        String = v5;
        if ( v5 )
        {
          if ( v5 > 0 )
            String = (unsigned __int16)v5 | 0x80070000;
        }
        else
        {
          String = 0;
          *(_OWORD *)v11 = 0;
          v12 = 0;
          StringCchPrintfW(v11, 0x10u, L"%S", v10);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&v8, v11);
        }
      }
      else
      {
        String = -2147467263;
      }
    }
    else
    {
      String = UtilRegGetString(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\GameCore", L"SandboxId", (__int64)&v8, 0, 1);
    }
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v7);
  }
  else
  {
    String = UtilRegGetString(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\XboxLive", L"Sandbox", (__int64)&v8, 0, 1);
    if ( String < 0 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&v8, L"RETAIL");
      String = 0;
    }
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1, (void *)v8);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v8);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800394d4  mov     [rsp-8+arg_8], rbx
0x1800394d9  mov     [rsp-8+arg_10], rdi
0x1800394de  push    rbp
0x1800394df  lea     rbp, [rsp-57h]
0x1800394e4  sub     rsp, 0F0h
0x1800394eb  mov     rax, cs:__security_cookie
0x1800394f2  xor     rax, rsp
0x1800394f5  mov     [rbp+57h+var_10], rax
0x1800394f9  mov     rdi, rcx
0x1800394fc  lea     rcx, [rbp+57h+var_A8]; void *
0x180039500  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180039505  nop
0x180039506  mov     dword ptr [rbp+57h+var_B0], 0
0x18003950d  xor     r8d, r8d
0x180039510  lea     rdx, [rbp+57h+var_B0]
0x180039514  xor     ecx, ecx
0x180039516  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18003951d  nop     dword ptr [rax+rax+00h]
0x180039522  cmp     dword ptr [rbp+57h+var_B0], 5
0x180039526  jnz     loc_180039623
0x18003952c  xor     edx, edx; hFile
0x18003952e  mov     r8d, 800h; dwFlags
0x180039534  lea     rcx, aXboxlivetitlei; "XboxLiveTitleId.dll"
0x18003953b  call    cs:__imp_LoadLibraryExW
0x180039542  nop     dword ptr [rax+rax+00h]
0x180039547  mov     [rbp+57h+var_B0], rax
0x18003954b  test    rax, rax
0x18003954e  jnz     short loc_180039587
0x180039550  mov     [rsp+0F0h+var_C0], 1; char
0x180039555  mov     [rsp+0F0h+var_C8], al; char
0x180039559  lea     rax, [rbp+57h+var_A8]
0x18003955d  mov     [rsp+0F0h+var_D0], rax; __int64
0x180039562  lea     r9, aRetail; "RETAIL"
0x180039569  lea     r8, aSandboxid; "SandboxId"
0x180039570  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\GameCore"
0x180039577  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003957e  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180039583  mov     ebx, eax
0x180039585  jmp     short loc_1800395AA
0x180039587  lea     rdx, aGetsystemxboxl; "GetSystemXboxLiveInfo"
0x18003958e  mov     rcx, rax; hModule
0x180039591  call    cs:__imp_GetProcAddress
0x180039598  nop     dword ptr [rax+rax+00h]
0x18003959d  mov     rbx, rax
0x1800395a0  test    rax, rax
0x1800395a3  jnz     short loc_1800395B8
0x1800395a5  mov     ebx, 80004001h
0x1800395aa  lea     rcx, [rbp+57h+var_B0]
0x1800395ae  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x1800395b3  jmp     loc_18003966F
0x1800395b8  xor     edx, edx; Val
0x1800395ba  lea     r8d, [rdx+48h]; Size
0x1800395be  lea     rcx, [rbp+57h+var_80]; void *
0x1800395c2  call    memset_0
0x1800395c7  mov     r8d, 48h ; 'H'
0x1800395cd  lea     rdx, [rbp+57h+var_80]
0x1800395d1  lea     ecx, [r8-47h]
0x1800395d5  mov     rax, rbx
0x1800395d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395dd  mov     ebx, eax
0x1800395df  test    eax, eax
0x1800395e1  jz      short loc_1800395F0
0x1800395e3  jle     short loc_1800395AA
0x1800395e5  movzx   ebx, ax
0x1800395e8  or      ebx, 80070000h
0x1800395ee  jmp     short loc_1800395AA
0x1800395f0  xor     ebx, ebx
0x1800395f2  xorps   xmm0, xmm0
0x1800395f5  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x1800395f9  movups  [rbp+57h+var_20], xmm0
0x1800395fd  lea     r9, [rbp+57h+var_48]
0x180039601  lea     r8, aS_2; "%S"
0x180039608  lea     edx, [rbx+10h]; unsigned __int64
0x18003960b  lea     rcx, [rbp+57h+var_30]; wchar_t *
0x18003960f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180039614  lea     rdx, [rbp+57h+var_30]
0x180039618  lea     rcx, [rbp+57h+var_A8]
0x18003961c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180039621  jmp     short loc_1800395AA
0x180039623  mov     [rsp+0F0h+var_C0], 1; char
0x180039628  mov     [rsp+0F0h+var_C8], 0; char
0x18003962d  lea     rax, [rbp+57h+var_A8]
0x180039631  mov     [rsp+0F0h+var_D0], rax; __int64
0x180039636  lea     r9, aRetail; "RETAIL"
0x18003963d  lea     r8, aSandbox; "Sandbox"
0x180039644  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\XboxLive"
0x18003964b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180039652  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180039657  mov     ebx, eax
0x180039659  test    eax, eax
0x18003965b  jns     short loc_18003966F
0x18003965d  lea     rdx, aRetail; "RETAIL"
0x180039664  lea     rcx, [rbp+57h+var_A8]
0x180039668  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18003966d  xor     ebx, ebx
0x18003966f  mov     r8, [rbp+57h+var_A0]
0x180039673  mov     rdx, [rbp+57h+var_A8]
0x180039677  sub     r8, rdx
0x18003967a  sar     r8, 1
0x18003967d  mov     rcx, rdi
0x180039680  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180039685  nop
0x180039686  lea     rcx, [rbp+57h+var_A8]; void *
0x18003968a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003968f  mov     eax, ebx
0x180039691  mov     rcx, [rbp+57h+var_10]
0x180039695  xor     rcx, rsp; StackCookie
0x180039698  call    __security_check_cookie
0x18003969d  lea     r11, [rsp+0F0h+var_s0]
0x1800396a5  mov     rbx, [r11+18h]
0x1800396a9  mov     rdi, [r11+20h]
0x1800396ad  mov     rsp, r11
0x1800396b0  pop     rbp
0x1800396b1  retn
```
