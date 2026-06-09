# uus::Session::GetFullPath(wchar_t const *)

- ea: `0x140007320`
- end: `0x14000745a`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z`
- size: `314`
- prototype: `struct std::filesystem::path __high(const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400074c8`

## callees

- `0x140006d08`
- `0x140007060`
- `0x140007320`
- `0x140008fd4`
- `0x140009214`
- `0x140009340`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400073fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400073fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall uus::Session::GetFullPath(__int64 a1, void *a2, __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  LPVOID pv[2]; // [rsp+20h] [rbp-39h] BYREF
  __int128 v12; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+40h] [rbp-19h]
  __int64 v14; // [rsp+48h] [rbp-11h]
  __int128 v15; // [rsp+50h] [rbp-9h] BYREF
  __int64 v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  __int128 v18; // [rsp+70h] [rbp+17h] BYREF
  __int64 v19; // [rsp+80h] [rbp+27h]
  __int64 v20; // [rsp+88h] [rbp+2Fh]

  pv[0] = a2;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a3 + 2 * v7) );
  v18 = 0;
  v19 = 0;
  v20 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v18, a3);
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
    do
      ++v6;
    while ( *(_WORD *)(v9 + 2 * v6) );
    v12 = 0;
    v13 = 0;
    v14 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v12, v9);
  }
  else
  {
    pv[0] = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(pv);
    do
      ++v6;
    while ( *((_WORD *)pv[0] + v6) );
    v15 = 0;
    v16 = 0;
    v17 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v15, pv[0]);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    uus::Utility::GetGuestOrNativeArchFolder(&v12, &v15);
    std::wstring::~wstring(&v15);
  }
  std::filesystem::operator/(a2, (struct std::filesystem::path *)&v12, &v18);
  std::wstring::~wstring(&v12);
  std::wstring::~wstring(&v18);
  return a2;
}

```

## disassembly

```asm
0x140007320  mov     [rsp-8+arg_10], rbx
0x140007325  mov     [rsp-8+arg_18], rsi
0x14000732a  push    rbp
0x14000732b  push    rdi
0x14000732c  push    r14
0x14000732e  lea     rbp, [rsp-47h]
0x140007333  sub     rsp, 0A0h
0x14000733a  mov     rax, r8
0x14000733d  mov     rdi, rdx
0x140007340  mov     rsi, rcx
0x140007343  mov     [rbp+57h+pv], rdx
0x140007347  xor     r14d, r14d
0x14000734a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000734e  mov     r8, rbx
0x140007351  inc     r8
0x140007354  cmp     [rax+r8*2], r14w
0x140007359  jnz     short loc_140007351
0x14000735b  xorps   xmm0, xmm0
0x14000735e  movups  [rbp+57h+var_40], xmm0
0x140007362  mov     [rbp+57h+var_30], r14
0x140007366  mov     [rbp+57h+var_28], r14
0x14000736a  mov     rdx, rax
0x14000736d  lea     rcx, [rbp+57h+var_40]
0x140007371  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140007376  nop
0x140007377  mov     rcx, [rsi+8]
0x14000737b  test    rcx, rcx
0x14000737e  jz      short loc_1400073BB
0x140007380  mov     rax, [rcx]
0x140007383  mov     edx, 1
0x140007388  mov     rax, [rax+28h]
0x14000738c  call    _guard_dispatch_icall
0x140007391  inc     rbx
0x140007394  cmp     [rax+rbx*2], r14w
0x140007399  jnz     short loc_140007391
0x14000739b  xorps   xmm0, xmm0
0x14000739e  movups  [rbp+57h+var_80], xmm0
0x1400073a2  mov     [rbp+57h+var_70], r14
0x1400073a6  mov     [rbp+57h+var_68], r14
0x1400073aa  mov     r8, rbx
0x1400073ad  mov     rdx, rax
0x1400073b0  lea     rcx, [rbp+57h+var_80]
0x1400073b4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400073b9  jmp     short loc_14000741B
0x1400073bb  mov     [rbp+57h+pv], r14
0x1400073bf  lea     rcx, [rbp+57h+pv]
0x1400073c3  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x1400073c8  nop
0x1400073c9  mov     rdx, [rbp+57h+pv]
0x1400073cd  inc     rbx
0x1400073d0  cmp     [rdx+rbx*2], r14w
0x1400073d5  jnz     short loc_1400073CD
0x1400073d7  xorps   xmm0, xmm0
0x1400073da  movups  [rbp+57h+var_60], xmm0
0x1400073de  mov     [rbp+57h+var_50], r14
0x1400073e2  mov     [rbp+57h+var_48], r14
0x1400073e6  mov     r8, rbx
0x1400073e9  lea     rcx, [rbp+57h+var_60]
0x1400073ed  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400073f2  nop
0x1400073f3  mov     rcx, [rbp+57h+pv]; pv
0x1400073f7  test    rcx, rcx
0x1400073fa  jz      short loc_140007403
0x1400073fc  call    cs:__imp_CoTaskMemFree
0x140007402  nop
0x140007403  lea     rdx, [rbp+57h+var_60]
0x140007407  lea     rcx, [rbp+57h+var_80]
0x14000740b  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x140007410  nop
0x140007411  lea     rcx, [rbp+57h+var_60]
0x140007415  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000741a  nop
0x14000741b  lea     r8, [rbp+57h+var_40]; void *
0x14000741f  lea     rdx, [rbp+57h+var_80]; struct std::filesystem::path *
0x140007423  mov     rcx, rdi; Src
0x140007426  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14000742b  nop
0x14000742c  lea     rcx, [rbp+57h+var_80]
0x140007430  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007435  nop
0x140007436  lea     rcx, [rbp+57h+var_40]
0x14000743a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000743f  mov     rax, rdi
0x140007442  lea     r11, [rsp+0B0h+var_10]
0x14000744a  mov     rbx, [r11+30h]
0x14000744e  mov     rsi, [r11+38h]
0x140007452  mov     rsp, r11
0x140007455  pop     r14
0x140007457  pop     rdi
0x140007458  pop     rbp
0x140007459  retn
```
