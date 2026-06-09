# Windows::Service::Task::SetInterval(std::chrono::duration<int,std::ratio<60,1>> const &,std::chrono::duration<int,std::ratio<60,1>> const &)

- ea: `0x18005dfbc`
- end: `0x18005e36a`
- name: `?SetInterval@Task@Service@Windows@@QEAAXAEBV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@0@Z`
- size: `942`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x18005de30`

## callees

- `0x180007660`
- `0x18001ee04`
- `0x1800209fc`
- `0x18002107c`
- `0x180023a34`
- `0x180023ac4`
- `0x18005ac34`
- `0x18005c9d8`
- `0x18005dfbc`
- `0x18005ecd0`
- `0x180071010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e0ed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e229`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e0ed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e229`
- `OLEAUT32!__imp_SysAllocString` at `0x18005e10d`
- `OLEAUT32!__imp_SysAllocString` at `0x18005e10d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e14c`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e264`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e274`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e28e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e14c`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e264`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e274`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e28e`

## string_xrefs

- `0x18005e32e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005e2f2`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e307`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e31c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e343`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e358`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall Windows::Service::Task::SetInterval(__int64 a1, unsigned int *a2, unsigned int *a3)
{
  __int64 v6; // rax
  void *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  OLECHAR **v13; // rcx
  __int64 *v14; // rdi
  __int64 v15; // r14
  const OLECHAR *v16; // rcx
  OLECHAR *v17; // rax
  const char *v18; // r9
  OLECHAR *v19; // rbx
  int v20; // eax
  __int64 v21; // rax
  void *v22; // rax
  __int64 v23; // rax
  __int128 *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  __int64 result; // rax
  int v29[2]; // [rsp+20h] [rbp-89h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-81h] BYREF
  BSTR v31; // [rsp+30h] [rbp-79h] BYREF
  __int64 *v32; // [rsp+38h] [rbp-71h] BYREF
  int v33; // [rsp+40h] [rbp-69h]
  BSTR v34[2]; // [rsp+48h] [rbp-61h] BYREF
  OLECHAR *psz[2]; // [rsp+58h] [rbp-51h] BYREF
  __int128 v36; // [rsp+68h] [rbp-41h]
  __int128 v37; // [rsp+78h] [rbp-31h] BYREF
  __int128 v38; // [rsp+88h] [rbp-21h]
  _BYTE v39[32]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v40[32]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v33 = 0;
  Windows::Service::Task::GetTimeTrigger(a1, &v32);
  v6 = std::to_wstring(v40, *a2);
  v7 = (void *)std::operator+<unsigned short>(v39, L"PT", v6);
  v8 = std::wstring::_Append<unsigned short>(v7);
  *(_OWORD *)psz = 0;
  v36 = 0;
  *(_OWORD *)psz = *(_OWORD *)v8;
  v36 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  std::wstring::_Tidy_deallocate(v39);
  std::wstring::_Tidy_deallocate(v40);
  *(_QWORD *)v29 = 0;
  v9 = *v32;
  *(_QWORD *)v29 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, int *))(v9 + 80))(v32, v29);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v10,
      v29[0]);
  v31 = 0;
  v11 = **(_QWORD **)v29;
  v31 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(v11 + 56))(*(_QWORD *)v29, &v31);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v12,
      v29[0]);
  v13 = psz;
  if ( *((_QWORD *)&v36 + 1) > 7u )
    v13 = (OLECHAR **)psz[0];
  if ( (unsigned int)_o__wcsicmp(v13, v31) )
  {
    v14 = *(__int64 **)v29;
    v15 = **(_QWORD **)v29;
    v16 = (const OLECHAR *)psz;
    if ( *((_QWORD *)&v36 + 1) > 7u )
      v16 = psz[0];
    v17 = SysAllocString(v16);
    v19 = v17;
    v34[1] = v17;
    v33 = 3;
    if ( !v17 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v18);
    v20 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *))(v15 + 64))(v14, v17);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v20,
        v29[0]);
    SysFreeString(v19);
    *(_BYTE *)(a1 + 40) = 1;
  }
  v21 = std::to_wstring(v39, *a3);
  v22 = (void *)std::operator+<unsigned short>(v40, L"PT", v21);
  v23 = std::wstring::_Append<unsigned short>(v22);
  v37 = 0;
  v38 = 0;
  v37 = *(_OWORD *)v23;
  v38 = *(_OWORD *)(v23 + 16);
  *(_QWORD *)(v23 + 16) = 0;
  *(_QWORD *)(v23 + 24) = 7;
  *(_WORD *)v23 = 0;
  std::wstring::_Tidy_deallocate(v40);
  std::wstring::_Tidy_deallocate(v39);
  v24 = &v37;
  if ( *((_QWORD *)&v38 + 1) > 7u )
    v24 = (__int128 *)v37;
  wil::make_bstr(v34, v24);
  bstrString = 0;
  v25 = *v32;
  bstrString = 0;
  v26 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v25 + 160))(v32, &bstrString);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v26,
      v29[0]);
  if ( (unsigned int)_o__wcsicmp(v34[0], bstrString) )
  {
    v27 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(*v32 + 168))(v32, v34[0]);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v27,
        v29[0]);
    *(_BYTE *)(a1 + 40) = 1;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v34[0] )
    SysFreeString(v34[0]);
  std::wstring::_Tidy_deallocate(&v37);
  if ( v31 )
    SysFreeString(v31);
  if ( *(_QWORD *)v29 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 16LL))(*(_QWORD *)v29);
  result = std::wstring::_Tidy_deallocate(psz);
  if ( v32 )
    return (*(__int64 (__fastcall **)(__int64 *))(*v32 + 16))(v32);
  return result;
}

```

## disassembly

```asm
0x18005dfbc  mov     [rsp-8+arg_18], rbx
0x18005dfc1  push    rbp
0x18005dfc2  push    rsi
0x18005dfc3  push    rdi
0x18005dfc4  push    r14
0x18005dfc6  push    r15
0x18005dfc8  lea     rbp, [rsp-37h]
0x18005dfcd  sub     rsp, 0E0h
0x18005dfd4  mov     rax, cs:__security_cookie
0x18005dfdb  xor     rax, rsp
0x18005dfde  mov     [rbp+57h+var_28], rax
0x18005dfe2  mov     r15, r8
0x18005dfe5  mov     rbx, rdx
0x18005dfe8  mov     rsi, rcx
0x18005dfeb  mov     [rbp+57h+var_C0], 0
0x18005dff2  lea     rdx, [rbp+57h+var_C8]
0x18005dff6  call    ?GetTimeTrigger@Task@Service@Windows@@AEAA?AV?$com_ptr_t@UITimeTrigger@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::GetTimeTrigger(void)
0x18005dffb  nop
0x18005dffc  mov     edx, [rbx]
0x18005dffe  lea     rcx, [rbp+57h+var_48]
0x18005e002  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x18005e007  nop
0x18005e008  mov     r8, rax
0x18005e00b  lea     rdx, aPt; "PT"
0x18005e012  lea     rcx, [rbp+57h+var_68]
0x18005e016  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18005e01b  nop
0x18005e01c  mov     r8d, 1
0x18005e022  lea     rdx, aM; "M"
0x18005e029  mov     rcx, rax; Src
0x18005e02c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005e031  xorps   xmm0, xmm0
0x18005e034  movups  xmmword ptr [rbp+57h+psz], xmm0
0x18005e038  xorps   xmm1, xmm1
0x18005e03b  movdqu  [rbp+57h+var_98], xmm1
0x18005e040  movups  xmm0, xmmword ptr [rax]
0x18005e043  movups  xmmword ptr [rbp+57h+psz], xmm0
0x18005e047  movups  xmm1, xmmword ptr [rax+10h]
0x18005e04b  movups  [rbp+57h+var_98], xmm1
0x18005e04f  mov     qword ptr [rax+10h], 0
0x18005e057  mov     qword ptr [rax+18h], 7
0x18005e05f  xor     ecx, ecx
0x18005e061  mov     [rax], cx
0x18005e064  lea     rcx, [rbp+57h+var_68]
0x18005e068  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e06d  nop
0x18005e06e  lea     rcx, [rbp+57h+var_48]
0x18005e072  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e077  mov     qword ptr [rsp+100h+var_E0], 0
0x18005e080  mov     rcx, [rbp+57h+var_C8]
0x18005e084  mov     rax, [rcx]
0x18005e087  mov     qword ptr [rsp+100h+var_E0], 0; int
0x18005e090  lea     rdx, [rsp+100h+var_E0]
0x18005e095  mov     rax, [rax+50h]
0x18005e099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e09e  mov     rcx, [rbp+5Fh]; this
0x18005e0a2  test    eax, eax
0x18005e0a4  js      loc_18005E304
0x18005e0aa  mov     [rbp+57h+var_D0], 0
0x18005e0b2  mov     rcx, qword ptr [rsp+100h+var_E0]
0x18005e0b7  mov     rax, [rcx]
0x18005e0ba  mov     [rbp+57h+var_D0], 0
0x18005e0c2  lea     rdx, [rbp+57h+var_D0]
0x18005e0c6  mov     rax, [rax+38h]
0x18005e0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0cf  mov     rcx, [rbp+5Fh]; this
0x18005e0d3  test    eax, eax
0x18005e0d5  js      loc_18005E319
0x18005e0db  lea     rcx, [rbp+57h+psz]
0x18005e0df  cmp     qword ptr [rbp+57h+var_98+8], 7
0x18005e0e4  cmova   rcx, [rbp+57h+psz]
0x18005e0e9  mov     rdx, [rbp+57h+var_D0]
0x18005e0ed  call    cs:__imp__o__wcsicmp
0x18005e0f3  test    eax, eax
0x18005e0f5  jz      short loc_18005E156
0x18005e0f7  mov     rdi, qword ptr [rsp+100h+var_E0]
0x18005e0fc  mov     r14, [rdi]
0x18005e0ff  lea     rcx, [rbp+57h+psz]
0x18005e103  cmp     qword ptr [rbp+57h+var_98+8], 7
0x18005e108  cmova   rcx, [rbp+57h+psz]; psz
0x18005e10d  call    cs:__imp_SysAllocString
0x18005e113  mov     rbx, rax
0x18005e116  mov     [rbp+57h+var_B0], rax
0x18005e11a  mov     [rbp+57h+var_C0], 3
0x18005e121  mov     rcx, [rbp+5Fh]; this
0x18005e125  test    rax, rax
0x18005e128  jz      loc_18005E32E
0x18005e12e  mov     rdx, rax
0x18005e131  mov     rcx, rdi
0x18005e134  mov     rax, [r14+40h]
0x18005e138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e13d  mov     rcx, [rbp+5Fh]; this
0x18005e141  test    eax, eax
0x18005e143  js      loc_18005E340
0x18005e149  mov     rcx, rbx; bstrString
0x18005e14c  call    cs:__imp_SysFreeString
0x18005e152  mov     byte ptr [rsi+28h], 1
0x18005e156  mov     edx, [r15]
0x18005e159  lea     rcx, [rbp+57h+var_68]
0x18005e15d  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x18005e162  nop
0x18005e163  mov     r8, rax
0x18005e166  lea     rdx, aPt; "PT"
0x18005e16d  lea     rcx, [rbp+57h+var_48]
0x18005e171  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18005e176  nop
0x18005e177  mov     r8d, 1
0x18005e17d  lea     rdx, aM; "M"
0x18005e184  mov     rcx, rax; Src
0x18005e187  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005e18c  xorps   xmm0, xmm0
0x18005e18f  movups  [rbp+57h+var_88], xmm0
0x18005e193  xorps   xmm1, xmm1
0x18005e196  movdqu  [rbp+57h+var_78], xmm1
0x18005e19b  movups  xmm0, xmmword ptr [rax]
0x18005e19e  movups  [rbp+57h+var_88], xmm0
0x18005e1a2  movups  xmm1, xmmword ptr [rax+10h]
0x18005e1a6  movups  [rbp+57h+var_78], xmm1
0x18005e1aa  mov     qword ptr [rax+10h], 0
0x18005e1b2  mov     qword ptr [rax+18h], 7
0x18005e1ba  xor     ecx, ecx
0x18005e1bc  mov     [rax], cx
0x18005e1bf  lea     rcx, [rbp+57h+var_48]
0x18005e1c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e1c8  nop
0x18005e1c9  lea     rcx, [rbp+57h+var_68]
0x18005e1cd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e1d2  lea     rdx, [rbp+57h+var_88]
0x18005e1d6  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18005e1db  cmova   rdx, qword ptr [rbp+57h+var_88]
0x18005e1e0  lea     rcx, [rbp+57h+var_B8]
0x18005e1e4  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005e1e9  nop
0x18005e1ea  mov     [rsp+100h+bstrString], 0
0x18005e1f3  mov     rcx, [rbp+57h+var_C8]
0x18005e1f7  mov     rax, [rcx]
0x18005e1fa  mov     [rsp+100h+bstrString], 0
0x18005e203  lea     rdx, [rsp+100h+bstrString]
0x18005e208  mov     rax, [rax+0A0h]
0x18005e20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e214  mov     rcx, [rbp+5Fh]; this
0x18005e218  test    eax, eax
0x18005e21a  js      loc_18005E355
0x18005e220  mov     rdx, [rsp+100h+bstrString]
0x18005e225  mov     rcx, [rbp+57h+var_B8]
0x18005e229  call    cs:__imp__o__wcsicmp
0x18005e22f  test    eax, eax
0x18005e231  jz      short loc_18005E25A
0x18005e233  mov     rcx, [rbp+57h+var_C8]
0x18005e237  mov     rax, [rcx]
0x18005e23a  mov     rdx, [rbp+57h+var_B8]
0x18005e23e  mov     rax, [rax+0A8h]
0x18005e245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e24a  mov     rcx, [rbp+5Fh]; this
0x18005e24e  test    eax, eax
0x18005e250  js      loc_18005E2EF
0x18005e256  mov     byte ptr [rsi+28h], 1
0x18005e25a  mov     rcx, [rsp+100h+bstrString]; bstrString
0x18005e25f  test    rcx, rcx
0x18005e262  jz      short loc_18005E26B
0x18005e264  call    cs:__imp_SysFreeString
0x18005e26a  nop
0x18005e26b  mov     rcx, [rbp+57h+var_B8]; bstrString
0x18005e26f  test    rcx, rcx
0x18005e272  jz      short loc_18005E27B
0x18005e274  call    cs:__imp_SysFreeString
0x18005e27a  nop
0x18005e27b  lea     rcx, [rbp+57h+var_88]
0x18005e27f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e284  nop
0x18005e285  mov     rcx, [rbp+57h+var_D0]; bstrString
0x18005e289  test    rcx, rcx
0x18005e28c  jz      short loc_18005E295
0x18005e28e  call    cs:__imp_SysFreeString
0x18005e294  nop
0x18005e295  mov     rcx, qword ptr [rsp+100h+var_E0]
0x18005e29a  test    rcx, rcx
0x18005e29d  jz      short loc_18005E2AC
0x18005e29f  mov     rax, [rcx]
0x18005e2a2  mov     rax, [rax+10h]
0x18005e2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2ab  nop
0x18005e2ac  lea     rcx, [rbp+57h+psz]
0x18005e2b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e2b5  nop
0x18005e2b6  mov     rcx, [rbp+57h+var_C8]
0x18005e2ba  test    rcx, rcx
0x18005e2bd  jz      short loc_18005E2CC
0x18005e2bf  mov     rax, [rcx]
0x18005e2c2  mov     rax, [rax+10h]
0x18005e2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2cb  nop
0x18005e2cc  mov     rcx, [rbp+57h+var_28]
0x18005e2d0  xor     rcx, rsp; StackCookie
0x18005e2d3  call    __security_check_cookie
0x18005e2d8  mov     rbx, [rsp+100h+arg_18]
0x18005e2e0  add     rsp, 0E0h
0x18005e2e7  pop     r15
0x18005e2e9  pop     r14
0x18005e2eb  pop     rdi
0x18005e2ec  pop     rsi
0x18005e2ed  pop     rbp
0x18005e2ee  retn
0x18005e2ef  mov     r9d, eax; char *
0x18005e2f2  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e2f9  mov     edx, 72h ; 'r'; void *
0x18005e2fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e304  mov     r9d, eax; char *
0x18005e307  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e30e  mov     edx, 60h ; '`'; void *
0x18005e313  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e319  mov     r9d, eax; char *
0x18005e31c  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e323  mov     edx, 63h ; 'c'; void *
0x18005e328  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e32e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005e335  mov     edx, 15F3h; void *
0x18005e33a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005e340  mov     r9d, eax; char *
0x18005e343  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e34a  mov     edx, 66h ; 'f'; void *
0x18005e34f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e355  mov     r9d, eax; char *
0x18005e358  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e35f  mov     edx, 6Fh ; 'o'; void *
0x18005e364  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
