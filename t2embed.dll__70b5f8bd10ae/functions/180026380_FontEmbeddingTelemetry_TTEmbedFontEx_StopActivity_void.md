# FontEmbeddingTelemetry::TTEmbedFontEx::StopActivity(void)

- ea: `0x180026380`
- end: `0x1800265ac`
- name: `?StopActivity@TTEmbedFontEx@FontEmbeddingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontEmbeddingTelemetry::TTEmbedFontEx *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800019d8`
- `0x18001c024`
- `0x18001d4e8`
- `0x180026380`
- `0x180027148`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002654d`
- `KERNEL32!GetCurrentThreadId` at `0x18002654d`

## pseudocode

```c
void __fastcall FontEmbeddingTelemetry::TTEmbedFontEx::StopActivity(FontEmbeddingTelemetry::TTEmbedFontEx *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  int v15; // [rsp+C8h] [rbp-78h] BYREF
  int v16; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v17; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v18; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v27[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v28; // [rsp+150h] [rbp+10h] BYREF
  int v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  int v31; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = FontEmbeddingTelemetryProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = *((_QWORD *)v4 + 6);
      v19 = *((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v30) = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v31 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v13 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v14 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v6;
      v28 = v4[17];
      v29 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)byte_18002DC89,
        v7 + 8,
        (_DWORD)v5,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v17);
    }
  }
  else
  {
    wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = FontEmbeddingTelemetryProvider::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v11 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_18002DAAB,
        v11 + 8,
        v12,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180026380  push    rbp
0x180026382  push    rbx
0x180026383  push    rdi
0x180026384  lea     rbp, [rsp+10h]
0x180026389  sub     rsp, 130h
0x180026390  mov     rdi, [rcx+110h]
0x180026397  mov     rbx, rcx
0x18002639a  mov     eax, [rdi+48h]
0x18002639d  test    eax, eax
0x18002639f  jns     loc_180026539
0x1800263a5  add     rdi, 50h ; 'P'
0x1800263a9  cmp     eax, [rdi+8]
0x1800263ac  jnz     loc_180026539
0x1800263b2  test    rdi, rdi
0x1800263b5  jz      loc_180026539
0x1800263bb  call    ?zInternalStop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800263c0  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x1800263c5  mov     r9, rax
0x1800263c8  mov     ecx, [rax]
0x1800263ca  cmp     ecx, 5
0x1800263cd  jbe     loc_18002659A
0x1800263d3  mov     rax, [rdi+70h]
0x1800263d7  lea     rdx, byte_18002DC89
0x1800263de  mov     rcx, [rdi+30h]
0x1800263e2  mov     [rbp+var_60], rax
0x1800263e6  mov     eax, [rdi+68h]
0x1800263e9  mov     r8, [rbx+110h]
0x1800263f0  mov     dword ptr [rbp+arg_10], eax
0x1800263f3  add     r8, 8
0x1800263f7  mov     rax, [rdi+60h]
0x1800263fb  mov     [rbp+var_58], rax
0x1800263ff  mov     rax, [rdi+58h]
0x180026403  mov     [rbp+var_50], rax
0x180026407  mov     eax, [rdi+50h]
0x18002640a  mov     [rbp+arg_18], eax
0x18002640d  mov     rax, [rdi+48h]
0x180026411  mov     [rbp+var_48], rax
0x180026415  mov     eax, [rdi+20h]
0x180026418  mov     [rbp+var_80], eax
0x18002641b  mov     rax, [rdi+18h]
0x18002641f  mov     [rbp+var_40], rax
0x180026423  mov     eax, [rdi]
0x180026425  mov     [rbp+var_7C], eax
0x180026428  mov     rax, [rdi+80h]
0x18002642f  mov     [rbp+var_38], rax
0x180026433  mov     eax, [rdi+40h]
0x180026436  mov     [rbp+var_78], eax
0x180026439  mov     rax, [rdi+38h]
0x18002643d  mov     [rbp+var_30], rax
0x180026441  mov     eax, [rdi+8]
0x180026444  mov     [rbp+var_74], eax
0x180026447  lea     rax, [rbp+var_70]
0x18002644b  mov     [rsp+140h+var_90], rax
0x180026453  lea     rax, [rbp+arg_0]
0x180026457  mov     [rsp+140h+var_98], rax
0x18002645f  lea     rax, [rbp+arg_8]
0x180026463  mov     [rsp+140h+var_A0], rax
0x18002646b  lea     rax, [rbp+var_68]
0x18002646f  mov     [rsp+140h+var_A8], rax
0x180026477  lea     rax, [rbp+var_60]
0x18002647b  mov     [rsp+140h+var_B0], rax
0x180026483  lea     rax, [rbp+arg_10]
0x180026487  mov     [rsp+140h+var_B8], rax
0x18002648f  lea     rax, [rbp+var_58]
0x180026493  mov     [rsp+140h+var_C0], rax
0x18002649b  lea     rax, [rbp+var_50]
0x18002649f  mov     [rsp+140h+var_C8], rax
0x1800264a4  lea     rax, [rbp+arg_18]
0x1800264a8  mov     [rsp+140h+var_D0], rax
0x1800264ad  lea     rax, [rbp+var_48]
0x1800264b1  mov     [rsp+140h+var_D8], rax
0x1800264b6  lea     rax, [rbp+var_80]
0x1800264ba  mov     [rsp+140h+var_E0], rax
0x1800264bf  lea     rax, [rbp+var_40]
0x1800264c3  mov     [rsp+140h+var_E8], rax
0x1800264c8  lea     rax, [rbp+var_7C]
0x1800264cc  mov     [rsp+140h+var_F0], rax
0x1800264d1  lea     rax, [rbp+var_38]
0x1800264d5  mov     [rsp+140h+var_F8], rax
0x1800264da  lea     rax, [rbp+var_78]
0x1800264de  mov     [rsp+140h+var_100], rax
0x1800264e3  lea     rax, [rbp+var_30]
0x1800264e7  mov     [rsp+140h+var_108], rax
0x1800264ec  lea     rax, [rbp+var_74]
0x1800264f0  mov     [rbp+var_70], rcx
0x1800264f4  mov     ecx, [rdi+44h]
0x1800264f7  mov     [rsp+140h+var_110], rax
0x1800264fc  lea     rax, [rbp+var_28]
0x180026500  mov     [rbp+arg_0], ecx
0x180026503  mov     ecx, [rdi+10h]
0x180026506  mov     [rbp+arg_8], ecx
0x180026509  mov     rcx, [rdi+78h]
0x18002650d  mov     [rsp+140h+var_118], rax
0x180026512  lea     rax, [rbp+var_20]
0x180026516  mov     [rbp+var_68], rcx
0x18002651a  mov     rcx, r9
0x18002651d  mov     [rsp+140h+var_120], rax
0x180026522  mov     [rbp+var_28], 1000000h
0x18002652a  mov     [rbp+var_20], 0
0x180026532  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180026537  jmp     short loc_18002659A
0x180026539  call    ?zInternalStop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002653e  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x180026543  mov     rdi, rax
0x180026546  mov     ecx, [rax]
0x180026548  cmp     ecx, 5
0x18002654b  jbe     short loc_18002659A
0x18002654d  call    cs:__imp_GetCurrentThreadId
0x180026553  mov     r8, [rbx+110h]
0x18002655a  lea     rdx, byte_18002DAAB
0x180026561  mov     [rbp+arg_0], eax
0x180026564  lea     rax, [rbp+arg_0]
0x180026568  mov     [rsp+140h+var_110], rax
0x18002656d  lea     rax, [rbp+arg_8]
0x180026571  mov     [rsp+140h+var_118], rax
0x180026576  lea     rax, [rbp+arg_10]
0x18002657a  mov     ecx, [r8+48h]
0x18002657e  add     r8, 8
0x180026582  mov     [rbp+arg_8], ecx
0x180026585  mov     rcx, rdi
0x180026588  mov     [rsp+140h+var_120], rax
0x18002658d  mov     [rbp+arg_10], 0
0x180026595  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002659a  mov     rcx, rbx
0x18002659d  add     rsp, 130h
0x1800265a4  pop     rdi
0x1800265a5  pop     rbx
0x1800265a6  pop     rbp
0x1800265a7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
