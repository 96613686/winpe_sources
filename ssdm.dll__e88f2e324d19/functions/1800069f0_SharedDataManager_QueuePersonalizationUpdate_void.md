# SharedDataManager::QueuePersonalizationUpdate(void)

- ea: `0x1800069f0`
- end: `0x180006b1a`
- name: `?QueuePersonalizationUpdate@SharedDataManager@@AEAAXXZ`
- size: `298`
- prototype: `void __fastcall(SharedDataManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180005ec0`

## callees

- `0x180002a88`
- `0x180004c60`
- `0x180005b40`
- `0x1800069f0`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006b07`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ac5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ae3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ae3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180006adb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180006adb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180006ad2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180006ad2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180006af0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180006af0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180006ab3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180006ab3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SharedDataManager::QueuePersonalizationUpdate(struct _TP_WORK **this)
{
  struct HrtfPersonalizationParams *PersonalizationParamsFromDefaultConfiguration; // rsi
  HrtfPersonalizationParams *v3; // rdi
  struct _TP_WORK ***v4; // rax
  struct _TP_WORK ***v5; // rbx
  struct _TP_WORK *v6; // r14
  struct _TP_WORK *v7; // r15
  volatile signed __int32 *v8; // rsi
  struct _TP_WORK *ThreadpoolWork; // rsi
  struct _TP_WORK *v10; // r14
  DWORD LastError; // ebx

  PersonalizationParamsFromDefaultConfiguration = SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration((SharedDataManager *)this);
  v3 = PersonalizationParamsFromDefaultConfiguration;
  *(_DWORD *)PersonalizationParamsFromDefaultConfiguration = *((_DWORD *)this[6] + 2);
  v4 = (struct _TP_WORK ***)operator new(0x20u);
  v5 = v4;
  if ( v4 )
  {
    *v4 = this;
    v3 = 0;
    v4[1] = (struct _TP_WORK **)PersonalizationParamsFromDefaultConfiguration;
    v4[2] = 0;
    v4[3] = 0;
    v6 = this[7];
    v7 = this[6];
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)v6 + 2);
    v8 = (volatile signed __int32 *)v4[3];
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    v5[3] = (struct _TP_WORK **)v6;
    v5[2] = (struct _TP_WORK **)v7;
  }
  else
  {
    v5 = 0;
  }
  ThreadpoolWork = CreateThreadpoolWork(lambda_a106477e8615dd5396f31ef56e820506_::_lambda_invoker_cdecl_, v5, 0);
  v10 = this[15];
  if ( v10 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v10, 0);
    CloseThreadpoolWork(v10);
    SetLastError(LastError);
  }
  this[15] = ThreadpoolWork;
  SubmitThreadpoolWork(ThreadpoolWork);
  if ( v3 )
  {
    HrtfPersonalizationParams::~HrtfPersonalizationParams(v3);
    operator delete(v3);
  }
}

```

## disassembly

```asm
0x1800069f0  push    rbx
0x1800069f2  push    rbp
0x1800069f3  push    rsi
0x1800069f4  push    rdi
0x1800069f5  push    r14
0x1800069f7  push    r15
0x1800069f9  sub     rsp, 28h
0x1800069fd  mov     rbp, rcx
0x180006a00  call    ?GetPersonalizationParamsFromDefaultConfiguration@SharedDataManager@@AEAAPEAUHrtfPersonalizationParams@@XZ; SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration(void)
0x180006a05  mov     rsi, rax
0x180006a08  mov     rdi, rax
0x180006a0b  mov     [rsp+58h+arg_0], rax
0x180006a10  mov     rdx, [rbp+30h]
0x180006a14  mov     r8d, [rdx+8]
0x180006a18  mov     [rax], r8d
0x180006a1b  mov     ecx, 20h ; ' '; Size
0x180006a20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a25  mov     rbx, rax
0x180006a28  mov     [rsp+58h+arg_0], rax
0x180006a2d  test    rax, rax
0x180006a30  jz      short loc_180006AA4
0x180006a32  mov     [rax], rbp
0x180006a35  xor     edi, edi
0x180006a37  mov     [rsp+58h+arg_0], rdi
0x180006a3c  mov     [rax+8], rsi
0x180006a40  mov     [rax+10h], rdi
0x180006a44  mov     [rax+18h], rdi
0x180006a48  mov     r14, [rbp+38h]
0x180006a4c  mov     r15, [rbp+30h]
0x180006a50  test    r14, r14
0x180006a53  jz      short loc_180006A5A
0x180006a55  lock inc dword ptr [r14+8]
0x180006a5a  mov     rsi, [rax+18h]
0x180006a5e  test    rsi, rsi
0x180006a61  jz      short loc_180006A9A
0x180006a63  or      eax, 0FFFFFFFFh
0x180006a66  lock xadd [rsi+8], eax
0x180006a6b  cmp     eax, 1
0x180006a6e  jnz     short loc_180006A9A
0x180006a70  mov     rax, [rsi]
0x180006a73  mov     rcx, rsi
0x180006a76  mov     rax, [rax]
0x180006a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a7e  or      eax, 0FFFFFFFFh
0x180006a81  lock xadd [rsi+0Ch], eax
0x180006a86  cmp     eax, 1
0x180006a89  jnz     short loc_180006A9A
0x180006a8b  mov     rax, [rsi]
0x180006a8e  mov     rcx, rsi
0x180006a91  mov     rax, [rax+8]
0x180006a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9a  mov     [rbx+18h], r14
0x180006a9e  mov     [rbx+10h], r15
0x180006aa2  jmp     short loc_180006AA6
0x180006aa4  xor     ebx, ebx
0x180006aa6  xor     r8d, r8d; pcbe
0x180006aa9  mov     rdx, rbx; pv
0x180006aac  lea     rcx, _lambda_a106477e8615dd5396f31ef56e820506____lambda_invoker_cdecl_; pfnwk
0x180006ab3  call    cs:__imp_CreateThreadpoolWork
0x180006ab9  mov     rsi, rax
0x180006abc  mov     r14, [rbp+78h]
0x180006ac0  test    r14, r14
0x180006ac3  jz      short loc_180006AE9
0x180006ac5  call    cs:__imp_GetLastError
0x180006acb  mov     ebx, eax
0x180006acd  xor     edx, edx; fCancelPendingCallbacks
0x180006acf  mov     rcx, r14; pwk
0x180006ad2  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180006ad8  mov     rcx, r14; pwk
0x180006adb  call    cs:__imp_CloseThreadpoolWork
0x180006ae1  mov     ecx, ebx; dwErrCode
0x180006ae3  call    cs:__imp_SetLastError
0x180006ae9  mov     [rbp+78h], rsi
0x180006aed  mov     rcx, rsi; pwk
0x180006af0  call    cs:__imp_SubmitThreadpoolWork
0x180006af6  nop
0x180006af7  test    rdi, rdi
0x180006afa  jz      short loc_180006B0D
0x180006afc  mov     rcx, rdi; this
0x180006aff  call    ??1HrtfPersonalizationParams@@QEAA@XZ; HrtfPersonalizationParams::~HrtfPersonalizationParams(void)
0x180006b04  mov     rcx, rdi
0x180006b07  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b0d  add     rsp, 28h
0x180006b11  pop     r15
0x180006b13  pop     r14
0x180006b15  pop     rdi
0x180006b16  pop     rsi
0x180006b17  pop     rbp
0x180006b18  pop     rbx
0x180006b19  retn
```
