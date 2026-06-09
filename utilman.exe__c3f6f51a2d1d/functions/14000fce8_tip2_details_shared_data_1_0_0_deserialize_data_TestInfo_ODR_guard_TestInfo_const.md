# tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)

- ea: `0x14000fce8`
- end: `0x14000fe74`
- name: `?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z`
- size: `396`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x14000f828`
- `0x14000fad8`
- `0x14000fe7c`
- `0x140023104`

## callees

- `0x140002480`
- `0x14000ae80`
- `0x14000af04`
- `0x14000b918`
- `0x14000ca2c`
- `0x14000cb78`
- `0x14000fb98`
- `0x14000fc74`
- `0x14000fce8`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<1,0,0>::deserialize_data(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rsi
  bool v5; // zf
  __int64 v6; // rdx
  _BYTE *v7; // rcx
  __int64 result; // rax
  char v9; // [rsp+20h] [rbp-E0h] BYREF
  const char *v10; // [rsp+28h] [rbp-D8h] BYREF
  char v11; // [rsp+30h] [rbp-D0h]
  char *v12; // [rsp+38h] [rbp-C8h]
  const char *v13; // [rsp+40h] [rbp-C0h]
  char v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  const char *v16; // [rsp+58h] [rbp-A8h]
  char v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+98h] [rbp-68h]
  char v22; // [rsp+B0h] [rbp-50h]

  if ( (*(_DWORD *)(a2 + 20) & 0x1000) == 0 )
    goto LABEL_15;
  tson::read_buffer::read_buffer((tson::read_buffer *)v19, *(const char **)(a2 + 24));
  v4 = (_QWORD *)(a1 + 8);
  tson::input_archive::input_archive((tson::input_archive *)&v20, (struct tson::read_buffer *)v19, *(_BYTE *)(a1 + 33));
  if ( (*(_DWORD *)(a1 + 20) & 0x40000) != 0 )
  {
    v5 = *(_QWORD *)(a1 + 24) == 0;
    v10 = "name";
    v11 = 4;
    if ( v5 )
    {
      v12 = (char *)(a1 + 8);
      tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(
        &v20,
        &v10);
      if ( *v4 )
        *(_QWORD *)(a1 + 24) = *v4;
    }
    else
    {
      v9 = 0;
      v12 = &v9;
      tson::input_archive::operator()<tson::nvp<tson::ansistring_skip_tag &>>((tson::input_archive *)&v20);
    }
  }
  v11 = 5;
  v10 = "flags";
  v14 = 6;
  v12 = (char *)(a1 + 120);
  v17 = 3;
  v13 = "errors";
  v15 = a1 + 72;
  v16 = "log";
  v18 = a1 + 96;
  tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v20);
  v7 = *(_BYTE **)(v20 + 8);
  if ( (unsigned __int64)v7 >= *(_QWORD *)(v20 + 16) )
    goto LABEL_10;
  LOBYTE(v6) = 8;
  if ( *v7 == 8 )
    result = tson::input_archive::consume_expected_marker(&v20, v6, 2147944029LL);
  else
LABEL_10:
    result = tip2::details::shared_data<1,0,0>::deserialize(a1, &v20);
  if ( v21 < 0 || (result = v20, *(_BYTE *)(v20 + 24)) || v22 )
  {
LABEL_15:
    *(_DWORD *)(a1 + 64) |= 0x80000u;
  }
  else
  {
    result = *(unsigned int *)(a2 + 16);
    *(_DWORD *)(a1 + 184) = result;
  }
  return result;
}

```

## disassembly

```asm
0x14000fce8  mov     [rsp-8+arg_10], rbx
0x14000fced  push    rbp
0x14000fcee  push    rsi
0x14000fcef  push    rdi
0x14000fcf0  lea     rbp, [rsp-30h]
0x14000fcf5  sub     rsp, 130h
0x14000fcfc  mov     rax, cs:__security_cookie
0x14000fd03  xor     rax, rsp
0x14000fd06  mov     [rbp+40h+var_20], rax
0x14000fd0a  test    dword ptr [rdx+14h], 1000h
0x14000fd11  mov     rdi, rdx
0x14000fd14  mov     rbx, rcx
0x14000fd17  jz      loc_14000FE4F
0x14000fd1d  mov     rdx, [rdx+18h]; char *
0x14000fd21  lea     rcx, [rsp+140h+var_D0]; this
0x14000fd26  call    ??0read_buffer@tson@@QEAA@PEBD@Z; tson::read_buffer::read_buffer(char const *)
0x14000fd2b  lea     rsi, [rbx+8]
0x14000fd2f  mov     r8b, [rsi+19h]; unsigned __int8
0x14000fd33  lea     rdx, [rsp+140h+var_D0]; struct tson::read_buffer *
0x14000fd38  lea     rcx, [rbp+40h+var_B0]; this
0x14000fd3c  call    ??0input_archive@tson@@QEAA@AEAVread_buffer@1@E@Z; tson::input_archive::input_archive(tson::read_buffer &,uchar)
0x14000fd41  test    dword ptr [rbx+14h], 40000h
0x14000fd48  jz      short loc_14000FD97
0x14000fd4a  cmp     qword ptr [rbx+18h], 0
0x14000fd4f  lea     rax, aName; "name"
0x14000fd56  mov     [rsp+140h+var_118], rax
0x14000fd5b  lea     rdx, [rsp+140h+var_118]
0x14000fd60  mov     [rsp+140h+var_110], 4
0x14000fd65  lea     rcx, [rbp+40h+var_B0]; this
0x14000fd69  jnz     short loc_14000FD83
0x14000fd6b  mov     [rsp+140h+var_108], rsi
0x14000fd70  call    ??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z; tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)
0x14000fd75  mov     rax, [rsi]
0x14000fd78  test    rax, rax
0x14000fd7b  jz      short loc_14000FD97
0x14000fd7d  mov     [rbx+18h], rax
0x14000fd81  jmp     short loc_14000FD97
0x14000fd83  lea     rax, [rsp+140h+var_120]
0x14000fd88  mov     [rsp+140h+var_120], 0
0x14000fd8d  mov     [rsp+140h+var_108], rax
0x14000fd92  call    ??$?RV?$nvp@AEAUansistring_skip_tag@tson@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUansistring_skip_tag@tson@@@1@@Z; tson::input_archive::operator()<tson::nvp<tson::ansistring_skip_tag &>>(tson::nvp<tson::ansistring_skip_tag &> &&)
0x14000fd97  lea     rax, aFlags; "flags"
0x14000fd9e  mov     [rsp+140h+var_110], 5
0x14000fda3  mov     [rsp+140h+var_118], rax
0x14000fda8  lea     r9, [rsp+140h+var_118]
0x14000fdad  lea     rax, [rbx+78h]
0x14000fdb1  mov     [rsp+140h+var_F8], 6
0x14000fdb6  mov     [rsp+140h+var_108], rax
0x14000fdbb  lea     r8, [rsp+140h+var_100]
0x14000fdc0  lea     rax, aErrors; "errors"
0x14000fdc7  mov     [rsp+140h+var_E0], 3
0x14000fdcc  mov     [rsp+140h+var_100], rax
0x14000fdd1  lea     rdx, [rsp+140h+var_E8]
0x14000fdd6  lea     rax, [rbx+48h]
0x14000fdda  mov     [rsp+140h+var_F0], rax
0x14000fddf  lea     rcx, [rbp+40h+var_B0]; this
0x14000fde3  lea     rax, aLog; "log"
0x14000fdea  mov     [rsp+140h+var_E8], rax
0x14000fdef  lea     rax, [rbx+60h]
0x14000fdf3  mov     [rsp+140h+var_D8], rax
0x14000fdf8  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x14000fdfd  mov     rax, [rbp+40h+var_B0]
0x14000fe01  mov     rcx, [rax+8]
0x14000fe05  cmp     rcx, [rax+10h]
0x14000fe09  jnb     short loc_14000FE22
0x14000fe0b  mov     dl, 8
0x14000fe0d  cmp     [rcx], dl
0x14000fe0f  jnz     short loc_14000FE22
0x14000fe11  mov     r8d, 8007065Dh
0x14000fe17  lea     rcx, [rbp+40h+var_B0]
0x14000fe1b  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x14000fe20  jmp     short loc_14000FE2E
0x14000fe22  lea     rdx, [rbp+40h+var_B0]
0x14000fe26  mov     rcx, rbx
0x14000fe29  call    ?deserialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVinput_archive@tson@@@Z; tip2::details::shared_data<1,0,0>::deserialize(tson::input_archive &)
0x14000fe2e  cmp     [rbp+40h+var_A8], 0
0x14000fe32  jl      short loc_14000FE4F
0x14000fe34  mov     rax, [rbp+40h+var_B0]
0x14000fe38  cmp     byte ptr [rax+18h], 0
0x14000fe3c  jnz     short loc_14000FE4F
0x14000fe3e  cmp     [rbp+40h+var_90], 0
0x14000fe42  jnz     short loc_14000FE4F
0x14000fe44  mov     eax, [rdi+10h]
0x14000fe47  mov     [rbx+0B8h], eax
0x14000fe4d  jmp     short loc_14000FE54
0x14000fe4f  bts     dword ptr [rbx+40h], 13h
0x14000fe54  mov     rcx, [rbp+40h+var_20]
0x14000fe58  xor     rcx, rsp; StackCookie
0x14000fe5b  call    __security_check_cookie
0x14000fe60  mov     rbx, [rsp+140h+arg_10]
0x14000fe68  add     rsp, 130h
0x14000fe6f  pop     rdi
0x14000fe70  pop     rsi
0x14000fe71  pop     rbp
0x14000fe72  retn
```
