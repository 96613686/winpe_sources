# tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x140011ff8`
- end: `0x14001218d`
- name: `?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `405`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x14000fe7c`
- `0x1400100c8`
- `0x1400121cc`

## callees

- `0x140002480`
- `0x14000ac88`
- `0x14000b080`
- `0x14000b9bc`
- `0x14000bf4c`
- `0x14000cac4`
- `0x140010478`
- `0x14001057c`
- `0x140010f3c`
- `0x140011f94`
- `0x140011ff8`
- `0x1400123e4`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<1,0,0>::serialize_data(
        __int64 a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rsi
  __int64 v7; // rdx
  __int64 string_tag; // rax
  __int64 v9; // xmm1_8
  const char *v11; // [rsp+20h] [rbp-E0h] BYREF
  char v12; // [rsp+28h] [rbp-D8h]
  __int128 v13; // [rsp+30h] [rbp-D0h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  const char *v15; // [rsp+48h] [rbp-B8h] BYREF
  char v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  const char *v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+68h] [rbp-98h]

  if ( a3 )
  {
    v6 = (_BYTE *)(a1 + 33);
    tson::output_archive::output_archive((tson::output_archive *)&v18, a2, *(_BYTE *)(a1 + 33));
    if ( (a3 & 4) != 0 && *v6 )
    {
      v12 = 7;
      v11 = "version";
      *(_QWORD *)&v13 = v6;
      tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v18, &v11);
    }
    if ( (a3 & 1) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 20) & 0x40000) != 0 )
      {
        v7 = *(_QWORD *)(a1 + 8);
        if ( !v7 )
          v7 = *(_QWORD *)(a1 + 24);
        string_tag = tson::make_string_tag(&v15, v7);
        v12 = 4;
        v11 = "name";
        v9 = *(_QWORD *)(string_tag + 16);
        v13 = *(_OWORD *)string_tag;
        v14 = v9;
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(&v18, &v11);
      }
      v12 = 5;
      v11 = "flags";
      v16 = 6;
      *(_QWORD *)&v13 = a1 + 120;
      v15 = "errors";
      v17 = a1 + 72;
      v18 = "log";
      v19 = 3;
      tson::output_archive::startNode((tson::output_archive *)&v18);
      tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>((tson::output_archive *)&v18);
      tson::output_archive::finishNode((tson::output_archive *)&v18);
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson::output_archive *)&v18);
    }
    tip2::details::shared_data<1,0,0>::serialize(a1, &v18, a3);
    if ( (int)tson::output_archive::finish((tson::output_archive *)&v18) >= 0 )
      return *((_QWORD *)a2 + 258);
    *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x140011ff8  push    rbp
0x140011ffa  push    rbx
0x140011ffb  push    rsi
0x140011ffc  push    rdi
0x140011ffd  push    r14
0x140011fff  lea     rbp, [rsp-10h]
0x140012004  sub     rsp, 110h
0x14001200b  mov     rax, cs:__security_cookie
0x140012012  xor     rax, rsp
0x140012015  mov     [rbp+30h+var_30], rax
0x140012019  mov     edi, r8d
0x14001201c  mov     r14, rdx
0x14001201f  mov     rbx, rcx
0x140012022  test    r8d, r8d
0x140012025  jz      loc_140012170
0x14001202b  lea     rsi, [rcx+21h]
0x14001202f  mov     r8b, [rsi]; unsigned __int8
0x140012032  lea     rcx, [rsp+130h+var_D0]; this
0x140012037  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x14001203c  test    dil, 4
0x140012040  jz      short loc_14001206C
0x140012042  cmp     byte ptr [rsi], 0
0x140012045  jbe     short loc_14001206C
0x140012047  lea     rax, aVersion; "version"
0x14001204e  mov     [rsp+130h+var_108], 7
0x140012053  lea     rdx, [rsp+130h+var_110]
0x140012058  mov     [rsp+130h+var_110], rax
0x14001205d  lea     rcx, [rsp+130h+var_D0]
0x140012062  mov     qword ptr [rsp+130h+var_100], rsi
0x140012067  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x14001206c  test    dil, 1
0x140012070  jz      loc_140012144
0x140012076  test    dword ptr [rbx+14h], 40000h
0x14001207d  jz      short loc_1400120C9
0x14001207f  mov     rdx, [rbx+8]
0x140012083  test    rdx, rdx
0x140012086  jnz     short loc_14001208C
0x140012088  mov     rdx, [rbx+18h]
0x14001208c  lea     rcx, [rsp+130h+var_E8]
0x140012091  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x140012096  lea     rcx, aName; "name"
0x14001209d  mov     [rsp+130h+var_108], 4
0x1400120a2  mov     [rsp+130h+var_110], rcx
0x1400120a7  lea     rdx, [rsp+130h+var_110]
0x1400120ac  lea     rcx, [rsp+130h+var_D0]
0x1400120b1  movups  xmm0, xmmword ptr [rax]
0x1400120b4  movsd   xmm1, qword ptr [rax+10h]
0x1400120b9  movups  [rsp+130h+var_100], xmm0
0x1400120be  movsd   [rsp+130h+var_F0], xmm1
0x1400120c4  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x1400120c9  lea     rax, aFlags; "flags"
0x1400120d0  mov     [rsp+130h+var_108], 5
0x1400120d5  mov     [rsp+130h+var_110], rax
0x1400120da  lea     rcx, [rsp+130h+var_D0]; this
0x1400120df  lea     rax, [rbx+78h]
0x1400120e3  mov     [rsp+130h+var_E0], 6
0x1400120e8  mov     qword ptr [rsp+130h+var_100], rax
0x1400120ed  lea     rax, aErrors; "errors"
0x1400120f4  mov     [rsp+130h+var_E8], rax
0x1400120f9  lea     rax, [rbx+48h]
0x1400120fd  mov     [rsp+130h+var_D8], rax
0x140012102  lea     rax, aLog; "log"
0x140012109  mov     [rsp+130h+var_D0], rax
0x14001210e  mov     [rsp+130h+var_C8], 3
0x140012113  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x140012118  lea     rdx, [rbx+60h]
0x14001211c  lea     rcx, [rsp+130h+var_D0]; this
0x140012121  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x140012126  lea     rcx, [rsp+130h+var_D0]; this
0x14001212b  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x140012130  lea     r8, [rsp+130h+var_110]
0x140012135  lea     rdx, [rsp+130h+var_E8]
0x14001213a  lea     rcx, [rsp+130h+var_D0]; this
0x14001213f  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x140012144  mov     r8d, edi
0x140012147  lea     rdx, [rsp+130h+var_D0]
0x14001214c  mov     rcx, rbx
0x14001214f  call    ?serialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize(tson::output_archive &,tip2::details::serialize_options)
0x140012154  lea     rcx, [rsp+130h+var_D0]; this
0x140012159  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x14001215e  test    eax, eax
0x140012160  js      short loc_14001216B
0x140012162  mov     rax, [r14+810h]
0x140012169  jmp     short loc_140012172
0x14001216b  bts     dword ptr [rbx+40h], 14h
0x140012170  xor     eax, eax
0x140012172  mov     rcx, [rbp+30h+var_30]
0x140012176  xor     rcx, rsp; StackCookie
0x140012179  call    __security_check_cookie
0x14001217e  add     rsp, 110h
0x140012185  pop     r14
0x140012187  pop     rdi
0x140012188  pop     rsi
0x140012189  pop     rbx
0x14001218a  pop     rbp
0x14001218b  retn
```
