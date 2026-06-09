# uus::Utility::GetFirstBrainSession<uus::Brain3>(ushort const *,uint)

- ea: `0x180063e34`
- end: `0x1800640db`
- name: `??$GetFirstBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@PEBGI@Z`
- size: `679`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180065770`

## callees

- `0x180007660`
- `0x180008560`
- `0x18001ba70`
- `0x18001ee04`
- `0x18002127c`
- `0x18003ceb4`
- `0x180058020`
- `0x180063d20`
- `0x180063e34`
- `0x1800640e4`
- `0x180064d78`
- `0x180065190`
- `0x180065c18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063edf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063f8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063edf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063f8a`

## string_xrefs

- `0x180064072`: `uusbrain.dll`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetFirstBrainSession<uus::Brain3>(__int64 a1, int a2)
{
  __int64 v2; // r8
  __int128 *v4; // rcx
  __int64 v5; // r8
  const unsigned __int16 *v6; // r8
  void **v7; // r11
  unsigned __int64 v8; // rbx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r11
  const unsigned __int16 *v13; // rcx
  unsigned __int64 v14; // rdx
  void **v15; // rcx
  void **v16; // r9
  void **v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rbx
  LPVOID pv[2]; // [rsp+20h] [rbp-79h] BYREF
  __int128 v21; // [rsp+30h] [rbp-69h] BYREF
  __m128i v22; // [rsp+40h] [rbp-59h]
  char v23; // [rsp+50h] [rbp-49h]
  __int64 v24; // [rsp+58h] [rbp-41h] BYREF
  int v25; // [rsp+60h] [rbp-39h]
  int v26; // [rsp+64h] [rbp-35h]
  __int16 *v27; // [rsp+68h] [rbp-31h]
  __int64 v28; // [rsp+70h] [rbp-29h]
  void *Src[2]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v30; // [rsp+88h] [rbp-11h]
  unsigned __int64 v31; // [rsp+90h] [rbp-9h]
  void *v32[2]; // [rsp+98h] [rbp-1h] BYREF
  __m128i si128; // [rsp+A8h] [rbp+Fh]
  __int128 v34; // [rsp+B8h] [rbp+1Fh] BYREF
  __int64 v35; // [rsp+C8h] [rbp+2Fh]
  __int64 v36; // [rsp+D0h] [rbp+37h]

  v24 = 32;
  v25 = 3;
  v26 = a2;
  v27 = &_ImageBase;
  v28 = a1;
  *(_OWORD *)v32 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v32[0]) = 0;
  if ( (a2 & 8) != 0 )
  {
    wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(pv);
    v5 = -1;
    do
      ++v5;
    while ( *((_WORD *)pv[0] + v5) );
    *(_OWORD *)Src = 0;
    v30 = 0;
    v31 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Src, pv[0], v5);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    v7 = Src;
    if ( v31 > 7 )
      v7 = (void **)Src[0];
    v8 = v30;
    for ( i = std::filesystem::_Find_root_name_end((std::filesystem *)v7, (const unsigned __int16 *const)v7 + v30, v6);
          i != v10 && (*i == 92 || *i == 47);
          ++i )
    {
      ;
    }
    if ( i != v10 )
    {
      do
      {
        v13 = v10 - 1;
        if ( *(v10 - 1) == 92 )
          break;
        if ( *v13 == 47 )
          break;
        --v10;
      }
      while ( i != v13 );
    }
    v14 = ((__int64)v10 - v12) >> 1;
    if ( v8 < v14 )
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    v30 = v14;
    v15 = Src;
    if ( v31 > 7 )
      v15 = (void **)Src[0];
    *((_WORD *)v15 + v14) = 0;
    v16 = Src;
    if ( v31 > 7 )
      v16 = (void **)Src[0];
    if ( v30 > si128.m128i_i64[1] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v32,
        v30,
        v11,
        v16);
    }
    else
    {
      v17 = v32;
      if ( si128.m128i_i64[1] > 7uLL )
        v17 = (void **)v32[0];
      si128.m128i_i64[0] = v30;
      v18 = 2 * v30;
      memmove_0(v17, v16, 2 * v30);
      *(_WORD *)((char *)v17 + v18) = 0;
    }
    std::wstring::_Tidy_deallocate(Src);
    v34 = 0;
    v35 = 0;
    v36 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v34, L"uusbrain.dll", 12);
    std::filesystem::path::operator/=(v32, (std::filesystem *)&v34);
    v4 = &v34;
    goto LABEL_36;
  }
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
    pv,
    L"%SystemRoot%\\uus");
  v2 = -1;
  do
    ++v2;
  while ( *((_WORD *)pv[0] + v2) );
  v34 = 0;
  v35 = 0;
  v36 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v34, pv[0], v2);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  uus::Utility::FindFileInArchFolder(&v21, &v34);
  std::wstring::_Tidy_deallocate(&v34);
  if ( !v23 )
  {
    std::wstring::_Tidy_deallocate(v32);
    return 0;
  }
  std::wstring::_Tidy_deallocate(v32);
  *(_OWORD *)v32 = v21;
  si128 = v22;
  v22 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21) = 0;
  if ( v23 )
  {
    v4 = &v21;
LABEL_36:
    std::wstring::_Tidy_deallocate(v4);
  }
  v19 = uus::Utility::GetBrainSession<uus::Brain3>((char *)v32, (__int64)&v24);
  std::wstring::_Tidy_deallocate(v32);
  return v19;
}

```

## disassembly

```asm
0x180063e34  mov     [rsp-8+arg_10], rbx
0x180063e39  push    rbp
0x180063e3a  push    rsi
0x180063e3b  push    rdi
0x180063e3c  lea     rbp, [rsp-47h]
0x180063e41  sub     rsp, 0E0h
0x180063e48  mov     rax, cs:__security_cookie
0x180063e4f  xor     rax, rsp
0x180063e52  mov     [rbp+57h+var_18], rax
0x180063e56  xor     esi, esi
0x180063e58  mov     [rbp+57h+var_98], 20h ; ' '
0x180063e60  mov     [rbp+57h+var_90], 3
0x180063e67  mov     [rbp+57h+var_8C], edx
0x180063e6a  lea     r8, __ImageBase
0x180063e71  mov     [rbp+57h+var_88], r8
0x180063e75  mov     [rbp+57h+var_80], rcx
0x180063e79  and     edx, 8
0x180063e7c  xorps   xmm0, xmm0
0x180063e7f  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180063e83  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180063e8b  movdqu  [rbp+57h+var_48], xmm1
0x180063e90  mov     word ptr [rbp+57h+var_58], si
0x180063e94  lea     rcx, [rbp+57h+pv]
0x180063e98  jnz     loc_180063F50
0x180063e9e  lea     rdx, aSystemrootUus; "%SystemRoot%\\uus"
0x180063ea5  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180063eaa  nop
0x180063eab  mov     rdx, [rbp+57h+pv]
0x180063eaf  or      r8, 0FFFFFFFFFFFFFFFFh
0x180063eb3  inc     r8
0x180063eb6  cmp     [rdx+r8*2], si
0x180063ebb  jnz     short loc_180063EB3
0x180063ebd  xorps   xmm0, xmm0
0x180063ec0  movups  [rbp+57h+var_38], xmm0
0x180063ec4  mov     [rbp+57h+var_28], rsi
0x180063ec8  mov     [rbp+57h+var_20], rsi
0x180063ecc  lea     rcx, [rbp+57h+var_38]
0x180063ed0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180063ed5  nop
0x180063ed6  mov     rcx, [rbp+57h+pv]; pv
0x180063eda  test    rcx, rcx
0x180063edd  jz      short loc_180063EE6
0x180063edf  call    cs:__imp_CoTaskMemFree
0x180063ee5  nop
0x180063ee6  lea     rdx, [rbp+57h+var_38]
0x180063eea  lea     rcx, [rbp+57h+var_C0]
0x180063eee  call    ?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)
0x180063ef3  nop
0x180063ef4  lea     rcx, [rbp+57h+var_38]
0x180063ef8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063efd  cmp     [rbp+57h+var_A0], sil
0x180063f01  jnz     short loc_180063F13
0x180063f03  lea     rcx, [rbp+57h+var_58]
0x180063f07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063f0c  xor     eax, eax
0x180063f0e  jmp     loc_1800640B6
0x180063f13  lea     rcx, [rbp+57h+var_58]
0x180063f17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063f1c  movups  xmm0, [rbp+57h+var_C0]
0x180063f20  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180063f24  movups  xmm1, [rbp+57h+var_B0]
0x180063f28  movups  [rbp+57h+var_48], xmm1
0x180063f2c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180063f34  movdqu  [rbp+57h+var_B0], xmm0
0x180063f39  mov     word ptr [rbp+57h+var_C0], si
0x180063f3d  cmp     [rbp+57h+var_A0], sil
0x180063f41  jz      loc_18006409A
0x180063f47  lea     rcx, [rbp+57h+var_C0]
0x180063f4b  jmp     loc_180064095
0x180063f50  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x180063f55  nop
0x180063f56  mov     rdx, [rbp+57h+pv]
0x180063f5a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180063f5e  inc     r8
0x180063f61  cmp     [rdx+r8*2], si
0x180063f66  jnz     short loc_180063F5E
0x180063f68  xorps   xmm0, xmm0
0x180063f6b  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180063f6f  mov     [rbp+57h+var_68], rsi
0x180063f73  mov     [rbp+57h+var_60], rsi
0x180063f77  lea     rcx, [rbp+57h+Src]
0x180063f7b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180063f80  nop
0x180063f81  mov     rcx, [rbp+57h+pv]; pv
0x180063f85  test    rcx, rcx
0x180063f88  jz      short loc_180063F91
0x180063f8a  call    cs:__imp_CoTaskMemFree
0x180063f90  nop
0x180063f91  lea     r11, [rbp+57h+Src]
0x180063f95  cmp     [rbp+57h+var_60], 7
0x180063f9a  cmova   r11, [rbp+57h+Src]
0x180063f9f  mov     rbx, [rbp+57h+var_68]
0x180063fa3  lea     rdx, [r11+rbx*2]; unsigned __int16 *
0x180063fa7  mov     rcx, r11; this
0x180063faa  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180063faf  jmp     short loc_180063FC1
0x180063fb1  cmp     word ptr [rax], 5Ch ; '\'
0x180063fb5  jz      short loc_180063FBD
0x180063fb7  cmp     word ptr [rax], 2Fh ; '/'
0x180063fbb  jnz     short loc_180063FC6
0x180063fbd  add     rax, 2
0x180063fc1  cmp     rax, rdx
0x180063fc4  jnz     short loc_180063FB1
0x180063fc6  cmp     rax, rdx
0x180063fc9  jz      short loc_180063FE3
0x180063fcb  lea     rcx, [rdx-2]
0x180063fcf  cmp     word ptr [rcx], 5Ch ; '\'
0x180063fd3  jz      short loc_180063FE3
0x180063fd5  cmp     word ptr [rcx], 2Fh ; '/'
0x180063fd9  jz      short loc_180063FE3
0x180063fdb  mov     rdx, rcx
0x180063fde  cmp     rax, rcx
0x180063fe1  jnz     short loc_180063FCB
0x180063fe3  sub     rdx, r11
0x180063fe6  sar     rdx, 1
0x180063fe9  cmp     rbx, rdx
0x180063fec  jb      loc_1800640D5
0x180063ff2  mov     [rbp+57h+var_68], rdx
0x180063ff6  lea     rcx, [rbp+57h+Src]
0x180063ffa  cmp     [rbp+57h+var_60], 7
0x180063fff  cmova   rcx, [rbp+57h+Src]
0x180064004  mov     [rcx+rdx*2], si
0x180064008  mov     rdx, [rbp+57h+var_68]
0x18006400c  lea     r9, [rbp+57h+Src]
0x180064010  cmp     [rbp+57h+var_60], 7
0x180064015  cmova   r9, [rbp+57h+Src]
0x18006401a  cmp     rdx, qword ptr [rbp+57h+var_48+8]
0x18006401e  ja      short loc_18006404A
0x180064020  lea     rdi, [rbp+57h+var_58]
0x180064024  cmp     qword ptr [rbp+57h+var_48+8], 7
0x180064029  cmova   rdi, [rbp+57h+var_58]
0x18006402e  mov     qword ptr [rbp+57h+var_48], rdx
0x180064032  lea     rbx, [rdx+rdx]
0x180064036  mov     r8, rbx; Size
0x180064039  mov     rdx, r9; Src
0x18006403c  mov     rcx, rdi; void *
0x18006403f  call    memmove_0
0x180064044  mov     [rdi+rbx], si
0x180064048  jmp     short loc_180064054
0x18006404a  lea     rcx, [rbp+57h+var_58]
0x18006404e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180064053  nop
0x180064054  lea     rcx, [rbp+57h+Src]
0x180064058  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006405d  xorps   xmm0, xmm0
0x180064060  movups  [rbp+57h+var_38], xmm0
0x180064064  mov     [rbp+57h+var_28], rsi
0x180064068  mov     [rbp+57h+var_20], rsi
0x18006406c  mov     r8d, 0Ch
0x180064072  lea     rdx, aUusbrainDll; "uusbrain.dll"
0x180064079  lea     rcx, [rbp+57h+var_38]
0x18006407d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180064082  nop
0x180064083  lea     rdx, [rbp+57h+var_38]; this
0x180064087  lea     rcx, [rbp+57h+var_58]; Src
0x18006408b  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x180064090  nop
0x180064091  lea     rcx, [rbp+57h+var_38]
0x180064095  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006409a  lea     rdx, [rbp+57h+var_98]
0x18006409e  lea     rcx, [rbp+57h+var_58]
0x1800640a2  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x1800640a7  mov     rbx, rax
0x1800640aa  lea     rcx, [rbp+57h+var_58]
0x1800640ae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800640b3  mov     rax, rbx
0x1800640b6  mov     rcx, [rbp+57h+var_18]
0x1800640ba  xor     rcx, rsp; StackCookie
0x1800640bd  call    __security_check_cookie
0x1800640c2  mov     rbx, [rsp+0F0h+arg_10]
0x1800640ca  add     rsp, 0E0h
0x1800640d1  pop     rdi
0x1800640d2  pop     rsi
0x1800640d3  pop     rbp
0x1800640d4  retn
0x1800640d5  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
