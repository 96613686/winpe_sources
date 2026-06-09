# uus::Session::Session(wchar_t const *)

- ea: `0x180008848`
- end: `0x180008a07`
- name: `??0Session@uus@@QEAA@PEB_W@Z`
- size: `447`
- prototype: `uus::Session *__fastcall(uus::Session *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005524`

## callees

- `0x180008148`
- `0x1800082c0`
- `0x180008388`
- `0x180008714`
- `0x180008848`
- `0x180009a60`
- `0x18000a360`
- `0x18000a574`
- `0x18000a620`
- `0x18000a98c`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008902`

## pseudocode

```c
uus::Session *__fastcall uus::Session::Session(uus::Session *this, const wchar_t *a2)
{
  __int64 v3; // rbx
  __int64 v4; // r8
  struct std::filesystem::path *GuestOrNativeArchFolder; // rax
  __int64 HostArchFolder; // rax
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v9; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h]
  __int64 v11; // [rsp+40h] [rbp-C0h]
  _BYTE v12[40]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v14; // [rsp+98h] [rbp-68h]
  __int64 v15; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v16; // [rsp+A8h] [rbp-58h]
  const wchar_t *v17; // [rsp+B0h] [rbp-50h]
  __int128 v18; // [rsp+B8h] [rbp-48h] BYREF
  __m128i v19; // [rsp+C8h] [rbp-38h]
  char v20; // [rsp+D8h] [rbp-28h]
  _OWORD v21[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v22; // [rsp+100h] [rbp+0h]
  char v23[16]; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]

  v3 = 0;
  *(_QWORD *)this = &uus::Session::`vftable';
  v14 = 32;
  v15 = 3;
  v16 = 0x180000000uLL;
  v17 = a2;
  *(_OWORD *)v23 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(_WORD *)v23 = 0;
  pv = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(&pv);
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)pv + v4) );
  v9 = 0;
  v10 = 0;
  v11 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v9, pv, v4);
  if ( pv )
    CoTaskMemFree(pv);
  GuestOrNativeArchFolder = (struct std::filesystem::path *)uus::Utility::GetGuestOrNativeArchFolder(v13, &v9);
  uus::Utility::FindFileInSubFolder((std::filesystem::path *)&v18, GuestOrNativeArchFolder);
  std::wstring::~wstring(v13);
  if ( v20 )
  {
    v21[0] = v18;
    v21[1] = v19;
    v19 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v18) = 0;
    v22 = 1;
LABEL_10:
    std::wstring::~wstring(&v18);
    goto LABEL_11;
  }
  HostArchFolder = uus::Utility::GetHostArchFolder(v12, &v9);
  uus::Utility::FindFileInSubFolder(v21, HostArchFolder);
  if ( v12[32] )
    std::wstring::~wstring(v12);
  if ( v20 )
    goto LABEL_10;
LABEL_11:
  std::wstring::~wstring(&v9);
  if ( v22 )
  {
    std::filesystem::path::operator=(v23, v21);
    if ( v22 )
      std::wstring::~wstring(v21);
    v3 = uus::Utility::GetBrainSession<uus::Brain3>(v23);
  }
  std::wstring::~wstring(v23);
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x180008848  mov     [rsp-8+arg_10], rbx
0x18000884d  mov     [rsp-8+arg_18], rdi
0x180008852  push    rbp
0x180008853  lea     rbp, [rsp-30h]
0x180008858  sub     rsp, 130h
0x18000885f  mov     rax, cs:__security_cookie
0x180008866  xor     rax, rsp
0x180008869  mov     [rbp+30h+var_8], rax
0x18000886d  mov     rdi, rcx
0x180008870  mov     [rsp+130h+pv], rcx
0x180008875  xor     ebx, ebx
0x180008877  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x18000887e  mov     [rcx], rax
0x180008881  mov     [rbp+30h+var_98], 20h ; ' '
0x180008889  mov     [rbp+30h+var_90], 3
0x180008891  lea     rax, cs:180000000h
0x180008898  mov     [rbp+30h+var_88], rax
0x18000889c  mov     [rbp+30h+var_80], rdx
0x1800088a0  xorps   xmm0, xmm0
0x1800088a3  movups  xmmword ptr [rbp+30h+var_28], xmm0
0x1800088a7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800088af  movdqu  [rbp+30h+var_18], xmm1
0x1800088b4  mov     word ptr [rbp+30h+var_28], bx
0x1800088b8  mov     [rsp+130h+pv], rbx
0x1800088bd  lea     rcx, [rsp+130h+pv]
0x1800088c2  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x1800088c7  nop
0x1800088c8  mov     rdx, [rsp+130h+pv]
0x1800088cd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800088d1  inc     r8
0x1800088d4  cmp     [rdx+r8*2], bx
0x1800088d9  jnz     short loc_1800088D1
0x1800088db  xorps   xmm0, xmm0
0x1800088de  movups  [rsp+130h+var_108], xmm0
0x1800088e3  mov     [rsp+130h+var_F8], rbx
0x1800088e8  mov     [rsp+130h+var_F0], rbx
0x1800088ed  lea     rcx, [rsp+130h+var_108]
0x1800088f2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800088f7  nop
0x1800088f8  mov     rcx, [rsp+130h+pv]; pv
0x1800088fd  test    rcx, rcx
0x180008900  jz      short loc_180008909
0x180008902  call    cs:__imp_CoTaskMemFree
0x180008908  nop
0x180008909  lea     rdx, [rsp+130h+var_108]
0x18000890e  lea     rcx, [rsp+130h+var_B8]
0x180008913  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180008918  nop
0x180008919  mov     rdx, rax; struct std::filesystem::path *
0x18000891c  lea     rcx, [rbp+30h+var_78]; this
0x180008920  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)
0x180008925  nop
0x180008926  lea     rcx, [rsp+130h+var_B8]
0x18000892b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008930  cmp     [rbp+30h+var_58], bl
0x180008933  jz      short loc_18000895C
0x180008935  movups  xmm1, [rbp+30h+var_78]
0x180008939  movups  [rbp+30h+var_50], xmm1
0x18000893d  movups  xmm0, [rbp+30h+var_68]
0x180008941  movups  [rbp+30h+var_40], xmm0
0x180008945  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000894d  movdqu  [rbp+30h+var_68], xmm1
0x180008952  mov     word ptr [rbp+30h+var_78], bx
0x180008956  mov     [rbp+30h+var_30], 1
0x18000895a  jmp     short loc_18000898F
0x18000895c  lea     rdx, [rsp+130h+var_108]
0x180008961  lea     rcx, [rsp+130h+var_E0]
0x180008966  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x18000896b  nop
0x18000896c  mov     rdx, rax
0x18000896f  lea     rcx, [rbp+30h+var_50]
0x180008973  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,wchar_t const *)
0x180008978  nop
0x180008979  cmp     [rsp+130h+var_C0], bl
0x18000897d  jz      short loc_18000898A
0x18000897f  lea     rcx, [rsp+130h+var_E0]
0x180008984  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008989  nop
0x18000898a  cmp     [rbp+30h+var_58], bl
0x18000898d  jz      short loc_180008999
0x18000898f  lea     rcx, [rbp+30h+var_78]
0x180008993  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008998  nop
0x180008999  lea     rcx, [rsp+130h+var_108]
0x18000899e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800089a3  cmp     [rbp+30h+var_30], bl
0x1800089a6  jnz     short loc_1800089AA
0x1800089a8  jmp     short loc_1800089D6
0x1800089aa  lea     rdx, [rbp+30h+var_50]
0x1800089ae  lea     rcx, [rbp+30h+var_28]
0x1800089b2  call    ??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z; std::filesystem::path::operator=(std::filesystem::path &&)
0x1800089b7  nop
0x1800089b8  cmp     [rbp+30h+var_30], bl
0x1800089bb  jz      short loc_1800089C6
0x1800089bd  lea     rcx, [rbp+30h+var_50]
0x1800089c1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800089c6  lea     rdx, [rbp+30h+var_98]
0x1800089ca  lea     rcx, [rbp+30h+var_28]; char *
0x1800089ce  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x1800089d3  mov     rbx, rax
0x1800089d6  lea     rcx, [rbp+30h+var_28]
0x1800089da  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800089df  mov     [rdi+8], rbx
0x1800089e3  mov     rax, rdi
0x1800089e6  mov     rcx, [rbp+30h+var_8]
0x1800089ea  xor     rcx, rsp; StackCookie
0x1800089ed  call    __security_check_cookie
0x1800089f2  lea     r11, [rsp+130h+var_s0]
0x1800089fa  mov     rbx, [r11+20h]
0x1800089fe  mov     rdi, [r11+28h]
0x180008a02  mov     rsp, r11
0x180008a05  pop     rbp
0x180008a06  retn
```
