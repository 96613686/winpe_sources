# COleScript::~COleScript(void)

- ea: `0x1800140e4`
- end: `0x1800142b9`
- name: `??1COleScript@@UEAA@XZ`
- size: `469`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180013f70`
- `0x18001ecc0`

## callees

- `0x1800140e4`
- `0x1800142c0`
- `0x18001e32c`
- `0x18004289c`
- `0x1800428c4`
- `0x180042ccc`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800142a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142a8`
- `KERNEL32!FreeLibrary` at `0x180014273`
- `KERNEL32!FreeLibrary` at `0x180014273`
- `KERNEL32!DeleteCriticalSection` at `0x180014262`
- `KERNEL32!DeleteCriticalSection` at `0x180014262`
- `KERNEL32!GetProcAddress` at `0x1800141f0`
- `KERNEL32!GetProcAddress` at `0x1800141f0`

## string_xrefs

- `0x1800141e9`: `AmsiUninitialize`

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
0x1800140e4  push    rbx
0x1800140e6  sub     rsp, 20h
0x1800140ea  lea     rax, ??_7COleScript@@6BIActiveScript@@@; const COleScript::`vftable'{for `IActiveScript'}
0x1800140f1  mov     rbx, rcx
0x1800140f4  mov     [rcx], rax
0x1800140f7  lea     rax, ??_7COleScript@@6BIActiveScriptParse64@@@; const COleScript::`vftable'{for `IActiveScriptParse64'}
0x1800140fe  mov     [rcx+8], rax
0x180014102  lea     rax, ??_7COleScript@@6BIActiveScriptProperty@@@; const COleScript::`vftable'{for `IActiveScriptProperty'}
0x180014109  mov     [rcx+10h], rax
0x18001410d  lea     rax, ??_7COleScript@@6BIActiveScriptEncode@@@; const COleScript::`vftable'{for `IActiveScriptEncode'}
0x180014114  mov     [rcx+18h], rax
0x180014118  lea     rax, ??_7COleScript@@6BIActiveScriptDebug64@@@; const COleScript::`vftable'{for `IActiveScriptDebug64'}
0x18001411f  mov     [rcx+20h], rax
0x180014123  lea     rax, ??_7COleScript@@6BIDebugStackFrameSnifferEx64@@@; const COleScript::`vftable'{for `IDebugStackFrameSnifferEx64'}
0x18001412a  mov     [rcx+28h], rax
0x18001412e  lea     rax, ??_7COleScript@@6BIProvideExpressionContexts@@@; const COleScript::`vftable'{for `IProvideExpressionContexts'}
0x180014135  mov     [rcx+30h], rax
0x180014139  lea     rax, ??_7COleScript@@6BIRemoteDebugApplicationEvents@@@; const COleScript::`vftable'{for `IRemoteDebugApplicationEvents'}
0x180014140  mov     [rcx+38h], rax
0x180014144  lea     rax, ??_7COleScript@@6BIActiveScriptParseProcedure2_64@@@; const COleScript::`vftable'{for `IActiveScriptParseProcedure2_64'}
0x18001414b  mov     [rcx+40h], rax
0x18001414f  lea     rax, ??_7COleScript@@6BIHostInfoUpdate@@@; const COleScript::`vftable'{for `IHostInfoUpdate'}
0x180014156  mov     [rcx+48h], rax
0x18001415a  lea     rax, ??_7COleScript@@6BIWrapTypeLibs@@@; const COleScript::`vftable'{for `IWrapTypeLibs'}
0x180014161  mov     [rcx+50h], rax
0x180014165  lea     rax, ??_7COleScript@@6BIScriptHelper@@@; const COleScript::`vftable'{for `IScriptHelper'}
0x18001416c  mov     [rcx+58h], rax
0x180014170  lea     rax, ??_7COleScript@@6BIObjectSafety@@@; const COleScript::`vftable'{for `IObjectSafety'}
0x180014177  mov     [rcx+60h], rax
0x18001417b  lea     rax, ??_7COleScript@@6BIVariantChangeType@@@; const COleScript::`vftable'{for `IVariantChangeType'}
0x180014182  mov     [rcx+68h], rax
0x180014186  lea     rax, ??_7COleScript@@6BIActiveScriptStats@@@; const COleScript::`vftable'{for `IActiveScriptStats'}
0x18001418d  mov     [rcx+70h], rax
0x180014191  lea     rax, ??_7COleScript@@6BIActiveScriptTraceInfo@@@; const COleScript::`vftable'{for `IActiveScriptTraceInfo'}
0x180014198  mov     [rcx+78h], rax
0x18001419c  lea     rax, ??_7COleScript@@6BIActiveScriptSIPInfo@@@; const COleScript::`vftable'{for `IActiveScriptSIPInfo'}
0x1800141a3  mov     [rcx+80h], rax
0x1800141aa  call    ?Close@COleScript@@UEAAJXZ; COleScript::Close(void)
0x1800141af  cmp     dword ptr [rbx+210h], 0
0x1800141b6  jnz     loc_18001425B
0x1800141bc  lea     rcx, [rbx+240h]; struct tagEXCEPINFO *
0x1800141c3  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x1800141c8  mov     rcx, [rbx+388h]
0x1800141cf  test    rcx, rcx
0x1800141d2  jnz     loc_18001428C
0x1800141d8  cmp     qword ptr [rbx+3A0h], 0
0x1800141e0  jz      short loc_180014213
0x1800141e2  mov     rcx, [rbx+3C0h]; hModule
0x1800141e9  lea     rdx, ProcName; "AmsiUninitialize"
0x1800141f0  call    cs:__imp_GetProcAddress
0x1800141f7  nop     dword ptr [rax+rax+00h]
0x1800141fc  mov     rcx, [rbx+3A0h]
0x180014203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014208  mov     qword ptr [rbx+3A0h], 0
0x180014213  mov     rcx, [rbx+3C0h]; hLibModule
0x18001421a  test    rcx, rcx
0x18001421d  jnz     short loc_180014273
0x18001421f  mov     rcx, [rbx+3B0h]; bstrString
0x180014226  test    rcx, rcx
0x180014229  jnz     short loc_1800142A8
0x18001422b  lock dec cs:?g_cLibRef@@3JA; long g_cLibRef
0x180014232  lea     rcx, [rbx+328h]; this
0x180014239  call    ??1MUTX@@QEAA@XZ; MUTX::~MUTX(void)
0x18001423e  lea     rcx, [rbx+118h]; this
0x180014245  call    ??1NamedItemList@@QEAA@XZ; NamedItemList::~NamedItemList(void)
0x18001424a  lea     rcx, [rbx+0C8h]; this
0x180014251  add     rsp, 20h
0x180014255  pop     rbx
0x180014256  jmp     ??1JAmsi@@QEAA@XZ; JAmsi::~JAmsi(void)
0x18001425b  lea     rcx, [rbx+218h]; lpCriticalSection
0x180014262  call    cs:__imp_DeleteCriticalSection
0x180014269  nop     dword ptr [rax+rax+00h]
0x18001426e  jmp     loc_1800141BC
0x180014273  call    cs:__imp_FreeLibrary
0x18001427a  nop     dword ptr [rax+rax+00h]
0x18001427f  mov     qword ptr [rbx+3C0h], 0
0x18001428a  jmp     short loc_18001421F
0x18001428c  mov     rax, [rcx]
0x18001428f  mov     rax, [rax+10h]
0x180014293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014298  mov     qword ptr [rbx+388h], 0
0x1800142a3  jmp     loc_1800141D8
0x1800142a8  call    cs:__imp_SysFreeString
0x1800142af  nop     dword ptr [rax+rax+00h]
0x1800142b4  jmp     loc_18001422B
```
