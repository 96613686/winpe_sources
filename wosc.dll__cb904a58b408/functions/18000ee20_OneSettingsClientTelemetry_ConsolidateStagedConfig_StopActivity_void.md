# OneSettingsClientTelemetry::ConsolidateStagedConfig::StopActivity(void)

- ea: `0x18000ee20`
- end: `0x18000f046`
- name: `?StopActivity@ConsolidateStagedConfig@OneSettingsClientTelemetry@@MEAAXXZ`
- size: `550`
- prototype: `void __fastcall(OneSettingsClientTelemetry::ConsolidateStagedConfig *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800010c0`
- `0x1800013e4`
- `0x180001b6c`
- `0x18000c5a8`
- `0x18000d15c`
- `0x18000ee20`
- `0x180012b38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efe6`

## pseudocode

```c
void __fastcall OneSettingsClientTelemetry::ConsolidateStagedConfig::StopActivity(
        OneSettingsClientTelemetry::ConsolidateStagedConfig *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WoscLoggingProvider::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v27[0] = 0x80000000LL;
      v18 = v9;
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_180066641,
        v10 + 8,
        v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = WoscLoggingProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v7) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0x80000000LL;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&unk_180066770,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x18000ee20  push    rbp
0x18000ee22  push    rbx
0x18000ee23  push    rdi
0x18000ee24  lea     rbp, [rsp-47h]
0x18000ee29  sub     rsp, 100h
0x18000ee30  mov     rdi, [rcx+110h]
0x18000ee37  mov     rbx, rcx
0x18000ee3a  mov     eax, [rdi+48h]
0x18000ee3d  test    eax, eax
0x18000ee3f  jns     loc_18000EFBC
0x18000ee45  add     rdi, 50h ; 'P'
0x18000ee49  cmp     eax, [rdi+8]
0x18000ee4c  jnz     loc_18000EFBC
0x18000ee52  test    rdi, rdi
0x18000ee55  jz      loc_18000EFBC
0x18000ee5b  call    ?zInternalStop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000ee60  call    ?Provider@WoscLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; WoscLoggingProvider::Provider(void)
0x18000ee65  mov     r9, rax
0x18000ee68  mov     ecx, [rax]
0x18000ee6a  cmp     ecx, 5
0x18000ee6d  jbe     loc_18000F034
0x18000ee73  mov     rdx, 400000000000h
0x18000ee7d  mov     rcx, rax
0x18000ee80  call    _tlgKeywordOn
0x18000ee85  test    al, al
0x18000ee87  jz      loc_18000F034
0x18000ee8d  mov     rax, [rdi+70h]
0x18000ee91  lea     rdx, byte_180066641
0x18000ee98  mov     rcx, [rdi+78h]
0x18000ee9c  mov     r8, [rbx+110h]
0x18000eea3  mov     [rbp+57h+var_60], rax
0x18000eea7  add     r8, 8
0x18000eeab  mov     eax, [rdi+68h]
0x18000eeae  mov     [rbp+57h+arg_0], eax
0x18000eeb1  mov     rax, [rdi+60h]
0x18000eeb5  mov     [rbp+57h+var_58], rax
0x18000eeb9  mov     rax, [rdi+58h]
0x18000eebd  mov     [rbp+57h+var_50], rax
0x18000eec1  mov     eax, [rdi+50h]
0x18000eec4  mov     [rbp+57h+arg_8], eax
0x18000eec7  mov     rax, [rdi+48h]
0x18000eecb  mov     [rbp+57h+var_48], rax
0x18000eecf  mov     eax, [rdi+20h]
0x18000eed2  mov     dword ptr [rbp+57h+arg_10], eax
0x18000eed5  mov     rax, [rdi+18h]
0x18000eed9  mov     [rbp+57h+var_40], rax
0x18000eedd  mov     eax, [rdi]
0x18000eedf  mov     [rbp+57h+arg_18], eax
0x18000eee2  mov     rax, [rdi+80h]
0x18000eee9  mov     [rbp+57h+var_38], rax
0x18000eeed  mov     eax, [rdi+40h]
0x18000eef0  mov     [rbp+57h+var_70], eax
0x18000eef3  mov     rax, [rdi+38h]
0x18000eef7  mov     [rbp+57h+var_30], rax
0x18000eefb  mov     eax, [rdi+8]
0x18000eefe  mov     [rbp+57h+var_6C], eax
0x18000ef01  mov     eax, 80000000h
0x18000ef06  mov     [rbp+57h+var_20], rax
0x18000ef0a  lea     rax, [rbp+57h+var_68]
0x18000ef0e  mov     [rsp+110h+var_78], rax
0x18000ef16  lea     rax, [rbp+57h+var_60]
0x18000ef1a  mov     [rsp+110h+var_80], rax
0x18000ef22  lea     rax, [rbp+57h+arg_0]
0x18000ef26  mov     [rsp+110h+var_88], rax
0x18000ef2e  lea     rax, [rbp+57h+var_58]
0x18000ef32  mov     [rsp+110h+var_90], rax
0x18000ef3a  lea     rax, [rbp+57h+var_50]
0x18000ef3e  mov     [rsp+110h+var_98], rax
0x18000ef43  lea     rax, [rbp+57h+arg_8]
0x18000ef47  mov     [rsp+110h+var_A0], rax
0x18000ef4c  lea     rax, [rbp+57h+var_48]
0x18000ef50  mov     [rsp+110h+var_A8], rax
0x18000ef55  lea     rax, [rbp+57h+arg_10]
0x18000ef59  mov     [rsp+110h+var_B0], rax
0x18000ef5e  lea     rax, [rbp+57h+var_40]
0x18000ef62  mov     [rsp+110h+var_B8], rax
0x18000ef67  lea     rax, [rbp+57h+arg_18]
0x18000ef6b  mov     [rsp+110h+var_C0], rax
0x18000ef70  lea     rax, [rbp+57h+var_38]
0x18000ef74  mov     [rsp+110h+var_C8], rax
0x18000ef79  lea     rax, [rbp+57h+var_70]
0x18000ef7d  mov     [rsp+110h+var_D0], rax
0x18000ef82  lea     rax, [rbp+57h+var_30]
0x18000ef86  mov     [rsp+110h+var_D8], rax
0x18000ef8b  lea     rax, [rbp+57h+var_6C]
0x18000ef8f  mov     [rsp+110h+var_E0], rax
0x18000ef94  lea     rax, [rbp+57h+var_28]
0x18000ef98  mov     [rsp+110h+var_E8], rax
0x18000ef9d  lea     rax, [rbp+57h+var_20]
0x18000efa1  mov     [rbp+57h+var_68], rcx
0x18000efa5  mov     rcx, r9
0x18000efa8  mov     [rsp+110h+var_F0], rax
0x18000efad  mov     [rbp+57h+var_28], 1000000h
0x18000efb5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000efba  jmp     short loc_18000F034
0x18000efbc  call    ?zInternalStop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000efc1  call    ?Provider@WoscLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; WoscLoggingProvider::Provider(void)
0x18000efc6  mov     rdi, rax
0x18000efc9  mov     ecx, [rax]
0x18000efcb  cmp     ecx, 5
0x18000efce  jbe     short loc_18000F034
0x18000efd0  mov     rdx, 400000000000h
0x18000efda  mov     rcx, rax
0x18000efdd  call    _tlgKeywordOn
0x18000efe2  test    al, al
0x18000efe4  jz      short loc_18000F034
0x18000efe6  call    cs:__imp_GetCurrentThreadId
0x18000efec  mov     r8, [rbx+110h]
0x18000eff3  lea     rdx, unk_180066770
0x18000effa  mov     [rbp+57h+arg_0], eax
0x18000effd  mov     rcx, rdi
0x18000f000  mov     eax, [r8+48h]
0x18000f004  add     r8, 8
0x18000f008  mov     [rbp+57h+arg_8], eax
0x18000f00b  mov     eax, 80000000h
0x18000f010  mov     [rbp+57h+arg_10], rax
0x18000f014  lea     rax, [rbp+57h+arg_0]
0x18000f018  mov     [rsp+110h+var_E0], rax
0x18000f01d  lea     rax, [rbp+57h+arg_8]
0x18000f021  mov     [rsp+110h+var_E8], rax
0x18000f026  lea     rax, [rbp+57h+arg_10]
0x18000f02a  mov     [rsp+110h+var_F0], rax
0x18000f02f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f034  mov     rcx, rbx
0x18000f037  add     rsp, 100h
0x18000f03e  pop     rdi
0x18000f03f  pop     rbx
0x18000f040  pop     rbp
0x18000f041  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
