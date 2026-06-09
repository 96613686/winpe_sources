# TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::StartActivity(void)

- ea: `0x1800150d4`
- end: `0x18001518b`
- name: `?StartActivity@SynchronizeWithAnInternetTimeServer_UpdateNow@TimeDateTraceLoggingTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180015ca8`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x180005b94`
- `0x180007908`
- `0x1800098e4`
- `0x1800150d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001510f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001510f`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::StartActivity(
        TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow *this)
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
      (unsigned int)&unk_180031F86,
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
0x1800150d4  mov     [rsp+arg_10], rbx
0x1800150d9  push    rdi
0x1800150da  sub     rsp, 30h
0x1800150de  mov     rbx, rcx
0x1800150e1  call    ?zInternalStart@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800150e6  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x1800150eb  mov     rdi, rax
0x1800150ee  mov     edx, [rax]
0x1800150f0  cmp     edx, 5
0x1800150f3  jbe     loc_180015179
0x1800150f9  mov     rdx, 200000000000h
0x180015103  mov     rcx, rax
0x180015106  call    _tlgKeywordOn
0x18001510b  test    al, al
0x18001510d  jz      short loc_180015179
0x18001510f  call    cs:__imp_GetCurrentThreadId
0x180015115  mov     r8, [rbx+110h]
0x18001511c  mov     [rsp+38h+arg_0], eax
0x180015120  mov     [rsp+38h+arg_8], 0
0x180015129  cmp     byte ptr [r8+4], 0
0x18001512e  jz      short loc_18001514F
0x180015130  lea     r9, [r8+18h]
0x180015134  cmp     dword ptr [r9], 0
0x180015138  jnz     short loc_180015152
0x18001513a  cmp     dword ptr [r9+4], 0
0x18001513f  jnz     short loc_180015152
0x180015141  cmp     dword ptr [r9+8], 0
0x180015146  jnz     short loc_180015152
0x180015148  cmp     dword ptr [r9+0Ch], 0
0x18001514d  jnz     short loc_180015152
0x18001514f  xor     r9d, r9d
0x180015152  lea     rax, [rsp+38h+arg_0]
0x180015157  add     r8, 8
0x18001515b  mov     [rsp+38h+var_10], rax
0x180015160  lea     rdx, unk_180031F86
0x180015167  lea     rax, [rsp+38h+arg_8]
0x18001516c  mov     rcx, rdi
0x18001516f  mov     [rsp+38h+var_18], rax
0x180015174  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180015179  mov     rcx, rbx
0x18001517c  mov     rbx, [rsp+38h+arg_10]
0x180015181  add     rsp, 30h
0x180015185  pop     rdi
0x180015186  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
