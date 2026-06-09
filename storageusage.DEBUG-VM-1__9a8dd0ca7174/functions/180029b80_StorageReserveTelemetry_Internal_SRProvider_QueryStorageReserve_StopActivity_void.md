# StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StopActivity(void)

- ea: `0x180029b80`
- end: `0x180029dac`
- name: `?StopActivity@QueryStorageReserve@SRProvider@Internal@StorageReserveTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800036d0`
- `0x180003a54`
- `0x180027a34`
- `0x18002832c`
- `0x180029b80`
- `0x18002a8e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d4d`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StopActivity(
        StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *this)
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
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
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
        (unsigned int)byte_180038BC9,
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
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
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
        (unsigned int)byte_180038B75,
        v11 + 8,
        v12,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180029b80  push    rbp
0x180029b82  push    rbx
0x180029b83  push    rdi
0x180029b84  lea     rbp, [rsp+10h]
0x180029b89  sub     rsp, 130h
0x180029b90  mov     rdi, [rcx+110h]
0x180029b97  mov     rbx, rcx
0x180029b9a  mov     eax, [rdi+48h]
0x180029b9d  test    eax, eax
0x180029b9f  jns     loc_180029D39
0x180029ba5  add     rdi, 50h ; 'P'
0x180029ba9  cmp     eax, [rdi+8]
0x180029bac  jnz     loc_180029D39
0x180029bb2  test    rdi, rdi
0x180029bb5  jz      loc_180029D39
0x180029bbb  call    ?zInternalStop@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180029bc0  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x180029bc5  mov     r9, rax
0x180029bc8  mov     ecx, [rax]
0x180029bca  cmp     ecx, 5
0x180029bcd  jbe     loc_180029D9A
0x180029bd3  mov     rax, [rdi+70h]
0x180029bd7  lea     rdx, byte_180038BC9
0x180029bde  mov     rcx, [rdi+30h]
0x180029be2  mov     [rbp+var_60], rax
0x180029be6  mov     eax, [rdi+68h]
0x180029be9  mov     r8, [rbx+110h]
0x180029bf0  mov     dword ptr [rbp+arg_10], eax
0x180029bf3  add     r8, 8
0x180029bf7  mov     rax, [rdi+60h]
0x180029bfb  mov     [rbp+var_58], rax
0x180029bff  mov     rax, [rdi+58h]
0x180029c03  mov     [rbp+var_50], rax
0x180029c07  mov     eax, [rdi+50h]
0x180029c0a  mov     [rbp+arg_18], eax
0x180029c0d  mov     rax, [rdi+48h]
0x180029c11  mov     [rbp+var_48], rax
0x180029c15  mov     eax, [rdi+20h]
0x180029c18  mov     [rbp+var_80], eax
0x180029c1b  mov     rax, [rdi+18h]
0x180029c1f  mov     [rbp+var_40], rax
0x180029c23  mov     eax, [rdi]
0x180029c25  mov     [rbp+var_7C], eax
0x180029c28  mov     rax, [rdi+80h]
0x180029c2f  mov     [rbp+var_38], rax
0x180029c33  mov     eax, [rdi+40h]
0x180029c36  mov     [rbp+var_78], eax
0x180029c39  mov     rax, [rdi+38h]
0x180029c3d  mov     [rbp+var_30], rax
0x180029c41  mov     eax, [rdi+8]
0x180029c44  mov     [rbp+var_74], eax
0x180029c47  lea     rax, [rbp+var_70]
0x180029c4b  mov     [rsp+140h+var_90], rax
0x180029c53  lea     rax, [rbp+arg_0]
0x180029c57  mov     [rsp+140h+var_98], rax
0x180029c5f  lea     rax, [rbp+arg_8]
0x180029c63  mov     [rsp+140h+var_A0], rax
0x180029c6b  lea     rax, [rbp+var_68]
0x180029c6f  mov     [rsp+140h+var_A8], rax
0x180029c77  lea     rax, [rbp+var_60]
0x180029c7b  mov     [rsp+140h+var_B0], rax
0x180029c83  lea     rax, [rbp+arg_10]
0x180029c87  mov     [rsp+140h+var_B8], rax
0x180029c8f  lea     rax, [rbp+var_58]
0x180029c93  mov     [rsp+140h+var_C0], rax
0x180029c9b  lea     rax, [rbp+var_50]
0x180029c9f  mov     [rsp+140h+var_C8], rax
0x180029ca4  lea     rax, [rbp+arg_18]
0x180029ca8  mov     [rsp+140h+var_D0], rax
0x180029cad  lea     rax, [rbp+var_48]
0x180029cb1  mov     [rsp+140h+var_D8], rax
0x180029cb6  lea     rax, [rbp+var_80]
0x180029cba  mov     [rsp+140h+var_E0], rax
0x180029cbf  lea     rax, [rbp+var_40]
0x180029cc3  mov     [rsp+140h+var_E8], rax
0x180029cc8  lea     rax, [rbp+var_7C]
0x180029ccc  mov     [rsp+140h+var_F0], rax
0x180029cd1  lea     rax, [rbp+var_38]
0x180029cd5  mov     [rsp+140h+var_F8], rax
0x180029cda  lea     rax, [rbp+var_78]
0x180029cde  mov     [rsp+140h+var_100], rax
0x180029ce3  lea     rax, [rbp+var_30]
0x180029ce7  mov     [rsp+140h+var_108], rax
0x180029cec  lea     rax, [rbp+var_74]
0x180029cf0  mov     [rbp+var_70], rcx
0x180029cf4  mov     ecx, [rdi+44h]
0x180029cf7  mov     [rsp+140h+var_110], rax
0x180029cfc  lea     rax, [rbp+var_28]
0x180029d00  mov     [rbp+arg_0], ecx
0x180029d03  mov     ecx, [rdi+10h]
0x180029d06  mov     [rbp+arg_8], ecx
0x180029d09  mov     rcx, [rdi+78h]
0x180029d0d  mov     [rsp+140h+var_118], rax
0x180029d12  lea     rax, [rbp+var_20]
0x180029d16  mov     [rbp+var_68], rcx
0x180029d1a  mov     rcx, r9
0x180029d1d  mov     [rsp+140h+var_120], rax
0x180029d22  mov     [rbp+var_28], 1000000h
0x180029d2a  mov     [rbp+var_20], 0
0x180029d32  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180029d37  jmp     short loc_180029D9A
0x180029d39  call    ?zInternalStop@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180029d3e  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x180029d43  mov     rdi, rax
0x180029d46  mov     ecx, [rax]
0x180029d48  cmp     ecx, 5
0x180029d4b  jbe     short loc_180029D9A
0x180029d4d  call    cs:__imp_GetCurrentThreadId
0x180029d53  mov     r8, [rbx+110h]
0x180029d5a  lea     rdx, byte_180038B75
0x180029d61  mov     [rbp+arg_0], eax
0x180029d64  lea     rax, [rbp+arg_0]
0x180029d68  mov     [rsp+140h+var_110], rax
0x180029d6d  lea     rax, [rbp+arg_8]
0x180029d71  mov     [rsp+140h+var_118], rax
0x180029d76  lea     rax, [rbp+arg_10]
0x180029d7a  mov     ecx, [r8+48h]
0x180029d7e  add     r8, 8
0x180029d82  mov     [rbp+arg_8], ecx
0x180029d85  mov     rcx, rdi
0x180029d88  mov     [rsp+140h+var_120], rax
0x180029d8d  mov     [rbp+arg_10], 0
0x180029d95  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029d9a  mov     rcx, rbx
0x180029d9d  add     rsp, 130h
0x180029da4  pop     rdi
0x180029da5  pop     rbx
0x180029da6  pop     rbp
0x180029da7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
