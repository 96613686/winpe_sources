# wil::iterable_range<Windows::ApplicationModel::Package *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::ApplicationModel::Package *> *)

- ea: `0x180014884`
- end: `0x18001493e`
- name: `??0iterable_iterator@?$iterable_range@PEAVPackage@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAVPackage@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006c3c`

## callees

- `0x180006db4`
- `0x180014884`
- `0x18001a610`
- `0x180029010`

## string_xrefs

- `0x1800148d3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001490a`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::iterable_range<Windows::ApplicationModel::Package *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
        _QWORD *a1,
        __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, _QWORD *); // rbx
  int v5; // eax
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v10; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  a1[2] = 0;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 48LL);
  _InternalRelease___ComPtr_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__WRL_Microsoft__IEAAKXZ(a1);
  v5 = v4(a2, a1);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v5,
      v8);
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*a1 + 56LL))(*a1, &v10);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v6,
      v8);
  *((_DWORD *)a1 + 2) = (v10 != 0) - 1;
  return a1;
}

```

## disassembly

```asm
0x180014884  mov     [rsp+arg_10], rbx
0x180014889  mov     [rsp+arg_18], rsi
0x18001488e  mov     [rsp+arg_0], rcx
0x180014893  push    rdi; int
0x180014894  sub     rsp, 20h
0x180014898  mov     rdi, rdx
0x18001489b  mov     rsi, rcx
0x18001489e  mov     qword ptr [rcx], 0
0x1800148a5  mov     qword ptr [rcx+10h], 0
0x1800148ad  mov     rax, [rdx]
0x1800148b0  mov     rbx, [rax+30h]
0x1800148b4  call    ?InternalRelease@?$ComPtr@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::InternalRelease(void)
0x1800148b9  mov     rdx, rsi
0x1800148bc  mov     rcx, rdi
0x1800148bf  mov     rax, rbx
0x1800148c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c7  mov     rcx, [rsp+28h]; this
0x1800148cc  test    eax, eax
0x1800148ce  jns     short loc_1800148E5
0x1800148d0  mov     r9d, eax; char *
0x1800148d3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800148da  mov     edx, 1CBEh; void *
0x1800148df  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800148e5  mov     [rsp+28h+arg_8], 0
0x1800148ea  mov     rcx, [rsi]
0x1800148ed  mov     rax, [rcx]
0x1800148f0  lea     rdx, [rsp+28h+arg_8]
0x1800148f5  mov     rax, [rax+38h]
0x1800148f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148fe  mov     rcx, [rsp+28h]; this
0x180014903  test    eax, eax
0x180014905  jns     short loc_18001491C
0x180014907  mov     r9d, eax; char *
0x18001490a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014911  mov     edx, 1CBEh; void *
0x180014916  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001491c  mov     al, [rsp+28h+arg_8]
0x180014920  neg     al
0x180014922  sbb     ecx, ecx
0x180014924  neg     ecx
0x180014926  dec     ecx
0x180014928  mov     [rsi+8], ecx
0x18001492b  mov     rax, rsi
0x18001492e  mov     rbx, [rsp+28h+arg_10]
0x180014933  mov     rsi, [rsp+28h+arg_18]
0x180014938  add     rsp, 20h
0x18001493c  pop     rdi
0x18001493d  retn
```
