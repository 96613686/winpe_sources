# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180020c48`
- end: `0x180020d82`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006608`

## callees

- `0x1800067a0`
- `0x180006db4`
- `0x18000b924`
- `0x180020aa0`
- `0x180020c48`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180020ced`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180020ced`

## string_xrefs

- `0x180020caf`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        int a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  v14 = a3;
  dwindex = a2;
  v15 = 0;
  _InternalRelease___ComPtr_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__WRL_Microsoft__IEAAKXZ(&v15);
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1608;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v4,
      lpdwindex);
    goto LABEL_14;
  }
  v4 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1609;
    goto LABEL_5;
  }
  pHandles = *(HANDLE *)(v15 + 56);
  dwindex = 0;
  v4 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1621;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(v15 + 48) == 1 )
  {
    v5 = 0;
  }
  else
  {
    v10 = 0;
    v7 = **a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v5 = v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10);
    if ( v5 >= 0 )
    {
      v14 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 64LL))(v10, &v14);
      if ( v5 >= 0 )
        v5 = v14;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
LABEL_14:
  _InternalRelease___ComPtr_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__WRL_Microsoft__IEAAKXZ(&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020c48  mov     [rsp-18h+arg_18], r9
0x180020c4d  mov     [rsp-18h+arg_10], r8d
0x180020c52  mov     [rsp-18h+dwindex], edx
0x180020c56  push    rbp
0x180020c57  push    rbx
0x180020c58  push    rdi
0x180020c59  mov     rbp, rsp
0x180020c5c  sub     rsp, 40h
0x180020c60  mov     rdi, rcx
0x180020c63  mov     [rbp+arg_18], 0
0x180020c6b  lea     rcx, [rbp+arg_18]
0x180020c6f  call    ?InternalRelease@?$ComPtr@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::InternalRelease(void)
0x180020c74  lea     rcx, [rbp+arg_18]
0x180020c78  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x180020c7d  mov     ebx, eax
0x180020c7f  test    eax, eax
0x180020c81  jns     short loc_180020C8A
0x180020c83  mov     edx, 648h
0x180020c88  jmp     short loc_180020CA8
0x180020c8a  mov     rax, [rdi]
0x180020c8d  mov     rdx, [rbp+arg_18]
0x180020c91  mov     rcx, rdi
0x180020c94  mov     rax, [rax+30h]
0x180020c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c9d  mov     ebx, eax
0x180020c9f  test    eax, eax
0x180020ca1  jns     short loc_180020CC0
0x180020ca3  mov     edx, 649h; void *
0x180020ca8  mov     rcx, [rbp+18h]; this
0x180020cac  mov     r9d, eax; char *
0x180020caf  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020cb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cbb  jmp     loc_180020D6F
0x180020cc0  mov     rax, [rbp+arg_18]
0x180020cc4  mov     rcx, [rax+38h]
0x180020cc8  mov     [rbp+pHandles], rcx
0x180020ccc  mov     [rbp+dwindex], 0
0x180020cd3  lea     rax, [rbp+dwindex]
0x180020cd7  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x180020cdc  lea     r9, [rbp+pHandles]; pHandles
0x180020ce0  mov     r8d, 1; cHandles
0x180020ce6  or      edx, 0FFFFFFFFh; dwTimeout
0x180020ce9  lea     ecx, [r8+7]; dwFlags
0x180020ced  call    cs:__imp_CoWaitForMultipleHandles
0x180020cf3  mov     ebx, eax
0x180020cf5  test    eax, eax
0x180020cf7  jns     short loc_180020D00
0x180020cf9  mov     edx, 655h
0x180020cfe  jmp     short loc_180020CA8
0x180020d00  mov     rax, [rbp+arg_18]
0x180020d04  mov     ecx, [rax+30h]
0x180020d07  cmp     ecx, 1
0x180020d0a  jz      short loc_180020D6D
0x180020d0c  mov     [rbp+var_10], 0
0x180020d14  mov     rax, [rdi]
0x180020d17  mov     rbx, [rax]
0x180020d1a  lea     rcx, [rbp+var_10]
0x180020d1e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020d23  lea     r8, [rbp+var_10]
0x180020d27  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180020d2e  mov     rcx, rdi
0x180020d31  mov     rax, rbx
0x180020d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d39  mov     ebx, eax
0x180020d3b  test    eax, eax
0x180020d3d  js      short loc_180020D62
0x180020d3f  mov     [rbp+arg_10], 8000FFFFh
0x180020d46  mov     rcx, [rbp+var_10]
0x180020d4a  mov     rax, [rcx]
0x180020d4d  lea     rdx, [rbp+arg_10]
0x180020d51  mov     rax, [rax+40h]
0x180020d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d5a  mov     ebx, eax
0x180020d5c  test    eax, eax
0x180020d5e  cmovns  ebx, [rbp+arg_10]
0x180020d62  lea     rcx, [rbp+var_10]
0x180020d66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020d6b  jmp     short loc_180020D6F
0x180020d6d  xor     ebx, ebx
0x180020d6f  lea     rcx, [rbp+arg_18]
0x180020d73  call    ?InternalRelease@?$ComPtr@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::InternalRelease(void)
0x180020d78  mov     eax, ebx
0x180020d7a  add     rsp, 40h
0x180020d7e  pop     rdi
0x180020d7f  pop     rbx
0x180020d80  pop     rbp
0x180020d81  retn
```
