# COleScript::~COleScript(void)

- ea: `0x1800194b0`
- end: `0x18001966a`
- name: `??1COleScript@@UEAA@XZ`
- size: `442`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180019340`
- `0x1800238b0`

## callees

- `0x1800194b0`
- `0x180019670`
- `0x180022e44`
- `0x1800415b8`
- `0x1800415e0`
- `0x180041928`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180019662`
- `OLEAUT32!__imp_SysFreeString` at `0x180019662`
- `KERNEL32!FreeLibrary` at `0x180019633`
- `KERNEL32!FreeLibrary` at `0x180019633`
- `KERNEL32!DeleteCriticalSection` at `0x180019628`
- `KERNEL32!DeleteCriticalSection` at `0x180019628`
- `KERNEL32!GetProcAddress` at `0x1800195bc`
- `KERNEL32!GetProcAddress` at `0x1800195bc`

## string_xrefs

- `0x1800195b5`: `AmsiUninitialize`

## pseudocode

```c
void __fastcall COleScript::~COleScript(COleScript *this)
{
  __int64 v2; // rcx
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx
  OLECHAR *v5; // rcx

  *(_QWORD *)this = &COleScript::`vftable'{for `IActiveScript'};
  *((_QWORD *)this + 1) = &COleScript::`vftable'{for `IActiveScriptParse64'};
  *((_QWORD *)this + 2) = &COleScript::`vftable'{for `IActiveScriptProperty'};
  *((_QWORD *)this + 3) = &COleScript::`vftable'{for `IActiveScriptEncode'};
  *((_QWORD *)this + 4) = &COleScript::`vftable'{for `IActiveScriptDebug64'};
  *((_QWORD *)this + 5) = &COleScript::`vftable'{for `IDebugStackFrameSnifferEx64'};
  *((_QWORD *)this + 6) = &COleScript::`vftable'{for `IProvideExpressionContexts'};
  *((_QWORD *)this + 7) = &COleScript::`vftable'{for `IRemoteDebugApplicationEvents'};
  *((_QWORD *)this + 8) = &COleScript::`vftable'{for `IActiveScriptParseProcedure2_64'};
  *((_QWORD *)this + 9) = &COleScript::`vftable'{for `IHostInfoUpdate'};
  *((_QWORD *)this + 10) = &COleScript::`vftable'{for `IWrapTypeLibs'};
  *((_QWORD *)this + 11) = &COleScript::`vftable'{for `IScriptHelper'};
  *((_QWORD *)this + 12) = &COleScript::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 13) = &COleScript::`vftable'{for `IVariantChangeType'};
  *((_QWORD *)this + 14) = &COleScript::`vftable'{for `IActiveScriptStats'};
  *((_QWORD *)this + 15) = &COleScript::`vftable'{for `IActiveScriptTraceInfo'};
  *((_QWORD *)this + 16) = &COleScript::`vftable'{for `IActiveScriptSIPInfo'};
  COleScript::Close(this);
  if ( *((_DWORD *)this + 132) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  FreeExcepInfo((struct tagEXCEPINFO *)this + 9);
  v2 = *((_QWORD *)this + 113);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 113) = 0;
  }
  if ( *((_QWORD *)this + 116) )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)this + 120), "AmsiUninitialize");
    ((void (__fastcall *)(_QWORD))ProcAddress)(*((_QWORD *)this + 116));
    *((_QWORD *)this + 116) = 0;
  }
  v4 = (HMODULE)*((_QWORD *)this + 120);
  if ( v4 )
  {
    FreeLibrary(v4);
    *((_QWORD *)this + 120) = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 118);
  if ( v5 )
    SysFreeString(v5);
  _InterlockedDecrement(&g_cLibRef);
  MUTX::~MUTX((COleScript *)((char *)this + 808));
  NamedItemList::~NamedItemList((COleScript *)((char *)this + 280));
  JAmsi::~JAmsi((COleScript *)((char *)this + 200));
}

```

## disassembly

```asm
0x1800194b0  push    rbx
0x1800194b2  sub     rsp, 20h
0x1800194b6  lea     rax, ??_7COleScript@@6BIActiveScript@@@; const COleScript::`vftable'{for `IActiveScript'}
0x1800194bd  mov     rbx, rcx
0x1800194c0  mov     [rcx], rax
0x1800194c3  lea     rax, ??_7COleScript@@6BIActiveScriptParse64@@@; const COleScript::`vftable'{for `IActiveScriptParse64'}
0x1800194ca  mov     [rcx+8], rax
0x1800194ce  lea     rax, ??_7COleScript@@6BIActiveScriptProperty@@@; const COleScript::`vftable'{for `IActiveScriptProperty'}
0x1800194d5  mov     [rcx+10h], rax
0x1800194d9  lea     rax, ??_7COleScript@@6BIActiveScriptEncode@@@; const COleScript::`vftable'{for `IActiveScriptEncode'}
0x1800194e0  mov     [rcx+18h], rax
0x1800194e4  lea     rax, ??_7COleScript@@6BIActiveScriptDebug64@@@; const COleScript::`vftable'{for `IActiveScriptDebug64'}
0x1800194eb  mov     [rcx+20h], rax
0x1800194ef  lea     rax, ??_7COleScript@@6BIDebugStackFrameSnifferEx64@@@; const COleScript::`vftable'{for `IDebugStackFrameSnifferEx64'}
0x1800194f6  mov     [rcx+28h], rax
0x1800194fa  lea     rax, ??_7COleScript@@6BIProvideExpressionContexts@@@; const COleScript::`vftable'{for `IProvideExpressionContexts'}
0x180019501  mov     [rcx+30h], rax
0x180019505  lea     rax, ??_7COleScript@@6BIRemoteDebugApplicationEvents@@@; const COleScript::`vftable'{for `IRemoteDebugApplicationEvents'}
0x18001950c  mov     [rcx+38h], rax
0x180019510  lea     rax, ??_7COleScript@@6BIActiveScriptParseProcedure2_64@@@; const COleScript::`vftable'{for `IActiveScriptParseProcedure2_64'}
0x180019517  mov     [rcx+40h], rax
0x18001951b  lea     rax, ??_7COleScript@@6BIHostInfoUpdate@@@; const COleScript::`vftable'{for `IHostInfoUpdate'}
0x180019522  mov     [rcx+48h], rax
0x180019526  lea     rax, ??_7COleScript@@6BIWrapTypeLibs@@@; const COleScript::`vftable'{for `IWrapTypeLibs'}
0x18001952d  mov     [rcx+50h], rax
0x180019531  lea     rax, ??_7COleScript@@6BIScriptHelper@@@; const COleScript::`vftable'{for `IScriptHelper'}
0x180019538  mov     [rcx+58h], rax
0x18001953c  lea     rax, ??_7COleScript@@6BIObjectSafety@@@; const COleScript::`vftable'{for `IObjectSafety'}
0x180019543  mov     [rcx+60h], rax
0x180019547  lea     rax, ??_7COleScript@@6BIVariantChangeType@@@; const COleScript::`vftable'{for `IVariantChangeType'}
0x18001954e  mov     [rcx+68h], rax
0x180019552  lea     rax, ??_7COleScript@@6BIActiveScriptStats@@@; const COleScript::`vftable'{for `IActiveScriptStats'}
0x180019559  mov     [rcx+70h], rax
0x18001955d  lea     rax, ??_7COleScript@@6BIActiveScriptTraceInfo@@@; const COleScript::`vftable'{for `IActiveScriptTraceInfo'}
0x180019564  mov     [rcx+78h], rax
0x180019568  lea     rax, ??_7COleScript@@6BIActiveScriptSIPInfo@@@; const COleScript::`vftable'{for `IActiveScriptSIPInfo'}
0x18001956f  mov     [rcx+80h], rax
0x180019576  call    ?Close@COleScript@@UEAAJXZ; COleScript::Close(void)
0x18001957b  cmp     dword ptr [rbx+210h], 0
0x180019582  jnz     loc_180019621
0x180019588  lea     rcx, [rbx+240h]; struct tagEXCEPINFO *
0x18001958f  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180019594  mov     rcx, [rbx+388h]
0x18001959b  test    rcx, rcx
0x18001959e  jnz     loc_180019646
0x1800195a4  cmp     qword ptr [rbx+3A0h], 0
0x1800195ac  jz      short loc_1800195D9
0x1800195ae  mov     rcx, [rbx+3C0h]; hModule
0x1800195b5  lea     rdx, ProcName; "AmsiUninitialize"
0x1800195bc  call    cs:__imp_GetProcAddress
0x1800195c2  mov     rcx, [rbx+3A0h]
0x1800195c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195ce  mov     qword ptr [rbx+3A0h], 0
0x1800195d9  mov     rcx, [rbx+3C0h]; hLibModule
0x1800195e0  test    rcx, rcx
0x1800195e3  jnz     short loc_180019633
0x1800195e5  mov     rcx, [rbx+3B0h]; bstrString
0x1800195ec  test    rcx, rcx
0x1800195ef  jnz     short loc_180019662
0x1800195f1  lock dec cs:?g_cLibRef@@3JA; long g_cLibRef
0x1800195f8  lea     rcx, [rbx+328h]; this
0x1800195ff  call    ??1MUTX@@QEAA@XZ; MUTX::~MUTX(void)
0x180019604  lea     rcx, [rbx+118h]; this
0x18001960b  call    ??1NamedItemList@@QEAA@XZ; NamedItemList::~NamedItemList(void)
0x180019610  lea     rcx, [rbx+0C8h]; this
0x180019617  add     rsp, 20h
0x18001961b  pop     rbx
0x18001961c  jmp     ??1JAmsi@@QEAA@XZ; JAmsi::~JAmsi(void)
0x180019621  lea     rcx, [rbx+218h]; lpCriticalSection
0x180019628  call    cs:__imp_DeleteCriticalSection
0x18001962e  jmp     loc_180019588
0x180019633  call    cs:__imp_FreeLibrary
0x180019639  mov     qword ptr [rbx+3C0h], 0
0x180019644  jmp     short loc_1800195E5
0x180019646  mov     rax, [rcx]
0x180019649  mov     rax, [rax+10h]
0x18001964d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019652  mov     qword ptr [rbx+388h], 0
0x18001965d  jmp     loc_1800195A4
0x180019662  call    cs:__imp_SysFreeString
0x180019668  jmp     short loc_1800195F1
```
