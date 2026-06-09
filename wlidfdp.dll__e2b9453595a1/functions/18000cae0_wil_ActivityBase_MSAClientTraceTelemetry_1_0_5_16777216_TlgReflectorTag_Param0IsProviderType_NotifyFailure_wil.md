# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x18000cae0`
- end: `0x18000ce0c`
- name: `?NotifyFailure@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `812`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800018f8`
- `0x180001b9c`
- `0x180001fec`
- `0x180008810`
- `0x18000c848`
- `0x18000ca50`
- `0x18000cae0`
- `0x18000cea8`
- `0x180012010`

## pseudocode

```c
char __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  char *v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // r9
  const unsigned __int16 *v10; // rcx
  __int64 v11; // r8
  _DWORD *v12; // rax
  int v13; // edx
  int v15; // [rsp+B0h] [rbp-80h] BYREF
  int v16; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v17; // [rsp+B8h] [rbp-78h] BYREF
  char *v18; // [rsp+C0h] [rbp-70h] BYREF
  char *v19; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp-58h] BYREF
  char *v22; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+E8h] [rbp-48h] BYREF
  char *v24; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v27; // [rsp+108h] [rbp-28h] BYREF
  __int64 v28[4]; // [rsp+110h] [rbp-20h] BYREF
  RTL_SRWLOCK *v29; // [rsp+140h] [rbp+10h] BYREF
  int v30; // [rsp+148h] [rbp+18h] BYREF
  int v31; // [rsp+150h] [rbp+20h] BYREF
  int v32; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v9 = MSAClientTraceTelemetry::Provider();
      if ( *(_DWORD *)v9 > 2u )
      {
        v10 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        v11 = a1[34];
        v31 = a2[26];
        v22 = (char *)*((_QWORD *)a2 + 12);
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v32 = a2[20];
        v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v16 = a2[8];
        v19 = (char *)*((_QWORD *)a2 + 3);
        v15 = *a2;
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v17) = a2[16];
        v27 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v18) = a2[2];
        v25 = (__int64)v10;
        LODWORD(v29) = a2[17];
        v30 = a2[4];
        v24 = (char *)*((_QWORD *)a2 + 15);
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v28[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)v9,
          (__int64)&byte_18001BD07,
          v11 + 8,
          (__int64)v9,
          (__int64)v28,
          (__int64)&v18,
          &v27,
          (__int64)&v17,
          &v26,
          (__int64)&v15,
          &v19,
          (__int64)&v16,
          &v20,
          (__int64)&v32,
          &v21,
          &v22,
          (__int64)&v31,
          &v23,
          &v24,
          (__int64)&v30,
          (__int64)&v29,
          (const unsigned __int16 **)&v25);
      }
    }
    else
    {
      v4 = MSAClientTraceTelemetry::Provider();
      if ( *(_DWORD *)v4 > 2u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5, v4) )
      {
        v7 = (char *)*((_QWORD *)a2 + 15);
        v8 = a1[34];
        v17 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(v29) = a2[26];
        v19 = (char *)*((_QWORD *)a2 + 12);
        v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v30 = a2[20];
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v31 = a2[8];
        v22 = (char *)*((_QWORD *)a2 + 3);
        v32 = *a2;
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v15 = a2[16];
        v24 = (char *)*((_QWORD *)a2 + 7);
        v16 = a2[2];
        v18 = v7;
        v25 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)word_18001BBA2,
          v8 + 8,
          v6,
          (__int64)&v25,
          (__int64)&v16,
          (const unsigned __int16 **)&v24,
          (__int64)&v15,
          &v23,
          (__int64)&v32,
          &v22,
          (__int64)&v31,
          &v21,
          (__int64)&v30,
          &v20,
          &v19,
          (__int64)&v29,
          &v17,
          &v18);
      }
    }
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v29);
  v12 = (_DWORD *)a1[34];
  v13 = a2[2];
  if ( v13 != v12[22] && (v13 != v12[18] || (int)v12[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v12 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
  return 1;
}

```

## disassembly

```asm
0x18000cae0  push    rbp
0x18000cae2  push    rbx
0x18000cae3  push    rdi
0x18000cae4  lea     rbp, [rsp+10h]
0x18000cae9  sub     rsp, 120h
0x18000caf0  test    byte ptr [rdx+4], 2
0x18000caf4  mov     rbx, rdx
0x18000caf7  mov     rdi, rcx
0x18000cafa  jnz     loc_18000CDC4
0x18000cb00  mov     rax, [rcx]
0x18000cb03  mov     edx, [rdx+10h]
0x18000cb06  mov     rax, [rax+10h]
0x18000cb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb0f  test    al, al
0x18000cb11  jnz     loc_18000CC61
0x18000cb17  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000cb1c  mov     r9, rax
0x18000cb1f  mov     ecx, [rax]
0x18000cb21  cmp     ecx, 2
0x18000cb24  jbe     loc_18000CDC4
0x18000cb2a  mov     rdx, 200000000000h
0x18000cb34  mov     rcx, rax
0x18000cb37  call    _tlgKeywordOn
0x18000cb3c  test    al, al
0x18000cb3e  jz      loc_18000CDC4
0x18000cb44  mov     rax, [rbx+70h]
0x18000cb48  lea     rdx, word_18001BBA2
0x18000cb4f  mov     rcx, [rbx+78h]
0x18000cb53  mov     r8, [rdi+110h]
0x18000cb5a  mov     [rbp+var_78], rax
0x18000cb5e  add     r8, 8
0x18000cb62  mov     eax, [rbx+68h]
0x18000cb65  mov     dword ptr [rbp+arg_0], eax
0x18000cb68  mov     rax, [rbx+60h]
0x18000cb6c  mov     [rbp+var_68], rax
0x18000cb70  mov     rax, [rbx+58h]
0x18000cb74  mov     [rbp+var_60], rax
0x18000cb78  mov     eax, [rbx+50h]
0x18000cb7b  mov     [rbp+arg_8], eax
0x18000cb7e  mov     rax, [rbx+48h]
0x18000cb82  mov     [rbp+var_58], rax
0x18000cb86  mov     eax, [rbx+20h]
0x18000cb89  mov     [rbp+arg_10], eax
0x18000cb8c  mov     rax, [rbx+18h]
0x18000cb90  mov     [rbp+var_50], rax
0x18000cb94  mov     eax, [rbx]
0x18000cb96  mov     [rbp+arg_18], eax
0x18000cb99  mov     rax, [rbx+80h]
0x18000cba0  mov     [rbp+var_48], rax
0x18000cba4  mov     eax, [rbx+40h]
0x18000cba7  mov     [rbp+var_80], eax
0x18000cbaa  mov     rax, [rbx+38h]
0x18000cbae  mov     [rbp+var_40], rax
0x18000cbb2  mov     eax, [rbx+8]
0x18000cbb5  mov     [rbp+var_7C], eax
0x18000cbb8  lea     rax, [rbp+var_70]
0x18000cbbc  mov     [rsp+130h+var_A0], rax
0x18000cbc4  lea     rax, [rbp+var_78]
0x18000cbc8  mov     [rsp+130h+var_A8], rax
0x18000cbd0  lea     rax, [rbp+arg_0]
0x18000cbd4  mov     [rsp+130h+var_B0], rax
0x18000cbdc  lea     rax, [rbp+var_68]
0x18000cbe0  mov     [rsp+130h+var_B8], rax
0x18000cbe5  lea     rax, [rbp+var_60]
0x18000cbe9  mov     [rsp+130h+var_C0], rax
0x18000cbee  lea     rax, [rbp+arg_8]
0x18000cbf2  mov     [rsp+130h+var_C8], rax
0x18000cbf7  lea     rax, [rbp+var_58]
0x18000cbfb  mov     [rsp+130h+var_D0], rax
0x18000cc00  lea     rax, [rbp+arg_10]
0x18000cc04  mov     [rsp+130h+var_D8], rax
0x18000cc09  lea     rax, [rbp+var_50]
0x18000cc0d  mov     [rsp+130h+var_E0], rax
0x18000cc12  lea     rax, [rbp+arg_18]
0x18000cc16  mov     [rsp+130h+var_E8], rax
0x18000cc1b  lea     rax, [rbp+var_48]
0x18000cc1f  mov     [rsp+130h+var_F0], rax
0x18000cc24  lea     rax, [rbp+var_80]
0x18000cc28  mov     [rsp+130h+var_F8], rax
0x18000cc2d  lea     rax, [rbp+var_40]
0x18000cc31  mov     [rsp+130h+var_100], rax
0x18000cc36  lea     rax, [rbp+var_7C]
0x18000cc3a  mov     [rsp+130h+var_108], rax
0x18000cc3f  lea     rax, [rbp+var_38]
0x18000cc43  mov     [rbp+var_70], rcx
0x18000cc47  mov     rcx, r9
0x18000cc4a  mov     [rsp+130h+var_110], rax
0x18000cc4f  mov     [rbp+var_38], 1000000h
0x18000cc57  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000cc5c  jmp     loc_18000CDC4
0x18000cc61  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000cc66  mov     r9, rax
0x18000cc69  mov     ecx, [rax]
0x18000cc6b  cmp     ecx, 2
0x18000cc6e  jbe     loc_18000CDC4
0x18000cc74  mov     eax, [rbx+68h]
0x18000cc77  lea     rdx, byte_18001BD07
0x18000cc7e  mov     rcx, [rbx+30h]
0x18000cc82  mov     r8, [rdi+110h]
0x18000cc89  mov     [rbp+arg_10], eax
0x18000cc8c  add     r8, 8
0x18000cc90  mov     rax, [rbx+60h]
0x18000cc94  mov     [rbp+var_50], rax
0x18000cc98  mov     rax, [rbx+58h]
0x18000cc9c  mov     [rbp+var_58], rax
0x18000cca0  mov     eax, [rbx+50h]
0x18000cca3  mov     [rbp+arg_18], eax
0x18000cca6  mov     rax, [rbx+48h]
0x18000ccaa  mov     [rbp+var_60], rax
0x18000ccae  mov     eax, [rbx+20h]
0x18000ccb1  mov     [rbp+var_7C], eax
0x18000ccb4  mov     rax, [rbx+18h]
0x18000ccb8  mov     [rbp+var_68], rax
0x18000ccbc  mov     eax, [rbx]
0x18000ccbe  mov     [rbp+var_80], eax
0x18000ccc1  mov     rax, [rbx+80h]
0x18000ccc8  mov     [rbp+var_30], rax
0x18000cccc  mov     eax, [rbx+40h]
0x18000cccf  mov     dword ptr [rbp+var_78], eax
0x18000ccd2  mov     rax, [rbx+38h]
0x18000ccd6  mov     [rbp+var_28], rax
0x18000ccda  mov     eax, [rbx+8]
0x18000ccdd  mov     dword ptr [rbp+var_70], eax
0x18000cce0  lea     rax, [rbp+var_38]
0x18000cce4  mov     [rsp+130h+var_88], rax
0x18000ccec  lea     rax, [rbp+arg_0]
0x18000ccf0  mov     [rsp+130h+var_90], rax
0x18000ccf8  lea     rax, [rbp+arg_8]
0x18000ccfc  mov     [rsp+130h+var_98], rax
0x18000cd04  lea     rax, [rbp+var_40]
0x18000cd08  mov     [rsp+130h+var_A0], rax
0x18000cd10  lea     rax, [rbp+var_48]
0x18000cd14  mov     [rsp+130h+var_A8], rax
0x18000cd1c  lea     rax, [rbp+arg_10]
0x18000cd20  mov     [rsp+130h+var_B0], rax
0x18000cd28  lea     rax, [rbp+var_50]
0x18000cd2c  mov     [rsp+130h+var_B8], rax
0x18000cd31  lea     rax, [rbp+var_58]
0x18000cd35  mov     [rsp+130h+var_C0], rax
0x18000cd3a  lea     rax, [rbp+arg_18]
0x18000cd3e  mov     [rsp+130h+var_C8], rax
0x18000cd43  lea     rax, [rbp+var_60]
0x18000cd47  mov     [rsp+130h+var_D0], rax
0x18000cd4c  lea     rax, [rbp+var_7C]
0x18000cd50  mov     [rsp+130h+var_D8], rax
0x18000cd55  lea     rax, [rbp+var_68]
0x18000cd59  mov     [rsp+130h+var_E0], rax
0x18000cd5e  lea     rax, [rbp+var_80]
0x18000cd62  mov     [rsp+130h+var_E8], rax
0x18000cd67  lea     rax, [rbp+var_30]
0x18000cd6b  mov     [rsp+130h+var_F0], rax
0x18000cd70  lea     rax, [rbp+var_78]
0x18000cd74  mov     [rsp+130h+var_F8], rax
0x18000cd79  lea     rax, [rbp+var_28]
0x18000cd7d  mov     [rbp+var_38], rcx
0x18000cd81  mov     ecx, [rbx+44h]
0x18000cd84  mov     dword ptr [rbp+arg_0], ecx
0x18000cd87  mov     ecx, [rbx+10h]
0x18000cd8a  mov     [rsp+130h+var_100], rax
0x18000cd8f  lea     rax, [rbp+var_70]
0x18000cd93  mov     [rbp+arg_8], ecx
0x18000cd96  mov     rcx, [rbx+78h]
0x18000cd9a  mov     [rbp+var_40], rcx
0x18000cd9e  mov     rcx, [rbx+70h]
0x18000cda2  mov     [rsp+130h+var_108], rax
0x18000cda7  lea     rax, [rbp+var_20]
0x18000cdab  mov     [rbp+var_48], rcx
0x18000cdaf  mov     rcx, r9
0x18000cdb2  mov     [rsp+130h+var_110], rax
0x18000cdb7  mov     [rbp+var_20], 1000000h
0x18000cdbf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000cdc4  lea     rdx, [rbp+arg_0]
0x18000cdc8  mov     rcx, rdi
0x18000cdcb  call    ?LockExclusive@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cdd0  mov     rax, [rdi+110h]
0x18000cdd7  mov     edx, [rbx+8]
0x18000cdda  lea     rcx, [rax+50h]; this
0x18000cdde  cmp     edx, [rcx+8]
0x18000cde1  jz      short loc_18000CDF6
0x18000cde3  cmp     edx, [rax+48h]
0x18000cde6  jnz     short loc_18000CDEE
0x18000cde8  cmp     dword ptr [rax+48h], 0
0x18000cdec  jl      short loc_18000CDF6
0x18000cdee  mov     rdx, rbx; struct wil::FailureInfo *
0x18000cdf1  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18000cdf6  lea     rcx, [rbp+arg_0]
0x18000cdfa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000cdff  mov     al, 1
0x18000ce01  add     rsp, 120h
0x18000ce08  pop     rdi
0x18000ce09  pop     rbx
0x18000ce0a  pop     rbp
0x18000ce0b  retn
```
