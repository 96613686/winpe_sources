# TimeDateTraceLoggingTelemetry::OpenDateTimeCfgDlg::StartActivity(void)

- ea: `0x180008484`
- end: `0x18000853b`
- name: `?StartActivity@OpenDateTimeCfgDlg@TimeDateTraceLoggingTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::OpenDateTimeCfgDlg *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800075ec`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x180005b94`
- `0x180007908`
- `0x180008484`
- `0x1800098e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084bf`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::OpenDateTimeCfgDlg::StartActivity(
        TimeDateTraceLoggingTelemetry::OpenDateTimeCfgDlg *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = TimeDateTraceLogging::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    v7 = CurrentThreadId;
    v8 = 0;
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&unk_1800313F3,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180008484  mov     [rsp+arg_10], rbx
0x180008489  push    rdi
0x18000848a  sub     rsp, 30h
0x18000848e  mov     rbx, rcx
0x180008491  call    ?zInternalStart@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180008496  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18000849b  mov     rdi, rax
0x18000849e  mov     edx, [rax]
0x1800084a0  cmp     edx, 5
0x1800084a3  jbe     loc_180008529
0x1800084a9  mov     rdx, 200000000000h
0x1800084b3  mov     rcx, rax
0x1800084b6  call    _tlgKeywordOn
0x1800084bb  test    al, al
0x1800084bd  jz      short loc_180008529
0x1800084bf  call    cs:__imp_GetCurrentThreadId
0x1800084c5  mov     r8, [rbx+110h]
0x1800084cc  mov     [rsp+38h+arg_0], eax
0x1800084d0  mov     [rsp+38h+arg_8], 0
0x1800084d9  cmp     byte ptr [r8+4], 0
0x1800084de  jz      short loc_1800084FF
0x1800084e0  lea     r9, [r8+18h]
0x1800084e4  cmp     dword ptr [r9], 0
0x1800084e8  jnz     short loc_180008502
0x1800084ea  cmp     dword ptr [r9+4], 0
0x1800084ef  jnz     short loc_180008502
0x1800084f1  cmp     dword ptr [r9+8], 0
0x1800084f6  jnz     short loc_180008502
0x1800084f8  cmp     dword ptr [r9+0Ch], 0
0x1800084fd  jnz     short loc_180008502
0x1800084ff  xor     r9d, r9d
0x180008502  lea     rax, [rsp+38h+arg_0]
0x180008507  add     r8, 8
0x18000850b  mov     [rsp+38h+var_10], rax
0x180008510  lea     rdx, unk_1800313F3
0x180008517  lea     rax, [rsp+38h+arg_8]
0x18000851c  mov     rcx, rdi
0x18000851f  mov     [rsp+38h+var_18], rax
0x180008524  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180008529  mov     rcx, rbx
0x18000852c  mov     rbx, [rsp+38h+arg_10]
0x180008531  add     rsp, 30h
0x180008535  pop     rdi
0x180008536  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
