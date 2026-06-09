# CacheStorageClient::OpenOrCreateCacheStorageTablesInNewSessionHelper(bool)

- ea: `0x18003bdb8`
- end: `0x18003bfaf`
- name: `?OpenOrCreateCacheStorageTablesInNewSessionHelper@CacheStorageClient@@AEAA?AUCacheStorageTables@@_N@Z`
- size: `503`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003bcf8`
- `0x18007ed28`

## callees

- `0x18000e1c0`
- `0x18003bdb8`
- `0x18003c3ec`
- `0x18003c67c`
- `0x1800c6010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003bfa8`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003bfa8`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003be48`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003be48`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003be23`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003be23`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003bf96`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003bf96`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003be5a`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003be5a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003be3c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003be3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall CacheStorageClient::OpenOrCreateCacheStorageTablesInNewSessionHelper(
        __int64 a1,
        _QWORD *a2,
        char a3)
{
  BOOL inited; // edi
  std::_Ref_count_base *v7; // rdi
  __int64 (__fastcall *v8)(std::_Ref_count_base *, _BYTE *, const unsigned __int16 *, void *); // rbx
  CacheStoragesTable *v9; // rcx
  const unsigned __int16 *v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  std::_Ref_count_base *v14; // rcx
  std::_Ref_count_base *v15; // rcx
  std::_Ref_count_base *v16; // rdi
  __int64 (__fastcall *v17)(std::_Ref_count_base *, _BYTE *, const unsigned __int16 *, void *); // rbx
  const unsigned __int16 *v18; // rax
  __int64 *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  std::_Ref_count_base *v22; // rcx
  std::_Ref_count_base *v23[2]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v24[8]; // [rsp+48h] [rbp-38h] BYREF
  std::_Ref_count_base *v25; // [rsp+50h] [rbp-30h]
  _QWORD Parameter[3]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v27; // [rsp+70h] [rbp-10h] BYREF
  char v28; // [rsp+B0h] [rbp+30h] BYREF

  v28 = a3;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  a2[3] = 0;
  Parameter[0] = a2;
  Parameter[1] = a1;
  Parameter[2] = &v28;
  v27 = 0;
  __ExceptionPtrCreate(&v27);
  inited = InitOnceExecuteOnce(
             (PINIT_ONCE)(a1 + 40),
             lambda_25fa63afcae5292643df52702cc968ff_::_lambda_invoker_cdecl_,
             Parameter,
             0);
  if ( __ExceptionPtrToBool(&v27) )
  {
    *(_OWORD *)v23 = 0;
    __ExceptionPtrCopy(v23, &v27);
    __ExceptionPtrRethrow(v23);
    JUMPOUT(0x18003BFAELL);
  }
  __ExceptionPtrDestroy(&v27);
  if ( inited && !*a2 )
  {
    (*(void (__fastcall **)(_QWORD, std::_Ref_count_base **, bool))(**(_QWORD **)(a1 + 24) + 32LL))(
      *(_QWORD *)(a1 + 24),
      v23,
      *(_BYTE *)(a1 + 160) != 0);
    v7 = v23[0];
    v8 = *(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *, const unsigned __int16 *, void *))(*(_QWORD *)v23[0] + 8LL);
    v10 = CacheStoragesTable::Name(v9);
    v11 = (__int64 *)v8(v7, v24, v10, &CacheStoragesTable::Schema);
    v12 = *v11;
    v13 = v11[1];
    *v11 = 0;
    v11[1] = 0;
    *a2 = v12;
    v14 = (std::_Ref_count_base *)a2[1];
    a2[1] = v13;
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    v15 = v25;
    if ( v25 )
      std::_Ref_count_base::_Decref(v25);
    v16 = v23[0];
    v17 = *(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *, const unsigned __int16 *, void *))(*(_QWORD *)v23[0] + 8LL);
    v18 = StagingTable::Name(v15);
    v19 = (__int64 *)v17(v16, v24, v18, &StagingTable::Schema);
    v20 = *v19;
    v21 = v19[1];
    *v19 = 0;
    v19[1] = 0;
    a2[2] = v20;
    v22 = (std::_Ref_count_base *)a2[3];
    a2[3] = v21;
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    if ( v25 )
      std::_Ref_count_base::_Decref(v25);
    if ( v23[1] )
      std::_Ref_count_base::_Decref(v23[1]);
  }
  return a2;
}

```

## disassembly

```asm
0x18003bdb8  mov     [rsp-18h+arg_18], rbx
0x18003bdbd  mov     [rsp-18h+arg_10], r8b
0x18003bdc2  mov     [rsp-18h+arg_8], rdx
0x18003bdc7  push    rbp
0x18003bdc8  push    rsi
0x18003bdc9  push    rdi
0x18003bdca  mov     rbp, rsp
0x18003bdcd  sub     rsp, 80h
0x18003bdd4  mov     rsi, rdx
0x18003bdd7  mov     rbx, rcx
0x18003bdda  mov     [rbp+var_50], 0
0x18003bde1  mov     qword ptr [rdx], 0
0x18003bde8  mov     qword ptr [rdx+8], 0
0x18003bdf0  mov     qword ptr [rdx+10h], 0
0x18003bdf8  mov     qword ptr [rdx+18h], 0
0x18003be00  mov     [rbp+var_50], 1
0x18003be07  mov     [rbp+Parameter], rdx
0x18003be0b  mov     [rbp+var_20], rcx
0x18003be0f  lea     rax, [rbp+arg_10]
0x18003be13  mov     [rbp+var_18], rax
0x18003be17  xorps   xmm0, xmm0
0x18003be1a  movdqu  [rbp+var_10], xmm0
0x18003be1f  lea     rcx, [rbp+var_10]
0x18003be23  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003be29  nop
0x18003be2a  lea     rcx, [rbx+28h]; InitOnce
0x18003be2e  xor     r9d, r9d; Context
0x18003be31  lea     r8, [rbp+Parameter]; Parameter
0x18003be35  lea     rdx, _lambda_25fa63afcae5292643df52702cc968ff____lambda_invoker_cdecl_; InitFn
0x18003be3c  call    cs:__imp_InitOnceExecuteOnce
0x18003be42  mov     edi, eax
0x18003be44  lea     rcx, [rbp+var_10]
0x18003be48  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003be4e  test    al, al
0x18003be50  jnz     loc_18003BF86
0x18003be56  lea     rcx, [rbp+var_10]
0x18003be5a  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003be60  test    edi, edi
0x18003be62  jnz     short loc_18003BE7A
0x18003be64  mov     rax, rsi
0x18003be67  mov     rbx, [rsp+80h+arg_18]
0x18003be6f  add     rsp, 80h
0x18003be76  pop     rdi
0x18003be77  pop     rsi
0x18003be78  pop     rbp
0x18003be79  retn
0x18003be7a  cmp     qword ptr [rsi], 0
0x18003be7e  jnz     short loc_18003BE64
0x18003be80  mov     rcx, [rbx+18h]
0x18003be84  mov     rax, [rcx]
0x18003be87  xor     r8d, r8d
0x18003be8a  cmp     [rbx+0A0h], r8b
0x18003be91  setnz   r8b
0x18003be95  lea     rdx, [rbp+var_48]
0x18003be99  mov     rax, [rax+20h]
0x18003be9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bea2  mov     [rbp+var_50], 3
0x18003bea9  mov     rdi, [rbp+var_48]
0x18003bead  mov     rax, [rdi]
0x18003beb0  mov     rbx, [rax+8]
0x18003beb4  call    ?Name@CacheStoragesTable@@YAPEBGXZ; CacheStoragesTable::Name(void)
0x18003beb9  lea     r9, ?Schema@CacheStoragesTable@@3UTableDefinition@DatabaseSchema@EseHelper@@B; EseHelper::DatabaseSchema::TableDefinition const CacheStoragesTable::Schema
0x18003bec0  mov     r8, rax
0x18003bec3  lea     rdx, [rbp+var_38]
0x18003bec7  mov     rcx, rdi
0x18003beca  mov     rax, rbx
0x18003becd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bed2  mov     rcx, [rax]
0x18003bed5  mov     rdx, [rax+8]
0x18003bed9  mov     qword ptr [rax], 0
0x18003bee0  mov     qword ptr [rax+8], 0
0x18003bee8  mov     [rsi], rcx
0x18003beeb  mov     rcx, [rsi+8]; this
0x18003beef  mov     [rsi+8], rdx
0x18003bef3  test    rcx, rcx
0x18003bef6  jz      short loc_18003BEFD
0x18003bef8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003befd  mov     rcx, [rbp+var_30]; this
0x18003bf01  test    rcx, rcx
0x18003bf04  jz      short loc_18003BF0B
0x18003bf06  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003bf0b  mov     rdi, [rbp+var_48]
0x18003bf0f  mov     rax, [rdi]
0x18003bf12  mov     rbx, [rax+8]
0x18003bf16  call    ?Name@StagingTable@@YAPEBGXZ; StagingTable::Name(void)
0x18003bf1b  lea     r9, ?Schema@StagingTable@@3UTableDefinition@DatabaseSchema@EseHelper@@B; EseHelper::DatabaseSchema::TableDefinition const StagingTable::Schema
0x18003bf22  mov     r8, rax
0x18003bf25  lea     rdx, [rbp+var_38]
0x18003bf29  mov     rcx, rdi
0x18003bf2c  mov     rax, rbx
0x18003bf2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf34  mov     rcx, [rax]
0x18003bf37  mov     rdx, [rax+8]
0x18003bf3b  mov     qword ptr [rax], 0
0x18003bf42  mov     qword ptr [rax+8], 0
0x18003bf4a  mov     [rsi+10h], rcx
0x18003bf4e  mov     rcx, [rsi+18h]; this
0x18003bf52  mov     [rsi+18h], rdx
0x18003bf56  test    rcx, rcx
0x18003bf59  jz      short loc_18003BF60
0x18003bf5b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003bf60  mov     rcx, [rbp+var_30]; this
0x18003bf64  test    rcx, rcx
0x18003bf67  jz      short loc_18003BF6F
0x18003bf69  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003bf6e  nop
0x18003bf6f  mov     rcx, [rbp+var_48+8]; this
0x18003bf73  test    rcx, rcx
0x18003bf76  jz      loc_18003BE64
0x18003bf7c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003bf81  jmp     loc_18003BE64
0x18003bf86  xorps   xmm0, xmm0
0x18003bf89  movdqu  xmmword ptr [rbp+var_48], xmm0
0x18003bf8e  lea     rdx, [rbp+var_10]
0x18003bf92  lea     rcx, [rbp+var_48]
0x18003bf96  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003bf9c  lea     rax, [rbp+var_48]
0x18003bfa0  mov     [rbp+arg_0], rax
0x18003bfa4  lea     rcx, [rbp+var_48]
0x18003bfa8  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
