# tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)

- ea: `0x18001aba8`
- end: `0x18001aec2`
- name: `?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z`
- size: `794`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18001a704`
- `0x18001a9a4`
- `0x18001aec8`

## callees

- `0x180008320`
- `0x180009018`
- `0x1800129cc`
- `0x1800135e4`
- `0x180013b98`
- `0x18001aa5c`
- `0x18001aba8`
- `0x18001c834`
- `0x18001ceb4`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<1,0,0>::deserialize_data(__int64 *a1, __int64 a2)
{
  int *v4; // r8
  unsigned int v5; // ecx
  __int64 *v6; // r14
  char v7; // bl
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int16 v12; // ax
  unsigned __int64 v13; // r8
  __int64 v14; // rdx
  int *v15; // rcx
  __int64 v16; // rcx
  unsigned __int8 v17[8]; // [rsp+30h] [rbp-D0h] BYREF
  const char *v18; // [rsp+38h] [rbp-C8h] BYREF
  char v19; // [rsp+40h] [rbp-C0h]
  __int64 *v20; // [rsp+48h] [rbp-B8h]
  int *v21; // [rsp+50h] [rbp-B0h] BYREF
  int *v22; // [rsp+58h] [rbp-A8h]
  int *v23; // [rsp+60h] [rbp-A0h]
  char v24; // [rsp+68h] [rbp-98h]
  const char *v25; // [rsp+70h] [rbp-90h]
  char v26; // [rsp+78h] [rbp-88h]
  __int64 *v27; // [rsp+80h] [rbp-80h]
  const char *v28; // [rsp+88h] [rbp-78h]
  char v29; // [rsp+90h] [rbp-70h]
  __int64 *v30; // [rsp+98h] [rbp-68h]
  int **v31; // [rsp+A0h] [rbp-60h] BYREF
  int v32; // [rsp+A8h] [rbp-58h]
  const char *v33; // [rsp+B0h] [rbp-50h]
  __int16 v34; // [rsp+B8h] [rbp-48h]
  char v35; // [rsp+C0h] [rbp-40h]
  _DWORD v36[25]; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int64 v37; // [rsp+128h] [rbp+28h]

  if ( (*(_DWORD *)(a2 + 20) & 0x1000) == 0 )
    goto LABEL_35;
  v4 = *(int **)(a2 + 24);
  v21 = v4;
  v22 = v4;
  v23 = v4;
  v24 = 0;
  if ( v4
    && *(_BYTE *)v4
    && *((_BYTE *)v4 + 1)
    && *((_BYTE *)v4 + 2)
    && *((_BYTE *)v4 + 3)
    && !*((_BYTE *)v4 + 4)
    && (*v4 & 0xC0C0C0C0) == 0x80408040 )
  {
    v5 = *v4;
    v22 = (int *)((char *)v4 + 5);
    v23 = (int *)((char *)v4
                + (v5 & 0x3F | ((v5 & 0x3F00 | ((v5 & 0x3F0000 | (unsigned __int64)((v5 >> 2) & 0xFC00000)) >> 2)) >> 2)));
  }
  else
  {
    v24 = 1;
  }
  v6 = a1 + 1;
  v7 = *((_BYTE *)a1 + 33);
  v31 = &v21;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v37 = 0;
  LOBYTE(v8) = 0x80;
  tson::input_archive::consume_expected_marker(&v31, v8, 2147943177LL);
  LOBYTE(v9) = v7;
  tson::input_archive::consume_expected_marker(&v31, v9, v10);
  if ( v37 >= 0x19 )
    v35 = 1;
  else
    v36[v37++] = 0;
  if ( (*((_DWORD *)a1 + 5) & 0x40000) != 0 )
  {
    if ( a1[3] )
    {
      v33 = "name";
      LOBYTE(v34) = 4;
      if ( tson::input_archive::search((tson::input_archive *)&v31) )
      {
        LOBYTE(v11) = 23;
        tson::input_archive::consume_expected_marker(&v31, v11, 2147944029LL);
        v17[0] = 0;
        tson::read_buffer::consume<unsigned char>(v31, v17);
        if ( v17[0] > 1u )
        {
          v12 = tson::input_archive::upgrade_string_size((tson::input_archive *)&v31, v17[0]);
          v13 = (unsigned __int64)v31[1] + (unsigned __int16)(v12 - 1);
          if ( v13 > (unsigned __int64)v31[2] )
            *((_BYTE *)v31 + 24) = 1;
          else
            v31[1] = (int *)v13;
        }
      }
    }
    else
    {
      v18 = "name";
      v19 = 4;
      v20 = a1 + 1;
      tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(
        &v31,
        &v18);
      if ( *v6 )
        a1[3] = *v6;
    }
  }
  v18 = "flags";
  v19 = 5;
  v20 = a1 + 15;
  v25 = "errors";
  v26 = 6;
  v27 = a1 + 9;
  v28 = "log";
  v29 = 3;
  v30 = a1 + 12;
  tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v31);
  v15 = v31[1];
  if ( v15 >= v31[2] )
    goto LABEL_26;
  LOBYTE(v14) = 8;
  if ( *(_BYTE *)v15 == 8 )
  {
    tson::input_archive::consume_expected_marker(&v31, v14, 2147944029LL);
  }
  else
  {
LABEL_26:
    v16 = *a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v16, 0, 0, &v31, 0)
        && !*((_BYTE *)a1 + 160) )
      {
        *((_BYTE *)a1 + 160) = 3;
        *((_WORD *)a1 + 81) = 16397;
        a1[21] = 0;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, int ***))(*(_QWORD *)v16 + 16LL))(v16, &v31);
    }
  }
  if ( v32 < 0 || *((_BYTE *)v31 + 24) || v35 )
LABEL_35:
    *((_DWORD *)a1 + 16) |= 0x80000u;
  else
    *((_DWORD *)a1 + 46) = *(_DWORD *)(a2 + 16);
}

```

## disassembly

```asm
0x18001aba8  mov     [rsp-8+arg_8], rbx
0x18001abad  mov     [rsp-8+arg_10], rsi
0x18001abb2  push    rbp
0x18001abb3  push    rdi
0x18001abb4  push    r12
0x18001abb6  push    r14
0x18001abb8  push    r15
0x18001abba  lea     rbp, [rsp-40h]
0x18001abbf  sub     rsp, 140h
0x18001abc6  mov     rax, cs:__security_cookie
0x18001abcd  xor     rax, rsp
0x18001abd0  mov     [rbp+60h+var_30], rax
0x18001abd4  mov     rsi, rdx
0x18001abd7  mov     rdi, rcx
0x18001abda  test    dword ptr [rdx+14h], 1000h
0x18001abe1  jz      loc_18001AE95
0x18001abe7  mov     r8, [rdx+18h]
0x18001abeb  mov     [rsp+160h+var_110], r8
0x18001abf0  mov     [rsp+160h+var_108], r8
0x18001abf5  mov     [rsp+160h+var_100], r8
0x18001abfa  xor     r15d, r15d
0x18001abfd  mov     [rsp+160h+var_F8], r15b
0x18001ac02  lea     r12d, [r15+1]
0x18001ac06  test    r8, r8
0x18001ac09  jz      short loc_18001AC7B
0x18001ac0b  cmp     [r8], r15b
0x18001ac0e  jz      short loc_18001AC7B
0x18001ac10  cmp     [r8+1], r15b
0x18001ac14  jz      short loc_18001AC7B
0x18001ac16  cmp     [r8+2], r15b
0x18001ac1a  jz      short loc_18001AC7B
0x18001ac1c  cmp     [r8+3], r15b
0x18001ac20  jz      short loc_18001AC7B
0x18001ac22  cmp     [r8+4], r15b
0x18001ac26  jnz     short loc_18001AC7B
0x18001ac28  mov     eax, [r8]
0x18001ac2b  and     eax, 0C0C0C0C0h
0x18001ac30  cmp     eax, 80408040h
0x18001ac35  jnz     short loc_18001AC7B
0x18001ac37  mov     ecx, [r8]
0x18001ac3a  lea     rax, [r8+5]
0x18001ac3e  mov     [rsp+160h+var_108], rax
0x18001ac43  mov     edx, ecx
0x18001ac45  shr     rdx, 2
0x18001ac49  and     edx, 0FC00000h
0x18001ac4f  mov     eax, ecx
0x18001ac51  and     eax, 3F0000h
0x18001ac56  or      rdx, rax
0x18001ac59  shr     rdx, 2
0x18001ac5d  mov     eax, ecx
0x18001ac5f  and     eax, 3F00h
0x18001ac64  or      rdx, rax
0x18001ac67  shr     rdx, 2
0x18001ac6b  and     ecx, 3Fh
0x18001ac6e  or      rdx, rcx
0x18001ac71  add     rdx, r8
0x18001ac74  mov     [rsp+160h+var_100], rdx
0x18001ac79  jmp     short loc_18001AC80
0x18001ac7b  mov     [rsp+160h+var_F8], r12b
0x18001ac80  lea     r14, [rdi+8]
0x18001ac84  mov     bl, [r14+19h]
0x18001ac88  lea     rax, [rsp+160h+var_110]
0x18001ac8d  mov     [rbp+60h+var_C0], rax
0x18001ac91  mov     [rbp+60h+var_B8], r15d
0x18001ac95  mov     [rbp+60h+var_B0], r15
0x18001ac99  mov     [rbp+60h+var_A8], r15w
0x18001ac9e  mov     [rbp+60h+var_A0], r15b
0x18001aca2  xor     edx, edx; Val
0x18001aca4  lea     r8d, [rdx+64h]; Size
0x18001aca8  lea     rcx, [rbp+60h+var_9C]; void *
0x18001acac  call    memset_0
0x18001acb1  mov     [rbp+60h+var_38], r15
0x18001acb5  mov     r8d, 80070309h
0x18001acbb  mov     dl, 80h
0x18001acbd  lea     rcx, [rbp+60h+var_C0]
0x18001acc1  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001acc6  mov     dl, bl
0x18001acc8  lea     rcx, [rbp+60h+var_C0]
0x18001accc  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001acd1  mov     r8, [rbp+60h+var_38]
0x18001acd5  cmp     r8, 19h
0x18001acd9  jnb     short loc_18001ACE6
0x18001acdb  mov     [rbp+r8*4+60h+var_9C], r15d
0x18001ace0  add     [rbp+60h+var_38], r12
0x18001ace4  jmp     short loc_18001ACEA
0x18001ace6  mov     [rbp+60h+var_A0], r12b
0x18001acea  mov     ebx, 8007065Dh
0x18001acef  test    dword ptr [rdi+14h], 40000h
0x18001acf6  jz      loc_18001AD98
0x18001acfc  lea     rax, aName; "name"
0x18001ad03  lea     rcx, [rbp+60h+var_C0]; this
0x18001ad07  cmp     [rdi+18h], r15
0x18001ad0b  jnz     short loc_18001AD34
0x18001ad0d  mov     [rsp+160h+var_128], rax
0x18001ad12  mov     [rsp+160h+var_120], 4
0x18001ad17  mov     [rsp+160h+var_118], r14
0x18001ad1c  lea     rdx, [rsp+160h+var_128]
0x18001ad21  call    ??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z; tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)
0x18001ad26  mov     rax, [r14]
0x18001ad29  test    rax, rax
0x18001ad2c  jz      short loc_18001AD98
0x18001ad2e  mov     [rdi+18h], rax
0x18001ad32  jmp     short loc_18001AD98
0x18001ad34  mov     [rbp+60h+var_B0], rax
0x18001ad38  mov     byte ptr [rbp+60h+var_A8], 4
0x18001ad3c  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x18001ad41  test    al, al
0x18001ad43  jz      short loc_18001AD98
0x18001ad45  mov     r8d, ebx
0x18001ad48  mov     dl, 17h
0x18001ad4a  lea     rcx, [rbp+60h+var_C0]
0x18001ad4e  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001ad53  mov     [rsp+160h+var_130], r15b
0x18001ad58  lea     rdx, [rsp+160h+var_130]
0x18001ad5d  mov     rcx, [rbp+60h+var_C0]
0x18001ad61  call    ??$consume@E@read_buffer@tson@@QEAA_NAEAE@Z; tson::read_buffer::consume<uchar>(uchar &)
0x18001ad66  mov     dl, [rsp+160h+var_130]; unsigned __int8
0x18001ad6a  cmp     dl, r12b
0x18001ad6d  jbe     short loc_18001AD98
0x18001ad6f  lea     rcx, [rbp+60h+var_C0]; this
0x18001ad73  call    ?upgrade_string_size@input_archive@tson@@AEAAGE@Z; tson::input_archive::upgrade_string_size(uchar)
0x18001ad78  sub     ax, r12w
0x18001ad7c  movzx   r8d, ax
0x18001ad80  mov     rdx, [rbp+60h+var_C0]
0x18001ad84  add     r8, [rdx+8]
0x18001ad88  cmp     r8, [rdx+10h]
0x18001ad8c  ja      short loc_18001AD94
0x18001ad8e  mov     [rdx+8], r8
0x18001ad92  jmp     short loc_18001AD98
0x18001ad94  mov     [rdx+18h], r12b
0x18001ad98  lea     rax, aFlags; "flags"
0x18001ad9f  mov     [rsp+160h+var_128], rax
0x18001ada4  mov     [rsp+160h+var_120], 5
0x18001ada9  lea     rax, [rdi+78h]
0x18001adad  mov     [rsp+160h+var_118], rax
0x18001adb2  lea     rax, aErrors; "errors"
0x18001adb9  mov     [rsp+160h+var_F0], rax
0x18001adbe  mov     [rsp+160h+var_E8], 6
0x18001adc3  lea     rax, [rdi+48h]
0x18001adc7  mov     [rbp+60h+var_E0], rax
0x18001adcb  lea     rax, aLog; "log"
0x18001add2  mov     [rbp+60h+var_D8], rax
0x18001add6  mov     [rbp+60h+var_D0], 3
0x18001adda  lea     rax, [rdi+60h]
0x18001adde  mov     [rbp+60h+var_C8], rax
0x18001ade2  lea     r9, [rsp+160h+var_128]
0x18001ade7  lea     r8, [rsp+160h+var_F0]
0x18001adec  lea     rdx, [rbp+60h+var_D8]
0x18001adf0  lea     rcx, [rbp+60h+var_C0]; this
0x18001adf4  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18001adf9  mov     rax, [rbp+60h+var_C0]
0x18001adfd  mov     rcx, [rax+8]
0x18001ae01  cmp     rcx, [rax+10h]
0x18001ae05  jnb     short loc_18001AE1B
0x18001ae07  mov     dl, 8
0x18001ae09  cmp     [rcx], dl
0x18001ae0b  jnz     short loc_18001AE1B
0x18001ae0d  mov     r8d, ebx
0x18001ae10  lea     rcx, [rbp+60h+var_C0]
0x18001ae14  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001ae19  jmp     short loc_18001AE74
0x18001ae1b  mov     rcx, [rdi]
0x18001ae1e  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18001ae25  test    rax, rax
0x18001ae28  jz      short loc_18001AE63
0x18001ae2a  mov     [rsp+160h+var_140], r15
0x18001ae2f  lea     r9, [rbp+60h+var_C0]
0x18001ae33  xor     r8d, r8d
0x18001ae36  xor     edx, edx
0x18001ae38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae3d  test    al, al
0x18001ae3f  jnz     short loc_18001AE74
0x18001ae41  cmp     [rdi+0A0h], r15b
0x18001ae48  jnz     short loc_18001AE74
0x18001ae4a  mov     byte ptr [rdi+0A0h], 3
0x18001ae51  mov     word ptr [rdi+0A2h], 400Dh
0x18001ae5a  mov     [rdi+0A8h], r15
0x18001ae61  jmp     short loc_18001AE74
0x18001ae63  mov     rax, [rcx]
0x18001ae66  lea     rdx, [rbp+60h+var_C0]
0x18001ae6a  mov     rax, [rax+10h]
0x18001ae6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae73  nop
0x18001ae74  cmp     [rbp+60h+var_B8], r15d
0x18001ae78  jl      short loc_18001AE95
0x18001ae7a  mov     rax, [rbp+60h+var_C0]
0x18001ae7e  cmp     [rax+18h], r15b
0x18001ae82  jnz     short loc_18001AE95
0x18001ae84  cmp     [rbp+60h+var_A0], r15b
0x18001ae88  jnz     short loc_18001AE95
0x18001ae8a  mov     eax, [rsi+10h]
0x18001ae8d  mov     [rdi+0B8h], eax
0x18001ae93  jmp     short loc_18001AE9A
0x18001ae95  bts     dword ptr [rdi+40h], 13h
0x18001ae9a  mov     rcx, [rbp+60h+var_30]
0x18001ae9e  xor     rcx, rsp; StackCookie
0x18001aea1  call    __security_check_cookie
0x18001aea6  lea     r11, [rsp+160h+var_20]
0x18001aeae  mov     rbx, [r11+38h]
0x18001aeb2  mov     rsi, [r11+40h]
0x18001aeb6  mov     rsp, r11
0x18001aeb9  pop     r15
0x18001aebb  pop     r14
0x18001aebd  pop     r12
0x18001aebf  pop     rdi
0x18001aec0  pop     rbp
0x18001aec1  retn
```
