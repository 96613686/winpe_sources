# uus::Session::Session(wchar_t const *)

- ea: `0x14000713c`
- end: `0x140007319`
- name: `??0Session@uus@@QEAA@PEB_W@Z`
- size: `477`
- prototype: `__int64 __fastcall(uus::Session *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400074c8`

## callees

- `0x1400069c0`
- `0x140006aa0`
- `0x14000713c`
- `0x140008f20`
- `0x1400090f0`
- `0x140009214`
- `0x140009340`
- `0x14000951c`
- `0x140009bb0`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400071f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400071f3`

## string_xrefs

- `0x1400072aa`: `uusbrain.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
uus::Session *__fastcall uus::Session::Session(uus::Session *this, const wchar_t *a2)
{
  __int64 v3; // r8
  const wchar_t *v4; // r8
  std::filesystem *v5; // rcx
  const wchar_t *i; // rax
  const wchar_t *v7; // rdx
  __int64 v8; // rcx
  unsigned __int64 v9; // r11
  const wchar_t *v10; // r8
  unsigned __int64 v11; // rdx
  std::filesystem **v12; // rax
  std::filesystem **v13; // rdx
  __int64 v14; // rbx
  LPVOID pv; // [rsp+20h] [rbp-49h] BYREF
  std::filesystem *v17[2]; // [rsp+28h] [rbp-41h] BYREF
  unsigned __int64 v18; // [rsp+38h] [rbp-31h]
  unsigned __int64 v19; // [rsp+40h] [rbp-29h]
  __int128 v20; // [rsp+50h] [rbp-19h] BYREF
  __int64 v21; // [rsp+60h] [rbp-9h]
  __int64 v22; // [rsp+68h] [rbp-1h]
  __int64 v23; // [rsp+70h] [rbp+7h] BYREF
  int v24; // [rsp+78h] [rbp+Fh]
  int v25; // [rsp+7Ch] [rbp+13h]
  struct HINSTANCE__ *v26; // [rsp+80h] [rbp+17h]
  const wchar_t *v27; // [rsp+88h] [rbp+1Fh]
  _OWORD Src[2]; // [rsp+90h] [rbp+27h] BYREF

  *(_QWORD *)this = &uus::Session::`vftable';
  v23 = 32;
  v24 = 3;
  v25 = 8;
  v26 = &_ImageBase;
  v27 = a2;
  Src[0] = 0;
  Src[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  pv = 0;
  wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(&pv);
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)pv + v3) );
  *(_OWORD *)v17 = 0;
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v17, pv);
  if ( pv )
    CoTaskMemFree(pv);
  v5 = (std::filesystem *)v17;
  if ( v19 > 7 )
    v5 = v17[0];
  for ( i = std::filesystem::_Find_root_name_end(v5, (const wchar_t *const)v5 + v18, v4);
        i != v7 && (*i == 92 || *i == 47);
        ++i )
  {
    ;
  }
  if ( i != v7 )
  {
    do
    {
      v10 = v7 - 1;
      if ( *(v7 - 1) == 92 )
        break;
      if ( *v10 == 47 )
        break;
      --v7;
    }
    while ( i != v10 );
  }
  v11 = ((__int64)v7 - v8) >> 1;
  if ( v9 < v11 )
    std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
  v18 = v11;
  v12 = v17;
  if ( v19 > 7 )
    v12 = (std::filesystem **)v17[0];
  *((_WORD *)v12 + v11) = 0;
  v13 = v17;
  if ( v19 > 7 )
    v13 = (std::filesystem **)v17[0];
  std::wstring::assign(Src, v13);
  std::wstring::~wstring(v17);
  v20 = 0;
  v21 = 0;
  v22 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v20, L"uusbrain.dll");
  std::filesystem::path::operator/=(Src, &v20);
  std::wstring::~wstring(&v20);
  v14 = uus::Utility::GetBrainSession<uus::Brain3>((char *)Src, (__int64)&v23);
  std::wstring::~wstring(Src);
  *((_QWORD *)this + 1) = v14;
  return this;
}

```

## disassembly

```asm
0x14000713c  mov     [rsp-8+arg_10], rbx
0x140007141  mov     [rsp-8+arg_18], rdi
0x140007146  push    rbp
0x140007147  lea     rbp, [rsp-57h]
0x14000714c  sub     rsp, 0C0h
0x140007153  mov     rax, cs:__security_cookie
0x14000715a  xor     rax, rsp
0x14000715d  mov     [rbp+57h+var_10], rax
0x140007161  mov     rdi, rcx
0x140007164  mov     [rbp+57h+pv], rcx
0x140007168  xor     ebx, ebx
0x14000716a  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x140007171  mov     [rcx], rax
0x140007174  mov     [rbp+57h+var_50], 20h ; ' '
0x14000717c  mov     [rbp+57h+var_48], 3
0x140007183  mov     [rbp+57h+var_44], 8
0x14000718a  lea     r8, __ImageBase
0x140007191  mov     [rbp+57h+var_40], r8
0x140007195  mov     [rbp+57h+var_38], rdx
0x140007199  xorps   xmm0, xmm0
0x14000719c  movups  [rbp+57h+Src], xmm0
0x1400071a0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400071a8  movdqu  [rbp+57h+var_20], xmm1
0x1400071ad  mov     word ptr [rbp+57h+Src], bx
0x1400071b1  mov     [rbp+57h+pv], rbx
0x1400071b5  lea     rcx, [rbp+57h+pv]
0x1400071b9  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x1400071be  nop
0x1400071bf  mov     rdx, [rbp+57h+pv]
0x1400071c3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400071c7  inc     r8
0x1400071ca  cmp     [rdx+r8*2], bx
0x1400071cf  jnz     short loc_1400071C7
0x1400071d1  xorps   xmm0, xmm0
0x1400071d4  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x1400071d8  mov     [rbp+57h+var_88], rbx
0x1400071dc  mov     [rbp+57h+var_80], rbx
0x1400071e0  lea     rcx, [rbp+57h+var_98]
0x1400071e4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400071e9  nop
0x1400071ea  mov     rcx, [rbp+57h+pv]; pv
0x1400071ee  test    rcx, rcx
0x1400071f1  jz      short loc_1400071FA
0x1400071f3  call    cs:__imp_CoTaskMemFree
0x1400071f9  nop
0x1400071fa  lea     rcx, [rbp+57h+var_98]
0x1400071fe  cmp     [rbp+57h+var_80], 7
0x140007203  cmova   rcx, [rbp+57h+var_98]; this
0x140007208  mov     r11, [rbp+57h+var_88]
0x14000720c  lea     rdx, [rcx+r11*2]; wchar_t *
0x140007210  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x140007215  jmp     short loc_140007227
0x140007217  cmp     word ptr [rax], 5Ch ; '\'
0x14000721b  jz      short loc_140007223
0x14000721d  cmp     word ptr [rax], 2Fh ; '/'
0x140007221  jnz     short loc_14000722C
0x140007223  add     rax, 2
0x140007227  cmp     rax, rdx
0x14000722a  jnz     short loc_140007217
0x14000722c  cmp     rax, rdx
0x14000722f  jz      short loc_14000724B
0x140007231  lea     r8, [rdx-2]
0x140007235  cmp     word ptr [r8], 5Ch ; '\'
0x14000723a  jz      short loc_14000724B
0x14000723c  cmp     word ptr [r8], 2Fh ; '/'
0x140007241  jz      short loc_14000724B
0x140007243  mov     rdx, r8
0x140007246  cmp     rax, r8
0x140007249  jnz     short loc_140007231
0x14000724b  sub     rdx, rcx
0x14000724e  sar     rdx, 1
0x140007251  cmp     r11, rdx
0x140007254  jb      loc_140007313
0x14000725a  mov     [rbp+57h+var_88], rdx
0x14000725e  lea     rax, [rbp+57h+var_98]
0x140007262  cmp     [rbp+57h+var_80], 7
0x140007267  cmova   rax, [rbp+57h+var_98]
0x14000726c  mov     [rax+rdx*2], bx
0x140007270  lea     rdx, [rbp+57h+var_98]
0x140007274  cmp     [rbp+57h+var_80], 7
0x140007279  cmova   rdx, [rbp+57h+var_98]; Src
0x14000727e  mov     r8, [rbp+57h+var_88]
0x140007282  lea     rcx, [rbp+57h+Src]; void *
0x140007286  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x14000728b  nop
0x14000728c  lea     rcx, [rbp+57h+var_98]
0x140007290  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007295  xorps   xmm0, xmm0
0x140007298  movups  [rbp+57h+var_70], xmm0
0x14000729c  mov     [rbp+57h+var_60], rbx
0x1400072a0  mov     [rbp+57h+var_58], rbx
0x1400072a4  mov     r8d, 0Ch
0x1400072aa  lea     rdx, aUusbrainDll; "uusbrain.dll"
0x1400072b1  lea     rcx, [rbp+57h+var_70]
0x1400072b5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400072ba  nop
0x1400072bb  lea     rdx, [rbp+57h+var_70]; void *
0x1400072bf  lea     rcx, [rbp+57h+Src]; Src
0x1400072c3  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x1400072c8  nop
0x1400072c9  lea     rcx, [rbp+57h+var_70]
0x1400072cd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400072d2  lea     rdx, [rbp+57h+var_50]
0x1400072d6  lea     rcx, [rbp+57h+Src]
0x1400072da  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x1400072df  mov     rbx, rax
0x1400072e2  lea     rcx, [rbp+57h+Src]
0x1400072e6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400072eb  mov     [rdi+8], rbx
0x1400072ef  mov     rax, rdi
0x1400072f2  mov     rcx, [rbp+57h+var_10]
0x1400072f6  xor     rcx, rsp; StackCookie
0x1400072f9  call    __security_check_cookie
0x1400072fe  lea     r11, [rsp+0C0h+var_s0]
0x140007306  mov     rbx, [r11+20h]
0x14000730a  mov     rdi, [r11+28h]
0x14000730e  mov     rsp, r11
0x140007311  pop     rbp
0x140007312  retn
0x140007313  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
