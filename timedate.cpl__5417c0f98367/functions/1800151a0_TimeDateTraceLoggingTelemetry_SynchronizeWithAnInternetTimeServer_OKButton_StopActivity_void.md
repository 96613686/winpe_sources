# TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::StopActivity(void)

- ea: `0x1800151a0`
- end: `0x1800153c4`
- name: `?StopActivity@SynchronizeWithAnInternetTimeServer_OKButton@TimeDateTraceLoggingTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton *__hidden this)`
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
- `0x1800151a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015365`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015365`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::StopActivity(
        TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton *this)
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
        (unsigned int)&unk_180031E42,
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
        (unsigned int)&unk_180031DD5,
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
0x1800151a0  push    rbp
0x1800151a2  push    rbx
0x1800151a3  push    rdi
0x1800151a4  lea     rbp, [rsp-47h]
0x1800151a9  sub     rsp, 100h
0x1800151b0  mov     rdi, [rcx+110h]
0x1800151b7  mov     rbx, rcx
0x1800151ba  mov     eax, [rdi+48h]
0x1800151bd  test    eax, eax
0x1800151bf  jns     loc_18001533B
0x1800151c5  add     rdi, 50h ; 'P'
0x1800151c9  cmp     eax, [rdi+8]
0x1800151cc  jnz     loc_18001533B
0x1800151d2  test    rdi, rdi
0x1800151d5  jz      loc_18001533B
0x1800151db  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800151e0  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x1800151e5  mov     r9, rax
0x1800151e8  mov     ecx, [rax]
0x1800151ea  cmp     ecx, 5
0x1800151ed  jbe     loc_1800153B2
0x1800151f3  mov     rdx, 200000000000h
0x1800151fd  mov     rcx, rax
0x180015200  call    _tlgKeywordOn
0x180015205  test    al, al
0x180015207  jz      loc_1800153B2
0x18001520d  mov     rax, [rdi+70h]
0x180015211  lea     rdx, unk_180031E42
0x180015218  mov     rcx, [rdi+78h]
0x18001521c  mov     r8, [rbx+110h]
0x180015223  mov     [rbp+57h+var_60], rax
0x180015227  add     r8, 8
0x18001522b  mov     eax, [rdi+68h]
0x18001522e  mov     [rbp+57h+arg_0], eax
0x180015231  mov     rax, [rdi+60h]
0x180015235  mov     [rbp+57h+var_58], rax
0x180015239  mov     rax, [rdi+58h]
0x18001523d  mov     [rbp+57h+var_50], rax
0x180015241  mov     eax, [rdi+50h]
0x180015244  mov     [rbp+57h+arg_8], eax
0x180015247  mov     rax, [rdi+48h]
0x18001524b  mov     [rbp+57h+var_48], rax
0x18001524f  mov     eax, [rdi+20h]
0x180015252  mov     dword ptr [rbp+57h+arg_10], eax
0x180015255  mov     rax, [rdi+18h]
0x180015259  mov     [rbp+57h+var_40], rax
0x18001525d  mov     eax, [rdi]
0x18001525f  mov     [rbp+57h+arg_18], eax
0x180015262  mov     rax, [rdi+80h]
0x180015269  mov     [rbp+57h+var_38], rax
0x18001526d  mov     eax, [rdi+40h]
0x180015270  mov     [rbp+57h+var_70], eax
0x180015273  mov     rax, [rdi+38h]
0x180015277  mov     [rbp+57h+var_30], rax
0x18001527b  mov     eax, [rdi+8]
0x18001527e  mov     [rbp+57h+var_6C], eax
0x180015281  lea     rax, [rbp+57h+var_68]
0x180015285  mov     [rsp+110h+var_78], rax
0x18001528d  lea     rax, [rbp+57h+var_60]
0x180015291  mov     [rsp+110h+var_80], rax
0x180015299  lea     rax, [rbp+57h+arg_0]
0x18001529d  mov     [rsp+110h+var_88], rax
0x1800152a5  lea     rax, [rbp+57h+var_58]
0x1800152a9  mov     [rsp+110h+var_90], rax
0x1800152b1  lea     rax, [rbp+57h+var_50]
0x1800152b5  mov     [rsp+110h+var_98], rax
0x1800152ba  lea     rax, [rbp+57h+arg_8]
0x1800152be  mov     [rsp+110h+var_A0], rax
0x1800152c3  lea     rax, [rbp+57h+var_48]
0x1800152c7  mov     [rsp+110h+var_A8], rax
0x1800152cc  lea     rax, [rbp+57h+arg_10]
0x1800152d0  mov     [rsp+110h+var_B0], rax
0x1800152d5  lea     rax, [rbp+57h+var_40]
0x1800152d9  mov     [rsp+110h+var_B8], rax
0x1800152de  lea     rax, [rbp+57h+arg_18]
0x1800152e2  mov     [rsp+110h+var_C0], rax
0x1800152e7  lea     rax, [rbp+57h+var_38]
0x1800152eb  mov     [rsp+110h+var_C8], rax
0x1800152f0  lea     rax, [rbp+57h+var_70]
0x1800152f4  mov     [rsp+110h+var_D0], rax
0x1800152f9  lea     rax, [rbp+57h+var_30]
0x1800152fd  mov     [rsp+110h+var_D8], rax
0x180015302  lea     rax, [rbp+57h+var_6C]
0x180015306  mov     [rsp+110h+var_E0], rax
0x18001530b  lea     rax, [rbp+57h+var_28]
0x18001530f  mov     [rsp+110h+var_E8], rax
0x180015314  lea     rax, [rbp+57h+var_20]
0x180015318  mov     [rbp+57h+var_68], rcx
0x18001531c  mov     rcx, r9
0x18001531f  mov     [rsp+110h+var_F0], rax
0x180015324  mov     [rbp+57h+var_28], 1000000h
0x18001532c  mov     [rbp+57h+var_20], 0
0x180015334  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180015339  jmp     short loc_1800153B2
0x18001533b  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015340  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x180015345  mov     rdi, rax
0x180015348  mov     ecx, [rax]
0x18001534a  cmp     ecx, 5
0x18001534d  jbe     short loc_1800153B2
0x18001534f  mov     rdx, 200000000000h
0x180015359  mov     rcx, rax
0x18001535c  call    _tlgKeywordOn
0x180015361  test    al, al
0x180015363  jz      short loc_1800153B2
0x180015365  call    cs:__imp_GetCurrentThreadId
0x18001536b  mov     r8, [rbx+110h]
0x180015372  lea     rdx, unk_180031DD5
0x180015379  mov     [rbp+57h+arg_0], eax
0x18001537c  mov     rcx, rdi
0x18001537f  mov     eax, [r8+48h]
0x180015383  add     r8, 8
0x180015387  mov     [rbp+57h+arg_8], eax
0x18001538a  lea     rax, [rbp+57h+arg_0]
0x18001538e  mov     [rsp+110h+var_E0], rax
0x180015393  lea     rax, [rbp+57h+arg_8]
0x180015397  mov     [rsp+110h+var_E8], rax
0x18001539c  lea     rax, [rbp+57h+arg_10]
0x1800153a0  mov     [rsp+110h+var_F0], rax
0x1800153a5  mov     [rbp+57h+arg_10], 0
0x1800153ad  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800153b2  mov     rcx, rbx
0x1800153b5  add     rsp, 100h
0x1800153bc  pop     rdi
0x1800153bd  pop     rbx
0x1800153be  pop     rbp
0x1800153bf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
