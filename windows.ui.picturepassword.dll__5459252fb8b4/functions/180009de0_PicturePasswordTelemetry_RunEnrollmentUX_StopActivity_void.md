# PicturePasswordTelemetry::RunEnrollmentUX::StopActivity(void)

- ea: `0x180009de0`
- end: `0x18000a004`
- name: `?StopActivity@RunEnrollmentUX@PicturePasswordTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(PicturePasswordTelemetry::RunEnrollmentUX *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x180007d94`
- `0x180008c00`
- `0x180009de0`
- `0x18000b9dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009fa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009fa5`

## pseudocode

```c
void __fastcall PicturePasswordTelemetry::RunEnrollmentUX::StopActivity(
        PicturePasswordTelemetry::RunEnrollmentUX *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  const WCHAR *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
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
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = PicturePasswordLogger::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
    {
      v8 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
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
      v18 = v8;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)byte_180024A19,
        v9 + 8,
        v7,
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
    wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = PicturePasswordLogger::Provider();
    v12 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)qword_180024B40,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180009de0  push    rbp
0x180009de2  push    rbx
0x180009de3  push    rdi
0x180009de4  lea     rbp, [rsp-47h]
0x180009de9  sub     rsp, 100h
0x180009df0  mov     rdi, [rcx+110h]
0x180009df7  mov     rbx, rcx
0x180009dfa  mov     eax, [rdi+48h]
0x180009dfd  test    eax, eax
0x180009dff  jns     loc_180009F7B
0x180009e05  add     rdi, 50h ; 'P'
0x180009e09  cmp     eax, [rdi+8]
0x180009e0c  jnz     loc_180009F7B
0x180009e12  test    rdi, rdi
0x180009e15  jz      loc_180009F7B
0x180009e1b  call    ?zInternalStop@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180009e20  call    ?Provider@PicturePasswordLogger@@SAPEBU_tlgProvider_t@@XZ; PicturePasswordLogger::Provider(void)
0x180009e25  mov     r9, rax
0x180009e28  mov     ecx, [rax]
0x180009e2a  cmp     ecx, 5
0x180009e2d  jbe     loc_180009FF2
0x180009e33  mov     rdx, 200000000000h
0x180009e3d  mov     rcx, rax
0x180009e40  call    _tlgKeywordOn
0x180009e45  test    al, al
0x180009e47  jz      loc_180009FF2
0x180009e4d  mov     rax, [rdi+70h]
0x180009e51  lea     rdx, byte_180024A19
0x180009e58  mov     rcx, [rdi+78h]
0x180009e5c  mov     r8, [rbx+110h]
0x180009e63  mov     [rbp+57h+var_60], rax
0x180009e67  add     r8, 8
0x180009e6b  mov     eax, [rdi+68h]
0x180009e6e  mov     [rbp+57h+arg_0], eax
0x180009e71  mov     rax, [rdi+60h]
0x180009e75  mov     [rbp+57h+var_58], rax
0x180009e79  mov     rax, [rdi+58h]
0x180009e7d  mov     [rbp+57h+var_50], rax
0x180009e81  mov     eax, [rdi+50h]
0x180009e84  mov     [rbp+57h+arg_8], eax
0x180009e87  mov     rax, [rdi+48h]
0x180009e8b  mov     [rbp+57h+var_48], rax
0x180009e8f  mov     eax, [rdi+20h]
0x180009e92  mov     dword ptr [rbp+57h+arg_10], eax
0x180009e95  mov     rax, [rdi+18h]
0x180009e99  mov     [rbp+57h+var_40], rax
0x180009e9d  mov     eax, [rdi]
0x180009e9f  mov     [rbp+57h+arg_18], eax
0x180009ea2  mov     rax, [rdi+80h]
0x180009ea9  mov     [rbp+57h+var_38], rax
0x180009ead  mov     eax, [rdi+40h]
0x180009eb0  mov     [rbp+57h+var_70], eax
0x180009eb3  mov     rax, [rdi+38h]
0x180009eb7  mov     [rbp+57h+var_30], rax
0x180009ebb  mov     eax, [rdi+8]
0x180009ebe  mov     [rbp+57h+var_6C], eax
0x180009ec1  lea     rax, [rbp+57h+var_68]
0x180009ec5  mov     [rsp+110h+var_78], rax
0x180009ecd  lea     rax, [rbp+57h+var_60]
0x180009ed1  mov     [rsp+110h+var_80], rax
0x180009ed9  lea     rax, [rbp+57h+arg_0]
0x180009edd  mov     [rsp+110h+var_88], rax
0x180009ee5  lea     rax, [rbp+57h+var_58]
0x180009ee9  mov     [rsp+110h+var_90], rax
0x180009ef1  lea     rax, [rbp+57h+var_50]
0x180009ef5  mov     [rsp+110h+var_98], rax
0x180009efa  lea     rax, [rbp+57h+arg_8]
0x180009efe  mov     [rsp+110h+var_A0], rax
0x180009f03  lea     rax, [rbp+57h+var_48]
0x180009f07  mov     [rsp+110h+var_A8], rax
0x180009f0c  lea     rax, [rbp+57h+arg_10]
0x180009f10  mov     [rsp+110h+var_B0], rax
0x180009f15  lea     rax, [rbp+57h+var_40]
0x180009f19  mov     [rsp+110h+var_B8], rax
0x180009f1e  lea     rax, [rbp+57h+arg_18]
0x180009f22  mov     [rsp+110h+var_C0], rax
0x180009f27  lea     rax, [rbp+57h+var_38]
0x180009f2b  mov     [rsp+110h+var_C8], rax
0x180009f30  lea     rax, [rbp+57h+var_70]
0x180009f34  mov     [rsp+110h+var_D0], rax
0x180009f39  lea     rax, [rbp+57h+var_30]
0x180009f3d  mov     [rsp+110h+var_D8], rax
0x180009f42  lea     rax, [rbp+57h+var_6C]
0x180009f46  mov     [rsp+110h+var_E0], rax
0x180009f4b  lea     rax, [rbp+57h+var_28]
0x180009f4f  mov     [rsp+110h+var_E8], rax
0x180009f54  lea     rax, [rbp+57h+var_20]
0x180009f58  mov     [rbp+57h+var_68], rcx
0x180009f5c  mov     rcx, r9
0x180009f5f  mov     [rsp+110h+var_F0], rax
0x180009f64  mov     [rbp+57h+var_28], 1000000h
0x180009f6c  mov     [rbp+57h+var_20], 0
0x180009f74  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180009f79  jmp     short loc_180009FF2
0x180009f7b  call    ?zInternalStop@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180009f80  call    ?Provider@PicturePasswordLogger@@SAPEBU_tlgProvider_t@@XZ; PicturePasswordLogger::Provider(void)
0x180009f85  mov     rdi, rax
0x180009f88  mov     ecx, [rax]
0x180009f8a  cmp     ecx, 5
0x180009f8d  jbe     short loc_180009FF2
0x180009f8f  mov     rdx, 200000000000h
0x180009f99  mov     rcx, rax
0x180009f9c  call    _tlgKeywordOn
0x180009fa1  test    al, al
0x180009fa3  jz      short loc_180009FF2
0x180009fa5  call    cs:__imp_GetCurrentThreadId
0x180009fab  mov     r8, [rbx+110h]
0x180009fb2  lea     rdx, qword_180024B40
0x180009fb9  mov     [rbp+57h+arg_0], eax
0x180009fbc  mov     rcx, rdi
0x180009fbf  mov     eax, [r8+48h]
0x180009fc3  add     r8, 8
0x180009fc7  mov     [rbp+57h+arg_8], eax
0x180009fca  lea     rax, [rbp+57h+arg_0]
0x180009fce  mov     [rsp+110h+var_E0], rax
0x180009fd3  lea     rax, [rbp+57h+arg_8]
0x180009fd7  mov     [rsp+110h+var_E8], rax
0x180009fdc  lea     rax, [rbp+57h+arg_10]
0x180009fe0  mov     [rsp+110h+var_F0], rax
0x180009fe5  mov     [rbp+57h+arg_10], 0
0x180009fed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009ff2  mov     rcx, rbx
0x180009ff5  add     rsp, 100h
0x180009ffc  pop     rdi
0x180009ffd  pop     rbx
0x180009ffe  pop     rbp
0x180009fff  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
