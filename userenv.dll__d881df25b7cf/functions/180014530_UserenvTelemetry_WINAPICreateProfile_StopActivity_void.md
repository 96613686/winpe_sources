# UserenvTelemetry::WINAPICreateProfile::StopActivity(void)

- ea: `0x180014530`
- end: `0x180014758`
- name: `?StopActivity@WINAPICreateProfile@UserenvTelemetry@@MEAAXXZ`
- size: `552`
- prototype: `void __fastcall(UserenvTelemetry::WINAPICreateProfile *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800012a4`
- `0x180001558`
- `0x180001d68`
- `0x18000d8ec`
- `0x180013d08`
- `0x180014530`
- `0x180014c30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800146f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800146f2`

## pseudocode

```c
void __fastcall UserenvTelemetry::WINAPICreateProfile::StopActivity(UserenvTelemetry::WINAPICreateProfile *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
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
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = ProfileAPILogging::Provider();
    v8 = v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v26 = 0x1000000;
      v27[0] = 0x1000000;
      v18 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)byte_180021DFB,
        v10 + 8,
        (_DWORD)v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = ProfileAPILogging::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&byte_180021DA7,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180014530  push    rbp
0x180014532  push    rbx
0x180014533  push    rdi
0x180014534  lea     rbp, [rsp-47h]
0x180014539  sub     rsp, 100h
0x180014540  mov     rdi, [rcx+110h]
0x180014547  mov     rbx, rcx
0x18001454a  mov     eax, [rdi+48h]
0x18001454d  test    eax, eax
0x18001454f  jns     loc_1800146C8
0x180014555  add     rdi, 50h ; 'P'
0x180014559  cmp     eax, [rdi+8]
0x18001455c  jnz     loc_1800146C8
0x180014562  test    rdi, rdi
0x180014565  jz      loc_1800146C8
0x18001456b  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014570  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x180014575  mov     r9, rax
0x180014578  mov     ecx, [rax]
0x18001457a  cmp     ecx, 5
0x18001457d  jbe     loc_180014746
0x180014583  mov     rdx, 400000000000h
0x18001458d  mov     rcx, rax
0x180014590  call    _tlgKeywordOn
0x180014595  test    al, al
0x180014597  jz      loc_180014746
0x18001459d  mov     rax, [rdi+70h]
0x1800145a1  lea     rdx, byte_180021DFB
0x1800145a8  mov     rcx, [rdi+78h]
0x1800145ac  mov     r8, [rbx+110h]
0x1800145b3  mov     [rbp+57h+var_60], rax
0x1800145b7  add     r8, 8
0x1800145bb  mov     eax, [rdi+68h]
0x1800145be  mov     [rbp+57h+arg_0], eax
0x1800145c1  mov     rax, [rdi+60h]
0x1800145c5  mov     [rbp+57h+var_58], rax
0x1800145c9  mov     rax, [rdi+58h]
0x1800145cd  mov     [rbp+57h+var_50], rax
0x1800145d1  mov     eax, [rdi+50h]
0x1800145d4  mov     [rbp+57h+arg_8], eax
0x1800145d7  mov     rax, [rdi+48h]
0x1800145db  mov     [rbp+57h+var_48], rax
0x1800145df  mov     eax, [rdi+20h]
0x1800145e2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800145e5  mov     rax, [rdi+18h]
0x1800145e9  mov     [rbp+57h+var_40], rax
0x1800145ed  mov     eax, [rdi]
0x1800145ef  mov     [rbp+57h+arg_18], eax
0x1800145f2  mov     rax, [rdi+80h]
0x1800145f9  mov     [rbp+57h+var_38], rax
0x1800145fd  mov     eax, [rdi+40h]
0x180014600  mov     [rbp+57h+var_70], eax
0x180014603  mov     rax, [rdi+38h]
0x180014607  mov     [rbp+57h+var_30], rax
0x18001460b  mov     eax, [rdi+8]
0x18001460e  mov     [rbp+57h+var_6C], eax
0x180014611  mov     eax, 1000000h
0x180014616  mov     [rbp+57h+var_28], rax
0x18001461a  mov     [rbp+57h+var_20], rax
0x18001461e  lea     rax, [rbp+57h+var_68]
0x180014622  mov     [rsp+110h+var_78], rax
0x18001462a  lea     rax, [rbp+57h+var_60]
0x18001462e  mov     [rsp+110h+var_80], rax
0x180014636  lea     rax, [rbp+57h+arg_0]
0x18001463a  mov     [rsp+110h+var_88], rax
0x180014642  lea     rax, [rbp+57h+var_58]
0x180014646  mov     [rsp+110h+var_90], rax
0x18001464e  lea     rax, [rbp+57h+var_50]
0x180014652  mov     [rsp+110h+var_98], rax
0x180014657  lea     rax, [rbp+57h+arg_8]
0x18001465b  mov     [rsp+110h+var_A0], rax
0x180014660  lea     rax, [rbp+57h+var_48]
0x180014664  mov     [rsp+110h+var_A8], rax
0x180014669  lea     rax, [rbp+57h+arg_10]
0x18001466d  mov     [rsp+110h+var_B0], rax
0x180014672  lea     rax, [rbp+57h+var_40]
0x180014676  mov     [rsp+110h+var_B8], rax
0x18001467b  lea     rax, [rbp+57h+arg_18]
0x18001467f  mov     [rsp+110h+var_C0], rax
0x180014684  lea     rax, [rbp+57h+var_38]
0x180014688  mov     [rsp+110h+var_C8], rax
0x18001468d  lea     rax, [rbp+57h+var_70]
0x180014691  mov     [rsp+110h+var_D0], rax
0x180014696  lea     rax, [rbp+57h+var_30]
0x18001469a  mov     [rsp+110h+var_D8], rax
0x18001469f  lea     rax, [rbp+57h+var_6C]
0x1800146a3  mov     [rsp+110h+var_E0], rax
0x1800146a8  lea     rax, [rbp+57h+var_28]
0x1800146ac  mov     [rsp+110h+var_E8], rax
0x1800146b1  lea     rax, [rbp+57h+var_20]
0x1800146b5  mov     [rbp+57h+var_68], rcx
0x1800146b9  mov     rcx, r9
0x1800146bc  mov     [rsp+110h+var_F0], rax
0x1800146c1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800146c6  jmp     short loc_180014746
0x1800146c8  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800146cd  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x1800146d2  mov     rdi, rax
0x1800146d5  mov     ecx, [rax]
0x1800146d7  cmp     ecx, 5
0x1800146da  jbe     short loc_180014746
0x1800146dc  mov     rdx, 400000000000h
0x1800146e6  mov     rcx, rax
0x1800146e9  call    _tlgKeywordOn
0x1800146ee  test    al, al
0x1800146f0  jz      short loc_180014746
0x1800146f2  call    cs:__imp_GetCurrentThreadId
0x1800146f9  nop     dword ptr [rax+rax+00h]
0x1800146fe  mov     r8, [rbx+110h]
0x180014705  lea     rdx, byte_180021DA7
0x18001470c  mov     [rbp+57h+arg_0], eax
0x18001470f  mov     rcx, rdi
0x180014712  mov     eax, [r8+48h]
0x180014716  add     r8, 8
0x18001471a  mov     [rbp+57h+arg_8], eax
0x18001471d  mov     eax, 1000000h
0x180014722  mov     [rbp+57h+arg_10], rax
0x180014726  lea     rax, [rbp+57h+arg_0]
0x18001472a  mov     [rsp+110h+var_E0], rax
0x18001472f  lea     rax, [rbp+57h+arg_8]
0x180014733  mov     [rsp+110h+var_E8], rax
0x180014738  lea     rax, [rbp+57h+arg_10]
0x18001473c  mov     [rsp+110h+var_F0], rax
0x180014741  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014746  mov     rcx, rbx
0x180014749  add     rsp, 100h
0x180014750  pop     rdi
0x180014751  pop     rbx
0x180014752  pop     rbp
0x180014753  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
