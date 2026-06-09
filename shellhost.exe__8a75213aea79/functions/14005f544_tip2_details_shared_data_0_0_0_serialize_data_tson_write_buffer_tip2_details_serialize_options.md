# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x14005f544`
- end: `0x14005f71f`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `475`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x14005d9cc`
- `0x14005dd48`
- `0x14005f760`

## callees

- `0x14000f7e0`
- `0x14004c498`
- `0x14004c558`
- `0x140050d5c`
- `0x140050f14`
- `0x140052ac0`
- `0x14005e13c`
- `0x14005e1f0`
- `0x14005e5d4`
- `0x14005f544`
- `0x14005f90c`
- `0x140067010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
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
      if ( !(unsigned __int8)((__int64 (__fastcall *)(__int64, const char **, _QWORD, _QWORD, _QWORD))tip2::details::g_test_interface_exception_guard)(
                               v9,
                               &v18,
                               a3,
                               0,
                               0) )
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
0x14005f544  push    rbp
0x14005f546  push    rbx
0x14005f547  push    rsi
0x14005f548  push    rdi
0x14005f549  push    r14
0x14005f54b  lea     rbp, [rsp-20h]
0x14005f550  sub     rsp, 120h
0x14005f557  mov     rax, cs:__security_cookie
0x14005f55e  xor     rax, rsp
0x14005f561  mov     [rbp+40h+var_30], rax
0x14005f565  mov     edi, r8d
0x14005f568  mov     r14, rdx
0x14005f56b  mov     rbx, rcx
0x14005f56e  test    r8d, r8d
0x14005f571  jz      loc_14005F703
0x14005f577  lea     rsi, [rcx+21h]
0x14005f57b  mov     r8b, [rsi]; unsigned __int8
0x14005f57e  lea     rcx, [rsp+140h+var_D0]; this
0x14005f583  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x14005f588  test    dil, 4
0x14005f58c  jz      short loc_14005F5B8
0x14005f58e  cmp     byte ptr [rsi], 0
0x14005f591  jbe     short loc_14005F5B8
0x14005f593  lea     rax, aVersion; "version"
0x14005f59a  mov     [rsp+140h+var_110], rax
0x14005f59f  mov     [rsp+140h+var_108], 7
0x14005f5a4  mov     qword ptr [rsp+140h+var_100], rsi
0x14005f5a9  lea     rdx, [rsp+140h+var_110]
0x14005f5ae  lea     rcx, [rsp+140h+var_D0]
0x14005f5b3  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x14005f5b8  test    dil, 1
0x14005f5bc  jz      loc_14005F691
0x14005f5c2  test    dword ptr [rbx+14h], 40000h
0x14005f5c9  jz      short loc_14005F615
0x14005f5cb  mov     rdx, [rbx+8]
0x14005f5cf  test    rdx, rdx
0x14005f5d2  jnz     short loc_14005F5D8
0x14005f5d4  mov     rdx, [rbx+18h]
0x14005f5d8  lea     rcx, [rsp+140h+var_E8]
0x14005f5dd  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x14005f5e2  lea     rcx, aName; "name"
0x14005f5e9  mov     [rsp+140h+var_110], rcx
0x14005f5ee  mov     [rsp+140h+var_108], 4
0x14005f5f3  movups  xmm0, xmmword ptr [rax]
0x14005f5f6  movups  [rsp+140h+var_100], xmm0
0x14005f5fb  movsd   xmm1, qword ptr [rax+10h]
0x14005f600  movsd   [rsp+140h+var_F0], xmm1
0x14005f606  lea     rdx, [rsp+140h+var_110]
0x14005f60b  lea     rcx, [rsp+140h+var_D0]
0x14005f610  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x14005f615  lea     rax, aFlags; "flags"
0x14005f61c  mov     [rsp+140h+var_110], rax
0x14005f621  mov     [rsp+140h+var_108], 5
0x14005f626  lea     rax, [rbx+78h]
0x14005f62a  mov     qword ptr [rsp+140h+var_100], rax
0x14005f62f  lea     rax, aErrors; "errors"
0x14005f636  mov     [rsp+140h+var_E8], rax
0x14005f63b  mov     [rsp+140h+var_E0], 6
0x14005f640  lea     rax, [rbx+48h]
0x14005f644  mov     [rsp+140h+var_D8], rax
0x14005f649  lea     rax, aLog; "log"
0x14005f650  mov     [rsp+140h+var_D0], rax
0x14005f655  mov     [rsp+140h+var_C8], 3
0x14005f65a  lea     rcx, [rsp+140h+var_D0]; this
0x14005f65f  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x14005f664  lea     rdx, [rbx+60h]
0x14005f668  lea     rcx, [rsp+140h+var_D0]; this
0x14005f66d  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x14005f672  lea     rcx, [rsp+140h+var_D0]; this
0x14005f677  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x14005f67c  lea     r8, [rsp+140h+var_110]
0x14005f681  lea     rdx, [rsp+140h+var_E8]
0x14005f686  lea     rcx, [rsp+140h+var_D0]; this
0x14005f68b  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x14005f690  nop
0x14005f691  mov     rcx, [rbx]
0x14005f694  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x14005f69b  mov     r8d, edi
0x14005f69e  lea     rdx, [rsp+140h+var_D0]
0x14005f6a3  test    rax, rax
0x14005f6a6  jz      short loc_14005F6DA
0x14005f6a8  mov     [rsp+140h+var_120], 0
0x14005f6b1  xor     r9d, r9d
0x14005f6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005f6b9  test    al, al
0x14005f6bb  jnz     short loc_14005F6E7
0x14005f6bd  mov     byte ptr [rbx+0A0h], 3
0x14005f6c4  mov     word ptr [rbx+0A2h], 400Ch
0x14005f6cd  mov     qword ptr [rbx+0A8h], 0
0x14005f6d8  jmp     short loc_14005F6E7
0x14005f6da  mov     rax, [rcx]
0x14005f6dd  mov     rax, [rax+8]
0x14005f6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005f6e6  nop
0x14005f6e7  lea     rcx, [rsp+140h+var_D0]; this
0x14005f6ec  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x14005f6f1  test    eax, eax
0x14005f6f3  js      short loc_14005F6FE
0x14005f6f5  mov     rax, [r14+810h]
0x14005f6fc  jmp     short loc_14005F705
0x14005f6fe  bts     dword ptr [rbx+40h], 14h
0x14005f703  xor     eax, eax
0x14005f705  mov     rcx, [rbp+40h+var_30]
0x14005f709  xor     rcx, rsp; StackCookie
0x14005f70c  call    __security_check_cookie
0x14005f711  add     rsp, 120h
0x14005f718  pop     r14
0x14005f71a  pop     rdi
0x14005f71b  pop     rsi
0x14005f71c  pop     rbx
0x14005f71d  pop     rbp
0x14005f71e  retn
```
