# tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x140050f14`
- end: `0x140050fa1`
- name: `??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(tson::output_archive *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x14005f544`

## callees

- `0x14004c3bc`
- `0x140050f14`
- `0x14005e5d4`
- `0x14005fed8`
- `0x14005ff88`

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
  rsize_t v9; // rbp
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
0x140050f14  mov     r11, rsp
0x140050f17  mov     [r11+8], rbx
0x140050f1b  mov     [r11+18h], rbp
0x140050f1f  push    rsi
0x140050f20  push    rdi
0x140050f21  push    r14
0x140050f23  sub     rsp, 40h
0x140050f27  mov     rax, [rdx+10h]
0x140050f2b  mov     r9, rdx
0x140050f2e  lea     rdx, [r11+10h]
0x140050f32  mov     [r11+10h], rax
0x140050f36  mov     rdi, rcx
0x140050f39  call    ??$?RUsize_tag@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAUsize_tag@1@@Z; tson::output_archive::operator()<tson::size_tag>(tson::size_tag &&)
0x140050f3e  mov     rax, [r9+10h]
0x140050f42  mov     rbx, [r9]
0x140050f45  lea     rsi, [rbx+rax*8]
0x140050f49  jmp     short loc_140050F89
0x140050f4b  mov     rdx, [rbx]
0x140050f4e  lea     rcx, [rsp+58h+var_38]
0x140050f53  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x140050f58  mov     r8b, 17h
0x140050f5b  mov     rcx, rdi
0x140050f5e  mov     r14, [rax]
0x140050f61  mov     rbp, [rax+8]
0x140050f65  test    r14, r14
0x140050f68  setz    dl
0x140050f6b  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x140050f70  test    al, al
0x140050f72  jz      short loc_140050F85
0x140050f74  mov     r9, rbp; unsigned __int64
0x140050f77  mov     r8, r14; void *
0x140050f7a  mov     rdx, rbp; unsigned __int64
0x140050f7d  mov     rcx, rdi; this
0x140050f80  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x140050f85  add     rbx, 8
0x140050f89  cmp     rbx, rsi
0x140050f8c  jnz     short loc_140050F4B
0x140050f8e  mov     rbx, [rsp+58h+arg_0]
0x140050f93  mov     rbp, [rsp+58h+arg_10]
0x140050f98  add     rsp, 40h
0x140050f9c  pop     r14
0x140050f9e  pop     rdi
0x140050f9f  pop     rsi
0x140050fa0  retn
```
