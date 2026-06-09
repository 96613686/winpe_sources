# wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18004e4d0`
- end: `0x18004e69e`
- name: `?Stop@?$ActivityBase@VDataPackageTracing@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18005dcac`

## callees

- `0x180001d2c`
- `0x180002ad0`
- `0x18000346c`
- `0x18003a774`
- `0x18003daf8`
- `0x18004e4d0`
- `0x180050ef0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e52f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e52f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e586`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e612`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e586`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e612`

## string_xrefs

- `0x18004e62d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 *v10; // rcx
  const struct wil::FailureInfo *v11; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v16; // [rsp+70h] [rbp-90h]
  __int64 v17; // [rsp+78h] [rbp-88h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-80h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-70h]
  __int64 v21; // [rsp+98h] [rbp-68h]
  void *retaddr; // [rsp+128h] [rbp+28h]

  wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v15, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v15, v11);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    result = (__int64)DataPackageTracing::Provider();
    v8 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = a2;
        v14 = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v21 = 4;
        p_SRWLock = &SRWLock;
        v19 = 4;
        v16 = &v14;
        v17 = 8;
        result = tlgWriteTransfer_EventWriteTransfer(v8, byte_18009AC95, *(_QWORD *)(a1 + 272) + 8LL, 0, 5, v15);
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v9 = a1 + 288;
    if ( *(_DWORD *)(v9 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v9 + 24) = 0;
    v10 = *(__int64 **)v9;
    while ( 1 )
    {
      result = *v10;
      if ( !*v10 )
        break;
      if ( result == v9 )
      {
        result = *(_QWORD *)(v9 + 16);
        *v10 = result;
        break;
      }
      v10 = (__int64 *)(result + 16);
      *(_QWORD *)v9 = result + 16;
    }
    *(_QWORD *)v9 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004e4d0  push    rbp
0x18004e4d2  push    rbx
0x18004e4d3  push    rsi
0x18004e4d4  push    rdi
0x18004e4d5  lea     rbp, [rsp-8]
0x18004e4da  sub     rsp, 108h
0x18004e4e1  mov     rax, cs:__security_cookie
0x18004e4e8  xor     rax, rsp
0x18004e4eb  mov     [rbp+20h+var_30], rax
0x18004e4ef  mov     esi, edx
0x18004e4f1  mov     rbx, rcx
0x18004e4f4  lea     rdx, [rsp+120h+SRWLock]
0x18004e4f9  call    ?LockExclusive@?$ActivityBase@VDataPackageTracing@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004e4fe  mov     rax, [rbx+110h]
0x18004e505  mov     edi, [rax+0F8h]
0x18004e50b  cmp     edi, 1
0x18004e50e  jl      loc_18004E681
0x18004e514  cmp     dword ptr [rax+48h], 0
0x18004e518  jl      short loc_18004E51D
0x18004e51a  mov     [rax+48h], esi
0x18004e51d  dec     edi
0x18004e51f  mov     [rax+0F8h], edi
0x18004e525  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x18004e52a  test    rcx, rcx
0x18004e52d  jz      short loc_18004E535
0x18004e52f  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e535  test    edi, edi
0x18004e537  jnz     short loc_18004E54D
0x18004e539  mov     rax, [rbx]
0x18004e53c  mov     rcx, rbx
0x18004e53f  mov     rax, [rax+8]
0x18004e543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e548  jmp     loc_18004E602
0x18004e54d  call    ?Provider@DataPackageTracing@@SAPEBU_tlgProvider_t@@XZ; DataPackageTracing::Provider(void)
0x18004e552  mov     rdi, rax
0x18004e555  mov     ecx, [rax]
0x18004e557  cmp     ecx, 5
0x18004e55a  jbe     loc_18004E602
0x18004e560  mov     rax, [rax+18h]
0x18004e564  mov     rcx, [rdi+10h]
0x18004e568  mov     rdx, 400000000000h
0x18004e572  test    rdx, rcx
0x18004e575  jz      loc_18004E602
0x18004e57b  mov     rcx, rax
0x18004e57e  and     rcx, rdx
0x18004e581  cmp     rcx, rax
0x18004e584  jnz     short loc_18004E602
0x18004e586  call    cs:__imp_GetCurrentThreadId
0x18004e58c  mov     [rsp+120h+var_F0], eax
0x18004e590  mov     dword ptr [rsp+120h+SRWLock], esi
0x18004e594  mov     [rsp+120h+var_E0], 1000000h
0x18004e59d  lea     rax, [rsp+120h+var_F0]
0x18004e5a2  mov     [rbp+20h+var_90], rax
0x18004e5a6  mov     [rbp+20h+var_88], 4
0x18004e5ae  lea     rax, [rsp+120h+SRWLock]
0x18004e5b3  mov     [rbp+20h+var_A0], rax
0x18004e5b7  mov     [rbp+20h+var_98], 4
0x18004e5bf  lea     rax, [rsp+120h+var_E0]
0x18004e5c4  mov     [rsp+120h+var_B0], rax
0x18004e5c9  mov     [rsp+120h+var_A8], 8
0x18004e5d2  mov     r8, [rbx+110h]
0x18004e5d9  add     r8, 8
0x18004e5dd  lea     rax, [rsp+120h+var_D0]
0x18004e5e2  mov     [rsp+120h+var_F8], rax
0x18004e5e7  mov     [rsp+120h+var_100], 5
0x18004e5ef  xor     r9d, r9d
0x18004e5f2  lea     rdx, byte_18009AC95
0x18004e5f9  mov     rcx, rdi
0x18004e5fc  call    _tlgWriteTransfer_EventWriteTransfer
0x18004e601  nop
0x18004e602  cmp     dword ptr [rbx+138h], 0
0x18004e609  jz      short loc_18004E669
0x18004e60b  add     rbx, 120h
0x18004e612  call    cs:__imp_GetCurrentThreadId
0x18004e618  cmp     [rbx+18h], eax
0x18004e61b  jz      short loc_18004E639
0x18004e61d  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18004e624  test    rax, rax
0x18004e627  jz      short loc_18004E639
0x18004e629  mov     rdx, [rbp+28h]
0x18004e62d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18004e634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e639  mov     dword ptr [rbx+18h], 0
0x18004e640  mov     rcx, [rbx]
0x18004e643  jmp     short loc_18004E651
0x18004e645  cmp     rax, rbx
0x18004e648  jz      short loc_18004E65B
0x18004e64a  lea     rcx, [rax+10h]
0x18004e64e  mov     [rbx], rcx
0x18004e651  mov     rax, [rcx]
0x18004e654  test    rax, rax
0x18004e657  jnz     short loc_18004E645
0x18004e659  jmp     short loc_18004E662
0x18004e65b  mov     rax, [rbx+10h]
0x18004e65f  mov     [rcx], rax
0x18004e662  mov     qword ptr [rbx], 0
0x18004e669  mov     rcx, [rbp+20h+var_30]
0x18004e66d  xor     rcx, rsp; StackCookie
0x18004e670  call    __security_check_cookie
0x18004e675  add     rsp, 108h
0x18004e67c  pop     rdi
0x18004e67d  pop     rsi
0x18004e67e  pop     rbx
0x18004e67f  pop     rbp
0x18004e680  retn
0x18004e681  xor     edx, edx; Val
0x18004e683  mov     r8d, 98h; Size
0x18004e689  lea     rcx, [rsp+120h+var_D0]; void *
0x18004e68e  call    memset_0
0x18004e693  lea     rcx, [rsp+120h+var_D0]; this
0x18004e698  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
