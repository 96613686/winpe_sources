# TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::StopActivity(void)

- ea: `0x1800153d0`
- end: `0x1800155f4`
- name: `?StopActivity@SynchronizeWithAnInternetTimeServer_UpdateNow@TimeDateTraceLoggingTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x1800067f4`
- `0x180007908`
- `0x180009954`
- `0x1800153d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015595`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015595`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::StopActivity(
        TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow *this)
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
        (unsigned int)&unk_180032059,
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
        (unsigned int)&unk_180031FEB,
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
0x1800153d0  push    rbp
0x1800153d2  push    rbx
0x1800153d3  push    rdi
0x1800153d4  lea     rbp, [rsp-47h]
0x1800153d9  sub     rsp, 100h
0x1800153e0  mov     rdi, [rcx+110h]
0x1800153e7  mov     rbx, rcx
0x1800153ea  mov     eax, [rdi+48h]
0x1800153ed  test    eax, eax
0x1800153ef  jns     loc_18001556B
0x1800153f5  add     rdi, 50h ; 'P'
0x1800153f9  cmp     eax, [rdi+8]
0x1800153fc  jnz     loc_18001556B
0x180015402  test    rdi, rdi
0x180015405  jz      loc_18001556B
0x18001540b  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015410  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x180015415  mov     r9, rax
0x180015418  mov     ecx, [rax]
0x18001541a  cmp     ecx, 5
0x18001541d  jbe     loc_1800155E2
0x180015423  mov     rdx, 200000000000h
0x18001542d  mov     rcx, rax
0x180015430  call    _tlgKeywordOn
0x180015435  test    al, al
0x180015437  jz      loc_1800155E2
0x18001543d  mov     rax, [rdi+70h]
0x180015441  lea     rdx, unk_180032059
0x180015448  mov     rcx, [rdi+78h]
0x18001544c  mov     r8, [rbx+110h]
0x180015453  mov     [rbp+57h+var_60], rax
0x180015457  add     r8, 8
0x18001545b  mov     eax, [rdi+68h]
0x18001545e  mov     [rbp+57h+arg_0], eax
0x180015461  mov     rax, [rdi+60h]
0x180015465  mov     [rbp+57h+var_58], rax
0x180015469  mov     rax, [rdi+58h]
0x18001546d  mov     [rbp+57h+var_50], rax
0x180015471  mov     eax, [rdi+50h]
0x180015474  mov     [rbp+57h+arg_8], eax
0x180015477  mov     rax, [rdi+48h]
0x18001547b  mov     [rbp+57h+var_48], rax
0x18001547f  mov     eax, [rdi+20h]
0x180015482  mov     dword ptr [rbp+57h+arg_10], eax
0x180015485  mov     rax, [rdi+18h]
0x180015489  mov     [rbp+57h+var_40], rax
0x18001548d  mov     eax, [rdi]
0x18001548f  mov     [rbp+57h+arg_18], eax
0x180015492  mov     rax, [rdi+80h]
0x180015499  mov     [rbp+57h+var_38], rax
0x18001549d  mov     eax, [rdi+40h]
0x1800154a0  mov     [rbp+57h+var_70], eax
0x1800154a3  mov     rax, [rdi+38h]
0x1800154a7  mov     [rbp+57h+var_30], rax
0x1800154ab  mov     eax, [rdi+8]
0x1800154ae  mov     [rbp+57h+var_6C], eax
0x1800154b1  lea     rax, [rbp+57h+var_68]
0x1800154b5  mov     [rsp+110h+var_78], rax
0x1800154bd  lea     rax, [rbp+57h+var_60]
0x1800154c1  mov     [rsp+110h+var_80], rax
0x1800154c9  lea     rax, [rbp+57h+arg_0]
0x1800154cd  mov     [rsp+110h+var_88], rax
0x1800154d5  lea     rax, [rbp+57h+var_58]
0x1800154d9  mov     [rsp+110h+var_90], rax
0x1800154e1  lea     rax, [rbp+57h+var_50]
0x1800154e5  mov     [rsp+110h+var_98], rax
0x1800154ea  lea     rax, [rbp+57h+arg_8]
0x1800154ee  mov     [rsp+110h+var_A0], rax
0x1800154f3  lea     rax, [rbp+57h+var_48]
0x1800154f7  mov     [rsp+110h+var_A8], rax
0x1800154fc  lea     rax, [rbp+57h+arg_10]
0x180015500  mov     [rsp+110h+var_B0], rax
0x180015505  lea     rax, [rbp+57h+var_40]
0x180015509  mov     [rsp+110h+var_B8], rax
0x18001550e  lea     rax, [rbp+57h+arg_18]
0x180015512  mov     [rsp+110h+var_C0], rax
0x180015517  lea     rax, [rbp+57h+var_38]
0x18001551b  mov     [rsp+110h+var_C8], rax
0x180015520  lea     rax, [rbp+57h+var_70]
0x180015524  mov     [rsp+110h+var_D0], rax
0x180015529  lea     rax, [rbp+57h+var_30]
0x18001552d  mov     [rsp+110h+var_D8], rax
0x180015532  lea     rax, [rbp+57h+var_6C]
0x180015536  mov     [rsp+110h+var_E0], rax
0x18001553b  lea     rax, [rbp+57h+var_28]
0x18001553f  mov     [rsp+110h+var_E8], rax
0x180015544  lea     rax, [rbp+57h+var_20]
0x180015548  mov     [rbp+57h+var_68], rcx
0x18001554c  mov     rcx, r9
0x18001554f  mov     [rsp+110h+var_F0], rax
0x180015554  mov     [rbp+57h+var_28], 1000000h
0x18001555c  mov     [rbp+57h+var_20], 0
0x180015564  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180015569  jmp     short loc_1800155E2
0x18001556b  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015570  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x180015575  mov     rdi, rax
0x180015578  mov     ecx, [rax]
0x18001557a  cmp     ecx, 5
0x18001557d  jbe     short loc_1800155E2
0x18001557f  mov     rdx, 200000000000h
0x180015589  mov     rcx, rax
0x18001558c  call    _tlgKeywordOn
0x180015591  test    al, al
0x180015593  jz      short loc_1800155E2
0x180015595  call    cs:__imp_GetCurrentThreadId
0x18001559b  mov     r8, [rbx+110h]
0x1800155a2  lea     rdx, unk_180031FEB
0x1800155a9  mov     [rbp+57h+arg_0], eax
0x1800155ac  mov     rcx, rdi
0x1800155af  mov     eax, [r8+48h]
0x1800155b3  add     r8, 8
0x1800155b7  mov     [rbp+57h+arg_8], eax
0x1800155ba  lea     rax, [rbp+57h+arg_0]
0x1800155be  mov     [rsp+110h+var_E0], rax
0x1800155c3  lea     rax, [rbp+57h+arg_8]
0x1800155c7  mov     [rsp+110h+var_E8], rax
0x1800155cc  lea     rax, [rbp+57h+arg_10]
0x1800155d0  mov     [rsp+110h+var_F0], rax
0x1800155d5  mov     [rbp+57h+arg_10], 0
0x1800155dd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800155e2  mov     rcx, rbx
0x1800155e5  add     rsp, 100h
0x1800155ec  pop     rdi
0x1800155ed  pop     rbx
0x1800155ee  pop     rbp
0x1800155ef  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
