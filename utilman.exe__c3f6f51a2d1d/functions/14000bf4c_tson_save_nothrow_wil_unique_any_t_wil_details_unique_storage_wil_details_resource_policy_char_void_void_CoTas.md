# tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x14000bf4c`
- end: `0x14000bfda`
- name: `??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(tson::output_archive *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x140011ff8`

## callees

- `0x14000aadc`
- `0x14000bf4c`
- `0x140010f3c`
- `0x140012908`
- `0x1400129b8`

## pseudocode

```c
void __fastcall tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::output_archive *this,
        __int64 a2)
{
  _QWORD *v3; // r10
  _QWORD *v4; // rbx
  __int64 v5; // rsi
  __int64 string_tag; // rax
  void *v7; // r14
  unsigned __int64 v8; // rbp
  _BYTE v9[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = *(_QWORD *)(a2 + 16);
  tson::output_archive::operator()<tson::size_tag>(this, &v10);
  v4 = (_QWORD *)*v3;
  v5 = *v3 + 8LL * v3[2];
  while ( v4 != (_QWORD *)v5 )
  {
    string_tag = tson::make_string_tag(v9, *v4);
    v7 = *(void **)string_tag;
    v8 = *(_QWORD *)(string_tag + 8);
    if ( tson::output_archive::write_type(this, *(_QWORD *)string_tag == 0, 23) )
      tson::output_archive::write_string_bytes(this, v8, v7, v8);
    ++v4;
  }
}

```

## disassembly

```asm
0x14000bf4c  mov     r11, rsp
0x14000bf4f  mov     [r11+8], rbx
0x14000bf53  mov     [r11+18h], rbp
0x14000bf57  push    rsi
0x14000bf58  push    rdi
0x14000bf59  push    r14
0x14000bf5b  sub     rsp, 40h
0x14000bf5f  mov     rax, [rdx+10h]
0x14000bf63  mov     r10, rdx
0x14000bf66  lea     rdx, [r11+10h]
0x14000bf6a  mov     [r11+10h], rax
0x14000bf6e  mov     rdi, rcx
0x14000bf71  call    ??$?RUsize_tag@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAUsize_tag@1@@Z; tson::output_archive::operator()<tson::size_tag>(tson::size_tag &&)
0x14000bf76  mov     rax, [r10+10h]
0x14000bf7a  mov     rbx, [r10]
0x14000bf7d  lea     rsi, [rbx+rax*8]
0x14000bf81  jmp     short loc_14000BFC1
0x14000bf83  mov     rdx, [rbx]
0x14000bf86  lea     rcx, [rsp+58h+var_38]
0x14000bf8b  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x14000bf90  mov     r8b, 17h
0x14000bf93  mov     rcx, rdi
0x14000bf96  mov     r14, [rax]
0x14000bf99  mov     rbp, [rax+8]
0x14000bf9d  test    r14, r14
0x14000bfa0  setz    dl
0x14000bfa3  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x14000bfa8  test    al, al
0x14000bfaa  jz      short loc_14000BFBD
0x14000bfac  mov     r9, rbp; unsigned __int64
0x14000bfaf  mov     r8, r14; void *
0x14000bfb2  mov     rdx, rbp; unsigned __int64
0x14000bfb5  mov     rcx, rdi; this
0x14000bfb8  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x14000bfbd  add     rbx, 8
0x14000bfc1  cmp     rbx, rsi
0x14000bfc4  jnz     short loc_14000BF83
0x14000bfc6  mov     rbx, [rsp+58h+arg_0]
0x14000bfcb  mov     rbp, [rsp+58h+arg_10]
0x14000bfd0  add     rsp, 40h
0x14000bfd4  pop     r14
0x14000bfd6  pop     rdi
0x14000bfd7  pop     rsi
0x14000bfd8  retn
```
