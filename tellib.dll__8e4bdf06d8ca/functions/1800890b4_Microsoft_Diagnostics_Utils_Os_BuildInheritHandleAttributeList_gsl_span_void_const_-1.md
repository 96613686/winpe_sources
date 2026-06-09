# Microsoft::Diagnostics::Utils::Os::BuildInheritHandleAttributeList(gsl::span<void * const,-1>)

- ea: `0x1800890b4`
- end: `0x180089251`
- name: `?BuildInheritHandleAttributeList@Os@Utils@Diagnostics@Microsoft@@CA?AUAttributeListAndMemory@1234@V?$span@QEAX$0?0@gsl@@@Z`
- size: `413`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008674c`
- `0x180088da8`

## callees

- `0x18005af1c`
- `0x1800890b4`
- `0x1800a1e24`
- `0x1800b83bc`
- `0x1800d0d7c`
- `0x1800d0df0`
- `0x18016ff48`
- `0x180170014`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800891df`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800891df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800890fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800890fe`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800890ea`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180089169`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800890ea`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180089169`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800891a8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180089217`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180089217`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::BuildInheritHandleAttributeList(__int64 a1, __int64 *a2)
{
  const char *v4; // r9
  const struct std::nothrow_t *v5; // rax
  const char *v6; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *v7; // rdi
  unsigned __int64 v8; // rax
  const char *v9; // r9
  void (__stdcall *v11)(LPPROC_THREAD_ATTRIBUTE_LIST); // [rsp+48h] [rbp-18h] BYREF
  _BYTE v12[16]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  ULONG_PTR Size; // [rsp+90h] [rbp+30h] BYREF
  __int64 v15; // [rsp+98h] [rbp+38h] BYREF

  Size = 0;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && GetLastError() != 122 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE4D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
      v4);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v5 = (const struct std::nothrow_t *)std::make_unique<unsigned char [0],0>(&v15, Size);
  std::unique_ptr<enum gsl::byte [0]>::operator=<std::default_delete<enum gsl::byte [0]>,0>((void **)a1, v5);
  std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v15);
  if ( !InitializeProcThreadAttributeList(*(LPPROC_THREAD_ATTRIBUTE_LIST *)a1, 1u, 0, &Size) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE57,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
      v6);
  v7 = *(struct _PROC_THREAD_ATTRIBUTE_LIST **)a1;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v15 = *(_QWORD *)(a1 + 8);
    wil::last_error_context::last_error_context((wil::last_error_context *)v12);
    v11 = DeleteProcThreadAttributeList;
    wistd::invoke<void * (*)(void *),void * &>(&v11, &v15);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v12);
  }
  *(_QWORD *)(a1 + 8) = v7;
  v8 = *a2;
  if ( (unsigned __int64)*a2 >= 0x1FFFFFFFFFFFFFFFLL )
  {
    LODWORD(v8) = _o_terminate();
    __debugbreak();
  }
  if ( !UpdateProcThreadAttribute(v7, 0, 0x20002u, (PVOID)a2[1], (unsigned int)(8 * v8), 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE63,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
      v9);
  return a1;
}

```

## disassembly

```asm
0x1800890b4  mov     [rsp-18h+arg_8], rbx
0x1800890b9  mov     [rsp-18h+arg_0], rcx
0x1800890be  push    rbp
0x1800890bf  push    rsi
0x1800890c0  push    rdi
0x1800890c1  mov     rbp, rsp
0x1800890c4  sub     rsp, 60h
0x1800890c8  mov     rsi, rdx
0x1800890cb  mov     rbx, rcx
0x1800890ce  mov     [rbp+var_20], 0
0x1800890d5  mov     [rbp+Size], 0
0x1800890dd  lea     r9, [rbp+Size]; lpSize
0x1800890e1  xor     r8d, r8d; dwFlags
0x1800890e4  lea     edx, [r8+1]; dwAttributeCount
0x1800890e8  xor     ecx, ecx; lpAttributeList
0x1800890ea  call    cs:__imp_InitializeProcThreadAttributeList
0x1800890f1  nop     dword ptr [rax+rax+00h]
0x1800890f6  test    eax, eax
0x1800890f8  jnz     short loc_180089124
0x1800890fa  mov     rdi, [rbp+18h]
0x1800890fe  call    cs:__imp_GetLastError
0x180089105  nop     dword ptr [rax+rax+00h]
0x18008910a  cmp     eax, 7Ah ; 'z'
0x18008910d  jz      short loc_180089124
0x18008910f  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180089116  mov     edx, 0E4Dh; void *
0x18008911b  mov     rcx, rdi; this
0x18008911e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180089124  mov     qword ptr [rbx], 0
0x18008912b  mov     qword ptr [rbx+8], 0
0x180089133  mov     [rbp+var_20], 1
0x18008913a  mov     rdx, [rbp+Size]
0x18008913e  lea     rcx, [rbp+arg_18]
0x180089142  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180089147  mov     rdx, rax
0x18008914a  mov     rcx, rbx
0x18008914d  call    ??$?4U?$default_delete@$$BY0A@W4byte@gsl@@@std@@$0A@@?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<gsl::byte [0]>::operator=<std::default_delete<gsl::byte [0]>,0>(std::unique_ptr<gsl::byte [0]> &&)
0x180089152  lea     rcx, [rbp+arg_18]
0x180089156  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18008915b  lea     r9, [rbp+Size]; lpSize
0x18008915f  xor     r8d, r8d; dwFlags
0x180089162  lea     edx, [r8+1]; dwAttributeCount
0x180089166  mov     rcx, [rbx]; lpAttributeList
0x180089169  call    cs:__imp_InitializeProcThreadAttributeList
0x180089170  nop     dword ptr [rax+rax+00h]
0x180089175  test    eax, eax
0x180089177  jnz     short loc_18008918F
0x180089179  mov     rcx, [rbp+18h]; this
0x18008917d  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180089184  mov     edx, 0E57h; void *
0x180089189  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008918f  mov     rdi, [rbx]
0x180089192  mov     rax, [rbx+8]
0x180089196  test    rax, rax
0x180089199  jz      short loc_1800891C9
0x18008919b  mov     [rbp+arg_18], rax
0x18008919f  lea     rcx, [rbp+var_10]; this
0x1800891a3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800891a8  mov     rax, cs:__imp_DeleteProcThreadAttributeList
0x1800891af  mov     [rbp+var_18], rax
0x1800891b3  lea     rdx, [rbp+arg_18]
0x1800891b7  lea     rcx, [rbp+var_18]
0x1800891bb  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x1800891c0  lea     rcx, [rbp+var_10]; this
0x1800891c4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800891c9  mov     [rbx+8], rdi
0x1800891cd  mov     rax, [rsi]
0x1800891d0  mov     rcx, 1FFFFFFFFFFFFFFFh
0x1800891da  cmp     rax, rcx
0x1800891dd  jb      short loc_1800891EC
0x1800891df  call    cs:__imp__o_terminate
0x1800891e6  nop     dword ptr [rax+rax+00h]
0x1800891eb  int     3; Trap to Debugger
0x1800891ec  shl     eax, 3
0x1800891ef  mov     edx, eax
0x1800891f1  mov     [rsp+60h+lpReturnSize], 0; lpReturnSize
0x1800891fa  mov     [rsp+60h+lpPreviousValue], 0; lpPreviousValue
0x180089203  mov     [rsp+60h+cbSize], rdx; cbSize
0x180089208  mov     r9, [rsi+8]; lpValue
0x18008920c  xor     edx, edx; dwFlags
0x18008920e  mov     r8d, 20002h; Attribute
0x180089214  mov     rcx, rdi; lpAttributeList
0x180089217  call    cs:__imp_UpdateProcThreadAttribute
0x18008921e  nop     dword ptr [rax+rax+00h]
0x180089223  test    eax, eax
0x180089225  jnz     short loc_18008923D
0x180089227  mov     rcx, [rbp+18h]; this
0x18008922b  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180089232  mov     edx, 0E63h; void *
0x180089237  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008923d  mov     rax, rbx
0x180089240  mov     rbx, [rsp+60h+arg_8]
0x180089248  add     rsp, 60h
0x18008924c  pop     rdi
0x18008924d  pop     rsi
0x18008924e  pop     rbp
0x18008924f  retn
```
