# RestoreSystemPolicies

- ea: `0x14000fcb8`
- end: `0x14000fef4`
- name: `RestoreSystemPolicies`
- size: `572`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001a54c`

## callees

- `0x140004348`
- `0x1400085b4`
- `0x14000fcb8`
- `0x140011fd0`
- `0x140017af0`
- `0x14003ea9c`
- `0x14003eb10`
- `0x14003ec14`
- `0x1400530a8`
- `0x14008be98`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000fdf8`
- `KERNEL32!GetProcAddress` at `0x14000fdf8`
- `KERNEL32!LoadLibraryW` at `0x14000fde5`
- `KERNEL32!LoadLibraryW` at `0x14000fde5`
- `KERNEL32!GetLastError` at `0x14000fd48`
- `KERNEL32!GetLastError` at `0x14000fe03`
- `KERNEL32!GetLastError` at `0x14000fd48`
- `KERNEL32!GetLastError` at `0x14000fe03`
- `KERNEL32!SetLastError` at `0x14000fe0e`
- `KERNEL32!SetLastError` at `0x14000fe0e`
- `ntdll!NtClose` at `0x14000fd31`
- `ntdll!NtClose` at `0x14000fd31`
- `ntdll!RtlNtStatusToDosError` at `0x14000fd22`
- `ntdll!RtlNtStatusToDosError` at `0x14000fd22`

## string_xrefs

- `0x14000fdde`: `dwmapi.dll`
- `0x14000fd0c`: `ERROR: Could not disable cache hits: %x\n`
- `0x14000fd9c`: `> Not necessary to reenable EMD cache.`
- `0x14000fe6d`: `Warning: Composition Restart not supported`
- `0x14000fe96`: `Warning: Composition Restart not supported`
- `0x14000fea7`: `> Composition restarted`
- `0x14000fed4`: `> Composition restarted`
- `0x14000fe14`: `INFO: DwmpRestartComposition() did not return OK!`

## pseudocode

```c
__int64 RestoreSystemPolicies()
{
  __int64 v0; // rcx
  int v1; // eax
  NTSTATUS v2; // edi
  ULONG v3; // eax
  HMODULE LibraryW; // rax
  __int64 (*ProcAddress)(void); // rax
  int v7; // eax
  __int64 v8; // rax
  const wchar_t *v9; // rdx
  __int64 *v10; // rax
  WCHAR Buffer[256]; // [rsp+20h] [rbp-228h] BYREF
  DWORD LastError; // [rsp+220h] [rbp-28h]
  char v13; // [rsp+224h] [rbp-24h]
  __int64 v14; // [rsp+228h] [rbp-20h]

  LogEnterPhase(140, L"Restore system policies");
  if ( byte_1401C1258 )
  {
    v1 = SmuCacheHitsControl(v0, 0);
    v2 = v1;
    if ( v1 >= 0 )
    {
      NtClose(s_EMDControlHandle);
      v3 = 0;
      s_EMDControlHandle = 0;
    }
    else
    {
      Log_Text_F("base\\winsat\\exe\\main.cpp", 2437, "ERROR: Could not disable cache hits: %x\n", v1);
      v3 = RtlNtStatusToDosError(v2);
    }
    if ( v3 )
    {
      v13 = 1;
      LastError = GetLastError();
      v14 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      Log_Text_F("base\\winsat\\exe\\main.cpp", 2762, "> Unable to reenable EMD device; %s", (const char *)Buffer);
    }
    else
    {
      Log_Text_F("base\\winsat\\exe\\main.cpp", 2764, "> Successfully reenabled EMD.");
    }
  }
  else
  {
    Log_Text_F("base\\winsat\\exe\\main.cpp", 2767, "> Not necessary to reenable EMD cache.");
  }
  if ( byte_1401C1249 )
  {
    byte_1401C1249 = 0;
    SetWinsatRegKeyULONGLONG(L"CKCLStart");
  }
  if ( byte_1401C1248 )
  {
    LibraryW = LoadLibraryW(L"dwmapi.dll");
    if ( !LibraryW || (ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x67)) == 0 )
    {
      GetLastError();
      SetLastError(0x32u);
LABEL_15:
      Log_Text_F("base\\winsat\\exe\\main.cpp", 2793, "INFO: DwmpRestartComposition() did not return OK!");
      return LogLeavePhase();
    }
    v7 = ProcAddress();
    if ( v7 == 50 )
    {
      if ( !*(_BYTE *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&theKeyInfo)
                     + 490) )
        goto LABEL_15;
      Log_Text_F("base\\winsat\\exe\\main.cpp", 2786, "Warning: Composition Restart not supported");
      if ( !App::s_Verbose )
        return LogLeavePhase();
      v8 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
      v9 = L"Warning: Composition Restart not supported";
    }
    else
    {
      if ( v7 )
        goto LABEL_15;
      Log_Text_F("base\\winsat\\exe\\main.cpp", 2790, "> Composition restarted");
      if ( !App::s_Verbose )
        return LogLeavePhase();
      v8 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
      v9 = L"> Composition restarted";
    }
    v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v8 + 240), (__int64)v9);
    std::endl(v10);
  }
  return LogLeavePhase();
}

```

## disassembly

```asm
0x14000fcb8  mov     [rsp+arg_0], rbx
0x14000fcbd  push    rdi
0x14000fcbe  sub     rsp, 240h
0x14000fcc5  mov     rax, cs:__security_cookie
0x14000fccc  xor     rax, rsp
0x14000fccf  mov     [rsp+248h+var_18], rax
0x14000fcd7  mov     ecx, 8Ch
0x14000fcdc  lea     rdx, aRestoreSystemP; "Restore system policies"
0x14000fce3  call    LogEnterPhase
0x14000fce8  cmp     cs:byte_1401C1258, 0
0x14000fcef  jz      loc_14000FD9C
0x14000fcf5  xor     edx, edx
0x14000fcf7  call    SmuCacheHitsControl
0x14000fcfc  lea     rbx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14000fd03  mov     edi, eax
0x14000fd05  test    eax, eax
0x14000fd07  jns     short loc_14000FD2A
0x14000fd09  mov     r9d, eax
0x14000fd0c  lea     r8, aErrorCouldNotD; "ERROR: Could not disable cache hits: %x"...
0x14000fd13  mov     edx, 985h
0x14000fd18  mov     rcx, rbx
0x14000fd1b  call    Log_Text_F
0x14000fd20  mov     ecx, edi; Status
0x14000fd22  call    cs:__imp_RtlNtStatusToDosError
0x14000fd28  jmp     short loc_14000FD44
0x14000fd2a  mov     rcx, cs:?s_EMDControlHandle@@3PEAXEA; Handle
0x14000fd31  call    cs:__imp_NtClose
0x14000fd37  xor     eax, eax
0x14000fd39  mov     cs:?s_EMDControlHandle@@3PEAXEA, 0; void * s_EMDControlHandle
0x14000fd44  test    eax, eax
0x14000fd46  jz      short loc_14000FD8E
0x14000fd48  call    cs:__imp_GetLastError
0x14000fd4e  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x14000fd53  mov     [rsp+248h+var_24], 1
0x14000fd5b  mov     [rsp+248h+var_28], eax
0x14000fd62  mov     [rsp+248h+var_20], 0
0x14000fd6e  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14000fd73  lea     r9, [rsp+248h+Buffer]
0x14000fd78  mov     edx, 0ACAh
0x14000fd7d  lea     r8, aUnableToReenab; "> Unable to reenable EMD device; %s"
0x14000fd84  mov     rcx, rbx
0x14000fd87  call    Log_Text_F
0x14000fd8c  jmp     short loc_14000FDB7
0x14000fd8e  lea     r8, aSuccessfullyRe; "> Successfully reenabled EMD."
0x14000fd95  mov     edx, 0ACCh
0x14000fd9a  jmp     short loc_14000FDAF
0x14000fd9c  lea     r8, aNotNecessaryTo; "> Not necessary to reenable EMD cache."
0x14000fda3  mov     edx, 0ACFh
0x14000fda8  lea     rbx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14000fdaf  mov     rcx, rbx
0x14000fdb2  call    Log_Text_F
0x14000fdb7  cmp     cs:byte_1401C1249, 0
0x14000fdbe  jz      short loc_14000FDD5
0x14000fdc0  xor     edx, edx
0x14000fdc2  mov     cs:byte_1401C1249, 0
0x14000fdc9  lea     rcx, aCkclstart; "CKCLStart"
0x14000fdd0  call    SetWinsatRegKeyULONGLONG
0x14000fdd5  cmp     cs:byte_1401C1248, 0
0x14000fddc  jz      short loc_14000FE28
0x14000fdde  lea     rcx, LibFileName; "dwmapi.dll"
0x14000fde5  call    cs:__imp_LoadLibraryW
0x14000fdeb  test    rax, rax
0x14000fdee  jz      short loc_14000FE03
0x14000fdf0  mov     edx, 67h ; 'g'; lpProcName
0x14000fdf5  mov     rcx, rax; hModule
0x14000fdf8  call    cs:__imp_GetProcAddress
0x14000fdfe  test    rax, rax
0x14000fe01  jnz     short loc_14000FE4E
0x14000fe03  call    cs:__imp_GetLastError
0x14000fe09  mov     ecx, 32h ; '2'; dwErrCode
0x14000fe0e  call    cs:__imp_SetLastError
0x14000fe14  lea     r8, aInfoDwmprestar; "INFO: DwmpRestartComposition() did not "...
0x14000fe1b  mov     edx, 0AE9h
0x14000fe20  mov     rcx, rbx
0x14000fe23  call    Log_Text_F
0x14000fe28  call    LogLeavePhase
0x14000fe2d  mov     rcx, [rsp+248h+var_18]
0x14000fe35  xor     rcx, rsp; StackCookie
0x14000fe38  call    __security_check_cookie
0x14000fe3d  mov     rbx, [rsp+248h+arg_0]
0x14000fe45  add     rsp, 240h
0x14000fe4c  pop     rdi
0x14000fe4d  retn
0x14000fe4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe53  cmp     eax, 32h ; '2'
0x14000fe56  jnz     short loc_14000FE9F
0x14000fe58  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x14000fe5f  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14000fe64  cmp     byte ptr [rax+1EAh], 0
0x14000fe6b  jz      short loc_14000FE14
0x14000fe6d  lea     r8, aWarningComposi_0; "Warning: Composition Restart not suppor"...
0x14000fe74  mov     edx, 0AE2h
0x14000fe79  mov     rcx, rbx
0x14000fe7c  call    Log_Text_F
0x14000fe81  cmp     cs:?s_Verbose@App@@2_NA, 0; bool App::s_Verbose
0x14000fe88  jz      short loc_14000FE28
0x14000fe8a  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14000fe91  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14000fe96  lea     rdx, aWarningComposi; "Warning: Composition Restart not suppor"...
0x14000fe9d  jmp     short loc_14000FEDB
0x14000fe9f  test    eax, eax
0x14000fea1  jnz     loc_14000FE14
0x14000fea7  lea     r8, aCompositionRes_0; "> Composition restarted"
0x14000feae  mov     edx, 0AE6h
0x14000feb3  mov     rcx, rbx
0x14000feb6  call    Log_Text_F
0x14000febb  cmp     cs:?s_Verbose@App@@2_NA, 0; bool App::s_Verbose
0x14000fec2  jz      loc_14000FE28
0x14000fec8  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14000fecf  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14000fed4  lea     rdx, aCompositionRes; "> Composition restarted"
0x14000fedb  lea     rcx, [rax+0F0h]
0x14000fee2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000fee7  mov     rcx, rax
0x14000feea  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14000feef  jmp     loc_14000FE28
```
