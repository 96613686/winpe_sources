# tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18001c9e0`
- end: `0x18001cbbb`
- name: `?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `475`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18001aec8`
- `0x18001b164`
- `0x18001cbfc`

## callees

- `0x180008320`
- `0x1800127d8`
- `0x180012b44`
- `0x180013c3c`
- `0x180014210`
- `0x180014944`
- `0x18001b558`
- `0x18001b65c`
- `0x18001bd88`
- `0x18001c9e0`
- `0x18001ce20`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<1,0,0>::serialize_data(
        __int64 *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rsi
  __int64 v7; // rdx
  __int64 string_tag; // rax
  __int64 v9; // rcx
  const char *v11; // [rsp+30h] [rbp-D0h] BYREF
  char v12; // [rsp+38h] [rbp-C8h]
  __int128 v13; // [rsp+40h] [rbp-C0h]
  __int64 v14; // [rsp+50h] [rbp-B0h]
  const char *v15; // [rsp+58h] [rbp-A8h] BYREF
  char v16; // [rsp+60h] [rbp-A0h]
  __int64 *v17; // [rsp+68h] [rbp-98h]
  const char *v18; // [rsp+70h] [rbp-90h] BYREF
  char v19; // [rsp+78h] [rbp-88h]

  if ( a3 )
  {
    v6 = (char *)a1 + 33;
    tson::output_archive::output_archive((tson::output_archive *)&v18, a2, *((_BYTE *)a1 + 33));
    if ( (a3 & 4) != 0 && *v6 )
    {
      v11 = "version";
      v12 = 7;
      *(_QWORD *)&v13 = v6;
      tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v18, &v11);
    }
    if ( (a3 & 1) != 0 )
    {
      if ( (*((_DWORD *)a1 + 5) & 0x40000) != 0 )
      {
        v7 = a1[1];
        if ( !v7 )
          v7 = a1[3];
        string_tag = tson::make_string_tag(&v15, v7);
        v11 = "name";
        v12 = 4;
        v13 = *(_OWORD *)string_tag;
        v14 = *(_QWORD *)(string_tag + 16);
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(&v18, &v11);
      }
      v11 = "flags";
      v12 = 5;
      *(_QWORD *)&v13 = a1 + 15;
      v15 = "errors";
      v16 = 6;
      v17 = a1 + 9;
      v18 = "log";
      v19 = 3;
      tson::output_archive::startNode((tson::output_archive *)&v18);
      tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>((tson::output_archive *)&v18);
      tson::output_archive::finishNode((tson::output_archive *)&v18);
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson::output_archive *)&v18);
    }
    v9 = *a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v9, &v18, a3, 0, 0) )
      {
        *((_BYTE *)a1 + 160) = 3;
        *((_WORD *)a1 + 81) = 16396;
        a1[21] = 0;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, const char **, _QWORD))(*(_QWORD *)v9 + 8LL))(v9, &v18, a3);
    }
    if ( (int)tson::output_archive::finish((tson::output_archive *)&v18) >= 0 )
      return *((_QWORD *)a2 + 258);
    *((_DWORD *)a1 + 16) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c9e0  push    rbp
0x18001c9e2  push    rbx
0x18001c9e3  push    rsi
0x18001c9e4  push    rdi
0x18001c9e5  push    r14
0x18001c9e7  lea     rbp, [rsp-20h]
0x18001c9ec  sub     rsp, 120h
0x18001c9f3  mov     rax, cs:__security_cookie
0x18001c9fa  xor     rax, rsp
0x18001c9fd  mov     [rbp+40h+var_30], rax
0x18001ca01  mov     edi, r8d
0x18001ca04  mov     r14, rdx
0x18001ca07  mov     rbx, rcx
0x18001ca0a  test    r8d, r8d
0x18001ca0d  jz      loc_18001CB9F
0x18001ca13  lea     rsi, [rcx+21h]
0x18001ca17  mov     r8b, [rsi]; unsigned __int8
0x18001ca1a  lea     rcx, [rsp+140h+var_D0]; this
0x18001ca1f  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x18001ca24  test    dil, 4
0x18001ca28  jz      short loc_18001CA54
0x18001ca2a  cmp     byte ptr [rsi], 0
0x18001ca2d  jbe     short loc_18001CA54
0x18001ca2f  lea     rax, aVersion; "version"
0x18001ca36  mov     [rsp+140h+var_110], rax
0x18001ca3b  mov     [rsp+140h+var_108], 7
0x18001ca40  mov     qword ptr [rsp+140h+var_100], rsi
0x18001ca45  lea     rdx, [rsp+140h+var_110]
0x18001ca4a  lea     rcx, [rsp+140h+var_D0]
0x18001ca4f  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x18001ca54  test    dil, 1
0x18001ca58  jz      loc_18001CB2D
0x18001ca5e  test    dword ptr [rbx+14h], 40000h
0x18001ca65  jz      short loc_18001CAB1
0x18001ca67  mov     rdx, [rbx+8]
0x18001ca6b  test    rdx, rdx
0x18001ca6e  jnz     short loc_18001CA74
0x18001ca70  mov     rdx, [rbx+18h]
0x18001ca74  lea     rcx, [rsp+140h+var_E8]
0x18001ca79  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x18001ca7e  lea     rcx, aName; "name"
0x18001ca85  mov     [rsp+140h+var_110], rcx
0x18001ca8a  mov     [rsp+140h+var_108], 4
0x18001ca8f  movups  xmm0, xmmword ptr [rax]
0x18001ca92  movups  [rsp+140h+var_100], xmm0
0x18001ca97  movsd   xmm1, qword ptr [rax+10h]
0x18001ca9c  movsd   [rsp+140h+var_F0], xmm1
0x18001caa2  lea     rdx, [rsp+140h+var_110]
0x18001caa7  lea     rcx, [rsp+140h+var_D0]
0x18001caac  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x18001cab1  lea     rax, aFlags; "flags"
0x18001cab8  mov     [rsp+140h+var_110], rax
0x18001cabd  mov     [rsp+140h+var_108], 5
0x18001cac2  lea     rax, [rbx+78h]
0x18001cac6  mov     qword ptr [rsp+140h+var_100], rax
0x18001cacb  lea     rax, aErrors; "errors"
0x18001cad2  mov     [rsp+140h+var_E8], rax
0x18001cad7  mov     [rsp+140h+var_E0], 6
0x18001cadc  lea     rax, [rbx+48h]
0x18001cae0  mov     [rsp+140h+var_D8], rax
0x18001cae5  lea     rax, aLog; "log"
0x18001caec  mov     [rsp+140h+var_D0], rax
0x18001caf1  mov     [rsp+140h+var_C8], 3
0x18001caf6  lea     rcx, [rsp+140h+var_D0]; this
0x18001cafb  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18001cb00  lea     rdx, [rbx+60h]
0x18001cb04  lea     rcx, [rsp+140h+var_D0]; this
0x18001cb09  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x18001cb0e  lea     rcx, [rsp+140h+var_D0]; this
0x18001cb13  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18001cb18  lea     r8, [rsp+140h+var_110]
0x18001cb1d  lea     rdx, [rsp+140h+var_E8]
0x18001cb22  lea     rcx, [rsp+140h+var_D0]; this
0x18001cb27  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18001cb2c  nop
0x18001cb2d  mov     rcx, [rbx]
0x18001cb30  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18001cb37  mov     r8d, edi
0x18001cb3a  lea     rdx, [rsp+140h+var_D0]
0x18001cb3f  test    rax, rax
0x18001cb42  jz      short loc_18001CB76
0x18001cb44  mov     [rsp+140h+var_120], 0
0x18001cb4d  xor     r9d, r9d
0x18001cb50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb55  test    al, al
0x18001cb57  jnz     short loc_18001CB83
0x18001cb59  mov     byte ptr [rbx+0A0h], 3
0x18001cb60  mov     word ptr [rbx+0A2h], 400Ch
0x18001cb69  mov     qword ptr [rbx+0A8h], 0
0x18001cb74  jmp     short loc_18001CB83
0x18001cb76  mov     rax, [rcx]
0x18001cb79  mov     rax, [rax+8]
0x18001cb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb82  nop
0x18001cb83  lea     rcx, [rsp+140h+var_D0]; this
0x18001cb88  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x18001cb8d  test    eax, eax
0x18001cb8f  js      short loc_18001CB9A
0x18001cb91  mov     rax, [r14+810h]
0x18001cb98  jmp     short loc_18001CBA1
0x18001cb9a  bts     dword ptr [rbx+40h], 14h
0x18001cb9f  xor     eax, eax
0x18001cba1  mov     rcx, [rbp+40h+var_30]
0x18001cba5  xor     rcx, rsp; StackCookie
0x18001cba8  call    __security_check_cookie
0x18001cbad  add     rsp, 120h
0x18001cbb4  pop     r14
0x18001cbb6  pop     rdi
0x18001cbb7  pop     rsi
0x18001cbb8  pop     rbx
0x18001cbb9  pop     rbp
0x18001cbba  retn
```
