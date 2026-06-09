# GetAppSettingStringSet

- ea: `0x180033d40`
- end: `0x18003415e`
- name: `GetAppSettingStringSet`
- size: `1054`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035800`

## callees

- `0x18001f038`
- `0x18001f3fc`
- `0x1800203ec`
- `0x1800206f4`
- `0x180026f8c`
- `0x1800271a0`
- `0x180031128`
- `0x180031214`
- `0x180032224`
- `0x180032db0`
- `0x180032e80`
- `0x18003301c`
- `0x180033590`
- `0x180033d40`
- `0x180034164`
- `0x180034664`
- `0x1800392b0`
- `0x180039cb0`

## string_xrefs

- `0x180033dae`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180033f65`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
__int64 __fastcall GetAppSettingStringSet(__int64 a1, __int64 a2, __int64 a3, int a4, _QWORD *a5, __int64 a6)
{
  int v6; // r14d
  __int64 v7; // r10
  int v8; // eax
  unsigned int v9; // ebx
  char v10; // r13
  char v11; // r12
  _QWORD *v12; // rbx
  _QWORD *v13; // r15
  char v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rdi
  int v17; // edi
  bool v18; // al
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdi
  _QWORD *v22; // rsi
  int v23; // eax
  __int64 unique_hlocal; // rax
  __int64 v25; // rbx
  int v27; // [rsp+28h] [rbp-E0h]
  int v28; // [rsp+28h] [rbp-E0h]
  __int64 v29; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+68h] [rbp-A0h] BYREF
  char v32[8]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v33[64]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v34[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v35; // [rsp+C8h] [rbp-40h]
  int v36; // [rsp+CCh] [rbp-3Ch]
  _QWORD *v37; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD *v38; // [rsp+D8h] [rbp-30h]
  _BYTE v39[64]; // [rsp+E8h] [rbp-20h] BYREF
  char v40[8]; // [rsp+128h] [rbp+20h] BYREF
  _QWORD *v41; // [rsp+130h] [rbp+28h]
  _BYTE v42[64]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v43[112]; // [rsp+1A8h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]
  int v45; // [rsp+230h] [rbp+128h]
  __int64 v46; // [rsp+238h] [rbp+130h] BYREF
  int v47; // [rsp+240h] [rbp+138h]

  v47 = a4;
  v46 = a3;
  v45 = a2;
  v6 = a3;
  v34[0] = a2;
  v34[1] = a3;
  v35 = a4;
  v36 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v37);
  v8 = SIPolicyForEachPolicy(v7, StringSetPolicyFn, v34);
  if ( v8 >= 0 )
  {
    v10 = 0;
    v11 = 0;
    std::unordered_set<std::wstring>::unordered_set<std::wstring>(v39);
    std::unordered_set<std::wstring>::unordered_set<std::wstring>(v33);
    v12 = v37;
    v13 = v38;
    if ( v37 != v38 )
    {
      do
      {
        v14 = 0;
        std::unordered_set<std::wstring>::unordered_set<std::wstring>(v40);
        v15 = v12[1];
        v16 = *v12;
        if ( *v12 != v15 )
        {
          do
          {
            if ( !(unsigned __int8)SIPolicyIsSystemPolicy(v16) || *(_DWORD *)(v16 + 20) != -1073741275 )
            {
              v14 = 1;
              std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
                v40,
                **(_QWORD **)(v16 + 32),
                *(_QWORD *)(v16 + 32));
            }
            v16 += 88;
          }
          while ( v16 != v15 );
          if ( v14 )
          {
            v17 = v47 & 1;
            v18 = !*(_BYTE *)(*v12 + 16LL) || (v47 & 1) == 0;
            if ( !v10 && v18 )
            {
              v10 = 1;
              std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
                v39,
                *v41,
                v41);
            }
            if ( !v11 )
            {
              v11 = 1;
              std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
                v33,
                *v41,
                v41);
            }
            if ( !*(_BYTE *)(*v12 + 16LL) || !v17 )
            {
              v19 = WldpIntersectSet(v42, v40, v39);
              std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(
                v39,
                v19);
              std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v42);
            }
            v20 = WldpIntersectSet(v43, v40, v33);
            std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(
              v33,
              v20);
            std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v43);
          }
        }
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v40);
        v12 += 3;
      }
      while ( v12 != v13 );
      v6 = v46;
    }
    v31 = 0;
    v21 = a6;
    v28 = a6;
    v22 = a5;
    v23 = FlattenStringIterable_std::unordered_set_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________(
            v39,
            *a5,
            a5,
            &v31);
    v9 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x391,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
        (const char *)(unsigned int)v23,
        v28);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v33);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v39);
      goto LABEL_39;
    }
    if ( !v21 )
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v33);
LABEL_38:
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v39);
      v9 = 0;
      goto LABEL_39;
    }
    if ( (unsigned __int8)std::operator!=<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>,std::allocator<std::wstring>>(
                            v33,
                            v39) )
    {
      v29 = 0;
      v30 = 0;
      v46 = 0;
      if ( (int)FlattenStringIterable_std::unordered_set_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________(
                  v33,
                  0,
                  &v29,
                  &v30) < 0
        || (unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned short [0]>(v32, v29),
            wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
              &v46,
              unique_hlocal),
            wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(v32),
            (v25 = v46) == 0)
        || (int)FlattenStringIterable_std::unordered_set_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________(
                  v33,
                  v29,
                  &v29,
                  &v30) < 0 )
      {
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(&v46);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v33);
        goto LABEL_38;
      }
      LogApplicationSettingQuery(v45, v6, 4, v31, *v22, v21, v30, v29, v25);
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(&v46);
    }
    else
    {
      LogApplicationSettingQuery(v45, v6, 4, v31, *v22, v21, 0, 0, 0);
    }
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v33);
    goto LABEL_38;
  }
  v9 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x349,
         (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
         (const char *)(unsigned int)v8,
         v27);
LABEL_39:
  AppSettingsContext<std::unordered_set<std::wstring>>::~AppSettingsContext<std::unordered_set<std::wstring>>(v34);
  return v9;
}

```

## disassembly

```asm
0x180033d40  mov     rax, rsp
0x180033d43  mov     [rax+8], rbx
0x180033d47  mov     [rax+20h], r9d
0x180033d4b  mov     [rax+18h], r8
0x180033d4f  mov     [rax+10h], rdx
0x180033d53  push    rbp
0x180033d54  push    rsi
0x180033d55  push    rdi
0x180033d56  push    r12
0x180033d58  push    r13
0x180033d5a  push    r14
0x180033d5c  push    r15
0x180033d5e  lea     rbp, [rax-118h]
0x180033d65  sub     rsp, 1E0h
0x180033d6c  mov     r14, r8
0x180033d6f  mov     r10, rcx
0x180033d72  mov     [rbp+110h+var_160], rdx
0x180033d76  mov     [rbp+110h+var_158], r8
0x180033d7a  mov     [rbp+110h+var_150], r9d
0x180033d7e  xor     eax, eax
0x180033d80  mov     [rbp+110h+var_14C], eax
0x180033d83  lea     rcx, [rbp+110h+var_148]
0x180033d87  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x180033d8c  nop
0x180033d8d  lea     r8, [rbp+110h+var_160]
0x180033d91  lea     rdx, StringSetPolicyFn
0x180033d98  mov     rcx, r10
0x180033d9b  call    SIPolicyForEachPolicy
0x180033da0  test    eax, eax
0x180033da2  jns     short loc_180033DC6
0x180033da4  mov     rcx, [rbp+118h]; this
0x180033dab  mov     r9d, eax; char *
0x180033dae  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180033db5  mov     edx, 349h; void *
0x180033dba  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180033dbf  mov     ebx, eax
0x180033dc1  jmp     loc_180034138
0x180033dc6  xor     r13b, r13b
0x180033dc9  xor     r12b, r12b
0x180033dcc  lea     rcx, [rbp+110h+var_130]
0x180033dd0  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180033dd5  nop
0x180033dd6  lea     rcx, [rsp+70h]
0x180033ddb  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180033de0  nop
0x180033de1  mov     rbx, [rbp+110h+var_148]
0x180033de5  mov     r15, [rbp+110h+var_140]
0x180033de9  cmp     rbx, r15
0x180033dec  jz      loc_180033F26
0x180033df2  xor     r14b, r14b
0x180033df5  lea     rcx, [rbp+110h+var_F0]
0x180033df9  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180033dfe  nop
0x180033dff  mov     rsi, [rbx+8]
0x180033e03  mov     rdi, [rbx]
0x180033e06  cmp     rdi, rsi
0x180033e09  jz      loc_180033F09
0x180033e0f  mov     rcx, rdi
0x180033e12  call    SIPolicyIsSystemPolicy
0x180033e17  test    al, al
0x180033e19  jz      short loc_180033E24
0x180033e1b  cmp     dword ptr [rdi+14h], 0C0000225h
0x180033e22  jz      short loc_180033E3A
0x180033e24  mov     r14b, 1
0x180033e27  mov     rdx, [rdi+20h]
0x180033e2b  mov     r8, rdx
0x180033e2e  mov     rdx, [rdx]
0x180033e31  lea     rcx, [rbp+110h+var_F0]
0x180033e35  call    ??$_Insert_range_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180033e3a  add     rdi, 58h ; 'X'
0x180033e3e  cmp     rdi, rsi
0x180033e41  jnz     short loc_180033E0F
0x180033e43  test    r14b, r14b
0x180033e46  jz      loc_180033F09
0x180033e4c  mov     edi, [rbp+110h+arg_18]
0x180033e52  and     edi, 1
0x180033e55  mov     rax, [rbx]
0x180033e58  cmp     byte ptr [rax+10h], 0
0x180033e5c  jz      short loc_180033E66
0x180033e5e  test    edi, edi
0x180033e60  jz      short loc_180033E66
0x180033e62  xor     al, al
0x180033e64  jmp     short loc_180033E68
0x180033e66  mov     al, 1
0x180033e68  test    r13b, r13b
0x180033e6b  jnz     short loc_180033E87
0x180033e6d  test    al, al
0x180033e6f  jz      short loc_180033E87
0x180033e71  mov     r13b, 1
0x180033e74  mov     rdx, [rbp+110h+var_E8]
0x180033e78  mov     r8, rdx
0x180033e7b  mov     rdx, [rdx]
0x180033e7e  lea     rcx, [rbp+110h+var_130]
0x180033e82  call    ??$_Insert_range_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180033e87  test    r12b, r12b
0x180033e8a  jnz     short loc_180033EA3
0x180033e8c  mov     r12b, 1
0x180033e8f  mov     rdx, [rbp+110h+var_E8]
0x180033e93  mov     r8, rdx
0x180033e96  mov     rdx, [rdx]
0x180033e99  lea     rcx, [rsp+70h]
0x180033e9e  call    ??$_Insert_range_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180033ea3  mov     rax, [rbx]
0x180033ea6  cmp     byte ptr [rax+10h], 0
0x180033eaa  jz      short loc_180033EB0
0x180033eac  test    edi, edi
0x180033eae  jnz     short loc_180033ED8
0x180033eb0  lea     r8, [rbp+110h+var_130]
0x180033eb4  lea     rdx, [rbp+110h+var_F0]
0x180033eb8  lea     rcx, [rbp+110h+var_B0]
0x180033ebc  call    WldpIntersectSet
0x180033ec1  nop
0x180033ec2  mov     rdx, rax
0x180033ec5  lea     rcx, [rbp+110h+var_130]
0x180033ec9  call    ??4?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>> &&)
0x180033ece  nop
0x180033ecf  lea     rcx, [rbp+110h+var_B0]
0x180033ed3  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180033ed8  lea     r8, [rsp+70h]
0x180033edd  lea     rdx, [rbp+110h+var_F0]
0x180033ee1  lea     rcx, [rbp+110h+var_70]
0x180033ee8  call    WldpIntersectSet
0x180033eed  nop
0x180033eee  mov     rdx, rax
0x180033ef1  lea     rcx, [rsp+70h]
0x180033ef6  call    ??4?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>> &&)
0x180033efb  nop
0x180033efc  lea     rcx, [rbp+110h+var_70]
0x180033f03  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180033f08  nop
0x180033f09  lea     rcx, [rbp+110h+var_F0]
0x180033f0d  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180033f12  add     rbx, 18h
0x180033f16  cmp     rbx, r15
0x180033f19  jnz     loc_180033DF2
0x180033f1f  mov     r14, [rbp+110h+arg_10]
0x180033f26  xor     r15d, r15d
0x180033f29  mov     [rsp+210h+var_1B0], r15
0x180033f2e  mov     rdi, [rbp+110h+arg_28]
0x180033f35  mov     qword ptr [rsp+210h+var_1F0], rdi; int
0x180033f3a  lea     r9, [rsp+210h+var_1B0]
0x180033f3f  mov     rsi, [rbp+110h+arg_20]
0x180033f46  mov     r8, rsi
0x180033f49  mov     rdx, [rsi]
0x180033f4c  lea     rcx, [rbp+110h+var_130]
0x180033f50  call    FlattenStringIterable_std__unordered_set_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__hash_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__equal_to_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__allocator_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_________
0x180033f55  mov     ebx, eax
0x180033f57  test    eax, eax
0x180033f59  jns     short loc_180033F90
0x180033f5b  mov     rcx, [rbp+118h]; this
0x180033f62  mov     r9d, eax; char *
0x180033f65  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180033f6c  mov     edx, 391h; void *
0x180033f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f76  nop
0x180033f77  lea     rcx, [rsp+70h]
0x180033f7c  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180033f81  nop
0x180033f82  lea     rcx, [rbp+110h+var_130]
0x180033f86  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180033f8b  jmp     loc_180034138
0x180033f90  test    rdi, rdi
0x180033f93  jnz     short loc_180033FA5
0x180033f95  lea     rcx, [rsp+70h]
0x180033f9a  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180033f9f  nop
0x180033fa0  jmp     loc_18003412C
0x180033fa5  lea     rdx, [rbp+110h+var_130]
0x180033fa9  lea     rcx, [rsp+70h]
0x180033fae  call    ??$?9V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@std@@YA_NAEBV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@0@0@Z; std::operator!=<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>,std::allocator<std::wstring>>(std::unordered_set<std::wstring> const &,std::unordered_set<std::wstring> const &)
0x180033fb3  test    al, al
0x180033fb5  jz      loc_1800340EA
0x180033fbb  mov     [rsp+210h+var_1C0], r15
0x180033fc0  mov     [rsp+210h+var_1B8], r15
0x180033fc5  mov     [rbp+110h+arg_10], r15
0x180033fcc  mov     qword ptr [rsp+210h+var_1F0], r15
0x180033fd1  lea     r9, [rsp+210h+var_1B8]
0x180033fd6  lea     r8, [rsp+210h+var_1C0]
0x180033fdb  xor     edx, edx
0x180033fdd  lea     rcx, [rsp+70h]
0x180033fe2  call    FlattenStringIterable_std__unordered_set_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__hash_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__equal_to_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__allocator_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_________
0x180033fe7  test    eax, eax
0x180033fe9  jns     short loc_180034008
0x180033feb  lea     rcx, [rbp+110h+arg_10]
0x180033ff2  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180033ff7  nop
0x180033ff8  lea     rcx, [rsp+70h]
0x180033ffd  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180034002  nop
0x180034003  jmp     loc_18003412C
0x180034008  mov     rdx, [rsp+210h+var_1C0]
0x18003400d  lea     rcx, [rsp+210h+var_1A8]
0x180034012  call    ??$make_unique_hlocal_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<ushort [0]>(unsigned __int64)
0x180034017  nop
0x180034018  mov     rdx, rax
0x18003401b  lea     rcx, [rbp+110h+arg_10]
0x180034022  call    ??4?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x180034027  nop
0x180034028  lea     rcx, [rsp+210h+var_1A8]
0x18003402d  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180034032  mov     rbx, [rbp+110h+arg_10]
0x180034039  test    rbx, rbx
0x18003403c  jz      loc_1800340D0
0x180034042  mov     qword ptr [rsp+210h+var_1F0], rbx
0x180034047  lea     r9, [rsp+210h+var_1B8]
0x18003404c  lea     r8, [rsp+210h+var_1C0]
0x180034051  mov     rdx, [rsp+210h+var_1C0]
0x180034056  lea     rcx, [rsp+70h]
0x18003405b  call    FlattenStringIterable_std__unordered_set_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__hash_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__equal_to_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__allocator_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_________
0x180034060  test    eax, eax
0x180034062  jns     short loc_180034081
0x180034064  lea     rcx, [rbp+110h+arg_10]
0x18003406b  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180034070  nop
0x180034071  lea     rcx, [rsp+70h]
0x180034076  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18003407b  nop
0x18003407c  jmp     loc_18003412C
0x180034081  mov     [rsp+40h], rbx
0x180034086  mov     rax, [rsp+210h+var_1C0]
0x18003408b  mov     [rsp+210h+var_1D8], rax
0x180034090  mov     rax, [rsp+210h+var_1B8]
0x180034095  mov     [rsp+210h+var_1E0], rax
0x18003409a  mov     [rsp+210h+var_1E8], rdi
0x18003409f  mov     rax, [rsi]
0x1800340a2  mov     qword ptr [rsp+210h+var_1F0], rax
0x1800340a7  mov     r9, [rsp+210h+var_1B0]
0x1800340ac  mov     r8d, 4
0x1800340b2  mov     rdx, r14
0x1800340b5  mov     rcx, [rbp+110h+arg_8]
0x1800340bc  call    LogApplicationSettingQuery
0x1800340c1  nop
0x1800340c2  lea     rcx, [rbp+110h+arg_10]
0x1800340c9  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x1800340ce  jmp     short loc_180034121
0x1800340d0  lea     rcx, [rbp+110h+arg_10]
0x1800340d7  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x1800340dc  nop
0x1800340dd  lea     rcx, [rsp+70h]
0x1800340e2  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x1800340e7  nop
0x1800340e8  jmp     short loc_18003412C
0x1800340ea  mov     [rsp+40h], r15
0x1800340ef  mov     [rsp+210h+var_1D8], r15
0x1800340f4  mov     [rsp+210h+var_1E0], r15
0x1800340f9  mov     [rsp+210h+var_1E8], rdi
0x1800340fe  mov     rax, [rsi]
0x180034101  mov     qword ptr [rsp+210h+var_1F0], rax
0x180034106  mov     r9, [rsp+210h+var_1B0]
0x18003410b  mov     r8d, 4
0x180034111  mov     rdx, r14
0x180034114  mov     rcx, [rbp+110h+arg_8]
0x18003411b  call    LogApplicationSettingQuery
0x180034120  nop
0x180034121  lea     rcx, [rsp+70h]
0x180034126  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18003412b  nop
0x18003412c  lea     rcx, [rbp+110h+var_130]
0x180034130  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180034135  mov     ebx, r15d
0x180034138  lea     rcx, [rbp+110h+var_160]
0x18003413c  call    ??1?$AppSettingsContext@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@QEAA@XZ; AppSettingsContext<std::unordered_set<std::wstring>>::~AppSettingsContext<std::unordered_set<std::wstring>>(void)
0x180034141  mov     eax, ebx
0x180034143  mov     rbx, [rsp+210h+arg_0]
0x18003414b  add     rsp, 1E0h
0x180034152  pop     r15
0x180034154  pop     r14
0x180034156  pop     r13
0x180034158  pop     r12
0x18003415a  pop     rdi
0x18003415b  pop     rsi
0x18003415c  pop     rbp
0x18003415d  retn
```
