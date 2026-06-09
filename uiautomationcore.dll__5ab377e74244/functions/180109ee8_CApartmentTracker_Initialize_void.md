# CApartmentTracker::Initialize(void)

- ea: `0x180109ee8`
- end: `0x18010a00f`
- name: `?Initialize@CApartmentTracker@@QEAAJXZ`
- size: `295`
- prototype: `__int64 __fastcall(CApartmentTracker *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007f1d0`
- `0x1800805e0`
- `0x180109940`

## callees

- `0x1800d2f00`
- `0x180109ee8`
- `0x18010a018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180109f09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180109f09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180109fda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180109fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109f10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109fac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109f10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109fac`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x180109f9d`
- `api-ms-win-core-com-private-l1-1-0!CoRevokeInitializeSpy` at `0x180109f9d`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180109ff1`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180109ff1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CApartmentTracker::Initialize(ULARGE_INTEGER *this)
{
  DWORD CurrentThreadId; // r9d
  __int64 v3; // rdx
  unsigned __int64 i; // r8
  __int64 v5; // rax
  __int64 v6; // rdi
  DWORD v7; // eax
  HRESULT result; // eax
  DWORD v9; // [rsp+48h] [rbp+10h]
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+50h] [rbp+18h]

  v10 = &CApartmentTracker::_classLock;
  EnterCriticalSection(&CApartmentTracker::_classLock);
  CurrentThreadId = GetCurrentThreadId();
  v9 = CurrentThreadId;
  v3 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v3 = 0x100000001B3LL * (*((unsigned __int8 *)&v9 + i) ^ (unsigned __int64)v3);
  v5 = *((_QWORD *)Block + 2 * (v3 & qword_18039F790) + 1);
  if ( v5 == qword_18039F768 )
  {
LABEL_7:
    v5 = 0;
  }
  else
  {
    while ( CurrentThreadId != *(_DWORD *)(v5 + 16) )
    {
      if ( v5 == *((_QWORD *)Block + 2 * (v3 & qword_18039F790)) )
        goto LABEL_7;
      v5 = *(_QWORD *)(v5 + 8);
    }
  }
  v6 = qword_18039F768;
  if ( v5 )
    v6 = v5;
  if ( v6 != qword_18039F768 )
  {
    CoRevokeInitializeSpy(*(ULARGE_INTEGER *)(*(_QWORD *)(v6 + 24) + 32LL));
    RefcountBase::Release(*(RefcountBase **)(v6 + 24));
  }
  v7 = GetCurrentThreadId();
  v9 = v7;
  try
  {
    *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,CApartmentTracker *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,CApartmentTracker *>>,0>>::_Try_emplace<unsigned long,>()
              + 24LL) = this;
    _InterlockedIncrement((volatile signed __int32 *)&this[1]);
    this[3].LowPart = 1;
    LeaveCriticalSection(&CApartmentTracker::_classLock);
    result = CoRegisterInitializeSpy((IInitializeSpy *)((unsigned __int64)&this[2] & -(__int64)(this != 0)), this + 4);
  }
  catch ( std::bad_alloc )
  {
    return -2147024882;
  }
  return result;
}

```

## disassembly

```asm
0x180109ee8  mov     [rsp+arg_0], rbx
0x180109eed  mov     [rsp+arg_18], rsi
0x180109ef2  push    rdi
0x180109ef3  sub     rsp, 30h
0x180109ef7  mov     rsi, rcx
0x180109efa  lea     rbx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CApartmentTracker::_classLock
0x180109f01  mov     [rsp+38h+arg_10], rbx
0x180109f06  mov     rcx, rbx; lpCriticalSection
0x180109f09  call    cs:__imp_EnterCriticalSection
0x180109f0f  nop
0x180109f10  call    cs:__imp_GetCurrentThreadId
0x180109f16  mov     r9d, eax
0x180109f19  mov     [rsp+38h+arg_8], eax
0x180109f1d  mov     rdx, 0CBF29CE484222325h
0x180109f27  xor     r8d, r8d
0x180109f2a  movzx   ecx, byte ptr [rsp+r8+38h+arg_8]
0x180109f30  xor     rdx, rcx
0x180109f33  mov     rax, 100000001B3h
0x180109f3d  imul    rdx, rax
0x180109f41  inc     r8
0x180109f44  cmp     r8, 4
0x180109f48  jb      short loc_180109F2A
0x180109f4a  mov     rcx, cs:qword_18039F790
0x180109f51  and     rcx, rdx
0x180109f54  add     rcx, rcx
0x180109f57  mov     rdx, cs:Block
0x180109f5e  mov     rax, [rdx+rcx*8+8]
0x180109f63  mov     r8, cs:qword_18039F768
0x180109f6a  cmp     rax, r8
0x180109f6d  jz      short loc_180109F84
0x180109f6f  mov     r10, [rdx+rcx*8]
0x180109f73  cmp     r9d, [rax+10h]
0x180109f77  jz      short loc_180109F86
0x180109f79  cmp     rax, r10
0x180109f7c  jz      short loc_180109F84
0x180109f7e  mov     rax, [rax+8]
0x180109f82  jmp     short loc_180109F73
0x180109f84  xor     eax, eax
0x180109f86  mov     rdi, r8
0x180109f89  test    rax, rax
0x180109f8c  cmovnz  rdi, rax
0x180109f90  cmp     rdi, r8
0x180109f93  jz      short loc_180109FAC
0x180109f95  mov     rcx, [rdi+18h]
0x180109f99  mov     rcx, [rcx+20h]; uliCookie
0x180109f9d  call    cs:__imp_CoRevokeInitializeSpy
0x180109fa3  mov     rcx, [rdi+18h]; this
0x180109fa7  call    ?Release@RefcountBase@@QEAAKXZ; RefcountBase::Release(void)
0x180109fac  call    cs:__imp_GetCurrentThreadId
0x180109fb2  mov     [rsp+38h+arg_8], eax
0x180109fb6  lea     r8, [rsp+38h+arg_8]
0x180109fbb  lea     rdx, [rsp+38h+var_18]
0x180109fc0  call    ??$_Try_emplace@K$$V@?$_Hash@V?$_Umap_traits@KPEAVCApartmentTracker@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAVCApartmentTracker@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKPEAVCApartmentTracker@@@std@@PEAX@std@@_N@1@$$QEAK@Z; std::_Hash<std::_Umap_traits<ulong,CApartmentTracker *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,CApartmentTracker *>>,0>>::_Try_emplace<ulong,>(ulong &&)
0x180109fc5  mov     rax, [rax]
0x180109fc8  mov     [rax+18h], rsi
0x180109fcc  lock inc dword ptr [rsi+8]
0x180109fd0  mov     dword ptr [rsi+18h], 1
0x180109fd7  mov     rcx, rbx; lpCriticalSection
0x180109fda  call    cs:__imp_LeaveCriticalSection
0x180109fe0  lea     rdx, [rsi+20h]; puliCookie
0x180109fe4  lea     rax, [rsi+10h]
0x180109fe8  neg     rsi
0x180109feb  sbb     rcx, rcx
0x180109fee  and     rcx, rax; pSpy
0x180109ff1  call    cs:__imp_CoRegisterInitializeSpy
0x180109ff7  nop
0x180109ff8  mov     rbx, [rsp+38h+arg_0]
0x180109ffd  mov     rsi, [rsp+38h+arg_18]
0x18010a002  add     rsp, 30h
0x18010a006  pop     rdi
0x18010a007  retn
0x18010a008  mov     eax, 8007000Eh
0x18010a00d  jmp     short loc_180109FF8
```
