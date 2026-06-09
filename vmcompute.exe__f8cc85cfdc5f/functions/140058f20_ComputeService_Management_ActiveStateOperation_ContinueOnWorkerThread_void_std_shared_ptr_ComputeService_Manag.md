# ComputeService::Management::ActiveStateOperation::ContinueOnWorkerThread(void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation))

- ea: `0x140058f20`
- end: `0x14005911d`
- name: `?ContinueOnWorkerThread@ActiveStateOperation@Management@ComputeService@@QEAAXP6AXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@V123@@Z@Z`
- size: `509`
- prototype: ``
- caller_count: `27`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140021800`
- `0x140071700`
- `0x140078f30`
- `0x140079640`
- `0x140079e40`
- `0x14007b440`
- `0x14007b870`
- `0x14007c000`
- `0x14007c490`
- `0x1400b0ac0`
- `0x1400b2760`
- `0x1400b2e10`
- `0x1400b39b0`
- `0x1400c8740`
- `0x1400caf40`
- `0x140100950`
- `0x1401015e0`
- `0x140107c80`
- `0x140115120`
- `0x140124e60`
- `0x140171a90`
- `0x140172540`
- `0x1401a72c0`
- `0x1401cfd20`
- `0x1401d0070`
- `0x1401d0360`
- `0x1401d3c80`

## callees

- `0x140058f20`
- `0x140059148`
- `0x14007fe20`
- `0x14007fea8`
- `0x140080180`
- `0x1400a200c`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140059001`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140059001`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400590d9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400590d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140058fd9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140058fd9`

## string_xrefs

- `0x140058f49`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x140058f70`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x140058fad`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x140059033`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x140059105`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`
- `0x1400590a3`: `onecore\vm\compute\management\shared\compute\StateOperation.h`

## pseudocode

```c
void __fastcall ComputeService::Management::ActiveStateOperation::ContinueOnWorkerThread(PVOID *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 v5; // rax
  PTP_WORK ThreadpoolWork; // rax
  const char *v7; // r9
  struct _TP_WORK *v8; // rsi
  PTP_WORK v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v14; // [rsp+40h] [rbp+8h] BYREF

  v4 = *(_QWORD *)*a1;
  if ( *(_DWORD *)(v4 + 24) != 1 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x80070032LL,
      v12);
  if ( *(_QWORD *)(v4 + 416) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x8007139FLL,
      v12);
  v5 = *(_QWORD *)(v4 + 40);
  if ( !v5 || !*(_DWORD *)(v5 + 8) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x80070032LL,
      v12);
  if ( !*(_DWORD *)(v4 + 432) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x8007139FLL,
      v12);
  if ( !*(_QWORD *)(v4 + 408) )
  {
    ThreadpoolWork = CreateThreadpoolWork(ComputeService::Management::ActiveStateOperation::ThreadpoolThunk, *a1, 0);
    v8 = *(struct _TP_WORK **)(v4 + 408);
    v9 = ThreadpoolWork;
    if ( v8 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
      CloseThreadpoolWork(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
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
  v10 = *(_QWORD *)(*(_QWORD *)*a1 + 424LL);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(v10);
  *(_DWORD *)(*(_QWORD *)*a1 + 132LL) |= 1u;
  v11 = *(_QWORD *)*a1;
  if ( !*(_DWORD *)(v11 + 432) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\StateOperation.h",
      (const char *)0x8007139FLL,
      v12);
  *(_BYTE *)(v11 + 120) = 1;
  *(_DWORD *)(*(_QWORD *)*a1 + 124LL) = 0;
  SubmitThreadpoolWork(*(PTP_WORK *)(*(_QWORD *)*a1 + 408LL));
  *a1 = 0;
}

```

## disassembly

```asm
0x140058f20  mov     [rsp+arg_8], rbx
0x140058f25  mov     [rsp+arg_10], rbp
0x140058f2a  push    rsi
0x140058f2b  push    rdi
0x140058f2c  push    r14; int
0x140058f2e  sub     rsp, 20h
0x140058f32  mov     r14, rdx
0x140058f35  mov     rbx, rcx
0x140058f38  mov     rdx, [rcx]; pv
0x140058f3b  mov     rdi, [rdx]
0x140058f3e  cmp     dword ptr [rdi+18h], 1
0x140058f42  jz      short loc_140058F61
0x140058f44  mov     rcx, [rsp+38h]; this
0x140058f49  lea     r8, aOnecoreVmCompu_125; "onecore\\vm\\compute\\management\\share"...
0x140058f50  mov     r9d, 80070032h; char *
0x140058f56  mov     edx, 193h; void *
0x140058f5b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x140058f61  cmp     qword ptr [rdi+1A0h], 0
0x140058f69  jz      short loc_140058F88
0x140058f6b  mov     rcx, [rsp+38h]; this
0x140058f70  lea     r8, aOnecoreVmCompu_125; "onecore\\vm\\compute\\management\\share"...
0x140058f77  mov     r9d, 8007139Fh; char *
0x140058f7d  mov     edx, 195h; void *
0x140058f82  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x140058f88  mov     rax, [rdi+28h]
0x140058f8c  test    rax, rax
0x140058f8f  jz      loc_140059100
0x140058f95  cmp     dword ptr [rax+8], 0
0x140058f99  jz      loc_140059100
0x140058f9f  cmp     dword ptr [rdi+1B0h], 0
0x140058fa6  jnz     short loc_140058FC5
0x140058fa8  mov     rcx, [rsp+38h]; this
0x140058fad  lea     r8, aOnecoreVmCompu_125; "onecore\\vm\\compute\\management\\share"...
0x140058fb4  mov     r9d, 8007139Fh; char *
0x140058fba  mov     edx, 19Bh; void *
0x140058fbf  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x140058fc5  cmp     qword ptr [rdi+198h], 0
0x140058fcd  jnz     short loc_140059045
0x140058fcf  xor     r8d, r8d; pcbe
0x140058fd2  lea     rcx, ?ThreadpoolThunk@ActiveStateOperation@Management@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140058fd9  call    cs:__imp_CreateThreadpoolWork
0x140058fe0  nop     dword ptr [rax+rax+00h]
0x140058fe5  mov     rsi, [rdi+198h]
0x140058fec  mov     rbp, rax
0x140058fef  test    rsi, rsi
0x140058ff2  jz      short loc_140059017
0x140058ff4  lea     rcx, [rsp+38h+arg_0]; this
0x140058ff9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140058ffe  mov     rcx, rsi; pwk
0x140059001  call    cs:__imp_CloseThreadpoolWork
0x140059008  nop     dword ptr [rax+rax+00h]
0x14005900d  lea     rcx, [rsp+38h+arg_0]; this
0x140059012  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140059017  mov     [rdi+198h], rbp
0x14005901e  mov     rax, [rbx]
0x140059021  mov     rcx, [rax]
0x140059024  cmp     qword ptr [rcx+198h], 0
0x14005902c  jnz     short loc_140059045
0x14005902e  mov     rcx, [rsp+38h]; this
0x140059033  lea     r8, aOnecoreVmCompu_125; "onecore\\vm\\compute\\management\\share"...
0x14005903a  mov     edx, 1A2h; void *
0x14005903f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140059045  mov     rax, [rbx]
0x140059048  mov     rcx, [rax]
0x14005904b  mov     [rcx+1A0h], r14
0x140059052  mov     rax, [rbx]
0x140059055  mov     rcx, [rax]
0x140059058  add     rcx, 140h; this
0x14005905f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140059064  mov     rax, [rbx]
0x140059067  mov     rcx, [rax]
0x14005906a  mov     rcx, [rcx+1A8h]
0x140059071  test    rcx, rcx
0x140059074  jz      short loc_140059082
0x140059076  mov     rax, [rcx]
0x140059079  mov     rax, [rax+30h]
0x14005907d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059082  mov     rax, [rbx]
0x140059085  mov     rcx, [rax]
0x140059088  or      dword ptr [rcx+84h], 1
0x14005908f  mov     rax, [rbx]
0x140059092  mov     rcx, [rax]
0x140059095  cmp     dword ptr [rcx+1B0h], 0
0x14005909c  jnz     short loc_1400590BB
0x14005909e  mov     rcx, [rsp+38h]; this
0x1400590a3  lea     r8, aOnecoreVmCompu_96; "onecore\\vm\\compute\\management\\share"...
0x1400590aa  mov     r9d, 8007139Fh; char *
0x1400590b0  mov     edx, 1C6h; void *
0x1400590b5  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1400590bb  mov     byte ptr [rcx+78h], 1
0x1400590bf  mov     rax, [rbx]
0x1400590c2  mov     rcx, [rax]
0x1400590c5  mov     dword ptr [rcx+7Ch], 0
0x1400590cc  mov     rax, [rbx]
0x1400590cf  mov     rcx, [rax]
0x1400590d2  mov     rcx, [rcx+198h]; pwk
0x1400590d9  call    cs:__imp_SubmitThreadpoolWork
0x1400590e0  nop     dword ptr [rax+rax+00h]
0x1400590e5  mov     rbp, [rsp+38h+arg_10]
0x1400590ea  mov     qword ptr [rbx], 0
0x1400590f1  mov     rbx, [rsp+38h+arg_8]
0x1400590f6  add     rsp, 20h
0x1400590fa  pop     r14
0x1400590fc  pop     rdi
0x1400590fd  pop     rsi
0x1400590fe  retn
0x140059100  mov     rcx, [rsp+38h]; this
0x140059105  lea     r8, aOnecoreVmCompu_125; "onecore\\vm\\compute\\management\\share"...
0x14005910c  mov     r9d, 80070032h; char *
0x140059112  mov     edx, 198h; void *
0x140059117  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
