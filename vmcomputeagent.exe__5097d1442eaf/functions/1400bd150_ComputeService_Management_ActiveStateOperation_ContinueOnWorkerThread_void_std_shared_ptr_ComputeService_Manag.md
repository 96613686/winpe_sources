# ComputeService::Management::ActiveStateOperation::ContinueOnWorkerThread(void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation))

- ea: `0x1400bd150`
- end: `0x1400bd33b`
- name: `?ContinueOnWorkerThread@ActiveStateOperation@Management@ComputeService@@QEAAXP6AXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@V123@@Z@Z`
- size: `491`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400878e0`
- `0x140089490`
- `0x14008b220`
- `0x14008d9c0`

## callees

- `0x14000ddac`
- `0x14003407c`
- `0x14004199c`
- `0x1400bd150`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400bd1e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400bd1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bd1ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bd1ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400bd1d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400bd1d9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400bd279`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400bd279`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400bd1b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400bd1b9`

## string_xrefs

- `0x1400bd298`: `onecore\vm\compute\management\shared\compute\StateOperation.h`
- `0x1400bd2b5`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x1400bd2d2`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x1400bd2ef`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x1400bd30c`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x1400bd329`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`

## pseudocode

```c
void __fastcall ComputeService::Management::ActiveStateOperation::ContinueOnWorkerThread(PVOID *a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  PTP_WORK ThreadpoolWork; // rax
  const char *v7; // r9
  struct _TP_WORK *v8; // rbp
  PTP_WORK v9; // r14
  DWORD LastError; // ebx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = *(_QWORD *)*a1;
  if ( *(_DWORD *)(v4 + 24) != 1 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x80070032LL,
      v13);
  if ( *(_QWORD *)(v4 + 416) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x8007139FLL,
      v13);
  v5 = *(_QWORD *)(v4 + 40);
  if ( !v5 || !*(_DWORD *)(v5 + 8) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x80070032LL,
      v13);
  if ( !*(_DWORD *)(v4 + 432) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x8007139FLL,
      v13);
  if ( !*(_QWORD *)(v4 + 408) )
  {
    ThreadpoolWork = CreateThreadpoolWork(ComputeService::Management::ActiveStateOperation::ThreadpoolThunk, *a1, 0);
    v8 = *(struct _TP_WORK **)(v4 + 408);
    v9 = ThreadpoolWork;
    if ( v8 )
    {
      LastError = GetLastError();
      CloseThreadpoolWork(v8);
      SetLastError(LastError);
    }
    *(_QWORD *)(v4 + 408) = v9;
    if ( !*(_QWORD *)(*(_QWORD *)*a1 + 408LL) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
        v7);
  }
  *(_QWORD *)(*(_QWORD *)*a1 + 416LL) = a2;
  wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(*(_QWORD *)*a1 + 320LL));
  v11 = *(_QWORD *)(*(_QWORD *)*a1 + 424LL);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 48LL))(v11);
  *(_DWORD *)(*(_QWORD *)*a1 + 132LL) |= 1u;
  v12 = *(_QWORD *)*a1;
  if ( !*(_DWORD *)(v12 + 432) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\StateOperation.h",
      (const char *)0x8007139FLL,
      v13);
  *(_BYTE *)(v12 + 120) = 1;
  *(_DWORD *)(*(_QWORD *)*a1 + 124LL) = 0;
  SubmitThreadpoolWork(*(PTP_WORK *)(*(_QWORD *)*a1 + 408LL));
  *a1 = 0;
}

```

## disassembly

```asm
0x1400bd150  push    rbx
0x1400bd152  push    rbp
0x1400bd153  push    rsi
0x1400bd154  push    rdi
0x1400bd155  push    r14
0x1400bd157  push    r15
0x1400bd159  sub     rsp, 28h
0x1400bd15d  mov     r15, rdx
0x1400bd160  mov     rdi, rcx
0x1400bd163  mov     rdx, [rcx]; pv
0x1400bd166  mov     rsi, [rdx]
0x1400bd169  cmp     dword ptr [rsi+18h], 1
0x1400bd16d  jnz     loc_1400BD2CD
0x1400bd173  cmp     qword ptr [rsi+1A0h], 0
0x1400bd17b  jnz     loc_1400BD2EA
0x1400bd181  mov     rax, [rsi+28h]
0x1400bd185  test    rax, rax
0x1400bd188  jz      loc_1400BD2B0
0x1400bd18e  cmp     dword ptr [rax+8], 0
0x1400bd192  jz      loc_1400BD2B0
0x1400bd198  cmp     dword ptr [rsi+1B0h], 0
0x1400bd19f  jz      loc_1400BD307
0x1400bd1a5  cmp     qword ptr [rsi+198h], 0
0x1400bd1ad  jnz     short loc_1400BD202
0x1400bd1af  xor     r8d, r8d; pcbe
0x1400bd1b2  lea     rcx, ?ThreadpoolThunk@ActiveStateOperation@Management@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1400bd1b9  call    cs:__imp_CreateThreadpoolWork
0x1400bd1bf  mov     rbp, [rsi+198h]
0x1400bd1c6  mov     r14, rax
0x1400bd1c9  test    rbp, rbp
0x1400bd1cc  jz      short loc_1400BD1E7
0x1400bd1ce  call    cs:__imp_GetLastError
0x1400bd1d4  mov     rcx, rbp; pwk
0x1400bd1d7  mov     ebx, eax
0x1400bd1d9  call    cs:__imp_CloseThreadpoolWork
0x1400bd1df  mov     ecx, ebx; dwErrCode
0x1400bd1e1  call    cs:__imp_SetLastError
0x1400bd1e7  mov     [rsi+198h], r14
0x1400bd1ee  mov     rax, [rdi]
0x1400bd1f1  mov     rcx, [rax]
0x1400bd1f4  cmp     qword ptr [rcx+198h], 0
0x1400bd1fc  jz      loc_1400BD324
0x1400bd202  mov     rax, [rdi]
0x1400bd205  mov     rcx, [rax]
0x1400bd208  mov     [rcx+1A0h], r15
0x1400bd20f  mov     rax, [rdi]
0x1400bd212  mov     rcx, [rax]
0x1400bd215  add     rcx, 140h; this
0x1400bd21c  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400bd221  mov     rax, [rdi]
0x1400bd224  mov     rcx, [rax]
0x1400bd227  mov     rcx, [rcx+1A8h]
0x1400bd22e  test    rcx, rcx
0x1400bd231  jz      short loc_1400BD23F
0x1400bd233  mov     rax, [rcx]
0x1400bd236  mov     rax, [rax+30h]
0x1400bd23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400bd23f  mov     rax, [rdi]
0x1400bd242  mov     rcx, [rax]
0x1400bd245  or      dword ptr [rcx+84h], 1
0x1400bd24c  mov     rax, [rdi]
0x1400bd24f  mov     rcx, [rax]
0x1400bd252  cmp     dword ptr [rcx+1B0h], 0
0x1400bd259  jz      short loc_1400BD293
0x1400bd25b  mov     byte ptr [rcx+78h], 1
0x1400bd25f  mov     rax, [rdi]
0x1400bd262  mov     rcx, [rax]
0x1400bd265  mov     dword ptr [rcx+7Ch], 0
0x1400bd26c  mov     rax, [rdi]
0x1400bd26f  mov     rcx, [rax]
0x1400bd272  mov     rcx, [rcx+198h]; pwk
0x1400bd279  call    cs:__imp_SubmitThreadpoolWork
0x1400bd27f  mov     qword ptr [rdi], 0
0x1400bd286  add     rsp, 28h
0x1400bd28a  pop     r15
0x1400bd28c  pop     r14
0x1400bd28e  pop     rdi
0x1400bd28f  pop     rsi
0x1400bd290  pop     rbp
0x1400bd291  pop     rbx
0x1400bd292  retn
0x1400bd293  mov     rcx, [rsp+58h]; this
0x1400bd298  lea     r8, aOnecoreVmCompu_43; "onecore\\vm\\compute\\management\\share"...
0x1400bd29f  mov     r9d, 8007139Fh; char *
0x1400bd2a5  mov     edx, 1C6h; void *
0x1400bd2aa  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400bd2b0  mov     rcx, [rsp+58h]; this
0x1400bd2b5  lea     r8, aOnecoreVmCompu_47; "onecore\\vm\\compute\\management\\share"...
0x1400bd2bc  mov     r9d, 80070032h; char *
0x1400bd2c2  mov     edx, 198h; void *
0x1400bd2c7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400bd2cd  mov     rcx, [rsp+58h]; this
0x1400bd2d2  lea     r8, aOnecoreVmCompu_47; "onecore\\vm\\compute\\management\\share"...
0x1400bd2d9  mov     r9d, 80070032h; char *
0x1400bd2df  mov     edx, 193h; void *
0x1400bd2e4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400bd2ea  mov     rcx, [rsp+58h]; this
0x1400bd2ef  lea     r8, aOnecoreVmCompu_47; "onecore\\vm\\compute\\management\\share"...
0x1400bd2f6  mov     r9d, 8007139Fh; char *
0x1400bd2fc  mov     edx, 195h; void *
0x1400bd301  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400bd307  mov     rcx, [rsp+58h]; this
0x1400bd30c  lea     r8, aOnecoreVmCompu_47; "onecore\\vm\\compute\\management\\share"...
0x1400bd313  mov     r9d, 8007139Fh; char *
0x1400bd319  mov     edx, 19Bh; void *
0x1400bd31e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400bd324  mov     rcx, [rsp+58h]; this
0x1400bd329  lea     r8, aOnecoreVmCompu_47; "onecore\\vm\\compute\\management\\share"...
0x1400bd330  mov     edx, 1A2h; void *
0x1400bd335  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
