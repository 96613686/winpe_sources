# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x180046274`
- end: `0x1800464b9`
- name: `?ReportStopActivity@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180045a98`
- `0x180046964`

## callees

- `0x18000186c`
- `0x180001968`
- `0x18000205c`
- `0x180045fc8`
- `0x180046274`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046444`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046444`

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
  const WCHAR *v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  __int64 v15; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v20; // [rsp+A0h] [rbp-19h] BYREF
  int v21; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-11h] BYREF
  const WCHAR *v23; // [rsp+B0h] [rbp-9h] BYREF
  const CHAR *v24; // [rsp+B8h] [rbp-1h] BYREF
  const WCHAR *v25; // [rsp+C0h] [rbp+7h] BYREF
  const CHAR *v26; // [rsp+C8h] [rbp+Fh] BYREF
  const CHAR *v27; // [rsp+D0h] [rbp+17h] BYREF
  const WCHAR *v28; // [rsp+D8h] [rbp+1Fh] BYREF
  const CHAR *v29; // [rsp+E0h] [rbp+27h] BYREF
  const CHAR *v30; // [rsp+E8h] [rbp+2Fh] BYREF
  int v31; // [rsp+120h] [rbp+67h] BYREF
  DWORD v32; // [rsp+128h] [rbp+6Fh] BYREF
  const WCHAR *v33; // [rsp+130h] [rbp+77h] BYREF
  const CHAR *v34; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = MSAClientTraceTelemetry::Provider();
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL, v8) )
      {
        v10 = *(const WCHAR **)(v6 + 120);
        v11 = a1[34];
        v24 = *(const CHAR **)(v6 + 112);
        v32 = *(_DWORD *)(v6 + 104);
        v25 = *(const WCHAR **)(v6 + 96);
        v26 = *(const CHAR **)(v6 + 88);
        v31 = *(_DWORD *)(v6 + 80);
        v27 = *(const CHAR **)(v6 + 72);
        LODWORD(v33) = *(_DWORD *)(v6 + 32);
        v28 = *(const WCHAR **)(v6 + 24);
        LODWORD(v34) = *(_DWORD *)v6;
        v29 = *(const CHAR **)(v6 + 128);
        v20 = *(_DWORD *)(v6 + 64);
        v30 = *(const CHAR **)(v6 + 56);
        v21 = *(_DWORD *)(v6 + 8);
        v23 = v10;
        v22 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v9,
          (__int64)&word_18008584E,
          v11 + 8,
          v9,
          (__int64)&v22,
          (__int64)&v21,
          &v30,
          (__int64)&v20,
          &v29,
          (__int64)&v34,
          &v28,
          (__int64)&v33,
          &v27,
          (__int64)&v31,
          &v26,
          &v25,
          (__int64)&v32,
          &v24,
          &v23);
      }
    }
    else
    {
      v12 = MSAClientTraceTelemetry::Provider();
      v14 = (__int64)v12;
      if ( *(_DWORD *)v12 > 2u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v13) )
      {
        v15 = a1[34];
        v33 = *(const WCHAR **)(v15 + 56);
        v34 = *(const CHAR **)(v15 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v17 = a1[34];
        v32 = CurrentThreadId;
        v31 = a2;
        v22 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v14,
          (__int64)byte_180085783,
          v17 + 8,
          v18,
          (__int64)&v22,
          (__int64)&v31,
          (__int64)&v32,
          &v34,
          &v33);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x180046274  push    rbp
0x180046276  push    rbx
0x180046277  push    rsi
0x180046278  push    rdi
0x180046279  lea     rbp, [rsp-3Fh]
0x18004627e  sub     rsp, 0F8h
0x180046285  mov     esi, edx
0x180046287  mov     rbx, rcx
0x18004628a  test    edx, edx
0x18004628c  jns     loc_18004649F
0x180046292  mov     rdi, [rcx+110h]
0x180046299  mov     eax, [rdi+48h]
0x18004629c  test    eax, eax
0x18004629e  jns     loc_180046404
0x1800462a4  add     rdi, 50h ; 'P'
0x1800462a8  cmp     eax, [rdi+8]
0x1800462ab  jnz     loc_180046404
0x1800462b1  test    rdi, rdi
0x1800462b4  jz      loc_180046404
0x1800462ba  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x1800462bf  mov     r9, rax
0x1800462c2  mov     ecx, [rax]
0x1800462c4  cmp     ecx, 2
0x1800462c7  jbe     loc_18004649F
0x1800462cd  mov     rdx, 200000000000h
0x1800462d7  mov     rcx, rax
0x1800462da  call    _tlgKeywordOn
0x1800462df  test    al, al
0x1800462e1  jz      loc_18004649F
0x1800462e7  mov     rax, [rdi+70h]
0x1800462eb  lea     rdx, word_18008584E
0x1800462f2  mov     rcx, [rdi+78h]
0x1800462f6  mov     r8, [rbx+110h]
0x1800462fd  mov     [rbp+57h+var_58], rax
0x180046301  add     r8, 8
0x180046305  mov     eax, [rdi+68h]
0x180046308  mov     [rbp+57h+arg_8], eax
0x18004630b  mov     rax, [rdi+60h]
0x18004630f  mov     [rbp+57h+var_50], rax
0x180046313  mov     rax, [rdi+58h]
0x180046317  mov     [rbp+57h+var_48], rax
0x18004631b  mov     eax, [rdi+50h]
0x18004631e  mov     [rbp+57h+arg_0], eax
0x180046321  mov     rax, [rdi+48h]
0x180046325  mov     [rbp+57h+var_40], rax
0x180046329  mov     eax, [rdi+20h]
0x18004632c  mov     dword ptr [rbp+57h+arg_10], eax
0x18004632f  mov     rax, [rdi+18h]
0x180046333  mov     [rbp+57h+var_38], rax
0x180046337  mov     eax, [rdi]
0x180046339  mov     dword ptr [rbp+57h+arg_18], eax
0x18004633c  mov     rax, [rdi+80h]
0x180046343  mov     [rbp+57h+var_30], rax
0x180046347  mov     eax, [rdi+40h]
0x18004634a  mov     [rbp+57h+var_70], eax
0x18004634d  mov     rax, [rdi+38h]
0x180046351  mov     [rbp+57h+var_28], rax
0x180046355  mov     eax, [rdi+8]
0x180046358  mov     [rbp+57h+var_6C], eax
0x18004635b  lea     rax, [rbp+57h+var_60]
0x18004635f  mov     [rsp+110h+var_80], rax
0x180046367  lea     rax, [rbp+57h+var_58]
0x18004636b  mov     [rsp+110h+var_88], rax
0x180046373  lea     rax, [rbp+57h+arg_8]
0x180046377  mov     [rsp+110h+var_90], rax
0x18004637f  lea     rax, [rbp+57h+var_50]
0x180046383  mov     [rsp+110h+var_98], rax
0x180046388  lea     rax, [rbp+57h+var_48]
0x18004638c  mov     [rsp+110h+var_A0], rax
0x180046391  lea     rax, [rbp+57h+arg_0]
0x180046395  mov     [rsp+110h+var_A8], rax
0x18004639a  lea     rax, [rbp+57h+var_40]
0x18004639e  mov     [rsp+110h+var_B0], rax
0x1800463a3  lea     rax, [rbp+57h+arg_10]
0x1800463a7  mov     [rsp+110h+var_B8], rax
0x1800463ac  lea     rax, [rbp+57h+var_38]
0x1800463b0  mov     [rsp+110h+var_C0], rax
0x1800463b5  lea     rax, [rbp+57h+arg_18]
0x1800463b9  mov     [rsp+110h+var_C8], rax
0x1800463be  lea     rax, [rbp+57h+var_30]
0x1800463c2  mov     [rsp+110h+var_D0], rax
0x1800463c7  lea     rax, [rbp+57h+var_70]
0x1800463cb  mov     [rsp+110h+var_D8], rax
0x1800463d0  lea     rax, [rbp+57h+var_28]
0x1800463d4  mov     [rsp+110h+var_E0], rax
0x1800463d9  lea     rax, [rbp+57h+var_6C]
0x1800463dd  mov     [rsp+110h+var_E8], rax
0x1800463e2  lea     rax, [rbp+57h+var_68]
0x1800463e6  mov     [rbp+57h+var_60], rcx
0x1800463ea  mov     rcx, r9
0x1800463ed  mov     [rsp+110h+var_F0], rax
0x1800463f2  mov     [rbp+57h+var_68], 1000000h
0x1800463fa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800463ff  jmp     loc_18004649F
0x180046404  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180046409  mov     rdi, rax
0x18004640c  mov     ecx, [rax]
0x18004640e  cmp     ecx, 2
0x180046411  jbe     loc_18004649F
0x180046417  mov     rdx, 200000000000h
0x180046421  mov     rcx, rax
0x180046424  call    _tlgKeywordOn
0x180046429  test    al, al
0x18004642b  jz      short loc_18004649F
0x18004642d  mov     rcx, [rbx+110h]
0x180046434  mov     rax, [rcx+38h]
0x180046438  mov     [rbp+57h+arg_10], rax
0x18004643c  mov     rax, [rcx+30h]
0x180046440  mov     [rbp+57h+arg_18], rax
0x180046444  call    cs:__imp_GetCurrentThreadId
0x18004644a  mov     r8, [rbx+110h]
0x180046451  lea     rdx, byte_180085783
0x180046458  mov     [rbp+57h+arg_8], eax
0x18004645b  add     r8, 8
0x18004645f  lea     rax, [rbp+57h+arg_10]
0x180046463  mov     [rbp+57h+arg_0], esi
0x180046466  mov     [rsp+110h+var_D0], rax
0x18004646b  mov     rcx, rdi
0x18004646e  lea     rax, [rbp+57h+arg_18]
0x180046472  mov     [rbp+57h+var_68], 1000000h
0x18004647a  mov     [rsp+110h+var_D8], rax
0x18004647f  lea     rax, [rbp+57h+arg_8]
0x180046483  mov     [rsp+110h+var_E0], rax
0x180046488  lea     rax, [rbp+57h+arg_0]
0x18004648c  mov     [rsp+110h+var_E8], rax
0x180046491  lea     rax, [rbp+57h+var_68]
0x180046495  mov     [rsp+110h+var_F0], rax
0x18004649a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18004649f  mov     rax, [rbx]
0x1800464a2  mov     rcx, rbx
0x1800464a5  mov     rax, [rax+8]
0x1800464a9  add     rsp, 0F8h
0x1800464b0  pop     rdi
0x1800464b1  pop     rsi
0x1800464b2  pop     rbx
0x1800464b3  pop     rbp
0x1800464b4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
