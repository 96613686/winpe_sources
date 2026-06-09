# uus::Session::Session(wchar_t const *)

- ea: `0x180006f90`
- end: `0x18000714f`
- name: `??0Session@uus@@QEAA@PEB_W@Z`
- size: `447`
- prototype: `uus::Session *__fastcall(uus::Session *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007308`

## callees

- `0x1800069a4`
- `0x180006b3c`
- `0x180006bd4`
- `0x180006cd0`
- `0x180006d98`
- `0x180006f90`
- `0x1800082b4`
- `0x1800085e8`
- `0x180008868`
- `0x180008a44`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000704a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000704a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  _QWORD v14[4]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v15; // [rsp+B8h] [rbp-48h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-38h]
  char v17; // [rsp+D8h] [rbp-28h]
  _OWORD v18[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v19; // [rsp+100h] [rbp+0h]
  _OWORD v20[2]; // [rsp+108h] [rbp+8h] BYREF

  v3 = 0;
  *(_QWORD *)this = &uus::Session::`vftable';
  v14[0] = 32;
  v14[1] = 3;
  v14[2] = 0x180000000uLL;
  v14[3] = a2;
  v20[0] = 0;
  v20[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v20[0]) = 0;
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
  uus::Utility::FindFileInSubFolder((std::filesystem::path *)&v15, GuestOrNativeArchFolder);
  std::wstring::~wstring(v13);
  if ( v17 )
  {
    v18[0] = v15;
    v18[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15) = 0;
    v19 = 1;
LABEL_10:
    std::wstring::~wstring(&v15);
    goto LABEL_11;
  }
  HostArchFolder = uus::Utility::GetHostArchFolder(v12, &v9);
  uus::Utility::FindFileInSubFolder(v18, HostArchFolder);
  if ( v12[32] )
    std::wstring::~wstring(v12);
  if ( v17 )
    goto LABEL_10;
LABEL_11:
  std::wstring::~wstring(&v9);
  if ( v19 )
  {
    std::filesystem::path::operator=(v20, v18);
    if ( v19 )
      std::wstring::~wstring(v18);
    v3 = uus::Utility::GetBrainSession<uus::Brain3>((char *)v20, (__int64)v14);
  }
  std::wstring::~wstring(v20);
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x180006f90  mov     [rsp-8+arg_10], rbx
0x180006f95  mov     [rsp-8+arg_18], rdi
0x180006f9a  push    rbp
0x180006f9b  lea     rbp, [rsp-30h]
0x180006fa0  sub     rsp, 130h
0x180006fa7  mov     rax, cs:__security_cookie
0x180006fae  xor     rax, rsp
0x180006fb1  mov     [rbp+30h+var_8], rax
0x180006fb5  mov     rdi, rcx
0x180006fb8  mov     [rsp+130h+pv], rcx
0x180006fbd  xor     ebx, ebx
0x180006fbf  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x180006fc6  mov     [rcx], rax
0x180006fc9  mov     [rbp+30h+var_98], 20h ; ' '
0x180006fd1  mov     [rbp+30h+var_90], 3
0x180006fd9  lea     rax, cs:180000000h
0x180006fe0  mov     [rbp+30h+var_88], rax
0x180006fe4  mov     [rbp+30h+var_80], rdx
0x180006fe8  xorps   xmm0, xmm0
0x180006feb  movups  [rbp+30h+var_28], xmm0
0x180006fef  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180006ff7  movdqu  [rbp+30h+var_18], xmm1
0x180006ffc  mov     word ptr [rbp+30h+var_28], bx
0x180007000  mov     [rsp+130h+pv], rbx
0x180007005  lea     rcx, [rsp+130h+pv]
0x18000700a  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18000700f  nop
0x180007010  mov     rdx, [rsp+130h+pv]
0x180007015  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007019  inc     r8
0x18000701c  cmp     [rdx+r8*2], bx
0x180007021  jnz     short loc_180007019
0x180007023  xorps   xmm0, xmm0
0x180007026  movups  [rsp+130h+var_108], xmm0
0x18000702b  mov     [rsp+130h+var_F8], rbx
0x180007030  mov     [rsp+130h+var_F0], rbx
0x180007035  lea     rcx, [rsp+130h+var_108]
0x18000703a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000703f  nop
0x180007040  mov     rcx, [rsp+130h+pv]; pv
0x180007045  test    rcx, rcx
0x180007048  jz      short loc_180007051
0x18000704a  call    cs:__imp_CoTaskMemFree
0x180007050  nop
0x180007051  lea     rdx, [rsp+130h+var_108]
0x180007056  lea     rcx, [rsp+130h+var_B8]
0x18000705b  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180007060  nop
0x180007061  mov     rdx, rax; struct std::filesystem::path *
0x180007064  lea     rcx, [rbp+30h+var_78]; this
0x180007068  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)
0x18000706d  nop
0x18000706e  lea     rcx, [rsp+130h+var_B8]
0x180007073  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007078  cmp     [rbp+30h+var_58], bl
0x18000707b  jz      short loc_1800070A4
0x18000707d  movups  xmm1, [rbp+30h+var_78]
0x180007081  movups  [rbp+30h+var_50], xmm1
0x180007085  movups  xmm0, [rbp+30h+var_68]
0x180007089  movups  [rbp+30h+var_40], xmm0
0x18000708d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180007095  movdqu  [rbp+30h+var_68], xmm1
0x18000709a  mov     word ptr [rbp+30h+var_78], bx
0x18000709e  mov     [rbp+30h+var_30], 1
0x1800070a2  jmp     short loc_1800070D7
0x1800070a4  lea     rdx, [rsp+130h+var_108]
0x1800070a9  lea     rcx, [rsp+130h+var_E0]
0x1800070ae  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x1800070b3  nop
0x1800070b4  mov     rdx, rax
0x1800070b7  lea     rcx, [rbp+30h+var_50]
0x1800070bb  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,wchar_t const *)
0x1800070c0  nop
0x1800070c1  cmp     [rsp+130h+var_C0], bl
0x1800070c5  jz      short loc_1800070D2
0x1800070c7  lea     rcx, [rsp+130h+var_E0]
0x1800070cc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800070d1  nop
0x1800070d2  cmp     [rbp+30h+var_58], bl
0x1800070d5  jz      short loc_1800070E1
0x1800070d7  lea     rcx, [rbp+30h+var_78]
0x1800070db  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800070e0  nop
0x1800070e1  lea     rcx, [rsp+130h+var_108]
0x1800070e6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800070eb  cmp     [rbp+30h+var_30], bl
0x1800070ee  jnz     short loc_1800070F2
0x1800070f0  jmp     short loc_18000711E
0x1800070f2  lea     rdx, [rbp+30h+var_50]
0x1800070f6  lea     rcx, [rbp+30h+var_28]
0x1800070fa  call    ??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z; std::filesystem::path::operator=(std::filesystem::path &&)
0x1800070ff  nop
0x180007100  cmp     [rbp+30h+var_30], bl
0x180007103  jz      short loc_18000710E
0x180007105  lea     rcx, [rbp+30h+var_50]
0x180007109  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000710e  lea     rdx, [rbp+30h+var_98]
0x180007112  lea     rcx, [rbp+30h+var_28]
0x180007116  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x18000711b  mov     rbx, rax
0x18000711e  lea     rcx, [rbp+30h+var_28]
0x180007122  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007127  mov     [rdi+8], rbx
0x18000712b  mov     rax, rdi
0x18000712e  mov     rcx, [rbp+30h+var_8]
0x180007132  xor     rcx, rsp; StackCookie
0x180007135  call    __security_check_cookie
0x18000713a  lea     r11, [rsp+130h+var_s0]
0x180007142  mov     rbx, [r11+20h]
0x180007146  mov     rdi, [r11+28h]
0x18000714a  mov     rsp, r11
0x18000714d  pop     rbp
0x18000714e  retn
```
