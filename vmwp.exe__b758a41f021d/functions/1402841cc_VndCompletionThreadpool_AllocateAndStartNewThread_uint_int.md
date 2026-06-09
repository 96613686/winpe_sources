# VndCompletionThreadpool::AllocateAndStartNewThread(uint,int)

- ea: `0x1402841cc`
- end: `0x140284395`
- name: `?AllocateAndStartNewThread@VndCompletionThreadpool@@AEAAPEAVVndCompletionThread@@IH@Z`
- size: `457`
- prototype: `struct VndCompletionThread *__fastcall(VndCompletionThreadpool *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c8568`

## callees

- `0x140032620`
- `0x1400364a0`
- `0x14003d828`
- `0x1400545bc`
- `0x140055af4`
- `0x140078628`
- `0x1400a5d70`
- `0x1400c015c`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x1402841cc`
- `0x1402844dc`
- `0x140284850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402842ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14028432b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402842ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14028432b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x140284305`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x140284305`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14028431b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14028431b`
- `vid!VidMessageSlotMap` at `0x14028429d`
- `vid!VidMessageSlotMap` at `0x14028429d`

## string_xrefs

- `0x14028421e`: `VndCompletionThreadpoolThread prio %d index %d`
- `0x14028434c`: `Failed to set VND thread priority! Error = %u\n`
- `0x1402842d4`: `onecore\vm\worker\vidpartition\vndcompletionthreadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct VndCompletionThread *__fastcall VndCompletionThreadpool::AllocateAndStartNewThread(
        VndCompletionThreadpool *this,
        unsigned int a2,
        int a3)
{
  VndCompletionThread *v5; // rax
  Vml::VmThread *v6; // rbx
  __int64 v7; // rdi
  signed int LastError; // eax
  const unsigned __int16 *v9; // rdx
  DWORD v10; // edi
  int v12; // [rsp+20h] [rbp-50h]
  Vml::VmThread *v13; // [rsp+30h] [rbp-40h] BYREF
  void *v14; // [rsp+38h] [rbp-38h]
  unsigned __int16 *v15[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+50h] [rbp-20h]
  unsigned __int64 v17; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v13 = 0;
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v17 = 7;
  LOWORD(v15[0]) = 0;
  Vml::FormatString(v15, L"VndCompletionThreadpoolThread prio %d index %d", *((unsigned int *)this + 32), a2);
  v14 = operator new(0xF0u);
  memset_0(v14, 0, 0xF0u);
  v5 = VndCompletionThread::VndCompletionThread((VndCompletionThread *)v14, this, a3);
  Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(&v13, v5);
  v6 = v13;
  v7 = **(_QWORD **)(*((_QWORD *)v13 + 15) + 120LL);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)v13 + 152,
    0);
  if ( *((int *)v6 + 36) < 0 || (unsigned int)VidMessageSlotMap(*(_QWORD *)(v7 + 40), (char *)v6 + 128) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\vm\\worker\\vidpartition\\vndcompletionthreadpool.cpp",
      (const char *)(unsigned int)LastError,
      v12);
  v9 = (const unsigned __int16 *)v15;
  if ( v17 > 7 )
    v9 = v15[0];
  Vml::VmThread::Start(v6, v9);
  SetThreadPriorityBoost(*((HANDLE *)v6 + 8), 1);
  if ( !SetThreadPriority(*((HANDLE *)v6 + 8), *((_DWORD *)this + 32)) )
  {
    v10 = GetLastError();
    if ( (unsigned int)VmlIsDebugTraceEnabled(32804) )
      VmlDebugTrace(32804, L"Failed to set VND thread priority! Error = %u\n", v10);
  }
  v13 = 0;
  std::wstring::_Tidy_deallocate(v15);
  Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(&v13);
  return v6;
}

```

## disassembly

```asm
0x1402841cc  mov     [rsp-18h+arg_18], rbx
0x1402841d1  push    rbp
0x1402841d2  push    rsi
0x1402841d3  push    rdi
0x1402841d4  mov     rbp, rsp
0x1402841d7  sub     rsp, 70h
0x1402841db  mov     rax, cs:__security_cookie
0x1402841e2  xor     rax, rsp
0x1402841e5  mov     [rbp+var_10], rax
0x1402841e9  mov     edi, r8d
0x1402841ec  mov     rsi, rcx
0x1402841ef  mov     [rbp+var_40], 0
0x1402841f7  xorps   xmm0, xmm0
0x1402841fa  movups  xmmword ptr [rbp+var_30], xmm0
0x1402841fe  mov     [rbp+var_20], 0
0x140284206  mov     [rbp+var_18], 7
0x14028420e  xor     eax, eax
0x140284210  mov     word ptr [rbp+var_30], ax
0x140284214  mov     r9d, edx
0x140284217  mov     r8d, [rcx+80h]
0x14028421e  lea     rdx, aVndcompletiont; "VndCompletionThreadpoolThread prio %d i"...
0x140284225  lea     rcx, [rbp+var_30]
0x140284229  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14028422e  mov     ecx, 0F0h; Size
0x140284233  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140284238  mov     rbx, rax
0x14028423b  mov     [rbp+var_38], rax
0x14028423f  xor     edx, edx; Val
0x140284241  mov     r8d, 0F0h; Size
0x140284247  mov     rcx, rax; void *
0x14028424a  call    memset_0
0x14028424f  mov     r8d, edi; int
0x140284252  mov     rdx, rsi; struct VndCompletionThreadpool *
0x140284255  mov     rcx, rbx; this
0x140284258  call    ??0VndCompletionThread@@QEAA@PEAVVndCompletionThreadpool@@H@Z; VndCompletionThread::VndCompletionThread(VndCompletionThreadpool *,int)
0x14028425d  mov     rdx, rax
0x140284260  lea     rcx, [rbp+var_40]
0x140284264  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x140284269  mov     rbx, [rbp+var_40]
0x14028426d  mov     rax, [rbx+78h]
0x140284271  mov     rcx, [rax+78h]
0x140284275  mov     rdi, [rcx]
0x140284278  lea     rcx, [rbx+98h]
0x14028427f  xor     edx, edx
0x140284281  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140284286  mov     r8d, [rbx+90h]
0x14028428d  test    r8d, r8d
0x140284290  js      short loc_1402842C7
0x140284292  lea     rdx, [rbx+80h]
0x140284299  mov     rcx, [rdi+28h]
0x14028429d  call    cs:__imp_VidMessageSlotMap
0x1402842a4  nop     dword ptr [rax+rax+00h]
0x1402842a9  test    eax, eax
0x1402842ab  jnz     short loc_1402842C7
0x1402842ad  call    cs:__imp_GetLastError
0x1402842b4  nop     dword ptr [rax+rax+00h]
0x1402842b9  test    eax, eax
0x1402842bb  jle     short loc_1402842C9
0x1402842bd  movzx   eax, ax
0x1402842c0  or      eax, 80070000h
0x1402842c5  jmp     short loc_1402842C9
0x1402842c7  xor     eax, eax
0x1402842c9  mov     rcx, [rbp+18h]; this
0x1402842cd  test    eax, eax
0x1402842cf  jns     short loc_1402842E6
0x1402842d1  mov     r9d, eax; char *
0x1402842d4  lea     r8, aOnecoreVmWorke_59; "onecore\\vm\\worker\\vidpartition\\vndc"...
0x1402842db  mov     edx, 102h; void *
0x1402842e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402842e6  lea     rdx, [rbp+var_30]
0x1402842ea  cmp     [rbp+var_18], 7
0x1402842ef  cmova   rdx, [rbp+var_30]; unsigned __int16 *
0x1402842f4  mov     rcx, rbx; this
0x1402842f7  call    ?Start@VmThread@Vml@@QEAAXPEBG@Z; Vml::VmThread::Start(ushort const *)
0x1402842fc  mov     edx, 1; bDisablePriorityBoost
0x140284301  mov     rcx, [rbx+40h]; hThread
0x140284305  call    cs:__imp_SetThreadPriorityBoost
0x14028430c  nop     dword ptr [rax+rax+00h]
0x140284311  mov     edx, [rsi+80h]; nPriority
0x140284317  mov     rcx, [rbx+40h]; hThread
0x14028431b  call    cs:__imp_SetThreadPriority
0x140284322  nop     dword ptr [rax+rax+00h]
0x140284327  test    eax, eax
0x140284329  jnz     short loc_14028435A
0x14028432b  call    cs:__imp_GetLastError
0x140284332  nop     dword ptr [rax+rax+00h]
0x140284337  mov     edi, eax
0x140284339  mov     esi, 8024h
0x14028433e  mov     ecx, esi
0x140284340  call    VmlIsDebugTraceEnabled
0x140284345  test    eax, eax
0x140284347  jz      short loc_14028435A
0x140284349  mov     r8d, edi
0x14028434c  lea     rdx, aFailedToSetVnd; "Failed to set VND thread priority! Erro"...
0x140284353  mov     ecx, esi
0x140284355  call    VmlDebugTrace
0x14028435a  mov     [rbp+var_40], 0
0x140284362  lea     rcx, [rbp+var_30]
0x140284366  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028436b  nop
0x14028436c  lea     rcx, [rbp+var_40]
0x140284370  call    ??1?$VmReferencePtr@UIMemoryContentsFileSizeChangeCallback@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(void)
0x140284375  mov     rax, rbx
0x140284378  mov     rcx, [rbp+var_10]
0x14028437c  xor     rcx, rsp; StackCookie
0x14028437f  call    __security_check_cookie
0x140284384  mov     rbx, [rsp+70h+arg_18]
0x14028438c  add     rsp, 70h
0x140284390  pop     rdi
0x140284391  pop     rsi
0x140284392  pop     rbp
0x140284393  retn
```
