# FontEmbeddingTelemetry::TTEmbedFont::StopActivity(void)

- ea: `0x180026140`
- end: `0x18002636c`
- name: `?StopActivity@TTEmbedFont@FontEmbeddingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontEmbeddingTelemetry::TTEmbedFont *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800019d8`
- `0x18001c024`
- `0x18001d4e8`
- `0x180026140`
- `0x180027148`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002630d`
- `KERNEL32!GetCurrentThreadId` at `0x18002630d`

## pseudocode

```c
void __fastcall FontEmbeddingTelemetry::TTEmbedFont::StopActivity(FontEmbeddingTelemetry::TTEmbedFont *this)
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
        (unsigned int)&dword_18002D524,
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
        (unsigned int)&dword_18002D6B4,
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
0x180026140  push    rbp
0x180026142  push    rbx
0x180026143  push    rdi
0x180026144  lea     rbp, [rsp+10h]
0x180026149  sub     rsp, 130h
0x180026150  mov     rdi, [rcx+110h]
0x180026157  mov     rbx, rcx
0x18002615a  mov     eax, [rdi+48h]
0x18002615d  test    eax, eax
0x18002615f  jns     loc_1800262F9
0x180026165  add     rdi, 50h ; 'P'
0x180026169  cmp     eax, [rdi+8]
0x18002616c  jnz     loc_1800262F9
0x180026172  test    rdi, rdi
0x180026175  jz      loc_1800262F9
0x18002617b  call    ?zInternalStop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180026180  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x180026185  mov     r9, rax
0x180026188  mov     ecx, [rax]
0x18002618a  cmp     ecx, 5
0x18002618d  jbe     loc_18002635A
0x180026193  mov     rax, [rdi+70h]
0x180026197  lea     rdx, dword_18002D524
0x18002619e  mov     rcx, [rdi+30h]
0x1800261a2  mov     [rbp+var_60], rax
0x1800261a6  mov     eax, [rdi+68h]
0x1800261a9  mov     r8, [rbx+110h]
0x1800261b0  mov     dword ptr [rbp+arg_10], eax
0x1800261b3  add     r8, 8
0x1800261b7  mov     rax, [rdi+60h]
0x1800261bb  mov     [rbp+var_58], rax
0x1800261bf  mov     rax, [rdi+58h]
0x1800261c3  mov     [rbp+var_50], rax
0x1800261c7  mov     eax, [rdi+50h]
0x1800261ca  mov     [rbp+arg_18], eax
0x1800261cd  mov     rax, [rdi+48h]
0x1800261d1  mov     [rbp+var_48], rax
0x1800261d5  mov     eax, [rdi+20h]
0x1800261d8  mov     [rbp+var_80], eax
0x1800261db  mov     rax, [rdi+18h]
0x1800261df  mov     [rbp+var_40], rax
0x1800261e3  mov     eax, [rdi]
0x1800261e5  mov     [rbp+var_7C], eax
0x1800261e8  mov     rax, [rdi+80h]
0x1800261ef  mov     [rbp+var_38], rax
0x1800261f3  mov     eax, [rdi+40h]
0x1800261f6  mov     [rbp+var_78], eax
0x1800261f9  mov     rax, [rdi+38h]
0x1800261fd  mov     [rbp+var_30], rax
0x180026201  mov     eax, [rdi+8]
0x180026204  mov     [rbp+var_74], eax
0x180026207  lea     rax, [rbp+var_70]
0x18002620b  mov     [rsp+140h+var_90], rax
0x180026213  lea     rax, [rbp+arg_0]
0x180026217  mov     [rsp+140h+var_98], rax
0x18002621f  lea     rax, [rbp+arg_8]
0x180026223  mov     [rsp+140h+var_A0], rax
0x18002622b  lea     rax, [rbp+var_68]
0x18002622f  mov     [rsp+140h+var_A8], rax
0x180026237  lea     rax, [rbp+var_60]
0x18002623b  mov     [rsp+140h+var_B0], rax
0x180026243  lea     rax, [rbp+arg_10]
0x180026247  mov     [rsp+140h+var_B8], rax
0x18002624f  lea     rax, [rbp+var_58]
0x180026253  mov     [rsp+140h+var_C0], rax
0x18002625b  lea     rax, [rbp+var_50]
0x18002625f  mov     [rsp+140h+var_C8], rax
0x180026264  lea     rax, [rbp+arg_18]
0x180026268  mov     [rsp+140h+var_D0], rax
0x18002626d  lea     rax, [rbp+var_48]
0x180026271  mov     [rsp+140h+var_D8], rax
0x180026276  lea     rax, [rbp+var_80]
0x18002627a  mov     [rsp+140h+var_E0], rax
0x18002627f  lea     rax, [rbp+var_40]
0x180026283  mov     [rsp+140h+var_E8], rax
0x180026288  lea     rax, [rbp+var_7C]
0x18002628c  mov     [rsp+140h+var_F0], rax
0x180026291  lea     rax, [rbp+var_38]
0x180026295  mov     [rsp+140h+var_F8], rax
0x18002629a  lea     rax, [rbp+var_78]
0x18002629e  mov     [rsp+140h+var_100], rax
0x1800262a3  lea     rax, [rbp+var_30]
0x1800262a7  mov     [rsp+140h+var_108], rax
0x1800262ac  lea     rax, [rbp+var_74]
0x1800262b0  mov     [rbp+var_70], rcx
0x1800262b4  mov     ecx, [rdi+44h]
0x1800262b7  mov     [rsp+140h+var_110], rax
0x1800262bc  lea     rax, [rbp+var_28]
0x1800262c0  mov     [rbp+arg_0], ecx
0x1800262c3  mov     ecx, [rdi+10h]
0x1800262c6  mov     [rbp+arg_8], ecx
0x1800262c9  mov     rcx, [rdi+78h]
0x1800262cd  mov     [rsp+140h+var_118], rax
0x1800262d2  lea     rax, [rbp+var_20]
0x1800262d6  mov     [rbp+var_68], rcx
0x1800262da  mov     rcx, r9
0x1800262dd  mov     [rsp+140h+var_120], rax
0x1800262e2  mov     [rbp+var_28], 1000000h
0x1800262ea  mov     [rbp+var_20], 0
0x1800262f2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800262f7  jmp     short loc_18002635A
0x1800262f9  call    ?zInternalStop@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800262fe  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x180026303  mov     rdi, rax
0x180026306  mov     ecx, [rax]
0x180026308  cmp     ecx, 5
0x18002630b  jbe     short loc_18002635A
0x18002630d  call    cs:__imp_GetCurrentThreadId
0x180026313  mov     r8, [rbx+110h]
0x18002631a  lea     rdx, dword_18002D6B4
0x180026321  mov     [rbp+arg_0], eax
0x180026324  lea     rax, [rbp+arg_0]
0x180026328  mov     [rsp+140h+var_110], rax
0x18002632d  lea     rax, [rbp+arg_8]
0x180026331  mov     [rsp+140h+var_118], rax
0x180026336  lea     rax, [rbp+arg_10]
0x18002633a  mov     ecx, [r8+48h]
0x18002633e  add     r8, 8
0x180026342  mov     [rbp+arg_8], ecx
0x180026345  mov     rcx, rdi
0x180026348  mov     [rsp+140h+var_120], rax
0x18002634d  mov     [rbp+arg_10], 0
0x180026355  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002635a  mov     rcx, rbx
0x18002635d  add     rsp, 130h
0x180026364  pop     rdi
0x180026365  pop     rbx
0x180026366  pop     rbp
0x180026367  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
