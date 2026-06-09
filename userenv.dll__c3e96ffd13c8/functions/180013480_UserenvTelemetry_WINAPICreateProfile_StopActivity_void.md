# UserenvTelemetry::WINAPICreateProfile::StopActivity(void)

- ea: `0x180013480`
- end: `0x1800136a2`
- name: `?StopActivity@WINAPICreateProfile@UserenvTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(UserenvTelemetry::WINAPICreateProfile *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800012a4`
- `0x180001558`
- `0x180001d58`
- `0x18000cc14`
- `0x180012c48`
- `0x180013480`
- `0x180013b7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013642`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013642`

## pseudocode

```c
void __fastcall UserenvTelemetry::WINAPICreateProfile::StopActivity(UserenvTelemetry::WINAPICreateProfile *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  const size_t *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  int v14; // edi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  const size_t *v20; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v21; // [rsp+B0h] [rbp-9h] BYREF
  const size_t *v22; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  const size_t *v25; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v29[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v30; // [rsp+120h] [rbp+67h] BYREF
  int v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  int v33; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = ProfileAPILogging::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
    {
      v9 = (const size_t *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v30 = v4[26];
      v22 = (const size_t *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v32) = v4[8];
      v25 = (const size_t *)*((_QWORD *)v4 + 3);
      v33 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v18 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v19 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (int)byte_180020DBB,
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
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = ProfileAPILogging::Provider(v11);
    v14 = (int)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v16 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (int)&byte_180020D67,
        v16 + 8,
        v17,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180013480  push    rbp
0x180013482  push    rbx
0x180013483  push    rdi
0x180013484  lea     rbp, [rsp-47h]
0x180013489  sub     rsp, 100h
0x180013490  mov     rdi, [rcx+110h]
0x180013497  mov     rbx, rcx
0x18001349a  mov     eax, [rdi+48h]
0x18001349d  test    eax, eax
0x18001349f  jns     loc_180013618
0x1800134a5  add     rdi, 50h ; 'P'
0x1800134a9  cmp     eax, [rdi+8]
0x1800134ac  jnz     loc_180013618
0x1800134b2  test    rdi, rdi
0x1800134b5  jz      loc_180013618
0x1800134bb  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800134c0  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x1800134c5  mov     r9, rax
0x1800134c8  mov     ecx, [rax]
0x1800134ca  cmp     ecx, 5
0x1800134cd  jbe     loc_180013690
0x1800134d3  mov     rdx, 400000000000h
0x1800134dd  mov     rcx, rax
0x1800134e0  call    _tlgKeywordOn
0x1800134e5  test    al, al
0x1800134e7  jz      loc_180013690
0x1800134ed  mov     rax, [rdi+70h]
0x1800134f1  lea     rdx, byte_180020DBB
0x1800134f8  mov     rcx, [rdi+78h]
0x1800134fc  mov     r8, [rbx+110h]
0x180013503  mov     [rbp+57h+var_60], rax
0x180013507  add     r8, 8
0x18001350b  mov     eax, [rdi+68h]
0x18001350e  mov     [rbp+57h+arg_0], eax
0x180013511  mov     rax, [rdi+60h]
0x180013515  mov     [rbp+57h+var_58], rax
0x180013519  mov     rax, [rdi+58h]
0x18001351d  mov     [rbp+57h+var_50], rax
0x180013521  mov     eax, [rdi+50h]
0x180013524  mov     [rbp+57h+arg_8], eax
0x180013527  mov     rax, [rdi+48h]
0x18001352b  mov     [rbp+57h+var_48], rax
0x18001352f  mov     eax, [rdi+20h]
0x180013532  mov     dword ptr [rbp+57h+arg_10], eax
0x180013535  mov     rax, [rdi+18h]
0x180013539  mov     [rbp+57h+var_40], rax
0x18001353d  mov     eax, [rdi]
0x18001353f  mov     [rbp+57h+arg_18], eax
0x180013542  mov     rax, [rdi+80h]
0x180013549  mov     [rbp+57h+var_38], rax
0x18001354d  mov     eax, [rdi+40h]
0x180013550  mov     [rbp+57h+var_70], eax
0x180013553  mov     rax, [rdi+38h]
0x180013557  mov     [rbp+57h+var_30], rax
0x18001355b  mov     eax, [rdi+8]
0x18001355e  mov     [rbp+57h+var_6C], eax
0x180013561  mov     eax, 1000000h
0x180013566  mov     [rbp+57h+var_28], rax
0x18001356a  mov     [rbp+57h+var_20], rax
0x18001356e  lea     rax, [rbp+57h+var_68]
0x180013572  mov     [rsp+110h+var_78], rax
0x18001357a  lea     rax, [rbp+57h+var_60]
0x18001357e  mov     [rsp+110h+var_80], rax
0x180013586  lea     rax, [rbp+57h+arg_0]
0x18001358a  mov     [rsp+110h+var_88], rax
0x180013592  lea     rax, [rbp+57h+var_58]
0x180013596  mov     [rsp+110h+var_90], rax
0x18001359e  lea     rax, [rbp+57h+var_50]
0x1800135a2  mov     [rsp+110h+var_98], rax
0x1800135a7  lea     rax, [rbp+57h+arg_8]
0x1800135ab  mov     [rsp+110h+var_A0], rax
0x1800135b0  lea     rax, [rbp+57h+var_48]
0x1800135b4  mov     [rsp+110h+var_A8], rax
0x1800135b9  lea     rax, [rbp+57h+arg_10]
0x1800135bd  mov     [rsp+110h+var_B0], rax
0x1800135c2  lea     rax, [rbp+57h+var_40]
0x1800135c6  mov     [rsp+110h+var_B8], rax
0x1800135cb  lea     rax, [rbp+57h+arg_18]
0x1800135cf  mov     [rsp+110h+var_C0], rax
0x1800135d4  lea     rax, [rbp+57h+var_38]
0x1800135d8  mov     [rsp+110h+var_C8], rax
0x1800135dd  lea     rax, [rbp+57h+var_70]
0x1800135e1  mov     [rsp+110h+var_D0], rax
0x1800135e6  lea     rax, [rbp+57h+var_30]
0x1800135ea  mov     [rsp+110h+var_D8], rax
0x1800135ef  lea     rax, [rbp+57h+var_6C]
0x1800135f3  mov     [rsp+110h+var_E0], rax
0x1800135f8  lea     rax, [rbp+57h+var_28]
0x1800135fc  mov     [rsp+110h+var_E8], rax
0x180013601  lea     rax, [rbp+57h+var_20]
0x180013605  mov     [rbp+57h+var_68], rcx
0x180013609  mov     rcx, r9
0x18001360c  mov     [rsp+110h+var_F0], rax
0x180013611  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180013616  jmp     short loc_180013690
0x180013618  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001361d  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x180013622  mov     rdi, rax
0x180013625  mov     ecx, [rax]
0x180013627  cmp     ecx, 5
0x18001362a  jbe     short loc_180013690
0x18001362c  mov     rdx, 400000000000h
0x180013636  mov     rcx, rax
0x180013639  call    _tlgKeywordOn
0x18001363e  test    al, al
0x180013640  jz      short loc_180013690
0x180013642  call    cs:__imp_GetCurrentThreadId
0x180013648  mov     r8, [rbx+110h]
0x18001364f  lea     rdx, byte_180020D67
0x180013656  mov     [rbp+57h+arg_0], eax
0x180013659  mov     rcx, rdi
0x18001365c  mov     eax, [r8+48h]
0x180013660  add     r8, 8
0x180013664  mov     [rbp+57h+arg_8], eax
0x180013667  mov     eax, 1000000h
0x18001366c  mov     [rbp+57h+arg_10], rax
0x180013670  lea     rax, [rbp+57h+arg_0]
0x180013674  mov     [rsp+110h+var_E0], rax
0x180013679  lea     rax, [rbp+57h+arg_8]
0x18001367d  mov     [rsp+110h+var_E8], rax
0x180013682  lea     rax, [rbp+57h+arg_10]
0x180013686  mov     [rsp+110h+var_F0], rax
0x18001368b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013690  mov     rcx, rbx
0x180013693  add     rsp, 100h
0x18001369a  pop     rdi
0x18001369b  pop     rbx
0x18001369c  pop     rbp
0x18001369d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
