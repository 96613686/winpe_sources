# ?Advise@?QIIdentityProvider@@CWindowsLiveProvider@@UEAAJPEAUIIdentityAdvise@@KPEAK@Z

- ea: `0x18000e0a0`
- end: `0x18000e3d5`
- name: `?Advise@?QIIdentityProvider@@CWindowsLiveProvider@@UEAAJPEAUIIdentityAdvise@@KPEAK@Z`
- size: `821`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18000bcc4`
- `0x18000e0a0`
- `0x18000e3dc`
- `0x18000e408`
- `0x18000e48c`
- `0x18000e720`
- `0x18000f0d8`
- `0x18001ca08`
- `0x18004db08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e1d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e2b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e2dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e1d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e2b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e2dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e14f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e14f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e22d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e33a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _Advise__QIIdentityProvider__CWindowsLiveProvider__UEAAJPEAUIIdentityAdvise__KPEAK_Z(
        __int64 a1,
        struct IUnknown *a2,
        int a3,
        _DWORD *a4)
{
  struct IUnknown **v8; // rax
  struct IUnknown **v9; // rbx
  CWLIDNotifyItem *v10; // rax
  CWLIDNotifyItem *v11; // rdi
  unsigned int v12; // edx
  struct IUnknown *EventW; // rax
  bool v15; // r9
  struct IUnknown *v16; // r13
  HANDLE v17; // rax
  signed int LastError; // eax
  unsigned int v19; // edx
  unsigned int v20; // edx
  const unsigned __int16 *v21; // [rsp+20h] [rbp-98h]
  __int64 v22; // [rsp+20h] [rbp-98h]
  int v23; // [rsp+30h] [rbp-88h] BYREF
  CWLIDNotifyItem *v24; // [rsp+38h] [rbp-80h]
  __int64 v25; // [rsp+40h] [rbp-78h]
  ATL::CAtlException *v26; // [rsp+48h] [rbp-70h] BYREF
  CPassportException *v27; // [rsp+50h] [rbp-68h] BYREF
  __int64 v28; // [rsp+58h] [rbp-60h] BYREF
  char v29; // [rsp+60h] [rbp-58h]
  _QWORD v30[5]; // [rsp+68h] [rbp-50h] BYREF
  int v31; // [rsp+C8h] [rbp+10h] BYREF
  _DWORD *v32; // [rsp+D8h] [rbp+20h]

  v32 = a4;
  v31 = 0;
  v30[0] = "CWindowsLiveProvider::Advise";
  v30[1] = &v31;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "CWindowsLiveProvider::Advise",
    (const char *)0x40D,
    0,
    v21);
  if ( !a2 || !a3 || !a4 )
  {
    v31 = -2147024809;
    CTraceFuncW<long>::~CTraceFuncW<long>(v30);
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
  }
  LODWORD(v22) = a3;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    0x418u,
    L"Events: (0x%x)",
    v22);
  v28 = a1 + 184;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  v29 = 1;
  if ( *(_DWORD *)(a1 + 176) >= 0xFFFFFFFE )
  {
    v31 = -2147024809;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
    CTraceFuncW<long>::~CTraceFuncW<long>(v30);
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
  }
  v8 = (struct IUnknown **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    *v8 = 0;
    v8[3] = 0;
    v8[1] = 0;
    v8[2] = 0;
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    v31 = -2147024882;
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v28);
    CTraceFuncW<long>::~CTraceFuncW<long>(v30);
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
  }
  v10 = (CWLIDNotifyItem *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  v24 = v10;
  if ( !v10 )
  {
    v31 = -2147024882;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
    CTraceFuncW<long>::~CTraceFuncW<long>(v30);
    _WLIDNotifyParam::`scalar deleting destructor'((_WLIDNotifyParam *)v9, v12);
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
  }
  *(_QWORD *)v10 = 0;
  *((_QWORD *)v10 + 1) = 0;
  v24 = v10;
  EventW = (struct IUnknown *)CreateEventW(0, 1, 0, 0);
  v16 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_21;
  }
  *(_DWORD *)v9 = a3;
  if ( v9[1] != a2 )
    ATL::AtlComPtrAssign(v9 + 1, a2);
  v9[3] = v16;
  *((_QWORD *)v11 + 1) = v16;
  v17 = IDCRLCreateThread((LPTHREAD_START_ROUTINE)NotificationThread, v9, (void *)1, v15);
  *(_QWORD *)v11 = v17;
  if ( !v17 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_21:
    v31 = LastError;
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v28);
    CTraceFuncW<long>::~CTraceFuncW<long>(v30);
    CWLIDNotifyItem::`scalar deleting destructor'(v11, v19);
    _WLIDNotifyParam::`scalar deleting destructor'((_WLIDNotifyParam *)v9, v20);
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
  }
  try
  {
    v25 = 0;
    *(_QWORD *)ATL::CAtlMap<unsigned long,CWLIDNotifyItem *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CWLIDNotifyItem *>>::operator[](
                 a1 + 104,
                 *(unsigned int *)(a1 + 176)) = v11;
    *v32 = (*(_DWORD *)(a1 + 176))++;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
    CTraceFuncW<long>::~CTraceFuncW<long>(v30);
  }
  catch ( CPassportException *v27 )
  {
    v31 = *((_DWORD *)v27 + 2);
    if ( v31 >= 0 )
      v31 = -2147418113;
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
  }
  catch ( ATL::CAtlException *v26 )
  {
    v31 = *(_DWORD *)v26;
    if ( v31 >= 0 )
      v31 = -2147418113;
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
  }
  catch ( std::bad_alloc )
  {
    v31 = -2147024882;
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
  }
  catch ( long v23 )
  {
    v31 = v23;
    if ( v23 >= 0 )
      v31 = -2147418113;
  }
  return ErrorHandlingUtilities::MapInternalErrorToExternal(v31, 0, 0);
}

```

## disassembly

```asm
0x18000e0a0  mov     r11, rsp
0x18000e0a3  mov     [r11+8], rbx
0x18000e0a7  mov     [r11+18h], rsi
0x18000e0ab  mov     [r11+20h], r9
0x18000e0af  push    rdi
0x18000e0b0  push    r12
0x18000e0b2  push    r13
0x18000e0b4  push    r14
0x18000e0b6  push    r15
0x18000e0b8  sub     rsp, 90h
0x18000e0bf  mov     rbx, r9
0x18000e0c2  mov     r15d, r8d
0x18000e0c5  mov     r12, rdx
0x18000e0c8  mov     rsi, rcx
0x18000e0cb  xor     r13d, r13d
0x18000e0ce  mov     [r11+10h], r13d
0x18000e0d2  lea     rdx, aCwindowslivepr_16; "CWindowsLiveProvider::Advise"
0x18000e0d9  mov     [r11-50h], rdx
0x18000e0dd  lea     rax, [r11+10h]
0x18000e0e1  mov     [r11-48h], rax
0x18000e0e5  mov     [r11-40h], r13
0x18000e0e9  mov     [r11-38h], r13
0x18000e0ed  xor     r9d, r9d; unsigned int
0x18000e0f0  mov     r8d, 40Dh; char *
0x18000e0f6  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000e0fd  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000e102  nop
0x18000e103  test    r12, r12
0x18000e106  jz      loc_18000E3A6
0x18000e10c  test    r15d, r15d
0x18000e10f  jz      loc_18000E3A6
0x18000e115  test    rbx, rbx
0x18000e118  jz      loc_18000E3A6
0x18000e11e  mov     [rsp+0B8h+var_98], r15d
0x18000e123  lea     r9, aEvents0xX; "Events: (0x%x)"
0x18000e12a  mov     r8d, 418h; unsigned int
0x18000e130  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000e137  lea     ecx, [r13+5]; unsigned __int8
0x18000e13b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000e140  lea     r14, [rsi+0B8h]
0x18000e147  mov     [rsp+0B8h+var_60], r14
0x18000e14c  mov     rcx, r14; lpCriticalSection
0x18000e14f  call    cs:__imp_EnterCriticalSection
0x18000e155  mov     [rsp+0B8h+var_58], 1
0x18000e15a  cmp     dword ptr [rsi+0B0h], 0FFFFFFFEh
0x18000e161  jnb     loc_18000E2CF
0x18000e167  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e16e  lea     ecx, [r13+20h]; unsigned __int64
0x18000e172  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e177  mov     rbx, rax
0x18000e17a  test    rax, rax
0x18000e17d  jz      loc_18000E2C7
0x18000e183  mov     [rax], r13
0x18000e186  mov     [rax+18h], r13
0x18000e18a  mov     [rax+8], r13
0x18000e18e  mov     [rax+10h], r13
0x18000e192  test    rbx, rbx
0x18000e195  jz      loc_18000E380
0x18000e19b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e1a2  mov     ecx, 10h; unsigned __int64
0x18000e1a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e1ac  mov     rdi, rax
0x18000e1af  mov     [rsp+0B8h+var_80], rax
0x18000e1b4  test    rax, rax
0x18000e1b7  jz      short loc_18000E1CA
0x18000e1b9  mov     [rax], r13
0x18000e1bc  mov     [rax+8], r13
0x18000e1c0  mov     [rsp+0B8h+var_80], rax
0x18000e1c5  test    rax, rax
0x18000e1c8  jnz     short loc_18000E221
0x18000e1ca  mov     [rsp+0B8h+arg_8], 8007000Eh
0x18000e1d5  mov     rcx, r14; lpCriticalSection
0x18000e1d8  call    cs:__imp_LeaveCriticalSection
0x18000e1de  nop
0x18000e1df  lea     rcx, [rsp+0B8h+var_50]
0x18000e1e4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000e1e9  nop
0x18000e1ea  mov     rcx, rbx; this
0x18000e1ed  call    ??_G_WLIDNotifyParam@@QEAAPEAXI@Z; _WLIDNotifyParam::`scalar deleting destructor'(uint)
0x18000e1f2  nop
0x18000e1f3  xor     r8d, r8d; bool *
0x18000e1f6  xor     edx, edx; bool
0x18000e1f8  mov     ecx, [rsp+0B8h+arg_8]; int
0x18000e1ff  call    ?MapInternalErrorToExternal@ErrorHandlingUtilities@@SAJJ_NPEA_N@Z; ErrorHandlingUtilities::MapInternalErrorToExternal(long,bool,bool *)
0x18000e204  lea     r11, [rsp+0B8h+var_28]
0x18000e20c  mov     rbx, [r11+30h]
0x18000e210  mov     rsi, [r11+40h]
0x18000e214  mov     rsp, r11
0x18000e217  pop     r15
0x18000e219  pop     r14
0x18000e21b  pop     r13
0x18000e21d  pop     r12
0x18000e21f  pop     rdi
0x18000e220  retn
0x18000e221  xor     r9d, r9d; lpName
0x18000e224  xor     r8d, r8d; bInitialState
0x18000e227  lea     edx, [r9+1]; bManualReset
0x18000e22b  xor     ecx, ecx; lpEventAttributes
0x18000e22d  call    cs:__imp_CreateEventW
0x18000e233  mov     r13, rax
0x18000e236  test    rax, rax
0x18000e239  jz      loc_18000E2F4
0x18000e23f  mov     [rbx], r15d
0x18000e242  lea     rcx, [rbx+8]; struct IUnknown **
0x18000e246  cmp     [rcx], r12
0x18000e249  jz      short loc_18000E253
0x18000e24b  mov     rdx, r12; struct IUnknown *
0x18000e24e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000e253  mov     [rbx+18h], r13
0x18000e257  mov     [rdi+8], r13
0x18000e25b  mov     r8d, 1; int
0x18000e261  mov     rdx, rbx; lpParameter
0x18000e264  lea     rcx, ?NotificationThread@@YAKPEAX@Z; lpStartAddress
0x18000e26b  call    ?IDCRLCreateThread@@YAPEAXP6AKPEAX@Z0H@Z; IDCRLCreateThread(ulong (*)(void *),void *,int)
0x18000e270  mov     [rdi], rax
0x18000e273  test    rax, rax
0x18000e276  jz      loc_18000E33A
0x18000e27c  mov     [rsp+0B8h+var_78], 0
0x18000e285  lea     rcx, [rsi+68h]
0x18000e289  mov     edx, [rsi+0B0h]
0x18000e28f  call    ??A?$CAtlMap@KPEAVCWLIDNotifyItem@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCWLIDNotifyItem@@@3@@ATL@@QEAAAEAPEAVCWLIDNotifyItem@@K@Z; ATL::CAtlMap<ulong,CWLIDNotifyItem *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CWLIDNotifyItem *>>::operator[](ulong)
0x18000e294  mov     [rax], rdi
0x18000e297  mov     eax, [rsi+0B0h]
0x18000e29d  mov     rcx, [rsp+0B8h+arg_18]
0x18000e2a5  mov     [rcx], eax
0x18000e2a7  inc     dword ptr [rsi+0B0h]
0x18000e2ad  mov     rcx, r14; lpCriticalSection
0x18000e2b0  call    cs:__imp_LeaveCriticalSection
0x18000e2b6  nop
0x18000e2b7  lea     rcx, [rsp+0B8h+var_50]
0x18000e2bc  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000e2c1  nop
0x18000e2c2  jmp     loc_18000E1F3
0x18000e2c7  mov     rbx, r13
0x18000e2ca  jmp     loc_18000E192
0x18000e2cf  mov     [rsp+0B8h+arg_8], 80070057h
0x18000e2da  mov     rcx, r14; lpCriticalSection
0x18000e2dd  call    cs:__imp_LeaveCriticalSection
0x18000e2e3  nop
0x18000e2e4  lea     rcx, [rsp+0B8h+var_50]
0x18000e2e9  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000e2ee  nop
0x18000e2ef  jmp     loc_18000E1F3
0x18000e2f4  call    cs:__imp_GetLastError
0x18000e2fa  test    eax, eax
0x18000e2fc  jle     short loc_18000E306
0x18000e2fe  movzx   eax, ax
0x18000e301  or      eax, 80070000h
0x18000e306  mov     [rsp+0B8h+arg_8], eax
0x18000e30d  lea     rcx, [rsp+0B8h+var_60]
0x18000e312  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000e317  nop
0x18000e318  lea     rcx, [rsp+0B8h+var_50]
0x18000e31d  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000e322  nop
0x18000e323  mov     rcx, rdi; this
0x18000e326  call    ??_GCWLIDNotifyItem@@QEAAPEAXI@Z; CWLIDNotifyItem::`scalar deleting destructor'(uint)
0x18000e32b  nop
0x18000e32c  mov     rcx, rbx; this
0x18000e32f  call    ??_G_WLIDNotifyParam@@QEAAPEAXI@Z; _WLIDNotifyParam::`scalar deleting destructor'(uint)
0x18000e334  nop
0x18000e335  jmp     loc_18000E1F3
0x18000e33a  call    cs:__imp_GetLastError
0x18000e340  test    eax, eax
0x18000e342  jle     short loc_18000E34C
0x18000e344  movzx   eax, ax
0x18000e347  or      eax, 80070000h
0x18000e34c  mov     [rsp+0B8h+arg_8], eax
0x18000e353  lea     rcx, [rsp+0B8h+var_60]
0x18000e358  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000e35d  nop
0x18000e35e  lea     rcx, [rsp+0B8h+var_50]
0x18000e363  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000e368  nop
0x18000e369  mov     rcx, rdi; this
0x18000e36c  call    ??_GCWLIDNotifyItem@@QEAAPEAXI@Z; CWLIDNotifyItem::`scalar deleting destructor'(uint)
0x18000e371  nop
0x18000e372  mov     rcx, rbx; this
0x18000e375  call    ??_G_WLIDNotifyParam@@QEAAPEAXI@Z; _WLIDNotifyParam::`scalar deleting destructor'(uint)
0x18000e37a  nop
0x18000e37b  jmp     loc_18000E1F3
0x18000e380  mov     [rsp+0B8h+arg_8], 8007000Eh
0x18000e38b  lea     rcx, [rsp+0B8h+var_60]
0x18000e390  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000e395  nop
0x18000e396  lea     rcx, [rsp+0B8h+var_50]
0x18000e39b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000e3a0  nop
0x18000e3a1  jmp     loc_18000E1F3
0x18000e3a6  mov     [rsp+0B8h+arg_8], 80070057h
0x18000e3b1  lea     rcx, [rsp+0B8h+var_50]
0x18000e3b6  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000e3bb  nop
0x18000e3bc  jmp     loc_18000E1F3
0x18000e3c1  jmp     loc_18000E1F3
0x18000e3c6  jmp     loc_18000E1F3
0x18000e3cb  jmp     loc_18000E1F3
0x18000e3d0  jmp     loc_18000E1F3
```
