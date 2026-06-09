# UserenvTelemetry::WINAPIDeleteProfile::StopActivity(void)

- ea: `0x180014760`
- end: `0x180014988`
- name: `?StopActivity@WINAPIDeleteProfile@UserenvTelemetry@@MEAAXXZ`
- size: `552`
- prototype: `void __fastcall(UserenvTelemetry::WINAPIDeleteProfile *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800012a4`
- `0x180001558`
- `0x180001d68`
- `0x18000d8ec`
- `0x180013d08`
- `0x180014760`
- `0x180014c30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014922`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014922`

## pseudocode

```c
void __fastcall UserenvTelemetry::WINAPIDeleteProfile::StopActivity(UserenvTelemetry::WINAPIDeleteProfile *this)
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
        (unsigned int)byte_180022269,
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
        (unsigned int)&word_180021F26,
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
0x180014760  push    rbp
0x180014762  push    rbx
0x180014763  push    rdi
0x180014764  lea     rbp, [rsp-47h]
0x180014769  sub     rsp, 100h
0x180014770  mov     rdi, [rcx+110h]
0x180014777  mov     rbx, rcx
0x18001477a  mov     eax, [rdi+48h]
0x18001477d  test    eax, eax
0x18001477f  jns     loc_1800148F8
0x180014785  add     rdi, 50h ; 'P'
0x180014789  cmp     eax, [rdi+8]
0x18001478c  jnz     loc_1800148F8
0x180014792  test    rdi, rdi
0x180014795  jz      loc_1800148F8
0x18001479b  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800147a0  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x1800147a5  mov     r9, rax
0x1800147a8  mov     ecx, [rax]
0x1800147aa  cmp     ecx, 5
0x1800147ad  jbe     loc_180014976
0x1800147b3  mov     rdx, 400000000000h
0x1800147bd  mov     rcx, rax
0x1800147c0  call    _tlgKeywordOn
0x1800147c5  test    al, al
0x1800147c7  jz      loc_180014976
0x1800147cd  mov     rax, [rdi+70h]
0x1800147d1  lea     rdx, byte_180022269
0x1800147d8  mov     rcx, [rdi+78h]
0x1800147dc  mov     r8, [rbx+110h]
0x1800147e3  mov     [rbp+57h+var_60], rax
0x1800147e7  add     r8, 8
0x1800147eb  mov     eax, [rdi+68h]
0x1800147ee  mov     [rbp+57h+arg_0], eax
0x1800147f1  mov     rax, [rdi+60h]
0x1800147f5  mov     [rbp+57h+var_58], rax
0x1800147f9  mov     rax, [rdi+58h]
0x1800147fd  mov     [rbp+57h+var_50], rax
0x180014801  mov     eax, [rdi+50h]
0x180014804  mov     [rbp+57h+arg_8], eax
0x180014807  mov     rax, [rdi+48h]
0x18001480b  mov     [rbp+57h+var_48], rax
0x18001480f  mov     eax, [rdi+20h]
0x180014812  mov     dword ptr [rbp+57h+arg_10], eax
0x180014815  mov     rax, [rdi+18h]
0x180014819  mov     [rbp+57h+var_40], rax
0x18001481d  mov     eax, [rdi]
0x18001481f  mov     [rbp+57h+arg_18], eax
0x180014822  mov     rax, [rdi+80h]
0x180014829  mov     [rbp+57h+var_38], rax
0x18001482d  mov     eax, [rdi+40h]
0x180014830  mov     [rbp+57h+var_70], eax
0x180014833  mov     rax, [rdi+38h]
0x180014837  mov     [rbp+57h+var_30], rax
0x18001483b  mov     eax, [rdi+8]
0x18001483e  mov     [rbp+57h+var_6C], eax
0x180014841  mov     eax, 1000000h
0x180014846  mov     [rbp+57h+var_28], rax
0x18001484a  mov     [rbp+57h+var_20], rax
0x18001484e  lea     rax, [rbp+57h+var_68]
0x180014852  mov     [rsp+110h+var_78], rax
0x18001485a  lea     rax, [rbp+57h+var_60]
0x18001485e  mov     [rsp+110h+var_80], rax
0x180014866  lea     rax, [rbp+57h+arg_0]
0x18001486a  mov     [rsp+110h+var_88], rax
0x180014872  lea     rax, [rbp+57h+var_58]
0x180014876  mov     [rsp+110h+var_90], rax
0x18001487e  lea     rax, [rbp+57h+var_50]
0x180014882  mov     [rsp+110h+var_98], rax
0x180014887  lea     rax, [rbp+57h+arg_8]
0x18001488b  mov     [rsp+110h+var_A0], rax
0x180014890  lea     rax, [rbp+57h+var_48]
0x180014894  mov     [rsp+110h+var_A8], rax
0x180014899  lea     rax, [rbp+57h+arg_10]
0x18001489d  mov     [rsp+110h+var_B0], rax
0x1800148a2  lea     rax, [rbp+57h+var_40]
0x1800148a6  mov     [rsp+110h+var_B8], rax
0x1800148ab  lea     rax, [rbp+57h+arg_18]
0x1800148af  mov     [rsp+110h+var_C0], rax
0x1800148b4  lea     rax, [rbp+57h+var_38]
0x1800148b8  mov     [rsp+110h+var_C8], rax
0x1800148bd  lea     rax, [rbp+57h+var_70]
0x1800148c1  mov     [rsp+110h+var_D0], rax
0x1800148c6  lea     rax, [rbp+57h+var_30]
0x1800148ca  mov     [rsp+110h+var_D8], rax
0x1800148cf  lea     rax, [rbp+57h+var_6C]
0x1800148d3  mov     [rsp+110h+var_E0], rax
0x1800148d8  lea     rax, [rbp+57h+var_28]
0x1800148dc  mov     [rsp+110h+var_E8], rax
0x1800148e1  lea     rax, [rbp+57h+var_20]
0x1800148e5  mov     [rbp+57h+var_68], rcx
0x1800148e9  mov     rcx, r9
0x1800148ec  mov     [rsp+110h+var_F0], rax
0x1800148f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800148f6  jmp     short loc_180014976
0x1800148f8  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800148fd  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x180014902  mov     rdi, rax
0x180014905  mov     ecx, [rax]
0x180014907  cmp     ecx, 5
0x18001490a  jbe     short loc_180014976
0x18001490c  mov     rdx, 400000000000h
0x180014916  mov     rcx, rax
0x180014919  call    _tlgKeywordOn
0x18001491e  test    al, al
0x180014920  jz      short loc_180014976
0x180014922  call    cs:__imp_GetCurrentThreadId
0x180014929  nop     dword ptr [rax+rax+00h]
0x18001492e  mov     r8, [rbx+110h]
0x180014935  lea     rdx, word_180021F26
0x18001493c  mov     [rbp+57h+arg_0], eax
0x18001493f  mov     rcx, rdi
0x180014942  mov     eax, [r8+48h]
0x180014946  add     r8, 8
0x18001494a  mov     [rbp+57h+arg_8], eax
0x18001494d  mov     eax, 1000000h
0x180014952  mov     [rbp+57h+arg_10], rax
0x180014956  lea     rax, [rbp+57h+arg_0]
0x18001495a  mov     [rsp+110h+var_E0], rax
0x18001495f  lea     rax, [rbp+57h+arg_8]
0x180014963  mov     [rsp+110h+var_E8], rax
0x180014968  lea     rax, [rbp+57h+arg_10]
0x18001496c  mov     [rsp+110h+var_F0], rax
0x180014971  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014976  mov     rcx, rbx
0x180014979  add     rsp, 100h
0x180014980  pop     rdi
0x180014981  pop     rbx
0x180014982  pop     rbp
0x180014983  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
