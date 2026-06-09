# FontEmbeddingTelemetry::TTLoadEmbeddedFont::StopActivity(void)

- ea: `0x180026800`
- end: `0x180026a2c`
- name: `?StopActivity@TTLoadEmbeddedFont@FontEmbeddingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontEmbeddingTelemetry::TTLoadEmbeddedFont *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800019d8`
- `0x18001c024`
- `0x18001d4e8`
- `0x180026800`
- `0x180027148`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800269cd`
- `KERNEL32!GetCurrentThreadId` at `0x1800269cd`

## pseudocode

```c
void __fastcall FontEmbeddingTelemetry::TTLoadEmbeddedFont::StopActivity(
        FontEmbeddingTelemetry::TTLoadEmbeddedFont *this)
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
        (unsigned int)byte_18002DAF9,
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
        (unsigned int)byte_18002D909,
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
0x180026800  push    rbp
0x180026802  push    rbx
0x180026803  push    rdi
0x180026804  lea     rbp, [rsp+10h]
0x180026809  sub     rsp, 130h
0x180026810  mov     rdi, [rcx+110h]
0x180026817  mov     rbx, rcx
0x18002681a  mov     eax, [rdi+48h]
0x18002681d  test    eax, eax
0x18002681f  jns     loc_1800269B9
0x180026825  add     rdi, 50h ; 'P'
0x180026829  cmp     eax, [rdi+8]
0x18002682c  jnz     loc_1800269B9
0x180026832  test    rdi, rdi
0x180026835  jz      loc_1800269B9
0x18002683b  call    ?zInternalStop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180026840  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x180026845  mov     r9, rax
0x180026848  mov     ecx, [rax]
0x18002684a  cmp     ecx, 5
0x18002684d  jbe     loc_180026A1A
0x180026853  mov     rax, [rdi+70h]
0x180026857  lea     rdx, byte_18002DAF9
0x18002685e  mov     rcx, [rdi+30h]
0x180026862  mov     [rbp+var_60], rax
0x180026866  mov     eax, [rdi+68h]
0x180026869  mov     r8, [rbx+110h]
0x180026870  mov     dword ptr [rbp+arg_10], eax
0x180026873  add     r8, 8
0x180026877  mov     rax, [rdi+60h]
0x18002687b  mov     [rbp+var_58], rax
0x18002687f  mov     rax, [rdi+58h]
0x180026883  mov     [rbp+var_50], rax
0x180026887  mov     eax, [rdi+50h]
0x18002688a  mov     [rbp+arg_18], eax
0x18002688d  mov     rax, [rdi+48h]
0x180026891  mov     [rbp+var_48], rax
0x180026895  mov     eax, [rdi+20h]
0x180026898  mov     [rbp+var_80], eax
0x18002689b  mov     rax, [rdi+18h]
0x18002689f  mov     [rbp+var_40], rax
0x1800268a3  mov     eax, [rdi]
0x1800268a5  mov     [rbp+var_7C], eax
0x1800268a8  mov     rax, [rdi+80h]
0x1800268af  mov     [rbp+var_38], rax
0x1800268b3  mov     eax, [rdi+40h]
0x1800268b6  mov     [rbp+var_78], eax
0x1800268b9  mov     rax, [rdi+38h]
0x1800268bd  mov     [rbp+var_30], rax
0x1800268c1  mov     eax, [rdi+8]
0x1800268c4  mov     [rbp+var_74], eax
0x1800268c7  lea     rax, [rbp+var_70]
0x1800268cb  mov     [rsp+140h+var_90], rax
0x1800268d3  lea     rax, [rbp+arg_0]
0x1800268d7  mov     [rsp+140h+var_98], rax
0x1800268df  lea     rax, [rbp+arg_8]
0x1800268e3  mov     [rsp+140h+var_A0], rax
0x1800268eb  lea     rax, [rbp+var_68]
0x1800268ef  mov     [rsp+140h+var_A8], rax
0x1800268f7  lea     rax, [rbp+var_60]
0x1800268fb  mov     [rsp+140h+var_B0], rax
0x180026903  lea     rax, [rbp+arg_10]
0x180026907  mov     [rsp+140h+var_B8], rax
0x18002690f  lea     rax, [rbp+var_58]
0x180026913  mov     [rsp+140h+var_C0], rax
0x18002691b  lea     rax, [rbp+var_50]
0x18002691f  mov     [rsp+140h+var_C8], rax
0x180026924  lea     rax, [rbp+arg_18]
0x180026928  mov     [rsp+140h+var_D0], rax
0x18002692d  lea     rax, [rbp+var_48]
0x180026931  mov     [rsp+140h+var_D8], rax
0x180026936  lea     rax, [rbp+var_80]
0x18002693a  mov     [rsp+140h+var_E0], rax
0x18002693f  lea     rax, [rbp+var_40]
0x180026943  mov     [rsp+140h+var_E8], rax
0x180026948  lea     rax, [rbp+var_7C]
0x18002694c  mov     [rsp+140h+var_F0], rax
0x180026951  lea     rax, [rbp+var_38]
0x180026955  mov     [rsp+140h+var_F8], rax
0x18002695a  lea     rax, [rbp+var_78]
0x18002695e  mov     [rsp+140h+var_100], rax
0x180026963  lea     rax, [rbp+var_30]
0x180026967  mov     [rsp+140h+var_108], rax
0x18002696c  lea     rax, [rbp+var_74]
0x180026970  mov     [rbp+var_70], rcx
0x180026974  mov     ecx, [rdi+44h]
0x180026977  mov     [rsp+140h+var_110], rax
0x18002697c  lea     rax, [rbp+var_28]
0x180026980  mov     [rbp+arg_0], ecx
0x180026983  mov     ecx, [rdi+10h]
0x180026986  mov     [rbp+arg_8], ecx
0x180026989  mov     rcx, [rdi+78h]
0x18002698d  mov     [rsp+140h+var_118], rax
0x180026992  lea     rax, [rbp+var_20]
0x180026996  mov     [rbp+var_68], rcx
0x18002699a  mov     rcx, r9
0x18002699d  mov     [rsp+140h+var_120], rax
0x1800269a2  mov     [rbp+var_28], 1000000h
0x1800269aa  mov     [rbp+var_20], 0
0x1800269b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800269b7  jmp     short loc_180026A1A
0x1800269b9  call    ?zInternalStop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800269be  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x1800269c3  mov     rdi, rax
0x1800269c6  mov     ecx, [rax]
0x1800269c8  cmp     ecx, 5
0x1800269cb  jbe     short loc_180026A1A
0x1800269cd  call    cs:__imp_GetCurrentThreadId
0x1800269d3  mov     r8, [rbx+110h]
0x1800269da  lea     rdx, byte_18002D909
0x1800269e1  mov     [rbp+arg_0], eax
0x1800269e4  lea     rax, [rbp+arg_0]
0x1800269e8  mov     [rsp+140h+var_110], rax
0x1800269ed  lea     rax, [rbp+arg_8]
0x1800269f1  mov     [rsp+140h+var_118], rax
0x1800269f6  lea     rax, [rbp+arg_10]
0x1800269fa  mov     ecx, [r8+48h]
0x1800269fe  add     r8, 8
0x180026a02  mov     [rbp+arg_8], ecx
0x180026a05  mov     rcx, rdi
0x180026a08  mov     [rsp+140h+var_120], rax
0x180026a0d  mov     [rbp+arg_10], 0
0x180026a15  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180026a1a  mov     rcx, rbx
0x180026a1d  add     rsp, 130h
0x180026a24  pop     rdi
0x180026a25  pop     rbx
0x180026a26  pop     rbp
0x180026a27  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
