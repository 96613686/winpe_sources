# tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x1800189d8`
- end: `0x180018c95`
- name: `?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `701`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180015e20`
- `0x18001620c`
- `0x180018c9c`

## callees

- `0x180001e40`
- `0x18000c558`
- `0x18000ddb4`
- `0x18000f1ec`
- `0x18000fa64`
- `0x180017c40`
- `0x1800189d8`
- `0x180018f64`
- `0x180019178`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<1,0,0>::serialize_data(
        __int64 *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rdi
  void *v7; // rax
  void *v8; // r15
  unsigned __int64 v9; // rsi
  tson::write_buffer *v10; // rdi
  __int64 v11; // rcx
  wil::details::in1diag3 *v12; // rcx
  tson::write_buffer *v13; // rax
  _DWORD *v14; // r9
  unsigned __int64 v15; // r8
  const char *v17; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+38h] [rbp-C8h]
  _BYTE *v19; // [rsp+40h] [rbp-C0h]
  const char *v20; // [rsp+48h] [rbp-B8h]
  char v21; // [rsp+50h] [rbp-B0h]
  __int64 *v22; // [rsp+58h] [rbp-A8h]
  const char *v23; // [rsp+60h] [rbp-A0h]
  char v24; // [rsp+68h] [rbp-98h]
  __int64 *v25; // [rsp+70h] [rbp-90h]
  const char *v26; // [rsp+80h] [rbp-80h] BYREF
  char v27; // [rsp+88h] [rbp-78h]
  char v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+108h] [rbp+8h]
  tson::write_buffer *v30; // [rsp+110h] [rbp+10h]

  if ( !a3 )
    return 0;
  v6 = (char *)a1 + 33;
  tson::output_archive::output_archive((tson::output_archive *)&v26, a2, *((_BYTE *)a1 + 33));
  if ( (a3 & 4) != 0 && *v6 )
  {
    v17 = "version";
    v18 = 7;
    v19 = v6;
    tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v26, &v17);
  }
  if ( (a3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_19:
      v17 = "flags";
      v18 = 5;
      v19 = a1 + 15;
      v23 = "errors";
      v24 = 6;
      v25 = a1 + 9;
      v20 = "log";
      v21 = 3;
      v22 = a1 + 12;
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v26);
      goto LABEL_20;
    }
    v7 = (void *)a1[1];
    if ( v7 )
    {
      v8 = (void *)a1[1];
    }
    else
    {
      v7 = (void *)a1[3];
      v8 = v7;
      if ( !v7 )
      {
        v9 = 0;
        goto LABEL_14;
      }
    }
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v7 + v9) );
LABEL_14:
    *(_DWORD *)((char *)&v22 + 1) = 0;
    *(_WORD *)((char *)&v22 + 5) = 0;
    HIBYTE(v22) = 0;
    v26 = "name";
    v27 = 4;
    if ( tson::output_archive::write_name((tson::output_archive *)&v26, v8 == 0) )
    {
      v10 = v30;
      if ( *((_QWORD *)v30 + 259) < *((_QWORD *)v30 + 260) || tson::write_buffer::reserve(v30, 1u) )
        *(_BYTE *)(*((_QWORD *)v10 + 259))++ = 23;
      tson::output_archive::write_string_bytes((tson::output_archive *)&v26, v9, v8, v9);
    }
    goto LABEL_19;
  }
LABEL_20:
  v11 = *a1;
  if ( tip2::details::g_test_interface_exception_guard )
  {
    if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v11, &v26, a3, 0, 0) )
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16396;
      a1[21] = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, const char **, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, &v26, a3);
  }
  if ( v29 < 0 || v28 )
    goto LABEL_30;
  v13 = v30;
  if ( *((_BYTE *)v30 + 8) )
  {
    *((_QWORD *)v30 + 258) = 0;
    *((_QWORD *)v13 + 259) = 0;
    *((_QWORD *)v13 + 260) = 0;
LABEL_30:
    *((_DWORD *)a1 + 16) |= 0x100000u;
    return 0;
  }
  v14 = (_DWORD *)*((_QWORD *)v30 + 258);
  v15 = (unsigned int)*((_QWORD *)v30 + 259) - (unsigned int)v14;
  if ( v15 > 0xFFFFFF )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v12);
  *v14 = v15 & 0x3F | (4 * (_WORD)v15) & 0x3F00 | ((_DWORD)v15 << 6) & 0x3F000000 | (16 * v15) & 0x3F0000 | 0x80408040;
  return *((_QWORD *)a2 + 258);
}

```

## disassembly

```asm
0x1800189d8  push    rbp
0x1800189da  push    rbx
0x1800189db  push    rsi
0x1800189dc  push    rdi
0x1800189dd  push    r13
0x1800189df  push    r14
0x1800189e1  push    r15
0x1800189e3  lea     rbp, [rsp-30h]
0x1800189e8  sub     rsp, 130h
0x1800189ef  mov     rax, cs:__security_cookie
0x1800189f6  xor     rax, rsp
0x1800189f9  mov     [rbp+60h+var_40], rax
0x1800189fd  mov     r14d, r8d
0x180018a00  mov     r13, rdx
0x180018a03  mov     rbx, rcx
0x180018a06  test    r8d, r8d
0x180018a09  jz      loc_180018C6F
0x180018a0f  lea     rdi, [rcx+21h]
0x180018a13  mov     r8b, [rdi]; unsigned __int8
0x180018a16  lea     rcx, [rbp+60h+var_E0]; this
0x180018a1a  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x180018a1f  test    r14b, 4
0x180018a23  jz      short loc_180018A4E
0x180018a25  cmp     byte ptr [rdi], 0
0x180018a28  jbe     short loc_180018A4E
0x180018a2a  lea     rax, aVersion; "version"
0x180018a31  mov     [rsp+160h+var_130], rax
0x180018a36  mov     [rsp+160h+var_128], 7
0x180018a3b  mov     [rsp+160h+var_120], rdi
0x180018a40  lea     rdx, [rsp+160h+var_130]
0x180018a45  lea     rcx, [rbp+60h+var_E0]
0x180018a49  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x180018a4e  test    r14b, 1
0x180018a52  jz      loc_180018B70
0x180018a58  test    dword ptr [rbx+14h], 40000h
0x180018a5f  jz      loc_180018B09
0x180018a65  mov     rax, [rbx+8]
0x180018a69  test    rax, rax
0x180018a6c  jz      short loc_180018A73
0x180018a6e  mov     r15, rax
0x180018a71  jmp     short loc_180018A7F
0x180018a73  mov     rax, [rbx+18h]
0x180018a77  mov     r15, rax
0x180018a7a  test    rax, rax
0x180018a7d  jz      short loc_180018A8E
0x180018a7f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180018a83  inc     rsi
0x180018a86  cmp     byte ptr [rax+rsi], 0
0x180018a8a  jnz     short loc_180018A83
0x180018a8c  jmp     short loc_180018A90
0x180018a8e  xor     esi, esi
0x180018a90  xor     eax, eax
0x180018a92  mov     [rsp+160h+var_107], eax
0x180018a96  mov     [rsp+160h+var_103], ax
0x180018a9b  mov     [rsp+160h+var_101], al
0x180018a9f  lea     rax, aName; "name"
0x180018aa6  mov     [rbp+60h+var_E0], rax
0x180018aaa  mov     [rbp+60h+var_D8], 4
0x180018aae  test    r15, r15
0x180018ab1  setz    dl; bool
0x180018ab4  lea     rcx, [rbp+60h+var_E0]; this
0x180018ab8  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180018abd  test    al, al
0x180018abf  jz      short loc_180018B09
0x180018ac1  mov     rdi, [rbp+60h+var_50]
0x180018ac5  mov     rax, [rdi+820h]
0x180018acc  cmp     [rdi+818h], rax
0x180018ad3  jb      short loc_180018AE6
0x180018ad5  mov     edx, 1; unsigned __int64
0x180018ada  mov     rcx, rdi; this
0x180018add  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180018ae2  test    al, al
0x180018ae4  jz      short loc_180018AF7
0x180018ae6  mov     rax, [rdi+818h]
0x180018aed  mov     byte ptr [rax], 17h
0x180018af0  inc     qword ptr [rdi+818h]
0x180018af7  mov     r9, rsi; unsigned __int64
0x180018afa  mov     r8, r15; void *
0x180018afd  mov     rdx, rsi; unsigned __int64
0x180018b00  lea     rcx, [rbp+60h+var_E0]; this
0x180018b04  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x180018b09  lea     rax, aFlags; "flags"
0x180018b10  mov     [rsp+160h+var_130], rax
0x180018b15  mov     [rsp+160h+var_128], 5
0x180018b1a  lea     rax, [rbx+78h]
0x180018b1e  mov     [rsp+160h+var_120], rax
0x180018b23  lea     rax, aErrors; "errors"
0x180018b2a  mov     [rsp+160h+var_100], rax
0x180018b2f  mov     [rsp+160h+var_F8], 6
0x180018b34  lea     rax, [rbx+48h]
0x180018b38  mov     [rsp+160h+var_F0], rax
0x180018b3d  lea     rax, aLog; "log"
0x180018b44  mov     [rsp+160h+var_118], rax
0x180018b49  mov     [rsp+160h+var_110], 3
0x180018b4e  lea     rax, [rbx+60h]
0x180018b52  mov     [rsp+58h], rax
0x180018b57  lea     r9, [rsp+160h+var_130]
0x180018b5c  lea     r8, [rsp+160h+var_100]
0x180018b61  lea     rdx, [rsp+160h+var_118]
0x180018b66  lea     rcx, [rbp+60h+var_E0]; this
0x180018b6a  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x180018b6f  nop
0x180018b70  mov     rcx, [rbx]
0x180018b73  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180018b7a  mov     r8d, r14d
0x180018b7d  lea     rdx, [rbp+60h+var_E0]
0x180018b81  test    rax, rax
0x180018b84  jz      short loc_180018BB8
0x180018b86  mov     [rsp+160h+var_140], 0
0x180018b8f  xor     r9d, r9d
0x180018b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b97  test    al, al
0x180018b99  jnz     short loc_180018BC5
0x180018b9b  mov     byte ptr [rbx+0A0h], 3
0x180018ba2  mov     word ptr [rbx+0A2h], 400Ch
0x180018bab  mov     qword ptr [rbx+0A8h], 0
0x180018bb6  jmp     short loc_180018BC5
0x180018bb8  mov     rax, [rcx]
0x180018bbb  mov     rax, [rax+8]
0x180018bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bc4  nop
0x180018bc5  cmp     [rbp+60h+var_58], 0
0x180018bc9  jl      loc_180018C6A
0x180018bcf  cmp     [rbp+60h+var_C8], 0
0x180018bd3  jnz     loc_180018C6A
0x180018bd9  mov     rax, [rbp+60h+var_50]
0x180018bdd  cmp     byte ptr [rax+8], 0
0x180018be1  jnz     short loc_180018C49
0x180018be3  mov     r9, [rax+810h]
0x180018bea  mov     r8, [rax+818h]
0x180018bf1  sub     r8, r9
0x180018bf4  mov     r8d, r8d
0x180018bf7  cmp     r8, 0FFFFFFh
0x180018bfe  ja      loc_180018C8F
0x180018c04  mov     edx, r8d
0x180018c07  shl     rdx, 4
0x180018c0b  and     edx, 3F0000h
0x180018c11  mov     ecx, r8d
0x180018c14  shl     rcx, 6
0x180018c18  and     ecx, 3F000000h
0x180018c1e  or      edx, ecx
0x180018c20  lea     rcx, ds:0[r8*4]
0x180018c28  and     ecx, 3F00h
0x180018c2e  or      edx, ecx
0x180018c30  and     r8d, 3Fh
0x180018c34  or      edx, r8d
0x180018c37  or      edx, 80408040h
0x180018c3d  mov     [r9], edx
0x180018c40  mov     rax, [r13+810h]
0x180018c47  jmp     short loc_180018C71
0x180018c49  mov     qword ptr [rax+810h], 0
0x180018c54  mov     qword ptr [rax+818h], 0
0x180018c5f  mov     qword ptr [rax+820h], 0
0x180018c6a  bts     dword ptr [rbx+40h], 14h
0x180018c6f  xor     eax, eax
0x180018c71  mov     rcx, [rbp+60h+var_40]
0x180018c75  xor     rcx, rsp; StackCookie
0x180018c78  call    __security_check_cookie
0x180018c7d  add     rsp, 130h
0x180018c84  pop     r15
0x180018c86  pop     r14
0x180018c88  pop     r13
0x180018c8a  pop     rdi
0x180018c8b  pop     rsi
0x180018c8c  pop     rbx
0x180018c8d  pop     rbp
0x180018c8e  retn
0x180018c8f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
