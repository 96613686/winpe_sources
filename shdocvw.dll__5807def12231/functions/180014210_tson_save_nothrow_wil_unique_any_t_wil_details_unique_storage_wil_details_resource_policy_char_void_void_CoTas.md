# tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x180014210`
- end: `0x18001429d`
- name: `??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(tson::output_archive *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001c9e0`

## callees

- `0x180012628`
- `0x180014210`
- `0x18001bd88`
- `0x18001d034`
- `0x18001d0e4`

## pseudocode

```c
void __fastcall tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::output_archive *this,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r9
  _QWORD *v5; // rbx
  __int64 v6; // rsi
  __int64 string_tag; // rax
  void *v8; // r14
  unsigned __int64 v9; // rbp
  _BYTE v10[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = *(_QWORD *)(a2 + 16);
  tson::output_archive::operator()<tson::size_tag>(this, &v11, a3, a2);
  v5 = (_QWORD *)*v4;
  v6 = *v4 + 8LL * v4[2];
  while ( v5 != (_QWORD *)v6 )
  {
    string_tag = tson::make_string_tag(v10, *v5);
    v8 = *(void **)string_tag;
    v9 = *(_QWORD *)(string_tag + 8);
    if ( tson::output_archive::write_type(this, *(_QWORD *)string_tag == 0, 23) )
      tson::output_archive::write_string_bytes(this, v9, v8, v9);
    ++v5;
  }
}

```

## disassembly

```asm
0x180014210  mov     r11, rsp
0x180014213  mov     [r11+8], rbx
0x180014217  mov     [r11+18h], rbp
0x18001421b  push    rsi
0x18001421c  push    rdi
0x18001421d  push    r14
0x18001421f  sub     rsp, 40h
0x180014223  mov     rax, [rdx+10h]
0x180014227  mov     r9, rdx
0x18001422a  lea     rdx, [r11+10h]
0x18001422e  mov     [r11+10h], rax
0x180014232  mov     rdi, rcx
0x180014235  call    ??$?RUsize_tag@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAUsize_tag@1@@Z; tson::output_archive::operator()<tson::size_tag>(tson::size_tag &&)
0x18001423a  mov     rax, [r9+10h]
0x18001423e  mov     rbx, [r9]
0x180014241  lea     rsi, [rbx+rax*8]
0x180014245  jmp     short loc_180014285
0x180014247  mov     rdx, [rbx]
0x18001424a  lea     rcx, [rsp+58h+var_38]
0x18001424f  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x180014254  mov     r8b, 17h
0x180014257  mov     rcx, rdi
0x18001425a  mov     r14, [rax]
0x18001425d  mov     rbp, [rax+8]
0x180014261  test    r14, r14
0x180014264  setz    dl
0x180014267  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x18001426c  test    al, al
0x18001426e  jz      short loc_180014281
0x180014270  mov     r9, rbp; unsigned __int64
0x180014273  mov     r8, r14; void *
0x180014276  mov     rdx, rbp; unsigned __int64
0x180014279  mov     rcx, rdi; this
0x18001427c  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x180014281  add     rbx, 8
0x180014285  cmp     rbx, rsi
0x180014288  jnz     short loc_180014247
0x18001428a  mov     rbx, [rsp+58h+arg_0]
0x18001428f  mov     rbp, [rsp+58h+arg_10]
0x180014294  add     rsp, 40h
0x180014298  pop     r14
0x18001429a  pop     rdi
0x18001429b  pop     rsi
0x18001429c  retn
```
