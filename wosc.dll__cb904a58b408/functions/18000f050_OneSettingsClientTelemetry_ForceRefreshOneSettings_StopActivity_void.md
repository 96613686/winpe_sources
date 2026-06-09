# OneSettingsClientTelemetry::ForceRefreshOneSettings::StopActivity(void)

- ea: `0x18000f050`
- end: `0x18000f276`
- name: `?StopActivity@ForceRefreshOneSettings@OneSettingsClientTelemetry@@MEAAXXZ`
- size: `550`
- prototype: `void __fastcall(OneSettingsClientTelemetry::ForceRefreshOneSettings *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800010c0`
- `0x1800013e4`
- `0x180001b6c`
- `0x18000c5a8`
- `0x18000d15c`
- `0x18000f050`
- `0x180012b38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f216`

## pseudocode

```c
void __fastcall OneSettingsClientTelemetry::ForceRefreshOneSettings::StopActivity(
        OneSettingsClientTelemetry::ForceRefreshOneSettings *this)
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
        (__int64)byte_180066969,
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
        (__int64)&unk_180066A98,
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
0x18000f050  push    rbp
0x18000f052  push    rbx
0x18000f053  push    rdi
0x18000f054  lea     rbp, [rsp-47h]
0x18000f059  sub     rsp, 100h
0x18000f060  mov     rdi, [rcx+110h]
0x18000f067  mov     rbx, rcx
0x18000f06a  mov     eax, [rdi+48h]
0x18000f06d  test    eax, eax
0x18000f06f  jns     loc_18000F1EC
0x18000f075  add     rdi, 50h ; 'P'
0x18000f079  cmp     eax, [rdi+8]
0x18000f07c  jnz     loc_18000F1EC
0x18000f082  test    rdi, rdi
0x18000f085  jz      loc_18000F1EC
0x18000f08b  call    ?zInternalStop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f090  call    ?Provider@WoscLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; WoscLoggingProvider::Provider(void)
0x18000f095  mov     r9, rax
0x18000f098  mov     ecx, [rax]
0x18000f09a  cmp     ecx, 5
0x18000f09d  jbe     loc_18000F264
0x18000f0a3  mov     rdx, 400000000000h
0x18000f0ad  mov     rcx, rax
0x18000f0b0  call    _tlgKeywordOn
0x18000f0b5  test    al, al
0x18000f0b7  jz      loc_18000F264
0x18000f0bd  mov     rax, [rdi+70h]
0x18000f0c1  lea     rdx, byte_180066969
0x18000f0c8  mov     rcx, [rdi+78h]
0x18000f0cc  mov     r8, [rbx+110h]
0x18000f0d3  mov     [rbp+57h+var_60], rax
0x18000f0d7  add     r8, 8
0x18000f0db  mov     eax, [rdi+68h]
0x18000f0de  mov     [rbp+57h+arg_0], eax
0x18000f0e1  mov     rax, [rdi+60h]
0x18000f0e5  mov     [rbp+57h+var_58], rax
0x18000f0e9  mov     rax, [rdi+58h]
0x18000f0ed  mov     [rbp+57h+var_50], rax
0x18000f0f1  mov     eax, [rdi+50h]
0x18000f0f4  mov     [rbp+57h+arg_8], eax
0x18000f0f7  mov     rax, [rdi+48h]
0x18000f0fb  mov     [rbp+57h+var_48], rax
0x18000f0ff  mov     eax, [rdi+20h]
0x18000f102  mov     dword ptr [rbp+57h+arg_10], eax
0x18000f105  mov     rax, [rdi+18h]
0x18000f109  mov     [rbp+57h+var_40], rax
0x18000f10d  mov     eax, [rdi]
0x18000f10f  mov     [rbp+57h+arg_18], eax
0x18000f112  mov     rax, [rdi+80h]
0x18000f119  mov     [rbp+57h+var_38], rax
0x18000f11d  mov     eax, [rdi+40h]
0x18000f120  mov     [rbp+57h+var_70], eax
0x18000f123  mov     rax, [rdi+38h]
0x18000f127  mov     [rbp+57h+var_30], rax
0x18000f12b  mov     eax, [rdi+8]
0x18000f12e  mov     [rbp+57h+var_6C], eax
0x18000f131  mov     eax, 80000000h
0x18000f136  mov     [rbp+57h+var_20], rax
0x18000f13a  lea     rax, [rbp+57h+var_68]
0x18000f13e  mov     [rsp+110h+var_78], rax
0x18000f146  lea     rax, [rbp+57h+var_60]
0x18000f14a  mov     [rsp+110h+var_80], rax
0x18000f152  lea     rax, [rbp+57h+arg_0]
0x18000f156  mov     [rsp+110h+var_88], rax
0x18000f15e  lea     rax, [rbp+57h+var_58]
0x18000f162  mov     [rsp+110h+var_90], rax
0x18000f16a  lea     rax, [rbp+57h+var_50]
0x18000f16e  mov     [rsp+110h+var_98], rax
0x18000f173  lea     rax, [rbp+57h+arg_8]
0x18000f177  mov     [rsp+110h+var_A0], rax
0x18000f17c  lea     rax, [rbp+57h+var_48]
0x18000f180  mov     [rsp+110h+var_A8], rax
0x18000f185  lea     rax, [rbp+57h+arg_10]
0x18000f189  mov     [rsp+110h+var_B0], rax
0x18000f18e  lea     rax, [rbp+57h+var_40]
0x18000f192  mov     [rsp+110h+var_B8], rax
0x18000f197  lea     rax, [rbp+57h+arg_18]
0x18000f19b  mov     [rsp+110h+var_C0], rax
0x18000f1a0  lea     rax, [rbp+57h+var_38]
0x18000f1a4  mov     [rsp+110h+var_C8], rax
0x18000f1a9  lea     rax, [rbp+57h+var_70]
0x18000f1ad  mov     [rsp+110h+var_D0], rax
0x18000f1b2  lea     rax, [rbp+57h+var_30]
0x18000f1b6  mov     [rsp+110h+var_D8], rax
0x18000f1bb  lea     rax, [rbp+57h+var_6C]
0x18000f1bf  mov     [rsp+110h+var_E0], rax
0x18000f1c4  lea     rax, [rbp+57h+var_28]
0x18000f1c8  mov     [rsp+110h+var_E8], rax
0x18000f1cd  lea     rax, [rbp+57h+var_20]
0x18000f1d1  mov     [rbp+57h+var_68], rcx
0x18000f1d5  mov     rcx, r9
0x18000f1d8  mov     [rsp+110h+var_F0], rax
0x18000f1dd  mov     [rbp+57h+var_28], 1000000h
0x18000f1e5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000f1ea  jmp     short loc_18000F264
0x18000f1ec  call    ?zInternalStop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f1f1  call    ?Provider@WoscLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; WoscLoggingProvider::Provider(void)
0x18000f1f6  mov     rdi, rax
0x18000f1f9  mov     ecx, [rax]
0x18000f1fb  cmp     ecx, 5
0x18000f1fe  jbe     short loc_18000F264
0x18000f200  mov     rdx, 400000000000h
0x18000f20a  mov     rcx, rax
0x18000f20d  call    _tlgKeywordOn
0x18000f212  test    al, al
0x18000f214  jz      short loc_18000F264
0x18000f216  call    cs:__imp_GetCurrentThreadId
0x18000f21c  mov     r8, [rbx+110h]
0x18000f223  lea     rdx, unk_180066A98
0x18000f22a  mov     [rbp+57h+arg_0], eax
0x18000f22d  mov     rcx, rdi
0x18000f230  mov     eax, [r8+48h]
0x18000f234  add     r8, 8
0x18000f238  mov     [rbp+57h+arg_8], eax
0x18000f23b  mov     eax, 80000000h
0x18000f240  mov     [rbp+57h+arg_10], rax
0x18000f244  lea     rax, [rbp+57h+arg_0]
0x18000f248  mov     [rsp+110h+var_E0], rax
0x18000f24d  lea     rax, [rbp+57h+arg_8]
0x18000f251  mov     [rsp+110h+var_E8], rax
0x18000f256  lea     rax, [rbp+57h+arg_10]
0x18000f25a  mov     [rsp+110h+var_F0], rax
0x18000f25f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f264  mov     rcx, rbx
0x18000f267  add     rsp, 100h
0x18000f26e  pop     rdi
0x18000f26f  pop     rbx
0x18000f270  pop     rbp
0x18000f271  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
