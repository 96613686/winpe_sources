# CSrmFunctionTracerBase::UpdateLocaITracingEnabledFlag(void)

- ea: `0x1800752c0`
- end: `0x18007543f`
- name: `?UpdateLocaITracingEnabledFlag@CSrmFunctionTracerBase@@AEAAXXZ`
- size: `383`
- prototype: `void __fastcall(CSrmFunctionTracerBase *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180071ea4`
- `0x18007434c`

## callees

- `0x1800716ec`
- `0x18007434c`
- `0x1800752c0`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180075372`
- `KERNEL32!GetCurrentProcessId` at `0x180075372`
- `KERNEL32!GetCommandLineW` at `0x180075369`
- `KERNEL32!GetCommandLineW` at `0x180075369`
- `SrmTrace!__imp_SrmIsTracingEnabledPerThread` at `0x180075325`
- `SrmTrace!__imp_SrmIsTracingEnabledPerThread` at `0x180075325`
- `SrmTrace!__imp_SrmIsTracingEnabledOnFunction` at `0x180075315`
- `SrmTrace!__imp_SrmIsTracingEnabledOnFunction` at `0x180075315`
- `SrmTrace!__imp_SrmGetTracingSequenceNumber` at `0x1800752ec`
- `SrmTrace!__imp_SrmGetTracingSequenceNumber` at `0x1800752ec`

## string_xrefs

- `0x1800753f0`: `Tracing started or updated. PID=%d, CommandLine=[%s], UserName=[%s]. SQN=[%d -> %d]`
- `0x180075390`: `CSrmFunctionTracerBase::UpdateLocaITracingEnabledFlag`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSrmFunctionTracerBase::UpdateLocaITracingEnabledFlag(CSrmFunctionTracerBase *this)
{
  int TracingSequenceNumber; // eax
  int IsTracingEnabledPerThread; // eax
  CSrmFunctionTracerBase *v4; // rcx
  int v5; // ebx
  unsigned int v6; // edi
  LPWSTR CommandLineW; // r14
  DWORD CurrentProcessId; // esi
  DWORD v9; // [rsp+28h] [rbp-D8h]
  unsigned int v10; // [rsp+40h] [rbp-C0h]
  int v11; // [rsp+48h] [rbp-B8h]
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v13; // [rsp+58h] [rbp-A8h]
  _QWORD v14[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+78h] [rbp-88h]
  int v16; // [rsp+7Ch] [rbp-84h]
  int v17; // [rsp+80h] [rbp-80h]
  _BYTE v18[96]; // [rsp+88h] [rbp-78h] BYREF
  int v19; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v20; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v21[2046]; // [rsp+F2h] [rbp-Eh] BYREF

  TracingSequenceNumber = SrmGetTracingSequenceNumber();
  if ( TracingSequenceNumber != *((_DWORD *)this + 4) )
  {
    *((_DWORD *)this + 4) = TracingSequenceNumber;
    v12 = 0;
    if ( (unsigned int)SrmIsTracingEnabledOnFunction(*((unsigned int *)this + 11), *((_QWORD *)this + 6), &v12) )
      IsTracingEnabledPerThread = v12;
    else
      IsTracingEnabledPerThread = SrmIsTracingEnabledPerThread();
    *((_DWORD *)this + 3) = IsTracingEnabledPerThread;
    if ( CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber != *((_DWORD *)this + 4) )
    {
      v20 = 0;
      memset_0(v21, 0, sizeof(v21));
      CSrmFunctionTracerBase::GetCurrentUserName(v4, &v20);
      v5 = *((_DWORD *)this + 4);
      v6 = CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber;
      CommandLineW = GetCommandLineW();
      CurrentProcessId = GetCurrentProcessId();
      v13 = v14;
      v14[0] = L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp";
      v14[1] = L"CSrmFunctionTracerBase::UpdateLocaITracingEnabledFlag";
      v14[2] = L"TRCTRCC";
      v15 = 512;
      v16 = 17;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      v11 = v5;
      v10 = v6;
      v9 = CurrentProcessId;
      CSrmFunctionTracerBase::TraceInternalWithFormat(
        this,
        v14,
        L"TRACING_STARTED",
        120,
        L"Tracing started or updated. PID=%d, CommandLine=[%s], UserName=[%s]. SQN=[%d -> %d]",
        v9,
        CommandLineW,
        &v20,
        v10,
        v11);
      CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber = *((_DWORD *)this + 4);
    }
  }
}

```

## disassembly

```asm
0x1800752c0  push    rbp
0x1800752c2  push    rbx
0x1800752c3  push    rsi
0x1800752c4  push    rdi
0x1800752c5  push    r14
0x1800752c7  push    r15
0x1800752c9  lea     rbp, [rsp-808h]
0x1800752d1  sub     rsp, 908h
0x1800752d8  mov     rax, cs:__security_cookie
0x1800752df  xor     rax, rsp
0x1800752e2  mov     [rbp+830h+var_40], rax
0x1800752e9  mov     r15, rcx
0x1800752ec  call    cs:__imp_SrmGetTracingSequenceNumber
0x1800752f2  cmp     eax, [r15+10h]
0x1800752f6  jz      loc_180075420
0x1800752fc  mov     [r15+10h], eax
0x180075300  mov     [rsp+930h+var_8E0], 0
0x180075308  lea     r8, [rsp+930h+var_8E0]
0x18007530d  mov     rdx, [r15+30h]
0x180075311  mov     ecx, [r15+2Ch]
0x180075315  call    cs:__imp_SrmIsTracingEnabledOnFunction
0x18007531b  test    eax, eax
0x18007531d  jz      short loc_180075325
0x18007531f  mov     eax, [rsp+930h+var_8E0]
0x180075323  jmp     short loc_18007532B
0x180075325  call    cs:__imp_SrmIsTracingEnabledPerThread
0x18007532b  mov     [r15+0Ch], eax
0x18007532f  mov     eax, [r15+10h]
0x180075333  cmp     cs:?m_dwGlobalTracingSettingsSequenceNumber@CSrmFunctionTracerBase@@0KA, eax; ulong CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber
0x180075339  jz      loc_180075420
0x18007533f  xor     eax, eax
0x180075341  mov     [rbp+830h+var_840], ax
0x180075345  xor     edx, edx; Val
0x180075347  mov     r8d, 7FEh; Size
0x18007534d  lea     rcx, [rbp+830h+var_83E]; void *
0x180075351  call    memset_0
0x180075356  lea     rdx, [rbp+830h+var_840]; unsigned __int16 *
0x18007535a  call    ?GetCurrentUserName@CSrmFunctionTracerBase@@QEAAXPEAGK@Z; CSrmFunctionTracerBase::GetCurrentUserName(ushort *,ulong)
0x18007535f  mov     ebx, [r15+10h]
0x180075363  mov     edi, cs:?m_dwGlobalTracingSettingsSequenceNumber@CSrmFunctionTracerBase@@0KA; ulong CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber
0x180075369  call    cs:__imp_GetCommandLineW
0x18007536f  mov     r14, rax
0x180075372  call    cs:__imp_GetCurrentProcessId
0x180075378  mov     esi, eax
0x18007537a  lea     rax, [rsp+930h+var_8D0]
0x18007537f  mov     [rsp+930h+var_8D8], rax
0x180075384  lea     rax, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x18007538b  mov     [rsp+930h+var_8D0], rax
0x180075390  lea     rax, aCsrmfunctiontr_0; "CSrmFunctionTracerBase::UpdateLocaITrac"...
0x180075397  mov     [rsp+930h+var_8C8], rax
0x18007539c  lea     rax, aTrctrcc; "TRCTRCC"
0x1800753a3  mov     [rsp+930h+var_8C0], rax
0x1800753a8  mov     [rsp+930h+var_8B8], 200h
0x1800753b0  mov     [rsp+930h+var_8B4], 11h
0x1800753b8  mov     [rbp+830h+var_8B0], 0FFh
0x1800753bf  mov     [rbp+830h+var_848], 1000000h
0x1800753c6  xor     edx, edx; Val
0x1800753c8  lea     r8d, [rdx+60h]; Size
0x1800753cc  lea     rcx, [rbp+830h+var_8A8]; void *
0x1800753d0  call    memset_0
0x1800753d5  nop
0x1800753d6  mov     [rsp+930h+var_8E8], ebx
0x1800753da  mov     [rsp+930h+var_8F0], edi
0x1800753de  lea     rax, [rbp+830h+var_840]
0x1800753e2  mov     [rsp+930h+var_8F8], rax
0x1800753e7  mov     [rsp+930h+var_900], r14
0x1800753ec  mov     [rsp+930h+var_908], esi
0x1800753f0  lea     rax, aTracingStarted_0; "Tracing started or updated. PID=%d, Com"...
0x1800753f7  mov     [rsp+930h+var_910], rax
0x1800753fc  mov     r9d, 78h ; 'x'
0x180075402  lea     r8, aTracingStarted; "TRACING_STARTED"
0x180075409  lea     rdx, [rsp+930h+var_8D0]
0x18007540e  mov     rcx, r15
0x180075411  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(CSrmDebugInfo,ushort const *,ulong,ushort const *,...)
0x180075416  mov     eax, [r15+10h]
0x18007541a  mov     cs:?m_dwGlobalTracingSettingsSequenceNumber@CSrmFunctionTracerBase@@0KA, eax; ulong CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber
0x180075420  mov     rcx, [rbp+830h+var_40]
0x180075427  xor     rcx, rsp; StackCookie
0x18007542a  call    __security_check_cookie
0x18007542f  add     rsp, 908h
0x180075436  pop     r15
0x180075438  pop     r14
0x18007543a  pop     rdi
0x18007543b  pop     rsi
0x18007543c  pop     rbx
0x18007543d  pop     rbp
0x18007543e  retn
```
