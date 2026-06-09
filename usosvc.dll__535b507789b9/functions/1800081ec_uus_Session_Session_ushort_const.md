# uus::Session::Session(ushort const *)

- ea: `0x1800081ec`
- end: `0x180008374`
- name: `??0Session@uus@@QEAA@PEBG@Z`
- size: `392`
- prototype: `uus::Session *__fastcall(uus::Session *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180009bf0`
- `0x18000c0b0`

## callees

- `0x1800026d0`
- `0x180002aa0`
- `0x180006b28`
- `0x180006d54`
- `0x1800074ac`
- `0x1800081ec`
- `0x180008b08`
- `0x180009364`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008294`

## pseudocode

```c
uus::Session *__fastcall uus::Session::Session(uus::Session *this, const unsigned __int16 *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  char v5; // cl
  unsigned __int64 v6; // rdx
  void *v7; // rcx
  LPVOID pv[4]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v10; // [rsp+40h] [rbp-39h] BYREF
  __int128 v11; // [rsp+50h] [rbp-29h]
  char v12; // [rsp+60h] [rbp-19h]
  _QWORD v13[4]; // [rsp+68h] [rbp-11h] BYREF
  void *v14[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v15; // [rsp+98h] [rbp+1Fh]
  _BYTE v16[32]; // [rsp+A8h] [rbp+2Fh] BYREF

  pv[0] = this;
  v3 = 0;
  *(_QWORD *)this = &uus::Session::`vftable';
  v13[0] = 32;
  v13[1] = 3;
  v13[2] = 0x180000000uLL;
  v13[3] = a2;
  *(_OWORD *)v14 = 0;
  *(_QWORD *)&v15 = 0;
  *((_QWORD *)&v15 + 1) = 7;
  LOWORD(v14[0]) = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(pv);
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)pv[0] + v4) );
  pv[2] = pv[0];
  pv[3] = (LPVOID)v4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v16);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  uus::Utility::FindFileInArchFolder(&v10, v16);
  std::wstring::~wstring(v16);
  v5 = v12;
  if ( v12 )
  {
    if ( *((_QWORD *)&v15 + 1) > 7u )
    {
      v6 = 2LL * *((_QWORD *)&v15 + 1) + 2;
      if ( v6 < 0x1000 )
      {
        v7 = v14[0];
      }
      else
      {
        v7 = (void *)*((_QWORD *)v14[0] - 1);
        if ( (unsigned __int64)((char *)v14[0] - (char *)v7 - 8) > 0x1F )
          __fastfail(5u);
        v6 = 2LL * *((_QWORD *)&v15 + 1) + 41;
      }
      operator delete(v7, v6);
      v5 = v12;
    }
    *(_OWORD *)v14 = v10;
    v15 = v11;
    *(_QWORD *)&v11 = 0;
    *((_QWORD *)&v11 + 1) = 7;
    LOWORD(v10) = 0;
    if ( v5 )
      std::wstring::~wstring(&v10);
    v3 = uus::Utility::GetBrainSession<uus::Brain3>((char *)v14, (__int64)v13);
  }
  std::wstring::~wstring(v14);
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x1800081ec  mov     [rsp-8+arg_10], rbx
0x1800081f1  mov     [rsp-8+arg_18], rdi
0x1800081f6  push    rbp
0x1800081f7  lea     rbp, [rsp-57h]
0x1800081fc  sub     rsp, 0D0h
0x180008203  mov     rax, cs:__security_cookie
0x18000820a  xor     rax, rsp
0x18000820d  mov     [rbp+57h+var_8], rax
0x180008211  mov     rdi, rcx
0x180008214  mov     [rbp+57h+pv], rcx
0x180008218  xor     ebx, ebx
0x18000821a  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x180008221  mov     [rcx], rax
0x180008224  mov     [rbp+57h+var_68], 20h ; ' '
0x18000822c  mov     [rbp+57h+var_60], 3
0x180008234  lea     rax, cs:180000000h
0x18000823b  mov     [rbp+57h+var_58], rax
0x18000823f  mov     [rbp+57h+var_50], rdx
0x180008243  xorps   xmm0, xmm0
0x180008246  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18000824a  mov     qword ptr [rbp+57h+var_38], rbx
0x18000824e  mov     qword ptr [rbp+57h+var_38+8], 7
0x180008256  mov     word ptr [rbp+57h+var_48], bx
0x18000825a  lea     rcx, [rbp+57h+pv]
0x18000825e  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180008263  nop
0x180008264  mov     rcx, [rbp+57h+pv]
0x180008268  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000826c  inc     rax
0x18000826f  cmp     [rcx+rax*2], bx
0x180008273  jnz     short loc_18000826C
0x180008275  mov     [rbp+57h+var_A0], rcx
0x180008279  mov     [rbp+57h+var_98], rax
0x18000827d  lea     rdx, [rbp+57h+var_A0]
0x180008281  lea     rcx, [rbp+57h+var_28]; void *
0x180008285  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18000828a  nop
0x18000828b  mov     rcx, [rbp+57h+pv]; pv
0x18000828f  test    rcx, rcx
0x180008292  jz      short loc_18000829B
0x180008294  call    cs:__imp_CoTaskMemFree
0x18000829a  nop
0x18000829b  lea     rdx, [rbp+57h+var_28]
0x18000829f  lea     rcx, [rbp+57h+var_90]
0x1800082a3  call    ?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)
0x1800082a8  nop
0x1800082a9  lea     rcx, [rbp+57h+var_28]
0x1800082ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800082b2  mov     cl, [rbp+57h+var_70]
0x1800082b5  test    cl, cl
0x1800082b7  jnz     short loc_1800082BE
0x1800082b9  jmp     loc_180008343
0x1800082be  mov     rdx, qword ptr [rbp+57h+var_38+8]
0x1800082c2  cmp     rdx, 7
0x1800082c6  jbe     short loc_180008306
0x1800082c8  mov     rax, [rbp+57h+var_48]
0x1800082cc  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x1800082d4  cmp     rdx, 1000h
0x1800082db  jb      short loc_1800082FB
0x1800082dd  mov     rcx, [rax-8]
0x1800082e1  sub     rax, rcx
0x1800082e4  sub     rax, 8
0x1800082e8  cmp     rax, 1Fh
0x1800082ec  ja      short loc_1800082F4
0x1800082ee  add     rdx, 27h ; '''
0x1800082f2  jmp     short loc_1800082FE
0x1800082f4  mov     ecx, 5
0x1800082f9  int     29h; Win8: RtlFailFast(ecx)
0x1800082fb  mov     rcx, rax; void *
0x1800082fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008303  mov     cl, [rbp+57h+var_70]
0x180008306  movups  xmm0, [rbp+57h+var_90]
0x18000830a  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18000830e  movups  xmm1, [rbp+57h+var_80]
0x180008312  movups  [rbp+57h+var_38], xmm1
0x180008316  mov     qword ptr [rbp+57h+var_80], rbx
0x18000831a  mov     qword ptr [rbp+57h+var_80+8], 7
0x180008322  mov     word ptr [rbp+57h+var_90], bx
0x180008326  test    cl, cl
0x180008328  jz      short loc_180008333
0x18000832a  lea     rcx, [rbp+57h+var_90]
0x18000832e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008333  lea     rdx, [rbp+57h+var_68]
0x180008337  lea     rcx, [rbp+57h+var_48]
0x18000833b  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x180008340  mov     rbx, rax
0x180008343  lea     rcx, [rbp+57h+var_48]
0x180008347  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000834c  mov     [rdi+8], rbx
0x180008350  mov     rax, rdi
0x180008353  mov     rcx, [rbp+57h+var_8]
0x180008357  xor     rcx, rsp; StackCookie
0x18000835a  call    __security_check_cookie
0x18000835f  lea     r11, [rsp+0D0h+var_s0]
0x180008367  mov     rbx, [r11+20h]
0x18000836b  mov     rdi, [r11+28h]
0x18000836f  mov     rsp, r11
0x180008372  pop     rbp
0x180008373  retn
```
