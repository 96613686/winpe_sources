# STATrackedObject::SetObject(IUnknown *)

- ea: `0x1800805e0`
- end: `0x1800808a9`
- name: `?SetObject@STATrackedObject@@QEAAJPEAUIUnknown@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(STATrackedObject *__hidden this, struct IUnknown *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007f1d0`
- `0x1800808b0`
- `0x1800ba120`
- `0x180109d74`

## callees

- `0x18002f580`
- `0x1800805e0`
- `0x180109ee8`
- `0x18012b47c`
- `0x1801e887c`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080612`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800806a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800806a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080618`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800806f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080618`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800806f3`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180080861`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180080861`

## string_xrefs

- `0x180080740`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x1800807e0`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x18008080e`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall STATrackedObject::SetObject(STATrackedObject *this, struct IUnknown *a2)
{
  _QWORD *v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 v6; // rdx
  unsigned __int64 i; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  HRESULT ClassObject; // edi
  _QWORD *v14; // rax
  int v15; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID v18; // [rsp+60h] [rbp+18h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp+20h]

  v19 = 0;
  if ( !g_ComMitigationDone && !`CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress )
  {
    `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 1;
    v18 = 0;
    ClassObject = CoGetClassObject(&CLSID_CUIAutomation, 1u, 0, &GUID_00000001_0000_0000_c000_000000000046, &v18);
    `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 0;
    if ( ClassObject < 0 )
      goto LABEL_23;
    if ( v18 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    g_ComMitigationDone = 1;
  }
  v4 = 0;
  EnterCriticalSection(&CApartmentTracker::_classLock);
  CurrentThreadId = GetCurrentThreadId();
  LODWORD(v18) = CurrentThreadId;
  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)&v18 + i) ^ (unsigned __int64)v6);
  v8 = 2 * (qword_18039F790 & v6);
  v9 = *((_QWORD *)Block + v8 + 1);
  if ( v9 == qword_18039F768 )
  {
LABEL_8:
    v9 = 0;
  }
  else
  {
    while ( CurrentThreadId != *(_DWORD *)(v9 + 16) )
    {
      if ( v9 == *((_QWORD *)Block + v8) )
        goto LABEL_8;
      v9 = *(_QWORD *)(v9 + 8);
    }
  }
  v10 = qword_18039F768;
  if ( v9 )
    v10 = v9;
  if ( v10 != qword_18039F768 )
    v4 = *(_QWORD **)(v10 + 24);
  LeaveCriticalSection(&CApartmentTracker::_classLock);
  if ( !v4 )
  {
    v14 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v4 = v14;
    v18 = v14;
    if ( v14 )
    {
      *v14 = &RefcountBase::`vftable';
      *((_DWORD *)v14 + 2) = 1;
      _InterlockedIncrement(&dword_18039DE7C);
      *v14 = &CApartmentTracker::`vftable'{for `RefcountBase'};
      v14[2] = &CApartmentTracker::`vftable'{for `IInitializeSpy'};
      *((_DWORD *)v14 + 6) = 0;
      v14[5] = 0;
      v14[4] = 0;
      v18 = v14;
      v15 = CApartmentTracker::Initialize((CApartmentTracker *)v14);
      ClassObject = v15;
      if ( v15 >= 0 )
        goto LABEL_16;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
        (const char *)(unsigned int)v15,
        ppv);
      AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&v18);
    }
    else
    {
      v18 = 0;
      ClassObject = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
        (const char *)0x8007000ELL,
        ppv);
    }
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
      (const char *)(unsigned int)ClassObject,
      ppv);
    return (unsigned int)ClassObject;
  }
  if ( !*((_DWORD *)v4 + 6) )
  {
    ClassObject = -2147467259;
    goto LABEL_23;
  }
  _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
LABEL_16:
  v19 = v4;
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  *((_QWORD *)this + 2) = v4[5];
  v11 = v4[5];
  if ( v11 )
    *(_QWORD *)(v11 + 24) = this;
  v4[5] = this;
  *((_QWORD *)this + 4) = a2;
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  *((_DWORD *)this + 10) = GetCurrentThreadId();
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v4)(v4, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800805e0  mov     [rsp+arg_0], rbx
0x1800805e5  push    rsi
0x1800805e6  push    rdi
0x1800805e7  push    r14
0x1800805e9  sub     rsp, 30h
0x1800805ed  mov     r14, rdx
0x1800805f0  mov     rsi, rcx
0x1800805f3  mov     [rsp+48h+arg_18], 0
0x1800805fc  cmp     cs:?g_ComMitigationDone@@3_NA, 0; bool g_ComMitigationDone
0x180080603  jz      loc_180080825
0x180080609  xor     ebx, ebx
0x18008060b  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180080612  call    cs:__imp_EnterCriticalSection
0x180080618  call    cs:__imp_GetCurrentThreadId
0x18008061e  mov     r9d, eax
0x180080621  mov     dword ptr [rsp+48h+arg_10], eax
0x180080625  mov     rdx, 0CBF29CE484222325h
0x18008062f  xor     r8d, r8d
0x180080632  movzx   ecx, byte ptr [rsp+r8+48h+arg_10]
0x180080638  xor     rdx, rcx
0x18008063b  mov     rax, 100000001B3h
0x180080645  imul    rdx, rax
0x180080649  inc     r8
0x18008064c  cmp     r8, 4
0x180080650  jb      short loc_180080632
0x180080652  and     rdx, cs:qword_18039F790
0x180080659  add     rdx, rdx
0x18008065c  mov     rcx, cs:Block
0x180080663  mov     rax, [rcx+rdx*8+8]
0x180080668  mov     r10, cs:qword_18039F768
0x18008066f  cmp     rax, r10
0x180080672  jz      short loc_180080689
0x180080674  mov     r8, [rcx+rdx*8]
0x180080678  cmp     r9d, [rax+10h]
0x18008067c  jz      short loc_18008068B
0x18008067e  cmp     rax, r8
0x180080681  jz      short loc_180080689
0x180080683  mov     rax, [rax+8]
0x180080687  jmp     short loc_180080678
0x180080689  xor     eax, eax
0x18008068b  mov     rdx, r10
0x18008068e  test    rax, rax
0x180080691  cmovnz  rdx, rax
0x180080695  cmp     rdx, r10
0x180080698  jz      short loc_18008069E
0x18008069a  mov     rbx, [rdx+18h]
0x18008069e  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800806a5  call    cs:__imp_LeaveCriticalSection
0x1800806ab  test    rbx, rbx
0x1800806ae  jz      loc_180080756
0x1800806b4  cmp     dword ptr [rbx+18h], 0
0x1800806b8  jz      short loc_180080733
0x1800806ba  lock inc dword ptr [rbx+8]
0x1800806be  mov     [rsp+48h+arg_18], rbx
0x1800806c3  lock inc dword ptr [rsi+8]
0x1800806c7  mov     rax, [rbx+28h]
0x1800806cb  mov     [rsi+10h], rax
0x1800806cf  mov     rax, [rbx+28h]
0x1800806d3  test    rax, rax
0x1800806d6  jz      short loc_1800806DC
0x1800806d8  mov     [rax+18h], rsi
0x1800806dc  mov     [rbx+28h], rsi
0x1800806e0  mov     [rsi+20h], r14
0x1800806e4  mov     rax, [r14]
0x1800806e7  mov     rcx, r14
0x1800806ea  mov     rax, [rax+8]
0x1800806ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800806f3  call    cs:__imp_GetCurrentThreadId
0x1800806f9  mov     [rsi+28h], eax
0x1800806fc  test    rbx, rbx
0x1800806ff  jz      short loc_18008070E
0x180080701  or      eax, 0FFFFFFFFh
0x180080704  lock xadd [rbx+8], eax
0x180080709  cmp     eax, 1
0x18008070c  jz      short loc_18008071E
0x18008070e  xor     eax, eax
0x180080710  mov     rbx, [rsp+48h+arg_0]
0x180080715  add     rsp, 30h
0x180080719  pop     r14
0x18008071b  pop     rdi
0x18008071c  pop     rsi
0x18008071d  retn
0x18008071e  mov     rax, [rbx]
0x180080721  mov     edx, 1
0x180080726  mov     rcx, rbx
0x180080729  mov     rax, [rax]
0x18008072c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080731  jmp     short loc_18008070E
0x180080733  mov     edi, 80004005h
0x180080738  mov     rcx, [rsp+48h]; this
0x18008073d  mov     r9d, edi; char *
0x180080740  lea     r8, aOnecoreWindows_107; "onecore\\windows\\accessibletech\\uiaut"...
0x180080747  mov     edx, 128h; void *
0x18008074c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080751  nop
0x180080752  mov     eax, edi
0x180080754  jmp     short loc_180080710
0x180080756  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008075d  mov     ecx, 30h ; '0'; unsigned __int64
0x180080762  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180080767  mov     rbx, rax
0x18008076a  mov     [rsp+48h+arg_10], rax
0x18008076f  test    rax, rax
0x180080772  jz      loc_18008089A
0x180080778  lea     rax, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x18008077f  mov     [rbx], rax
0x180080782  mov     dword ptr [rbx+8], 1
0x180080789  lock inc cs:dword_18039DE7C
0x180080790  lea     rax, ??_7CApartmentTracker@@6BRefcountBase@@@; const CApartmentTracker::`vftable'{for `RefcountBase'}
0x180080797  mov     [rbx], rax
0x18008079a  lea     rax, ??_7CApartmentTracker@@6BIInitializeSpy@@@; const CApartmentTracker::`vftable'{for `IInitializeSpy'}
0x1800807a1  mov     [rbx+10h], rax
0x1800807a5  mov     dword ptr [rbx+18h], 0
0x1800807ac  mov     qword ptr [rbx+28h], 0
0x1800807b4  mov     qword ptr [rbx+20h], 0
0x1800807bc  mov     [rsp+48h+arg_10], rbx
0x1800807c1  test    rbx, rbx
0x1800807c4  jz      short loc_180080801
0x1800807c6  mov     rcx, rbx; this
0x1800807c9  call    ?Initialize@CApartmentTracker@@QEAAJXZ; CApartmentTracker::Initialize(void)
0x1800807ce  mov     edi, eax
0x1800807d0  test    eax, eax
0x1800807d2  jns     loc_1800806BE
0x1800807d8  mov     rcx, [rsp+48h]; this
0x1800807dd  mov     r9d, eax; char *
0x1800807e0  lea     r8, aOnecoreWindows_107; "onecore\\windows\\accessibletech\\uiaut"...
0x1800807e7  mov     edx, 0F9h; void *
0x1800807ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800807f1  nop
0x1800807f2  lea     rcx, [rsp+48h+arg_10]
0x1800807f7  call    ??1?$AutoRelease@PEAVEditTextRange@@@@QEAA@XZ; AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(void)
0x1800807fc  jmp     loc_180080738
0x180080801  mov     rcx, [rsp+48h]; this
0x180080806  mov     edi, 8007000Eh
0x18008080b  mov     r9d, edi; char *
0x18008080e  lea     r8, aOnecoreWindows_107; "onecore\\windows\\accessibletech\\uiaut"...
0x180080815  mov     edx, 0F8h; void *
0x18008081a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008081f  nop
0x180080820  jmp     loc_180080738
0x180080825  cmp     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, 0; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x18008082c  jnz     loc_180080609
0x180080832  mov     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, 1; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180080839  mov     [rsp+48h+arg_10], 0
0x180080842  lea     rax, [rsp+48h+arg_10]
0x180080847  mov     qword ptr [rsp+48h+ppv], rax; ppv
0x18008084c  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180080853  xor     r8d, r8d; pvReserved
0x180080856  lea     edx, [r8+1]; dwClsContext
0x18008085a  lea     rcx, CLSID_CUIAutomation; rclsid
0x180080861  call    cs:__imp_CoGetClassObject
0x180080867  mov     edi, eax
0x180080869  mov     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, 0; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180080870  test    eax, eax
0x180080872  js      loc_180080738
0x180080878  mov     rcx, [rsp+48h+arg_10]
0x18008087d  test    rcx, rcx
0x180080880  jz      short loc_18008088E
0x180080882  mov     rax, [rcx]
0x180080885  mov     rax, [rax+10h]
0x180080889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008088e  mov     cs:?g_ComMitigationDone@@3_NA, 1; bool g_ComMitigationDone
0x180080895  jmp     loc_180080609
0x18008089a  mov     [rsp+48h+arg_10], 0
0x1800808a3  jmp     loc_180080801
```
