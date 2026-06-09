# CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::StopActivity(void)

- ea: `0x180017f30`
- end: `0x180018154`
- name: `?StopActivity@CoCreateInstanceAsSystem@CoCreateInstanceAsSystemTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x180007d94`
- `0x18000b9dc`
- `0x180017bd8`
- `0x180017f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800180f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800180f5`

## pseudocode

```c
void __fastcall CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::StopActivity(
        CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v20; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v21; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v22; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v25; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v29[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v30; // [rsp+120h] [rbp+67h] BYREF
  int v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  int v33; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = CoCreateInstanceAsSystemLogging::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL, v7) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v30 = v4[26];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v32) = v4[8];
      v25 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v33 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v18 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v19 = v4[2];
      v20 = v9;
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_1800251B1,
        v10 + 8,
        v8,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v19,
        &v27,
        (__int64)&v18,
        &v26,
        (__int64)&v33,
        &v25,
        (__int64)&v32,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        (__int64)&v30,
        &v21,
        &v20);
    }
  }
  else
  {
    wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = CoCreateInstanceAsSystemLogging::Provider(v11);
    v14 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v13) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v16 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)&unk_180025158,
        v16 + 8,
        v17,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180017f30  push    rbp
0x180017f32  push    rbx
0x180017f33  push    rdi
0x180017f34  lea     rbp, [rsp-47h]
0x180017f39  sub     rsp, 100h
0x180017f40  mov     rdi, [rcx+110h]
0x180017f47  mov     rbx, rcx
0x180017f4a  mov     eax, [rdi+48h]
0x180017f4d  test    eax, eax
0x180017f4f  jns     loc_1800180CB
0x180017f55  add     rdi, 50h ; 'P'
0x180017f59  cmp     eax, [rdi+8]
0x180017f5c  jnz     loc_1800180CB
0x180017f62  test    rdi, rdi
0x180017f65  jz      loc_1800180CB
0x180017f6b  call    ?zInternalStop@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180017f70  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x180017f75  mov     r9, rax
0x180017f78  mov     ecx, [rax]
0x180017f7a  cmp     ecx, 5
0x180017f7d  jbe     loc_180018142
0x180017f83  mov     rdx, 200000000000h
0x180017f8d  mov     rcx, rax
0x180017f90  call    _tlgKeywordOn
0x180017f95  test    al, al
0x180017f97  jz      loc_180018142
0x180017f9d  mov     rax, [rdi+70h]
0x180017fa1  lea     rdx, byte_1800251B1
0x180017fa8  mov     rcx, [rdi+78h]
0x180017fac  mov     r8, [rbx+110h]
0x180017fb3  mov     [rbp+57h+var_60], rax
0x180017fb7  add     r8, 8
0x180017fbb  mov     eax, [rdi+68h]
0x180017fbe  mov     [rbp+57h+arg_0], eax
0x180017fc1  mov     rax, [rdi+60h]
0x180017fc5  mov     [rbp+57h+var_58], rax
0x180017fc9  mov     rax, [rdi+58h]
0x180017fcd  mov     [rbp+57h+var_50], rax
0x180017fd1  mov     eax, [rdi+50h]
0x180017fd4  mov     [rbp+57h+arg_8], eax
0x180017fd7  mov     rax, [rdi+48h]
0x180017fdb  mov     [rbp+57h+var_48], rax
0x180017fdf  mov     eax, [rdi+20h]
0x180017fe2  mov     dword ptr [rbp+57h+arg_10], eax
0x180017fe5  mov     rax, [rdi+18h]
0x180017fe9  mov     [rbp+57h+var_40], rax
0x180017fed  mov     eax, [rdi]
0x180017fef  mov     [rbp+57h+arg_18], eax
0x180017ff2  mov     rax, [rdi+80h]
0x180017ff9  mov     [rbp+57h+var_38], rax
0x180017ffd  mov     eax, [rdi+40h]
0x180018000  mov     [rbp+57h+var_70], eax
0x180018003  mov     rax, [rdi+38h]
0x180018007  mov     [rbp+57h+var_30], rax
0x18001800b  mov     eax, [rdi+8]
0x18001800e  mov     [rbp+57h+var_6C], eax
0x180018011  lea     rax, [rbp+57h+var_68]
0x180018015  mov     [rsp+110h+var_78], rax
0x18001801d  lea     rax, [rbp+57h+var_60]
0x180018021  mov     [rsp+110h+var_80], rax
0x180018029  lea     rax, [rbp+57h+arg_0]
0x18001802d  mov     [rsp+110h+var_88], rax
0x180018035  lea     rax, [rbp+57h+var_58]
0x180018039  mov     [rsp+110h+var_90], rax
0x180018041  lea     rax, [rbp+57h+var_50]
0x180018045  mov     [rsp+110h+var_98], rax
0x18001804a  lea     rax, [rbp+57h+arg_8]
0x18001804e  mov     [rsp+110h+var_A0], rax
0x180018053  lea     rax, [rbp+57h+var_48]
0x180018057  mov     [rsp+110h+var_A8], rax
0x18001805c  lea     rax, [rbp+57h+arg_10]
0x180018060  mov     [rsp+110h+var_B0], rax
0x180018065  lea     rax, [rbp+57h+var_40]
0x180018069  mov     [rsp+110h+var_B8], rax
0x18001806e  lea     rax, [rbp+57h+arg_18]
0x180018072  mov     [rsp+110h+var_C0], rax
0x180018077  lea     rax, [rbp+57h+var_38]
0x18001807b  mov     [rsp+110h+var_C8], rax
0x180018080  lea     rax, [rbp+57h+var_70]
0x180018084  mov     [rsp+110h+var_D0], rax
0x180018089  lea     rax, [rbp+57h+var_30]
0x18001808d  mov     [rsp+110h+var_D8], rax
0x180018092  lea     rax, [rbp+57h+var_6C]
0x180018096  mov     [rsp+110h+var_E0], rax
0x18001809b  lea     rax, [rbp+57h+var_28]
0x18001809f  mov     [rsp+110h+var_E8], rax
0x1800180a4  lea     rax, [rbp+57h+var_20]
0x1800180a8  mov     [rbp+57h+var_68], rcx
0x1800180ac  mov     rcx, r9
0x1800180af  mov     [rsp+110h+var_F0], rax
0x1800180b4  mov     [rbp+57h+var_28], 1000000h
0x1800180bc  mov     [rbp+57h+var_20], 0
0x1800180c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800180c9  jmp     short loc_180018142
0x1800180cb  call    ?zInternalStop@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800180d0  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x1800180d5  mov     rdi, rax
0x1800180d8  mov     ecx, [rax]
0x1800180da  cmp     ecx, 5
0x1800180dd  jbe     short loc_180018142
0x1800180df  mov     rdx, 200000000000h
0x1800180e9  mov     rcx, rax
0x1800180ec  call    _tlgKeywordOn
0x1800180f1  test    al, al
0x1800180f3  jz      short loc_180018142
0x1800180f5  call    cs:__imp_GetCurrentThreadId
0x1800180fb  mov     r8, [rbx+110h]
0x180018102  lea     rdx, unk_180025158
0x180018109  mov     [rbp+57h+arg_0], eax
0x18001810c  mov     rcx, rdi
0x18001810f  mov     eax, [r8+48h]
0x180018113  add     r8, 8
0x180018117  mov     [rbp+57h+arg_8], eax
0x18001811a  lea     rax, [rbp+57h+arg_0]
0x18001811e  mov     [rsp+110h+var_E0], rax
0x180018123  lea     rax, [rbp+57h+arg_8]
0x180018127  mov     [rsp+110h+var_E8], rax
0x18001812c  lea     rax, [rbp+57h+arg_10]
0x180018130  mov     [rsp+110h+var_F0], rax
0x180018135  mov     [rbp+57h+arg_10], 0
0x18001813d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018142  mov     rcx, rbx
0x180018145  add     rsp, 100h
0x18001814c  pop     rdi
0x18001814d  pop     rbx
0x18001814e  pop     rbp
0x18001814f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
