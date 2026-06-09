# uus::Session::GetFullPath(wchar_t const *)

- ea: `0x18003453c`
- end: `0x18003465e`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z`
- size: `290`
- prototype: `struct std::filesystem::path __high(const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800346d8`

## callees

- `0x180033f24`
- `0x18003427c`
- `0x18003453c`
- `0x1800368b0`
- `0x180036c98`
- `0x180036d14`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034605`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall uus::Session::GetFullPath(__int64 a1, void *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // r8
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
  v16 = 0;
  v17 = 0;
  v18 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, L"wuaucltcore.exe");
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    v10 = 0;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v10, v5);
  }
  else
  {
    pv[0] = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(pv);
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)pv[0] + v7) );
    v13 = 0;
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v13, pv[0]);
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
0x18003453c  mov     [rsp-8+arg_10], rbx
0x180034541  push    rbp
0x180034542  push    rsi
0x180034543  push    rdi
0x180034544  lea     rbp, [rsp-47h]
0x180034549  sub     rsp, 0A0h
0x180034550  mov     rdi, rdx
0x180034553  mov     rbx, rcx
0x180034556  mov     [rbp+57h+pv], rdx
0x18003455a  xor     esi, esi
0x18003455c  xorps   xmm0, xmm0
0x18003455f  movups  [rbp+57h+var_40], xmm0
0x180034563  mov     [rbp+57h+var_30], rsi
0x180034567  mov     [rbp+57h+var_28], rsi
0x18003456b  lea     r8d, [rsi+0Fh]
0x18003456f  lea     rdx, ?c_szWuaucltCoreExe@@3QB_WB; "wuaucltcore.exe"
0x180034576  lea     rcx, [rbp+57h+var_40]
0x18003457a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003457f  nop
0x180034580  mov     rcx, [rbx+8]
0x180034584  test    rcx, rcx
0x180034587  jz      short loc_1800345C3
0x180034589  mov     rax, [rcx]
0x18003458c  lea     edx, [rsi+1]
0x18003458f  mov     rax, [rax+28h]
0x180034593  call    _guard_dispatch_icall
0x180034598  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003459c  inc     r8
0x18003459f  cmp     [rax+r8*2], si
0x1800345a4  jnz     short loc_18003459C
0x1800345a6  xorps   xmm0, xmm0
0x1800345a9  movups  [rbp+57h+var_80], xmm0
0x1800345ad  mov     [rbp+57h+var_70], rsi
0x1800345b1  mov     [rbp+57h+var_68], rsi
0x1800345b5  mov     rdx, rax
0x1800345b8  lea     rcx, [rbp+57h+var_80]
0x1800345bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800345c1  jmp     short loc_180034624
0x1800345c3  mov     [rbp+57h+pv], rsi
0x1800345c7  lea     rcx, [rbp+57h+pv]
0x1800345cb  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x1800345d0  nop
0x1800345d1  mov     rdx, [rbp+57h+pv]
0x1800345d5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800345d9  inc     r8
0x1800345dc  cmp     [rdx+r8*2], si
0x1800345e1  jnz     short loc_1800345D9
0x1800345e3  xorps   xmm0, xmm0
0x1800345e6  movups  [rbp+57h+var_60], xmm0
0x1800345ea  mov     [rbp+57h+var_50], rsi
0x1800345ee  mov     [rbp+57h+var_48], rsi
0x1800345f2  lea     rcx, [rbp+57h+var_60]
0x1800345f6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800345fb  nop
0x1800345fc  mov     rcx, [rbp+57h+pv]; pv
0x180034600  test    rcx, rcx
0x180034603  jz      short loc_18003460C
0x180034605  call    cs:__imp_CoTaskMemFree
0x18003460b  nop
0x18003460c  lea     rdx, [rbp+57h+var_60]
0x180034610  lea     rcx, [rbp+57h+var_80]
0x180034614  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180034619  nop
0x18003461a  lea     rcx, [rbp+57h+var_60]
0x18003461e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034623  nop
0x180034624  lea     r8, [rbp+57h+var_40]; void *
0x180034628  lea     rdx, [rbp+57h+var_80]; struct std::filesystem::path *
0x18003462c  mov     rcx, rdi; Src
0x18003462f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180034634  nop
0x180034635  lea     rcx, [rbp+57h+var_80]
0x180034639  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003463e  nop
0x18003463f  lea     rcx, [rbp+57h+var_40]
0x180034643  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034648  mov     rax, rdi
0x18003464b  mov     rbx, [rsp+0B0h+arg_10]
0x180034653  add     rsp, 0A0h
0x18003465a  pop     rdi
0x18003465b  pop     rsi
0x18003465c  pop     rbp
0x18003465d  retn
```
