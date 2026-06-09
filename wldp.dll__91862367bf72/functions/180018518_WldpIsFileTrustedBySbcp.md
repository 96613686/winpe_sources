# WldpIsFileTrustedBySbcp

- ea: `0x180018518`
- end: `0x1800188bf`
- name: `WldpIsFileTrustedBySbcp`
- size: `935`
- prototype: `__int64 __fastcall(int, int, char, _DWORD *, _OWORD *, _BYTE *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180015118`
- `0x18001e1d4`

## callees

- `0x180018518`
- `0x180018918`
- `0x180018950`
- `0x18001898c`
- `0x18001f038`
- `0x18001f0b4`
- `0x18001f3fc`
- `0x18001f414`
- `0x18001f8c4`
- `0x18002c9d4`
- `0x18002d728`

## string_xrefs

- `0x1800185f7`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`
- `0x180018735`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
__int64 __fastcall WldpIsFileTrustedBySbcp(int a1, int a2, char a3, _DWORD *a4, _OWORD *a5, _BYTE *a6)
{
  int v10; // edx
  int IsEmbedSignatureTrusted; // ebx
  __int64 v12; // rdx
  const char *v13; // r9
  __int64 result; // rax
  int IsCatalogSignatureTrusted; // eax
  __int64 v16; // rdx
  unsigned int v17; // ebx
  _QWORD *v18; // rbx
  _QWORD *v19; // rsi
  int v20; // [rsp+20h] [rbp-D8h]
  int v21; // [rsp+20h] [rbp-D8h]
  int v22; // [rsp+50h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-90h]
  unsigned int v25; // [rsp+70h] [rbp-88h] BYREF
  __int64 v26; // [rsp+78h] [rbp-80h] BYREF
  int v27; // [rsp+80h] [rbp-78h]
  unsigned int v28; // [rsp+84h] [rbp-74h] BYREF
  __int128 v29; // [rsp+88h] [rbp-70h] BYREF
  __int64 v30; // [rsp+98h] [rbp-60h] BYREF
  _QWORD *v31; // [rsp+A0h] [rbp-58h]
  __int64 *v32; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-48h] BYREF
  char v34; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v27 = 0;
  try
  {
    v29 = 0;
    v30 = 0;
    v28 = 0;
    v25 = 0;
    LOBYTE(v22) = 0;
    v26 = 0;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v23);
    v32 = &v26;
    v33 = 0;
    v34 = 1;
    v27 = 1;
    IsEmbedSignatureTrusted = WldpIsEmbedSignatureTrusted(
                                a1,
                                v10,
                                0,
                                (unsigned int)&v28,
                                (__int64)&v22,
                                (__int64)&v29,
                                (__int64)&v33,
                                0);
    v27 = 0;
    wil::details::out_param_t_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_______::_out_param_t_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_______(&v32);
    if ( IsEmbedSignatureTrusted < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43F,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
        (const char *)(unsigned int)IsEmbedSignatureTrusted,
        v20);
      if ( (_QWORD)v23 )
      {
        std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
          v23,
          *((_QWORD *)&v23 + 1));
        std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
        v23 = 0;
        v24 = 0;
      }
      if ( v26 )
        WldpFreeStateData();
      return (unsigned int)IsEmbedSignatureTrusted;
    }
    LOBYTE(v12) = a3;
    if ( (unsigned __int8)WldpValidateAgainstPolicy(v26, v12, v28) )
    {
      *a5 = v29;
      *a4 = 1;
      *a6 = 1;
      if ( (_QWORD)v23 )
      {
        std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
          v23,
          *((_QWORD *)&v23 + 1));
        std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
        v23 = 0;
        v24 = 0;
      }
LABEL_25:
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____(&v26);
      return 0;
    }
    IsCatalogSignatureTrusted = WldpIsCatalogSignatureTrusted(
                                  a1,
                                  a2,
                                  0,
                                  (unsigned int)&v23,
                                  0,
                                  (__int64)&v30,
                                  (__int64)&v25,
                                  (__int64)&v22,
                                  (__int64)&v29);
    v17 = IsCatalogSignatureTrusted;
    if ( IsCatalogSignatureTrusted >= 0 )
    {
      __SET_PAIR__((unsigned __int64)v19, (unsigned __int64)v18, v23);
      v31 = (_QWORD *)v23;
      while ( v18 != v19 )
      {
        LOBYTE(v16) = a3;
        if ( (unsigned __int8)WldpValidateAgainstPolicy(*v18, v16, v25) )
        {
          *a5 = v29;
          *a4 = 1;
          *a6 = 0;
          if ( (_QWORD)v23 )
          {
            std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
              v23,
              *((_QWORD *)&v23 + 1));
            std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
            v23 = 0;
            v24 = 0;
          }
          goto LABEL_25;
        }
        v31 = ++v18;
      }
      *a5 = v29;
      *a4 = 2;
      *a6 = 0;
      if ( (_QWORD)v23 )
      {
        std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
          v23,
          *((_QWORD *)&v23 + 1));
        std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
        v23 = 0;
        v24 = 0;
      }
      goto LABEL_25;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x459,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
      (const char *)(unsigned int)IsCatalogSignatureTrusted,
      v21);
    if ( (_QWORD)v23 )
    {
      std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
        v23,
        *((_QWORD *)&v23 + 1));
      std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
      v23 = 0;
      v24 = 0;
    }
    wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_____(&v26);
    result = v17;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x46C,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180018518  mov     rax, rsp
0x18001851b  push    rbx
0x18001851c  push    rsi
0x18001851d  push    rdi
0x18001851e  push    r12
0x180018520  push    r14
0x180018522  push    r15
0x180018524  sub     rsp, 0C8h
0x18001852b  mov     rdi, r9
0x18001852e  mov     r14b, r8b
0x180018531  mov     rsi, rdx
0x180018534  mov     r15, rcx
0x180018537  xor     r12d, r12d
0x18001853a  mov     [rax-78h], r12d
0x18001853e  xorps   xmm0, xmm0
0x180018541  movups  xmmword ptr [rax-70h], xmm0
0x180018545  mov     [rax-60h], r12
0x180018549  mov     [rax-74h], r12d
0x18001854d  mov     [rsp+0F8h+var_88], r12d
0x180018552  mov     byte ptr [rsp+0F8h+var_A8], r12b
0x180018557  mov     [rax-80h], r12
0x18001855b  lea     rcx, [rsp+0F8h+var_A0]
0x180018560  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x180018565  nop
0x180018566  lea     rax, [rsp+0F8h+var_80]
0x18001856b  mov     [rsp+0F8h+var_50], rax
0x180018573  mov     [rsp+0F8h+var_48], r12
0x18001857b  mov     [rsp+0F8h+var_40], 1
0x180018583  mov     [rsp+0F8h+var_78], 1
0x18001858e  mov     [rsp+0F8h+var_C0], r12
0x180018593  lea     rax, [rsp+0F8h+var_48]
0x18001859b  mov     [rsp+0F8h+var_C8], rax
0x1800185a0  lea     rax, [rsp+0F8h+var_70]
0x1800185a8  mov     [rsp+0F8h+var_D0], rax
0x1800185ad  lea     rax, [rsp+0F8h+var_A8]
0x1800185b2  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x1800185b7  lea     r9, [rsp+0F8h+var_74]
0x1800185bf  xor     r8d, r8d
0x1800185c2  mov     rcx, r15
0x1800185c5  call    WldpIsEmbedSignatureTrusted
0x1800185ca  mov     ebx, eax
0x1800185cc  lea     ecx, [r12+1]
0x1800185d1  and     ecx, 0FFFFFFFEh
0x1800185d4  mov     [rsp+0F8h+var_78], ecx
0x1800185db  lea     rcx, [rsp+0F8h+var_50]
0x1800185e3  call    wil__details__out_param_t_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t__________out_param_t_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_______
0x1800185e8  test    ebx, ebx
0x1800185ea  jns     short loc_180018657
0x1800185ec  mov     rcx, [rsp+0F8h]; this
0x1800185f4  mov     r9d, ebx; char *
0x1800185f7  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x1800185fe  mov     edx, 43Fh; void *
0x180018603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018608  nop
0x180018609  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x18001860e  test    rcx, rcx
0x180018611  jz      short loc_180018641
0x180018613  mov     rdx, qword ptr [rsp+0F8h+var_A0+8]
0x180018618  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x18001861d  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x180018622  mov     rdx, [rsp+0F8h+var_90]
0x180018627  sub     rdx, rcx
0x18001862a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001862e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018633  xorps   xmm0, xmm0
0x180018636  movdqu  [rsp+0F8h+var_A0], xmm0
0x18001863c  mov     [rsp+0F8h+var_90], r12
0x180018641  mov     rcx, [rsp+0F8h+var_80]
0x180018646  test    rcx, rcx
0x180018649  jz      short loc_180018650
0x18001864b  call    WldpFreeStateData
0x180018650  mov     eax, ebx
0x180018652  jmp     loc_1800188AD
0x180018657  mov     r8d, [rsp+0F8h+var_74]
0x18001865f  mov     dl, r14b
0x180018662  mov     rcx, [rsp+0F8h+var_80]
0x180018667  call    WldpValidateAgainstPolicy
0x18001866c  test    al, al
0x18001866e  jz      short loc_1800186DE
0x180018670  movups  xmm0, [rsp+0F8h+var_70]
0x180018678  mov     rax, [rsp+0F8h+arg_20]
0x180018680  movdqu  xmmword ptr [rax], xmm0
0x180018684  mov     dword ptr [rdi], 1
0x18001868a  mov     rax, [rsp+0F8h+arg_28]
0x180018692  mov     byte ptr [rax], 1
0x180018695  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x18001869a  test    rcx, rcx
0x18001869d  jz      short loc_1800186CD
0x18001869f  mov     rdx, qword ptr [rsp+0F8h+var_A0+8]
0x1800186a4  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x1800186a9  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x1800186ae  mov     rdx, [rsp+0F8h+var_90]
0x1800186b3  sub     rdx, rcx
0x1800186b6  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800186ba  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800186bf  xorps   xmm0, xmm0
0x1800186c2  movdqu  [rsp+0F8h+var_A0], xmm0
0x1800186c8  mov     [rsp+0F8h+var_90], r12
0x1800186cd  lea     rcx, [rsp+0F8h+var_80]
0x1800186d2  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_____
0x1800186d7  xor     eax, eax
0x1800186d9  jmp     loc_1800188AD
0x1800186de  lea     rax, [rsp+0F8h+var_70]
0x1800186e6  mov     [rsp+0F8h+var_B8], rax
0x1800186eb  lea     rax, [rsp+0F8h+var_A8]
0x1800186f0  mov     [rsp+0F8h+var_C0], rax
0x1800186f5  lea     rax, [rsp+0F8h+var_88]
0x1800186fa  mov     [rsp+0F8h+var_C8], rax
0x1800186ff  lea     rax, [rsp+0F8h+var_60]
0x180018707  mov     [rsp+0F8h+var_D0], rax
0x18001870c  mov     qword ptr [rsp+0F8h+var_D8], r12; int
0x180018711  lea     r9, [rsp+0F8h+var_A0]
0x180018716  xor     r8d, r8d
0x180018719  mov     rdx, rsi
0x18001871c  mov     rcx, r15
0x18001871f  call    WldpIsCatalogSignatureTrusted
0x180018724  mov     ebx, eax
0x180018726  test    eax, eax
0x180018728  jns     short loc_180018790
0x18001872a  mov     rcx, [rsp+0F8h]; this
0x180018732  mov     r9d, eax; char *
0x180018735  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18001873c  mov     edx, 459h; void *
0x180018741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018746  nop
0x180018747  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x18001874c  test    rcx, rcx
0x18001874f  jz      short loc_18001877F
0x180018751  mov     rdx, qword ptr [rsp+0F8h+var_A0+8]
0x180018756  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x18001875b  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x180018760  mov     rdx, [rsp+0F8h+var_90]
0x180018765  sub     rdx, rcx
0x180018768  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001876c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018771  xorps   xmm0, xmm0
0x180018774  movdqu  [rsp+0F8h+var_A0], xmm0
0x18001877a  mov     [rsp+0F8h+var_90], r12
0x18001877f  lea     rcx, [rsp+0F8h+var_80]
0x180018784  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_____
0x180018789  mov     eax, ebx
0x18001878b  jmp     loc_1800188AD
0x180018790  mov     rbx, qword ptr [rsp+0F8h+var_A0]
0x180018795  mov     [rsp+0F8h+var_58], rbx
0x18001879d  mov     rsi, qword ptr [rsp+0F8h+var_A0+8]
0x1800187a2  cmp     rbx, rsi
0x1800187a5  jz      loc_18001883E
0x1800187ab  mov     r8d, [rsp+0F8h+var_88]
0x1800187b0  mov     dl, r14b
0x1800187b3  mov     rcx, [rbx]
0x1800187b6  call    WldpValidateAgainstPolicy
0x1800187bb  test    al, al
0x1800187bd  jz      short loc_18001882D
0x1800187bf  movups  xmm0, [rsp+0F8h+var_70]
0x1800187c7  mov     rax, [rsp+0F8h+arg_20]
0x1800187cf  movdqu  xmmword ptr [rax], xmm0
0x1800187d3  mov     dword ptr [rdi], 1
0x1800187d9  mov     rax, [rsp+0F8h+arg_28]
0x1800187e1  mov     [rax], r12b
0x1800187e4  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x1800187e9  test    rcx, rcx
0x1800187ec  jz      short loc_18001881C
0x1800187ee  mov     rdx, qword ptr [rsp+0F8h+var_A0+8]
0x1800187f3  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x1800187f8  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x1800187fd  mov     rdx, [rsp+0F8h+var_90]
0x180018802  sub     rdx, rcx
0x180018805  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180018809  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001880e  xorps   xmm0, xmm0
0x180018811  movdqu  [rsp+0F8h+var_A0], xmm0
0x180018817  mov     [rsp+0F8h+var_90], r12
0x18001881c  lea     rcx, [rsp+0F8h+var_80]
0x180018821  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_____
0x180018826  xor     eax, eax
0x180018828  jmp     loc_1800188AD
0x18001882d  add     rbx, 8
0x180018831  mov     [rsp+0F8h+var_58], rbx
0x180018839  jmp     loc_1800187A2
0x18001883e  movups  xmm0, [rsp+0F8h+var_70]
0x180018846  mov     rax, [rsp+0F8h+arg_20]
0x18001884e  movdqu  xmmword ptr [rax], xmm0
0x180018852  mov     dword ptr [rdi], 2
0x180018858  mov     rax, [rsp+0F8h+arg_28]
0x180018860  mov     [rax], r12b
0x180018863  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x180018868  test    rcx, rcx
0x18001886b  jz      short loc_18001889B
0x18001886d  mov     rdx, qword ptr [rsp+0F8h+var_A0+8]
0x180018872  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x180018877  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x18001887c  mov     rdx, [rsp+0F8h+var_90]
0x180018881  sub     rdx, rcx
0x180018884  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180018888  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001888d  xorps   xmm0, xmm0
0x180018890  movdqu  [rsp+0F8h+var_A0], xmm0
0x180018896  mov     [rsp+0F8h+var_90], r12
0x18001889b  lea     rcx, [rsp+0F8h+var_80]
0x1800188a0  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_____
0x1800188a5  xor     eax, eax
0x1800188a7  jmp     short loc_1800188AD
0x1800188a9  mov     eax, [rsp+0F8h+var_88]
0x1800188ad  add     rsp, 0C8h
0x1800188b4  pop     r15
0x1800188b6  pop     r14
0x1800188b8  pop     r12
0x1800188ba  pop     rdi
0x1800188bb  pop     rsi
0x1800188bc  pop     rbx
0x1800188bd  retn
```
