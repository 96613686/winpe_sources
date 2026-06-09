# uus::Session::Session(wchar_t const *)

- ea: `0x180034358`
- end: `0x180034535`
- name: `??0Session@uus@@QEAA@PEB_W@Z`
- size: `477`
- prototype: `uus::Session *__fastcall(uus::Session *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800346d8`

## callees

- `0x180033bdc`
- `0x180033cbc`
- `0x180034358`
- `0x1800367fc`
- `0x180036b74`
- `0x180036c98`
- `0x180036d14`
- `0x180036ef0`
- `0x180037798`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003440f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003440f`

## string_xrefs

- `0x1800344c6`: `uusbrain.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
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
  __int16 *v26; // [rsp+80h] [rbp+17h]
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
0x180034358  mov     [rsp-8+arg_10], rbx
0x18003435d  mov     [rsp-8+arg_18], rdi
0x180034362  push    rbp
0x180034363  lea     rbp, [rsp-57h]
0x180034368  sub     rsp, 0C0h
0x18003436f  mov     rax, cs:__security_cookie
0x180034376  xor     rax, rsp
0x180034379  mov     [rbp+57h+var_10], rax
0x18003437d  mov     rdi, rcx
0x180034380  mov     [rbp+57h+pv], rcx
0x180034384  xor     ebx, ebx
0x180034386  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x18003438d  mov     [rcx], rax
0x180034390  mov     [rbp+57h+var_50], 20h ; ' '
0x180034398  mov     [rbp+57h+var_48], 3
0x18003439f  mov     [rbp+57h+var_44], 8
0x1800343a6  lea     r8, __ImageBase
0x1800343ad  mov     [rbp+57h+var_40], r8
0x1800343b1  mov     [rbp+57h+var_38], rdx
0x1800343b5  xorps   xmm0, xmm0
0x1800343b8  movups  [rbp+57h+Src], xmm0
0x1800343bc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800343c4  movdqu  [rbp+57h+var_20], xmm1
0x1800343c9  mov     word ptr [rbp+57h+Src], bx
0x1800343cd  mov     [rbp+57h+pv], rbx
0x1800343d1  lea     rcx, [rbp+57h+pv]
0x1800343d5  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x1800343da  nop
0x1800343db  mov     rdx, [rbp+57h+pv]
0x1800343df  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800343e3  inc     r8
0x1800343e6  cmp     [rdx+r8*2], bx
0x1800343eb  jnz     short loc_1800343E3
0x1800343ed  xorps   xmm0, xmm0
0x1800343f0  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x1800343f4  mov     [rbp+57h+var_88], rbx
0x1800343f8  mov     [rbp+57h+var_80], rbx
0x1800343fc  lea     rcx, [rbp+57h+var_98]
0x180034400  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180034405  nop
0x180034406  mov     rcx, [rbp+57h+pv]; pv
0x18003440a  test    rcx, rcx
0x18003440d  jz      short loc_180034416
0x18003440f  call    cs:__imp_CoTaskMemFree
0x180034415  nop
0x180034416  lea     rcx, [rbp+57h+var_98]
0x18003441a  cmp     [rbp+57h+var_80], 7
0x18003441f  cmova   rcx, [rbp+57h+var_98]; this
0x180034424  mov     r11, [rbp+57h+var_88]
0x180034428  lea     rdx, [rcx+r11*2]; wchar_t *
0x18003442c  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180034431  jmp     short loc_180034443
0x180034433  cmp     word ptr [rax], 5Ch ; '\'
0x180034437  jz      short loc_18003443F
0x180034439  cmp     word ptr [rax], 2Fh ; '/'
0x18003443d  jnz     short loc_180034448
0x18003443f  add     rax, 2
0x180034443  cmp     rax, rdx
0x180034446  jnz     short loc_180034433
0x180034448  cmp     rax, rdx
0x18003444b  jz      short loc_180034467
0x18003444d  lea     r8, [rdx-2]
0x180034451  cmp     word ptr [r8], 5Ch ; '\'
0x180034456  jz      short loc_180034467
0x180034458  cmp     word ptr [r8], 2Fh ; '/'
0x18003445d  jz      short loc_180034467
0x18003445f  mov     rdx, r8
0x180034462  cmp     rax, r8
0x180034465  jnz     short loc_18003444D
0x180034467  sub     rdx, rcx
0x18003446a  sar     rdx, 1
0x18003446d  cmp     r11, rdx
0x180034470  jb      loc_18003452F
0x180034476  mov     [rbp+57h+var_88], rdx
0x18003447a  lea     rax, [rbp+57h+var_98]
0x18003447e  cmp     [rbp+57h+var_80], 7
0x180034483  cmova   rax, [rbp+57h+var_98]
0x180034488  mov     [rax+rdx*2], bx
0x18003448c  lea     rdx, [rbp+57h+var_98]
0x180034490  cmp     [rbp+57h+var_80], 7
0x180034495  cmova   rdx, [rbp+57h+var_98]; Src
0x18003449a  mov     r8, [rbp+57h+var_88]
0x18003449e  lea     rcx, [rbp+57h+Src]; void *
0x1800344a2  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x1800344a7  nop
0x1800344a8  lea     rcx, [rbp+57h+var_98]
0x1800344ac  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800344b1  xorps   xmm0, xmm0
0x1800344b4  movups  [rbp+57h+var_70], xmm0
0x1800344b8  mov     [rbp+57h+var_60], rbx
0x1800344bc  mov     [rbp+57h+var_58], rbx
0x1800344c0  mov     r8d, 0Ch
0x1800344c6  lea     rdx, aUusbrainDll; "uusbrain.dll"
0x1800344cd  lea     rcx, [rbp+57h+var_70]
0x1800344d1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800344d6  nop
0x1800344d7  lea     rdx, [rbp+57h+var_70]; void *
0x1800344db  lea     rcx, [rbp+57h+Src]; Src
0x1800344df  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x1800344e4  nop
0x1800344e5  lea     rcx, [rbp+57h+var_70]
0x1800344e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800344ee  lea     rdx, [rbp+57h+var_50]
0x1800344f2  lea     rcx, [rbp+57h+Src]
0x1800344f6  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x1800344fb  mov     rbx, rax
0x1800344fe  lea     rcx, [rbp+57h+Src]
0x180034502  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034507  mov     [rdi+8], rbx
0x18003450b  mov     rax, rdi
0x18003450e  mov     rcx, [rbp+57h+var_10]
0x180034512  xor     rcx, rsp; StackCookie
0x180034515  call    __security_check_cookie
0x18003451a  lea     r11, [rsp+0C0h+var_s0]
0x180034522  mov     rbx, [r11+20h]
0x180034526  mov     rdi, [r11+28h]
0x18003452a  mov     rsp, r11
0x18003452d  pop     rbp
0x18003452e  retn
0x18003452f  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
