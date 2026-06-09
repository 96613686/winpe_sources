# Windows::Registry::SetValue<-2147483646>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::variant<uint,unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &)

- ea: `0x18003fea8`
- end: `0x180040121`
- name: `??$SetValue@$0?HPPPPPPO@@Registry@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEBV?$variant@I_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@3@@Z`
- size: `633`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180037470`

## callees

- `0x180007660`
- `0x1800085a8`
- `0x18001ee04`
- `0x18002778c`
- `0x18002ad38`
- `0x18003fea8`
- `0x1800408f8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ff44`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ffcf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800400a0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ff44`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ffcf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800400a0`

## string_xrefs

- `0x18003fff0`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x1800400c3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x180040100`: `Registry type unsupported`

## pseudocode

```c
__int64 __fastcall Windows::Registry::SetValue<-2147483646>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        __int64 *a5)
{
  __int64 *v6; // rdi
  char v7; // al
  __int64 *v8; // rsi
  LPCWSTR *v9; // rdi
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  __int64 *v12; // rsi
  LPCWSTR *v13; // rdi
  const WCHAR *v14; // rdx
  unsigned int v15; // eax
  __int64 *v16; // rsi
  LPCWSTR *v17; // rdi
  LPCVOID *lpData; // rcx
  const WCHAR *v19; // rdx
  unsigned int v20; // eax
  __int64 Data; // [rsp+40h] [rbp-21h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+48h] [rbp-19h] BYREF
  unsigned __int64 v24; // [rsp+60h] [rbp-1h]
  LPCVOID pExceptionObject[2]; // [rsp+68h] [rbp+7h] BYREF
  __int128 v26; // [rsp+78h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  v6 = a5;
  (*(void (__fastcall **)(__int64, LPCWSTR *, __int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, lpSubKey, a2, a3);
  v7 = *((_BYTE *)a5 + 32);
  if ( v7 )
  {
    if ( v7 == 1 )
    {
      Data = *a5;
      if ( *((_QWORD *)a4 + 3) <= 7u )
        v12 = (__int64 *)a4;
      else
        v12 = *(__int64 **)a4;
      v13 = lpSubKey;
      if ( v24 > 7 )
        v13 = (LPCWSTR *)lpSubKey[0];
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const WCHAR **)a4;
      v14 = (const WCHAR *)lpSubKey;
      if ( v24 > 7 )
        v14 = lpSubKey[0];
      v15 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v14, a4, 0xBu, &Data, 8u);
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x170,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
        (const char *)v15,
        (unsigned int)"%ws[%ws]",
        (const char *)v13,
        v12);
    }
    else
    {
      if ( v7 != 2 )
      {
        std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Registry type unsupported");
        throw (std::logic_error *)pExceptionObject;
      }
      *(_OWORD *)pExceptionObject = 0;
      v26 = 0;
      if ( (unsigned __int64)a5[3] > 7 )
        v6 = (__int64 *)*a5;
      std::wstring::_Construct<2,unsigned short const *>(pExceptionObject, v6, a5[2]);
      if ( *((_QWORD *)a4 + 3) <= 7u )
        v16 = (__int64 *)a4;
      else
        v16 = *(__int64 **)a4;
      v17 = lpSubKey;
      if ( v24 > 7 )
        v17 = (LPCWSTR *)lpSubKey[0];
      lpData = pExceptionObject;
      if ( *((_QWORD *)&v26 + 1) > 7u )
        lpData = (LPCVOID *)pExceptionObject[0];
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const WCHAR **)a4;
      v19 = (const WCHAR *)lpSubKey;
      if ( v24 > 7 )
        v19 = lpSubKey[0];
      v20 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v19, a4, 1u, lpData, 2 * v26 + 2);
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x17C,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
        (const char *)v20,
        (unsigned int)"%ws[%ws]",
        (const char *)v17,
        v16);
      std::wstring::_Tidy_deallocate(pExceptionObject);
    }
  }
  else
  {
    LODWORD(Data) = *(_DWORD *)a5;
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v8 = (__int64 *)a4;
    else
      v8 = *(__int64 **)a4;
    v9 = lpSubKey;
    if ( v24 > 7 )
      v9 = (LPCWSTR *)lpSubKey[0];
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v10 = (const WCHAR *)lpSubKey;
    if ( v24 > 7 )
      v10 = lpSubKey[0];
    v11 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v10, a4, 4u, &Data, 4u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
      (const char *)v11,
      (unsigned int)"%ws[%ws]",
      (const char *)v9,
      v8);
  }
  return std::wstring::_Tidy_deallocate(lpSubKey);
}

```

## disassembly

```asm
0x18003fea8  push    rbp
0x18003feaa  push    rbx
0x18003feab  push    rsi
0x18003feac  push    rdi
0x18003fead  lea     rbp, [rsp-37h]
0x18003feb2  sub     rsp, 98h
0x18003feb9  mov     rax, cs:__security_cookie
0x18003fec0  xor     rax, rsp
0x18003fec3  mov     [rbp+4Fh+var_28], rax
0x18003fec7  mov     rbx, r9
0x18003feca  mov     rdi, [rbp+4Fh+arg_20]
0x18003fece  mov     rax, [rcx]
0x18003fed1  mov     r9, r8
0x18003fed4  mov     r8, rdx
0x18003fed7  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003fedb  mov     rax, [rax+58h]
0x18003fedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fee4  nop
0x18003fee5  mov     al, [rdi+20h]
0x18003fee8  test    al, al
0x18003feea  jnz     short loc_18003FF6A
0x18003feec  mov     eax, [rdi]
0x18003feee  mov     dword ptr [rbp+4Fh+Data], eax
0x18003fef1  cmp     qword ptr [rbx+18h], 7
0x18003fef6  jbe     short loc_18003FEFD
0x18003fef8  mov     rsi, [rbx]
0x18003fefb  jmp     short loc_18003FF00
0x18003fefd  mov     rsi, rbx
0x18003ff00  lea     rdi, [rbp+4Fh+lpSubKey]
0x18003ff04  cmp     [rbp+4Fh+var_50], 7
0x18003ff09  cmova   rdi, [rbp+4Fh+lpSubKey]
0x18003ff0e  cmp     qword ptr [rbx+18h], 7
0x18003ff13  jbe     short loc_18003FF18
0x18003ff15  mov     rbx, [rbx]
0x18003ff18  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003ff1c  cmp     [rbp+4Fh+var_50], 7
0x18003ff21  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18003ff26  mov     r9d, 4; dwType
0x18003ff2c  mov     [rsp+0B0h+cbData], r9d; cbData
0x18003ff31  lea     rax, [rbp+4Fh+Data]
0x18003ff35  mov     [rsp+0B0h+lpData], rax; lpData
0x18003ff3a  mov     r8, rbx; lpValueName
0x18003ff3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ff44  call    cs:__imp_RegSetKeyValueW
0x18003ff4a  mov     [rsp+0B0h+var_80], rsi
0x18003ff4f  mov     qword ptr [rsp+0B0h+cbData], rdi
0x18003ff54  lea     rdx, aWsWs; "%ws[%ws]"
0x18003ff5b  mov     [rsp+0B0h+lpData], rdx
0x18003ff60  mov     edx, 165h
0x18003ff65  jmp     loc_18003FFF0
0x18003ff6a  cmp     al, 1
0x18003ff6c  jnz     loc_180040008
0x18003ff72  mov     rax, [rdi]
0x18003ff75  mov     [rbp+4Fh+Data], rax
0x18003ff79  cmp     qword ptr [rbx+18h], 7
0x18003ff7e  jbe     short loc_18003FF85
0x18003ff80  mov     rsi, [rbx]
0x18003ff83  jmp     short loc_18003FF88
0x18003ff85  mov     rsi, rbx
0x18003ff88  lea     rdi, [rbp+4Fh+lpSubKey]
0x18003ff8c  cmp     [rbp+4Fh+var_50], 7
0x18003ff91  cmova   rdi, [rbp+4Fh+lpSubKey]
0x18003ff96  cmp     qword ptr [rbx+18h], 7
0x18003ff9b  jbe     short loc_18003FFA0
0x18003ff9d  mov     rbx, [rbx]
0x18003ffa0  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003ffa4  cmp     [rbp+4Fh+var_50], 7
0x18003ffa9  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18003ffae  mov     [rsp+0B0h+cbData], 8; cbData
0x18003ffb6  lea     rax, [rbp+4Fh+Data]
0x18003ffba  mov     [rsp+0B0h+lpData], rax; lpData
0x18003ffbf  mov     r9d, 0Bh; dwType
0x18003ffc5  mov     r8, rbx; lpValueName
0x18003ffc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ffcf  call    cs:__imp_RegSetKeyValueW
0x18003ffd5  mov     [rsp+0B0h+var_80], rsi
0x18003ffda  mov     qword ptr [rsp+0B0h+cbData], rdi; char *
0x18003ffdf  lea     rdx, aWsWs; "%ws[%ws]"
0x18003ffe6  mov     [rsp+0B0h+lpData], rdx; unsigned int
0x18003ffeb  mov     edx, 170h; void *
0x18003fff0  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003fff7  mov     r9d, eax; char *
0x18003fffa  mov     rcx, [rbp+57h]; this
0x18003fffe  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180040003  jmp     loc_1800400DF
0x180040008  cmp     al, 2
0x18004000a  jnz     loc_180040100
0x180040010  xorps   xmm0, xmm0
0x180040013  movups  xmmword ptr [rbp+4Fh+pExceptionObject], xmm0
0x180040017  xorps   xmm1, xmm1
0x18004001a  movdqu  [rbp+4Fh+var_38], xmm1
0x18004001f  mov     r8, [rdi+10h]
0x180040023  cmp     qword ptr [rdi+18h], 7
0x180040028  jbe     short loc_18004002D
0x18004002a  mov     rdi, [rdi]
0x18004002d  mov     rdx, rdi
0x180040030  lea     rcx, [rbp+4Fh+pExceptionObject]
0x180040034  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180040039  nop
0x18004003a  cmp     qword ptr [rbx+18h], 7
0x18004003f  jbe     short loc_180040046
0x180040041  mov     rsi, [rbx]
0x180040044  jmp     short loc_180040049
0x180040046  mov     rsi, rbx
0x180040049  lea     rdi, [rbp+4Fh+lpSubKey]
0x18004004d  cmp     [rbp+4Fh+var_50], 7
0x180040052  cmova   rdi, [rbp+4Fh+lpSubKey]
0x180040057  mov     eax, dword ptr [rbp+4Fh+var_38]
0x18004005a  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18004005e  cmp     qword ptr [rbp+4Fh+var_38+8], 7
0x180040063  cmova   rcx, [rbp+4Fh+pExceptionObject]
0x180040068  cmp     qword ptr [rbx+18h], 7
0x18004006d  jbe     short loc_180040072
0x18004006f  mov     rbx, [rbx]
0x180040072  lea     rdx, [rbp+4Fh+lpSubKey]
0x180040076  cmp     [rbp+4Fh+var_50], 7
0x18004007b  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x180040080  lea     eax, ds:2[rax*2]
0x180040087  mov     [rsp+0B0h+cbData], eax; cbData
0x18004008b  mov     [rsp+0B0h+lpData], rcx; lpData
0x180040090  mov     r9d, 1; dwType
0x180040096  mov     r8, rbx; lpValueName
0x180040099  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800400a0  call    cs:__imp_RegSetKeyValueW
0x1800400a6  mov     rcx, [rbp+57h]; this
0x1800400aa  mov     [rsp+0B0h+var_80], rsi
0x1800400af  mov     qword ptr [rsp+0B0h+cbData], rdi; char *
0x1800400b4  lea     rdx, aWsWs; "%ws[%ws]"
0x1800400bb  mov     [rsp+0B0h+lpData], rdx; unsigned int
0x1800400c0  mov     r9d, eax; char *
0x1800400c3  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800400ca  mov     edx, 17Ch; void *
0x1800400cf  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800400d4  nop
0x1800400d5  lea     rcx, [rbp+4Fh+pExceptionObject]
0x1800400d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800400de  nop
0x1800400df  lea     rcx, [rbp+4Fh+lpSubKey]
0x1800400e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800400e8  mov     rcx, [rbp+4Fh+var_28]
0x1800400ec  xor     rcx, rsp; StackCookie
0x1800400ef  call    __security_check_cookie
0x1800400f4  add     rsp, 98h
0x1800400fb  pop     rdi
0x1800400fc  pop     rsi
0x1800400fd  pop     rbx
0x1800400fe  pop     rbp
0x1800400ff  retn
0x180040100  lea     rdx, aRegistryTypeUn; "Registry type unsupported"
0x180040107  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18004010b  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x180040110  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180040117  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18004011b  call    _CxxThrowException_0
```
