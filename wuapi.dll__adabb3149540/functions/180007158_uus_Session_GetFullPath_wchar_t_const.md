# uus::Session::GetFullPath(wchar_t const *)

- ea: `0x180007158`
- end: `0x180007293`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z`
- size: `315`
- prototype: `void *__fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007308`

## callees

- `0x1800061a4`
- `0x180006b3c`
- `0x180007158`
- `0x1800082b4`
- `0x1800085e8`
- `0x180008868`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007235`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    uus::Utility::GetGuestOrNativeArchFolder(&v10, (struct std::filesystem::path *)&v13);
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
0x180007158  mov     [rsp-8+arg_10], rbx
0x18000715d  mov     [rsp-8+arg_18], rsi
0x180007162  push    rbp
0x180007163  push    rdi
0x180007164  push    r14
0x180007166  lea     rbp, [rsp-47h]
0x18000716b  sub     rsp, 0A0h
0x180007172  mov     rdi, rdx
0x180007175  mov     rsi, rcx
0x180007178  mov     [rbp+57h+pv], rdx
0x18000717c  xor     r14d, r14d
0x18000717f  lea     rdx, Src
0x180007186  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000718a  mov     r8, rbx
0x18000718d  inc     r8
0x180007190  cmp     [rdx+r8*2], r14w
0x180007195  jnz     short loc_18000718D
0x180007197  xorps   xmm0, xmm0
0x18000719a  movups  [rbp+57h+var_40], xmm0
0x18000719e  mov     [rbp+57h+var_30], r14
0x1800071a2  mov     [rbp+57h+var_28], r14
0x1800071a6  lea     rcx, [rbp+57h+var_40]
0x1800071aa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800071af  nop
0x1800071b0  mov     rcx, [rsi+8]
0x1800071b4  test    rcx, rcx
0x1800071b7  jz      short loc_1800071F4
0x1800071b9  mov     rax, [rcx]
0x1800071bc  mov     edx, 1
0x1800071c1  mov     rax, [rax+28h]
0x1800071c5  call    _guard_dispatch_icall
0x1800071ca  inc     rbx
0x1800071cd  cmp     [rax+rbx*2], r14w
0x1800071d2  jnz     short loc_1800071CA
0x1800071d4  xorps   xmm0, xmm0
0x1800071d7  movups  [rbp+57h+var_80], xmm0
0x1800071db  mov     [rbp+57h+var_70], r14
0x1800071df  mov     [rbp+57h+var_68], r14
0x1800071e3  mov     r8, rbx
0x1800071e6  mov     rdx, rax
0x1800071e9  lea     rcx, [rbp+57h+var_80]
0x1800071ed  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800071f2  jmp     short loc_180007254
0x1800071f4  mov     [rbp+57h+pv], r14
0x1800071f8  lea     rcx, [rbp+57h+pv]
0x1800071fc  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180007201  nop
0x180007202  mov     rdx, [rbp+57h+pv]
0x180007206  inc     rbx
0x180007209  cmp     [rdx+rbx*2], r14w
0x18000720e  jnz     short loc_180007206
0x180007210  xorps   xmm0, xmm0
0x180007213  movups  [rbp+57h+var_60], xmm0
0x180007217  mov     [rbp+57h+var_50], r14
0x18000721b  mov     [rbp+57h+var_48], r14
0x18000721f  mov     r8, rbx
0x180007222  lea     rcx, [rbp+57h+var_60]
0x180007226  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000722b  nop
0x18000722c  mov     rcx, [rbp+57h+pv]; pv
0x180007230  test    rcx, rcx
0x180007233  jz      short loc_18000723C
0x180007235  call    cs:__imp_CoTaskMemFree
0x18000723b  nop
0x18000723c  lea     rdx, [rbp+57h+var_60]
0x180007240  lea     rcx, [rbp+57h+var_80]
0x180007244  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180007249  nop
0x18000724a  lea     rcx, [rbp+57h+var_60]
0x18000724e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007253  nop
0x180007254  lea     r8, [rbp+57h+var_40]; void *
0x180007258  lea     rdx, [rbp+57h+var_80]; struct std::filesystem::path *
0x18000725c  mov     rcx, rdi; Src
0x18000725f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180007264  nop
0x180007265  lea     rcx, [rbp+57h+var_80]
0x180007269  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000726e  nop
0x18000726f  lea     rcx, [rbp+57h+var_40]
0x180007273  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007278  mov     rax, rdi
0x18000727b  lea     r11, [rsp+0B0h+var_10]
0x180007283  mov     rbx, [r11+30h]
0x180007287  mov     rsi, [r11+38h]
0x18000728b  mov     rsp, r11
0x18000728e  pop     r14
0x180007290  pop     rdi
0x180007291  pop     rbp
0x180007292  retn
```
