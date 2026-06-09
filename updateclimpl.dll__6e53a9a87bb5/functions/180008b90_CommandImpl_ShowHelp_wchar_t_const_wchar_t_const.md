# CommandImpl::ShowHelp(wchar_t const *,wchar_t const *)

- ea: `0x180008b90`
- end: `0x180008cd3`
- name: `?ShowHelp@CommandImpl@@CAJPEB_W0@Z`
- size: `323`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800084bc`

## callees

- `0x180008408`
- `0x180008b90`
- `0x180008f78`
- `0x18000917c`
- `0x180009320`
- `0x18000d3b4`

## pseudocode

```c
__int64 __fastcall CommandImpl::ShowHelp(const wchar_t *a1, const wchar_t *a2)
{
  _QWORD *ResourceString; // rax
  __int64 v3; // r8
  __int64 v4; // rax
  _QWORD *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  const char *v8; // r9
  const struct CommandEntry near *const *i; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdi
  _QWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 result; // rax
  _BYTE v17[40]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    ResourceString = (_QWORD *)CliUtils::LoadResourceString(v17, 2001);
    v3 = ResourceString[2];
    if ( ResourceString[3] > 7u )
      ResourceString = (_QWORD *)*ResourceString;
    v4 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcout, ResourceString, v3);
    std::endl<wchar_t,std::char_traits<wchar_t>>(v4);
    std::wstring::~wstring((__int64)v17);
    std::endl<wchar_t,std::char_traits<wchar_t>>((__int64)&std::wcout);
    v5 = (_QWORD *)CliUtils::LoadResourceString(v17, 2002);
    v6 = v5[2];
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    v7 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcout, v5, v6);
    std::endl<wchar_t,std::char_traits<wchar_t>>(v7);
    std::wstring::~wstring((__int64)v17);
    for ( i = &CommandImpl::_commands; i != (const struct CommandEntry near *const *)&off_180017CE0; i += 4 )
    {
      if ( *((_DWORD *)i + 6) )
      {
        v10 = std::operator<<<wchar_t,std::char_traits<wchar_t>>((__int64)&std::wcout, (__int64)L"  ");
        v11 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v10, *i, *((_QWORD *)i + 1));
        v12 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v11, (__int64)L" - ");
        v13 = (_QWORD *)CliUtils::LoadResourceString(v17, *((unsigned int *)i + 6));
        v14 = v13[2];
        if ( v13[3] > 7u )
          v13 = (_QWORD *)*v13;
        v15 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v12, v13, v14);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v15);
        std::wstring::~wstring((__int64)v17);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xCC,
                           (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180008b90  mov     [rsp+arg_0], rbx
0x180008b95  mov     [rsp+arg_8], rdi
0x180008b9a  push    r14
0x180008b9c  sub     rsp, 40h
0x180008ba0  mov     edx, 7D1h
0x180008ba5  lea     rcx, [rsp+48h+var_28]
0x180008baa  call    ?LoadResourceString@CliUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; CliUtils::LoadResourceString(uint)
0x180008baf  nop
0x180008bb0  mov     r8, [rax+10h]
0x180008bb4  cmp     qword ptr [rax+18h], 7
0x180008bb9  jbe     short loc_180008BBE
0x180008bbb  mov     rax, [rax]
0x180008bbe  mov     rdx, rax
0x180008bc1  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180008bc8  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180008bcd  mov     rcx, rax
0x180008bd0  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008bd5  nop
0x180008bd6  lea     rcx, [rsp+48h+var_28]
0x180008bdb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008be0  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180008be7  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008bec  mov     edx, 7D2h
0x180008bf1  lea     rcx, [rsp+48h+var_28]
0x180008bf6  call    ?LoadResourceString@CliUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; CliUtils::LoadResourceString(uint)
0x180008bfb  nop
0x180008bfc  mov     r8, [rax+10h]
0x180008c00  cmp     qword ptr [rax+18h], 7
0x180008c05  jbe     short loc_180008C0A
0x180008c07  mov     rax, [rax]
0x180008c0a  mov     rdx, rax
0x180008c0d  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180008c14  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180008c19  mov     rcx, rax
0x180008c1c  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008c21  nop
0x180008c22  lea     rcx, [rsp+48h+var_28]
0x180008c27  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008c2c  lea     rbx, ?_commands@CommandImpl@@0QBUCommandEntry@@B; CommandEntry const near * const CommandImpl::_commands
0x180008c33  lea     r14, off_180017CE0
0x180008c3a  cmp     rbx, r14
0x180008c3d  jz      short loc_180008CB9
0x180008c3f  cmp     dword ptr [rbx+18h], 0
0x180008c43  jz      short loc_180008CB3
0x180008c45  lea     rdx, asc_180018420; "  "
0x180008c4c  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x180008c53  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180008c58  mov     r8, [rbx+8]
0x180008c5c  mov     rdx, [rbx]
0x180008c5f  mov     rcx, rax
0x180008c62  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180008c67  lea     rdx, asc_180018418; " - "
0x180008c6e  mov     rcx, rax
0x180008c71  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180008c76  mov     rdi, rax
0x180008c79  mov     edx, [rbx+18h]
0x180008c7c  lea     rcx, [rsp+48h+var_28]
0x180008c81  call    ?LoadResourceString@CliUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; CliUtils::LoadResourceString(uint)
0x180008c86  nop
0x180008c87  mov     r8, [rax+10h]
0x180008c8b  cmp     qword ptr [rax+18h], 7
0x180008c90  jbe     short loc_180008C95
0x180008c92  mov     rax, [rax]
0x180008c95  mov     rdx, rax
0x180008c98  mov     rcx, rdi
0x180008c9b  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180008ca0  mov     rcx, rax
0x180008ca3  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008ca8  nop
0x180008ca9  lea     rcx, [rsp+48h+var_28]
0x180008cae  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008cb3  add     rbx, 20h ; ' '
0x180008cb7  jmp     short loc_180008C3A
0x180008cb9  xor     eax, eax
0x180008cbb  jmp     short loc_180008CC1
0x180008cbd  mov     eax, [rsp+48h+arg_10]
0x180008cc1  mov     rbx, [rsp+48h+arg_0]
0x180008cc6  mov     rdi, [rsp+48h+arg_8]
0x180008ccb  add     rsp, 40h
0x180008ccf  pop     r14
0x180008cd1  retn
```
