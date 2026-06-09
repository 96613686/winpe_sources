# wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x180017880`
- end: `0x180017bc6`
- name: `?NotifyFailure@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `838`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800013cc`
- `0x180001670`
- `0x180001acc`
- `0x180005cb8`
- `0x180007fd4`
- `0x1800097d4`
- `0x180017880`
- `0x180017bd8`
- `0x18001f010`

## pseudocode

```c
char __fastcall wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  const WCHAR *v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  const unsigned __int16 *v12; // rcx
  __int64 v13; // r8
  _DWORD *v14; // rax
  int v15; // edx
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v19; // [rsp+B8h] [rbp-78h] BYREF
  const WCHAR *v20; // [rsp+C0h] [rbp-70h] BYREF
  const WCHAR *v21; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v22; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp-58h] BYREF
  const WCHAR *v24; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v25; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+108h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+110h] [rbp-20h] BYREF
  RTL_SRWLOCK *v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+148h] [rbp+18h] BYREF
  int v33; // [rsp+150h] [rbp+20h] BYREF
  int v34; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v9 = CoCreateInstanceAsSystemLogging::Provider();
      if ( *(_DWORD *)v9 > 2u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL, v10) )
      {
        LODWORD(v31) = a2[17];
        v32 = a2[4];
        v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 15);
        v13 = a1[34];
        v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v33 = a2[26];
        v24 = (const WCHAR *)*((_QWORD *)a2 + 12);
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v34 = a2[20];
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v18 = a2[8];
        v21 = (const WCHAR *)*((_QWORD *)a2 + 3);
        v17 = *a2;
        v28 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v19) = a2[16];
        v29 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v20) = a2[2];
        v27 = (__int64)v12;
        v30[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (__int64)byte_180024EBB,
          v13 + 8,
          v11,
          (__int64)v30,
          (__int64)&v20,
          &v29,
          (__int64)&v19,
          &v28,
          (__int64)&v17,
          &v21,
          (__int64)&v18,
          &v22,
          (__int64)&v34,
          &v23,
          &v24,
          (__int64)&v33,
          &v25,
          &v26,
          (__int64)&v32,
          (__int64)&v31,
          (const unsigned __int16 **)&v27);
      }
    }
    else
    {
      v4 = CoCreateInstanceAsSystemLogging::Provider();
      if ( *(_DWORD *)v4 > 2u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
      {
        v7 = (const WCHAR *)*((_QWORD *)a2 + 15);
        v8 = a1[34];
        v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(v31) = a2[26];
        v21 = (const WCHAR *)*((_QWORD *)a2 + 12);
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v32 = a2[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v33 = a2[8];
        v24 = (const WCHAR *)*((_QWORD *)a2 + 3);
        v34 = *a2;
        v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v17 = a2[16];
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        v18 = a2[2];
        v20 = v7;
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)byte_180024FF3,
          v8 + 8,
          v6,
          (__int64)&v27,
          (__int64)&v18,
          &v26,
          (__int64)&v17,
          &v25,
          (__int64)&v34,
          &v24,
          (__int64)&v33,
          &v23,
          (__int64)&v32,
          &v22,
          &v21,
          (__int64)&v31,
          &v19,
          &v20);
      }
    }
  }
  wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v31);
  v14 = (_DWORD *)a1[34];
  v15 = a2[2];
  if ( v15 != v14[22] && (v15 != v14[18] || (int)v14[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v14 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v31);
  return 1;
}

```

## disassembly

```asm
0x180017880  push    rbp
0x180017882  push    rbx
0x180017883  push    rdi
0x180017884  lea     rbp, [rsp+10h]
0x180017889  sub     rsp, 120h
0x180017890  test    byte ptr [rdx+4], 2
0x180017894  mov     rbx, rdx
0x180017897  mov     rdi, rcx
0x18001789a  jnz     loc_180017B7E
0x1800178a0  mov     rax, [rcx]
0x1800178a3  mov     edx, [rdx+10h]
0x1800178a6  mov     rax, [rax+10h]
0x1800178aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178af  test    al, al
0x1800178b1  jnz     loc_180017A01
0x1800178b7  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x1800178bc  mov     r9, rax
0x1800178bf  mov     ecx, [rax]
0x1800178c1  cmp     ecx, 2
0x1800178c4  jbe     loc_180017B7E
0x1800178ca  mov     rdx, 200000000000h
0x1800178d4  mov     rcx, rax
0x1800178d7  call    _tlgKeywordOn
0x1800178dc  test    al, al
0x1800178de  jz      loc_180017B7E
0x1800178e4  mov     rax, [rbx+70h]
0x1800178e8  lea     rdx, byte_180024FF3
0x1800178ef  mov     rcx, [rbx+78h]
0x1800178f3  mov     r8, [rdi+110h]
0x1800178fa  mov     [rbp+var_78], rax
0x1800178fe  add     r8, 8
0x180017902  mov     eax, [rbx+68h]
0x180017905  mov     dword ptr [rbp+arg_0], eax
0x180017908  mov     rax, [rbx+60h]
0x18001790c  mov     [rbp+var_68], rax
0x180017910  mov     rax, [rbx+58h]
0x180017914  mov     [rbp+var_60], rax
0x180017918  mov     eax, [rbx+50h]
0x18001791b  mov     [rbp+arg_8], eax
0x18001791e  mov     rax, [rbx+48h]
0x180017922  mov     [rbp+var_58], rax
0x180017926  mov     eax, [rbx+20h]
0x180017929  mov     [rbp+arg_10], eax
0x18001792c  mov     rax, [rbx+18h]
0x180017930  mov     [rbp+var_50], rax
0x180017934  mov     eax, [rbx]
0x180017936  mov     [rbp+arg_18], eax
0x180017939  mov     rax, [rbx+80h]
0x180017940  mov     [rbp+var_48], rax
0x180017944  mov     eax, [rbx+40h]
0x180017947  mov     [rbp+var_80], eax
0x18001794a  mov     rax, [rbx+38h]
0x18001794e  mov     [rbp+var_40], rax
0x180017952  mov     eax, [rbx+8]
0x180017955  mov     [rbp+var_7C], eax
0x180017958  lea     rax, [rbp+var_70]
0x18001795c  mov     [rsp+130h+var_A0], rax
0x180017964  lea     rax, [rbp+var_78]
0x180017968  mov     [rsp+130h+var_A8], rax
0x180017970  lea     rax, [rbp+arg_0]
0x180017974  mov     [rsp+130h+var_B0], rax
0x18001797c  lea     rax, [rbp+var_68]
0x180017980  mov     [rsp+130h+var_B8], rax
0x180017985  lea     rax, [rbp+var_60]
0x180017989  mov     [rsp+130h+var_C0], rax
0x18001798e  lea     rax, [rbp+arg_8]
0x180017992  mov     [rsp+130h+var_C8], rax
0x180017997  lea     rax, [rbp+var_58]
0x18001799b  mov     [rsp+130h+var_D0], rax
0x1800179a0  lea     rax, [rbp+arg_10]
0x1800179a4  mov     [rsp+130h+var_D8], rax
0x1800179a9  lea     rax, [rbp+var_50]
0x1800179ad  mov     [rsp+130h+var_E0], rax
0x1800179b2  lea     rax, [rbp+arg_18]
0x1800179b6  mov     [rsp+130h+var_E8], rax
0x1800179bb  lea     rax, [rbp+var_48]
0x1800179bf  mov     [rsp+130h+var_F0], rax
0x1800179c4  lea     rax, [rbp+var_80]
0x1800179c8  mov     [rsp+130h+var_F8], rax
0x1800179cd  lea     rax, [rbp+var_40]
0x1800179d1  mov     [rsp+130h+var_100], rax
0x1800179d6  lea     rax, [rbp+var_7C]
0x1800179da  mov     [rsp+130h+var_108], rax
0x1800179df  lea     rax, [rbp+var_38]
0x1800179e3  mov     [rbp+var_70], rcx
0x1800179e7  mov     rcx, r9
0x1800179ea  mov     [rsp+130h+var_110], rax
0x1800179ef  mov     [rbp+var_38], 1000000h
0x1800179f7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800179fc  jmp     loc_180017B7E
0x180017a01  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x180017a06  mov     r9, rax
0x180017a09  mov     ecx, [rax]
0x180017a0b  cmp     ecx, 2
0x180017a0e  jbe     loc_180017B7E
0x180017a14  mov     rdx, 200000000000h
0x180017a1e  mov     rcx, rax
0x180017a21  call    _tlgKeywordOn
0x180017a26  test    al, al
0x180017a28  jz      loc_180017B7E
0x180017a2e  mov     eax, [rbx+44h]
0x180017a31  lea     rdx, byte_180024EBB
0x180017a38  mov     dword ptr [rbp+arg_0], eax
0x180017a3b  mov     eax, [rbx+10h]
0x180017a3e  mov     [rbp+arg_8], eax
0x180017a41  mov     rax, [rbx+78h]
0x180017a45  mov     rcx, [rbx+30h]
0x180017a49  mov     [rbp+var_40], rax
0x180017a4d  mov     rax, [rbx+70h]
0x180017a51  mov     r8, [rdi+110h]
0x180017a58  mov     [rbp+var_48], rax
0x180017a5c  add     r8, 8
0x180017a60  mov     eax, [rbx+68h]
0x180017a63  mov     [rbp+arg_10], eax
0x180017a66  mov     rax, [rbx+60h]
0x180017a6a  mov     [rbp+var_50], rax
0x180017a6e  mov     rax, [rbx+58h]
0x180017a72  mov     [rbp+var_58], rax
0x180017a76  mov     eax, [rbx+50h]
0x180017a79  mov     [rbp+arg_18], eax
0x180017a7c  mov     rax, [rbx+48h]
0x180017a80  mov     [rbp+var_60], rax
0x180017a84  mov     eax, [rbx+20h]
0x180017a87  mov     [rbp+var_7C], eax
0x180017a8a  mov     rax, [rbx+18h]
0x180017a8e  mov     [rbp+var_68], rax
0x180017a92  mov     eax, [rbx]
0x180017a94  mov     [rbp+var_80], eax
0x180017a97  mov     rax, [rbx+80h]
0x180017a9e  mov     [rbp+var_30], rax
0x180017aa2  mov     eax, [rbx+40h]
0x180017aa5  mov     dword ptr [rbp+var_78], eax
0x180017aa8  mov     rax, [rbx+38h]
0x180017aac  mov     [rbp+var_28], rax
0x180017ab0  mov     eax, [rbx+8]
0x180017ab3  mov     dword ptr [rbp+var_70], eax
0x180017ab6  lea     rax, [rbp+var_38]
0x180017aba  mov     [rsp+130h+var_88], rax
0x180017ac2  lea     rax, [rbp+arg_0]
0x180017ac6  mov     [rsp+130h+var_90], rax
0x180017ace  lea     rax, [rbp+arg_8]
0x180017ad2  mov     [rsp+130h+var_98], rax
0x180017ada  lea     rax, [rbp+var_40]
0x180017ade  mov     [rsp+130h+var_A0], rax
0x180017ae6  lea     rax, [rbp+var_48]
0x180017aea  mov     [rsp+130h+var_A8], rax
0x180017af2  lea     rax, [rbp+arg_10]
0x180017af6  mov     [rsp+130h+var_B0], rax
0x180017afe  lea     rax, [rbp+var_50]
0x180017b02  mov     [rsp+130h+var_B8], rax
0x180017b07  lea     rax, [rbp+var_58]
0x180017b0b  mov     [rsp+130h+var_C0], rax
0x180017b10  lea     rax, [rbp+arg_18]
0x180017b14  mov     [rsp+130h+var_C8], rax
0x180017b19  lea     rax, [rbp+var_60]
0x180017b1d  mov     [rsp+130h+var_D0], rax
0x180017b22  lea     rax, [rbp+var_7C]
0x180017b26  mov     [rsp+130h+var_D8], rax
0x180017b2b  lea     rax, [rbp+var_68]
0x180017b2f  mov     [rsp+130h+var_E0], rax
0x180017b34  lea     rax, [rbp+var_80]
0x180017b38  mov     [rsp+130h+var_E8], rax
0x180017b3d  lea     rax, [rbp+var_30]
0x180017b41  mov     [rsp+130h+var_F0], rax
0x180017b46  lea     rax, [rbp+var_78]
0x180017b4a  mov     [rsp+130h+var_F8], rax
0x180017b4f  lea     rax, [rbp+var_28]
0x180017b53  mov     [rsp+130h+var_100], rax
0x180017b58  lea     rax, [rbp+var_70]
0x180017b5c  mov     [rsp+130h+var_108], rax
0x180017b61  lea     rax, [rbp+var_20]
0x180017b65  mov     [rbp+var_38], rcx
0x180017b69  mov     rcx, r9
0x180017b6c  mov     [rsp+130h+var_110], rax
0x180017b71  mov     [rbp+var_20], 1000000h
0x180017b79  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180017b7e  lea     rdx, [rbp+arg_0]
0x180017b82  mov     rcx, rdi
0x180017b85  call    ?LockExclusive@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017b8a  mov     rax, [rdi+110h]
0x180017b91  mov     edx, [rbx+8]
0x180017b94  lea     rcx, [rax+50h]; this
0x180017b98  cmp     edx, [rcx+8]
0x180017b9b  jz      short loc_180017BB0
0x180017b9d  cmp     edx, [rax+48h]
0x180017ba0  jnz     short loc_180017BA8
0x180017ba2  cmp     dword ptr [rax+48h], 0
0x180017ba6  jl      short loc_180017BB0
0x180017ba8  mov     rdx, rbx; struct wil::FailureInfo *
0x180017bab  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x180017bb0  lea     rcx, [rbp+arg_0]
0x180017bb4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017bb9  mov     al, 1
0x180017bbb  add     rsp, 120h
0x180017bc2  pop     rdi
0x180017bc3  pop     rbx
0x180017bc4  pop     rbp
0x180017bc5  retn
```
