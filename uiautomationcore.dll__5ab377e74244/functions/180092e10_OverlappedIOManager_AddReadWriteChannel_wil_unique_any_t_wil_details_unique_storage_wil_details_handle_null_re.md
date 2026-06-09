# OverlappedIOManager::AddReadWriteChannel(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard,std::default_delete<BasicUtils::CrossMachinePipeNameGuard>>,IReadWriteChannelCallback *,IReadWriteChannel * *,std::vector<uchar,std::allocator<uchar>>,bool,uint,bool)

- ea: `0x180092e10`
- end: `0x180093272`
- name: `?AddReadWriteChannel@OverlappedIOManager@@QEAAJV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@std@@PEAUIReadWriteChannelCallback@@PEAPEAUIReadWriteChannel@@V?$vector@EV?$allocator@E@std@@@5@_NI5@Z`
- size: `1122`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005ca40`
- `0x1801091e0`

## callees

- `0x18002f580`
- `0x180091924`
- `0x180091b98`
- `0x180091e38`
- `0x180092df4`
- `0x180092e10`
- `0x1800948b8`
- `0x1800be9c8`
- `0x1801ab2a4`
- `0x1801e887c`
- `0x1801fd9f8`
- `0x180235c74`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180092ffe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180093033`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180092ffe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180093033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093045`

## string_xrefs

- `0x180092f41`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x18009317f`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x1800931eb`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`
- `0x180093205`: `onecore\windows\accessibletech\uiautomationcore\overlappediomanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OverlappedIOManager::AddReadWriteChannel(
        OverlappedIOManager *a1,
        __int64 *a2,
        struct ChannelInfo **a3,
        __int64 a4,
        struct ChannelInfo **a5,
        _QWORD *a6,
        char a7,
        int a8,
        unsigned __int8 a9)
{
  signed int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // r8
  struct ChannelInfo *v14; // r13
  int v15; // eax
  int v16; // edx
  int v17; // ecx
  int v18; // r15d
  __int64 v19; // rcx
  __int64 v21; // rcx
  HANDLE EventW; // r13
  signed int LastError; // eax
  HANDLE v24; // r15
  signed int v25; // eax
  struct ChannelInfo *v26; // rax
  struct ChannelInfo *v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rcx
  int v31; // [rsp+20h] [rbp-58h]
  HANDLE v32; // [rsp+40h] [rbp-38h] BYREF
  HANDLE v33; // [rsp+48h] [rbp-30h] BYREF
  __int64 v34; // [rsp+50h] [rbp-28h] BYREF
  struct ChannelInfo *v35; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  if ( ((*a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v11 = Error::InternalErrorWorker(L"handle should be non-null");
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v30 = L"callback should be non-null";
LABEL_42:
    v11 = Error::InternalErrorWorker(v30);
    goto LABEL_39;
  }
  if ( !*((_DWORD *)a1 + 22) )
  {
    v30 = L"called before inited";
    goto LABEL_42;
  }
  *a5 = 0;
  EventW = CreateEventW(0, 1, 1, 0);
  v32 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x427,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
        (const char *)(unsigned int)v11,
        v31);
      goto LABEL_38;
    }
  }
  v24 = CreateEventW(0, 1, 1, 0);
  v33 = v24;
  if ( !v24 )
  {
    v25 = GetLastError();
    v11 = v25;
    if ( v25 > 0 )
      v11 = (unsigned __int16)v25 | 0x80070000;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x429,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
        (const char *)(unsigned int)v11,
        v31);
      goto LABEL_37;
    }
  }
  v26 = (struct ChannelInfo *)operator new(0x10C0u, (const struct std::nothrow_t *)std::nothrow);
  v27 = v26;
  v35 = v26;
  if ( v26 )
  {
    v35 = *a3;
    *a3 = 0;
    v28 = *a2;
    v34 = *a2;
    *a2 = 0;
    *(_QWORD *)(&v26->ATSC + 1) = 0;
    *(_QWORD *)&v26[1].lFrequency = 0;
    *(_QWORD *)(&v26[1].ATSC + 1) = a1;
    *(_QWORD *)&v26->lFrequency = &ReadWriteChannelInfo::`vftable'{for `ChannelInfo'};
    *(_QWORD *)&v26[2].lFrequency = &ReadWriteChannelInfo::`vftable'{for `IReadWriteChannel'};
    *(_QWORD *)(&v26[4].ATSC + 1) = 0;
    *(_QWORD *)&v26[5].lFrequency = 0;
    *(_QWORD *)(&v26[5].ATSC + 1) = 0;
    *(_QWORD *)(&v26[264].ATSC + 1) = 0;
    v26[265].lFrequency = 0;
    *(_QWORD *)(&v26[265].ATSC + 1) = 0;
    v26[266].lFrequency = 0;
    *(_QWORD *)(&v26[266].ATSC + 1) = 0;
    *(_QWORD *)&v26[267].lFrequency = 0;
    *((_BYTE *)&v26[267].ATSC + 8) = 0;
    if ( &v26[4].ATSC + 1 != (struct _ChannelInfo::$A19F8CC3FA49014D8618ED22280592FE::$D8EDD8813E9D2C777B4C66E2AEE9CFF4 *)&v34 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v26[4].ATSC + 1,
        v28);
      v34 = 0;
    }
    v29 = *(_QWORD *)&v27[5].lFrequency;
    *(_QWORD *)&v27[5].lFrequency = v35;
    if ( v29 )
      ((void (*)(void))std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator())();
    *(_QWORD *)&v27[3].lFrequency = EventW;
    *(_QWORD *)(&v27[3].ATSC + 1) = v24;
    *(_QWORD *)&v27[4].lFrequency = a4;
    v27[2].DVB.lTSID = 0;
    *(_QWORD *)(&v27[264].ATSC + 1) = v27 + 8;
    v27[265].lFrequency = 4096;
    *(_QWORD *)(&v27[266].ATSC + 1) = v27 + 8;
    v27[266].lFrequency = 4096;
    *(_QWORD *)(&v27[265].ATSC + 1) = v27 + 8;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
  }
  else
  {
    v27 = 0;
  }
  v35 = v27;
  if ( !v27 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42C,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
      (const char *)0x8007000ELL,
      v31);
LABEL_37:
    AutoCleanupInfo<void *>::SafeRelease(&v33);
LABEL_38:
    AutoCleanupInfo<void *>::SafeRelease(&v32);
LABEL_39:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
LABEL_3:
    if ( *a3 )
      std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(v12, *a3);
    goto LABEL_13;
  }
  v32 = 0;
  v33 = 0;
  v13 = a6[1];
  v14 = v27 + 2;
  if ( *a6 == v13 )
    goto LABEL_10;
  LOBYTE(v31) = 1;
  v15 = (*(__int64 (__fastcall **)(LONG *, _QWORD, _QWORD, __int64))(*(_QWORD *)&v14->lFrequency + 16LL))(
          &v27[2].lFrequency,
          *a6,
          (unsigned int)(v13 - *(_DWORD *)a6),
          0xFFFFFFFFLL);
  v18 = v15;
  if ( a7 )
  {
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0qqtqqd_EventWriteTransfer(
        a9,
        *((_DWORD *)a6 + 2) - *(_DWORD *)a6,
        1,
        a8,
        a9,
        *((_BYTE *)a6 + 8) - *(_BYTE *)a6,
        0,
        v15);
  }
  else if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
  {
    McTemplateU0qqqd_EventWriteTransfer(v17, v16, 1, a8, *((_BYTE *)a6 + 8) - *(_BYTE *)a6, v15);
  }
  if ( v18 >= 0 )
  {
LABEL_10:
    v35 = 0;
    OverlappedIOManager::AddChannel_AnyThread(a1, v27, 1);
    *a5 = v14;
    AutoCleanupInfo<void *>::SafeRelease(&v33);
    AutoCleanupInfo<void *>::SafeRelease(&v32);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
    if ( *a3 )
      std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(v19, *a3);
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43F,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\overlappediomanager.cpp",
      (const char *)(unsigned int)v18,
      v31);
    (*(void (__fastcall **)(struct ChannelInfo *, __int64))(*(_QWORD *)&v27->lFrequency + 24LL))(v27, 1);
    AutoCleanupInfo<void *>::SafeRelease(&v33);
    AutoCleanupInfo<void *>::SafeRelease(&v32);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
    if ( *a3 )
      std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(v21, *a3);
    v11 = v18;
  }
LABEL_13:
  std::vector<unsigned char>::_Tidy(a6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180092e10  mov     rax, rsp
0x180092e13  mov     [rax+20h], r9
0x180092e17  mov     [rax+18h], r8
0x180092e1b  mov     [rax+10h], rdx
0x180092e1f  mov     [rax+8], rcx
0x180092e23  push    rbp
0x180092e24  push    rbx
0x180092e25  push    rsi
0x180092e26  push    rdi
0x180092e27  push    r12
0x180092e29  push    r13
0x180092e2b  push    r14
0x180092e2d  push    r15
0x180092e2f  mov     rbp, rsp
0x180092e32  sub     rsp, 78h
0x180092e36  mov     r14, r8
0x180092e39  mov     rsi, rdx
0x180092e3c  mov     rax, [rdx]
0x180092e3f  mov     r15d, 1
0x180092e45  add     rax, r15
0x180092e48  mov     r12, [rbp+arg_28]
0x180092e4c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180092e52  jnz     loc_180092FD8
0x180092e58  lea     rcx, aHandleShouldBe; "handle should be non-null"
0x180092e5f  call    ?InternalErrorWorker@Error@@SAJPEBG@Z; Error::InternalErrorWorker(ushort const *)
0x180092e64  mov     edi, eax
0x180092e66  mov     rcx, rsi
0x180092e69  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180092e6e  nop
0x180092e6f  xor     ebx, ebx
0x180092e71  cmp     [r14], rbx
0x180092e74  jz      loc_180092F1F
0x180092e7a  mov     rdx, [r14]
0x180092e7d  call    ??R?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@QEBAXPEAUCrossMachinePipeNameGuard@BasicUtils@@@Z; std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(BasicUtils::CrossMachinePipeNameGuard *)
0x180092e82  jmp     loc_180092F1F
0x180092e87  mov     [rbp+var_38], rbx
0x180092e8b  mov     [rbp+var_30], rbx
0x180092e8f  mov     r8, [r12+8]
0x180092e94  lea     r13, [rdi+20h]
0x180092e98  cmp     [r12], r8
0x180092e9c  jz      short loc_180092EDD
0x180092e9e  mov     rax, [r13+0]
0x180092ea2  sub     r8d, [r12]
0x180092ea6  mov     byte ptr [rsp+78h+var_58], 1; int
0x180092eab  or      r9d, 0FFFFFFFFh
0x180092eaf  mov     rdx, [r12]
0x180092eb3  mov     rcx, r13
0x180092eb6  mov     rax, [rax+10h]
0x180092eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ebf  mov     r15d, eax
0x180092ec2  cmp     [rbp+arg_30], bl
0x180092ec5  jnz     loc_180092F93
0x180092ecb  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180092ed2  jnz     loc_18009322E
0x180092ed8  test    r15d, r15d
0x180092edb  js      short loc_180092F3A
0x180092edd  mov     [rbp+var_20], rbx
0x180092ee1  mov     r8b, 1; bool
0x180092ee4  mov     rdx, rdi; struct ChannelInfo *
0x180092ee7  mov     rcx, [rbp+arg_0]; this
0x180092eeb  call    ?AddChannel_AnyThread@OverlappedIOManager@@AEAAJPEAVChannelInfo@@_N@Z; OverlappedIOManager::AddChannel_AnyThread(ChannelInfo *,bool)
0x180092ef0  mov     rax, [rbp+arg_20]
0x180092ef4  mov     [rax], r13
0x180092ef7  lea     rcx, [rbp+var_30]
0x180092efb  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x180092f00  nop
0x180092f01  lea     rcx, [rbp+var_38]
0x180092f05  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x180092f0a  nop
0x180092f0b  mov     rcx, rsi
0x180092f0e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180092f13  nop
0x180092f14  cmp     [r14], rbx
0x180092f17  jnz     loc_180093264
0x180092f1d  mov     edi, ebx
0x180092f1f  mov     rcx, r12
0x180092f22  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180092f27  mov     eax, edi
0x180092f29  add     rsp, 78h
0x180092f2d  pop     r15
0x180092f2f  pop     r14
0x180092f31  pop     r13
0x180092f33  pop     r12
0x180092f35  pop     rdi
0x180092f36  pop     rsi
0x180092f37  pop     rbx
0x180092f38  pop     rbp
0x180092f39  retn
0x180092f3a  mov     rcx, [rbp+40h]; this
0x180092f3e  mov     r9d, r15d; char *
0x180092f41  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x180092f48  mov     edx, 43Fh; void *
0x180092f4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092f52  nop
0x180092f53  mov     rax, [rdi]
0x180092f56  mov     edx, 1
0x180092f5b  mov     rcx, rdi
0x180092f5e  mov     rax, [rax+18h]
0x180092f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092f67  nop
0x180092f68  lea     rcx, [rbp+var_30]
0x180092f6c  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x180092f71  nop
0x180092f72  lea     rcx, [rbp+var_38]
0x180092f76  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x180092f7b  nop
0x180092f7c  mov     rcx, rsi
0x180092f7f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180092f84  nop
0x180092f85  cmp     [r14], rbx
0x180092f88  jnz     loc_180093257
0x180092f8e  mov     edi, r15d
0x180092f91  jmp     short loc_180092F1F
0x180092f93  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180092f9a  jz      loc_180092ED8
0x180092fa0  mov     edx, [r12+8]
0x180092fa5  sub     edx, [r12]
0x180092fa9  movzx   ecx, [rbp+arg_40]
0x180092fb0  mov     [rsp+78h+var_40], r15d
0x180092fb5  mov     [rsp+78h+var_48], ebx
0x180092fb9  mov     [rsp+78h+var_50], edx
0x180092fbd  mov     [rsp+78h+var_58], ecx
0x180092fc1  mov     r9d, [rbp+arg_38]
0x180092fc8  mov     r8d, 1
0x180092fce  call    McTemplateU0qqtqqd_EventWriteTransfer
0x180092fd3  jmp     loc_180092ED8
0x180092fd8  xor     ebx, ebx
0x180092fda  test    r9, r9
0x180092fdd  jz      loc_1800931D4
0x180092fe3  cmp     [rcx+58h], ebx
0x180092fe6  jz      loc_18009321B
0x180092fec  mov     rax, [rbp+arg_20]
0x180092ff0  mov     [rax], rbx
0x180092ff3  xor     r9d, r9d; lpName
0x180092ff6  mov     r8d, r15d; bInitialState
0x180092ff9  mov     edx, r15d; bManualReset
0x180092ffc  xor     ecx, ecx; lpEventAttributes
0x180092ffe  call    cs:__imp_CreateEventW
0x180093004  mov     r13, rax
0x180093007  mov     [rbp+var_38], rax
0x18009300b  test    rax, rax
0x18009300e  jnz     short loc_180093028
0x180093010  call    cs:__imp_GetLastError
0x180093016  mov     edi, eax
0x180093018  test    eax, eax
0x18009301a  jg      loc_1800931B8
0x180093020  test    edi, edi
0x180093022  js      loc_1800931E4
0x180093028  xor     r9d, r9d; lpName
0x18009302b  mov     r8d, r15d; bInitialState
0x18009302e  mov     edx, r15d; bManualReset
0x180093031  xor     ecx, ecx; lpEventAttributes
0x180093033  call    cs:__imp_CreateEventW
0x180093039  mov     r15, rax
0x18009303c  mov     [rbp+var_30], rax
0x180093040  test    rax, rax
0x180093043  jnz     short loc_18009305D
0x180093045  call    cs:__imp_GetLastError
0x18009304b  mov     edi, eax
0x18009304d  test    eax, eax
0x18009304f  jg      loc_1800931C6
0x180093055  test    edi, edi
0x180093057  js      loc_1800931FE
0x18009305d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180093064  mov     ecx, 10C0h; unsigned __int64
0x180093069  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009306e  mov     rdi, rax
0x180093071  mov     [rbp+var_20], rax
0x180093075  test    rax, rax
0x180093078  jz      loc_1800931B3
0x18009307e  mov     rax, [r14]
0x180093081  mov     [rbp+var_20], rax
0x180093085  mov     [r14], rbx
0x180093088  mov     rdx, [rsi]
0x18009308b  mov     [rbp+var_28], rdx
0x18009308f  mov     [rsi], rbx
0x180093092  mov     [rdi+8], rbx
0x180093096  mov     [rdi+10h], rbx
0x18009309a  mov     rax, [rbp+arg_0]
0x18009309e  mov     [rdi+18h], rax
0x1800930a2  lea     rax, ??_7ReadWriteChannelInfo@@6BChannelInfo@@@; const ReadWriteChannelInfo::`vftable'{for `ChannelInfo'}
0x1800930a9  mov     [rdi], rax
0x1800930ac  lea     rax, ??_7ReadWriteChannelInfo@@6BIReadWriteChannel@@@; const ReadWriteChannelInfo::`vftable'{for `IReadWriteChannel'}
0x1800930b3  mov     [rdi+20h], rax
0x1800930b7  lea     rcx, [rdi+48h]
0x1800930bb  mov     [rcx], rbx
0x1800930be  mov     [rdi+50h], rbx
0x1800930c2  xor     eax, eax
0x1800930c4  mov     [rdi+58h], rax
0x1800930c8  mov     [rdi+1088h], rbx
0x1800930cf  mov     [rdi+1090h], ebx
0x1800930d5  mov     [rdi+1098h], rbx
0x1800930dc  mov     [rdi+10A0h], ebx
0x1800930e2  mov     [rdi+10A8h], rbx
0x1800930e9  mov     [rdi+10B0h], rax
0x1800930f0  mov     [rdi+10BCh], bl
0x1800930f6  lea     rax, [rbp+var_28]
0x1800930fa  cmp     rcx, rax
0x1800930fd  jz      short loc_180093108
0x1800930ff  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180093104  mov     [rbp+var_28], rbx
0x180093108  mov     rdx, [rdi+50h]
0x18009310c  mov     rax, [rbp+var_20]
0x180093110  mov     [rdi+50h], rax
0x180093114  test    rdx, rdx
0x180093117  jnz     loc_180093224
0x18009311d  mov     [rdi+30h], r13
0x180093121  mov     [rdi+38h], r15
0x180093125  mov     rax, [rbp+arg_18]
0x180093129  mov     [rdi+40h], rax
0x18009312d  mov     [rdi+28h], ebx
0x180093130  lea     rax, [rdi+80h]
0x180093137  mov     [rdi+1088h], rax
0x18009313e  mov     ecx, 1000h
0x180093143  mov     [rdi+1090h], ecx
0x180093149  mov     [rdi+10A8h], rax
0x180093150  mov     [rdi+10A0h], ecx
0x180093156  mov     [rdi+1098h], rax
0x18009315d  lea     rcx, [rbp+var_28]
0x180093161  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180093166  mov     [rbp+var_20], rdi
0x18009316a  test    rdi, rdi
0x18009316d  jnz     loc_180092E87
0x180093173  mov     rcx, [rbp+40h]; this
0x180093177  mov     edi, 8007000Eh
0x18009317c  mov     r9d, edi; char *
0x18009317f  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x180093186  mov     edx, 42Ch; void *
0x18009318b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093190  nop
0x180093191  lea     rcx, [rbp+var_30]
0x180093195  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18009319a  nop
0x18009319b  lea     rcx, [rbp+var_38]
0x18009319f  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x1800931a4  nop
0x1800931a5  mov     rcx, rsi
0x1800931a8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800931ad  nop
0x1800931ae  jmp     loc_180092E71
0x1800931b3  mov     rdi, rbx
0x1800931b6  jmp     short loc_180093166
0x1800931b8  movzx   edi, ax
0x1800931bb  or      edi, 80070000h
0x1800931c1  jmp     loc_180093020
0x1800931c6  movzx   edi, ax
0x1800931c9  or      edi, 80070000h
0x1800931cf  jmp     loc_180093055
0x1800931d4  lea     rcx, aCallbackShould; "callback should be non-null"
0x1800931db  call    ?InternalErrorWorker@Error@@SAJPEBG@Z; Error::InternalErrorWorker(ushort const *)
0x1800931e0  mov     edi, eax
0x1800931e2  jmp     short loc_1800931A5
0x1800931e4  mov     rcx, [rbp+40h]; this
0x1800931e8  mov     r9d, edi; char *
0x1800931eb  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x1800931f2  mov     edx, 427h; void *
0x1800931f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800931fc  jmp     short loc_18009319B
0x1800931fe  mov     rcx, [rbp+40h]; this
0x180093202  mov     r9d, edi; char *
0x180093205  lea     r8, aOnecoreWindows_101; "onecore\\windows\\accessibletech\\uiaut"...
0x18009320c  mov     edx, 429h; void *
0x180093211  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093216  jmp     loc_180093191
0x18009321b  lea     rcx, aCalledBeforeIn; "called before inited"
0x180093222  jmp     short loc_1800931DB
0x180093224  call    ??R?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@QEBAXPEAUCrossMachinePipeNameGuard@BasicUtils@@@Z; std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(BasicUtils::CrossMachinePipeNameGuard *)
0x180093229  jmp     loc_18009311D
0x18009322e  mov     eax, [r12+8]
0x180093233  sub     eax, [r12]
0x180093237  mov     [rsp+78h+var_50], r15d
0x18009323c  mov     [rsp+78h+var_58], eax
0x180093240  mov     r9d, [rbp+arg_38]
0x180093247  mov     r8d, 1
0x18009324d  call    McTemplateU0qqqd_EventWriteTransfer
0x180093252  jmp     loc_180092ED8
0x180093257  mov     rdx, [r14]
0x18009325a  call    ??R?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@QEBAXPEAUCrossMachinePipeNameGuard@BasicUtils@@@Z; std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(BasicUtils::CrossMachinePipeNameGuard *)
0x18009325f  jmp     loc_180092F8E
0x180093264  mov     rdx, [r14]
0x180093267  call    ??R?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@QEBAXPEAUCrossMachinePipeNameGuard@BasicUtils@@@Z; std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(BasicUtils::CrossMachinePipeNameGuard *)
0x18009326c  jmp     loc_180092F1D
```
