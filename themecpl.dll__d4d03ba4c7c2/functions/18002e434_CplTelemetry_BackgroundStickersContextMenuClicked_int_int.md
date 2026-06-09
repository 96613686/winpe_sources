# CplTelemetry::BackgroundStickersContextMenuClicked<int &>(int &)

- ea: `0x18002e434`
- end: `0x18002e589`
- name: `??$BackgroundStickersContextMenuClicked@AEAH@CplTelemetry@@SAXAEAH@Z`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180030ef0`

## callees

- `0x1800019e0`
- `0x180002280`
- `0x180002630`
- `0x18002e434`
- `0x18003155c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e472`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002e472`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e4f2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002e4f2`

## pseudocode

```c
int CplTelemetry::BackgroundStickersContextMenuClicked<int &>()
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  __int64 v1; // rcx
  __int64 v2; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-50h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+40h] [rbp-40h] BYREF
  WINBOOL *p_fPending; // [rsp+60h] [rbp-20h]
  __int64 v8; // [rsp+68h] [rbp-18h]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`CplLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_180070320 = 0;
    Context = &qword_180070318;
    qword_180070318 = &wil::details::FeatureLogging::`vftable';
    byte_180070328 = 0;
    dword_18007032C = 0;
    qword_180070330 = (struct _tlgProvider_t *)&`CplLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_708c6cf2d7f939f1dd45408a9a9b6ed2_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180070318, qword_180070330, v0);
    InitOnceComplete(&`CplLogging::Instance'::`2'::wrapper, 0, &qword_180070318);
  }
  v1 = *((_QWORD *)Context + 1);
  LODWORD(v2) = *(_DWORD *)v1;
  if ( *(_DWORD *)v1 > 5u )
  {
    v2 = *(_QWORD *)(v1 + 16);
    if ( (v2 & 0x200000000000LL) != 0 )
    {
      LODWORD(v2) = 0;
      if ( (*(_QWORD *)(v1 + 24) & 0x200000000000LL) == *(_QWORD *)(v1 + 24) )
      {
        fPending = dword_180070060;
        v8 = 4;
        p_fPending = &fPending;
        LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(v1, (unsigned __int8 *)byte_18006424B, 0, 0, 3u, &v6);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002e434  mov     [rsp-8+arg_0], rbx
0x18002e439  push    rbp
0x18002e43a  mov     rbp, rsp
0x18002e43d  sub     rsp, 80h
0x18002e444  mov     rax, cs:__security_cookie
0x18002e44b  xor     rax, rsp
0x18002e44e  mov     [rbp+var_10], rax
0x18002e452  lea     r9, [rbp+Context]; lpContext
0x18002e456  mov     [rbp+Context], 0
0x18002e45e  lea     r8, [rbp+fPending]; fPending
0x18002e462  mov     [rbp+fPending], 0
0x18002e469  xor     edx, edx; dwFlags
0x18002e46b  lea     rcx, ?wrapper@?1??Instance@CplLogging@@KAPEAV2@XZ@4V?$static_lazy@VCplLogging@@@details@wil@@A; lpInitOnce
0x18002e472  call    cs:__imp_InitOnceBeginInitialize
0x18002e479  nop     dword ptr [rax+rax+00h]
0x18002e47e  test    eax, eax
0x18002e480  jz      short loc_18002E4FE
0x18002e482  cmp     [rbp+fPending], 0
0x18002e486  jz      short loc_18002E4FE
0x18002e488  lea     rbx, qword_180070318
0x18002e48f  mov     cs:qword_180070320, 0
0x18002e49a  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18002e4a1  mov     [rbp+Context], rbx
0x18002e4a5  mov     cs:qword_180070318, rax
0x18002e4ac  mov     cs:byte_180070328, 0
0x18002e4b3  mov     cs:dword_18007032C, 0
0x18002e4bd  lea     rax, ?__hInner@?1???0StaticHandle@CplLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CplLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002e4c4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_708c6cf2d7f939f1dd45408a9a9b6ed2_@@CA@XZ; void (__cdecl *)()
0x18002e4cb  mov     cs:qword_180070330, rax
0x18002e4d2  call    atexit
0x18002e4d7  mov     rdx, cs:qword_180070330; struct _tlgProvider_t *
0x18002e4de  mov     rcx, rbx; this
0x18002e4e1  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18002e4e6  mov     r8, rbx; lpContext
0x18002e4e9  lea     rcx, ?wrapper@?1??Instance@CplLogging@@KAPEAV2@XZ@4V?$static_lazy@VCplLogging@@@details@wil@@A; lpInitOnce
0x18002e4f0  xor     edx, edx; dwFlags
0x18002e4f2  call    cs:__imp_InitOnceComplete
0x18002e4f9  nop     dword ptr [rax+rax+00h]
0x18002e4fe  mov     rax, [rbp+Context]
0x18002e502  mov     rcx, [rax+8]
0x18002e506  mov     eax, [rcx]
0x18002e508  cmp     eax, 5
0x18002e50b  jbe     short loc_18002E56B
0x18002e50d  mov     rdx, [rcx+18h]
0x18002e511  mov     r8, 200000000000h
0x18002e51b  mov     rax, [rcx+10h]
0x18002e51f  test    r8, rax
0x18002e522  jz      short loc_18002E56B
0x18002e524  mov     rax, rdx
0x18002e527  and     rax, r8
0x18002e52a  cmp     rax, rdx
0x18002e52d  jnz     short loc_18002E56B
0x18002e52f  mov     eax, cs:dword_180070060
0x18002e535  lea     rdx, byte_18006424B
0x18002e53c  mov     [rbp+fPending], eax
0x18002e53f  xor     r9d, r9d
0x18002e542  lea     rax, [rbp+fPending]
0x18002e546  mov     [rbp+var_18], 4
0x18002e54e  mov     [rbp+var_20], rax
0x18002e552  xor     r8d, r8d
0x18002e555  lea     rax, [rbp+var_40]
0x18002e559  mov     [rsp+80h+var_58], rax
0x18002e55e  mov     [rsp+80h+var_60], 3
0x18002e566  call    _tlgWriteTransfer_EventWriteTransfer
0x18002e56b  mov     rcx, [rbp+var_10]
0x18002e56f  xor     rcx, rsp; StackCookie
0x18002e572  call    __security_check_cookie
0x18002e577  mov     rbx, [rsp+80h+arg_0]
0x18002e57f  add     rsp, 80h
0x18002e586  pop     rbp
0x18002e587  retn
```
