# tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x180013b98`
- end: `0x180013c35`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `157`
- prototype: `__int64 __fastcall(tson *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001aba8`

## callees

- `0x18001360c`
- `0x180013724`
- `0x1800137dc`
- `0x18001b60c`
- `0x18001cd98`

## pseudocode

```c
void __fastcall tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  char v4; // r10
  __int64 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rbx

  v4 = *(_BYTE *)(a2 + 8);
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  *((_BYTE *)this + 24) = v4;
  v8 = *(__int64 **)(a2 + 16);
  tson::input_archive::startNode(this);
  tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
    this,
    v8);
  tson::input_archive::finishNode(this);
  v9 = *a3;
  *((_BYTE *)this + 24) = *((_BYTE *)a3 + 8);
  *((_QWORD *)this + 2) = v9;
  tson::input_archive::startNode(this);
  tson::load_nothrow<wil::StoredFailureInfo>(this);
  tson::input_archive::finishNode(this);
  v10 = *a4;
  *((_BYTE *)this + 24) = *((_BYTE *)a4 + 8);
  *((_QWORD *)this + 2) = v10;
  v11 = (_QWORD *)a4[2];
  tson::input_archive::startNode(this);
  tson::load_nothrow<tip2::test_flag>(this, v11);
  tson::input_archive::finishNode(this);
}

```

## disassembly

```asm
0x180013b98  push    rbx
0x180013b9a  push    rbp
0x180013b9b  push    rsi
0x180013b9c  push    rdi
0x180013b9d  sub     rsp, 28h
0x180013ba1  mov     r10b, [rdx+8]
0x180013ba5  mov     rsi, r9
0x180013ba8  mov     rax, [rdx]
0x180013bab  mov     rdi, r8
0x180013bae  mov     [rcx+10h], rax
0x180013bb2  mov     rbp, rcx
0x180013bb5  mov     [rcx+18h], r10b
0x180013bb9  mov     rbx, [rdx+10h]
0x180013bbd  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180013bc2  mov     rdx, rbx
0x180013bc5  mov     rcx, rbp; this
0x180013bc8  call    ??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x180013bcd  mov     rcx, rbp; this
0x180013bd0  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180013bd5  mov     cl, [rdi+8]
0x180013bd8  mov     rax, [rdi]
0x180013bdb  mov     [rbp+18h], cl
0x180013bde  mov     rcx, rbp; this
0x180013be1  mov     [rbp+10h], rax
0x180013be5  mov     rbx, [rdi+10h]
0x180013be9  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180013bee  mov     rdx, rbx
0x180013bf1  mov     rcx, rbp; this
0x180013bf4  call    ??$load_nothrow@VStoredFailureInfo@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@Z; tson::load_nothrow<wil::StoredFailureInfo>(tson::input_archive &,tip2::vector_nothrow<wil::StoredFailureInfo> &)
0x180013bf9  mov     rcx, rbp; this
0x180013bfc  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180013c01  mov     cl, [rsi+8]
0x180013c04  mov     rax, [rsi]
0x180013c07  mov     [rbp+18h], cl
0x180013c0a  mov     rcx, rbp; this
0x180013c0d  mov     [rbp+10h], rax
0x180013c11  mov     rbx, [rsi+10h]
0x180013c15  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180013c1a  mov     rdx, rbx
0x180013c1d  mov     rcx, rbp; this
0x180013c20  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180013c25  mov     rcx, rbp; this
0x180013c28  add     rsp, 28h
0x180013c2c  pop     rdi
0x180013c2d  pop     rsi
0x180013c2e  pop     rbp
0x180013c2f  pop     rbx
0x180013c30  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
