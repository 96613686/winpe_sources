# WldpIsFileTrusted2(void *,_GUID const &,ulong,bool,_GUID const &,ulong *)

- ea: `0x18001e1d4`
- end: `0x18001e622`
- name: `?WldpIsFileTrusted2@@YAJPEAXAEBU_GUID@@K_N1PEAK@Z`
- size: `1102`
- prototype: `__int64 __fastcall(void *, struct _GUID *, int, char, const struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18002e8b0`

## callees

- `0x1800159a0`
- `0x1800159f0`
- `0x1800175fc`
- `0x180018518`
- `0x180018918`
- `0x18001e1d4`
- `0x18001e6b8`
- `0x18001f3fc`
- `0x18001f8c4`
- `0x180021ec0`
- `0x1800229ec`
- `0x180022a10`
- `0x18002b90c`
- `0x18002c64c`

## import_xrefs

- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x18001e4f6`
- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x18001e4f6`
- `WINTRUST!WTLogConfigCiSignerEvent` at `0x18001e531`
- `WINTRUST!WTLogConfigCiSignerEvent` at `0x18001e531`

## pseudocode

```c
__int64 __fastcall WldpIsFileTrusted2(
        void *a1,
        struct _GUID *a2,
        int a3,
        char a4,
        const struct _GUID *a5,
        unsigned int *a6)
{
  __int64 v9; // r13
  char v10; // si
  int v11; // eax
  bool v12; // r15
  int v13; // r8d
  unsigned __int16 **v14; // rdx
  int IsFileTrustedByConfigCi; // eax
  __int64 v16; // r8
  unsigned int v17; // edi
  int v18; // ebx
  int v19; // ecx
  BOOL v20; // r14d
  int *v21; // rsi
  int v22; // r9d
  const unsigned __int16 *v23; // r8
  unsigned __int16 **v24; // r8
  __int64 v25; // rcx
  const struct _GUID *v26; // r14
  const struct _GUID *v27; // rax
  unsigned __int64 v28; // rsi
  const struct _GUID *i; // rcx
  unsigned __int64 v30; // r8
  const char *v31; // r9
  __int64 result; // rax
  _BYTE v33[4]; // [rsp+40h] [rbp-1C8h] BYREF
  int v34; // [rsp+44h] [rbp-1C4h] BYREF
  int v35; // [rsp+48h] [rbp-1C0h]
  const struct _GUID *v36; // [rsp+50h] [rbp-1B8h]
  __int128 v37; // [rsp+58h] [rbp-1B0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-1A0h]
  __int128 v39; // [rsp+70h] [rbp-198h] BYREF
  __int64 v40; // [rsp+80h] [rbp-188h]
  __int64 v41; // [rsp+88h] [rbp-180h] BYREF
  void *Buf1; // [rsp+90h] [rbp-178h]
  unsigned int *v43; // [rsp+98h] [rbp-170h]
  __int128 v44; // [rsp+A0h] [rbp-168h] BYREF
  unsigned __int16 *v45[3]; // [rsp+B0h] [rbp-158h] BYREF
  unsigned __int64 v46; // [rsp+C8h] [rbp-140h]
  int v47; // [rsp+D0h] [rbp-138h] BYREF
  int v48; // [rsp+D4h] [rbp-134h] BYREF
  int v49; // [rsp+D8h] [rbp-130h]
  int v50; // [rsp+DCh] [rbp-12Ch]
  char v51; // [rsp+E0h] [rbp-128h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  Buf1 = a2;
  v36 = a5;
  v43 = a6;
  try
  {
    v35 = 0;
    v44 = 0;
    v34 = 0;
    v33[0] = 0;
    v9 = 0;
    v41 = 0;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v39);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v37);
    v47 = 0;
    memset_0(&v48, 0, 0xE4u);
    if ( (a3 & 0x80000005) == 0x80000005 )
    {
      v10 = 1;
      v11 = -2147483641;
    }
    else
    {
      v10 = 0;
      v11 = -2147483620;
    }
    v12 = (v11 & a3) == v11;
    GetPathnameFromHandle(v45, a1);
    v14 = v45;
    if ( v10 )
    {
      if ( v46 > 7 )
        v14 = (unsigned __int16 **)v45[0];
      IsFileTrustedByConfigCi = WldpIsFileTrustedByConfigCi(a1, v14, &v37, &v39, &v41, &v34, &v44, v33);
      v35 = IsFileTrustedByConfigCi;
      v9 = v41;
    }
    else
    {
      if ( v46 > 7 )
        LODWORD(v14) = v45[0];
      LOBYTE(v13) = a4;
      IsFileTrustedByConfigCi = WldpIsFileTrustedBySbcp(
                                  (_DWORD)a1,
                                  (_DWORD)v14,
                                  v13,
                                  (unsigned int)&v34,
                                  (__int64)&v44,
                                  (__int64)v33);
      v35 = IsFileTrustedByConfigCi;
    }
    v17 = IsFileTrustedByConfigCi;
    if ( IsFileTrustedByConfigCi < 0 )
    {
      v19 = IsFileTrustedByConfigCi;
      v48 = IsFileTrustedByConfigCi;
      v20 = v12;
      v18 = v12 + 2;
      v49 = v18;
      v34 = v18;
    }
    else
    {
      v18 = v34;
      if ( v34 == 1 )
        v19 = 0;
      else
        v19 = v10 != 0 ? -790036478 : -800915454;
      v48 = v19;
      v49 = v34;
      v20 = v12;
    }
    if ( v19 >= 0 && v18 == 1 )
    {
      LOBYTE(v16) = v33[0];
      v17 = WldpCheckSipAgainstHost(Buf1, &v44, v16);
      v35 = v17;
      v19 = -2147016663;
      if ( v17 == -2147016663 )
      {
        v48 = -2147016663;
        v18 = v20 + 2;
        v49 = v20 + 2;
        v34 = v20 + 2;
      }
      else
      {
        v19 = v48;
      }
    }
    if ( v10 )
    {
      if ( (_QWORD)v39 == *((_QWORD *)&v39 + 1) )
      {
        v21 = &v47;
      }
      else
      {
        v21 = (int *)(v39 + 232 * v9);
        v21[1] = v19;
        v21[2] = v49;
        v21[3] = v50;
        *((_BYTE *)v21 + 16) = v51;
        v22 = memcmp_0(Buf1, &WLDP_HOST_MSI, 0x10u) == 0 ? 6 : 0;
        v23 = (const unsigned __int16 *)v45;
        if ( v46 > 7 )
          v23 = v45[0];
        WldpSmartAppControlTelemetryAndToast(
          (struct CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *)v21,
          (struct SAC_REPUTATION_EXTRA_INFO_ *)(v39 + 80),
          v23,
          v22,
          a1);
      }
      v24 = v45;
      if ( v46 > 7 )
        v24 = (unsigned __int16 **)v45[0];
      if ( (_QWORD)v37 == *((_QWORD *)&v37 + 1) )
        v25 = 0;
      else
        v25 = *(_QWORD *)(v37 + 8 * v9);
      v26 = v36;
      WTLogConfigCiScriptEvent2(v25, a1, v24, -1, 0, v21, v36);
      if ( v49 != 1 )
      {
        v27 = 0;
        v28 = 0;
        for ( i = 0; ; i = v27 )
        {
          v36 = v27;
          v30 = (__int64)(*((_QWORD *)&v37 + 1) - v37) >> 3;
          if ( v28 >= v30 )
            break;
          WTLogConfigCiSignerEvent(*(_QWORD *)(v37 + 8LL * (_QWORD)i), v26, v30, (unsigned int)v27);
          v27 = (const struct _GUID *)(v28 + 1);
          v28 = (unsigned __int64)v27;
        }
      }
    }
    *v43 = v18;
    if ( v12 )
      v17 = 0;
    std::wstring::~wstring(v45);
    if ( (_QWORD)v37 )
    {
      std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
        v37,
        *((_QWORD *)&v37 + 1));
      std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFF8uLL);
      v37 = 0;
      v38 = 0;
    }
    if ( (_QWORD)v39 )
    {
      std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
        v39,
        *((_QWORD *)&v39 + 1));
      std::_Deallocate<16>(v39, 8 * ((v40 - (__int64)v39) >> 3));
      v39 = 0;
      v40 = 0;
    }
    result = v17;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6ED,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                           v31);
  }
  return result;
}

```

## disassembly

```asm
0x18001e1d4  push    rbx
0x18001e1d6  push    rsi
0x18001e1d7  push    rdi
0x18001e1d8  push    r12
0x18001e1da  push    r13
0x18001e1dc  push    r14
0x18001e1de  push    r15
0x18001e1e0  sub     rsp, 1D0h
0x18001e1e7  mov     rax, cs:__security_cookie
0x18001e1ee  xor     rax, rsp
0x18001e1f1  mov     [rsp+208h+var_48], rax
0x18001e1f9  mov     dil, r9b
0x18001e1fc  mov     ebx, r8d
0x18001e1ff  mov     [rsp+208h+Buf1], rdx
0x18001e207  mov     r12, rcx
0x18001e20a  mov     rax, [rsp+208h+arg_20]
0x18001e212  mov     [rsp+208h+var_1B8], rax
0x18001e217  mov     rax, [rsp+208h+arg_28]
0x18001e21f  mov     [rsp+208h+var_170], rax
0x18001e227  xor     r14d, r14d
0x18001e22a  mov     [rsp+208h+var_1C0], r14d
0x18001e22f  xorps   xmm0, xmm0
0x18001e232  movups  [rsp+208h+var_168], xmm0
0x18001e23a  mov     [rsp+208h+var_1C4], r14d
0x18001e23f  mov     [rsp+208h+var_1C8], r14b
0x18001e244  mov     r13d, r14d
0x18001e247  mov     [rsp+208h+var_180], r14
0x18001e24f  lea     rcx, [rsp+208h+var_198]
0x18001e254  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x18001e259  nop
0x18001e25a  lea     rcx, [rsp+208h+var_1B0]
0x18001e25f  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x18001e264  nop
0x18001e265  mov     [rsp+208h+var_138], r14d
0x18001e26d  xor     edx, edx; Val
0x18001e26f  mov     r8d, 0E4h; Size
0x18001e275  lea     rcx, [rsp+208h+var_134]; void *
0x18001e27d  call    memset_0
0x18001e282  mov     eax, ebx
0x18001e284  mov     ecx, 80000005h
0x18001e289  and     eax, ecx
0x18001e28b  cmp     eax, ecx
0x18001e28d  jnz     short loc_18001E299
0x18001e28f  mov     sil, 1
0x18001e292  mov     eax, 80000007h
0x18001e297  jmp     short loc_18001E2A1
0x18001e299  mov     sil, r14b
0x18001e29c  mov     eax, 8000001Ch
0x18001e2a1  and     ebx, eax
0x18001e2a3  cmp     ebx, eax
0x18001e2a5  setz    r15b
0x18001e2a9  mov     rdx, r12
0x18001e2ac  lea     rcx, [rsp+208h+var_158]
0x18001e2b4  call    ?GetPathnameFromHandle@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetPathnameFromHandle(void *)
0x18001e2b9  nop
0x18001e2ba  lea     rdx, [rsp+208h+var_158]
0x18001e2c2  lea     rax, [rsp+208h+var_1C8]
0x18001e2c7  mov     rcx, r12
0x18001e2ca  test    sil, sil
0x18001e2cd  jz      short loc_18001E327
0x18001e2cf  cmp     [rsp+208h+var_140], 7
0x18001e2d8  cmova   rdx, [rsp+208h+var_158]
0x18001e2e1  mov     [rsp+208h+var_1D0], rax
0x18001e2e6  lea     rax, [rsp+208h+var_168]
0x18001e2ee  mov     [rsp+208h+var_1D8], rax
0x18001e2f3  lea     rax, [rsp+208h+var_1C4]
0x18001e2f8  mov     [rsp+208h+var_1E0], rax
0x18001e2fd  lea     rax, [rsp+208h+var_180]
0x18001e305  mov     [rsp+208h+var_1E8], rax
0x18001e30a  lea     r9, [rsp+208h+var_198]
0x18001e30f  lea     r8, [rsp+208h+var_1B0]
0x18001e314  call    WldpIsFileTrustedByConfigCi
0x18001e319  mov     [rsp+208h+var_1C0], eax
0x18001e31d  mov     r13, [rsp+208h+var_180]
0x18001e325  jmp     short loc_18001E35C
0x18001e327  cmp     [rsp+208h+var_140], 7
0x18001e330  cmova   rdx, [rsp+208h+var_158]
0x18001e339  mov     [rsp+208h+var_1E0], rax
0x18001e33e  lea     rax, [rsp+208h+var_168]
0x18001e346  mov     [rsp+208h+var_1E8], rax
0x18001e34b  lea     r9, [rsp+208h+var_1C4]
0x18001e350  mov     r8b, dil
0x18001e353  call    WldpIsFileTrustedBySbcp
0x18001e358  mov     [rsp+208h+var_1C0], eax
0x18001e35c  mov     edi, eax
0x18001e35e  test    eax, eax
0x18001e360  js      short loc_18001E397
0x18001e362  mov     ebx, [rsp+208h+var_1C4]
0x18001e366  cmp     ebx, 1
0x18001e369  jz      short loc_18001E380
0x18001e36b  mov     al, sil
0x18001e36e  neg     al
0x18001e370  sbb     ecx, ecx
0x18001e372  and     ecx, 0A60000h
0x18001e378  add     ecx, 0D0430002h
0x18001e37e  jmp     short loc_18001E383
0x18001e380  mov     ecx, r14d
0x18001e383  mov     [rsp+208h+var_134], ecx
0x18001e38a  mov     [rsp+208h+var_130], ebx
0x18001e391  movzx   r14d, r15b
0x18001e395  jmp     short loc_18001E3B3
0x18001e397  mov     ecx, edi
0x18001e399  mov     [rsp+208h+var_134], ecx
0x18001e3a0  movzx   r14d, r15b
0x18001e3a4  lea     ebx, [r14+2]
0x18001e3a8  mov     [rsp+208h+var_130], ebx
0x18001e3af  mov     [rsp+208h+var_1C4], ebx
0x18001e3b3  mov     eax, ebx
0x18001e3b5  test    ecx, ecx
0x18001e3b7  js      short loc_18001E406
0x18001e3b9  cmp     eax, 1
0x18001e3bc  jnz     short loc_18001E406
0x18001e3be  mov     r8b, [rsp+208h+var_1C8]
0x18001e3c3  lea     rdx, [rsp+208h+var_168]
0x18001e3cb  mov     rcx, [rsp+208h+Buf1]
0x18001e3d3  call    WldpCheckSipAgainstHost
0x18001e3d8  mov     edi, eax
0x18001e3da  mov     [rsp+208h+var_1C0], eax
0x18001e3de  mov     ecx, 80072029h
0x18001e3e3  cmp     eax, ecx
0x18001e3e5  jnz     short loc_18001E3FF
0x18001e3e7  mov     [rsp+208h+var_134], ecx
0x18001e3ee  lea     ebx, [r14+2]
0x18001e3f2  mov     [rsp+208h+var_130], ebx
0x18001e3f9  mov     [rsp+208h+var_1C4], ebx
0x18001e3fd  jmp     short loc_18001E406
0x18001e3ff  mov     ecx, [rsp+208h+var_134]
0x18001e406  test    sil, sil
0x18001e409  jz      loc_18001E543
0x18001e40f  mov     rdx, qword ptr [rsp+208h+var_198]
0x18001e414  cmp     rdx, qword ptr [rsp+208h+var_198+8]
0x18001e419  jnz     short loc_18001E428
0x18001e41b  lea     rsi, [rsp+208h+var_138]
0x18001e423  jmp     loc_18001E4A9
0x18001e428  imul    rsi, r13, 0E8h
0x18001e42f  add     rsi, rdx
0x18001e432  mov     [rsi+4], ecx
0x18001e435  mov     eax, [rsp+208h+var_130]
0x18001e43c  mov     [rsi+8], eax
0x18001e43f  mov     eax, [rsp+208h+var_12C]
0x18001e446  mov     [rsi+0Ch], eax
0x18001e449  mov     al, [rsp+208h+var_128]
0x18001e450  mov     [rsi+10h], al
0x18001e453  mov     r8d, 10h; Size
0x18001e459  lea     rdx, WLDP_HOST_MSI; Buf2
0x18001e460  mov     rcx, [rsp+208h+Buf1]; Buf1
0x18001e468  call    memcmp_0
0x18001e46d  neg     eax
0x18001e46f  sbb     r9d, r9d
0x18001e472  not     r9d
0x18001e475  and     r9d, 6; unsigned int
0x18001e479  lea     r8, [rsp+208h+var_158]
0x18001e481  cmp     [rsp+208h+var_140], 7
0x18001e48a  cmova   r8, [rsp+208h+var_158]; unsigned __int16 *
0x18001e493  mov     rdx, qword ptr [rsp+208h+var_198]
0x18001e498  add     rdx, 50h ; 'P'; struct SAC_REPUTATION_EXTRA_INFO_ *
0x18001e49c  mov     [rsp+208h+var_1E8], r12; void *
0x18001e4a1  mov     rcx, rsi; struct CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *
0x18001e4a4  call    ?WldpSmartAppControlTelemetryAndToast@@YAXPEAUCONFIG_CI_PROV_INFO_RESULT2_PRIVATE_@@PEAUSAC_REPUTATION_EXTRA_INFO_@@PEBGKQEAX@Z; WldpSmartAppControlTelemetryAndToast(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *,SAC_REPUTATION_EXTRA_INFO_ *,ushort const *,ulong,void * const)
0x18001e4a9  lea     r8, [rsp+208h+var_158]
0x18001e4b1  cmp     [rsp+208h+var_140], 7
0x18001e4ba  cmova   r8, [rsp+208h+var_158]
0x18001e4c3  mov     rcx, qword ptr [rsp+208h+var_1B0]
0x18001e4c8  cmp     rcx, qword ptr [rsp+208h+var_1B0+8]
0x18001e4cd  jnz     short loc_18001E4D3
0x18001e4cf  xor     ecx, ecx
0x18001e4d1  jmp     short loc_18001E4D7
0x18001e4d3  mov     rcx, [rcx+r13*8]
0x18001e4d7  mov     r14, [rsp+208h+var_1B8]
0x18001e4dc  mov     [rsp+208h+var_1D8], r14
0x18001e4e1  mov     [rsp+208h+var_1E0], rsi
0x18001e4e6  mov     [rsp+208h+var_1E8], 0
0x18001e4ef  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001e4f3  mov     rdx, r12
0x18001e4f6  call    cs:__imp_WTLogConfigCiScriptEvent2
0x18001e4fc  cmp     [rsp+208h+var_130], 1
0x18001e504  jz      short loc_18001E543
0x18001e506  xor     eax, eax
0x18001e508  xor     esi, esi
0x18001e50a  xor     ecx, ecx
0x18001e50c  mov     [rsp+208h+var_1B8], rax
0x18001e511  mov     r10, qword ptr [rsp+208h+var_1B0]
0x18001e516  mov     r8, qword ptr [rsp+208h+var_1B0+8]
0x18001e51b  sub     r8, r10
0x18001e51e  sar     r8, 3
0x18001e522  cmp     rsi, r8
0x18001e525  jnb     short loc_18001E543
0x18001e527  mov     r9d, eax
0x18001e52a  mov     rdx, r14
0x18001e52d  mov     rcx, [r10+rcx*8]
0x18001e531  call    cs:__imp_WTLogConfigCiSignerEvent
0x18001e537  lea     rax, [rsi+1]
0x18001e53b  mov     rsi, rax
0x18001e53e  mov     rcx, rax
0x18001e541  jmp     short loc_18001E50C
0x18001e543  mov     rax, [rsp+208h+var_170]
0x18001e54b  mov     [rax], ebx
0x18001e54d  xor     eax, eax
0x18001e54f  test    r15b, r15b
0x18001e552  cmovnz  edi, eax
0x18001e555  lea     rcx, [rsp+208h+var_158]
0x18001e55d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e562  nop
0x18001e563  mov     rcx, qword ptr [rsp+208h+var_1B0]
0x18001e568  test    rcx, rcx
0x18001e56b  jz      short loc_18001E59F
0x18001e56d  mov     rdx, qword ptr [rsp+208h+var_1B0+8]
0x18001e572  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x18001e577  mov     rcx, qword ptr [rsp+208h+var_1B0]
0x18001e57c  mov     rdx, [rsp+208h+var_1A0]
0x18001e581  sub     rdx, rcx
0x18001e584  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001e588  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e58d  xorps   xmm0, xmm0
0x18001e590  movdqu  [rsp+208h+var_1B0], xmm0
0x18001e596  mov     [rsp+208h+var_1A0], 0
0x18001e59f  mov     rcx, qword ptr [rsp+208h+var_198]
0x18001e5a4  test    rcx, rcx
0x18001e5a7  jz      short loc_18001E5F6
0x18001e5a9  mov     rdx, qword ptr [rsp+208h+var_198+8]
0x18001e5ae  call    std___Destroy_range_std__allocator_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____
0x18001e5b3  mov     rcx, qword ptr [rsp+208h+var_198]
0x18001e5b8  mov     rdx, [rsp+208h+var_188]
0x18001e5c0  sub     rdx, rcx
0x18001e5c3  sar     rdx, 3
0x18001e5c7  mov     rax, 34F72C234F72C235h
0x18001e5d1  imul    rdx, rax
0x18001e5d5  imul    rdx, 0E8h
0x18001e5dc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e5e1  xorps   xmm0, xmm0
0x18001e5e4  movdqu  [rsp+208h+var_198], xmm0
0x18001e5ea  mov     [rsp+208h+var_188], 0
0x18001e5f6  mov     eax, edi
0x18001e5f8  jmp     short loc_18001E5FE
0x18001e5fa  mov     eax, [rsp+208h+var_1C4]
0x18001e5fe  mov     rcx, [rsp+208h+var_48]
0x18001e606  xor     rcx, rsp; StackCookie
0x18001e609  call    __security_check_cookie
0x18001e60e  add     rsp, 1D0h
0x18001e615  pop     r15
0x18001e617  pop     r14
0x18001e619  pop     r13
0x18001e61b  pop     r12
0x18001e61d  pop     rdi
0x18001e61e  pop     rsi
0x18001e61f  pop     rbx
0x18001e620  retn
```
