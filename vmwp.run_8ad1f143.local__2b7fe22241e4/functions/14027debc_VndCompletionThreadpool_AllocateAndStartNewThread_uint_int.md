# VndCompletionThreadpool::AllocateAndStartNewThread(uint,int)

- ea: `0x14027debc`
- end: `0x14027e085`
- name: `?AllocateAndStartNewThread@VndCompletionThreadpool@@AEAAPEAVVndCompletionThread@@IH@Z`
- size: `457`
- prototype: `struct VndCompletionThread *__fastcall(VndCompletionThreadpool *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400da234`

## callees

- `0x140031ca8`
- `0x14003366c`
- `0x140042260`
- `0x140054a90`
- `0x140055d80`
- `0x14005ddf0`
- `0x14006af58`
- `0x1400d2d9c`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x14027debc`
- `0x14027e1cc`
- `0x14027e540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027df9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027e01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027df9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027e01b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x14027dff5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x14027dff5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14027e00b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14027e00b`
- `vid!VidMessageSlotMap` at `0x14027df8d`
- `vid!VidMessageSlotMap` at `0x14027df8d`

## string_xrefs

- `0x14027dfc4`: `onecore\vm\worker\vidpartition\vndcompletionthreadpool.cpp`
- `0x14027e03c`: `Failed to set VND thread priority! Error = %u\n`
- `0x14027df0e`: `VndCompletionThreadpoolThread prio %d index %d`

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
0x14027debc  mov     [rsp-18h+arg_18], rbx
0x14027dec1  push    rbp
0x14027dec2  push    rsi
0x14027dec3  push    rdi
0x14027dec4  mov     rbp, rsp
0x14027dec7  sub     rsp, 70h
0x14027decb  mov     rax, cs:__security_cookie
0x14027ded2  xor     rax, rsp
0x14027ded5  mov     [rbp+var_10], rax
0x14027ded9  mov     edi, r8d
0x14027dedc  mov     rsi, rcx
0x14027dedf  mov     [rbp+var_40], 0
0x14027dee7  xorps   xmm0, xmm0
0x14027deea  movups  xmmword ptr [rbp+var_30], xmm0
0x14027deee  mov     [rbp+var_20], 0
0x14027def6  mov     [rbp+var_18], 7
0x14027defe  xor     eax, eax
0x14027df00  mov     word ptr [rbp+var_30], ax
0x14027df04  mov     r9d, edx
0x14027df07  mov     r8d, [rcx+80h]
0x14027df0e  lea     rdx, aVndcompletiont; "VndCompletionThreadpoolThread prio %d i"...
0x14027df15  lea     rcx, [rbp+var_30]
0x14027df19  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14027df1e  mov     ecx, 0F0h; Size
0x14027df23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14027df28  mov     rbx, rax
0x14027df2b  mov     [rbp+var_38], rax
0x14027df2f  xor     edx, edx; Val
0x14027df31  mov     r8d, 0F0h; Size
0x14027df37  mov     rcx, rax; void *
0x14027df3a  call    memset_0
0x14027df3f  mov     r8d, edi; int
0x14027df42  mov     rdx, rsi; struct VndCompletionThreadpool *
0x14027df45  mov     rcx, rbx; this
0x14027df48  call    ??0VndCompletionThread@@QEAA@PEAVVndCompletionThreadpool@@H@Z; VndCompletionThread::VndCompletionThread(VndCompletionThreadpool *,int)
0x14027df4d  mov     rdx, rax
0x14027df50  lea     rcx, [rbp+var_40]
0x14027df54  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x14027df59  mov     rbx, [rbp+var_40]
0x14027df5d  mov     rax, [rbx+78h]
0x14027df61  mov     rcx, [rax+78h]
0x14027df65  mov     rdi, [rcx]
0x14027df68  lea     rcx, [rbx+98h]
0x14027df6f  xor     edx, edx
0x14027df71  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14027df76  mov     r8d, [rbx+90h]
0x14027df7d  test    r8d, r8d
0x14027df80  js      short loc_14027DFB7
0x14027df82  lea     rdx, [rbx+80h]
0x14027df89  mov     rcx, [rdi+28h]
0x14027df8d  call    cs:__imp_VidMessageSlotMap
0x14027df94  nop     dword ptr [rax+rax+00h]
0x14027df99  test    eax, eax
0x14027df9b  jnz     short loc_14027DFB7
0x14027df9d  call    cs:__imp_GetLastError
0x14027dfa4  nop     dword ptr [rax+rax+00h]
0x14027dfa9  test    eax, eax
0x14027dfab  jle     short loc_14027DFB9
0x14027dfad  movzx   eax, ax
0x14027dfb0  or      eax, 80070000h
0x14027dfb5  jmp     short loc_14027DFB9
0x14027dfb7  xor     eax, eax
0x14027dfb9  mov     rcx, [rbp+18h]; this
0x14027dfbd  test    eax, eax
0x14027dfbf  jns     short loc_14027DFD6
0x14027dfc1  mov     r9d, eax; char *
0x14027dfc4  lea     r8, aOnecoreVmWorke_58; "onecore\\vm\\worker\\vidpartition\\vndc"...
0x14027dfcb  mov     edx, 102h; void *
0x14027dfd0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14027dfd6  lea     rdx, [rbp+var_30]
0x14027dfda  cmp     [rbp+var_18], 7
0x14027dfdf  cmova   rdx, [rbp+var_30]; unsigned __int16 *
0x14027dfe4  mov     rcx, rbx; this
0x14027dfe7  call    ?Start@VmThread@Vml@@QEAAXPEBG@Z; Vml::VmThread::Start(ushort const *)
0x14027dfec  mov     edx, 1; bDisablePriorityBoost
0x14027dff1  mov     rcx, [rbx+40h]; hThread
0x14027dff5  call    cs:__imp_SetThreadPriorityBoost
0x14027dffc  nop     dword ptr [rax+rax+00h]
0x14027e001  mov     edx, [rsi+80h]; nPriority
0x14027e007  mov     rcx, [rbx+40h]; hThread
0x14027e00b  call    cs:__imp_SetThreadPriority
0x14027e012  nop     dword ptr [rax+rax+00h]
0x14027e017  test    eax, eax
0x14027e019  jnz     short loc_14027E04A
0x14027e01b  call    cs:__imp_GetLastError
0x14027e022  nop     dword ptr [rax+rax+00h]
0x14027e027  mov     edi, eax
0x14027e029  mov     esi, 8024h
0x14027e02e  mov     ecx, esi
0x14027e030  call    VmlIsDebugTraceEnabled
0x14027e035  test    eax, eax
0x14027e037  jz      short loc_14027E04A
0x14027e039  mov     r8d, edi
0x14027e03c  lea     rdx, aFailedToSetVnd; "Failed to set VND thread priority! Erro"...
0x14027e043  mov     ecx, esi
0x14027e045  call    VmlDebugTrace
0x14027e04a  mov     [rbp+var_40], 0
0x14027e052  lea     rcx, [rbp+var_30]
0x14027e056  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14027e05b  nop
0x14027e05c  lea     rcx, [rbp+var_40]
0x14027e060  call    ??1?$VmReferencePtr@UIMemoryContentsFileSizeChangeCallback@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(void)
0x14027e065  mov     rax, rbx
0x14027e068  mov     rcx, [rbp+var_10]
0x14027e06c  xor     rcx, rsp; StackCookie
0x14027e06f  call    __security_check_cookie
0x14027e074  mov     rbx, [rsp+70h+arg_18]
0x14027e07c  add     rsp, 70h
0x14027e080  pop     rdi
0x14027e081  pop     rsi
0x14027e082  pop     rbp
0x14027e083  retn
```
