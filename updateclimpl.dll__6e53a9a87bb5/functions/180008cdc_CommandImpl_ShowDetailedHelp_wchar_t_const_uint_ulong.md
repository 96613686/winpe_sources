# CommandImpl::ShowDetailedHelp(wchar_t const *,uint,ulong)

- ea: `0x180008cdc`
- end: `0x180008dfd`
- name: `?ShowDetailedHelp@CommandImpl@@CAXPEB_WIK@Z`
- size: `289`
- prototype: `void __fastcall(const wchar_t *, unsigned int, DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800084bc`

## callees

- `0x180008408`
- `0x18000884c`
- `0x180008cdc`
- `0x180008f78`
- `0x18000917c`
- `0x180009320`
- `0x18000d3b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008de8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008de8`

## pseudocode

```c
void __fastcall CommandImpl::ShowDetailedHelp(const wchar_t *a1, unsigned int a2, DWORD a3)
{
  _QWORD *ResourceString; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  _QWORD *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // rax
  HLOCAL v15; // rcx
  DWORD v16; // [rsp+28h] [rbp-50h]
  HLOCAL hMem; // [rsp+38h] [rbp-40h] BYREF
  const char *v19; // [rsp+40h] [rbp-38h]
  _BYTE v20[48]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v19 = (const char *)a1;
  try
  {
    CommandImpl::GetMessageW(&hMem, a3, 0);
    ResourceString = (_QWORD *)CliUtils::LoadResourceString(v20, 2001);
    v6 = ResourceString[2];
    if ( ResourceString[3] > 7u )
      ResourceString = (_QWORD *)*ResourceString;
    v7 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcout, ResourceString, v6);
    std::endl<wchar_t,std::char_traits<wchar_t>>(v7);
    std::wstring::~wstring((__int64)v20);
    std::endl<wchar_t,std::char_traits<wchar_t>>((__int64)&std::wcout);
    v8 = std::operator<<<wchar_t,std::char_traits<wchar_t>>((__int64)&std::wcout, (__int64)a1);
    v9 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v8, (__int64)L" - ");
    v10 = (_QWORD *)CliUtils::LoadResourceString(v20, a2);
    v11 = v10[2];
    if ( v10[3] > 7u )
      v10 = (_QWORD *)*v10;
    v12 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v9, v10, v11);
    std::endl<wchar_t,std::char_traits<wchar_t>>(v12);
    std::wstring::~wstring((__int64)v20);
    v13 = L"???";
    if ( hMem )
      v13 = (const wchar_t *)hMem;
    v14 = std::operator<<<wchar_t,std::char_traits<wchar_t>>((__int64)&std::wcout, (__int64)v13);
    std::endl<wchar_t,std::char_traits<wchar_t>>(v14);
    v15 = hMem;
    hMem = 0;
    if ( v15 )
      LocalFree(v15);
  }
  catch ( ... )
  {
    v16 = a3;
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0xD6,
      (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
      "Failed to load detailed help message for %ws with id %u",
      v19,
      v16);
  }
}

```

## disassembly

```asm
0x180008cdc  mov     [rsp+arg_18], rbx
0x180008ce1  push    rdi
0x180008ce2  sub     rsp, 70h
0x180008ce6  mov     eax, r8d
0x180008ce9  mov     edi, edx
0x180008ceb  mov     rbx, rcx
0x180008cee  mov     [rsp+78h+var_38], rcx
0x180008cf3  mov     [rsp+78h+var_48], eax
0x180008cf7  xor     r8d, r8d
0x180008cfa  mov     edx, eax
0x180008cfc  lea     rcx, [rsp+78h+hMem]
0x180008d01  call    ?GetMessageW@CommandImpl@@CA?AV?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@K_N@Z; CommandImpl::GetMessageW(ulong,bool)
0x180008d06  nop
0x180008d07  mov     edx, 7D1h
0x180008d0c  lea     rcx, [rsp+78h+var_30]
0x180008d11  call    ?LoadResourceString@CliUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; CliUtils::LoadResourceString(uint)
0x180008d16  nop
0x180008d17  mov     r8, [rax+10h]
0x180008d1b  cmp     qword ptr [rax+18h], 7
0x180008d20  jbe     short loc_180008D25
0x180008d22  mov     rax, [rax]
0x180008d25  mov     rdx, rax
0x180008d28  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180008d2f  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180008d34  mov     rcx, rax
0x180008d37  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008d3c  nop
0x180008d3d  lea     rcx, [rsp+78h+var_30]
0x180008d42  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008d47  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180008d4e  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008d53  mov     rdx, rbx
0x180008d56  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180008d5d  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180008d62  lea     rdx, asc_180018418; " - "
0x180008d69  mov     rcx, rax
0x180008d6c  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180008d71  mov     rbx, rax
0x180008d74  mov     edx, edi
0x180008d76  lea     rcx, [rsp+78h+var_30]
0x180008d7b  call    ?LoadResourceString@CliUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; CliUtils::LoadResourceString(uint)
0x180008d80  nop
0x180008d81  mov     r8, [rax+10h]
0x180008d85  cmp     qword ptr [rax+18h], 7
0x180008d8a  jbe     short loc_180008D8F
0x180008d8c  mov     rax, [rax]
0x180008d8f  mov     rdx, rax
0x180008d92  mov     rcx, rbx
0x180008d95  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180008d9a  mov     rcx, rax
0x180008d9d  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008da2  nop
0x180008da3  lea     rcx, [rsp+78h+var_30]
0x180008da8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008dad  lea     rdx, asc_180018428; "???"
0x180008db4  mov     rax, [rsp+78h+hMem]
0x180008db9  test    rax, rax
0x180008dbc  cmovnz  rdx, rax
0x180008dc0  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180008dc7  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180008dcc  mov     rcx, rax
0x180008dcf  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008dd4  nop
0x180008dd5  mov     rcx, [rsp+78h+hMem]; hMem
0x180008dda  mov     [rsp+78h+hMem], 0
0x180008de3  test    rcx, rcx
0x180008de6  jz      short loc_180008DEF
0x180008de8  call    cs:__imp_LocalFree
0x180008dee  nop
0x180008def  mov     rbx, [rsp+78h+arg_18]
0x180008df7  add     rsp, 70h
0x180008dfb  pop     rdi
0x180008dfc  retn
```
