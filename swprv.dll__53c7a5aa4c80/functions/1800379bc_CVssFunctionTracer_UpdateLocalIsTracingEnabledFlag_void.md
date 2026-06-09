# CVssFunctionTracer::UpdateLocalIsTracingEnabledFlag(void)

- ea: `0x1800379bc`
- end: `0x180037b40`
- name: `?UpdateLocalIsTracingEnabledFlag@CVssFunctionTracer@@AEAAXXZ`
- size: `388`
- prototype: `void __fastcall(CVssFunctionTracer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800356a8`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180035198`
- `0x1800356ec`
- `0x180036af8`
- `0x1800379bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037a7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180037a7d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180037a74`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180037a74`
- `VssTrace!__imp_VssIsTracingEnabledPerThread` at `0x180037a31`
- `VssTrace!__imp_VssIsTracingEnabledPerThread` at `0x180037a31`
- `VssTrace!__imp_VssIsTracingEnabledOnFunction` at `0x180037a11`
- `VssTrace!__imp_VssIsTracingEnabledOnFunction` at `0x180037a11`
- `VssTrace!__imp_VssGetTracingSequenceNumber` at `0x1800379e8`
- `VssTrace!__imp_VssGetTracingSequenceNumber` at `0x1800379e8`

## string_xrefs

- `0x180037af9`: `Tracing started or updated. PID=%d, CommandLine=[%s], UserName=[%s]. SQN=[%d -> %d]`
- `0x180037aaf`: `CVssFunctionTracer::UpdateLocalIsTracingEnabledFlag`

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
0x1800379bc  push    rbp
0x1800379be  push    rbx
0x1800379bf  push    rsi
0x1800379c0  push    rdi
0x1800379c1  push    r14
0x1800379c3  push    r15
0x1800379c5  lea     rbp, [rsp-818h]
0x1800379cd  sub     rsp, 918h
0x1800379d4  mov     rax, cs:__security_cookie
0x1800379db  xor     rax, rsp
0x1800379de  mov     [rbp+840h+var_40], rax
0x1800379e5  mov     r15, rcx
0x1800379e8  call    cs:__imp_VssGetTracingSequenceNumber
0x1800379ee  cmp     eax, [r15+4]
0x1800379f2  jz      loc_180037B21
0x1800379f8  mov     rdx, [r15+28h]
0x1800379fc  lea     r8, [rsp+940h+var_8F0]
0x180037a01  mov     ecx, [r15+24h]
0x180037a05  mov     [r15+4], eax
0x180037a09  mov     [rsp+940h+var_8F0], 0
0x180037a11  call    cs:__imp_VssIsTracingEnabledOnFunction
0x180037a17  test    eax, eax
0x180037a19  jz      short loc_180037A21
0x180037a1b  mov     eax, [rsp+940h+var_8F0]
0x180037a1f  jmp     short loc_180037A37
0x180037a21  mov     rcx, [r15+60h]; this
0x180037a25  test    rcx, rcx
0x180037a28  jz      short loc_180037A31
0x180037a2a  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x180037a2f  jmp     short loc_180037A37
0x180037a31  call    cs:__imp_VssIsTracingEnabledPerThread
0x180037a37  mov     [r15], eax
0x180037a3a  mov     eax, [r15+4]
0x180037a3e  cmp     cs:?m_dwGlobalTracingSettingsSequenceNumber@CVssFunctionTracer@@0KA, eax; ulong CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber
0x180037a44  jz      loc_180037B21
0x180037a4a  xor     eax, eax
0x180037a4c  lea     rcx, [rbp+840h+var_83E]; void *
0x180037a50  xor     edx, edx; Val
0x180037a52  mov     [rbp+840h+var_840], ax
0x180037a56  mov     r8d, 7FEh; Size
0x180037a5c  call    memset_0
0x180037a61  lea     rdx, [rbp+840h+var_840]; unsigned __int16 *
0x180037a65  call    ?GetCurrentUserName@CVssFunctionTracer@@QEAAXPEAGK@Z; CVssFunctionTracer::GetCurrentUserName(ushort *,ulong)
0x180037a6a  mov     ebx, [r15+4]
0x180037a6e  mov     edi, cs:?m_dwGlobalTracingSettingsSequenceNumber@CVssFunctionTracer@@0KA; ulong CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber
0x180037a74  call    cs:__imp_GetCommandLineW
0x180037a7a  mov     r14, rax
0x180037a7d  call    cs:__imp_GetCurrentProcessId
0x180037a83  xor     edx, edx; Val
0x180037a85  mov     [rsp+940h+var_8D0], 24Fh
0x180037a8d  mov     esi, eax
0x180037a8f  mov     [rsp+940h+var_8CC], 0Bh
0x180037a97  lea     rax, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x180037a9e  mov     [rsp+940h+var_8C8], 0FFh
0x180037aa6  mov     [rsp+940h+var_8E8], rax
0x180037aab  lea     rcx, [rbp+840h+var_8C0]; void *
0x180037aaf  lea     rax, aCvssfunctiontr; "CVssFunctionTracer::UpdateLocalIsTracin"...
0x180037ab6  mov     [rbp+840h+var_848], 1000000h
0x180037abd  mov     [rsp+940h+var_8E0], rax
0x180037ac2  lea     r8d, [rdx+78h]; Size
0x180037ac6  lea     rax, aTrctrcc; "TRCTRCC"
0x180037acd  mov     [rsp+940h+var_8D8], rax
0x180037ad2  call    memset_0
0x180037ad7  mov     [rsp+940h+var_8F8], ebx
0x180037adb  lea     rax, [rbp+840h+var_840]
0x180037adf  mov     [rsp+940h+var_900], edi
0x180037ae3  lea     r8, aTracingStarted; "TRACING_STARTED"
0x180037aea  mov     [rsp+940h+var_908], rax
0x180037aef  lea     rdx, [rsp+940h+var_8E8]
0x180037af4  mov     [rsp+940h+var_910], r14
0x180037af9  lea     rax, aTracingStarted_0; "Tracing started or updated. PID=%d, Com"...
0x180037b00  mov     [rsp+940h+var_918], esi
0x180037b04  mov     r9d, 78h ; 'x'
0x180037b0a  mov     rcx, r15
0x180037b0d  mov     [rsp+940h+var_920], rax
0x180037b12  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1ZZ; CVssFunctionTracer::TraceInternalWithFormat(CVssDebugInfo,ushort const *,ulong,ushort const *,...)
0x180037b17  mov     eax, [r15+4]
0x180037b1b  mov     cs:?m_dwGlobalTracingSettingsSequenceNumber@CVssFunctionTracer@@0KA, eax; ulong CVssFunctionTracer::m_dwGlobalTracingSettingsSequenceNumber
0x180037b21  mov     rcx, [rbp+840h+var_40]
0x180037b28  xor     rcx, rsp; StackCookie
0x180037b2b  call    __security_check_cookie
0x180037b30  add     rsp, 918h
0x180037b37  pop     r15
0x180037b39  pop     r14
0x180037b3b  pop     rdi
0x180037b3c  pop     rsi
0x180037b3d  pop     rbx
0x180037b3e  pop     rbp
0x180037b3f  retn
```
