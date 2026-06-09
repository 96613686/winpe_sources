# TimeDateTraceLoggingTelemetry::ChangeDateAndTime::StopActivity(void)

- ea: `0x18000c7c0`
- end: `0x18000c9e4`
- name: `?StopActivity@ChangeDateAndTime@TimeDateTraceLoggingTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::ChangeDateAndTime *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x1800067f4`
- `0x180007908`
- `0x180009954`
- `0x18000c7c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c985`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::ChangeDateAndTime::StopActivity(
        TimeDateTraceLoggingTelemetry::ChangeDateAndTime *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = TimeDateTraceLogging::Provider();
    v8 = v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)&unk_180031A69,
        v10 + 8,
        (_DWORD)v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = TimeDateTraceLogging::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&unk_180031A17,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x18000c7c0  push    rbp
0x18000c7c2  push    rbx
0x18000c7c3  push    rdi
0x18000c7c4  lea     rbp, [rsp-47h]
0x18000c7c9  sub     rsp, 100h
0x18000c7d0  mov     rdi, [rcx+110h]
0x18000c7d7  mov     rbx, rcx
0x18000c7da  mov     eax, [rdi+48h]
0x18000c7dd  test    eax, eax
0x18000c7df  jns     loc_18000C95B
0x18000c7e5  add     rdi, 50h ; 'P'
0x18000c7e9  cmp     eax, [rdi+8]
0x18000c7ec  jnz     loc_18000C95B
0x18000c7f2  test    rdi, rdi
0x18000c7f5  jz      loc_18000C95B
0x18000c7fb  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000c800  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18000c805  mov     r9, rax
0x18000c808  mov     ecx, [rax]
0x18000c80a  cmp     ecx, 5
0x18000c80d  jbe     loc_18000C9D2
0x18000c813  mov     rdx, 200000000000h
0x18000c81d  mov     rcx, rax
0x18000c820  call    _tlgKeywordOn
0x18000c825  test    al, al
0x18000c827  jz      loc_18000C9D2
0x18000c82d  mov     rax, [rdi+70h]
0x18000c831  lea     rdx, unk_180031A69
0x18000c838  mov     rcx, [rdi+78h]
0x18000c83c  mov     r8, [rbx+110h]
0x18000c843  mov     [rbp+57h+var_60], rax
0x18000c847  add     r8, 8
0x18000c84b  mov     eax, [rdi+68h]
0x18000c84e  mov     [rbp+57h+arg_0], eax
0x18000c851  mov     rax, [rdi+60h]
0x18000c855  mov     [rbp+57h+var_58], rax
0x18000c859  mov     rax, [rdi+58h]
0x18000c85d  mov     [rbp+57h+var_50], rax
0x18000c861  mov     eax, [rdi+50h]
0x18000c864  mov     [rbp+57h+arg_8], eax
0x18000c867  mov     rax, [rdi+48h]
0x18000c86b  mov     [rbp+57h+var_48], rax
0x18000c86f  mov     eax, [rdi+20h]
0x18000c872  mov     dword ptr [rbp+57h+arg_10], eax
0x18000c875  mov     rax, [rdi+18h]
0x18000c879  mov     [rbp+57h+var_40], rax
0x18000c87d  mov     eax, [rdi]
0x18000c87f  mov     [rbp+57h+arg_18], eax
0x18000c882  mov     rax, [rdi+80h]
0x18000c889  mov     [rbp+57h+var_38], rax
0x18000c88d  mov     eax, [rdi+40h]
0x18000c890  mov     [rbp+57h+var_70], eax
0x18000c893  mov     rax, [rdi+38h]
0x18000c897  mov     [rbp+57h+var_30], rax
0x18000c89b  mov     eax, [rdi+8]
0x18000c89e  mov     [rbp+57h+var_6C], eax
0x18000c8a1  lea     rax, [rbp+57h+var_68]
0x18000c8a5  mov     [rsp+110h+var_78], rax
0x18000c8ad  lea     rax, [rbp+57h+var_60]
0x18000c8b1  mov     [rsp+110h+var_80], rax
0x18000c8b9  lea     rax, [rbp+57h+arg_0]
0x18000c8bd  mov     [rsp+110h+var_88], rax
0x18000c8c5  lea     rax, [rbp+57h+var_58]
0x18000c8c9  mov     [rsp+110h+var_90], rax
0x18000c8d1  lea     rax, [rbp+57h+var_50]
0x18000c8d5  mov     [rsp+110h+var_98], rax
0x18000c8da  lea     rax, [rbp+57h+arg_8]
0x18000c8de  mov     [rsp+110h+var_A0], rax
0x18000c8e3  lea     rax, [rbp+57h+var_48]
0x18000c8e7  mov     [rsp+110h+var_A8], rax
0x18000c8ec  lea     rax, [rbp+57h+arg_10]
0x18000c8f0  mov     [rsp+110h+var_B0], rax
0x18000c8f5  lea     rax, [rbp+57h+var_40]
0x18000c8f9  mov     [rsp+110h+var_B8], rax
0x18000c8fe  lea     rax, [rbp+57h+arg_18]
0x18000c902  mov     [rsp+110h+var_C0], rax
0x18000c907  lea     rax, [rbp+57h+var_38]
0x18000c90b  mov     [rsp+110h+var_C8], rax
0x18000c910  lea     rax, [rbp+57h+var_70]
0x18000c914  mov     [rsp+110h+var_D0], rax
0x18000c919  lea     rax, [rbp+57h+var_30]
0x18000c91d  mov     [rsp+110h+var_D8], rax
0x18000c922  lea     rax, [rbp+57h+var_6C]
0x18000c926  mov     [rsp+110h+var_E0], rax
0x18000c92b  lea     rax, [rbp+57h+var_28]
0x18000c92f  mov     [rsp+110h+var_E8], rax
0x18000c934  lea     rax, [rbp+57h+var_20]
0x18000c938  mov     [rbp+57h+var_68], rcx
0x18000c93c  mov     rcx, r9
0x18000c93f  mov     [rsp+110h+var_F0], rax
0x18000c944  mov     [rbp+57h+var_28], 1000000h
0x18000c94c  mov     [rbp+57h+var_20], 0
0x18000c954  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000c959  jmp     short loc_18000C9D2
0x18000c95b  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000c960  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18000c965  mov     rdi, rax
0x18000c968  mov     ecx, [rax]
0x18000c96a  cmp     ecx, 5
0x18000c96d  jbe     short loc_18000C9D2
0x18000c96f  mov     rdx, 200000000000h
0x18000c979  mov     rcx, rax
0x18000c97c  call    _tlgKeywordOn
0x18000c981  test    al, al
0x18000c983  jz      short loc_18000C9D2
0x18000c985  call    cs:__imp_GetCurrentThreadId
0x18000c98b  mov     r8, [rbx+110h]
0x18000c992  lea     rdx, unk_180031A17
0x18000c999  mov     [rbp+57h+arg_0], eax
0x18000c99c  mov     rcx, rdi
0x18000c99f  mov     eax, [r8+48h]
0x18000c9a3  add     r8, 8
0x18000c9a7  mov     [rbp+57h+arg_8], eax
0x18000c9aa  lea     rax, [rbp+57h+arg_0]
0x18000c9ae  mov     [rsp+110h+var_E0], rax
0x18000c9b3  lea     rax, [rbp+57h+arg_8]
0x18000c9b7  mov     [rsp+110h+var_E8], rax
0x18000c9bc  lea     rax, [rbp+57h+arg_10]
0x18000c9c0  mov     [rsp+110h+var_F0], rax
0x18000c9c5  mov     [rbp+57h+arg_10], 0
0x18000c9cd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c9d2  mov     rcx, rbx
0x18000c9d5  add     rsp, 100h
0x18000c9dc  pop     rdi
0x18000c9dd  pop     rbx
0x18000c9de  pop     rbp
0x18000c9df  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
