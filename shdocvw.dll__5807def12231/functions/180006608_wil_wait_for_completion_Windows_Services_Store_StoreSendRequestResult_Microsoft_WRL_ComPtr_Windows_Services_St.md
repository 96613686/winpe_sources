# wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS)

- ea: `0x180006608`
- end: `0x18000667f`
- name: `??$wait_for_completion@PEAVStoreSendRequestResult@Store@Services@Windows@@V?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIStoreSendRequestResult@Store@Services@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b0c`
- `0x1800060a8`

## callees

- `0x180006608`
- `0x18001a610`
- `0x180020c48`
- `0x180029010`

## string_xrefs

- `0x18000665e`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::wait_for_completion<Windows::Services::Store::StoreSendRequestResult *,Microsoft::WRL::ComPtr<Windows::Services::Store::IStoreSendRequestResult>>(
        _QWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        int a3)
{
  int v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v5 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(
         a2,
         (DWORD)a2,
         a3);
  if ( v5 >= 0 )
    v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD *))(*a2)[8])(a2, a1);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v5,
      1);
  return a1;
}

```

## disassembly

```asm
0x180006608  mov     rax, rsp
0x18000660b  mov     [rax+10h], rbx
0x18000660f  mov     [rax+8], rcx
0x180006613  push    rdi
0x180006614  sub     rsp, 30h
0x180006618  mov     rdi, rdx
0x18000661b  mov     rbx, rcx
0x18000661e  mov     dword ptr [rax-18h], 0
0x180006625  mov     qword ptr [rcx], 0
0x18000662c  mov     dword ptr [rax-18h], 1
0x180006633  mov     rcx, rdx
0x180006636  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18000663b  test    eax, eax
0x18000663d  js      short loc_180006652
0x18000663f  mov     rax, [rdi]
0x180006642  mov     rdx, rbx
0x180006645  mov     rcx, rdi
0x180006648  mov     rax, [rax+40h]
0x18000664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006651  nop
0x180006652  test    eax, eax
0x180006654  jns     short loc_180006670
0x180006656  mov     rcx, [rsp+38h]; this
0x18000665b  mov     r9d, eax; char *
0x18000665e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006665  mov     edx, 71Bh; void *
0x18000666a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006670  mov     rax, rbx
0x180006673  mov     rbx, [rsp+38h+arg_8]
0x180006678  add     rsp, 30h
0x18000667c  pop     rdi
0x18000667d  retn
```
