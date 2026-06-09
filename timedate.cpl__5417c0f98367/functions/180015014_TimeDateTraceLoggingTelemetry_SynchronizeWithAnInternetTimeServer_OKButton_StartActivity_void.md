# TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::StartActivity(void)

- ea: `0x180015014`
- end: `0x1800150cb`
- name: `?StartActivity@SynchronizeWithAnInternetTimeServer_OKButton@TimeDateTraceLoggingTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180015ca8`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x180005b94`
- `0x180007908`
- `0x1800098e4`
- `0x180015014`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001504f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001504f`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::StartActivity(
        TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton *this)
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
      (unsigned int)&unk_180031D71,
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
0x180015014  mov     [rsp+arg_10], rbx
0x180015019  push    rdi
0x18001501a  sub     rsp, 30h
0x18001501e  mov     rbx, rcx
0x180015021  call    ?zInternalStart@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180015026  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18001502b  mov     rdi, rax
0x18001502e  mov     edx, [rax]
0x180015030  cmp     edx, 5
0x180015033  jbe     loc_1800150B9
0x180015039  mov     rdx, 200000000000h
0x180015043  mov     rcx, rax
0x180015046  call    _tlgKeywordOn
0x18001504b  test    al, al
0x18001504d  jz      short loc_1800150B9
0x18001504f  call    cs:__imp_GetCurrentThreadId
0x180015055  mov     r8, [rbx+110h]
0x18001505c  mov     [rsp+38h+arg_0], eax
0x180015060  mov     [rsp+38h+arg_8], 0
0x180015069  cmp     byte ptr [r8+4], 0
0x18001506e  jz      short loc_18001508F
0x180015070  lea     r9, [r8+18h]
0x180015074  cmp     dword ptr [r9], 0
0x180015078  jnz     short loc_180015092
0x18001507a  cmp     dword ptr [r9+4], 0
0x18001507f  jnz     short loc_180015092
0x180015081  cmp     dword ptr [r9+8], 0
0x180015086  jnz     short loc_180015092
0x180015088  cmp     dword ptr [r9+0Ch], 0
0x18001508d  jnz     short loc_180015092
0x18001508f  xor     r9d, r9d
0x180015092  lea     rax, [rsp+38h+arg_0]
0x180015097  add     r8, 8
0x18001509b  mov     [rsp+38h+var_10], rax
0x1800150a0  lea     rdx, unk_180031D71
0x1800150a7  lea     rax, [rsp+38h+arg_8]
0x1800150ac  mov     rcx, rdi
0x1800150af  mov     [rsp+38h+var_18], rax
0x1800150b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800150b9  mov     rcx, rbx
0x1800150bc  mov     rbx, [rsp+38h+arg_10]
0x1800150c1  add     rsp, 30h
0x1800150c5  pop     rdi
0x1800150c6  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
