# FontEmbeddingTelemetry::TTEmbedFontFromFileA::StopActivity(void)

- ea: `0x1800265c0`
- end: `0x1800267ec`
- name: `?StopActivity@TTEmbedFontFromFileA@FontEmbeddingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontEmbeddingTelemetry::TTEmbedFontFromFileA *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800019d8`
- `0x18001c024`
- `0x18001d4e8`
- `0x1800265c0`
- `0x180027148`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002678d`
- `KERNEL32!GetCurrentThreadId` at `0x18002678d`

## pseudocode

```c
void __fastcall FontEmbeddingTelemetry::TTEmbedFontFromFileA::StopActivity(
        FontEmbeddingTelemetry::TTEmbedFontFromFileA *this)
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
        (unsigned int)&dword_18002D95C,
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
        (unsigned int)&dword_18002D3AC,
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
0x1800265c0  push    rbp
0x1800265c2  push    rbx
0x1800265c3  push    rdi
0x1800265c4  lea     rbp, [rsp+10h]
0x1800265c9  sub     rsp, 130h
0x1800265d0  mov     rdi, [rcx+110h]
0x1800265d7  mov     rbx, rcx
0x1800265da  mov     eax, [rdi+48h]
0x1800265dd  test    eax, eax
0x1800265df  jns     loc_180026779
0x1800265e5  add     rdi, 50h ; 'P'
0x1800265e9  cmp     eax, [rdi+8]
0x1800265ec  jnz     loc_180026779
0x1800265f2  test    rdi, rdi
0x1800265f5  jz      loc_180026779
0x1800265fb  call    ?zInternalStop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180026600  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x180026605  mov     r9, rax
0x180026608  mov     ecx, [rax]
0x18002660a  cmp     ecx, 5
0x18002660d  jbe     loc_1800267DA
0x180026613  mov     rax, [rdi+70h]
0x180026617  lea     rdx, dword_18002D95C
0x18002661e  mov     rcx, [rdi+30h]
0x180026622  mov     [rbp+var_60], rax
0x180026626  mov     eax, [rdi+68h]
0x180026629  mov     r8, [rbx+110h]
0x180026630  mov     dword ptr [rbp+arg_10], eax
0x180026633  add     r8, 8
0x180026637  mov     rax, [rdi+60h]
0x18002663b  mov     [rbp+var_58], rax
0x18002663f  mov     rax, [rdi+58h]
0x180026643  mov     [rbp+var_50], rax
0x180026647  mov     eax, [rdi+50h]
0x18002664a  mov     [rbp+arg_18], eax
0x18002664d  mov     rax, [rdi+48h]
0x180026651  mov     [rbp+var_48], rax
0x180026655  mov     eax, [rdi+20h]
0x180026658  mov     [rbp+var_80], eax
0x18002665b  mov     rax, [rdi+18h]
0x18002665f  mov     [rbp+var_40], rax
0x180026663  mov     eax, [rdi]
0x180026665  mov     [rbp+var_7C], eax
0x180026668  mov     rax, [rdi+80h]
0x18002666f  mov     [rbp+var_38], rax
0x180026673  mov     eax, [rdi+40h]
0x180026676  mov     [rbp+var_78], eax
0x180026679  mov     rax, [rdi+38h]
0x18002667d  mov     [rbp+var_30], rax
0x180026681  mov     eax, [rdi+8]
0x180026684  mov     [rbp+var_74], eax
0x180026687  lea     rax, [rbp+var_70]
0x18002668b  mov     [rsp+140h+var_90], rax
0x180026693  lea     rax, [rbp+arg_0]
0x180026697  mov     [rsp+140h+var_98], rax
0x18002669f  lea     rax, [rbp+arg_8]
0x1800266a3  mov     [rsp+140h+var_A0], rax
0x1800266ab  lea     rax, [rbp+var_68]
0x1800266af  mov     [rsp+140h+var_A8], rax
0x1800266b7  lea     rax, [rbp+var_60]
0x1800266bb  mov     [rsp+140h+var_B0], rax
0x1800266c3  lea     rax, [rbp+arg_10]
0x1800266c7  mov     [rsp+140h+var_B8], rax
0x1800266cf  lea     rax, [rbp+var_58]
0x1800266d3  mov     [rsp+140h+var_C0], rax
0x1800266db  lea     rax, [rbp+var_50]
0x1800266df  mov     [rsp+140h+var_C8], rax
0x1800266e4  lea     rax, [rbp+arg_18]
0x1800266e8  mov     [rsp+140h+var_D0], rax
0x1800266ed  lea     rax, [rbp+var_48]
0x1800266f1  mov     [rsp+140h+var_D8], rax
0x1800266f6  lea     rax, [rbp+var_80]
0x1800266fa  mov     [rsp+140h+var_E0], rax
0x1800266ff  lea     rax, [rbp+var_40]
0x180026703  mov     [rsp+140h+var_E8], rax
0x180026708  lea     rax, [rbp+var_7C]
0x18002670c  mov     [rsp+140h+var_F0], rax
0x180026711  lea     rax, [rbp+var_38]
0x180026715  mov     [rsp+140h+var_F8], rax
0x18002671a  lea     rax, [rbp+var_78]
0x18002671e  mov     [rsp+140h+var_100], rax
0x180026723  lea     rax, [rbp+var_30]
0x180026727  mov     [rsp+140h+var_108], rax
0x18002672c  lea     rax, [rbp+var_74]
0x180026730  mov     [rbp+var_70], rcx
0x180026734  mov     ecx, [rdi+44h]
0x180026737  mov     [rsp+140h+var_110], rax
0x18002673c  lea     rax, [rbp+var_28]
0x180026740  mov     [rbp+arg_0], ecx
0x180026743  mov     ecx, [rdi+10h]
0x180026746  mov     [rbp+arg_8], ecx
0x180026749  mov     rcx, [rdi+78h]
0x18002674d  mov     [rsp+140h+var_118], rax
0x180026752  lea     rax, [rbp+var_20]
0x180026756  mov     [rbp+var_68], rcx
0x18002675a  mov     rcx, r9
0x18002675d  mov     [rsp+140h+var_120], rax
0x180026762  mov     [rbp+var_28], 1000000h
0x18002676a  mov     [rbp+var_20], 0
0x180026772  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180026777  jmp     short loc_1800267DA
0x180026779  call    ?zInternalStop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002677e  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x180026783  mov     rdi, rax
0x180026786  mov     ecx, [rax]
0x180026788  cmp     ecx, 5
0x18002678b  jbe     short loc_1800267DA
0x18002678d  call    cs:__imp_GetCurrentThreadId
0x180026793  mov     r8, [rbx+110h]
0x18002679a  lea     rdx, dword_18002D3AC
0x1800267a1  mov     [rbp+arg_0], eax
0x1800267a4  lea     rax, [rbp+arg_0]
0x1800267a8  mov     [rsp+140h+var_110], rax
0x1800267ad  lea     rax, [rbp+arg_8]
0x1800267b1  mov     [rsp+140h+var_118], rax
0x1800267b6  lea     rax, [rbp+arg_10]
0x1800267ba  mov     ecx, [r8+48h]
0x1800267be  add     r8, 8
0x1800267c2  mov     [rbp+arg_8], ecx
0x1800267c5  mov     rcx, rdi
0x1800267c8  mov     [rsp+140h+var_120], rax
0x1800267cd  mov     [rbp+arg_10], 0
0x1800267d5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800267da  mov     rcx, rbx
0x1800267dd  add     rsp, 130h
0x1800267e4  pop     rdi
0x1800267e5  pop     rbx
0x1800267e6  pop     rbp
0x1800267e7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
