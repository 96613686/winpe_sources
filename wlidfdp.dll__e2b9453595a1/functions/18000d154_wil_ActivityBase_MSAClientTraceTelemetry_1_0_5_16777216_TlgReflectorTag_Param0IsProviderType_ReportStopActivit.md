# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18000d154`
- end: `0x18000d399`
- name: `?ReportStopActivity@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000c978`
- `0x18000d88c`

## callees

- `0x1800017fc`
- `0x1800018f8`
- `0x180001fec`
- `0x18000cea8`
- `0x18000d154`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d324`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d324`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  int v21; // [rsp+A0h] [rbp-19h] BYREF
  int v22; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-11h] BYREF
  char *v24; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v25; // [rsp+B8h] [rbp-1h] BYREF
  char *v26; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v27; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v28; // [rsp+D0h] [rbp+17h] BYREF
  char *v29; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v30; // [rsp+E0h] [rbp+27h] BYREF
  const unsigned __int16 *v31; // [rsp+E8h] [rbp+2Fh] BYREF
  int v32; // [rsp+120h] [rbp+67h] BYREF
  DWORD v33; // [rsp+128h] [rbp+6Fh] BYREF
  char *v34; // [rsp+130h] [rbp+77h] BYREF
  const unsigned __int16 *v35; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = MSAClientTraceTelemetry::Provider((__int64)a1);
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL, v8, v7) )
      {
        v10 = *(char **)(v6 + 120);
        v11 = a1[34];
        v25 = *(const unsigned __int16 **)(v6 + 112);
        v33 = *(_DWORD *)(v6 + 104);
        v26 = *(char **)(v6 + 96);
        v27 = *(const unsigned __int16 **)(v6 + 88);
        v32 = *(_DWORD *)(v6 + 80);
        v28 = *(const unsigned __int16 **)(v6 + 72);
        LODWORD(v34) = *(_DWORD *)(v6 + 32);
        v29 = *(char **)(v6 + 24);
        LODWORD(v35) = *(_DWORD *)v6;
        v30 = *(const unsigned __int16 **)(v6 + 128);
        v21 = *(_DWORD *)(v6 + 64);
        v31 = *(const unsigned __int16 **)(v6 + 56);
        v22 = *(_DWORD *)(v6 + 8);
        v24 = v10;
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v9,
          (__int64)&word_18001B9B6,
          v11 + 8,
          v9,
          (__int64)&v23,
          (__int64)&v22,
          &v31,
          (__int64)&v21,
          &v30,
          (__int64)&v35,
          &v29,
          (__int64)&v34,
          &v28,
          (__int64)&v32,
          &v27,
          &v26,
          (__int64)&v33,
          &v25,
          &v24);
      }
    }
    else
    {
      v12 = MSAClientTraceTelemetry::Provider((__int64)a1);
      v15 = (__int64)v12;
      if ( *(_DWORD *)v12 > 2u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v13, v14) )
      {
        v16 = a1[34];
        v34 = *(char **)(v16 + 56);
        v35 = *(const unsigned __int16 **)(v16 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v18 = a1[34];
        v33 = CurrentThreadId;
        v32 = a2;
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v15,
          (__int64)byte_18001B93B,
          v18 + 8,
          v19,
          (__int64)&v23,
          (__int64)&v32,
          (__int64)&v33,
          &v35,
          &v34);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x18000d154  push    rbp
0x18000d156  push    rbx
0x18000d157  push    rsi
0x18000d158  push    rdi
0x18000d159  lea     rbp, [rsp-3Fh]
0x18000d15e  sub     rsp, 0F8h
0x18000d165  mov     esi, edx
0x18000d167  mov     rbx, rcx
0x18000d16a  test    edx, edx
0x18000d16c  jns     loc_18000D37F
0x18000d172  mov     rdi, [rcx+110h]
0x18000d179  mov     eax, [rdi+48h]
0x18000d17c  test    eax, eax
0x18000d17e  jns     loc_18000D2E4
0x18000d184  add     rdi, 50h ; 'P'
0x18000d188  cmp     eax, [rdi+8]
0x18000d18b  jnz     loc_18000D2E4
0x18000d191  test    rdi, rdi
0x18000d194  jz      loc_18000D2E4
0x18000d19a  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000d19f  mov     r9, rax
0x18000d1a2  mov     ecx, [rax]
0x18000d1a4  cmp     ecx, 2
0x18000d1a7  jbe     loc_18000D37F
0x18000d1ad  mov     rdx, 200000000000h
0x18000d1b7  mov     rcx, rax
0x18000d1ba  call    _tlgKeywordOn
0x18000d1bf  test    al, al
0x18000d1c1  jz      loc_18000D37F
0x18000d1c7  mov     rax, [rdi+70h]
0x18000d1cb  lea     rdx, word_18001B9B6
0x18000d1d2  mov     rcx, [rdi+78h]
0x18000d1d6  mov     r8, [rbx+110h]
0x18000d1dd  mov     [rbp+57h+var_58], rax
0x18000d1e1  add     r8, 8
0x18000d1e5  mov     eax, [rdi+68h]
0x18000d1e8  mov     [rbp+57h+arg_8], eax
0x18000d1eb  mov     rax, [rdi+60h]
0x18000d1ef  mov     [rbp+57h+var_50], rax
0x18000d1f3  mov     rax, [rdi+58h]
0x18000d1f7  mov     [rbp+57h+var_48], rax
0x18000d1fb  mov     eax, [rdi+50h]
0x18000d1fe  mov     [rbp+57h+arg_0], eax
0x18000d201  mov     rax, [rdi+48h]
0x18000d205  mov     [rbp+57h+var_40], rax
0x18000d209  mov     eax, [rdi+20h]
0x18000d20c  mov     dword ptr [rbp+57h+arg_10], eax
0x18000d20f  mov     rax, [rdi+18h]
0x18000d213  mov     [rbp+57h+var_38], rax
0x18000d217  mov     eax, [rdi]
0x18000d219  mov     dword ptr [rbp+57h+arg_18], eax
0x18000d21c  mov     rax, [rdi+80h]
0x18000d223  mov     [rbp+57h+var_30], rax
0x18000d227  mov     eax, [rdi+40h]
0x18000d22a  mov     [rbp+57h+var_70], eax
0x18000d22d  mov     rax, [rdi+38h]
0x18000d231  mov     [rbp+57h+var_28], rax
0x18000d235  mov     eax, [rdi+8]
0x18000d238  mov     [rbp+57h+var_6C], eax
0x18000d23b  lea     rax, [rbp+57h+var_60]
0x18000d23f  mov     [rsp+110h+var_80], rax
0x18000d247  lea     rax, [rbp+57h+var_58]
0x18000d24b  mov     [rsp+110h+var_88], rax
0x18000d253  lea     rax, [rbp+57h+arg_8]
0x18000d257  mov     [rsp+110h+var_90], rax
0x18000d25f  lea     rax, [rbp+57h+var_50]
0x18000d263  mov     [rsp+110h+var_98], rax
0x18000d268  lea     rax, [rbp+57h+var_48]
0x18000d26c  mov     [rsp+110h+var_A0], rax
0x18000d271  lea     rax, [rbp+57h+arg_0]
0x18000d275  mov     [rsp+110h+var_A8], rax
0x18000d27a  lea     rax, [rbp+57h+var_40]
0x18000d27e  mov     [rsp+110h+var_B0], rax
0x18000d283  lea     rax, [rbp+57h+arg_10]
0x18000d287  mov     [rsp+110h+var_B8], rax
0x18000d28c  lea     rax, [rbp+57h+var_38]
0x18000d290  mov     [rsp+110h+var_C0], rax
0x18000d295  lea     rax, [rbp+57h+arg_18]
0x18000d299  mov     [rsp+110h+var_C8], rax
0x18000d29e  lea     rax, [rbp+57h+var_30]
0x18000d2a2  mov     [rsp+110h+var_D0], rax
0x18000d2a7  lea     rax, [rbp+57h+var_70]
0x18000d2ab  mov     [rsp+110h+var_D8], rax
0x18000d2b0  lea     rax, [rbp+57h+var_28]
0x18000d2b4  mov     [rsp+110h+var_E0], rax
0x18000d2b9  lea     rax, [rbp+57h+var_6C]
0x18000d2bd  mov     [rsp+110h+var_E8], rax
0x18000d2c2  lea     rax, [rbp+57h+var_68]
0x18000d2c6  mov     [rbp+57h+var_60], rcx
0x18000d2ca  mov     rcx, r9
0x18000d2cd  mov     [rsp+110h+var_F0], rax
0x18000d2d2  mov     [rbp+57h+var_68], 1000000h
0x18000d2da  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000d2df  jmp     loc_18000D37F
0x18000d2e4  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000d2e9  mov     rdi, rax
0x18000d2ec  mov     ecx, [rax]
0x18000d2ee  cmp     ecx, 2
0x18000d2f1  jbe     loc_18000D37F
0x18000d2f7  mov     rdx, 200000000000h
0x18000d301  mov     rcx, rax
0x18000d304  call    _tlgKeywordOn
0x18000d309  test    al, al
0x18000d30b  jz      short loc_18000D37F
0x18000d30d  mov     rcx, [rbx+110h]
0x18000d314  mov     rax, [rcx+38h]
0x18000d318  mov     [rbp+57h+arg_10], rax
0x18000d31c  mov     rax, [rcx+30h]
0x18000d320  mov     [rbp+57h+arg_18], rax
0x18000d324  call    cs:__imp_GetCurrentThreadId
0x18000d32a  mov     r8, [rbx+110h]
0x18000d331  lea     rdx, byte_18001B93B
0x18000d338  mov     [rbp+57h+arg_8], eax
0x18000d33b  add     r8, 8
0x18000d33f  lea     rax, [rbp+57h+arg_10]
0x18000d343  mov     [rbp+57h+arg_0], esi
0x18000d346  mov     [rsp+110h+var_D0], rax
0x18000d34b  mov     rcx, rdi
0x18000d34e  lea     rax, [rbp+57h+arg_18]
0x18000d352  mov     [rbp+57h+var_68], 1000000h
0x18000d35a  mov     [rsp+110h+var_D8], rax
0x18000d35f  lea     rax, [rbp+57h+arg_8]
0x18000d363  mov     [rsp+110h+var_E0], rax
0x18000d368  lea     rax, [rbp+57h+arg_0]
0x18000d36c  mov     [rsp+110h+var_E8], rax
0x18000d371  lea     rax, [rbp+57h+var_68]
0x18000d375  mov     [rsp+110h+var_F0], rax
0x18000d37a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000d37f  mov     rax, [rbx]
0x18000d382  mov     rcx, rbx
0x18000d385  mov     rax, [rax+8]
0x18000d389  add     rsp, 0F8h
0x18000d390  pop     rdi
0x18000d391  pop     rsi
0x18000d392  pop     rbx
0x18000d393  pop     rbp
0x18000d394  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
