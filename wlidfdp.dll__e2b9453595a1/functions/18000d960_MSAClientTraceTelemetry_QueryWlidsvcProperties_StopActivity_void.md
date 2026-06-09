# MSAClientTraceTelemetry::QueryWlidsvcProperties::StopActivity(void)

- ea: `0x18000d960`
- end: `0x18000db8a`
- name: `?StopActivity@QueryWlidsvcProperties@MSAClientTraceTelemetry@@MEAAXXZ`
- size: `554`
- prototype: `void __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001458`
- `0x18000176c`
- `0x18000ca18`
- `0x18000cea8`
- `0x18000d960`
- `0x18000ed64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db2a`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::StopActivity(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // ecx
  __int64 v14; // r9
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v19; // [rsp+D0h] [rbp-70h] BYREF
  char *v20; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v21; // [rsp+E0h] [rbp-60h] BYREF
  char *v22; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v23; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v24; // [rsp+F8h] [rbp-48h] BYREF
  char *v25; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v26; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v30; // [rsp+150h] [rbp+10h] BYREF
  int v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  int v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = MSAClientTraceTelemetry::Provider(v5);
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v32) = v4[26];
      v8 = *((_QWORD *)this + 34);
      v22 = (char *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v33 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = (char *)*((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v18 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v19 = v7;
      v30 = v4[17];
      v31 = v4[4];
      v20 = (char *)*((_QWORD *)v4 + 15);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)byte_18001B541,
        v8 + 8,
        (__int64)v6,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        &v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v33,
        &v23,
        &v22,
        (__int64)&v32,
        &v21,
        &v20,
        (__int64)&v31,
        (__int64)&v30,
        &v19);
    }
  }
  else
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = MSAClientTraceTelemetry::Provider(v9);
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v13 = *(_DWORD *)(v12 + 72);
      v32 = 0x1000000;
      v31 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&byte_18001BE3F,
        v12 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000d960  push    rbp
0x18000d962  push    rbx
0x18000d963  push    rdi
0x18000d964  lea     rbp, [rsp+10h]
0x18000d969  sub     rsp, 130h
0x18000d970  mov     rdi, [rcx+110h]
0x18000d977  mov     rbx, rcx
0x18000d97a  mov     eax, [rdi+48h]
0x18000d97d  test    eax, eax
0x18000d97f  jns     loc_18000DB16
0x18000d985  add     rdi, 50h ; 'P'
0x18000d989  cmp     eax, [rdi+8]
0x18000d98c  jnz     loc_18000DB16
0x18000d992  test    rdi, rdi
0x18000d995  jz      loc_18000DB16
0x18000d99b  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d9a0  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000d9a5  mov     r9, rax
0x18000d9a8  mov     ecx, [rax]
0x18000d9aa  cmp     ecx, 5
0x18000d9ad  jbe     loc_18000DB78
0x18000d9b3  mov     rax, [rdi+70h]
0x18000d9b7  lea     rdx, byte_18001B541
0x18000d9be  mov     rcx, [rdi+30h]
0x18000d9c2  mov     [rbp+var_60], rax
0x18000d9c6  mov     eax, [rdi+68h]
0x18000d9c9  mov     dword ptr [rbp+arg_10], eax
0x18000d9cc  mov     rax, [rdi+60h]
0x18000d9d0  mov     r8, [rbx+110h]
0x18000d9d7  mov     [rbp+var_58], rax
0x18000d9db  add     r8, 8
0x18000d9df  mov     rax, [rdi+58h]
0x18000d9e3  mov     [rbp+var_50], rax
0x18000d9e7  mov     eax, [rdi+50h]
0x18000d9ea  mov     [rbp+arg_18], eax
0x18000d9ed  mov     rax, [rdi+48h]
0x18000d9f1  mov     [rbp+var_48], rax
0x18000d9f5  mov     eax, [rdi+20h]
0x18000d9f8  mov     [rbp+var_80], eax
0x18000d9fb  mov     rax, [rdi+18h]
0x18000d9ff  mov     [rbp+var_40], rax
0x18000da03  mov     eax, [rdi]
0x18000da05  mov     [rbp+var_7C], eax
0x18000da08  mov     rax, [rdi+80h]
0x18000da0f  mov     [rbp+var_38], rax
0x18000da13  mov     eax, [rdi+40h]
0x18000da16  mov     [rbp+var_78], eax
0x18000da19  mov     rax, [rdi+38h]
0x18000da1d  mov     [rbp+var_30], rax
0x18000da21  mov     eax, [rdi+8]
0x18000da24  mov     [rbp+var_74], eax
0x18000da27  mov     eax, 1000000h
0x18000da2c  mov     [rbp+var_28], rax
0x18000da30  mov     [rbp+var_20], rax
0x18000da34  lea     rax, [rbp+var_70]
0x18000da38  mov     [rsp+140h+var_90], rax
0x18000da40  lea     rax, [rbp+arg_0]
0x18000da44  mov     [rsp+140h+var_98], rax
0x18000da4c  lea     rax, [rbp+arg_8]
0x18000da50  mov     [rsp+140h+var_A0], rax
0x18000da58  lea     rax, [rbp+var_68]
0x18000da5c  mov     [rsp+140h+var_A8], rax
0x18000da64  lea     rax, [rbp+var_60]
0x18000da68  mov     [rsp+140h+var_B0], rax
0x18000da70  lea     rax, [rbp+arg_10]
0x18000da74  mov     [rsp+140h+var_B8], rax
0x18000da7c  lea     rax, [rbp+var_58]
0x18000da80  mov     [rsp+140h+var_C0], rax
0x18000da88  lea     rax, [rbp+var_50]
0x18000da8c  mov     [rsp+140h+var_C8], rax
0x18000da91  lea     rax, [rbp+arg_18]
0x18000da95  mov     [rsp+140h+var_D0], rax
0x18000da9a  lea     rax, [rbp+var_48]
0x18000da9e  mov     [rsp+140h+var_D8], rax
0x18000daa3  lea     rax, [rbp+var_80]
0x18000daa7  mov     [rsp+140h+var_E0], rax
0x18000daac  lea     rax, [rbp+var_40]
0x18000dab0  mov     [rsp+140h+var_E8], rax
0x18000dab5  lea     rax, [rbp+var_7C]
0x18000dab9  mov     [rsp+140h+var_F0], rax
0x18000dabe  lea     rax, [rbp+var_38]
0x18000dac2  mov     [rsp+140h+var_F8], rax
0x18000dac7  lea     rax, [rbp+var_78]
0x18000dacb  mov     [rsp+140h+var_100], rax
0x18000dad0  lea     rax, [rbp+var_30]
0x18000dad4  mov     [rsp+140h+var_108], rax
0x18000dad9  lea     rax, [rbp+var_74]
0x18000dadd  mov     [rbp+var_70], rcx
0x18000dae1  mov     ecx, [rdi+44h]
0x18000dae4  mov     [rsp+140h+var_110], rax
0x18000dae9  lea     rax, [rbp+var_28]
0x18000daed  mov     [rbp+arg_0], ecx
0x18000daf0  mov     ecx, [rdi+10h]
0x18000daf3  mov     [rbp+arg_8], ecx
0x18000daf6  mov     rcx, [rdi+78h]
0x18000dafa  mov     [rsp+140h+var_118], rax
0x18000daff  lea     rax, [rbp+var_20]
0x18000db03  mov     [rbp+var_68], rcx
0x18000db07  mov     rcx, r9
0x18000db0a  mov     [rsp+140h+var_120], rax
0x18000db0f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000db14  jmp     short loc_18000DB78
0x18000db16  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000db1b  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000db20  mov     rdi, rax
0x18000db23  mov     ecx, [rax]
0x18000db25  cmp     ecx, 5
0x18000db28  jbe     short loc_18000DB78
0x18000db2a  call    cs:__imp_GetCurrentThreadId
0x18000db30  mov     r8, [rbx+110h]
0x18000db37  lea     rdx, byte_18001BE3F
0x18000db3e  mov     [rbp+arg_0], eax
0x18000db41  mov     eax, 1000000h
0x18000db46  mov     ecx, [r8+48h]
0x18000db4a  add     r8, 8
0x18000db4e  mov     [rbp+arg_10], rax
0x18000db52  lea     rax, [rbp+arg_0]
0x18000db56  mov     [rsp+140h+var_110], rax
0x18000db5b  lea     rax, [rbp+arg_8]
0x18000db5f  mov     [rsp+140h+var_118], rax
0x18000db64  lea     rax, [rbp+arg_10]
0x18000db68  mov     [rbp+arg_8], ecx
0x18000db6b  mov     rcx, rdi
0x18000db6e  mov     [rsp+140h+var_120], rax
0x18000db73  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000db78  mov     rcx, rbx
0x18000db7b  add     rsp, 130h
0x18000db82  pop     rdi
0x18000db83  pop     rbx
0x18000db84  pop     rbp
0x18000db85  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
