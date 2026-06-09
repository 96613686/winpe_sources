# TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::StopActivity(void)

- ea: `0x18000f9d0`
- end: `0x18000fbf4`
- name: `?StopActivity@SetAdditionalClockSettings@TimeDateTraceLoggingTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x1800067f4`
- `0x180007908`
- `0x180009954`
- `0x18000f9d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb95`

## pseudocode

```c
void __fastcall TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::StopActivity(
        TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings *this)
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
        (unsigned int)&unk_180031C3F,
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
        (unsigned int)&unk_180031BE4,
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
0x18000f9d0  push    rbp
0x18000f9d2  push    rbx
0x18000f9d3  push    rdi
0x18000f9d4  lea     rbp, [rsp-47h]
0x18000f9d9  sub     rsp, 100h
0x18000f9e0  mov     rdi, [rcx+110h]
0x18000f9e7  mov     rbx, rcx
0x18000f9ea  mov     eax, [rdi+48h]
0x18000f9ed  test    eax, eax
0x18000f9ef  jns     loc_18000FB6B
0x18000f9f5  add     rdi, 50h ; 'P'
0x18000f9f9  cmp     eax, [rdi+8]
0x18000f9fc  jnz     loc_18000FB6B
0x18000fa02  test    rdi, rdi
0x18000fa05  jz      loc_18000FB6B
0x18000fa0b  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000fa10  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18000fa15  mov     r9, rax
0x18000fa18  mov     ecx, [rax]
0x18000fa1a  cmp     ecx, 5
0x18000fa1d  jbe     loc_18000FBE2
0x18000fa23  mov     rdx, 200000000000h
0x18000fa2d  mov     rcx, rax
0x18000fa30  call    _tlgKeywordOn
0x18000fa35  test    al, al
0x18000fa37  jz      loc_18000FBE2
0x18000fa3d  mov     rax, [rdi+70h]
0x18000fa41  lea     rdx, unk_180031C3F
0x18000fa48  mov     rcx, [rdi+78h]
0x18000fa4c  mov     r8, [rbx+110h]
0x18000fa53  mov     [rbp+57h+var_60], rax
0x18000fa57  add     r8, 8
0x18000fa5b  mov     eax, [rdi+68h]
0x18000fa5e  mov     [rbp+57h+arg_0], eax
0x18000fa61  mov     rax, [rdi+60h]
0x18000fa65  mov     [rbp+57h+var_58], rax
0x18000fa69  mov     rax, [rdi+58h]
0x18000fa6d  mov     [rbp+57h+var_50], rax
0x18000fa71  mov     eax, [rdi+50h]
0x18000fa74  mov     [rbp+57h+arg_8], eax
0x18000fa77  mov     rax, [rdi+48h]
0x18000fa7b  mov     [rbp+57h+var_48], rax
0x18000fa7f  mov     eax, [rdi+20h]
0x18000fa82  mov     dword ptr [rbp+57h+arg_10], eax
0x18000fa85  mov     rax, [rdi+18h]
0x18000fa89  mov     [rbp+57h+var_40], rax
0x18000fa8d  mov     eax, [rdi]
0x18000fa8f  mov     [rbp+57h+arg_18], eax
0x18000fa92  mov     rax, [rdi+80h]
0x18000fa99  mov     [rbp+57h+var_38], rax
0x18000fa9d  mov     eax, [rdi+40h]
0x18000faa0  mov     [rbp+57h+var_70], eax
0x18000faa3  mov     rax, [rdi+38h]
0x18000faa7  mov     [rbp+57h+var_30], rax
0x18000faab  mov     eax, [rdi+8]
0x18000faae  mov     [rbp+57h+var_6C], eax
0x18000fab1  lea     rax, [rbp+57h+var_68]
0x18000fab5  mov     [rsp+110h+var_78], rax
0x18000fabd  lea     rax, [rbp+57h+var_60]
0x18000fac1  mov     [rsp+110h+var_80], rax
0x18000fac9  lea     rax, [rbp+57h+arg_0]
0x18000facd  mov     [rsp+110h+var_88], rax
0x18000fad5  lea     rax, [rbp+57h+var_58]
0x18000fad9  mov     [rsp+110h+var_90], rax
0x18000fae1  lea     rax, [rbp+57h+var_50]
0x18000fae5  mov     [rsp+110h+var_98], rax
0x18000faea  lea     rax, [rbp+57h+arg_8]
0x18000faee  mov     [rsp+110h+var_A0], rax
0x18000faf3  lea     rax, [rbp+57h+var_48]
0x18000faf7  mov     [rsp+110h+var_A8], rax
0x18000fafc  lea     rax, [rbp+57h+arg_10]
0x18000fb00  mov     [rsp+110h+var_B0], rax
0x18000fb05  lea     rax, [rbp+57h+var_40]
0x18000fb09  mov     [rsp+110h+var_B8], rax
0x18000fb0e  lea     rax, [rbp+57h+arg_18]
0x18000fb12  mov     [rsp+110h+var_C0], rax
0x18000fb17  lea     rax, [rbp+57h+var_38]
0x18000fb1b  mov     [rsp+110h+var_C8], rax
0x18000fb20  lea     rax, [rbp+57h+var_70]
0x18000fb24  mov     [rsp+110h+var_D0], rax
0x18000fb29  lea     rax, [rbp+57h+var_30]
0x18000fb2d  mov     [rsp+110h+var_D8], rax
0x18000fb32  lea     rax, [rbp+57h+var_6C]
0x18000fb36  mov     [rsp+110h+var_E0], rax
0x18000fb3b  lea     rax, [rbp+57h+var_28]
0x18000fb3f  mov     [rsp+110h+var_E8], rax
0x18000fb44  lea     rax, [rbp+57h+var_20]
0x18000fb48  mov     [rbp+57h+var_68], rcx
0x18000fb4c  mov     rcx, r9
0x18000fb4f  mov     [rsp+110h+var_F0], rax
0x18000fb54  mov     [rbp+57h+var_28], 1000000h
0x18000fb5c  mov     [rbp+57h+var_20], 0
0x18000fb64  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000fb69  jmp     short loc_18000FBE2
0x18000fb6b  call    ?zInternalStop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000fb70  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x18000fb75  mov     rdi, rax
0x18000fb78  mov     ecx, [rax]
0x18000fb7a  cmp     ecx, 5
0x18000fb7d  jbe     short loc_18000FBE2
0x18000fb7f  mov     rdx, 200000000000h
0x18000fb89  mov     rcx, rax
0x18000fb8c  call    _tlgKeywordOn
0x18000fb91  test    al, al
0x18000fb93  jz      short loc_18000FBE2
0x18000fb95  call    cs:__imp_GetCurrentThreadId
0x18000fb9b  mov     r8, [rbx+110h]
0x18000fba2  lea     rdx, unk_180031BE4
0x18000fba9  mov     [rbp+57h+arg_0], eax
0x18000fbac  mov     rcx, rdi
0x18000fbaf  mov     eax, [r8+48h]
0x18000fbb3  add     r8, 8
0x18000fbb7  mov     [rbp+57h+arg_8], eax
0x18000fbba  lea     rax, [rbp+57h+arg_0]
0x18000fbbe  mov     [rsp+110h+var_E0], rax
0x18000fbc3  lea     rax, [rbp+57h+arg_8]
0x18000fbc7  mov     [rsp+110h+var_E8], rax
0x18000fbcc  lea     rax, [rbp+57h+arg_10]
0x18000fbd0  mov     [rsp+110h+var_F0], rax
0x18000fbd5  mov     [rbp+57h+arg_10], 0
0x18000fbdd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000fbe2  mov     rcx, rbx
0x18000fbe5  add     rsp, 100h
0x18000fbec  pop     rdi
0x18000fbed  pop     rbx
0x18000fbee  pop     rbp
0x18000fbef  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
