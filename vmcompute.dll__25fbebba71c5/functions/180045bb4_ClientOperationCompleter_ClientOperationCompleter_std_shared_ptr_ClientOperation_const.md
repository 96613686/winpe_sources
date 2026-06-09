# ClientOperationCompleter::ClientOperationCompleter(std::shared_ptr<ClientOperation> const &)

- ea: `0x180045bb4`
- end: `0x180045d90`
- name: `??0ClientOperationCompleter@@QEAA@AEBV?$shared_ptr@VClientOperation@@@std@@@Z`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180047aac`

## callees

- `0x180002f74`
- `0x180003388`
- `0x180003534`
- `0x18000d0ec`
- `0x18003881c`
- `0x180045bb4`
- `0x1800468c4`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045d34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045d53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045d53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180045d45`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180045d45`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180045d1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180045d1c`

## string_xrefs

- `0x180045d7e`: `onecore\vm\compute\dll\lib\core\ClientOperation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClientOperationCompleter::ClientOperationCompleter(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  char *v5; // rbx
  ClientOperationCompleter::CompleteContext *v6; // rbp
  _QWORD *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rbx
  PTP_WORK ThreadpoolWork; // rsi
  const char *v12; // r9
  struct _TP_WORK *v13; // rbp
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v4 = *(_QWORD *)(a2 + 8);
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  *(_QWORD *)a1 = *(_QWORD *)a2;
  *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  if ( ClientOperation::HasCompletionCallback(*(PSRWLOCK *)a2) )
  {
    v5 = (char *)operator new(0x48u);
    *((_DWORD *)v5 + 5) = 0;
    *((_QWORD *)v5 + 8) = 0;
    *(_QWORD *)v5 = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_DWORD *)v5 + 4) = -2147418113;
    *((_QWORD *)v5 + 3) = 0;
    *((_DWORD *)v5 + 8) = -1;
    *((_DWORD *)v5 + 9) = 0;
    *(_OWORD *)(v5 + 40) = 0;
    *((_QWORD *)v5 + 7) = 0;
    `eh vector constructor iterator'(
      v5 + 40,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
    v5[64] = 0;
    v6 = *(ClientOperationCompleter::CompleteContext **)(a1 + 24);
    *(_QWORD *)(a1 + 24) = v5;
    if ( v6 )
    {
      ClientOperationCompleter::CompleteContext::~CompleteContext(v6);
      operator delete(v6, 0x48u);
    }
    v7 = *(_QWORD **)(a1 + 24);
    v8 = *(_QWORD *)(a2 + 8);
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    v9 = *(_QWORD *)(a2 + 8);
    *v7 = *(_QWORD *)a2;
    v10 = (volatile signed __int32 *)v7[1];
    v7[1] = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    ThreadpoolWork = CreateThreadpoolWork(ClientOperationCompleter::CompleteWorker, *(PVOID *)(a1 + 24), 0);
    v13 = *(struct _TP_WORK **)(a1 + 16);
    if ( v13 )
    {
      LastError = GetLastError();
      CloseThreadpoolWork(v13);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 16) = ThreadpoolWork;
    if ( !ThreadpoolWork )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\ClientOperation.h",
        v12);
  }
  return a1;
}

```

## disassembly

```asm
0x180045bb4  mov     [rsp+arg_10], rbx
0x180045bb9  push    rbp
0x180045bba  push    rsi
0x180045bbb  push    rdi
0x180045bbc  sub     rsp, 40h
0x180045bc0  mov     rsi, rdx
0x180045bc3  mov     rdi, rcx
0x180045bc6  mov     [rsp+58h+var_20], rcx
0x180045bcb  mov     qword ptr [rcx], 0
0x180045bd2  mov     qword ptr [rcx+8], 0
0x180045bda  mov     rax, [rdx+8]
0x180045bde  test    rax, rax
0x180045be1  jz      short loc_180045BE7
0x180045be3  lock inc dword ptr [rax+8]
0x180045be7  mov     rax, [rdx]
0x180045bea  mov     [rcx], rax
0x180045bed  mov     rax, [rdx+8]
0x180045bf1  mov     [rcx+8], rax
0x180045bf5  mov     qword ptr [rcx+10h], 0
0x180045bfd  mov     qword ptr [rcx+18h], 0
0x180045c05  mov     rcx, [rdx]; SRWLock
0x180045c08  call    ?HasCompletionCallback@ClientOperation@@QEAA_NXZ; ClientOperation::HasCompletionCallback(void)
0x180045c0d  test    al, al
0x180045c0f  jz      loc_180045D6D
0x180045c15  mov     ecx, 48h ; 'H'; Size
0x180045c1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045c1f  mov     rbx, rax
0x180045c22  mov     dword ptr [rax+14h], 0
0x180045c29  mov     qword ptr [rax+40h], 0
0x180045c31  mov     qword ptr [rax], 0
0x180045c38  mov     qword ptr [rax+8], 0
0x180045c40  mov     dword ptr [rax+10h], 8000FFFFh
0x180045c47  mov     qword ptr [rax+18h], 0
0x180045c4f  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x180045c56  xor     eax, eax
0x180045c58  mov     [rbx+24h], eax
0x180045c5b  lea     rcx, [rbx+28h]; void *
0x180045c5f  xorps   xmm0, xmm0
0x180045c62  movups  xmmword ptr [rcx], xmm0
0x180045c65  mov     [rcx+10h], rax
0x180045c69  lea     rax, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x180045c70  mov     [rsp+58h+var_38], rax; void (*)(void *)
0x180045c75  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180045c7c  mov     edx, 8; unsigned __int64
0x180045c81  lea     r8d, [rdx-5]; unsigned __int64
0x180045c85  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180045c8a  mov     byte ptr [rbx+40h], 0
0x180045c8e  mov     rbp, [rdi+18h]
0x180045c92  mov     [rdi+18h], rbx
0x180045c96  test    rbp, rbp
0x180045c99  jz      short loc_180045CB0
0x180045c9b  mov     rcx, rbp; this
0x180045c9e  call    ??1CompleteContext@ClientOperationCompleter@@QEAA@XZ; ClientOperationCompleter::CompleteContext::~CompleteContext(void)
0x180045ca3  mov     edx, 48h ; 'H'; unsigned __int64
0x180045ca8  mov     rcx, rbp; void *
0x180045cab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180045cb0  mov     rdx, [rdi+18h]
0x180045cb4  mov     rax, [rsi+8]
0x180045cb8  test    rax, rax
0x180045cbb  jz      short loc_180045CC1
0x180045cbd  lock inc dword ptr [rax+8]
0x180045cc1  mov     rcx, [rsi+8]
0x180045cc5  mov     rax, [rsi]
0x180045cc8  mov     [rdx], rax
0x180045ccb  mov     rbx, [rdx+8]
0x180045ccf  mov     [rdx+8], rcx
0x180045cd3  test    rbx, rbx
0x180045cd6  jz      short loc_180045D0E
0x180045cd8  or      esi, 0FFFFFFFFh
0x180045cdb  mov     eax, esi
0x180045cdd  lock xadd [rbx+8], eax
0x180045ce2  add     eax, esi
0x180045ce4  jnz     short loc_180045D0E
0x180045ce6  mov     rax, [rbx]
0x180045ce9  mov     rcx, rbx
0x180045cec  mov     rax, [rax]
0x180045cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cf4  mov     eax, esi
0x180045cf6  lock xadd [rbx+0Ch], eax
0x180045cfb  add     eax, esi
0x180045cfd  jnz     short loc_180045D0E
0x180045cff  mov     rax, [rbx]
0x180045d02  mov     rcx, rbx
0x180045d05  mov     rax, [rax+8]
0x180045d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d0e  xor     r8d, r8d; pcbe
0x180045d11  mov     rdx, [rdi+18h]; pv
0x180045d15  lea     rcx, ?CompleteWorker@ClientOperationCompleter@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180045d1c  call    cs:__imp_CreateThreadpoolWork
0x180045d23  nop     dword ptr [rax+rax+00h]
0x180045d28  mov     rsi, rax
0x180045d2b  mov     rbp, [rdi+10h]
0x180045d2f  test    rbp, rbp
0x180045d32  jz      short loc_180045D5F
0x180045d34  call    cs:__imp_GetLastError
0x180045d3b  nop     dword ptr [rax+rax+00h]
0x180045d40  mov     ebx, eax
0x180045d42  mov     rcx, rbp; pwk
0x180045d45  call    cs:__imp_CloseThreadpoolWork
0x180045d4c  nop     dword ptr [rax+rax+00h]
0x180045d51  mov     ecx, ebx; dwErrCode
0x180045d53  call    cs:__imp_SetLastError
0x180045d5a  nop     dword ptr [rax+rax+00h]
0x180045d5f  mov     [rdi+10h], rsi
0x180045d63  mov     rcx, [rsp+58h]; this
0x180045d68  test    rsi, rsi
0x180045d6b  jz      short loc_180045D7E
0x180045d6d  mov     rax, rdi
0x180045d70  mov     rbx, [rsp+58h+arg_10]
0x180045d75  add     rsp, 40h
0x180045d79  pop     rdi
0x180045d7a  pop     rsi
0x180045d7b  pop     rbp
0x180045d7c  retn
0x180045d7e  lea     r8, aOnecoreVmCompu_24; "onecore\\vm\\compute\\dll\\lib\\core\\C"...
0x180045d85  mov     edx, 171h; void *
0x180045d8a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
