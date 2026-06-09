# ServiceWorkerStorageClient::EnsureTable(void)

- ea: `0x18003b3f8`
- end: `0x18003b588`
- name: `?EnsureTable@ServiceWorkerStorageClient@@QEAA?AV?$shared_ptr@VServiceWorkerDatabaseTable@@@std@@XZ`
- size: `400`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18003b2d0`
- `0x18003b3d0`
- `0x180067fa4`

## callees

- `0x18000e1c0`
- `0x18002f680`
- `0x18003b3f8`
- `0x18003b72c`
- `0x1800814bc`
- `0x1800c6010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003b581`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003b581`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003b46f`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003b46f`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003b44c`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003b44c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003b56f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003b56f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003b481`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003b481`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003b465`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003b465`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall ServiceWorkerStorageClient::EnsureTable(__int64 a1, _QWORD *a2)
{
  ServiceWorkerTable *v4; // rcx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, std::_Ref_count_base **, const unsigned __int16 *, void *); // rbx
  const unsigned __int16 *v7; // rax
  __int64 v8; // rax
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rdx
  std::_Ref_count_base *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  std::_Ref_count_base *v15[2]; // [rsp+38h] [rbp-21h] BYREF
  std::_Ref_count_base *v16[2]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v17; // [rsp+58h] [rbp-1h] BYREF
  std::_Ref_count_base *v18; // [rsp+60h] [rbp+7h]
  _QWORD Parameter[3]; // [rsp+68h] [rbp+Fh] BYREF
  _OWORD v20[3]; // [rsp+80h] [rbp+27h] BYREF
  _DWORD *v21; // [rsp+C0h] [rbp+67h]

  (*(void (__fastcall **)(_QWORD, __int64 *, _QWORD))(**(_QWORD **)(a1 + 72) + 32LL))(*(_QWORD *)(a1 + 72), &v17, 0);
  *(_OWORD *)v15 = 0;
  Parameter[0] = v15;
  Parameter[1] = a1;
  Parameter[2] = &v17;
  v20[0] = 0;
  __ExceptionPtrCreate(v20);
  InitOnceExecuteOnce(
    (PINIT_ONCE)(a1 + 64),
    lambda_56e6fc5e289388450c9dfe85180d5531_::_lambda_invoker_cdecl_,
    Parameter,
    0);
  if ( __ExceptionPtrToBool(v20) )
  {
    *(_OWORD *)v16 = 0;
    __ExceptionPtrCopy(v16, v20);
    __ExceptionPtrRethrow(v16);
    JUMPOUT(0x18003B587LL);
  }
  __ExceptionPtrDestroy(v20);
  if ( !v15[0] )
  {
    v5 = v17;
    v6 = *(__int64 (__fastcall **)(__int64, std::_Ref_count_base **, const unsigned __int16 *, void *))(*(_QWORD *)v17 + 8LL);
    v7 = ServiceWorkerTable::Name(v4);
    v8 = v6(v5, v16, v7, &ServiceWorkerTable::Schema);
    v9 = *(std::_Ref_count_base **)v8;
    v10 = *(std::_Ref_count_base **)(v8 + 8);
    *(_QWORD *)v8 = 0;
    *(_QWORD *)(v8 + 8) = 0;
    v15[0] = v9;
    v11 = v15[1];
    v15[1] = v10;
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
    if ( v16[1] )
      std::_Ref_count_base::_Decref(v16[1]);
  }
  v21 = operator new(0x20u);
  *(_OWORD *)v21 = 0;
  v21[2] = 1;
  v21[3] = 1;
  *(_QWORD *)v21 = &std::_Ref_count_obj2<ServiceWorkerRegistrationRow>::`vftable';
  std::shared_ptr<std::deque<__int64>>::shared_ptr<std::deque<__int64>>((_QWORD *)v21 + 2, v15);
  *a2 = v12;
  a2[1] = v13;
  if ( v15[1] )
    std::_Ref_count_base::_Decref(v15[1]);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  return a2;
}

```

## disassembly

```asm
0x18003b3f8  push    rbp
0x18003b3fa  push    rbx
0x18003b3fb  push    rsi
0x18003b3fc  push    rdi
0x18003b3fd  lea     rbp, [rsp-3Fh]
0x18003b402  sub     rsp, 98h
0x18003b409  mov     rsi, rdx
0x18003b40c  mov     rdi, rcx
0x18003b40f  mov     rcx, [rcx+48h]
0x18003b413  mov     rax, [rcx]
0x18003b416  xor     r8d, r8d
0x18003b419  lea     rdx, [rbp+57h+var_58]
0x18003b41d  mov     rax, [rax+20h]
0x18003b421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b426  nop
0x18003b427  xorps   xmm0, xmm0
0x18003b42a  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18003b42f  lea     rax, [rbp+57h+var_78]
0x18003b433  mov     [rbp+57h+Parameter], rax
0x18003b437  mov     [rbp+57h+var_40], rdi
0x18003b43b  lea     rax, [rbp+57h+var_58]
0x18003b43f  mov     [rbp+57h+var_38], rax
0x18003b443  movdqu  [rbp+57h+var_30], xmm0
0x18003b448  lea     rcx, [rbp+57h+var_30]
0x18003b44c  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003b452  nop
0x18003b453  xor     r9d, r9d; Context
0x18003b456  lea     r8, [rbp+57h+Parameter]; Parameter
0x18003b45a  lea     rdx, _lambda_56e6fc5e289388450c9dfe85180d5531____lambda_invoker_cdecl_; InitFn
0x18003b461  lea     rcx, [rdi+40h]; InitOnce
0x18003b465  call    cs:__imp_InitOnceExecuteOnce
0x18003b46b  lea     rcx, [rbp+57h+var_30]
0x18003b46f  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003b475  test    al, al
0x18003b477  jnz     loc_18003B55F
0x18003b47d  lea     rcx, [rbp+57h+var_30]
0x18003b481  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003b487  cmp     [rbp+57h+var_78], 0
0x18003b48c  jnz     short loc_18003B4F1
0x18003b48e  mov     rdi, [rbp+57h+var_58]
0x18003b492  mov     rax, [rdi]
0x18003b495  mov     rbx, [rax+8]
0x18003b499  call    ?Name@ServiceWorkerTable@@YAPEBGXZ; ServiceWorkerTable::Name(void)
0x18003b49e  lea     r9, ?Schema@ServiceWorkerTable@@3UTableDefinition@DatabaseSchema@EseHelper@@B; EseHelper::DatabaseSchema::TableDefinition const ServiceWorkerTable::Schema
0x18003b4a5  mov     r8, rax
0x18003b4a8  lea     rdx, [rbp+57h+var_68]
0x18003b4ac  mov     rcx, rdi
0x18003b4af  mov     rax, rbx
0x18003b4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4b7  mov     rcx, [rax]
0x18003b4ba  mov     rdx, [rax+8]
0x18003b4be  mov     qword ptr [rax], 0
0x18003b4c5  mov     qword ptr [rax+8], 0
0x18003b4cd  mov     [rbp+57h+var_78], rcx
0x18003b4d1  mov     rcx, [rbp+57h+var_78+8]; this
0x18003b4d5  mov     [rbp+57h+var_78+8], rdx
0x18003b4d9  test    rcx, rcx
0x18003b4dc  jz      short loc_18003B4E3
0x18003b4de  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b4e3  mov     rcx, [rbp+57h+var_68+8]; this
0x18003b4e7  test    rcx, rcx
0x18003b4ea  jz      short loc_18003B4F1
0x18003b4ec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b4f1  mov     ecx, 20h ; ' '; Size
0x18003b4f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b4fb  mov     r8, rax
0x18003b4fe  mov     [rbp+57h+arg_0], rax
0x18003b502  xorps   xmm0, xmm0
0x18003b505  movups  xmmword ptr [rax], xmm0
0x18003b508  mov     eax, 1
0x18003b50d  mov     [r8+8], eax
0x18003b511  mov     [r8+0Ch], eax
0x18003b515  lea     rax, ??_7?$_Ref_count_obj2@VServiceWorkerRegistrationRow@@@std@@6B@; const std::_Ref_count_obj2<ServiceWorkerRegistrationRow>::`vftable'
0x18003b51c  mov     [r8], rax
0x18003b51f  lea     rcx, [r8+10h]
0x18003b523  lea     rdx, [rbp+57h+var_78]
0x18003b527  call    ??0?$shared_ptr@V?$deque@_JV?$allocator@_J@std@@@std@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<std::deque<__int64>>::shared_ptr<std::deque<__int64>>(std::shared_ptr<std::deque<__int64>> const &)
0x18003b52c  mov     [rsi], rcx
0x18003b52f  mov     [rsi+8], r8
0x18003b533  mov     rcx, [rbp+57h+var_78+8]; this
0x18003b537  test    rcx, rcx
0x18003b53a  jz      short loc_18003B542
0x18003b53c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b541  nop
0x18003b542  mov     rcx, [rbp+57h+var_50]; this
0x18003b546  test    rcx, rcx
0x18003b549  jz      short loc_18003B550
0x18003b54b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b550  mov     rax, rsi
0x18003b553  add     rsp, 98h
0x18003b55a  pop     rdi
0x18003b55b  pop     rsi
0x18003b55c  pop     rbx
0x18003b55d  pop     rbp
0x18003b55e  retn
0x18003b55f  xorps   xmm0, xmm0
0x18003b562  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18003b567  lea     rdx, [rbp+57h+var_30]
0x18003b56b  lea     rcx, [rbp+57h+var_68]
0x18003b56f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003b575  lea     rax, [rbp+57h+var_68]
0x18003b579  mov     [rbp+57h+arg_0], rax
0x18003b57d  lea     rcx, [rbp+57h+var_68]
0x18003b581  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
