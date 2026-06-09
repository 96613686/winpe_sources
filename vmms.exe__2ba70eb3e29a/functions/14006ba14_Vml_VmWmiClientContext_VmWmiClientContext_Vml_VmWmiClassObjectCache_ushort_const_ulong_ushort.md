# Vml::VmWmiClientContext::VmWmiClientContext(Vml::VmWmiClassObjectCache *,ushort const *,ulong,ushort *)

- ea: `0x14006ba14`
- end: `0x14006bf5d`
- name: `??0VmWmiClientContext@Vml@@IEAA@PEAVVmWmiClassObjectCache@1@PEBGKPEAG@Z`
- size: `1353`
- prototype: `__int64 __fastcall(Vml::VmWmiClientContext *__hidden this, struct Vml::VmWmiClassObjectCache *, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1406afa10`

## callees

- `0x140034404`
- `0x14005c630`
- `0x14006ba14`
- `0x14006bf64`
- `0x1400acf04`
- `0x14017902c`
- `0x140188e18`
- `0x1402407a4`
- `0x1404828e0`
- `0x140498a40`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14006ba93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14006ba93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14006badc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14006badc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006be18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006be18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14006bd15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14006bd15`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14006bd31`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14006bd31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14006bc3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14006bc3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006bcb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006bcd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006bcb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006bcd6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006bc6b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006bc6b`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14006bb74`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14006bb74`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14006bd67`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14006bdda`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14006bd67`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14006bdda`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14006be59`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14006be59`

## string_xrefs

- `0x14006bbbb`: `onecore\vm\common\vml\VmCom.h`
- `0x14006bed3`: `onecore\vm\common\vml\VmCom.h`
- `0x14006befd`: `onecore\vm\common\vml\VmCom.h`
- `0x14006be50`: `SeChangeNotifyPrivilege`
- `0x14006bdf2`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14006bee8`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14006bf0f`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14006bf33`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14006bf48`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14006be91`: `A derivative of VmModuleBase has not been constructed!\n   This usually occurs because a portion of the VML has been\n   used in a component that is not built from one of the VML\n   module classes.\n`
- `0x14006bea6`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
Vml::VmWmiClientContext *__fastcall Vml::VmWmiClientContext::VmWmiClientContext(
        Vml::VmWmiClientContext *this,
        struct Vml::VmWmiClassObjectCache *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  struct _LIST_ENTRY *v9; // rdi
  struct _LIST_ENTRY *Flink; // rax
  HRESULT v11; // eax
  int v12; // eax
  void *v13; // rax
  void *v14; // rcx
  __int64 v15; // rdx
  char v16; // al
  int v17; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v19; // rcx
  const char *v20; // r9
  const char *v21; // r9
  HANDLE CurrentThread; // rax
  const char *v24; // r9
  LONG HighPart; // ecx
  const char *v26; // r9
  DWORD LastError; // eax
  const char *v28; // r9
  const char *v29; // r9
  unsigned int dwDesiredAccess; // [rsp+20h] [rbp-59h]
  void *ppInterface; // [rsp+50h] [rbp-29h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+58h] [rbp-21h] BYREF
  HANDLE hSourceHandle; // [rsp+68h] [rbp-11h] BYREF
  HANDLE TargetHandle; // [rsp+70h] [rbp-9h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  *((_QWORD *)this + 1) = &WmiMsvmReplicationAuthorizationSettingData::`vbtable';
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 11) = 0;
  v9 = (struct _LIST_ENTRY *)((char *)this + 120);
  *(_OWORD *)((char *)this + 120) = 0;
  AcquireSRWLockExclusive(&Vml::VmSharableObject::gm_AllocatedObjectLock);
  ++Vml::VmSharableObject::gm_AllocatedObjectCount;
  Flink = Vml::VmSharableObject::gm_AllocatedObjectList.Flink;
  if ( Vml::VmSharableObject::gm_AllocatedObjectList.Flink->Blink != &Vml::VmSharableObject::gm_AllocatedObjectList )
    __fastfail(3u);
  v9->Flink = Vml::VmSharableObject::gm_AllocatedObjectList.Flink;
  v9->Blink = &Vml::VmSharableObject::gm_AllocatedObjectList;
  Flink->Blink = v9;
  Vml::VmSharableObject::gm_AllocatedObjectList.Flink = v9;
  ReleaseSRWLockExclusive(&Vml::VmSharableObject::gm_AllocatedObjectLock);
  *((_QWORD *)this + 2) = 0;
  if ( !Vml::VmModuleBase::gm_ModuleBase )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(2) )
      VmlDebugTrace(
        2,
        L"A derivative of VmModuleBase has not been constructed!\n"
         "   This usually occurs because a portion of the VML has been\n"
         "   used in a component that is not built from one of the VML\n"
         "   module classes.\n");
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
      v29);
  }
  (*(void (__fastcall **)(struct Vml::VmModuleBase *, __int64))(*(_QWORD *)Vml::VmModuleBase::gm_ModuleBase + 8LL))(
    Vml::VmModuleBase::gm_ModuleBase,
    1);
  *(_QWORD *)this = &Vml::VmWmiClientContext::`vftable'{for `Vml::VmComObject'};
  *((_QWORD *)this + 3) = &Vml::VmWmiClientContext::`vftable';
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &Vml::VmWmiClientContext::`vftable'{for `Vml::VmSharableObject'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  hSourceHandle = 0;
  TargetHandle = 0;
  *(_QWORD *)&NewState.Privileges[0].Luid.HighPart = 0;
  *(_QWORD *)&PreviousState.PrivilegeCount = &NewState;
  *(_QWORD *)&NewState.PrivilegeCount = 0;
  ppInterface = 0;
  v11 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
  if ( v11 < 0 )
  {
    if ( v11 != -2147417833 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1806,
        (unsigned int)"onecore\\vm\\common\\vml\\VmCom.h",
        (const char *)(unsigned int)v11,
        dwDesiredAccess);
    goto LABEL_31;
  }
  if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
  {
LABEL_31:
    v14 = ppInterface;
    goto LABEL_8;
  }
  v12 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17FA,
      (unsigned int)"onecore\\vm\\common\\vml\\VmCom.h",
      (const char *)(unsigned int)v12,
      dwDesiredAccess);
  v13 = ppInterface;
  v14 = 0;
  ppInterface = 0;
  v15 = *(_QWORD *)&NewState.PrivilegeCount;
  *(_QWORD *)&NewState.PrivilegeCount = v13;
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_31;
  }
LABEL_8:
  if ( v14 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
  v16 = 1;
  LOBYTE(NewState.Privileges[0].Luid.HighPart) = 1;
  while ( v16 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, &hSourceHandle) )
    {
      LastError = GetLastError();
      if ( LastError == 1008 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xC34,
          (unsigned int)"onecore\\vm\\vmms\\wmibase\\vmwmi.cpp",
          (const char *)0x3F0,
          dwDesiredAccess);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1CC3,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        (const char *)LastError,
        dwDesiredAccess);
    }
    v16 = 0;
    LOBYTE(NewState.Privileges[0].Luid.HighPart) = 0;
  }
  if ( *(_QWORD *)&NewState.PrivilegeCount )
  {
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&NewState.PrivilegeCount + 40LL))(*(_QWORD *)&NewState.PrivilegeCount);
    if ( v17 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1822,
        (unsigned int)"onecore\\vm\\common\\vml\\VmCom.h",
        (const char *)(unsigned int)v17,
        dwDesiredAccess);
    if ( *(_QWORD *)&NewState.PrivilegeCount )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&NewState.PrivilegeCount + 16LL))(*(_QWORD *)&NewState.PrivilegeCount);
  }
  CurrentProcess = GetCurrentProcess();
  if ( DuplicateHandle(CurrentProcess, hSourceHandle, CurrentProcess, &TargetHandle, 0x20028u, 0, 0) )
  {
    if ( !AdjustTokenPrivileges(TargetHandle, 1, 0, 0, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1B12,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v24);
    HighPart = Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId.HighPart;
    if ( !Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId.HighPart
      && !Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId.LowPart )
    {
      if ( !LookupPrivilegeValueW(0, L"SeChangeNotifyPrivilege", &Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xC51,
          (unsigned int)"onecore\\vm\\vmms\\wmibase\\vmwmi.cpp",
          v28);
      HighPart = Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId.HighPart;
    }
    LODWORD(ppInterface) = 16;
    PreviousState = 0;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid.LowPart = Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId.LowPart;
    NewState.Privileges[0].Luid.HighPart = HighPart;
    NewState.Privileges[0].Attributes = 2;
    if ( !AdjustTokenPrivileges(TargetHandle, 0, &NewState, 0x10u, &PreviousState, (PDWORD)&ppInterface) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1B67,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v26);
  }
  Vml::VmWmiClientContext::FinishConstruction(this, a2, hSourceHandle, a3, a4, a5);
  v19 = 0;
  hSourceHandle = 0;
  if ( TargetHandle )
  {
    if ( !CloseHandle(TargetHandle) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1004,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v20);
    v19 = hSourceHandle;
  }
  if ( v19 && !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1004,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v21);
  return this;
}

```

## disassembly

```asm
0x14006ba14  mov     [rsp-8+arg_18], rbx
0x14006ba19  push    rbp
0x14006ba1a  push    rsi
0x14006ba1b  push    rdi
0x14006ba1c  push    r12
0x14006ba1e  push    r13
0x14006ba20  push    r14
0x14006ba22  push    r15
0x14006ba24  lea     rbp, [rsp-17h]
0x14006ba29  sub     rsp, 90h
0x14006ba30  mov     rax, cs:__security_cookie
0x14006ba37  xor     rax, rsp
0x14006ba3a  mov     [rbp+47h+var_38], rax
0x14006ba3e  mov     esi, r9d
0x14006ba41  mov     r15, r8
0x14006ba44  mov     r14, rdx
0x14006ba47  mov     rbx, rcx
0x14006ba4a  mov     [rbp+47h+var_78], rcx
0x14006ba4e  xor     r12d, r12d
0x14006ba51  mov     [rbp+47h+var_80], r12d
0x14006ba55  lea     rax, ??_8WmiMsvmReplicationAuthorizationSettingData@@7B@; const WmiMsvmReplicationAuthorizationSettingData::`vbtable'
0x14006ba5c  mov     [rcx+8], rax
0x14006ba60  mov     [rcx+50h], r12
0x14006ba64  mov     [rcx+60h], r12
0x14006ba68  mov     [rcx+68h], r12
0x14006ba6c  mov     [rcx+70h], r12
0x14006ba70  mov     [rcx+88h], r12
0x14006ba77  mov     [rcx+90h], r12
0x14006ba7e  mov     [rcx+58h], r12
0x14006ba82  lea     rdi, [rcx+78h]
0x14006ba86  xorps   xmm0, xmm0
0x14006ba89  movups  xmmword ptr [rdi], xmm0
0x14006ba8c  lea     rcx, ?gm_AllocatedObjectLock@VmSharableObject@Vml@@0U_RTL_SRWLOCK@@A; SRWLock
0x14006ba93  call    cs:__imp_AcquireSRWLockExclusive
0x14006ba9a  nop     dword ptr [rax+rax+00h]
0x14006ba9f  lea     r13d, [r12+1]
0x14006baa4  add     cs:?gm_AllocatedObjectCount@VmSharableObject@Vml@@0KA, r13d; ulong Vml::VmSharableObject::gm_AllocatedObjectCount
0x14006baab  mov     rax, cs:?gm_AllocatedObjectList@VmSharableObject@Vml@@0U_LIST_ENTRY@@A; _LIST_ENTRY Vml::VmSharableObject::gm_AllocatedObjectList
0x14006bab2  lea     rcx, ?gm_AllocatedObjectList@VmSharableObject@Vml@@0U_LIST_ENTRY@@A; _LIST_ENTRY Vml::VmSharableObject::gm_AllocatedObjectList
0x14006bab9  cmp     [rax+8], rcx
0x14006babd  jnz     loc_14006BE7C
0x14006bac3  mov     [rdi], rax
0x14006bac6  mov     [rdi+8], rcx
0x14006baca  mov     [rax+8], rdi
0x14006bace  mov     cs:?gm_AllocatedObjectList@VmSharableObject@Vml@@0U_LIST_ENTRY@@A, rdi; _LIST_ENTRY Vml::VmSharableObject::gm_AllocatedObjectList
0x14006bad5  lea     rcx, ?gm_AllocatedObjectLock@VmSharableObject@Vml@@0U_RTL_SRWLOCK@@A; SRWLock
0x14006badc  call    cs:__imp_ReleaseSRWLockExclusive
0x14006bae3  nop     dword ptr [rax+rax+00h]
0x14006bae8  nop
0x14006bae9  mov     [rbp+47h+var_80], r13d
0x14006baed  mov     [rbx+10h], r12
0x14006baf1  mov     rcx, cs:?gm_ModuleBase@VmModuleBase@Vml@@1PEAV12@EA; Vml::VmModuleBase * Vml::VmModuleBase::gm_ModuleBase
0x14006baf8  test    rcx, rcx
0x14006bafb  jz      loc_14006BE83
0x14006bb01  mov     rax, [rcx]
0x14006bb04  mov     edx, r13d
0x14006bb07  mov     rax, [rax+8]
0x14006bb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bb10  nop
0x14006bb11  lea     rax, ??_7VmWmiClientContext@Vml@@6BVmComObject@1@@; const Vml::VmWmiClientContext::`vftable'{for `Vml::VmComObject'}
0x14006bb18  mov     [rbx], rax
0x14006bb1b  lea     rax, ??_7VmWmiClientContext@Vml@@6B@; const Vml::VmWmiClientContext::`vftable'
0x14006bb22  mov     [rbx+18h], rax
0x14006bb26  mov     rax, [rbx+8]
0x14006bb2a  movsxd  rcx, dword ptr [rax+4]
0x14006bb2e  lea     rax, ??_7VmWmiClientContext@Vml@@6BVmSharableObject@1@@; const Vml::VmWmiClientContext::`vftable'{for `Vml::VmSharableObject'}
0x14006bb35  mov     [rcx+rbx+8], rax
0x14006bb3a  mov     [rbx+20h], r12
0x14006bb3e  mov     [rbx+28h], r12
0x14006bb42  mov     [rbx+30h], r12
0x14006bb46  mov     [rbx+38h], r12
0x14006bb4a  mov     [rbp+47h+hSourceHandle], r12
0x14006bb4e  mov     [rbp+47h+TargetHandle], r12
0x14006bb52  xorps   xmm0, xmm0
0x14006bb55  movups  xmmword ptr [rbp+47h+NewState.PrivilegeCount], xmm0
0x14006bb59  lea     rax, [rbp+47h+NewState]
0x14006bb5d  mov     qword ptr [rbp+47h+PreviousState.PrivilegeCount], rax
0x14006bb61  mov     qword ptr [rbp+47h+NewState.PrivilegeCount], r12
0x14006bb65  mov     [rbp+47h+ppInterface], r12
0x14006bb69  lea     rdx, [rbp+47h+ppInterface]; ppInterface
0x14006bb6d  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x14006bb74  call    cs:__imp_CoGetCallContext
0x14006bb7b  nop     dword ptr [rax+rax+00h]
0x14006bb80  test    eax, eax
0x14006bb82  js      loc_14006BE04
0x14006bb88  mov     rcx, [rbp+47h+ppInterface]
0x14006bb8c  mov     rax, [rcx]
0x14006bb8f  mov     rax, [rax+30h]
0x14006bb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bb98  test    eax, eax
0x14006bb9a  jnz     loc_14006BE0F
0x14006bba0  mov     rcx, [rbp+47h+ppInterface]
0x14006bba4  mov     rax, [rcx]
0x14006bba7  mov     rax, [rax+20h]
0x14006bbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bbb0  mov     rcx, [rbp+4Fh]; this
0x14006bbb4  test    eax, eax
0x14006bbb6  jns     short loc_14006BBCD
0x14006bbb8  mov     r9d, eax; char *
0x14006bbbb  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\vml\\VmCom.h"
0x14006bbc2  mov     edx, 17FAh; void *
0x14006bbc7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006bbcd  mov     rax, [rbp+47h+ppInterface]
0x14006bbd1  mov     rcx, r12
0x14006bbd4  mov     [rbp+47h+ppInterface], rcx
0x14006bbd8  mov     rdx, qword ptr [rbp+47h+NewState.PrivilegeCount]
0x14006bbdc  mov     qword ptr [rbp+47h+NewState.PrivilegeCount], rax
0x14006bbe0  test    rdx, rdx
0x14006bbe3  jnz     loc_14006BEB8
0x14006bbe9  test    rcx, rcx
0x14006bbec  jz      short loc_14006BBFB
0x14006bbee  mov     rax, [rcx]
0x14006bbf1  mov     rax, [rax+10h]
0x14006bbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bbfa  nop
0x14006bbfb  mov     al, r13b
0x14006bbfe  mov     byte ptr [rbp+47h+NewState.Privileges.Luid.HighPart], al
0x14006bc01  test    al, al
0x14006bc03  jnz     loc_14006BD15
0x14006bc09  mov     rcx, qword ptr [rbp+47h+NewState.PrivilegeCount]
0x14006bc0d  test    rcx, rcx
0x14006bc10  jz      short loc_14006BC3F
0x14006bc12  mov     rax, [rcx]
0x14006bc15  mov     rax, [rax+28h]
0x14006bc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bc1e  mov     rcx, [rbp+4Fh]; this
0x14006bc22  test    eax, eax
0x14006bc24  js      loc_14006BEFA
0x14006bc2a  mov     rcx, qword ptr [rbp+47h+NewState.PrivilegeCount]
0x14006bc2e  test    rcx, rcx
0x14006bc31  jz      short loc_14006BC3F
0x14006bc33  mov     rax, [rcx]
0x14006bc36  mov     rax, [rax+10h]
0x14006bc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bc3f  call    cs:__imp_GetCurrentProcess
0x14006bc46  nop     dword ptr [rax+rax+00h]
0x14006bc4b  mov     [rsp+0C0h+dwOptions], r12d; dwOptions
0x14006bc50  mov     [rsp+0C0h+bInheritHandle], r12d; bInheritHandle
0x14006bc55  mov     [rsp+0C0h+dwDesiredAccess], 20028h; dwDesiredAccess
0x14006bc5d  lea     r9, [rbp+47h+TargetHandle]; lpTargetHandle
0x14006bc61  mov     r8, rax; hTargetProcessHandle
0x14006bc64  mov     rdx, [rbp+47h+hSourceHandle]; hSourceHandle
0x14006bc68  mov     rcx, rax; hSourceProcessHandle
0x14006bc6b  call    cs:__imp_DuplicateHandle
0x14006bc72  nop     dword ptr [rax+rax+00h]
0x14006bc77  test    eax, eax
0x14006bc79  jnz     loc_14006BD50
0x14006bc7f  mov     rax, [rbp+47h+arg_20]
0x14006bc83  mov     qword ptr [rsp+0C0h+bInheritHandle], rax; unsigned __int16 *
0x14006bc88  mov     [rsp+0C0h+dwDesiredAccess], esi; unsigned int
0x14006bc8c  mov     r9, r15; unsigned __int16 *
0x14006bc8f  mov     r8, [rbp+47h+hSourceHandle]; void *
0x14006bc93  mov     rdx, r14; struct Vml::VmWmiClassObjectCache *
0x14006bc96  mov     rcx, rbx; this
0x14006bc99  call    ?FinishConstruction@VmWmiClientContext@Vml@@AEAAXPEAVVmWmiClassObjectCache@2@PEAXPEBGKPEAG@Z; Vml::VmWmiClientContext::FinishConstruction(Vml::VmWmiClassObjectCache *,void *,ushort const *,ulong,ushort *)
0x14006bc9e  mov     rcx, r12
0x14006bca1  mov     [rbp+47h+hSourceHandle], rcx
0x14006bca5  mov     rax, [rbp+47h+TargetHandle]
0x14006bca9  test    rax, rax
0x14006bcac  jz      short loc_14006BCCD
0x14006bcae  mov     rdi, [rbp+4Fh]
0x14006bcb2  mov     rcx, rax; hObject
0x14006bcb5  call    cs:__imp_CloseHandle
0x14006bcbc  nop     dword ptr [rax+rax+00h]
0x14006bcc1  test    eax, eax
0x14006bcc3  jz      loc_14006BF33
0x14006bcc9  mov     rcx, [rbp+47h+hSourceHandle]; hObject
0x14006bccd  test    rcx, rcx
0x14006bcd0  jz      short loc_14006BCEA
0x14006bcd2  mov     rdi, [rbp+4Fh]
0x14006bcd6  call    cs:__imp_CloseHandle
0x14006bcdd  nop     dword ptr [rax+rax+00h]
0x14006bce2  test    eax, eax
0x14006bce4  jz      loc_14006BF48
0x14006bcea  mov     rax, rbx
0x14006bced  mov     rcx, [rbp+47h+var_38]
0x14006bcf1  xor     rcx, rsp; StackCookie
0x14006bcf4  call    __security_check_cookie
0x14006bcf9  mov     rbx, [rsp+0C0h+arg_18]
0x14006bd01  add     rsp, 90h
0x14006bd08  pop     r15
0x14006bd0a  pop     r14
0x14006bd0c  pop     r13
0x14006bd0e  pop     r12
0x14006bd10  pop     rdi
0x14006bd11  pop     rsi
0x14006bd12  pop     rbp
0x14006bd13  retn
0x14006bd15  call    cs:__imp_GetCurrentThread
0x14006bd1c  nop     dword ptr [rax+rax+00h]
0x14006bd21  nop
0x14006bd22  lea     r9, [rbp+47h+hSourceHandle]; TokenHandle
0x14006bd26  mov     r8d, r13d; OpenAsSelf
0x14006bd29  mov     edx, 2000Eh; DesiredAccess
0x14006bd2e  mov     rcx, rax; ThreadHandle
0x14006bd31  call    cs:__imp_OpenThreadToken
0x14006bd38  nop     dword ptr [rax+rax+00h]
0x14006bd3d  test    eax, eax
0x14006bd3f  jz      loc_14006BE18
0x14006bd45  mov     al, r12b
0x14006bd48  mov     byte ptr [rbp+47h+NewState.Privileges.Luid.HighPart], al
0x14006bd4b  jmp     loc_14006BC01
0x14006bd50  mov     qword ptr [rsp+0C0h+bInheritHandle], r12; ReturnLength
0x14006bd55  mov     qword ptr [rsp+0C0h+dwDesiredAccess], r12; PreviousState
0x14006bd5a  xor     r9d, r9d; BufferLength
0x14006bd5d  xor     r8d, r8d; NewState
0x14006bd60  mov     edx, r13d; DisableAllPrivileges
0x14006bd63  mov     rcx, [rbp+47h+TargetHandle]; TokenHandle
0x14006bd67  call    cs:__imp_AdjustTokenPrivileges
0x14006bd6e  nop     dword ptr [rax+rax+00h]
0x14006bd73  mov     rcx, [rbp+4Fh]; this
0x14006bd77  test    eax, eax
0x14006bd79  jz      loc_14006BF0F
0x14006bd7f  mov     ecx, cs:?gm_SeChangeNotifyPrivilegeId@VmWmiClientContext@Vml@@0U_LUID@@A.HighPart; _LUID Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId ...
0x14006bd85  test    ecx, ecx
0x14006bd87  jnz     short loc_14006BD96
0x14006bd89  cmp     cs:?gm_SeChangeNotifyPrivilegeId@VmWmiClientContext@Vml@@0U_LUID@@A.LowPart, r12d; _LUID Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId ...
0x14006bd90  jz      loc_14006BE49
0x14006bd96  mov     r9d, 10h; BufferLength
0x14006bd9c  mov     dword ptr [rbp+47h+ppInterface], r9d
0x14006bda0  xorps   xmm0, xmm0
0x14006bda3  movups  xmmword ptr [rbp+47h+PreviousState.PrivilegeCount], xmm0
0x14006bda7  mov     [rbp+47h+NewState.PrivilegeCount], r13d
0x14006bdab  mov     eax, cs:?gm_SeChangeNotifyPrivilegeId@VmWmiClientContext@Vml@@0U_LUID@@A.LowPart; _LUID Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId ...
0x14006bdb1  mov     [rbp+47h+NewState.Privileges.Luid.LowPart], eax
0x14006bdb4  mov     [rbp+47h+NewState.Privileges.Luid.HighPart], ecx
0x14006bdb7  mov     [rbp+47h+NewState.Privileges.Attributes], 2
0x14006bdbe  lea     rax, [rbp+47h+ppInterface]
0x14006bdc2  mov     qword ptr [rsp+0C0h+bInheritHandle], rax; ReturnLength
0x14006bdc7  lea     rax, [rbp+47h+PreviousState]
0x14006bdcb  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rax; PreviousState
0x14006bdd0  lea     r8, [rbp+47h+NewState]; NewState
0x14006bdd4  xor     edx, edx; DisableAllPrivileges
0x14006bdd6  mov     rcx, [rbp+47h+TargetHandle]; TokenHandle
0x14006bdda  call    cs:__imp_AdjustTokenPrivileges
0x14006bde1  nop     dword ptr [rax+rax+00h]
0x14006bde6  mov     rcx, [rbp+4Fh]; this
0x14006bdea  test    eax, eax
0x14006bdec  jnz     loc_14006BC7F
0x14006bdf2  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14006bdf9  mov     edx, 1B67h; void *
0x14006bdfe  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14006be04  cmp     eax, 80010117h
0x14006be09  jnz     loc_14006BECC
0x14006be0f  mov     rcx, [rbp+47h+ppInterface]
0x14006be13  jmp     loc_14006BBE9
0x14006be18  call    cs:__imp_GetLastError
0x14006be1f  nop     dword ptr [rax+rax+00h]
0x14006be24  mov     r9d, 3F0h; char *
0x14006be2a  mov     rcx, [rbp+4Fh]; this
0x14006be2e  cmp     eax, r9d
0x14006be31  jnz     loc_14006BEE5
0x14006be37  lea     r8, aOnecoreVmVmmsW_2; "onecore\\vm\\vmms\\wmibase\\vmwmi.cpp"
0x14006be3e  mov     edx, 0C34h; void *
0x14006be43  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14006be49  lea     r8, ?gm_SeChangeNotifyPrivilegeId@VmWmiClientContext@Vml@@0U_LUID@@A; lpLuid
0x14006be50  lea     rdx, Name; "SeChangeNotifyPrivilege"
0x14006be57  xor     ecx, ecx; lpSystemName
0x14006be59  call    cs:__imp_LookupPrivilegeValueW
0x14006be60  nop     dword ptr [rax+rax+00h]
0x14006be65  mov     rcx, [rbp+4Fh]; this
0x14006be69  test    eax, eax
0x14006be6b  jz      loc_14006BF21
0x14006be71  mov     ecx, cs:?gm_SeChangeNotifyPrivilegeId@VmWmiClientContext@Vml@@0U_LUID@@A.HighPart; _LUID Vml::VmWmiClientContext::gm_SeChangeNotifyPrivilegeId ...
0x14006be77  jmp     loc_14006BD96
0x14006be7c  mov     ecx, 3
0x14006be81  int     29h; Win8: RtlFailFast(ecx)
0x14006be83  mov     ecx, 2
0x14006be88  call    VmlIsDebugTraceEnabled
0x14006be8d  test    eax, eax
0x14006be8f  jz      short loc_14006BEA2
0x14006be91  lea     rdx, aADerivativeOfV; "A derivative of VmModuleBase has not be"...
0x14006be98  mov     ecx, 2
0x14006be9d  call    VmlDebugTrace
0x14006bea2  mov     rcx, [rbp+4Fh]; this
0x14006bea6  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmModules.h"
0x14006bead  mov     edx, 0A9h; void *
0x14006beb2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14006beb8  mov     rax, [rdx]
0x14006bebb  mov     rcx, rdx
0x14006bebe  mov     rax, [rax+10h]
0x14006bec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bec7  jmp     loc_14006BE0F
0x14006becc  mov     rcx, [rbp+4Fh]; this
0x14006bed0  mov     r9d, eax; char *
0x14006bed3  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\vml\\VmCom.h"
0x14006beda  mov     edx, 1806h; void *
0x14006bedf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006bee5  mov     r9d, eax; char *
0x14006bee8  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14006beef  mov     edx, 1CC3h; void *
0x14006bef4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14006befa  mov     r9d, eax; char *
0x14006befd  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\vml\\VmCom.h"
0x14006bf04  mov     edx, 1822h; void *
0x14006bf09  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x14006bf0f  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14006bf16  mov     edx, 1B12h; void *
0x14006bf1b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14006bf21  lea     r8, aOnecoreVmVmmsW_2; "onecore\\vm\\vmms\\wmibase\\vmwmi.cpp"
  ... truncated ...
```
