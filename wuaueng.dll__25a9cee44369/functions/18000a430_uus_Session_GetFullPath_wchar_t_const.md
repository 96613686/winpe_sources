# uus::Session::GetFullPath(wchar_t const *)

- ea: `0x18000a430`
- end: `0x18000a56b`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z`
- size: `315`
- prototype: `void *__fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005524`

## callees

- `0x1800098b8`
- `0x180009a60`
- `0x18000a360`
- `0x18000a430`
- `0x18000a620`
- `0x18000a98c`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a50d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a50d`

## pseudocode

```c
void *__fastcall uus::Session::GetFullPath(__int64 a1, void *a2)
{
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  LPVOID pv[2]; // [rsp+20h] [rbp-39h] BYREF
  __int128 v10; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+40h] [rbp-19h]
  __int64 v12; // [rsp+48h] [rbp-11h]
  __int128 v13; // [rsp+50h] [rbp-9h] BYREF
  __int64 v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  __int128 v16; // [rsp+70h] [rbp+17h] BYREF
  __int64 v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  pv[0] = a2;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(&Src + v5) );
  v16 = 0;
  v17 = 0;
  v18 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, &Src, v5);
  v6 = *(_QWORD *)(a1 + 8);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
    do
      ++v4;
    while ( *(_WORD *)(v7 + 2 * v4) );
    v10 = 0;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v10, v7, v4);
  }
  else
  {
    pv[0] = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(pv);
    do
      ++v4;
    while ( *((_WORD *)pv[0] + v4) );
    v13 = 0;
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v13, pv[0], v4);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    uus::Utility::GetGuestOrNativeArchFolder(&v10, &v13);
    std::wstring::~wstring(&v13);
  }
  std::filesystem::operator/(a2, (struct std::filesystem::path *)&v10, &v16);
  std::wstring::~wstring(&v10);
  std::wstring::~wstring(&v16);
  return a2;
}

```

## disassembly

```asm
0x18000a430  mov     [rsp-8+arg_10], rbx
0x18000a435  mov     [rsp-8+arg_18], rsi
0x18000a43a  push    rbp
0x18000a43b  push    rdi
0x18000a43c  push    r14
0x18000a43e  lea     rbp, [rsp-47h]
0x18000a443  sub     rsp, 0A0h
0x18000a44a  mov     rdi, rdx
0x18000a44d  mov     rsi, rcx
0x18000a450  mov     [rbp+57h+pv], rdx
0x18000a454  xor     r14d, r14d
0x18000a457  lea     rdx, Src
0x18000a45e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a462  mov     r8, rbx
0x18000a465  inc     r8
0x18000a468  cmp     [rdx+r8*2], r14w
0x18000a46d  jnz     short loc_18000A465
0x18000a46f  xorps   xmm0, xmm0
0x18000a472  movups  [rbp+57h+var_40], xmm0
0x18000a476  mov     [rbp+57h+var_30], r14
0x18000a47a  mov     [rbp+57h+var_28], r14
0x18000a47e  lea     rcx, [rbp+57h+var_40]
0x18000a482  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000a487  nop
0x18000a488  mov     rcx, [rsi+8]
0x18000a48c  test    rcx, rcx
0x18000a48f  jz      short loc_18000A4CC
0x18000a491  mov     rax, [rcx]
0x18000a494  mov     edx, 1
0x18000a499  mov     rax, [rax+28h]
0x18000a49d  call    _guard_dispatch_icall
0x18000a4a2  inc     rbx
0x18000a4a5  cmp     [rax+rbx*2], r14w
0x18000a4aa  jnz     short loc_18000A4A2
0x18000a4ac  xorps   xmm0, xmm0
0x18000a4af  movups  [rbp+57h+var_80], xmm0
0x18000a4b3  mov     [rbp+57h+var_70], r14
0x18000a4b7  mov     [rbp+57h+var_68], r14
0x18000a4bb  mov     r8, rbx
0x18000a4be  mov     rdx, rax
0x18000a4c1  lea     rcx, [rbp+57h+var_80]
0x18000a4c5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000a4ca  jmp     short loc_18000A52C
0x18000a4cc  mov     [rbp+57h+pv], r14
0x18000a4d0  lea     rcx, [rbp+57h+pv]
0x18000a4d4  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18000a4d9  nop
0x18000a4da  mov     rdx, [rbp+57h+pv]
0x18000a4de  inc     rbx
0x18000a4e1  cmp     [rdx+rbx*2], r14w
0x18000a4e6  jnz     short loc_18000A4DE
0x18000a4e8  xorps   xmm0, xmm0
0x18000a4eb  movups  [rbp+57h+var_60], xmm0
0x18000a4ef  mov     [rbp+57h+var_50], r14
0x18000a4f3  mov     [rbp+57h+var_48], r14
0x18000a4f7  mov     r8, rbx
0x18000a4fa  lea     rcx, [rbp+57h+var_60]
0x18000a4fe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000a503  nop
0x18000a504  mov     rcx, [rbp+57h+pv]; pv
0x18000a508  test    rcx, rcx
0x18000a50b  jz      short loc_18000A514
0x18000a50d  call    cs:__imp_CoTaskMemFree
0x18000a513  nop
0x18000a514  lea     rdx, [rbp+57h+var_60]
0x18000a518  lea     rcx, [rbp+57h+var_80]
0x18000a51c  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x18000a521  nop
0x18000a522  lea     rcx, [rbp+57h+var_60]
0x18000a526  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a52b  nop
0x18000a52c  lea     r8, [rbp+57h+var_40]; void *
0x18000a530  lea     rdx, [rbp+57h+var_80]; struct std::filesystem::path *
0x18000a534  mov     rcx, rdi; Src
0x18000a537  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000a53c  nop
0x18000a53d  lea     rcx, [rbp+57h+var_80]
0x18000a541  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a546  nop
0x18000a547  lea     rcx, [rbp+57h+var_40]
0x18000a54b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a550  mov     rax, rdi
0x18000a553  lea     r11, [rsp+0B0h+var_10]
0x18000a55b  mov     rbx, [r11+30h]
0x18000a55f  mov     rsi, [r11+38h]
0x18000a563  mov     rsp, r11
0x18000a566  pop     r14
0x18000a568  pop     rdi
0x18000a569  pop     rbp
0x18000a56a  retn
```
