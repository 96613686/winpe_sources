# CVssFunctionTracer::UpdateLocalIsTracingEnabledFlag(void)

- ea: `0x1400ce55c`
- end: `0x1400ce6e0`
- name: `?UpdateLocalIsTracingEnabledFlag@CVssFunctionTracer@@AEAAXXZ`
- size: `388`
- prototype: `void __fastcall(CVssFunctionTracer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140013c60`

## callees

- `0x140013cb0`
- `0x1400144d0`
- `0x14004073c`
- `0x140091560`
- `0x1400921dc`
- `0x1400ce55c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400ce61d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400ce61d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400ce614`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400ce614`
- `VssTrace!__imp_VssIsTracingEnabledPerThread` at `0x1400ce5d1`
- `VssTrace!__imp_VssIsTracingEnabledPerThread` at `0x1400ce5d1`
- `VssTrace!__imp_VssIsTracingEnabledOnFunction` at `0x1400ce5b1`
- `VssTrace!__imp_VssIsTracingEnabledOnFunction` at `0x1400ce5b1`
- `VssTrace!__imp_VssGetTracingSequenceNumber` at `0x1400ce588`
- `VssTrace!__imp_VssGetTracingSequenceNumber` at `0x1400ce588`

## string_xrefs

- `0x1400ce699`: `Tracing started or updated. PID=%d, CommandLine=[%s], UserName=[%s]. SQN=[%d -> %d]`
- `0x1400ce64f`: `CVssFunctionTracer::UpdateLocalIsTracingEnabledFlag`

## pseudocode

```c
void __fastcall CVssFunctionTracer::UpdateLocalIsTracingEnabledFlag(CVssFunctionTracer *this)
{
  int TracingSequenceNumber; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  int IsTracingEnabled; // eax
  CVssFunctionTracer *v6; // rcx
  CVssFunctionTracer *v7; // rcx
  int v8; // ebx
  unsigned int v9; // edi
  LPWSTR CommandLineW; // r14
  DWORD CurrentProcessId; // eax
  DWORD v12; // esi
  DWORD v13; // [rsp+28h] [rbp-D8h]
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+74h] [rbp-8Ch]
  int v20; // [rsp+78h] [rbp-88h]
  char v21[120]; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v23; // [rsp+100h] [rbp+0h] BYREF
  char v24[2046]; // [rsp+102h] [rbp+2h] BYREF

  TracingSequenceNumber = VssGetTracingSequenceNumber();
  if ( TracingSequenceNumber != *((_DWORD *)this + 1) )
  {
    v3 = *((_QWORD *)this + 5);
    v4 = *((unsigned int *)this + 9);
    *((_DWORD *)this + 1) = TracingSequenceNumber;
    v16 = 0;
    if ( (unsigned int)VssIsTracingEnabledOnFunction(v4, v3, &v16) )
    {
      IsTracingEnabled = v16;
    }
    else
    {
      v6 = (CVssFunctionTracer *)*((_QWORD *)this + 12);
      if ( v6 )
        IsTracingEnabled = CVssFunctionTracer::IsTracingEnabled(v6);
      else
        IsTracingEnabled = VssIsTracingEnabledPerThread();
    }
    *(_DWORD *)this = IsTracingEnabled;
    if ( CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber != *((_DWORD *)this + 1) )
    {
      v23 = 0;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::GetCurrentUserName(v7, &v23);
      v8 = *((_DWORD *)this + 1);
      v9 = CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber;
      CommandLineW = GetCommandLineW();
      CurrentProcessId = GetCurrentProcessId();
      v18 = 591;
      v12 = CurrentProcessId;
      v19 = 11;
      v20 = 255;
      v17[0] = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v22 = 0x1000000;
      v17[1] = L"CVssFunctionTracer::UpdateLocalIsTracingEnabledFlag";
      v17[2] = L"TRCTRCC";
      memset_0(v21, 0, sizeof(v21));
      v15 = v8;
      v14 = v9;
      v13 = v12;
      CVssFunctionTracer::TraceInternalWithFormat(
        this,
        v17,
        L"TRACING_STARTED",
        120,
        L"Tracing started or updated. PID=%d, CommandLine=[%s], UserName=[%s]. SQN=[%d -> %d]",
        v13,
        CommandLineW,
        &v23,
        v14,
        v15);
      CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber = *((_DWORD *)this + 1);
    }
  }
}

```

## disassembly

```asm
0x1400ce55c  push    rbp
0x1400ce55e  push    rbx
0x1400ce55f  push    rsi
0x1400ce560  push    rdi
0x1400ce561  push    r14
0x1400ce563  push    r15
0x1400ce565  lea     rbp, [rsp-818h]
0x1400ce56d  sub     rsp, 918h
0x1400ce574  mov     rax, cs:__security_cookie
0x1400ce57b  xor     rax, rsp
0x1400ce57e  mov     [rbp+840h+var_40], rax
0x1400ce585  mov     r15, rcx
0x1400ce588  call    cs:__imp_VssGetTracingSequenceNumber
0x1400ce58e  cmp     eax, [r15+4]
0x1400ce592  jz      loc_1400CE6C1
0x1400ce598  mov     rdx, [r15+28h]
0x1400ce59c  lea     r8, [rsp+940h+var_8F0]
0x1400ce5a1  mov     ecx, [r15+24h]
0x1400ce5a5  mov     [r15+4], eax
0x1400ce5a9  mov     [rsp+940h+var_8F0], 0
0x1400ce5b1  call    cs:__imp_VssIsTracingEnabledOnFunction
0x1400ce5b7  test    eax, eax
0x1400ce5b9  jz      short loc_1400CE5C1
0x1400ce5bb  mov     eax, [rsp+940h+var_8F0]
0x1400ce5bf  jmp     short loc_1400CE5D7
0x1400ce5c1  mov     rcx, [r15+60h]; this
0x1400ce5c5  test    rcx, rcx
0x1400ce5c8  jz      short loc_1400CE5D1
0x1400ce5ca  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x1400ce5cf  jmp     short loc_1400CE5D7
0x1400ce5d1  call    cs:__imp_VssIsTracingEnabledPerThread
0x1400ce5d7  mov     [r15], eax
0x1400ce5da  mov     eax, [r15+4]
0x1400ce5de  cmp     cs:?m_dwGlobalTracingSettingsSequenceNumber@CVssFunctionTracer@@0KA, eax; ulong CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber
0x1400ce5e4  jz      loc_1400CE6C1
0x1400ce5ea  xor     eax, eax
0x1400ce5ec  lea     rcx, [rbp+840h+var_83E]; void *
0x1400ce5f0  xor     edx, edx; Val
0x1400ce5f2  mov     [rbp+840h+var_840], ax
0x1400ce5f6  mov     r8d, 7FEh; Size
0x1400ce5fc  call    memset_0
0x1400ce601  lea     rdx, [rbp+840h+var_840]; unsigned __int16 *
0x1400ce605  call    ?GetCurrentUserName@CVssFunctionTracer@@QEAAXPEAGK@Z; CVssFunctionTracer::GetCurrentUserName(ushort *,ulong)
0x1400ce60a  mov     ebx, [r15+4]
0x1400ce60e  mov     edi, cs:?m_dwGlobalTracingSettingsSequenceNumber@CVssFunctionTracer@@0KA; ulong CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber
0x1400ce614  call    cs:__imp_GetCommandLineW
0x1400ce61a  mov     r14, rax
0x1400ce61d  call    cs:__imp_GetCurrentProcessId
0x1400ce623  xor     edx, edx; Val
0x1400ce625  mov     [rsp+940h+var_8D0], 24Fh
0x1400ce62d  mov     esi, eax
0x1400ce62f  mov     [rsp+940h+var_8CC], 0Bh
0x1400ce637  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x1400ce63e  mov     [rsp+940h+var_8C8], 0FFh
0x1400ce646  mov     [rsp+940h+var_8E8], rax
0x1400ce64b  lea     rcx, [rbp+840h+var_8C0]; void *
0x1400ce64f  lea     rax, aCvssfunctiontr; "CVssFunctionTracer::UpdateLocalIsTracin"...
0x1400ce656  mov     [rbp+840h+var_848], 1000000h
0x1400ce65d  mov     [rsp+940h+var_8E0], rax
0x1400ce662  lea     r8d, [rdx+78h]; Size
0x1400ce666  lea     rax, aTrctrcc; "TRCTRCC"
0x1400ce66d  mov     [rsp+940h+var_8D8], rax
0x1400ce672  call    memset_0
0x1400ce677  mov     [rsp+940h+var_8F8], ebx
0x1400ce67b  lea     rax, [rbp+840h+var_840]
0x1400ce67f  mov     [rsp+940h+var_900], edi
0x1400ce683  lea     r8, aTracingStarted; "TRACING_STARTED"
0x1400ce68a  mov     [rsp+940h+var_908], rax
0x1400ce68f  lea     rdx, [rsp+940h+var_8E8]
0x1400ce694  mov     [rsp+940h+var_910], r14
0x1400ce699  lea     rax, aTracingStarted_0; "Tracing started or updated. PID=%d, Com"...
0x1400ce6a0  mov     [rsp+940h+var_918], esi
0x1400ce6a4  mov     r9d, 78h ; 'x'
0x1400ce6aa  mov     rcx, r15
0x1400ce6ad  mov     [rsp+940h+var_920], rax
0x1400ce6b2  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1ZZ; CVssFunctionTracer::TraceInternalWithFormat(CVssDebugInfo,ushort const *,ulong,ushort const *,...)
0x1400ce6b7  mov     eax, [r15+4]
0x1400ce6bb  mov     cs:?m_dwGlobalTracingSettingsSequenceNumber@CVssFunctionTracer@@0KA, eax; ulong CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber
0x1400ce6c1  mov     rcx, [rbp+840h+var_40]
0x1400ce6c8  xor     rcx, rsp; StackCookie
0x1400ce6cb  call    __security_check_cookie
0x1400ce6d0  add     rsp, 918h
0x1400ce6d7  pop     r15
0x1400ce6d9  pop     r14
0x1400ce6db  pop     rdi
0x1400ce6dc  pop     rsi
0x1400ce6dd  pop     rbx
0x1400ce6de  pop     rbp
0x1400ce6df  retn
```
