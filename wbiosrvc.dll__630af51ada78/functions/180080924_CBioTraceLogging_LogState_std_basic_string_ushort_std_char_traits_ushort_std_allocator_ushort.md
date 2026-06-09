# CBioTraceLogging::LogState(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180080924`
- end: `0x180080b20`
- name: `?LogState@CBioTraceLogging@@CA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `508`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800801d0`
- `0x180081e54`

## callees

- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180068f60`
- `0x180072d58`
- `0x180074380`
- `0x1800743fc`
- `0x180080924`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ad0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ad0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ae3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180080a0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180080a0a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180080a99`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180080a99`
- `msvcp_win!_Xtime_get_ticks` at `0x180080979`
- `msvcp_win!_Xtime_get_ticks` at `0x180080979`

## string_xrefs

- `0x1800809b9`: `onecore\ds\security\biometrics\service\server\biotracelogging.cpp`
- `0x180080a27`: `onecore\ds\security\biometrics\service\server\biotracelogging.cpp`
- `0x180080a58`: `onecore\ds\security\biometrics\service\server\biotracelogging.cpp`
- `0x180080ab6`: `onecore\ds\security\biometrics\service\server\biotracelogging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CBioTraceLogging::LogState(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // eax
  const WCHAR *v6; // rax
  int ValueW; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // eax
  const WCHAR *v11; // rax
  int v12; // eax
  char v13; // bl
  unsigned int pdwType; // [rsp+20h] [rbp-60h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-60h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-60h]
  unsigned int pdwTypec; // [rsp+20h] [rbp-60h]
  HKEY hkey; // [rsp+40h] [rbp-40h] BYREF
  int pvData; // [rsp+48h] [rbp-38h] BYREF
  DWORD Data[2]; // [rsp+50h] [rbp-30h] BYREF
  _OWORD v22[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  *(_QWORD *)Data = a1;
  v22[0] = 0;
  v22[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v22[0]) = 0;
  if ( (int)GetWinBioRegistryLocation((__int64)v22) < 0 )
  {
LABEL_19:
    v13 = 0;
    goto LABEL_20;
  }
  v2 = _Xtime_get_ticks() / 864000000000LL;
  hkey = 0;
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  v5 = wil::reg::open_unique_key_nothrow(v4, v3, &hkey);
  if ( v5 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x489,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biotracelogging.cpp",
      (const char *)v5,
      pdwType);
  pvData = 0;
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  Data[0] = 4;
  ValueW = RegGetValueW(hkey, 0, v6, 0x10u, 0, &pvData, Data);
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  if ( ValueW )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x48B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biotracelogging.cpp",
      (const char *)(unsigned int)ValueW,
      pdwTypea);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
    v10 = wil::reg::create_unique_key_nothrow(v9, v8, &hkey);
    if ( v10 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x491,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biotracelogging.cpp",
        (const char *)v10,
        pdwTypeb);
  }
  if ( (_DWORD)v2 == pvData )
  {
    if ( hkey )
      RegCloseKey(hkey);
    goto LABEL_19;
  }
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  Data[0] = v2;
  v12 = RegSetKeyValueW(hkey, 0, v11, 4u, Data, 4u);
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x498,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biotracelogging.cpp",
      (const char *)(unsigned int)v12,
      pdwTypec);
  if ( hkey )
    RegCloseKey(hkey);
  v13 = 1;
LABEL_20:
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(a1);
  return v13;
}

```

## disassembly

```asm
0x180080924  mov     [rsp-8+arg_8], rbx
0x180080929  mov     [rsp-8+arg_10], rdi
0x18008092e  push    rbp
0x18008092f  mov     rbp, rsp
0x180080932  sub     rsp, 80h
0x180080939  mov     rax, cs:__security_cookie
0x180080940  xor     rax, rsp
0x180080943  mov     [rbp+var_8], rax
0x180080947  mov     rdi, rcx
0x18008094a  mov     qword ptr [rbp+Data], rcx
0x18008094e  xorps   xmm0, xmm0
0x180080951  movups  [rbp+var_28], xmm0
0x180080955  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008095d  movdqu  [rbp+var_18], xmm1
0x180080962  xor     eax, eax
0x180080964  mov     word ptr [rbp+var_28], ax
0x180080968  lea     rcx, [rbp+var_28]
0x18008096c  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180080971  test    eax, eax
0x180080973  js      loc_180080AE9
0x180080979  call    cs:__imp__Xtime_get_ticks
0x18008097f  cqo
0x180080981  mov     rcx, 0C92A69C000h
0x18008098b  idiv    rcx
0x18008098e  mov     rbx, rax
0x180080991  mov     [rbp+hkey], 0
0x180080999  lea     rcx, [rbp+var_28]
0x18008099d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800809a2  mov     rdx, rax
0x1800809a5  lea     r8, [rbp+hkey]
0x1800809a9  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x1800809ae  mov     rcx, [rbp+8]; this
0x1800809b2  test    eax, eax
0x1800809b4  jz      short loc_1800809CA
0x1800809b6  mov     r9d, eax; char *
0x1800809b9  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\biometrics\\serv"...
0x1800809c0  mov     edx, 489h; void *
0x1800809c5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800809ca  mov     [rbp+var_38], 0
0x1800809d1  mov     rcx, rdi
0x1800809d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800809d9  mov     [rbp+Data], 4
0x1800809e0  lea     rcx, [rbp+Data]
0x1800809e4  mov     [rsp+80h+pcbData], rcx; pcbData
0x1800809e9  lea     rcx, [rbp+var_38]
0x1800809ed  mov     [rsp+80h+pvData], rcx; pvData
0x1800809f2  mov     [rsp+80h+pdwType], 0; unsigned int
0x1800809fb  mov     r9d, 10h; dwFlags
0x180080a01  mov     r8, rax; lpValue
0x180080a04  xor     edx, edx; lpSubKey
0x180080a06  mov     rcx, [rbp+hkey]; hkey
0x180080a0a  call    cs:__imp_RegGetValueW
0x180080a10  test    eax, eax
0x180080a12  jle     short loc_180080A1C
0x180080a14  movzx   eax, ax
0x180080a17  or      eax, 80070000h
0x180080a1c  mov     rcx, [rbp+8]; this
0x180080a20  test    eax, eax
0x180080a22  jz      short loc_180080A69
0x180080a24  mov     r9d, eax; char *
0x180080a27  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\biometrics\\serv"...
0x180080a2e  mov     edx, 48Bh; void *
0x180080a33  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180080a38  lea     rcx, [rbp+var_28]
0x180080a3c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180080a41  mov     rdx, rax
0x180080a44  lea     r8, [rbp+hkey]
0x180080a48  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180080a4d  mov     rcx, [rbp+8]; this
0x180080a51  test    eax, eax
0x180080a53  jz      short loc_180080A69
0x180080a55  mov     r9d, eax; char *
0x180080a58  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\biometrics\\serv"...
0x180080a5f  mov     edx, 491h; void *
0x180080a64  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180080a69  cmp     ebx, [rbp+var_38]
0x180080a6c  jz      short loc_180080ADA
0x180080a6e  mov     rcx, rdi
0x180080a71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180080a76  mov     [rbp+Data], ebx
0x180080a79  mov     dword ptr [rsp+80h+pvData], 4; cbData
0x180080a81  lea     rcx, [rbp+Data]
0x180080a85  mov     [rsp+80h+pdwType], rcx; unsigned int
0x180080a8a  mov     r9d, 4; dwType
0x180080a90  mov     r8, rax; lpValueName
0x180080a93  xor     edx, edx; lpSubKey
0x180080a95  mov     rcx, [rbp+hkey]; hKey
0x180080a99  call    cs:__imp_RegSetKeyValueW
0x180080a9f  test    eax, eax
0x180080aa1  jle     short loc_180080AAB
0x180080aa3  movzx   eax, ax
0x180080aa6  or      eax, 80070000h
0x180080aab  mov     rcx, [rbp+8]; this
0x180080aaf  test    eax, eax
0x180080ab1  jz      short loc_180080AC7
0x180080ab3  mov     r9d, eax; char *
0x180080ab6  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\biometrics\\serv"...
0x180080abd  mov     edx, 498h; void *
0x180080ac2  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180080ac7  mov     rcx, [rbp+hkey]; hKey
0x180080acb  test    rcx, rcx
0x180080ace  jz      short loc_180080AD6
0x180080ad0  call    cs:__imp_RegCloseKey
0x180080ad6  mov     bl, 1
0x180080ad8  jmp     short loc_180080AEB
0x180080ada  mov     rcx, [rbp+hkey]; hKey
0x180080ade  test    rcx, rcx
0x180080ae1  jz      short loc_180080AE9
0x180080ae3  call    cs:__imp_RegCloseKey
0x180080ae9  xor     ebx, ebx
0x180080aeb  lea     rcx, [rbp+var_28]
0x180080aef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080af4  nop
0x180080af5  mov     rcx, rdi
0x180080af8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080afd  mov     al, bl
0x180080aff  mov     rcx, [rbp+var_8]
0x180080b03  xor     rcx, rsp; StackCookie
0x180080b06  call    __security_check_cookie
0x180080b0b  lea     r11, [rsp+80h+var_s0]
0x180080b13  mov     rbx, [r11+18h]
0x180080b17  mov     rdi, [r11+20h]
0x180080b1b  mov     rsp, r11
0x180080b1e  pop     rbp
0x180080b1f  retn
```
