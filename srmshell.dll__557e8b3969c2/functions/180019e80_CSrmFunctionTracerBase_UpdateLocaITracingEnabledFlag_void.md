# CSrmFunctionTracerBase::UpdateLocaITracingEnabledFlag(void)

- ea: `0x180019e80`
- end: `0x180019fff`
- name: `?UpdateLocaITracingEnabledFlag@CSrmFunctionTracerBase@@AEAAXXZ`
- size: `383`
- prototype: `void __fastcall(CSrmFunctionTracerBase *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180017e38`
- `0x1800196f0`

## callees

- `0x180017820`
- `0x1800196f0`
- `0x180019e80`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019f32`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180019f29`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180019f29`
- `SrmTrace!__imp_SrmIsTracingEnabledPerThread` at `0x180019ee5`
- `SrmTrace!__imp_SrmIsTracingEnabledPerThread` at `0x180019ee5`
- `SrmTrace!__imp_SrmIsTracingEnabledOnFunction` at `0x180019ed5`
- `SrmTrace!__imp_SrmIsTracingEnabledOnFunction` at `0x180019ed5`
- `SrmTrace!__imp_SrmGetTracingSequenceNumber` at `0x180019eac`
- `SrmTrace!__imp_SrmGetTracingSequenceNumber` at `0x180019eac`

## string_xrefs

- `0x180019fb0`: `Tracing started or updated. PID=%d, CommandLine=[%s], UserName=[%s]. SQN=[%d -> %d]`
- `0x180019f50`: `CSrmFunctionTracerBase::UpdateLocaITracingEnabledFlag`

## pseudocode

```c
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
0x180019e80  push    rbp
0x180019e82  push    rbx
0x180019e83  push    rsi
0x180019e84  push    rdi
0x180019e85  push    r14
0x180019e87  push    r15
0x180019e89  lea     rbp, [rsp-808h]
0x180019e91  sub     rsp, 908h
0x180019e98  mov     rax, cs:__security_cookie
0x180019e9f  xor     rax, rsp
0x180019ea2  mov     [rbp+830h+var_40], rax
0x180019ea9  mov     r15, rcx
0x180019eac  call    cs:__imp_SrmGetTracingSequenceNumber
0x180019eb2  cmp     eax, [r15+10h]
0x180019eb6  jz      loc_180019FE0
0x180019ebc  mov     [r15+10h], eax
0x180019ec0  mov     [rsp+930h+var_8E0], 0
0x180019ec8  lea     r8, [rsp+930h+var_8E0]
0x180019ecd  mov     rdx, [r15+30h]
0x180019ed1  mov     ecx, [r15+2Ch]
0x180019ed5  call    cs:__imp_SrmIsTracingEnabledOnFunction
0x180019edb  test    eax, eax
0x180019edd  jz      short loc_180019EE5
0x180019edf  mov     eax, [rsp+930h+var_8E0]
0x180019ee3  jmp     short loc_180019EEB
0x180019ee5  call    cs:__imp_SrmIsTracingEnabledPerThread
0x180019eeb  mov     [r15+0Ch], eax
0x180019eef  mov     eax, [r15+10h]
0x180019ef3  cmp     cs:?m_dwGlobalTracingSettingsSequenceNumber@CSrmFunctionTracerBase@@0KA, eax; ulong CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber
0x180019ef9  jz      loc_180019FE0
0x180019eff  xor     eax, eax
0x180019f01  mov     [rbp+830h+var_840], ax
0x180019f05  xor     edx, edx; Val
0x180019f07  mov     r8d, 7FEh; Size
0x180019f0d  lea     rcx, [rbp+830h+var_83E]; void *
0x180019f11  call    memset_0
0x180019f16  lea     rdx, [rbp+830h+var_840]; unsigned __int16 *
0x180019f1a  call    ?GetCurrentUserName@CSrmFunctionTracerBase@@QEAAXPEAGK@Z; CSrmFunctionTracerBase::GetCurrentUserName(ushort *,ulong)
0x180019f1f  mov     ebx, [r15+10h]
0x180019f23  mov     edi, cs:?m_dwGlobalTracingSettingsSequenceNumber@CSrmFunctionTracerBase@@0KA; ulong CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber
0x180019f29  call    cs:__imp_GetCommandLineW
0x180019f2f  mov     r14, rax
0x180019f32  call    cs:__imp_GetCurrentProcessId
0x180019f38  mov     esi, eax
0x180019f3a  lea     rax, [rsp+930h+var_8D0]
0x180019f3f  mov     [rsp+930h+var_8D8], rax
0x180019f44  lea     rax, aBaseFsFsrmUtil_1; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x180019f4b  mov     [rsp+930h+var_8D0], rax
0x180019f50  lea     rax, aCsrmfunctiontr; "CSrmFunctionTracerBase::UpdateLocaITrac"...
0x180019f57  mov     [rsp+930h+var_8C8], rax
0x180019f5c  lea     rax, aTrctrcc; "TRCTRCC"
0x180019f63  mov     [rsp+930h+var_8C0], rax
0x180019f68  mov     [rsp+930h+var_8B8], 200h
0x180019f70  mov     [rsp+930h+var_8B4], 11h
0x180019f78  mov     [rbp+830h+var_8B0], 0FFh
0x180019f7f  mov     [rbp+830h+var_848], 1000000h
0x180019f86  xor     edx, edx; Val
0x180019f88  lea     r8d, [rdx+60h]; Size
0x180019f8c  lea     rcx, [rbp+830h+var_8A8]; void *
0x180019f90  call    memset_0
0x180019f95  nop
0x180019f96  mov     [rsp+930h+var_8E8], ebx
0x180019f9a  mov     [rsp+930h+var_8F0], edi
0x180019f9e  lea     rax, [rbp+830h+var_840]
0x180019fa2  mov     [rsp+930h+var_8F8], rax
0x180019fa7  mov     [rsp+930h+var_900], r14
0x180019fac  mov     [rsp+930h+var_908], esi
0x180019fb0  lea     rax, aTracingStarted_0; "Tracing started or updated. PID=%d, Com"...
0x180019fb7  mov     [rsp+930h+var_910], rax
0x180019fbc  mov     r9d, 78h ; 'x'
0x180019fc2  lea     r8, aTracingStarted; "TRACING_STARTED"
0x180019fc9  lea     rdx, [rsp+930h+var_8D0]
0x180019fce  mov     rcx, r15
0x180019fd1  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(CSrmDebugInfo,ushort const *,ulong,ushort const *,...)
0x180019fd6  mov     eax, [r15+10h]
0x180019fda  mov     cs:?m_dwGlobalTracingSettingsSequenceNumber@CSrmFunctionTracerBase@@0KA, eax; ulong CSrmFunctionTracerBase::m_dwGlobalTracingSettingsSequenceNumber
0x180019fe0  mov     rcx, [rbp+830h+var_40]
0x180019fe7  xor     rcx, rsp; StackCookie
0x180019fea  call    __security_check_cookie
0x180019fef  add     rsp, 908h
0x180019ff6  pop     r15
0x180019ff8  pop     r14
0x180019ffa  pop     rdi
0x180019ffb  pop     rsi
0x180019ffc  pop     rbx
0x180019ffd  pop     rbp
0x180019ffe  retn
```
