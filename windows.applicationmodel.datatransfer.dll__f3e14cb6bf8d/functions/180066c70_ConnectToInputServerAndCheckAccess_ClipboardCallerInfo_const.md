# ConnectToInputServerAndCheckAccess(ClipboardCallerInfo const &)

- ea: `0x180066c70`
- end: `0x1800670d7`
- name: `?ConnectToInputServerAndCheckAccess@@YA_NAEBUClipboardCallerInfo@@@Z`
- size: `1127`
- prototype: `bool __fastcall(const struct ClipboardCallerInfo *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800671c0`

## callees

- `0x1800054c0`
- `0x180005504`
- `0x18005679c`
- `0x1800660ec`
- `0x180066248`
- `0x1800663bc`
- `0x1800664bc`
- `0x1800666cc`
- `0x180066c70`
- `0x180067b7c`
- `0x18007bf8c`
- `0x18007c4d8`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180066e09`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180066e09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066e11`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180066ef8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180066f92`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180066ef8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180066f92`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180066e3b`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180066e3b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180066f23`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180066f23`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180066f11`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180066f11`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
bool __fastcall ConnectToInputServerAndCheckAccess(const struct ClipboardCallerInfo *a1)
{
  char *v2; // rdi
  void *v3; // rax
  Execution::ExecutionServices *v4; // rax
  Execution::ExecutionServices *v5; // rbx
  int v6; // r14d
  __int64 v7; // rax
  volatile signed __int32 *v8; // rcx
  DWORD ThreadId; // ebx
  volatile signed __int32 *v10; // rcx
  volatile signed __int32 *v11; // rbx
  void *v12; // rcx
  volatile signed __int32 *v13; // rbx
  int v14; // eax
  bool v15; // bl
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rax
  int lpdwindex; // [rsp+20h] [rbp-69h]
  int lpdwindexa; // [rsp+20h] [rbp-69h]
  int lpdwindexb; // [rsp+20h] [rbp-69h]
  _QWORD v23[2]; // [rsp+30h] [rbp-59h] BYREF
  __int128 v24; // [rsp+40h] [rbp-49h] BYREF
  HANDLE pHandles[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v26; // [rsp+60h] [rbp-29h] BYREF
  __int64 v27; // [rsp+70h] [rbp-19h] BYREF
  volatile signed __int32 *v28; // [rsp+78h] [rbp-11h]
  _QWORD *v29; // [rsp+80h] [rbp-9h]
  __int64 *v30; // [rsp+88h] [rbp-1h]
  __int128 *v31; // [rsp+90h] [rbp+7h]
  char *v32; // [rsp+98h] [rbp+Fh]
  char *v33; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v35; // [rsp+F8h] [rbp+6Fh] BYREF
  char *dwindex; // [rsp+100h] [rbp+77h] BYREF
  __int64 v37; // [rsp+108h] [rbp+7Fh] BYREF

  v23[0] = 0;
  v2 = (char *)operator new(0x28u);
  dwindex = v2;
  *(_OWORD *)v2 = 0;
  *((_DWORD *)v2 + 2) = 1;
  *((_DWORD *)v2 + 3) = 1;
  *(_QWORD *)v2 = &std::_Ref_count_obj2<CoreUISession>::`vftable';
  pHandles[0] = v2 + 16;
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 4) = 0;
  v3 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v3 )
  {
    v5 = 0;
    goto LABEL_6;
  }
  v4 = (Execution::ExecutionServices *)Execution::ExecutionServices::ExecutionServices(v3, 0);
  v5 = v4;
  if ( !v4 )
  {
LABEL_6:
    v6 = -2147024882;
    goto LABEL_7;
  }
  v6 = Execution::ExecutionServices::Init(v4);
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(Execution::ExecutionServices *))(*(_QWORD *)v5 + 8LL))(v5);
    *((_QWORD *)v2 + 4) = v5;
    v6 = 0;
  }
LABEL_7:
  if ( v5 )
    (*(void (__fastcall **)(Execution::ExecutionServices *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\private\\base\\inc\\CoreUIMessagingInterop.h",
      (const char *)(unsigned int)v6,
      lpdwindex);
  v32 = v2 + 16;
  v33 = v2;
  if ( v2 != (char *)-16LL )
  {
    v7 = *((_QWORD *)v2 + 3);
    if ( !v7 || !*(_DWORD *)(v7 + 8) )
    {
      _InterlockedAdd((volatile signed __int32 *)v2 + 2, 1u);
      _InterlockedAdd((volatile signed __int32 *)v2 + 3, 1u);
      *((_QWORD *)v2 + 2) = v2 + 16;
      v8 = (volatile signed __int32 *)*((_QWORD *)v2 + 3);
      *((_QWORD *)v2 + 3) = v2;
      if ( v8 && _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      if ( !_InterlockedDecrement((volatile signed __int32 *)v2 + 2) )
      {
        (**(void (__fastcall ***)(void *))v2)(v2);
        if ( !_InterlockedDecrement((volatile signed __int32 *)v2 + 3) )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
      }
    }
  }
  Microsoft::WRL::Details::Make<WaitForSessionConnect,>(&v37);
  *(_QWORD *)&v24 = v23;
  *((_QWORD *)&v24 + 1) = &v37;
  ThreadId = GetThreadId(*(HANDLE *)(*((_QWORD *)v2 + 4) + 128LL));
  if ( ThreadId == GetCurrentThreadId() )
  {
    lambda_f479fcabb570c85bc961811b2db403b6_::operator()(&v24);
  }
  else
  {
    Event<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::Event<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>(&v24);
    v26 = 0;
    __ExceptionPtrCreate(&v26);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( *((_QWORD *)&v24 + 1) )
    {
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 1u);
      v10 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    }
    v27 = v24;
    v28 = v10;
    v29 = v23;
    v30 = &v37;
    v31 = &v26;
    CoreUISession::ExecuteAsync__lambda_3d7fe68d703e265bdf060a71098eb542___(v2 + 16, &v27);
    v11 = v28;
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    LODWORD(dwindex) = 0;
    if ( (_QWORD)v24 )
      v12 = *(void **)v24;
    else
      v12 = 0;
    pHandles[0] = v12;
    if ( CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex) == -2147417835 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\private\\base\\inc\\CoreUIMessagingInterop.h",
        (const char *)0x80010115LL,
        lpdwindexa);
    if ( __ExceptionPtrToBool(&v26) )
    {
      v19 = std::exception_ptr::exception_ptr((std::exception_ptr *)pHandles, (const struct std::exception_ptr *)&v26);
      std::rethrow_exception(v19);
    }
    __ExceptionPtrDestroy(&v26);
    v13 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( *((_QWORD *)&v24 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
  }
  LODWORD(dwindex) = 0;
  pHandles[0] = *(HANDLE *)(v37 + 24);
  if ( CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex) == -2147417835 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\private\\base\\inc\\CoreUIMessagingInterop.h",
      (const char *)0x80010115LL,
      lpdwindexb);
  v35 = 0;
  v24 = *(_OWORD *)a1;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, int *))(*(_QWORD *)v23[0] + 424LL))(v23[0], &v24, &v35);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboardpolicy.cpp",
      (const char *)(unsigned int)v14,
      lpdwindexb);
  v15 = v35 == 1;
  v16 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( !_InterlockedDecrement((volatile signed __int32 *)v2 + 2) )
  {
    (**(void (__fastcall ***)(void *))v2)(v2);
    if ( !_InterlockedDecrement((volatile signed __int32 *)v2 + 3) )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  v17 = v23[0];
  if ( v23[0] )
  {
    v23[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return v15;
}

```

## disassembly

```asm
0x180066c70  push    rbp
0x180066c72  push    rbx
0x180066c73  push    rsi
0x180066c74  push    rdi
0x180066c75  push    r13
0x180066c77  push    r14
0x180066c79  push    r15
0x180066c7b  lea     rbp, [rsp-27h]
0x180066c80  sub     rsp, 0B0h
0x180066c87  mov     r15, rcx
0x180066c8a  mov     [rbp+57h+var_B0], 0
0x180066c92  mov     ecx, 28h ; '('; Size
0x180066c97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066c9c  mov     rdi, rax
0x180066c9f  mov     [rbp+57h+dwindex], rax
0x180066ca3  xorps   xmm0, xmm0
0x180066ca6  movups  xmmword ptr [rax], xmm0
0x180066ca9  mov     r13d, 1
0x180066caf  mov     [rax+8], r13d
0x180066cb3  mov     [rax+0Ch], r13d
0x180066cb7  lea     rax, ??_7?$_Ref_count_obj2@VCoreUISession@@@std@@6B@; const std::_Ref_count_obj2<CoreUISession>::`vftable'
0x180066cbe  mov     [rdi], rax
0x180066cc1  lea     rsi, [rdi+10h]
0x180066cc5  mov     [rbp+57h+pHandles], rsi
0x180066cc9  mov     qword ptr [rsi], 0
0x180066cd0  mov     qword ptr [rsi+8], 0
0x180066cd8  mov     qword ptr [rsi+10h], 0
0x180066ce0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180066ce7  mov     ecx, 90h; unsigned __int64
0x180066cec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180066cf1  test    rax, rax
0x180066cf4  jz      short loc_180066D2F
0x180066cf6  xor     edx, edx
0x180066cf8  mov     rcx, rax
0x180066cfb  call    ??0ExecutionServices@Execution@@QEAA@W4ComApartment@01@@Z; Execution::ExecutionServices::ExecutionServices(Execution::ExecutionServices::ComApartment)
0x180066d00  mov     rbx, rax
0x180066d03  test    rax, rax
0x180066d06  jz      short loc_180066D31
0x180066d08  mov     rcx, rax; this
0x180066d0b  call    ?Init@ExecutionServices@Execution@@IEAAJXZ; Execution::ExecutionServices::Init(void)
0x180066d10  mov     r14d, eax
0x180066d13  test    eax, eax
0x180066d15  js      short loc_180066D37
0x180066d17  mov     rax, [rbx]
0x180066d1a  mov     rcx, rbx
0x180066d1d  mov     rax, [rax+8]
0x180066d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d26  mov     [rsi+10h], rbx
0x180066d2a  xor     r14d, r14d
0x180066d2d  jmp     short loc_180066D37
0x180066d2f  xor     ebx, ebx
0x180066d31  mov     r14d, 8007000Eh
0x180066d37  test    rbx, rbx
0x180066d3a  jz      short loc_180066D4C
0x180066d3c  mov     rax, [rbx]
0x180066d3f  mov     rcx, rbx
0x180066d42  mov     rax, [rax+10h]
0x180066d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d4b  nop
0x180066d4c  mov     rcx, [rbp+5Fh]; this
0x180066d50  test    r14d, r14d
0x180066d53  js      loc_180067082
0x180066d59  mov     [rbp+57h+var_48], rsi
0x180066d5d  mov     [rbp+57h+var_40], rdi
0x180066d61  or      r14d, 0FFFFFFFFh
0x180066d65  test    rsi, rsi
0x180066d68  jz      short loc_180066DE4
0x180066d6a  mov     rax, [rsi+8]
0x180066d6e  test    rax, rax
0x180066d71  jz      short loc_180066D79
0x180066d73  cmp     dword ptr [rax+8], 0
0x180066d77  jnz     short loc_180066DE4
0x180066d79  lock add [rdi+8], r13d
0x180066d7e  lock add [rdi+0Ch], r13d
0x180066d83  mov     [rsi], rsi
0x180066d86  mov     rcx, [rsi+8]
0x180066d8a  mov     [rsi+8], rdi
0x180066d8e  test    rcx, rcx
0x180066d91  jz      short loc_180066DAC
0x180066d93  mov     eax, r14d
0x180066d96  lock xadd [rcx+0Ch], eax
0x180066d9b  add     eax, r14d
0x180066d9e  jnz     short loc_180066DAC
0x180066da0  mov     rax, [rcx]
0x180066da3  mov     rax, [rax+8]
0x180066da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066dac  mov     eax, r14d
0x180066daf  lock xadd [rdi+8], eax
0x180066db4  add     eax, r14d
0x180066db7  jnz     short loc_180066DE4
0x180066db9  mov     rax, [rdi]
0x180066dbc  mov     rcx, rdi
0x180066dbf  mov     rax, [rax]
0x180066dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066dc7  mov     eax, r14d
0x180066dca  lock xadd [rdi+0Ch], eax
0x180066dcf  add     eax, r14d
0x180066dd2  jnz     short loc_180066DE4
0x180066dd4  mov     rax, [rdi]
0x180066dd7  mov     rcx, rdi
0x180066dda  mov     rax, [rax+8]
0x180066dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066de3  nop
0x180066de4  lea     rcx, [rbp+57h+arg_18]
0x180066de8  call    ??$Make@VWaitForSessionConnect@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWaitForSessionConnect@@@12@XZ; Microsoft::WRL::Details::Make<WaitForSessionConnect,>(void)
0x180066ded  nop
0x180066dee  lea     rax, [rbp+57h+var_B0]
0x180066df2  mov     qword ptr [rbp+57h+var_A0], rax
0x180066df6  lea     rax, [rbp+57h+arg_18]
0x180066dfa  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180066dfe  mov     rcx, [rsi+10h]
0x180066e02  mov     rcx, [rcx+80h]; Thread
0x180066e09  call    cs:__imp_GetThreadId
0x180066e0f  mov     ebx, eax
0x180066e11  call    cs:__imp_GetCurrentThreadId
0x180066e17  lea     rcx, [rbp+57h+var_A0]
0x180066e1b  cmp     ebx, eax
0x180066e1d  jnz     short loc_180066E29
0x180066e1f  call    _lambda_f479fcabb570c85bc961811b2db403b6___operator__
0x180066e24  jmp     loc_180066F6A
0x180066e29  call    ??0?$Event@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@@QEAA@W4EventType@@_N@Z; Event<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::Event<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>(EventType,bool)
0x180066e2e  nop
0x180066e2f  xorps   xmm0, xmm0
0x180066e32  movdqu  [rbp+57h+var_80], xmm0
0x180066e37  lea     rcx, [rbp+57h+var_80]
0x180066e3b  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180066e41  nop
0x180066e42  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x180066e46  test    rcx, rcx
0x180066e49  jz      short loc_180066E54
0x180066e4b  lock add [rcx+8], r13d
0x180066e50  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x180066e54  mov     rax, qword ptr [rbp+57h+var_A0]
0x180066e58  mov     [rbp+57h+var_70], rax
0x180066e5c  mov     [rbp+57h+var_68], rcx
0x180066e60  lea     rax, [rbp+57h+var_B0]
0x180066e64  mov     [rbp+57h+var_60], rax
0x180066e68  lea     rax, [rbp+57h+arg_18]
0x180066e6c  mov     [rbp+57h+var_58], rax
0x180066e70  lea     rax, [rbp+57h+var_80]
0x180066e74  mov     [rbp+57h+var_50], rax
0x180066e78  lea     rdx, [rbp+57h+var_70]
0x180066e7c  mov     rcx, rsi
0x180066e7f  call    CoreUISession__ExecuteAsync__lambda_3d7fe68d703e265bdf060a71098eb542___
0x180066e84  nop
0x180066e85  mov     rbx, [rbp+57h+var_68]
0x180066e89  test    rbx, rbx
0x180066e8c  jz      short loc_180066EC5
0x180066e8e  mov     eax, r14d
0x180066e91  lock xadd [rbx+8], eax
0x180066e96  add     eax, r14d
0x180066e99  jnz     short loc_180066EC5
0x180066e9b  mov     rax, [rbx]
0x180066e9e  mov     rcx, rbx
0x180066ea1  mov     rax, [rax]
0x180066ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ea9  mov     eax, r14d
0x180066eac  lock xadd [rbx+0Ch], eax
0x180066eb1  add     eax, r14d
0x180066eb4  jnz     short loc_180066EC5
0x180066eb6  mov     rax, [rbx]
0x180066eb9  mov     rcx, rbx
0x180066ebc  mov     rax, [rax+8]
0x180066ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ec5  mov     dword ptr [rbp+57h+dwindex], 0
0x180066ecc  mov     rax, qword ptr [rbp+57h+var_A0]
0x180066ed0  test    rax, rax
0x180066ed3  jz      short loc_180066EDA
0x180066ed5  mov     rcx, [rax]
0x180066ed8  jmp     short loc_180066EDC
0x180066eda  xor     ecx, ecx
0x180066edc  mov     [rbp+57h+pHandles], rcx
0x180066ee0  lea     rax, [rbp+57h+dwindex]
0x180066ee4  mov     qword ptr [rsp+0E0h+lpdwindex], rax; int
0x180066ee9  lea     r9, [rbp+57h+pHandles]; pHandles
0x180066eed  mov     r8d, r13d; cHandles
0x180066ef0  or      edx, 0FFFFFFFFh; dwTimeout
0x180066ef3  mov     ecx, 8; dwFlags
0x180066ef8  call    cs:__imp_CoWaitForMultipleHandles
0x180066efe  mov     rcx, [rbp+5Fh]; this
0x180066f02  cmp     eax, 80010115h
0x180066f07  jz      loc_180067097
0x180066f0d  lea     rcx, [rbp+57h+var_80]
0x180066f11  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180066f17  test    al, al
0x180066f19  jnz     loc_1800670AC
0x180066f1f  lea     rcx, [rbp+57h+var_80]
0x180066f23  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180066f29  nop
0x180066f2a  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x180066f2e  test    rbx, rbx
0x180066f31  jz      short loc_180066F6A
0x180066f33  mov     eax, r14d
0x180066f36  lock xadd [rbx+8], eax
0x180066f3b  add     eax, r14d
0x180066f3e  jnz     short loc_180066F6A
0x180066f40  mov     rax, [rbx]
0x180066f43  mov     rcx, rbx
0x180066f46  mov     rax, [rax]
0x180066f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f4e  mov     eax, r14d
0x180066f51  lock xadd [rbx+0Ch], eax
0x180066f56  add     eax, r14d
0x180066f59  jnz     short loc_180066F6A
0x180066f5b  mov     rax, [rbx]
0x180066f5e  mov     rcx, rbx
0x180066f61  mov     rax, [rax+8]
0x180066f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f6a  mov     dword ptr [rbp+57h+dwindex], 0
0x180066f71  mov     rax, [rbp+57h+arg_18]
0x180066f75  mov     rcx, [rax+18h]
0x180066f79  mov     [rbp+57h+pHandles], rcx
0x180066f7d  lea     rax, [rbp+57h+dwindex]
0x180066f81  mov     qword ptr [rsp+0E0h+lpdwindex], rax; int
0x180066f86  lea     r9, [rbp+57h+pHandles]; pHandles
0x180066f8a  mov     r8d, r13d; cHandles
0x180066f8d  or      edx, 0FFFFFFFFh; dwTimeout
0x180066f90  xor     ecx, ecx; dwFlags
0x180066f92  call    cs:__imp_CoWaitForMultipleHandles
0x180066f98  mov     rcx, [rbp+5Fh]; this
0x180066f9c  cmp     eax, 80010115h
0x180066fa1  jz      loc_1800670C2
0x180066fa7  mov     [rbp+57h+arg_8], 0
0x180066fae  mov     rcx, [rbp+57h+var_B0]
0x180066fb2  movups  xmm0, xmmword ptr [r15]
0x180066fb6  movdqu  [rbp+57h+var_A0], xmm0
0x180066fbb  mov     rax, [rcx]
0x180066fbe  lea     r8, [rbp+57h+arg_8]
0x180066fc2  lea     rdx, [rbp+57h+var_A0]
0x180066fc6  mov     rax, [rax+1A8h]
0x180066fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fd2  mov     rcx, [rbp+5Fh]; this
0x180066fd6  test    eax, eax
0x180066fd8  js      loc_18006706D
0x180066fde  cmp     [rbp+57h+arg_8], r13d
0x180066fe2  setz    bl
0x180066fe5  mov     rcx, [rbp+57h+arg_18]
0x180066fe9  test    rcx, rcx
0x180066fec  jz      short loc_180067003
0x180066fee  mov     [rbp+57h+arg_18], 0
0x180066ff6  mov     rax, [rcx]
0x180066ff9  mov     rax, [rax+10h]
0x180066ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067002  nop
0x180067003  mov     eax, r14d
0x180067006  lock xadd [rdi+8], eax
0x18006700b  add     eax, r14d
0x18006700e  jnz     short loc_18006703B
0x180067010  mov     rax, [rdi]
0x180067013  mov     rcx, rdi
0x180067016  mov     rax, [rax]
0x180067019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006701e  mov     eax, r14d
0x180067021  lock xadd [rdi+0Ch], eax
0x180067026  add     eax, r14d
0x180067029  jnz     short loc_18006703B
0x18006702b  mov     rax, [rdi]
0x18006702e  mov     rcx, rdi
0x180067031  mov     rax, [rax+8]
0x180067035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006703a  nop
0x18006703b  mov     rcx, [rbp+57h+var_B0]
0x18006703f  test    rcx, rcx
0x180067042  jz      short loc_180067059
0x180067044  mov     [rbp+57h+var_B0], 0
0x18006704c  mov     rdx, [rcx]
0x18006704f  mov     rax, [rdx+10h]
0x180067053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067058  nop
0x180067059  mov     al, bl
0x18006705b  add     rsp, 0B0h
0x180067062  pop     r15
0x180067064  pop     r14
0x180067066  pop     r13
0x180067068  pop     rdi
0x180067069  pop     rsi
0x18006706a  pop     rbx
0x18006706b  pop     rbp
0x18006706c  retn
0x18006706d  mov     r9d, eax; char *
0x180067070  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180067077  mov     edx, 33h ; '3'; void *
0x18006707c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180067082  mov     r9d, r14d; char *
0x180067085  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\CoreUIM"...
0x18006708c  mov     edx, 6Fh ; 'o'; void *
0x180067091  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180067097  mov     r9d, eax; char *
0x18006709a  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\CoreUIM"...
0x1800670a1  mov     edx, 1Bh; void *
0x1800670a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800670ac  lea     rdx, [rbp+57h+var_80]; struct std::exception_ptr *
0x1800670b0  lea     rcx, [rbp+57h+pHandles]; this
0x1800670b4  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x1800670b9  mov     rcx, rax
0x1800670bc  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x1800670c2  mov     r9d, eax; char *
0x1800670c5  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\CoreUIM"...
0x1800670cc  mov     edx, 1Bh; void *
0x1800670d1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
