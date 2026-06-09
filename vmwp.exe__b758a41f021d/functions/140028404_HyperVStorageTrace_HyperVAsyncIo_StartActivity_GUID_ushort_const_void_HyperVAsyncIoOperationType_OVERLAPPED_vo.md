# HyperVStorageTrace::HyperVAsyncIo::StartActivity(_GUID,ushort const *,void *,HyperVAsyncIoOperationType,_OVERLAPPED *,void const *,ulong)

- ea: `0x140028404`
- end: `0x140028782`
- name: `?StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z`
- size: `894`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400282f4`

## callees

- `0x140006660`
- `0x1400243c0`
- `0x14002676c`
- `0x140028404`
- `0x140028d38`
- `0x14003b750`
- `0x14003d86c`
- `0x140042aec`
- `0x140047188`
- `0x14004cb70`
- `0x140055f4c`
- `0x1400b06a4`
- `0x14011fcec`
- `0x14011fd54`
- `0x1401c9424`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028613`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14002854f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14002854f`
- `RPCRT4!UuidCreate` at `0x140028491`
- `RPCRT4!UuidCreate` at `0x140028491`

## pseudocode

```c
void __fastcall HyperVStorageTrace::HyperVAsyncIo::StartActivity(
        __int64 a1,
        _OWORD *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        void *a7,
        unsigned int a8)
{
  _QWORD *v8; // r14
  wchar_t *v11; // rdx
  _QWORD *v12; // rdi
  int IsDebugTraceEnabled; // ebx
  unsigned __int64 v14; // rdx
  unsigned __int8 v15; // cl
  bool IsEnabled; // al
  char v17; // r15
  _QWORD *v18; // r9
  _QWORD *v19; // r8
  __int64 v20; // rbx
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rdx
  _DWORD *v23; // rbx
  bool v24; // cc
  __int64 v25; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v27; // r8
  wil::details::ThreadFailureCallbackHolder *v28; // rcx
  __int64 v29; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int v30; // [rsp+A8h] [rbp-78h] BYREF
  int v31; // [rsp+ACh] [rbp-74h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-70h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v39; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v40; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v41; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v42; // [rsp+100h] [rbp-20h] BYREF
  __int64 v43[7]; // [rsp+108h] [rbp-18h] BYREF

  v8 = (_QWORD *)(a1 + 368);
  *(_OWORD *)(a1 + 336) = *a2;
  if ( !a3 )
    a3 = &qword_1402EDF50;
  std::wstring::assign(a1 + 368, a3);
  *(_QWORD *)(a1 + 400) = a4;
  v11 = `HvsGetOperationName'::`2'::g_OperationNames[a5];
  v12 = (_QWORD *)(a1 + 416);
  *(_DWORD *)(a1 + 408) = a5;
  std::wstring::assign(a1 + 416, v11);
  *(_QWORD *)(a1 + 448) = a6;
  UuidCreate((UUID *)(a1 + 352));
  IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC020u);
  IsEnabled = HyperVStorageTrace::IsEnabled(v15, v14);
  v17 = IsEnabled;
  if ( IsDebugTraceEnabled || IsEnabled )
  {
    if ( __TSS0__8__StartActivity_HyperVAsyncIo_HyperVStorageTrace__QEAAXU_GUID__PEBGPEAXW4HyperVAsyncIoOperationType__PEAU_OVERLAPPED__PEBXK_Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
    {
      Init_thread_header(&__TSS0__8__StartActivity_HyperVAsyncIo_HyperVStorageTrace__QEAAXU_GUID__PEBGPEAXW4HyperVAsyncIoOperationType__PEAU_OVERLAPPED__PEBXK_Z_4HA);
      if ( __TSS0__8__StartActivity_HyperVAsyncIo_HyperVStorageTrace__QEAAXU_GUID__PEBGPEAXW4HyperVAsyncIoOperationType__PEAU_OVERLAPPED__PEBXK_Z_4HA == -1 )
      {
        byte_1403B4114 = IsDebugTraceEnabled != 0;
        byte_1403B4115 = v17;
        Init_thread_footer(&__TSS0__8__StartActivity_HyperVAsyncIo_HyperVStorageTrace__QEAAXU_GUID__PEBGPEAXW4HyperVAsyncIoOperationType__PEAU_OVERLAPPED__PEBXK_Z_4HA);
      }
    }
    if ( v8[3] <= 7u )
      v18 = v8;
    else
      v18 = (_QWORD *)*v8;
    if ( *(_QWORD *)(a1 + 440) <= 7u )
      v19 = (_QWORD *)(a1 + 416);
    else
      v19 = (_QWORD *)*v12;
    HvsDebugTraceInternal(
      0xC020u,
      (const struct HvsDebugTraceParameters *)&`HyperVStorageTrace::HyperVAsyncIo::StartActivity'::`9'::traceParameters,
      v19,
      v18);
  }
  v29 = 0;
  wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v29);
  v20 = *(_QWORD *)(a1 + 272);
  v21 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
  if ( *v21 > 5u && (unsigned __int8)tlgKeywordOn(v21, 160) )
    EventActivityIdControl(3u, (LPGUID)(v20 + 8));
  else
    *(_OWORD *)(v20 + 8) = 0;
  *(_DWORD *)v20 = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v29);
  v23 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
  if ( *v23 > 5u && (unsigned __int8)tlgKeywordOn(v23, 160) )
  {
    v24 = *(_QWORD *)(a1 + 440) <= 7u;
    v25 = *(_QWORD *)(a1 + 448);
    v30 = a8;
    v33 = (__int64)a7;
    v34 = *(_QWORD *)(v25 + 24);
    v31 = *(_DWORD *)(v25 + 20);
    LODWORD(v32) = *(_DWORD *)(v25 + 16);
    v35 = *(_QWORD *)(v25 + 8);
    v36 = *(_QWORD *)v25;
    v37 = v25;
    if ( !v24 )
      v12 = (_QWORD *)*v12;
    v24 = v8[3] <= 7u;
    v39 = *(_QWORD *)(a1 + 400);
    v38 = (__int64)v12;
    if ( !v24 )
      v8 = (_QWORD *)*v8;
    v40 = (__int64)v8;
    v41 = a1 + 352;
    v42 = a1 + 336;
    CurrentThreadId = GetCurrentThreadId();
    v27 = *(_QWORD *)(a1 + 272);
    LODWORD(v29) = CurrentThreadId;
    v43[0] = 0;
    if ( *(_BYTE *)(v27 + 4) )
      _tlgGuidIsZero((const struct _GUID *)(v27 + 24));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (int)v23,
      (int)&dword_140359364,
      v27 + 8,
      (__int64)v43,
      (__int64)&v29,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v30);
  }
  v28 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v28);
  if ( *(_DWORD *)(a1 + 408) == 5
    && HyperVStorageTrace::IsEnabled((unsigned __int8)v28, v22)
    && **(_DWORD **)(a1 + 272) == 1 )
  {
    HyperVStorageTrace::HyperVAsyncIo::TraceBufferContent(
      (HyperVStorageTrace::HyperVAsyncIo *)a1,
      L"ActivityStart",
      a7,
      a8);
  }
}

```

## disassembly

```asm
0x140028404  mov     [rsp-8+arg_8], rbx
0x140028409  push    rbp
0x14002840a  push    rsi
0x14002840b  push    rdi
0x14002840c  push    r12
0x14002840e  push    r13
0x140028410  push    r14
0x140028412  push    r15
0x140028414  lea     rbp, [rsp+10h]
0x140028419  sub     rsp, 110h
0x140028420  movups  xmm0, xmmword ptr [rdx]
0x140028423  mov     ebx, [rbp+20h+arg_20]
0x140028426  lea     rax, qword_1402EDF50
0x14002842d  mov     r13, [rbp+20h+arg_30]
0x140028431  lea     r14, [rcx+170h]
0x140028438  test    r8, r8
0x14002843b  mov     rsi, rcx
0x14002843e  movdqu  xmmword ptr [rcx+150h], xmm0
0x140028446  cmovz   r8, rax
0x14002844a  mov     rcx, r14
0x14002844d  mov     rdx, r8
0x140028450  mov     rdi, r9
0x140028453  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140028458  mov     [rsi+190h], rdi
0x14002845f  lea     rax, ?g_OperationNames@?1??HvsGetOperationName@@YAPEBGW4HyperVAsyncIoOperationType@@@Z@4QBQEBGB; ushort const * const near * const `HvsGetOperationName(HyperVAsyncIoOperationType)'::`2'::g_OperationNames
0x140028466  mov     rdx, [rax+rbx*8]
0x14002846a  lea     rdi, [rsi+1A0h]
0x140028471  mov     rcx, rdi
0x140028474  mov     [rsi+198h], ebx
0x14002847a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x14002847f  mov     rax, [rbp+20h+arg_28]
0x140028483  lea     rcx, [rsi+160h]; Uuid
0x14002848a  mov     [rsi+1C0h], rax
0x140028491  call    cs:__imp_UuidCreate
0x140028498  nop     dword ptr [rax+rax+00h]
0x14002849d  mov     ecx, 0C020h; unsigned __int16
0x1400284a2  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1400284a7  test    eax, eax
0x1400284a9  mov     ebx, eax
0x1400284ab  setnz   r12b
0x1400284af  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1400284b4  mov     r15b, al
0x1400284b7  test    ebx, ebx
0x1400284b9  jnz     short loc_1400284BF
0x1400284bb  test    al, al
0x1400284bd  jz      short loc_14002850E
0x1400284bf  mov     rcx, gs:58h
0x1400284c8  mov     eax, 810h
0x1400284cd  mov     rdx, [rcx]
0x1400284d0  mov     ecx, [rax+rdx]
0x1400284d3  cmp     cs:?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA, ecx
0x1400284d9  jg      loc_14002874A
0x1400284df  cmp     qword ptr [r14+18h], 7
0x1400284e4  jbe     short loc_1400284EB
0x1400284e6  mov     r9, [r14]
0x1400284e9  jmp     short loc_1400284EE
0x1400284eb  mov     r9, r14
0x1400284ee  cmp     qword ptr [rdi+18h], 7
0x1400284f3  jbe     short loc_1400284FA
0x1400284f5  mov     r8, [rdi]
0x1400284f8  jmp     short loc_1400284FD
0x1400284fa  mov     r8, rdi
0x1400284fd  lea     rdx, ?traceParameters@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4UHvsDebugTraceParameters@@B; struct HvsDebugTraceParameters *
0x140028504  mov     ecx, 0C020h; unsigned int
0x140028509  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x14002850e  xor     r12d, r12d
0x140028511  lea     rdx, [rbp+20h+var_A0]
0x140028515  mov     rcx, rsi
0x140028518  mov     [rbp+20h+var_A0], r12
0x14002851c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140028521  mov     rbx, [rsi+110h]
0x140028528  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x14002852d  mov     rcx, [rax+8]
0x140028531  mov     eax, [rcx]
0x140028533  cmp     eax, 5
0x140028536  jbe     short loc_14002855D
0x140028538  mov     edx, 0A0h
0x14002853d  call    _tlgKeywordOn
0x140028542  test    al, al
0x140028544  jz      short loc_14002855D
0x140028546  lea     rdx, [rbx+8]; ActivityId
0x14002854a  lea     ecx, [r12+3]; ControlCode
0x14002854f  call    cs:__imp_EventActivityIdControl
0x140028556  nop     dword ptr [rax+rax+00h]
0x14002855b  jmp     short loc_140028564
0x14002855d  xorps   xmm0, xmm0
0x140028560  movups  xmmword ptr [rbx+8], xmm0
0x140028564  lea     rcx, [rbp+20h+var_A0]
0x140028568  mov     dword ptr [rbx], 1
0x14002856e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140028573  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x140028578  mov     r15d, [rbp+20h+arg_38]
0x14002857c  mov     rbx, [rax+8]
0x140028580  mov     eax, [rbx]
0x140028582  cmp     eax, 5
0x140028585  jbe     loc_1400286E9
0x14002858b  mov     edx, 0A0h
0x140028590  mov     rcx, rbx
0x140028593  call    _tlgKeywordOn
0x140028598  test    al, al
0x14002859a  jz      loc_1400286E9
0x1400285a0  cmp     qword ptr [rdi+18h], 7
0x1400285a5  mov     rcx, [rsi+1C0h]
0x1400285ac  mov     dword ptr [rbp+20h+var_98], r15d
0x1400285b0  mov     [rbp+20h+var_88], r13
0x1400285b4  mov     rax, [rcx+18h]
0x1400285b8  mov     [rbp+20h+var_80], rax
0x1400285bc  mov     eax, [rcx+14h]
0x1400285bf  mov     dword ptr [rbp+20h+var_98+4], eax
0x1400285c2  mov     eax, [rcx+10h]
0x1400285c5  mov     dword ptr [rbp+20h+var_90], eax
0x1400285c8  mov     rax, [rcx+8]
0x1400285cc  mov     [rbp+20h+var_78], rax
0x1400285d0  mov     rax, [rcx]
0x1400285d3  mov     [rbp+20h+var_70], rax
0x1400285d7  mov     [rbp+20h+var_68], rcx
0x1400285db  jbe     short loc_1400285E0
0x1400285dd  mov     rdi, [rdi]
0x1400285e0  cmp     qword ptr [r14+18h], 7
0x1400285e5  mov     rax, [rsi+190h]
0x1400285ec  mov     [rbp+20h+var_58], rax
0x1400285f0  mov     [rbp+20h+var_60], rdi
0x1400285f4  jbe     short loc_1400285F9
0x1400285f6  mov     r14, [r14]
0x1400285f9  lea     rax, [rsi+160h]
0x140028600  mov     [rbp+20h+var_50], r14
0x140028604  mov     [rbp+20h+var_48], rax
0x140028608  lea     rax, [rsi+150h]
0x14002860f  mov     [rbp+20h+var_40], rax
0x140028613  call    cs:__imp_GetCurrentThreadId
0x14002861a  nop     dword ptr [rax+rax+00h]
0x14002861f  mov     r8, [rsi+110h]
0x140028626  mov     dword ptr [rbp+20h+var_A0], eax
0x140028629  mov     [rbp+20h+var_38], r12
0x14002862d  cmp     [r8+4], r12b
0x140028631  jz      short loc_140028640
0x140028633  lea     rcx, [r8+18h]; struct _GUID *
0x140028637  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x14002863c  test    al, al
0x14002863e  jz      short loc_140028643
0x140028640  mov     rcx, r12
0x140028643  lea     rax, [rbp+20h+var_98]
0x140028647  mov     r9, rcx
0x14002864a  mov     [rsp+140h+var_B0], rax; __int64
0x140028652  lea     rdx, dword_140359364; int
0x140028659  lea     rax, [rbp+20h+var_88]
0x14002865d  add     r8, 8; int
0x140028661  mov     [rsp+140h+var_B8], rax; __int64
0x140028669  mov     rcx, rbx; int
0x14002866c  lea     rax, [rbp+20h+var_80]
0x140028670  mov     [rsp+140h+var_C0], rax; __int64
0x140028678  lea     rax, [rbp+20h+var_98+4]
0x14002867c  mov     [rsp+140h+var_C8], rax; __int64
0x140028681  lea     rax, [rbp+20h+var_90]
0x140028685  mov     [rsp+140h+var_D0], rax; __int64
0x14002868a  lea     rax, [rbp+20h+var_78]
0x14002868e  mov     [rsp+140h+var_D8], rax; __int64
0x140028693  lea     rax, [rbp+20h+var_70]
0x140028697  mov     [rsp+140h+var_E0], rax; __int64
0x14002869c  lea     rax, [rbp+20h+var_68]
0x1400286a0  mov     [rsp+140h+var_E8], rax; __int64
0x1400286a5  lea     rax, [rbp+20h+var_60]
0x1400286a9  mov     [rsp+140h+var_F0], rax; __int64
0x1400286ae  lea     rax, [rbp+20h+var_58]
0x1400286b2  mov     [rsp+140h+var_F8], rax; __int64
0x1400286b7  lea     rax, [rbp+20h+var_50]
0x1400286bb  mov     [rsp+140h+var_100], rax; __int64
0x1400286c0  lea     rax, [rbp+20h+var_48]
0x1400286c4  mov     [rsp+140h+var_108], rax; __int64
0x1400286c9  lea     rax, [rbp+20h+var_40]
0x1400286cd  mov     [rsp+140h+var_110], rax; __int64
0x1400286d2  lea     rax, [rbp+20h+var_A0]
0x1400286d6  mov     [rsp+140h+var_118], rax; __int64
0x1400286db  lea     rax, [rbp+20h+var_38]
0x1400286df  mov     [rsp+140h+var_120], rax; __int64
0x1400286e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U3@U?$_tlgWrapSz@G@@U1@U4@U1@U1@U1@U2@U2@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@5AEBU?$_tlgWrapSz@G@@3633344334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400286e9  lea     rcx, [rsi+120h]; this
0x1400286f0  cmp     [rcx+18h], r12d
0x1400286f4  jnz     short loc_1400286FB
0x1400286f6  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1400286fb  cmp     dword ptr [rsi+198h], 5
0x140028702  jnz     short loc_14002872E
0x140028704  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x140028709  test    al, al
0x14002870b  jz      short loc_14002872E
0x14002870d  mov     rax, [rsi+110h]
0x140028714  cmp     dword ptr [rax], 1
0x140028717  jnz     short loc_14002872E
0x140028719  mov     r9d, r15d; unsigned int
0x14002871c  lea     rdx, aActivitystart; "ActivityStart"
0x140028723  mov     r8, r13; void *
0x140028726  mov     rcx, rsi; this
0x140028729  call    ?TraceBufferContent@HyperVAsyncIo@HyperVStorageTrace@@AEAAXPEBGPEBXK@Z; HyperVStorageTrace::HyperVAsyncIo::TraceBufferContent(ushort const *,void const *,ulong)
0x14002872e  mov     rbx, [rsp+140h+arg_8]
0x140028736  add     rsp, 110h
0x14002873d  pop     r15
0x14002873f  pop     r14
0x140028741  pop     r13
0x140028743  pop     r12
0x140028745  pop     rdi
0x140028746  pop     rsi
0x140028747  pop     rbp
0x140028748  retn
0x14002874a  lea     rcx, ?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA
0x140028751  call    _Init_thread_header
0x140028756  cmp     cs:?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA, 0FFFFFFFFh
0x14002875d  jnz     loc_1400284DF
0x140028763  lea     rcx, ?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA
0x14002876a  mov     cs:byte_1403B4114, r12b
0x140028771  mov     cs:byte_1403B4115, r15b
0x140028778  call    _Init_thread_footer
0x14002877d  jmp     loc_1400284DF
```
