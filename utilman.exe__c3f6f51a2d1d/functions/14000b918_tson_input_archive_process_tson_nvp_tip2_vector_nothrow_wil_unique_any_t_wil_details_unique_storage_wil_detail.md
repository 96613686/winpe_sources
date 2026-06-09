# tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x14000b918`
- end: `0x14000b9b5`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `157`
- prototype: `__int64 __fastcall(tson *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x14000fce8`

## callees

- `0x14000b380`
- `0x14000b4a0`
- `0x14000b558`
- `0x14001052c`
- `0x14001235c`

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
  tson::input_archive::startNode(this);
  tson::load_nothrow<tip2::test_flag>(this);
  tson::input_archive::finishNode(this);
}

```

## disassembly

```asm
0x14000b918  push    rbx
0x14000b91a  push    rbp
0x14000b91b  push    rsi
0x14000b91c  push    rdi
0x14000b91d  sub     rsp, 28h
0x14000b921  mov     r10b, [rdx+8]
0x14000b925  mov     rsi, r9
0x14000b928  mov     rax, [rdx]
0x14000b92b  mov     rdi, r8
0x14000b92e  mov     [rcx+10h], rax
0x14000b932  mov     rbp, rcx
0x14000b935  mov     [rcx+18h], r10b
0x14000b939  mov     rbx, [rdx+10h]
0x14000b93d  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x14000b942  mov     rdx, rbx
0x14000b945  mov     rcx, rbp; this
0x14000b948  call    ??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x14000b94d  mov     rcx, rbp; this
0x14000b950  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x14000b955  mov     cl, [rdi+8]
0x14000b958  mov     rax, [rdi]
0x14000b95b  mov     [rbp+18h], cl
0x14000b95e  mov     rcx, rbp; this
0x14000b961  mov     [rbp+10h], rax
0x14000b965  mov     rbx, [rdi+10h]
0x14000b969  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x14000b96e  mov     rdx, rbx
0x14000b971  mov     rcx, rbp; this
0x14000b974  call    ??$load_nothrow@VStoredFailureInfo@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@Z; tson::load_nothrow<wil::StoredFailureInfo>(tson::input_archive &,tip2::vector_nothrow<wil::StoredFailureInfo> &)
0x14000b979  mov     rcx, rbp; this
0x14000b97c  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x14000b981  mov     cl, [rsi+8]
0x14000b984  mov     rax, [rsi]
0x14000b987  mov     [rbp+18h], cl
0x14000b98a  mov     rcx, rbp; this
0x14000b98d  mov     [rbp+10h], rax
0x14000b991  mov     rbx, [rsi+10h]
0x14000b995  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x14000b99a  mov     rdx, rbx
0x14000b99d  mov     rcx, rbp; this
0x14000b9a0  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x14000b9a5  mov     rcx, rbp; this
0x14000b9a8  add     rsp, 28h
0x14000b9ac  pop     rdi
0x14000b9ad  pop     rsi
0x14000b9ae  pop     rbp
0x14000b9af  pop     rbx
0x14000b9b0  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
