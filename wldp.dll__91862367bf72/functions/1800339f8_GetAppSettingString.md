# GetAppSettingString

- ea: `0x1800339f8`
- end: `0x180033d38`
- name: `GetAppSettingString`
- size: `832`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x180035500`

## callees

- `0x18001f038`
- `0x18001f3fc`
- `0x18001f8c4`
- `0x1800203ec`
- `0x1800206f4`
- `0x180026f8c`
- `0x1800271a0`
- `0x1800312e0`
- `0x180031534`
- `0x180032940`
- `0x180032e10`
- `0x1800339f8`
- `0x180034164`
- `0x1800392b0`

## string_xrefs

- `0x180033a5e`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180033b1c`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
__int64 __fastcall GetAppSettingString(__int64 a1, __int64 a2, __int64 a3, int a4, _QWORD *a5, __int64 a6)
{
  char v6; // r12
  int v7; // r13d
  int v8; // r15d
  __int64 v9; // r10
  int v10; // eax
  unsigned int v11; // ebx
  __int64 *v12; // rbx
  __int64 *v13; // r14
  __int64 v14; // r15
  __int64 i; // rdi
  __int64 v16; // rsi
  __int64 v17; // rdi
  _QWORD *v18; // rsi
  int v19; // eax
  __int64 unique_hlocal; // rax
  __int64 v21; // rbx
  int v23; // [rsp+20h] [rbp-99h]
  int v24; // [rsp+20h] [rbp-99h]
  __int64 v25; // [rsp+50h] [rbp-69h] BYREF
  __int128 v26; // [rsp+58h] [rbp-61h]
  __int64 v27; // [rsp+68h] [rbp-51h] BYREF
  __int128 v28; // [rsp+70h] [rbp-49h]
  __int64 v29; // [rsp+80h] [rbp-39h] BYREF
  __int64 v30; // [rsp+88h] [rbp-31h] BYREF
  char v31[8]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD v32[2]; // [rsp+98h] [rbp-21h] BYREF
  int v33; // [rsp+A8h] [rbp-11h]
  int v34; // [rsp+ACh] [rbp-Dh]
  __int64 *v35; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v36; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]
  __int64 v38; // [rsp+118h] [rbp+5Fh] BYREF
  __int64 v39; // [rsp+120h] [rbp+67h] BYREF

  v38 = a2;
  v6 = a4;
  v7 = a3;
  v8 = a2;
  v32[0] = a2;
  v32[1] = a3;
  v33 = a4;
  v34 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v35);
  v10 = SIPolicyForEachPolicy(v9, StringPolicyFn, v32);
  if ( v10 >= 0 )
  {
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v27);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v25);
    v12 = v35;
    v13 = v36;
    if ( v35 != v36 )
    {
      do
      {
        v14 = v12[1];
        for ( i = *v12; i != v14; i += 56 )
        {
          if ( *(_BYTE *)(i + 16) && (v6 & 1) != 0 )
          {
            v16 = i + 24;
          }
          else
          {
            v16 = i + 24;
            std::vector<std::wstring>::emplace_back<std::wstring const &>(&v27, i + 24);
          }
          std::vector<std::wstring>::emplace_back<std::wstring const &>(&v25, v16);
        }
        v12 += 3;
      }
      while ( v12 != v13 );
      v8 = v38;
    }
    v30 = 0;
    v17 = a6;
    v24 = a6;
    v18 = a5;
    v19 = FlattenStringIterable_std::vector_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________(
            &v27,
            *a5,
            a5,
            &v30);
    v11 = v19;
    if ( v19 >= 0 )
    {
      if ( v17 )
      {
        if ( (_QWORD)v26 - v25 == (_QWORD)v28 - v27 )
        {
          LogApplicationSettingQuery(v8, v7, 3, v30, *v18, v17, 0, 0, 0);
        }
        else
        {
          v39 = 0;
          v29 = 0;
          v38 = 0;
          if ( (int)FlattenStringIterable_std::vector_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________(
                      &v25,
                      0,
                      &v39,
                      &v29) >= 0 )
          {
            unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned short [0]>(v31, v39);
            wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
              &v38,
              unique_hlocal);
            wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(v31);
            v21 = v38;
            if ( v38 )
            {
              if ( (int)FlattenStringIterable_std::vector_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________(
                          &v25,
                          v39,
                          &v39,
                          &v29) >= 0 )
                LogApplicationSettingQuery(v8, v7, 3, v30, *v18, v17, v29, v39, v21);
            }
          }
          wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(&v38);
        }
      }
      if ( v25 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v25, v26);
        std::_Deallocate<16>(v25, (*((_QWORD *)&v26 + 1) - v25) & 0xFFFFFFFFFFFFFFE0uLL);
        v25 = 0;
        v26 = 0;
      }
      if ( v27 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v27, v28);
        std::_Deallocate<16>(v27, (*((_QWORD *)&v28 + 1) - v27) & 0xFFFFFFFFFFFFFFE0uLL);
        v27 = 0;
        v28 = 0;
      }
      v11 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x266,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
        (const char *)(unsigned int)v19,
        v24);
      if ( v25 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v25, v26);
        std::_Deallocate<16>(v25, (*((_QWORD *)&v26 + 1) - v25) & 0xFFFFFFFFFFFFFFE0uLL);
        v25 = 0;
        v26 = 0;
      }
      if ( v27 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v27, v28);
        std::_Deallocate<16>(v27, (*((_QWORD *)&v28 + 1) - v27) & 0xFFFFFFFFFFFFFFE0uLL);
        v27 = 0;
        v28 = 0;
      }
    }
  }
  else
  {
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x24B,
            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
            (const char *)(unsigned int)v10,
            v23);
  }
  AppSettingsContext<std::wstring>::~AppSettingsContext<std::wstring>(v32);
  return v11;
}

```

## disassembly

```asm
0x1800339f8  mov     [rsp-8+arg_0], rbx
0x1800339fd  mov     [rsp-8+arg_8], rdx
0x180033a02  push    rbp
0x180033a03  push    rsi
0x180033a04  push    rdi
0x180033a05  push    r12
0x180033a07  push    r13
0x180033a09  push    r14
0x180033a0b  push    r15
0x180033a0d  lea     rbp, [rsp-17h]
0x180033a12  sub     rsp, 0D0h
0x180033a19  mov     r12d, r9d
0x180033a1c  mov     r13, r8
0x180033a1f  mov     r15, rdx
0x180033a22  mov     r10, rcx
0x180033a25  mov     [rbp+47h+var_68], rdx
0x180033a29  mov     [rbp+47h+var_60], r8
0x180033a2d  mov     [rbp+47h+var_58], r9d
0x180033a31  xor     eax, eax
0x180033a33  mov     [rbp+47h+var_54], eax
0x180033a36  lea     rcx, [rbp+47h+var_50]
0x180033a3a  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x180033a3f  nop
0x180033a40  lea     r8, [rbp+47h+var_68]
0x180033a44  lea     rdx, StringPolicyFn
0x180033a4b  mov     rcx, r10
0x180033a4e  call    SIPolicyForEachPolicy
0x180033a53  test    eax, eax
0x180033a55  jns     short loc_180033A76
0x180033a57  mov     rcx, [rbp+4Fh]; this
0x180033a5b  mov     r9d, eax; char *
0x180033a5e  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180033a65  mov     edx, 24Bh; void *
0x180033a6a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180033a6f  mov     ebx, eax
0x180033a71  jmp     loc_180033D12
0x180033a76  lea     rcx, [rbp+47h+var_98]
0x180033a7a  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x180033a7f  nop
0x180033a80  lea     rcx, [rbp+47h+var_B0]
0x180033a84  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x180033a89  nop
0x180033a8a  mov     rbx, [rbp+47h+var_50]
0x180033a8e  mov     r14, [rbp+47h+var_48]
0x180033a92  cmp     rbx, r14
0x180033a95  jz      short loc_180033AE4
0x180033a97  mov     r15, [rbx+8]
0x180033a9b  mov     rdi, [rbx]
0x180033a9e  jmp     short loc_180033AD2
0x180033aa0  cmp     byte ptr [rdi+10h], 0
0x180033aa4  jz      short loc_180033AB2
0x180033aa6  test    r12b, 1
0x180033aaa  jz      short loc_180033AB2
0x180033aac  lea     rsi, [rdi+18h]
0x180033ab0  jmp     short loc_180033AC2
0x180033ab2  lea     rsi, [rdi+18h]
0x180033ab6  mov     rdx, rsi
0x180033ab9  lea     rcx, [rbp+47h+var_98]
0x180033abd  call    ??$emplace_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring const &>(std::wstring const &)
0x180033ac2  mov     rdx, rsi
0x180033ac5  lea     rcx, [rbp+47h+var_B0]
0x180033ac9  call    ??$emplace_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring const &>(std::wstring const &)
0x180033ace  add     rdi, 38h ; '8'
0x180033ad2  cmp     rdi, r15
0x180033ad5  jnz     short loc_180033AA0
0x180033ad7  add     rbx, 18h
0x180033adb  cmp     rbx, r14
0x180033ade  jnz     short loc_180033A97
0x180033ae0  mov     r15, [rbp+47h+arg_8]
0x180033ae4  xor     r14d, r14d
0x180033ae7  mov     [rbp+47h+var_78], r14
0x180033aeb  mov     rdi, [rbp+47h+arg_28]
0x180033aef  mov     qword ptr [rsp+100h+var_E0], rdi; int
0x180033af4  lea     r9, [rbp+47h+var_78]
0x180033af8  mov     rsi, [rbp+47h+arg_20]
0x180033afc  mov     r8, rsi
0x180033aff  mov     rdx, [rsi]
0x180033b02  lea     rcx, [rbp+47h+var_98]
0x180033b06  call    FlattenStringIterable_std__vector_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__allocator_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_________
0x180033b0b  mov     ebx, eax
0x180033b0d  test    eax, eax
0x180033b0f  jns     loc_180033B9B
0x180033b15  mov     rcx, [rbp+4Fh]; this
0x180033b19  mov     r9d, eax; char *
0x180033b1c  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180033b23  mov     edx, 266h; void *
0x180033b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033b2d  nop
0x180033b2e  mov     rcx, [rbp+47h+var_B0]
0x180033b32  test    rcx, rcx
0x180033b35  jz      short loc_180033B60
0x180033b37  mov     rdx, qword ptr [rbp+47h+var_A8]
0x180033b3b  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180033b40  mov     rcx, [rbp+47h+var_B0]
0x180033b44  mov     rdx, qword ptr [rbp+47h+var_A8+8]
0x180033b48  sub     rdx, rcx
0x180033b4b  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180033b4f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180033b54  mov     [rbp+47h+var_B0], r14
0x180033b58  xorps   xmm0, xmm0
0x180033b5b  movdqu  [rbp+47h+var_A8], xmm0
0x180033b60  mov     rcx, [rbp+47h+var_98]
0x180033b64  test    rcx, rcx
0x180033b67  jz      loc_180033D12
0x180033b6d  mov     rdx, qword ptr [rbp+47h+var_90]
0x180033b71  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180033b76  mov     rcx, [rbp+47h+var_98]
0x180033b7a  mov     rdx, qword ptr [rbp+47h+var_90+8]
0x180033b7e  sub     rdx, rcx
0x180033b81  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180033b85  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180033b8a  mov     [rbp+47h+var_98], r14
0x180033b8e  xorps   xmm0, xmm0
0x180033b91  movdqu  [rbp+47h+var_90], xmm0
0x180033b96  jmp     loc_180033D12
0x180033b9b  test    rdi, rdi
0x180033b9e  jz      loc_180033CAB
0x180033ba4  mov     rcx, qword ptr [rbp+47h+var_90]
0x180033ba8  sub     rcx, [rbp+47h+var_98]
0x180033bac  mov     rax, qword ptr [rbp+47h+var_A8]
0x180033bb0  sub     rax, [rbp+47h+var_B0]
0x180033bb4  cmp     rax, rcx
0x180033bb7  jz      loc_180033C79
0x180033bbd  mov     [rbp+47h+arg_10], r14
0x180033bc1  mov     [rbp+47h+var_80], r14
0x180033bc5  mov     [rbp+47h+arg_8], r14
0x180033bc9  mov     qword ptr [rsp+100h+var_E0], r14
0x180033bce  lea     r9, [rbp+47h+var_80]
0x180033bd2  lea     r8, [rbp+47h+arg_10]
0x180033bd6  xor     edx, edx
0x180033bd8  lea     rcx, [rbp+47h+var_B0]
0x180033bdc  call    FlattenStringIterable_std__vector_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__allocator_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_________
0x180033be1  test    eax, eax
0x180033be3  js      loc_180033C6E
0x180033be9  mov     rdx, [rbp+47h+arg_10]
0x180033bed  lea     rcx, [rbp+47h+var_70]
0x180033bf1  call    ??$make_unique_hlocal_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<ushort [0]>(unsigned __int64)
0x180033bf6  nop
0x180033bf7  mov     rdx, rax
0x180033bfa  lea     rcx, [rbp+47h+arg_8]
0x180033bfe  call    ??4?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x180033c03  nop
0x180033c04  lea     rcx, [rbp+47h+var_70]
0x180033c08  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180033c0d  mov     rbx, [rbp+47h+arg_8]
0x180033c11  test    rbx, rbx
0x180033c14  jz      short loc_180033C6E
0x180033c16  mov     qword ptr [rsp+100h+var_E0], rbx
0x180033c1b  lea     r9, [rbp+47h+var_80]
0x180033c1f  lea     r8, [rbp+47h+arg_10]
0x180033c23  mov     rdx, [rbp+47h+arg_10]
0x180033c27  lea     rcx, [rbp+47h+var_B0]
0x180033c2b  call    FlattenStringIterable_std__vector_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__allocator_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_________
0x180033c30  test    eax, eax
0x180033c32  js      short loc_180033C6E
0x180033c34  mov     [rsp+100h+var_C0], rbx
0x180033c39  mov     rax, [rbp+47h+arg_10]
0x180033c3d  mov     [rsp+100h+var_C8], rax
0x180033c42  mov     rax, [rbp+47h+var_80]
0x180033c46  mov     [rsp+100h+var_D0], rax
0x180033c4b  mov     [rsp+100h+var_D8], rdi
0x180033c50  mov     rax, [rsi]
0x180033c53  mov     qword ptr [rsp+100h+var_E0], rax
0x180033c58  mov     r9, [rbp+47h+var_78]
0x180033c5c  mov     r8d, 3
0x180033c62  mov     rdx, r13
0x180033c65  mov     rcx, r15
0x180033c68  call    LogApplicationSettingQuery
0x180033c6d  nop
0x180033c6e  lea     rcx, [rbp+47h+arg_8]
0x180033c72  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180033c77  jmp     short loc_180033CAB
0x180033c79  mov     [rsp+100h+var_C0], r14
0x180033c7e  mov     [rsp+100h+var_C8], r14
0x180033c83  mov     [rsp+100h+var_D0], r14
0x180033c88  mov     [rsp+100h+var_D8], rdi
0x180033c8d  mov     rax, [rsi]
0x180033c90  mov     qword ptr [rsp+100h+var_E0], rax
0x180033c95  mov     r9, [rbp+47h+var_78]
0x180033c99  mov     r8d, 3
0x180033c9f  mov     rdx, r13
0x180033ca2  mov     rcx, r15
0x180033ca5  call    LogApplicationSettingQuery
0x180033caa  nop
0x180033cab  mov     rcx, [rbp+47h+var_B0]
0x180033caf  test    rcx, rcx
0x180033cb2  jz      short loc_180033CDD
0x180033cb4  mov     rdx, qword ptr [rbp+47h+var_A8]
0x180033cb8  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180033cbd  mov     rcx, [rbp+47h+var_B0]
0x180033cc1  mov     rdx, qword ptr [rbp+47h+var_A8+8]
0x180033cc5  sub     rdx, rcx
0x180033cc8  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180033ccc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180033cd1  xorps   xmm0, xmm0
0x180033cd4  mov     [rbp+47h+var_B0], r14
0x180033cd8  movdqu  [rbp+47h+var_A8], xmm0
0x180033cdd  mov     rcx, [rbp+47h+var_98]
0x180033ce1  test    rcx, rcx
0x180033ce4  jz      short loc_180033D0F
0x180033ce6  mov     rdx, qword ptr [rbp+47h+var_90]
0x180033cea  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180033cef  mov     rcx, [rbp+47h+var_98]
0x180033cf3  mov     rdx, qword ptr [rbp+47h+var_90+8]
0x180033cf7  sub     rdx, rcx
0x180033cfa  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180033cfe  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180033d03  xorps   xmm0, xmm0
0x180033d06  mov     [rbp+47h+var_98], r14
0x180033d0a  movdqu  [rbp+47h+var_90], xmm0
0x180033d0f  mov     ebx, r14d
0x180033d12  lea     rcx, [rbp+47h+var_68]
0x180033d16  call    ??1?$AppSettingsContext@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@QEAA@XZ; AppSettingsContext<std::wstring>::~AppSettingsContext<std::wstring>(void)
0x180033d1b  mov     eax, ebx
0x180033d1d  mov     rbx, [rsp+100h+arg_0]
0x180033d25  add     rsp, 0D0h
0x180033d2c  pop     r15
0x180033d2e  pop     r14
0x180033d30  pop     r13
0x180033d32  pop     r12
0x180033d34  pop     rdi
0x180033d35  pop     rsi
0x180033d36  pop     rbp
0x180033d37  retn
```
