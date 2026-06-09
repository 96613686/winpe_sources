# TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow::StopActivity(void)

- ea: `0x18001d610`
- end: `0x18001d834`
- name: `?StopActivity@SynchronizeWithAnInternetTimeServer_SyncNow@TimeDateTraceLoggingTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow *__hidden this)`
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
- `0x18001d610`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d7d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d7d5`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow::StopActivity(
        TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_SyncNow *this)
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
        (unsigned int)&unk_18003226D,
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
        (unsigned int)&unk_180032201,
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
0x18001d610  push    rbp
0x18001d612  push    rbx
0x18001d613  push    rdi
0x18001d614  lea     rbp, [rsp-47h]
0x18001d619  sub     rsp, 100h
0x18001d620  mov     rdi, [rcx+110h]
0x18001d627  mov     rbx, rcx
0x18001d62a  mov     eax, [rdi+48h]
0x18001d62d  test    eax, eax
0x18001d62f  jns     loc_18001D7AB
0x18001d635  add     rdi, 50h ; 'P'
0x18001d639  cmp     eax, [rdi+8]
0x18001d63c  jnz     loc_18001D7AB
0x18001d642  test    rdi, rdi
0x18001d645  jz      loc_18001D7AB
0x18001d64b  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001d650  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18001d655  mov     r9, rax
0x18001d658  mov     ecx, [rax]
0x18001d65a  cmp     ecx, 5
0x18001d65d  jbe     loc_18001D822
0x18001d663  mov     rdx, 200000000000h
0x18001d66d  mov     rcx, rax
0x18001d670  call    _tlgKeywordOn
0x18001d675  test    al, al
0x18001d677  jz      loc_18001D822
0x18001d67d  mov     rax, [rdi+70h]
0x18001d681  lea     rdx, unk_18003226D
0x18001d688  mov     rcx, [rdi+78h]
0x18001d68c  mov     r8, [rbx+110h]
0x18001d693  mov     [rbp+57h+var_60], rax
0x18001d697  add     r8, 8
0x18001d69b  mov     eax, [rdi+68h]
0x18001d69e  mov     [rbp+57h+arg_0], eax
0x18001d6a1  mov     rax, [rdi+60h]
0x18001d6a5  mov     [rbp+57h+var_58], rax
0x18001d6a9  mov     rax, [rdi+58h]
0x18001d6ad  mov     [rbp+57h+var_50], rax
0x18001d6b1  mov     eax, [rdi+50h]
0x18001d6b4  mov     [rbp+57h+arg_8], eax
0x18001d6b7  mov     rax, [rdi+48h]
0x18001d6bb  mov     [rbp+57h+var_48], rax
0x18001d6bf  mov     eax, [rdi+20h]
0x18001d6c2  mov     dword ptr [rbp+57h+arg_10], eax
0x18001d6c5  mov     rax, [rdi+18h]
0x18001d6c9  mov     [rbp+57h+var_40], rax
0x18001d6cd  mov     eax, [rdi]
0x18001d6cf  mov     [rbp+57h+arg_18], eax
0x18001d6d2  mov     rax, [rdi+80h]
0x18001d6d9  mov     [rbp+57h+var_38], rax
0x18001d6dd  mov     eax, [rdi+40h]
0x18001d6e0  mov     [rbp+57h+var_70], eax
0x18001d6e3  mov     rax, [rdi+38h]
0x18001d6e7  mov     [rbp+57h+var_30], rax
0x18001d6eb  mov     eax, [rdi+8]
0x18001d6ee  mov     [rbp+57h+var_6C], eax
0x18001d6f1  lea     rax, [rbp+57h+var_68]
0x18001d6f5  mov     [rsp+110h+var_78], rax
0x18001d6fd  lea     rax, [rbp+57h+var_60]
0x18001d701  mov     [rsp+110h+var_80], rax
0x18001d709  lea     rax, [rbp+57h+arg_0]
0x18001d70d  mov     [rsp+110h+var_88], rax
0x18001d715  lea     rax, [rbp+57h+var_58]
0x18001d719  mov     [rsp+110h+var_90], rax
0x18001d721  lea     rax, [rbp+57h+var_50]
0x18001d725  mov     [rsp+110h+var_98], rax
0x18001d72a  lea     rax, [rbp+57h+arg_8]
0x18001d72e  mov     [rsp+110h+var_A0], rax
0x18001d733  lea     rax, [rbp+57h+var_48]
0x18001d737  mov     [rsp+110h+var_A8], rax
0x18001d73c  lea     rax, [rbp+57h+arg_10]
0x18001d740  mov     [rsp+110h+var_B0], rax
0x18001d745  lea     rax, [rbp+57h+var_40]
0x18001d749  mov     [rsp+110h+var_B8], rax
0x18001d74e  lea     rax, [rbp+57h+arg_18]
0x18001d752  mov     [rsp+110h+var_C0], rax
0x18001d757  lea     rax, [rbp+57h+var_38]
0x18001d75b  mov     [rsp+110h+var_C8], rax
0x18001d760  lea     rax, [rbp+57h+var_70]
0x18001d764  mov     [rsp+110h+var_D0], rax
0x18001d769  lea     rax, [rbp+57h+var_30]
0x18001d76d  mov     [rsp+110h+var_D8], rax
0x18001d772  lea     rax, [rbp+57h+var_6C]
0x18001d776  mov     [rsp+110h+var_E0], rax
0x18001d77b  lea     rax, [rbp+57h+var_28]
0x18001d77f  mov     [rsp+110h+var_E8], rax
0x18001d784  lea     rax, [rbp+57h+var_20]
0x18001d788  mov     [rbp+57h+var_68], rcx
0x18001d78c  mov     rcx, r9
0x18001d78f  mov     [rsp+110h+var_F0], rax
0x18001d794  mov     [rbp+57h+var_28], 1000000h
0x18001d79c  mov     [rbp+57h+var_20], 0
0x18001d7a4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001d7a9  jmp     short loc_18001D822
0x18001d7ab  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001d7b0  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18001d7b5  mov     rdi, rax
0x18001d7b8  mov     ecx, [rax]
0x18001d7ba  cmp     ecx, 5
0x18001d7bd  jbe     short loc_18001D822
0x18001d7bf  mov     rdx, 200000000000h
0x18001d7c9  mov     rcx, rax
0x18001d7cc  call    _tlgKeywordOn
0x18001d7d1  test    al, al
0x18001d7d3  jz      short loc_18001D822
0x18001d7d5  call    cs:__imp_GetCurrentThreadId
0x18001d7db  mov     r8, [rbx+110h]
0x18001d7e2  lea     rdx, unk_180032201
0x18001d7e9  mov     [rbp+57h+arg_0], eax
0x18001d7ec  mov     rcx, rdi
0x18001d7ef  mov     eax, [r8+48h]
0x18001d7f3  add     r8, 8
0x18001d7f7  mov     [rbp+57h+arg_8], eax
0x18001d7fa  lea     rax, [rbp+57h+arg_0]
0x18001d7fe  mov     [rsp+110h+var_E0], rax
0x18001d803  lea     rax, [rbp+57h+arg_8]
0x18001d807  mov     [rsp+110h+var_E8], rax
0x18001d80c  lea     rax, [rbp+57h+arg_10]
0x18001d810  mov     [rsp+110h+var_F0], rax
0x18001d815  mov     [rbp+57h+arg_10], 0
0x18001d81d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d822  mov     rcx, rbx
0x18001d825  add     rsp, 100h
0x18001d82c  pop     rdi
0x18001d82d  pop     rbx
0x18001d82e  pop     rbp
0x18001d82f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
