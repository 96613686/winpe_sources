# HyperVStorageTrace::HyperVAsyncIo::StartActivity(_GUID,ushort const *,void *,HyperVAsyncIoOperationType,_OVERLAPPED *,void const *,ulong)

- ea: `0x140027e94`
- end: `0x140028212`
- name: `?StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z`
- size: `894`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x140027d84`

## callees

- `0x140006688`
- `0x140023e50`
- `0x1400261fc`
- `0x140027e94`
- `0x1400287c8`
- `0x14002ed20`
- `0x140031cec`
- `0x14004515c`
- `0x1400485a8`
- `0x14004dc30`
- `0x14005613c`
- `0x1400bfa24`
- `0x140133c0c`
- `0x140133c74`
- `0x1401d9f14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400280a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400280a3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140027fdf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140027fdf`
- `RPCRT4!UuidCreate` at `0x140027f21`
- `RPCRT4!UuidCreate` at `0x140027f21`

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
    a3 = &qword_1402E4D20;
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
        byte_1403A8044 = IsDebugTraceEnabled != 0;
        byte_1403A8045 = v17;
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
      (int)&word_14034E86A,
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
0x140027e94  mov     [rsp-8+arg_8], rbx
0x140027e99  push    rbp
0x140027e9a  push    rsi
0x140027e9b  push    rdi
0x140027e9c  push    r12
0x140027e9e  push    r13
0x140027ea0  push    r14
0x140027ea2  push    r15
0x140027ea4  lea     rbp, [rsp+10h]
0x140027ea9  sub     rsp, 110h
0x140027eb0  movups  xmm0, xmmword ptr [rdx]
0x140027eb3  mov     ebx, [rbp+20h+arg_20]
0x140027eb6  lea     rax, qword_1402E4D20
0x140027ebd  mov     r13, [rbp+20h+arg_30]
0x140027ec1  lea     r14, [rcx+170h]
0x140027ec8  test    r8, r8
0x140027ecb  mov     rsi, rcx
0x140027ece  movdqu  xmmword ptr [rcx+150h], xmm0
0x140027ed6  cmovz   r8, rax
0x140027eda  mov     rcx, r14
0x140027edd  mov     rdx, r8
0x140027ee0  mov     rdi, r9
0x140027ee3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140027ee8  mov     [rsi+190h], rdi
0x140027eef  lea     rax, ?g_OperationNames@?1??HvsGetOperationName@@YAPEBGW4HyperVAsyncIoOperationType@@@Z@4QBQEBGB; ushort const * const near * const `HvsGetOperationName(HyperVAsyncIoOperationType)'::`2'::g_OperationNames
0x140027ef6  mov     rdx, [rax+rbx*8]
0x140027efa  lea     rdi, [rsi+1A0h]
0x140027f01  mov     rcx, rdi
0x140027f04  mov     [rsi+198h], ebx
0x140027f0a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x140027f0f  mov     rax, [rbp+20h+arg_28]
0x140027f13  lea     rcx, [rsi+160h]; Uuid
0x140027f1a  mov     [rsi+1C0h], rax
0x140027f21  call    cs:__imp_UuidCreate
0x140027f28  nop     dword ptr [rax+rax+00h]
0x140027f2d  mov     ecx, 0C020h; unsigned __int16
0x140027f32  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x140027f37  test    eax, eax
0x140027f39  mov     ebx, eax
0x140027f3b  setnz   r12b
0x140027f3f  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x140027f44  mov     r15b, al
0x140027f47  test    ebx, ebx
0x140027f49  jnz     short loc_140027F4F
0x140027f4b  test    al, al
0x140027f4d  jz      short loc_140027F9E
0x140027f4f  mov     rcx, gs:58h
0x140027f58  mov     eax, 810h
0x140027f5d  mov     rdx, [rcx]
0x140027f60  mov     ecx, [rax+rdx]
0x140027f63  cmp     cs:?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA, ecx
0x140027f69  jg      loc_1400281DA
0x140027f6f  cmp     qword ptr [r14+18h], 7
0x140027f74  jbe     short loc_140027F7B
0x140027f76  mov     r9, [r14]
0x140027f79  jmp     short loc_140027F7E
0x140027f7b  mov     r9, r14
0x140027f7e  cmp     qword ptr [rdi+18h], 7
0x140027f83  jbe     short loc_140027F8A
0x140027f85  mov     r8, [rdi]
0x140027f88  jmp     short loc_140027F8D
0x140027f8a  mov     r8, rdi
0x140027f8d  lea     rdx, ?traceParameters@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4UHvsDebugTraceParameters@@B; struct HvsDebugTraceParameters *
0x140027f94  mov     ecx, 0C020h; unsigned int
0x140027f99  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x140027f9e  xor     r12d, r12d
0x140027fa1  lea     rdx, [rbp+20h+var_A0]
0x140027fa5  mov     rcx, rsi
0x140027fa8  mov     [rbp+20h+var_A0], r12
0x140027fac  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140027fb1  mov     rbx, [rsi+110h]
0x140027fb8  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x140027fbd  mov     rcx, [rax+8]
0x140027fc1  mov     eax, [rcx]
0x140027fc3  cmp     eax, 5
0x140027fc6  jbe     short loc_140027FED
0x140027fc8  mov     edx, 0A0h
0x140027fcd  call    _tlgKeywordOn
0x140027fd2  test    al, al
0x140027fd4  jz      short loc_140027FED
0x140027fd6  lea     rdx, [rbx+8]; ActivityId
0x140027fda  lea     ecx, [r12+3]; ControlCode
0x140027fdf  call    cs:__imp_EventActivityIdControl
0x140027fe6  nop     dword ptr [rax+rax+00h]
0x140027feb  jmp     short loc_140027FF4
0x140027fed  xorps   xmm0, xmm0
0x140027ff0  movups  xmmword ptr [rbx+8], xmm0
0x140027ff4  lea     rcx, [rbp+20h+var_A0]
0x140027ff8  mov     dword ptr [rbx], 1
0x140027ffe  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140028003  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x140028008  mov     r15d, [rbp+20h+arg_38]
0x14002800c  mov     rbx, [rax+8]
0x140028010  mov     eax, [rbx]
0x140028012  cmp     eax, 5
0x140028015  jbe     loc_140028179
0x14002801b  mov     edx, 0A0h
0x140028020  mov     rcx, rbx
0x140028023  call    _tlgKeywordOn
0x140028028  test    al, al
0x14002802a  jz      loc_140028179
0x140028030  cmp     qword ptr [rdi+18h], 7
0x140028035  mov     rcx, [rsi+1C0h]
0x14002803c  mov     dword ptr [rbp+20h+var_98], r15d
0x140028040  mov     [rbp+20h+var_88], r13
0x140028044  mov     rax, [rcx+18h]
0x140028048  mov     [rbp+20h+var_80], rax
0x14002804c  mov     eax, [rcx+14h]
0x14002804f  mov     dword ptr [rbp+20h+var_98+4], eax
0x140028052  mov     eax, [rcx+10h]
0x140028055  mov     dword ptr [rbp+20h+var_90], eax
0x140028058  mov     rax, [rcx+8]
0x14002805c  mov     [rbp+20h+var_78], rax
0x140028060  mov     rax, [rcx]
0x140028063  mov     [rbp+20h+var_70], rax
0x140028067  mov     [rbp+20h+var_68], rcx
0x14002806b  jbe     short loc_140028070
0x14002806d  mov     rdi, [rdi]
0x140028070  cmp     qword ptr [r14+18h], 7
0x140028075  mov     rax, [rsi+190h]
0x14002807c  mov     [rbp+20h+var_58], rax
0x140028080  mov     [rbp+20h+var_60], rdi
0x140028084  jbe     short loc_140028089
0x140028086  mov     r14, [r14]
0x140028089  lea     rax, [rsi+160h]
0x140028090  mov     [rbp+20h+var_50], r14
0x140028094  mov     [rbp+20h+var_48], rax
0x140028098  lea     rax, [rsi+150h]
0x14002809f  mov     [rbp+20h+var_40], rax
0x1400280a3  call    cs:__imp_GetCurrentThreadId
0x1400280aa  nop     dword ptr [rax+rax+00h]
0x1400280af  mov     r8, [rsi+110h]
0x1400280b6  mov     dword ptr [rbp+20h+var_A0], eax
0x1400280b9  mov     [rbp+20h+var_38], r12
0x1400280bd  cmp     [r8+4], r12b
0x1400280c1  jz      short loc_1400280D0
0x1400280c3  lea     rcx, [r8+18h]; struct _GUID *
0x1400280c7  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1400280cc  test    al, al
0x1400280ce  jz      short loc_1400280D3
0x1400280d0  mov     rcx, r12
0x1400280d3  lea     rax, [rbp+20h+var_98]
0x1400280d7  mov     r9, rcx
0x1400280da  mov     [rsp+140h+var_B0], rax; __int64
0x1400280e2  lea     rdx, word_14034E86A; int
0x1400280e9  lea     rax, [rbp+20h+var_88]
0x1400280ed  add     r8, 8; int
0x1400280f1  mov     [rsp+140h+var_B8], rax; __int64
0x1400280f9  mov     rcx, rbx; int
0x1400280fc  lea     rax, [rbp+20h+var_80]
0x140028100  mov     [rsp+140h+var_C0], rax; __int64
0x140028108  lea     rax, [rbp+20h+var_98+4]
0x14002810c  mov     [rsp+140h+var_C8], rax; __int64
0x140028111  lea     rax, [rbp+20h+var_90]
0x140028115  mov     [rsp+140h+var_D0], rax; __int64
0x14002811a  lea     rax, [rbp+20h+var_78]
0x14002811e  mov     [rsp+140h+var_D8], rax; __int64
0x140028123  lea     rax, [rbp+20h+var_70]
0x140028127  mov     [rsp+140h+var_E0], rax; __int64
0x14002812c  lea     rax, [rbp+20h+var_68]
0x140028130  mov     [rsp+140h+var_E8], rax; __int64
0x140028135  lea     rax, [rbp+20h+var_60]
0x140028139  mov     [rsp+140h+var_F0], rax; __int64
0x14002813e  lea     rax, [rbp+20h+var_58]
0x140028142  mov     [rsp+140h+var_F8], rax; __int64
0x140028147  lea     rax, [rbp+20h+var_50]
0x14002814b  mov     [rsp+140h+var_100], rax; __int64
0x140028150  lea     rax, [rbp+20h+var_48]
0x140028154  mov     [rsp+140h+var_108], rax; __int64
0x140028159  lea     rax, [rbp+20h+var_40]
0x14002815d  mov     [rsp+140h+var_110], rax; __int64
0x140028162  lea     rax, [rbp+20h+var_A0]
0x140028166  mov     [rsp+140h+var_118], rax; __int64
0x14002816b  lea     rax, [rbp+20h+var_38]
0x14002816f  mov     [rsp+140h+var_120], rax; __int64
0x140028174  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U3@U?$_tlgWrapSz@G@@U1@U4@U1@U1@U1@U2@U2@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@5AEBU?$_tlgWrapSz@G@@3633344334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140028179  lea     rcx, [rsi+120h]; this
0x140028180  cmp     [rcx+18h], r12d
0x140028184  jnz     short loc_14002818B
0x140028186  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14002818b  cmp     dword ptr [rsi+198h], 5
0x140028192  jnz     short loc_1400281BE
0x140028194  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x140028199  test    al, al
0x14002819b  jz      short loc_1400281BE
0x14002819d  mov     rax, [rsi+110h]
0x1400281a4  cmp     dword ptr [rax], 1
0x1400281a7  jnz     short loc_1400281BE
0x1400281a9  mov     r9d, r15d; unsigned int
0x1400281ac  lea     rdx, aActivitystart; "ActivityStart"
0x1400281b3  mov     r8, r13; void *
0x1400281b6  mov     rcx, rsi; this
0x1400281b9  call    ?TraceBufferContent@HyperVAsyncIo@HyperVStorageTrace@@AEAAXPEBGPEBXK@Z; HyperVStorageTrace::HyperVAsyncIo::TraceBufferContent(ushort const *,void const *,ulong)
0x1400281be  mov     rbx, [rsp+140h+arg_8]
0x1400281c6  add     rsp, 110h
0x1400281cd  pop     r15
0x1400281cf  pop     r14
0x1400281d1  pop     r13
0x1400281d3  pop     r12
0x1400281d5  pop     rdi
0x1400281d6  pop     rsi
0x1400281d7  pop     rbp
0x1400281d8  retn
0x1400281da  lea     rcx, ?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA
0x1400281e1  call    _Init_thread_header
0x1400281e6  cmp     cs:?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA, 0FFFFFFFFh
0x1400281ed  jnz     loc_140027F6F
0x1400281f3  lea     rcx, ?$TSS0@?8??StartActivity@HyperVAsyncIo@HyperVStorageTrace@@QEAAXU_GUID@@PEBGPEAXW4HyperVAsyncIoOperationType@@PEAU_OVERLAPPED@@PEBXK@Z@4HA
0x1400281fa  mov     cs:byte_1403A8044, r12b
0x140028201  mov     cs:byte_1403A8045, r15b
0x140028208  call    _Init_thread_footer
0x14002820d  jmp     loc_140027F6F
```
