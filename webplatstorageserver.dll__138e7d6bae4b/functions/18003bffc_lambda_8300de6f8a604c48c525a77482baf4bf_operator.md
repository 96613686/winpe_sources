# _lambda_8300de6f8a604c48c525a77482baf4bf_::operator()

- ea: `0x18003bffc`
- end: `0x18003c14b`
- name: `_lambda_8300de6f8a604c48c525a77482baf4bf_::operator()`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003bfc0`

## callees

- `0x18000e1c0`
- `0x180015a40`
- `0x180017618`
- `0x180017b70`
- `0x1800273f0`
- `0x18003bffc`
- `0x18003c154`
- `0x18003c2e4`
- `0x180065fcc`
- `0x180066010`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c085`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c099`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c0d3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c0e4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c085`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c099`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c0d3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c0e4`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18003c09f`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18003c09f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c079`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c08b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c0c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c0d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c079`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c08b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c0c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c0d9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003c073`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003c073`

## string_xrefs

- `0x18003c009`: `CacheStorage Delete Orphan`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_8300de6f8a604c48c525a77482baf4bf_::operator()(HANDLE **a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  const char *v8; // r9
  std::_Ref_count_base *v10[2]; // [rsp+20h] [rbp-38h] BYREF
  _OWORD v11[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SetThreadName(L"CacheStorage Delete Orphan");
  try
  {
    (*(void (__fastcall **)(HANDLE, std::_Ref_count_base **, _QWORD))(*(_QWORD *)**a1 + 32LL))(
      **a1,
      v10,
      *((unsigned int *)*a1 + 4));
    v11[0] = 0;
    v2 = HrJetBeginTransaction(*((_QWORD *)v10[0] + 3));
    v3 = v2;
    if ( v2 )
    {
      EseHelper::HandleUnexpectedEseError(v2, (char *)v10[0] + 56);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"onecoreuap\\inetcore\\lib\\esehelper\\lib\\databasetransaction.cxx",
        (const char *)v3,
        (int)v10[0]);
    }
    if ( v10[1] )
      _InterlockedIncrement((volatile signed __int32 *)v10[1] + 2);
    v11[0] = *(_OWORD *)v10;
    SetEvent(*a1[1]);
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, -1);
    v5 = GetCurrentThread();
    SetThreadPriority(v5, 0x10000);
    SwitchToThread();
    CacheStorageDeleteHelper::s_TryClearStagingTable(v10, 0);
    CacheStorageDeleteHelper::s_TryClearCacheStoragesTablePendingDeletes(v10);
    EseHelper::DatabaseTransaction::Commit((EseHelper::DatabaseTransaction *)v11);
    v6 = GetCurrentThread();
    SetThreadPriority(v6, 0x20000);
    v7 = GetCurrentThread();
    SetThreadPriority(v7, 0);
    EseHelper::DatabaseTransaction::~DatabaseTransaction((EseHelper::DatabaseTransaction *)v11);
    if ( v10[1] )
      std::_Ref_count_base::_Decref(v10[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\cachestoragedeletehelper.cxx",
      v8);
  }
  return SetThreadName(&word_1800D6108);
}

```

## disassembly

```asm
0x18003bffc  mov     [rsp+arg_0], rbx
0x18003c001  push    rdi
0x18003c002  sub     rsp, 50h
0x18003c006  mov     rdi, rcx
0x18003c009  lea     rcx, aCachestorageDe; "CacheStorage Delete Orphan"
0x18003c010  call    SetThreadName
0x18003c015  nop
0x18003c016  mov     r8, [rdi]
0x18003c019  mov     rcx, [r8]
0x18003c01c  mov     rax, [rcx]
0x18003c01f  mov     r8d, [r8+10h]
0x18003c023  lea     rdx, [rsp+58h+var_38]
0x18003c028  mov     rax, [rax+20h]
0x18003c02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c031  nop
0x18003c032  xorps   xmm0, xmm0
0x18003c035  movdqa  [rsp+58h+var_28], xmm0
0x18003c03b  mov     rcx, [rsp+58h+var_38]
0x18003c040  mov     rcx, [rcx+18h]; unsigned __int64
0x18003c044  call    ?HrJetBeginTransaction@@YAJ_K@Z; HrJetBeginTransaction(unsigned __int64)
0x18003c049  mov     ebx, eax
0x18003c04b  test    eax, eax
0x18003c04d  jnz     loc_18003C11E
0x18003c053  mov     rax, [rsp+58h+var_38+8]
0x18003c058  test    rax, rax
0x18003c05b  jz      short loc_18003C061
0x18003c05d  lock inc dword ptr [rax+8]
0x18003c061  movaps  xmm0, xmmword ptr [rsp+58h+var_38]
0x18003c066  movdqa  [rsp+58h+var_28], xmm0
0x18003c06c  mov     rcx, [rdi+8]
0x18003c070  mov     rcx, [rcx]; hEvent
0x18003c073  call    cs:__imp_SetEvent
0x18003c079  call    cs:__imp_GetCurrentThread
0x18003c07f  mov     rcx, rax; hThread
0x18003c082  or      edx, 0FFFFFFFFh; nPriority
0x18003c085  call    cs:__imp_SetThreadPriority
0x18003c08b  call    cs:__imp_GetCurrentThread
0x18003c091  mov     rcx, rax; hThread
0x18003c094  mov     edx, 10000h; nPriority
0x18003c099  call    cs:__imp_SetThreadPriority
0x18003c09f  call    cs:__imp_SwitchToThread
0x18003c0a5  xor     edx, edx
0x18003c0a7  lea     rcx, [rsp+58h+var_38]
0x18003c0ac  call    ?s_TryClearStagingTable@CacheStorageDeleteHelper@@CAXAEBV?$shared_ptr@UIDatabaseSession@EseHelper@@@std@@W4StagingTableIndex@Index@StagingTable@@@Z; CacheStorageDeleteHelper::s_TryClearStagingTable(std::shared_ptr<EseHelper::IDatabaseSession> const &,StagingTable::Index::StagingTableIndex)
0x18003c0b1  lea     rcx, [rsp+58h+var_38]
0x18003c0b6  call    ?s_TryClearCacheStoragesTablePendingDeletes@CacheStorageDeleteHelper@@CAXAEBV?$shared_ptr@UIDatabaseSession@EseHelper@@@std@@@Z; CacheStorageDeleteHelper::s_TryClearCacheStoragesTablePendingDeletes(std::shared_ptr<EseHelper::IDatabaseSession> const &)
0x18003c0bb  lea     rcx, [rsp+58h+var_28]; this
0x18003c0c0  call    ?Commit@DatabaseTransaction@EseHelper@@QEAAXXZ; EseHelper::DatabaseTransaction::Commit(void)
0x18003c0c5  call    cs:__imp_GetCurrentThread
0x18003c0cb  mov     rcx, rax; hThread
0x18003c0ce  mov     edx, 20000h; nPriority
0x18003c0d3  call    cs:__imp_SetThreadPriority
0x18003c0d9  call    cs:__imp_GetCurrentThread
0x18003c0df  mov     rcx, rax; hThread
0x18003c0e2  xor     edx, edx; nPriority
0x18003c0e4  call    cs:__imp_SetThreadPriority
0x18003c0ea  nop
0x18003c0eb  lea     rcx, [rsp+58h+var_28]; this
0x18003c0f0  call    ??1DatabaseTransaction@EseHelper@@QEAA@XZ; EseHelper::DatabaseTransaction::~DatabaseTransaction(void)
0x18003c0f5  nop
0x18003c0f6  mov     rcx, [rsp+58h+var_38+8]; this
0x18003c0fb  test    rcx, rcx
0x18003c0fe  jz      short loc_18003C106
0x18003c100  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003c105  nop
0x18003c106  lea     rcx, word_1800D6108; lpWideCharStr
0x18003c10d  call    SetThreadName
0x18003c112  nop
0x18003c113  mov     rbx, [rsp+58h+arg_0]
0x18003c118  add     rsp, 50h
0x18003c11c  pop     rdi
0x18003c11d  retn
0x18003c11e  mov     rdx, [rsp+58h+var_38]
0x18003c123  add     rdx, 38h ; '8'
0x18003c127  mov     ecx, ebx
0x18003c129  call    ?HandleUnexpectedEseError@EseHelper@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EseHelper::HandleUnexpectedEseError(long,std::wstring const &)
0x18003c12e  mov     rcx, [rsp+58h]; this
0x18003c133  mov     r9d, ebx; char *
0x18003c136  lea     r8, aOnecoreuapInet_49; "onecoreuap\\inetcore\\lib\\esehelper\\l"...
0x18003c13d  mov     edx, 15h; void *
0x18003c142  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c148  jmp     short loc_18003C106
```
