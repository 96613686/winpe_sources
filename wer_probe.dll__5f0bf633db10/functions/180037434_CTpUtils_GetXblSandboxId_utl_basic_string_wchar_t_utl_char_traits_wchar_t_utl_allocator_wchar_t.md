# CTpUtils::GetXblSandboxId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180037434`
- end: `0x180037600`
- name: `?GetXblSandboxId@CTpUtils@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800222c4`

## callees

- `0x180008174`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000c390`
- `0x18000dad0`
- `0x180037434`
- `0x1800376a8`
- `0x18003ec1c`
- `0x180050db0`
- `0x1800517cc`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037495`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037495`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800374e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800374e5`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180037476`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180037476`

## string_xrefs

- `0x18003748e`: `XboxLiveTitleId.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTpUtils::GetXblSandboxId(__int64 a1)
{
  HMODULE Library; // rax
  signed int String; // ebx
  FARPROC ProcAddress; // rbx
  int v5; // eax
  HMODULE v7; // [rsp+40h] [rbp-59h] BYREF
  __int64 v8[5]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v9[56]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v10[24]; // [rsp+A8h] [rbp+Fh] BYREF
  wchar_t v11[8]; // [rsp+C0h] [rbp+27h] BYREF
  __int128 v12; // [rsp+D0h] [rbp+37h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v8);
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
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v8);
        }
      }
      else
      {
        String = -2147467263;
      }
    }
    else
    {
      String = UtilRegGetString(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\GameCore", L"SandboxId", (__int64)v8, 0, 1);
    }
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v7);
  }
  else
  {
    String = UtilRegGetString(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\XboxLive", L"Sandbox", (__int64)v8, 0, 1);
    if ( String < 0 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v8);
      String = 0;
    }
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1, v8[0], (v8[1] - v8[0]) >> 1);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v8);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180037434  mov     [rsp-8+arg_8], rbx
0x180037439  mov     [rsp-8+arg_10], rdi
0x18003743e  push    rbp
0x18003743f  lea     rbp, [rsp-57h]
0x180037444  sub     rsp, 0F0h
0x18003744b  mov     rax, cs:__security_cookie
0x180037452  xor     rax, rsp
0x180037455  mov     [rbp+57h+var_10], rax
0x180037459  mov     rdi, rcx
0x18003745c  lea     rcx, [rbp+57h+var_A8]; void *
0x180037460  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180037465  nop
0x180037466  mov     dword ptr [rbp+57h+var_B0], 0
0x18003746d  xor     r8d, r8d
0x180037470  lea     rdx, [rbp+57h+var_B0]
0x180037474  xor     ecx, ecx
0x180037476  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18003747c  cmp     dword ptr [rbp+57h+var_B0], 5
0x180037480  jnz     loc_180037571
0x180037486  xor     edx, edx; hFile
0x180037488  mov     r8d, 800h; dwFlags
0x18003748e  lea     rcx, aXboxlivetitlei; "XboxLiveTitleId.dll"
0x180037495  call    cs:__imp_LoadLibraryExW
0x18003749b  mov     [rbp+57h+var_B0], rax
0x18003749f  test    rax, rax
0x1800374a2  jnz     short loc_1800374DB
0x1800374a4  mov     [rsp+0F0h+var_C0], 1; char
0x1800374a9  mov     [rsp+0F0h+var_C8], al; char
0x1800374ad  lea     rax, [rbp+57h+var_A8]
0x1800374b1  mov     [rsp+0F0h+var_D0], rax; __int64
0x1800374b6  lea     r9, aRetail; "RETAIL"
0x1800374bd  lea     r8, aSandboxid; "SandboxId"
0x1800374c4  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\GameCore"
0x1800374cb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800374d2  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800374d7  mov     ebx, eax
0x1800374d9  jmp     short loc_1800374F8
0x1800374db  lea     rdx, aGetsystemxboxl; "GetSystemXboxLiveInfo"
0x1800374e2  mov     rcx, rax; hModule
0x1800374e5  call    cs:__imp_GetProcAddress
0x1800374eb  mov     rbx, rax
0x1800374ee  test    rax, rax
0x1800374f1  jnz     short loc_180037506
0x1800374f3  mov     ebx, 80004001h
0x1800374f8  lea     rcx, [rbp+57h+var_B0]
0x1800374fc  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x180037501  jmp     loc_1800375BD
0x180037506  xor     edx, edx; Val
0x180037508  lea     r8d, [rdx+48h]; Size
0x18003750c  lea     rcx, [rbp+57h+var_80]; void *
0x180037510  call    memset_0
0x180037515  mov     r8d, 48h ; 'H'
0x18003751b  lea     rdx, [rbp+57h+var_80]
0x18003751f  lea     ecx, [r8-47h]
0x180037523  mov     rax, rbx
0x180037526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003752b  mov     ebx, eax
0x18003752d  test    eax, eax
0x18003752f  jz      short loc_18003753E
0x180037531  jle     short loc_1800374F8
0x180037533  movzx   ebx, ax
0x180037536  or      ebx, 80070000h
0x18003753c  jmp     short loc_1800374F8
0x18003753e  xor     ebx, ebx
0x180037540  xorps   xmm0, xmm0
0x180037543  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x180037547  movups  [rbp+57h+var_20], xmm0
0x18003754b  lea     r9, [rbp+57h+var_48]
0x18003754f  lea     r8, aS_2; "%S"
0x180037556  lea     edx, [rbx+10h]; unsigned __int64
0x180037559  lea     rcx, [rbp+57h+var_30]; wchar_t *
0x18003755d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180037562  lea     rdx, [rbp+57h+var_30]
0x180037566  lea     rcx, [rbp+57h+var_A8]
0x18003756a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18003756f  jmp     short loc_1800374F8
0x180037571  mov     [rsp+0F0h+var_C0], 1; char
0x180037576  mov     [rsp+0F0h+var_C8], 0; char
0x18003757b  lea     rax, [rbp+57h+var_A8]
0x18003757f  mov     [rsp+0F0h+var_D0], rax; __int64
0x180037584  lea     r9, aRetail; "RETAIL"
0x18003758b  lea     r8, aSandbox; "Sandbox"
0x180037592  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\XboxLive"
0x180037599  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800375a0  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800375a5  mov     ebx, eax
0x1800375a7  test    eax, eax
0x1800375a9  jns     short loc_1800375BD
0x1800375ab  lea     rdx, aRetail; "RETAIL"
0x1800375b2  lea     rcx, [rbp+57h+var_A8]
0x1800375b6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800375bb  xor     ebx, ebx
0x1800375bd  mov     r8, [rbp+57h+var_A0]
0x1800375c1  mov     rdx, [rbp+57h+var_A8]
0x1800375c5  sub     r8, rdx
0x1800375c8  sar     r8, 1
0x1800375cb  mov     rcx, rdi
0x1800375ce  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800375d3  nop
0x1800375d4  lea     rcx, [rbp+57h+var_A8]; void *
0x1800375d8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800375dd  mov     eax, ebx
0x1800375df  mov     rcx, [rbp+57h+var_10]
0x1800375e3  xor     rcx, rsp; StackCookie
0x1800375e6  call    __security_check_cookie
0x1800375eb  lea     r11, [rsp+0F0h+var_s0]
0x1800375f3  mov     rbx, [r11+18h]
0x1800375f7  mov     rdi, [r11+20h]
0x1800375fb  mov     rsp, r11
0x1800375fe  pop     rbp
0x1800375ff  retn
```
