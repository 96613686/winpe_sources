# TimeDateTraceLoggingTelemetry::ChangeTimeZone::StartActivity(void)

- ea: `0x18000c6f4`
- end: `0x18000c7ab`
- name: `?StartActivity@ChangeTimeZone@TimeDateTraceLoggingTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::ChangeTimeZone *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a670`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x180005b94`
- `0x180007908`
- `0x1800098e4`
- `0x18000c6f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c72f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c72f`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::ChangeTimeZone::StartActivity(
        TimeDateTraceLoggingTelemetry::ChangeTimeZone *this)
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
      (unsigned int)&unk_180031813,
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
0x18000c6f4  mov     [rsp+arg_10], rbx
0x18000c6f9  push    rdi
0x18000c6fa  sub     rsp, 30h
0x18000c6fe  mov     rbx, rcx
0x18000c701  call    ?zInternalStart@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000c706  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18000c70b  mov     rdi, rax
0x18000c70e  mov     edx, [rax]
0x18000c710  cmp     edx, 5
0x18000c713  jbe     loc_18000C799
0x18000c719  mov     rdx, 200000000000h
0x18000c723  mov     rcx, rax
0x18000c726  call    _tlgKeywordOn
0x18000c72b  test    al, al
0x18000c72d  jz      short loc_18000C799
0x18000c72f  call    cs:__imp_GetCurrentThreadId
0x18000c735  mov     r8, [rbx+110h]
0x18000c73c  mov     [rsp+38h+arg_0], eax
0x18000c740  mov     [rsp+38h+arg_8], 0
0x18000c749  cmp     byte ptr [r8+4], 0
0x18000c74e  jz      short loc_18000C76F
0x18000c750  lea     r9, [r8+18h]
0x18000c754  cmp     dword ptr [r9], 0
0x18000c758  jnz     short loc_18000C772
0x18000c75a  cmp     dword ptr [r9+4], 0
0x18000c75f  jnz     short loc_18000C772
0x18000c761  cmp     dword ptr [r9+8], 0
0x18000c766  jnz     short loc_18000C772
0x18000c768  cmp     dword ptr [r9+0Ch], 0
0x18000c76d  jnz     short loc_18000C772
0x18000c76f  xor     r9d, r9d
0x18000c772  lea     rax, [rsp+38h+arg_0]
0x18000c777  add     r8, 8
0x18000c77b  mov     [rsp+38h+var_10], rax
0x18000c780  lea     rdx, unk_180031813
0x18000c787  lea     rax, [rsp+38h+arg_8]
0x18000c78c  mov     rcx, rdi
0x18000c78f  mov     [rsp+38h+var_18], rax
0x18000c794  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000c799  mov     rcx, rbx
0x18000c79c  mov     rbx, [rsp+38h+arg_10]
0x18000c7a1  add     rsp, 30h
0x18000c7a5  pop     rdi
0x18000c7a6  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
