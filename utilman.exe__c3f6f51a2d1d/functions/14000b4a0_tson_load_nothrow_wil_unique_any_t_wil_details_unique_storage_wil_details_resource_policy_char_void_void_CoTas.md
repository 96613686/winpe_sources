# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x14000b4a0`
- end: `0x14000b550`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x14000b918`

## callees

- `0x14000aa08`
- `0x14000b4a0`
- `0x14000bb00`
- `0x14000cfc0`
- `0x14000f9c4`
- `0x14001156c`

## pseudocode

```c
void __fastcall tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 *a2)
{
  char *v4; // rbx
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdx
  char *v8; // rax
  __int64 v9; // rcx
  char *v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  tson::input_archive::operator()<tson::size_tag &>(this, &v10);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(a2);
  v4 = v10;
  while ( v4 )
  {
    v10 = 0;
    --v4;
    tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
      this,
      (__int64)&v10);
    v5 = a2[1];
    if ( a2[2] < v5 )
      goto LABEL_6;
    v6 = 2 * v5;
    if ( !v5 )
      v6 = 10;
    if ( (unsigned __int8)tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(
                            a2,
                            v6) )
    {
LABEL_6:
      v7 = a2[2];
      v8 = v10;
      v9 = *a2;
      v10 = 0;
      *(_QWORD *)(v9 + 8 * v7) = v8;
      ++a2[2];
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v10);
  }
}

```

## disassembly

```asm
0x14000b4a0  mov     rax, rsp
0x14000b4a3  mov     [rax+8], rbx
0x14000b4a7  mov     [rax+10h], rsi
0x14000b4ab  push    rdi
0x14000b4ac  sub     rsp, 20h
0x14000b4b0  mov     rdi, rdx
0x14000b4b3  mov     qword ptr [rax+18h], 0
0x14000b4bb  lea     rdx, [rax+18h]
0x14000b4bf  mov     rsi, rcx
0x14000b4c2  call    ??$?RAEAUsize_tag@tson@@@input_archive@tson@@QEAAAEAV01@AEAUsize_tag@1@@Z; tson::input_archive::operator()<tson::size_tag &>(tson::size_tag &)
0x14000b4c7  mov     rcx, rdi
0x14000b4ca  call    ?clear@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAAXXZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(void)
0x14000b4cf  mov     rbx, [rsp+28h+arg_10]
0x14000b4d4  jmp     short loc_14000B53A
0x14000b4d6  lea     rdx, [rsp+28h+arg_10]
0x14000b4db  mov     [rsp+28h+arg_10], 0
0x14000b4e4  mov     rcx, rsi; this
0x14000b4e7  dec     rbx
0x14000b4ea  call    ??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x14000b4ef  mov     rax, [rdi+8]
0x14000b4f3  cmp     [rdi+10h], rax
0x14000b4f7  jb      short loc_14000B513
0x14000b4f9  lea     rdx, [rax+rax]
0x14000b4fd  test    rax, rax
0x14000b500  jnz     short loc_14000B507
0x14000b502  mov     edx, 0Ah
0x14000b507  mov     rcx, rdi
0x14000b50a  call    ?reserve@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N_K@Z; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x14000b50f  test    al, al
0x14000b511  jz      short loc_14000B530
0x14000b513  mov     rdx, [rdi+10h]
0x14000b517  mov     rax, [rsp+28h+arg_10]
0x14000b51c  mov     rcx, [rdi]
0x14000b51f  mov     [rsp+28h+arg_10], 0
0x14000b528  mov     [rcx+rdx*8], rax
0x14000b52c  inc     qword ptr [rdi+10h]
0x14000b530  lea     rcx, [rsp+28h+arg_10]
0x14000b535  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000b53a  test    rbx, rbx
0x14000b53d  jnz     short loc_14000B4D6
0x14000b53f  mov     rbx, [rsp+28h+arg_0]
0x14000b544  mov     rsi, [rsp+28h+arg_8]
0x14000b549  add     rsp, 20h
0x14000b54d  pop     rdi
0x14000b54e  retn
```
