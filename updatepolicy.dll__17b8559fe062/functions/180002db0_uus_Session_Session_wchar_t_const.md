# uus::Session::Session(wchar_t const *)

- ea: `0x180002db0`
- end: `0x180002f6f`
- name: `??0Session@uus@@QEAA@PEB_W@Z`
- size: `447`
- prototype: `uus::Session *__fastcall(uus::Session *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003128`

## callees

- `0x1800027e4`
- `0x18000297c`
- `0x180002a14`
- `0x180002b10`
- `0x180002bd8`
- `0x180002db0`
- `0x180004348`
- `0x1800049c4`
- `0x18000593c`
- `0x1800078ac`
- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e6a`

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
  __int16 *v16; // [rsp+A8h] [rbp-58h]
  const wchar_t *v17; // [rsp+B0h] [rbp-50h]
  __int128 v18; // [rsp+B8h] [rbp-48h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-38h]
  char v20; // [rsp+D8h] [rbp-28h]
  _OWORD v21[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v22; // [rsp+100h] [rbp+0h]
  _OWORD v23[2]; // [rsp+108h] [rbp+8h] BYREF

  v3 = 0;
  *(_QWORD *)this = &uus::Session::`vftable';
  v14 = 32;
  v15 = 3;
  v16 = &_ImageBase;
  v17 = a2;
  v23[0] = 0;
  v23[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23[0]) = 0;
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
    v21[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
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
    v3 = uus::Utility::GetBrainSession<uus::Brain3>((char *)v23);
  }
  std::wstring::~wstring(v23);
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x180002db0  mov     [rsp-8+arg_10], rbx
0x180002db5  mov     [rsp-8+arg_18], rdi
0x180002dba  push    rbp
0x180002dbb  lea     rbp, [rsp-30h]
0x180002dc0  sub     rsp, 130h
0x180002dc7  mov     rax, cs:__security_cookie
0x180002dce  xor     rax, rsp
0x180002dd1  mov     [rbp+30h+var_8], rax
0x180002dd5  mov     rdi, rcx
0x180002dd8  mov     [rsp+130h+pv], rcx
0x180002ddd  xor     ebx, ebx
0x180002ddf  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x180002de6  mov     [rcx], rax
0x180002de9  mov     [rbp+30h+var_98], 20h ; ' '
0x180002df1  mov     [rbp+30h+var_90], 3
0x180002df9  lea     rax, __ImageBase
0x180002e00  mov     [rbp+30h+var_88], rax
0x180002e04  mov     [rbp+30h+var_80], rdx
0x180002e08  xorps   xmm0, xmm0
0x180002e0b  movups  [rbp+30h+var_28], xmm0
0x180002e0f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180002e17  movdqu  [rbp+30h+var_18], xmm1
0x180002e1c  mov     word ptr [rbp+30h+var_28], bx
0x180002e20  mov     [rsp+130h+pv], rbx
0x180002e25  lea     rcx, [rsp+130h+pv]
0x180002e2a  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180002e2f  nop
0x180002e30  mov     rdx, [rsp+130h+pv]
0x180002e35  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002e39  inc     r8
0x180002e3c  cmp     [rdx+r8*2], bx
0x180002e41  jnz     short loc_180002E39
0x180002e43  xorps   xmm0, xmm0
0x180002e46  movups  [rsp+130h+var_108], xmm0
0x180002e4b  mov     [rsp+130h+var_F8], rbx
0x180002e50  mov     [rsp+130h+var_F0], rbx
0x180002e55  lea     rcx, [rsp+130h+var_108]
0x180002e5a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002e5f  nop
0x180002e60  mov     rcx, [rsp+130h+pv]; pv
0x180002e65  test    rcx, rcx
0x180002e68  jz      short loc_180002E71
0x180002e6a  call    cs:__imp_CoTaskMemFree
0x180002e70  nop
0x180002e71  lea     rdx, [rsp+130h+var_108]
0x180002e76  lea     rcx, [rsp+130h+var_B8]
0x180002e7b  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180002e80  nop
0x180002e81  mov     rdx, rax; struct std::filesystem::path *
0x180002e84  lea     rcx, [rbp+30h+var_78]; this
0x180002e88  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)
0x180002e8d  nop
0x180002e8e  lea     rcx, [rsp+130h+var_B8]
0x180002e93  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002e98  cmp     [rbp+30h+var_58], bl
0x180002e9b  jz      short loc_180002EC4
0x180002e9d  movups  xmm1, [rbp+30h+var_78]
0x180002ea1  movups  [rbp+30h+var_50], xmm1
0x180002ea5  movups  xmm0, [rbp+30h+var_68]
0x180002ea9  movups  [rbp+30h+var_40], xmm0
0x180002ead  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180002eb5  movdqu  [rbp+30h+var_68], xmm1
0x180002eba  mov     word ptr [rbp+30h+var_78], bx
0x180002ebe  mov     [rbp+30h+var_30], 1
0x180002ec2  jmp     short loc_180002EF7
0x180002ec4  lea     rdx, [rsp+130h+var_108]
0x180002ec9  lea     rcx, [rsp+130h+var_E0]
0x180002ece  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x180002ed3  nop
0x180002ed4  mov     rdx, rax
0x180002ed7  lea     rcx, [rbp+30h+var_50]
0x180002edb  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,wchar_t const *)
0x180002ee0  nop
0x180002ee1  cmp     [rsp+130h+var_C0], bl
0x180002ee5  jz      short loc_180002EF2
0x180002ee7  lea     rcx, [rsp+130h+var_E0]
0x180002eec  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002ef1  nop
0x180002ef2  cmp     [rbp+30h+var_58], bl
0x180002ef5  jz      short loc_180002F01
0x180002ef7  lea     rcx, [rbp+30h+var_78]
0x180002efb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002f00  nop
0x180002f01  lea     rcx, [rsp+130h+var_108]
0x180002f06  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002f0b  cmp     [rbp+30h+var_30], bl
0x180002f0e  jnz     short loc_180002F12
0x180002f10  jmp     short loc_180002F3E
0x180002f12  lea     rdx, [rbp+30h+var_50]
0x180002f16  lea     rcx, [rbp+30h+var_28]
0x180002f1a  call    ??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z; std::filesystem::path::operator=(std::filesystem::path &&)
0x180002f1f  nop
0x180002f20  cmp     [rbp+30h+var_30], bl
0x180002f23  jz      short loc_180002F2E
0x180002f25  lea     rcx, [rbp+30h+var_50]
0x180002f29  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002f2e  lea     rdx, [rbp+30h+var_98]
0x180002f32  lea     rcx, [rbp+30h+var_28]
0x180002f36  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x180002f3b  mov     rbx, rax
0x180002f3e  lea     rcx, [rbp+30h+var_28]
0x180002f42  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002f47  mov     [rdi+8], rbx
0x180002f4b  mov     rax, rdi
0x180002f4e  mov     rcx, [rbp+30h+var_8]
0x180002f52  xor     rcx, rsp; StackCookie
0x180002f55  call    __security_check_cookie
0x180002f5a  lea     r11, [rsp+130h+var_s0]
0x180002f62  mov     rbx, [r11+20h]
0x180002f66  mov     rdi, [r11+28h]
0x180002f6a  mov     rsp, r11
0x180002f6d  pop     rbp
0x180002f6e  retn
```
