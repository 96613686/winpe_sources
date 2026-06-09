# TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::StartActivity(void)

- ea: `0x18000f90c`
- end: `0x18000f9c3`
- name: `?StartActivity@SetAdditionalClockSettings@TimeDateTraceLoggingTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800100c4`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x180005b94`
- `0x180007908`
- `0x1800098e4`
- `0x18000f90c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f947`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f947`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::StartActivity(
        TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings *this)
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
      (unsigned int)&unk_180031B92,
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
0x18000f90c  mov     [rsp+arg_10], rbx
0x18000f911  push    rdi
0x18000f912  sub     rsp, 30h
0x18000f916  mov     rbx, rcx
0x18000f919  call    ?zInternalStart@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000f91e  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18000f923  mov     rdi, rax
0x18000f926  mov     edx, [rax]
0x18000f928  cmp     edx, 5
0x18000f92b  jbe     loc_18000F9B1
0x18000f931  mov     rdx, 200000000000h
0x18000f93b  mov     rcx, rax
0x18000f93e  call    _tlgKeywordOn
0x18000f943  test    al, al
0x18000f945  jz      short loc_18000F9B1
0x18000f947  call    cs:__imp_GetCurrentThreadId
0x18000f94d  mov     r8, [rbx+110h]
0x18000f954  mov     [rsp+38h+arg_0], eax
0x18000f958  mov     [rsp+38h+arg_8], 0
0x18000f961  cmp     byte ptr [r8+4], 0
0x18000f966  jz      short loc_18000F987
0x18000f968  lea     r9, [r8+18h]
0x18000f96c  cmp     dword ptr [r9], 0
0x18000f970  jnz     short loc_18000F98A
0x18000f972  cmp     dword ptr [r9+4], 0
0x18000f977  jnz     short loc_18000F98A
0x18000f979  cmp     dword ptr [r9+8], 0
0x18000f97e  jnz     short loc_18000F98A
0x18000f980  cmp     dword ptr [r9+0Ch], 0
0x18000f985  jnz     short loc_18000F98A
0x18000f987  xor     r9d, r9d
0x18000f98a  lea     rax, [rsp+38h+arg_0]
0x18000f98f  add     r8, 8
0x18000f993  mov     [rsp+38h+var_10], rax
0x18000f998  lea     rdx, unk_180031B92
0x18000f99f  lea     rax, [rsp+38h+arg_8]
0x18000f9a4  mov     rcx, rdi
0x18000f9a7  mov     [rsp+38h+var_18], rax
0x18000f9ac  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000f9b1  mov     rcx, rbx
0x18000f9b4  mov     rbx, [rsp+38h+arg_10]
0x18000f9b9  add     rsp, 30h
0x18000f9bd  pop     rdi
0x18000f9be  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
