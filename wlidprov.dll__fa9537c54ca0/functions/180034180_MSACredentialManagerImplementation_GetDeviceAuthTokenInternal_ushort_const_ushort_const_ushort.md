# MSACredentialManagerImplementation::GetDeviceAuthTokenInternal(ushort const *,ushort const *,ushort * *)

- ea: `0x180034180`
- end: `0x180034309`
- name: `?GetDeviceAuthTokenInternal@MSACredentialManagerImplementation@@EEAAJPEBG0PEAPEAG@Z`
- size: `393`
- prototype: `__int64 __fastcall(MSACredentialManagerImplementation *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180016758`
- `0x18001a0d0`
- `0x180028650`
- `0x18003091c`
- `0x1800309c8`
- `0x1800309fc`
- `0x180034180`
- `0x1800350d0`
- `0x1800350e0`
- `0x1800351ac`

## import_xrefs

- `dsreg!DsrGetJoinInfo` at `0x1800341e6`
- `dsreg!DsrGetJoinInfo` at `0x1800341e6`
- `AADTB!AADTBAcquireToken` at `0x18003424b`
- `AADTB!AADTBAcquireToken` at `0x18003424b`

## string_xrefs

- `0x18003421a`: `https://login.microsoftonline.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MSACredentialManagerImplementation::GetDeviceAuthTokenInternal(
        MSACredentialManagerImplementation *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int JoinInfo; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  char v12; // al
  __int128 *v13; // rdx
  unsigned __int16 *v14; // rsi
  void *v15; // rdx
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  _BYTE *v21; // rax
  unsigned __int16 *v23; // [rsp+20h] [rbp-49h] BYREF
  __int64 v24; // [rsp+28h] [rbp-41h] BYREF
  __int64 v25; // [rsp+30h] [rbp-39h] BYREF
  __int128 v26; // [rsp+38h] [rbp-31h]
  __int64 v27; // [rsp+48h] [rbp-21h]
  const wchar_t *v28; // [rsp+50h] [rbp-19h]
  const wchar_t *v29; // [rsp+58h] [rbp-11h]
  const unsigned __int16 *v30; // [rsp+60h] [rbp-9h]
  __int64 v31; // [rsp+68h] [rbp-1h]
  __int128 v32; // [rsp+70h] [rbp+7h] BYREF
  __int128 v33; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( !a4 )
  {
    JoinInfo = -2147467261;
    v8 = 1172;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      (const char *)JoinInfo,
      (int)v23);
    return JoinInfo;
  }
  *a4 = 0;
  v24 = 0;
  JoinInfo = DsrGetJoinInfo(0, &v24);
  if ( (JoinInfo & 0x80000000) != 0 )
  {
    v8 = 1175;
    goto LABEL_3;
  }
  v25 = 64;
  v27 = 0;
  v31 = 0;
  v26 = (unsigned __int64)a2;
  v29 = L"https://login.microsoftonline.com";
  v28 = L"01cb2876-7ebd-4aa4-9cc9-d28bd4d359a9";
  v30 = a3;
  v27 = *(_QWORD *)(v24 + 32);
  v9 = AADTBAcquireToken(&v25);
  v32 = 0;
  v33 = 0;
  v10 = std::_WChar_traits<unsigned short>::length(v9);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::_Construct<1,unsigned short const *>(
    &v32,
    v11,
    v10);
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(&v32);
  v13 = &v32;
  if ( v12 )
    v13 = (__int128 *)v32;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v23,
    v13);
  v14 = v23;
  v23 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
  if ( !v14 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v15, v16, v17);
  *a4 = v14;
  if ( *((_QWORD *)&v33 + 1) > 7u )
  {
    v18 = v32;
    v19 = 2LL * *((_QWORD *)&v33 + 1) + 2;
    v20 = v19;
    v21 = (_BYTE *)v32;
    if ( 2LL * *((_QWORD *)&v33 + 1) != -2 )
    {
      do
      {
        *v21++ = 0;
        --v20;
      }
      while ( v20 );
    }
    std::_Deallocate<16>(v18, v19, v20);
  }
  return JoinInfo;
}

```

## disassembly

```asm
0x180034180  push    rbp
0x180034182  push    rbx
0x180034183  push    rsi
0x180034184  push    rdi
0x180034185  push    r14
0x180034187  lea     rbp, [rsp-37h]
0x18003418c  sub     rsp, 0A0h
0x180034193  mov     rax, cs:__security_cookie
0x18003419a  xor     rax, rsp
0x18003419d  mov     [rbp+57h+var_30], rax
0x1800341a1  mov     rdi, r9
0x1800341a4  mov     r14, r8
0x1800341a7  mov     rsi, rdx
0x1800341aa  test    r9, r9
0x1800341ad  jnz     short loc_1800341D1
0x1800341af  mov     ebx, 80004003h
0x1800341b4  mov     edx, 494h; void *
0x1800341b9  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800341c0  mov     r9d, ebx; char *
0x1800341c3  mov     rcx, [rbp+5Fh]; this
0x1800341c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800341cc  jmp     loc_1800342E7
0x1800341d1  mov     qword ptr [r9], 0
0x1800341d8  mov     [rbp+57h+var_98], 0
0x1800341e0  lea     rdx, [rbp+57h+var_98]
0x1800341e4  xor     ecx, ecx
0x1800341e6  call    cs:__imp_DsrGetJoinInfo
0x1800341ec  mov     ebx, eax
0x1800341ee  test    eax, eax
0x1800341f0  jns     short loc_1800341F9
0x1800341f2  mov     edx, 497h
0x1800341f7  jmp     short loc_1800341B9
0x1800341f9  mov     [rbp+57h+var_90], 40h ; '@'
0x180034201  xorps   xmm0, xmm0
0x180034204  xor     eax, eax
0x180034206  movups  [rbp+57h+var_88], xmm0
0x18003420a  movups  [rbp+57h+var_78], xmm0
0x18003420e  movups  [rbp+57h+var_68], xmm0
0x180034212  mov     [rbp+57h+var_58], rax
0x180034216  mov     qword ptr [rbp+57h+var_88], rsi
0x18003421a  lea     rax, aHttpsLoginMicr_0; "https://login.microsoftonline.com"
0x180034221  mov     qword ptr [rbp+57h+var_68], rax
0x180034225  lea     rax, a01cb28767ebd4a; "01cb2876-7ebd-4aa4-9cc9-d28bd4d359a9"
0x18003422c  mov     qword ptr [rbp+57h+var_78+8], rax
0x180034230  mov     qword ptr [rbp+57h+var_68+8], r14
0x180034234  mov     rax, [rbp+57h+var_98]
0x180034238  mov     rcx, [rax+20h]
0x18003423c  mov     qword ptr [rbp+57h+var_78], rcx
0x180034240  mov     dword ptr [rbp+57h+var_58], 0
0x180034247  lea     rcx, [rbp+57h+var_90]
0x18003424b  call    cs:__imp_AADTBAcquireToken
0x180034251  mov     rcx, rax
0x180034254  xorps   xmm0, xmm0
0x180034257  movups  [rbp+57h+var_50], xmm0
0x18003425b  xorps   xmm1, xmm1
0x18003425e  movdqu  [rbp+57h+var_40], xmm1
0x180034263  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180034268  mov     r8, rax
0x18003426b  mov     rdx, rcx
0x18003426e  lea     rcx, [rbp+57h+var_50]
0x180034272  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@AEAAXQEBG_K@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180034277  lea     rcx, [rbp+57h+var_50]
0x18003427b  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x180034280  lea     rdx, [rbp+57h+var_50]
0x180034284  test    al, al
0x180034286  cmovnz  rdx, qword ptr [rbp+57h+var_50]
0x18003428b  lea     rcx, [rbp+57h+var_A0]
0x18003428f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180034294  mov     rsi, [rbp+57h+var_A0]
0x180034298  mov     [rbp+57h+var_A0], 0
0x1800342a0  lea     rcx, [rbp+57h+var_A0]
0x1800342a4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800342a9  mov     rcx, [rbp+5Fh]; this
0x1800342ad  test    rsi, rsi
0x1800342b0  jz      short loc_180034303
0x1800342b2  mov     [rdi], rsi
0x1800342b5  mov     rax, qword ptr [rbp+57h+var_40+8]
0x1800342b9  cmp     rax, 7
0x1800342bd  jbe     short loc_1800342E7
0x1800342bf  mov     rcx, qword ptr [rbp+57h+var_50]
0x1800342c3  lea     rdx, ds:2[rax*2]
0x1800342cb  mov     r8, rdx
0x1800342ce  mov     rax, rcx
0x1800342d1  test    rdx, rdx
0x1800342d4  jz      short loc_1800342E2
0x1800342d6  mov     byte ptr [rax], 0
0x1800342d9  inc     rax
0x1800342dc  sub     r8, 1
0x1800342e0  jnz     short loc_1800342D6
0x1800342e2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800342e7  mov     eax, ebx
0x1800342e9  mov     rcx, [rbp+57h+var_30]
0x1800342ed  xor     rcx, rsp; StackCookie
0x1800342f0  call    __security_check_cookie
0x1800342f5  add     rsp, 0A0h
0x1800342fc  pop     r14
0x1800342fe  pop     rdi
0x1800342ff  pop     rsi
0x180034300  pop     rbx
0x180034301  pop     rbp
0x180034302  retn
0x180034303  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
