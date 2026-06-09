# OneSettingsClientTelemetry::RefreshOneSettings::StopActivity(void)

- ea: `0x180046cd0`
- end: `0x180046ef6`
- name: `?StopActivity@RefreshOneSettings@OneSettingsClientTelemetry@@MEAAXXZ`
- size: `550`
- prototype: `void __fastcall(OneSettingsClientTelemetry::RefreshOneSettings *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800010c0`
- `0x1800013e4`
- `0x180001b6c`
- `0x18000c5a8`
- `0x18000d15c`
- `0x180012b38`
- `0x180046cd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046e96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046e96`

## pseudocode

```c
void __fastcall OneSettingsClientTelemetry::RefreshOneSettings::StopActivity(
        OneSettingsClientTelemetry::RefreshOneSettings *this)
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
        (__int64)&word_1800677AE,
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
        (__int64)&unk_1800678D8,
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
0x180046cd0  push    rbp
0x180046cd2  push    rbx
0x180046cd3  push    rdi
0x180046cd4  lea     rbp, [rsp-47h]
0x180046cd9  sub     rsp, 100h
0x180046ce0  mov     rdi, [rcx+110h]
0x180046ce7  mov     rbx, rcx
0x180046cea  mov     eax, [rdi+48h]
0x180046ced  test    eax, eax
0x180046cef  jns     loc_180046E6C
0x180046cf5  add     rdi, 50h ; 'P'
0x180046cf9  cmp     eax, [rdi+8]
0x180046cfc  jnz     loc_180046E6C
0x180046d02  test    rdi, rdi
0x180046d05  jz      loc_180046E6C
0x180046d0b  call    ?zInternalStop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180046d10  call    ?Provider@WoscLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; WoscLoggingProvider::Provider(void)
0x180046d15  mov     r9, rax
0x180046d18  mov     ecx, [rax]
0x180046d1a  cmp     ecx, 5
0x180046d1d  jbe     loc_180046EE4
0x180046d23  mov     rdx, 400000000000h
0x180046d2d  mov     rcx, rax
0x180046d30  call    _tlgKeywordOn
0x180046d35  test    al, al
0x180046d37  jz      loc_180046EE4
0x180046d3d  mov     rax, [rdi+70h]
0x180046d41  lea     rdx, word_1800677AE
0x180046d48  mov     rcx, [rdi+78h]
0x180046d4c  mov     r8, [rbx+110h]
0x180046d53  mov     [rbp+57h+var_60], rax
0x180046d57  add     r8, 8
0x180046d5b  mov     eax, [rdi+68h]
0x180046d5e  mov     [rbp+57h+arg_0], eax
0x180046d61  mov     rax, [rdi+60h]
0x180046d65  mov     [rbp+57h+var_58], rax
0x180046d69  mov     rax, [rdi+58h]
0x180046d6d  mov     [rbp+57h+var_50], rax
0x180046d71  mov     eax, [rdi+50h]
0x180046d74  mov     [rbp+57h+arg_8], eax
0x180046d77  mov     rax, [rdi+48h]
0x180046d7b  mov     [rbp+57h+var_48], rax
0x180046d7f  mov     eax, [rdi+20h]
0x180046d82  mov     dword ptr [rbp+57h+arg_10], eax
0x180046d85  mov     rax, [rdi+18h]
0x180046d89  mov     [rbp+57h+var_40], rax
0x180046d8d  mov     eax, [rdi]
0x180046d8f  mov     [rbp+57h+arg_18], eax
0x180046d92  mov     rax, [rdi+80h]
0x180046d99  mov     [rbp+57h+var_38], rax
0x180046d9d  mov     eax, [rdi+40h]
0x180046da0  mov     [rbp+57h+var_70], eax
0x180046da3  mov     rax, [rdi+38h]
0x180046da7  mov     [rbp+57h+var_30], rax
0x180046dab  mov     eax, [rdi+8]
0x180046dae  mov     [rbp+57h+var_6C], eax
0x180046db1  mov     eax, 80000000h
0x180046db6  mov     [rbp+57h+var_20], rax
0x180046dba  lea     rax, [rbp+57h+var_68]
0x180046dbe  mov     [rsp+110h+var_78], rax
0x180046dc6  lea     rax, [rbp+57h+var_60]
0x180046dca  mov     [rsp+110h+var_80], rax
0x180046dd2  lea     rax, [rbp+57h+arg_0]
0x180046dd6  mov     [rsp+110h+var_88], rax
0x180046dde  lea     rax, [rbp+57h+var_58]
0x180046de2  mov     [rsp+110h+var_90], rax
0x180046dea  lea     rax, [rbp+57h+var_50]
0x180046dee  mov     [rsp+110h+var_98], rax
0x180046df3  lea     rax, [rbp+57h+arg_8]
0x180046df7  mov     [rsp+110h+var_A0], rax
0x180046dfc  lea     rax, [rbp+57h+var_48]
0x180046e00  mov     [rsp+110h+var_A8], rax
0x180046e05  lea     rax, [rbp+57h+arg_10]
0x180046e09  mov     [rsp+110h+var_B0], rax
0x180046e0e  lea     rax, [rbp+57h+var_40]
0x180046e12  mov     [rsp+110h+var_B8], rax
0x180046e17  lea     rax, [rbp+57h+arg_18]
0x180046e1b  mov     [rsp+110h+var_C0], rax
0x180046e20  lea     rax, [rbp+57h+var_38]
0x180046e24  mov     [rsp+110h+var_C8], rax
0x180046e29  lea     rax, [rbp+57h+var_70]
0x180046e2d  mov     [rsp+110h+var_D0], rax
0x180046e32  lea     rax, [rbp+57h+var_30]
0x180046e36  mov     [rsp+110h+var_D8], rax
0x180046e3b  lea     rax, [rbp+57h+var_6C]
0x180046e3f  mov     [rsp+110h+var_E0], rax
0x180046e44  lea     rax, [rbp+57h+var_28]
0x180046e48  mov     [rsp+110h+var_E8], rax
0x180046e4d  lea     rax, [rbp+57h+var_20]
0x180046e51  mov     [rbp+57h+var_68], rcx
0x180046e55  mov     rcx, r9
0x180046e58  mov     [rsp+110h+var_F0], rax
0x180046e5d  mov     [rbp+57h+var_28], 1000000h
0x180046e65  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180046e6a  jmp     short loc_180046EE4
0x180046e6c  call    ?zInternalStop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180046e71  call    ?Provider@WoscLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; WoscLoggingProvider::Provider(void)
0x180046e76  mov     rdi, rax
0x180046e79  mov     ecx, [rax]
0x180046e7b  cmp     ecx, 5
0x180046e7e  jbe     short loc_180046EE4
0x180046e80  mov     rdx, 400000000000h
0x180046e8a  mov     rcx, rax
0x180046e8d  call    _tlgKeywordOn
0x180046e92  test    al, al
0x180046e94  jz      short loc_180046EE4
0x180046e96  call    cs:__imp_GetCurrentThreadId
0x180046e9c  mov     r8, [rbx+110h]
0x180046ea3  lea     rdx, unk_1800678D8
0x180046eaa  mov     [rbp+57h+arg_0], eax
0x180046ead  mov     rcx, rdi
0x180046eb0  mov     eax, [r8+48h]
0x180046eb4  add     r8, 8
0x180046eb8  mov     [rbp+57h+arg_8], eax
0x180046ebb  mov     eax, 80000000h
0x180046ec0  mov     [rbp+57h+arg_10], rax
0x180046ec4  lea     rax, [rbp+57h+arg_0]
0x180046ec8  mov     [rsp+110h+var_E0], rax
0x180046ecd  lea     rax, [rbp+57h+arg_8]
0x180046ed1  mov     [rsp+110h+var_E8], rax
0x180046ed6  lea     rax, [rbp+57h+arg_10]
0x180046eda  mov     [rsp+110h+var_F0], rax
0x180046edf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046ee4  mov     rcx, rbx
0x180046ee7  add     rsp, 100h
0x180046eee  pop     rdi
0x180046eef  pop     rbx
0x180046ef0  pop     rbp
0x180046ef1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
