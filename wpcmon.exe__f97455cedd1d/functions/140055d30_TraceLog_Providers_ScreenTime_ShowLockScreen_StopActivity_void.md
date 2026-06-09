# TraceLog::Providers::ScreenTime::ShowLockScreen::StopActivity(void)

- ea: `0x140055d30`
- end: `0x140055fc0`
- name: `?StopActivity@ShowLockScreen@ScreenTime@Providers@TraceLog@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(TraceLog::Providers::ScreenTime::ShowLockScreen *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x1400544c4`
- `0x140055d30`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140055d8a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140055f1d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140055d8a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140055f1d`
- `KERNEL32!GetCurrentThreadId` at `0x140055f54`
- `KERNEL32!GetCurrentThreadId` at `0x140055f54`

## pseudocode

```c
void __fastcall TraceLog::Providers::ScreenTime::ShowLockScreen::StopActivity(
        TraceLog::Providers::ScreenTime::ShowLockScreen *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v15; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v16; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v17; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v18; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v19; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v20; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = TraceLog::Providers::ScreenTime::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0 && (v7 & 0x200000000000LL) == v7 )
      {
        v15 = (const WCHAR *)*((_QWORD *)v4 + 15);
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v17 = (const WCHAR *)*((_QWORD *)v4 + 12);
        v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v26 = v4[20];
        v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v27) = v4[8];
        v20 = (const WCHAR *)*((_QWORD *)v4 + 3);
        v28 = *v4;
        v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v13 = v4[16];
        v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v14 = v4[2];
        v23 = 0x1000000;
        v24[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)&byte_1400D6DFF,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          &v22,
          (__int64)&v13,
          &v21,
          (__int64)&v28,
          &v20,
          (__int64)&v27,
          &v19,
          (__int64)&v26,
          &v18,
          &v17,
          (__int64)&SRWLock,
          &v16,
          &v15);
      }
    }
  }
  else
  {
    wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = TraceLog::Providers::ScreenTime::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0 && (v10 & 0x200000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v26 = *(_DWORD *)(v11 + 72);
        v27 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (__int64)word_1400D6D6A,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((TraceLog::Providers::ScreenTime::ShowLockScreen *)((char *)this + 288));
}

```

## disassembly

```asm
0x140055d30  push    rbp
0x140055d32  push    rbx
0x140055d33  push    rdi
0x140055d34  lea     rbp, [rsp-47h]
0x140055d39  sub     rsp, 100h
0x140055d40  mov     rbx, rcx
0x140055d43  mov     rdi, [rcx+110h]
0x140055d4a  mov     eax, [rdi+48h]
0x140055d4d  test    eax, eax
0x140055d4f  jns     loc_140055EFE
0x140055d55  add     rdi, 50h ; 'P'
0x140055d59  cmp     eax, [rdi+8]
0x140055d5c  jnz     loc_140055EFE
0x140055d62  test    rdi, rdi
0x140055d65  jz      loc_140055EFE
0x140055d6b  lea     rdx, [rbp+57h+SRWLock]
0x140055d6f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140055d74  mov     rax, [rbx+110h]
0x140055d7b  mov     dword ptr [rax], 2
0x140055d81  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140055d85  test    rcx, rcx
0x140055d88  jz      short loc_140055D90
0x140055d8a  call    cs:__imp_ReleaseSRWLockExclusive
0x140055d90  call    ?Provider@ScreenTime@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::ScreenTime::Provider(void)
0x140055d95  mov     r9, rax
0x140055d98  mov     ecx, [rax]
0x140055d9a  cmp     ecx, 5
0x140055d9d  jbe     loc_140055FA2
0x140055da3  mov     rax, [rax+18h]
0x140055da7  mov     rcx, [r9+10h]
0x140055dab  mov     rdx, 200000000000h
0x140055db5  test    rdx, rcx
0x140055db8  jz      loc_140055FA2
0x140055dbe  mov     rcx, rax
0x140055dc1  and     rcx, rdx
0x140055dc4  cmp     rcx, rax
0x140055dc7  jnz     loc_140055FA2
0x140055dcd  mov     rax, [rdi+78h]
0x140055dd1  mov     [rbp+57h+var_68], rax
0x140055dd5  mov     rax, [rdi+70h]
0x140055dd9  mov     [rbp+57h+var_60], rax
0x140055ddd  mov     eax, [rdi+68h]
0x140055de0  mov     dword ptr [rbp+57h+SRWLock], eax
0x140055de3  mov     rax, [rdi+60h]
0x140055de7  mov     [rbp+57h+var_58], rax
0x140055deb  mov     rax, [rdi+58h]
0x140055def  mov     [rbp+57h+var_50], rax
0x140055df3  mov     eax, [rdi+50h]
0x140055df6  mov     [rbp+57h+arg_8], eax
0x140055df9  mov     rax, [rdi+48h]
0x140055dfd  mov     [rbp+57h+var_48], rax
0x140055e01  mov     eax, [rdi+20h]
0x140055e04  mov     dword ptr [rbp+57h+arg_10], eax
0x140055e07  mov     rax, [rdi+18h]
0x140055e0b  mov     [rbp+57h+var_40], rax
0x140055e0f  mov     eax, [rdi]
0x140055e11  mov     [rbp+57h+arg_18], eax
0x140055e14  mov     rax, [rdi+80h]
0x140055e1b  mov     [rbp+57h+var_38], rax
0x140055e1f  mov     eax, [rdi+40h]
0x140055e22  mov     [rbp+57h+var_70], eax
0x140055e25  mov     rax, [rdi+38h]
0x140055e29  mov     [rbp+57h+var_30], rax
0x140055e2d  mov     eax, [rdi+8]
0x140055e30  mov     [rbp+57h+var_6C], eax
0x140055e33  mov     [rbp+57h+var_28], 1000000h
0x140055e3b  mov     [rbp+57h+var_20], 0
0x140055e43  mov     r8, [rbx+110h]
0x140055e4a  add     r8, 8
0x140055e4e  lea     rax, [rbp+57h+var_68]
0x140055e52  mov     [rsp+110h+var_78], rax
0x140055e5a  lea     rax, [rbp+57h+var_60]
0x140055e5e  mov     [rsp+110h+var_80], rax
0x140055e66  lea     rax, [rbp+57h+SRWLock]
0x140055e6a  mov     [rsp+110h+var_88], rax
0x140055e72  lea     rax, [rbp+57h+var_58]
0x140055e76  mov     [rsp+110h+var_90], rax
0x140055e7e  lea     rax, [rbp+57h+var_50]
0x140055e82  mov     [rsp+110h+var_98], rax
0x140055e87  lea     rax, [rbp+57h+arg_8]
0x140055e8b  mov     [rsp+110h+var_A0], rax
0x140055e90  lea     rax, [rbp+57h+var_48]
0x140055e94  mov     [rsp+110h+var_A8], rax
0x140055e99  lea     rax, [rbp+57h+arg_10]
0x140055e9d  mov     [rsp+110h+var_B0], rax
0x140055ea2  lea     rax, [rbp+57h+var_40]
0x140055ea6  mov     [rsp+110h+var_B8], rax
0x140055eab  lea     rax, [rbp+57h+arg_18]
0x140055eaf  mov     [rsp+110h+var_C0], rax
0x140055eb4  lea     rax, [rbp+57h+var_38]
0x140055eb8  mov     [rsp+110h+var_C8], rax
0x140055ebd  lea     rax, [rbp+57h+var_70]
0x140055ec1  mov     [rsp+110h+var_D0], rax
0x140055ec6  lea     rax, [rbp+57h+var_30]
0x140055eca  mov     [rsp+110h+var_D8], rax
0x140055ecf  lea     rax, [rbp+57h+var_6C]
0x140055ed3  mov     [rsp+110h+var_E0], rax
0x140055ed8  lea     rax, [rbp+57h+var_28]
0x140055edc  mov     [rsp+110h+var_E8], rax
0x140055ee1  lea     rax, [rbp+57h+var_20]
0x140055ee5  mov     [rsp+110h+var_F0], rax
0x140055eea  lea     rdx, byte_1400D6DFF
0x140055ef1  mov     rcx, r9
0x140055ef4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140055ef9  jmp     loc_140055FA2
0x140055efe  lea     rdx, [rbp+57h+SRWLock]
0x140055f02  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140055f07  mov     rax, [rbx+110h]
0x140055f0e  mov     dword ptr [rax], 2
0x140055f14  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140055f18  test    rcx, rcx
0x140055f1b  jz      short loc_140055F23
0x140055f1d  call    cs:__imp_ReleaseSRWLockExclusive
0x140055f23  call    ?Provider@ScreenTime@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::ScreenTime::Provider(void)
0x140055f28  mov     rdi, rax
0x140055f2b  mov     ecx, [rax]
0x140055f2d  cmp     ecx, 5
0x140055f30  jbe     short loc_140055FA2
0x140055f32  mov     rax, [rax+18h]
0x140055f36  mov     rcx, [rdi+10h]
0x140055f3a  mov     rdx, 200000000000h
0x140055f44  test    rdx, rcx
0x140055f47  jz      short loc_140055FA2
0x140055f49  mov     rcx, rax
0x140055f4c  and     rcx, rdx
0x140055f4f  cmp     rcx, rax
0x140055f52  jnz     short loc_140055FA2
0x140055f54  call    cs:__imp_GetCurrentThreadId
0x140055f5a  mov     dword ptr [rbp+57h+SRWLock], eax
0x140055f5d  mov     r8, [rbx+110h]
0x140055f64  mov     eax, [r8+48h]
0x140055f68  mov     [rbp+57h+arg_8], eax
0x140055f6b  mov     [rbp+57h+arg_10], 0
0x140055f73  add     r8, 8
0x140055f77  lea     rax, [rbp+57h+SRWLock]
0x140055f7b  mov     [rsp+110h+var_E0], rax
0x140055f80  lea     rax, [rbp+57h+arg_8]
0x140055f84  mov     [rsp+110h+var_E8], rax
0x140055f89  lea     rax, [rbp+57h+arg_10]
0x140055f8d  mov     [rsp+110h+var_F0], rax
0x140055f92  lea     rdx, word_1400D6D6A
0x140055f99  mov     rcx, rdi
0x140055f9c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140055fa1  nop
0x140055fa2  lea     rcx, [rbx+120h]; this
0x140055fa9  cmp     dword ptr [rcx+18h], 0
0x140055fad  jz      short loc_140055FB5
0x140055faf  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140055fb4  nop
0x140055fb5  add     rsp, 100h
0x140055fbc  pop     rdi
0x140055fbd  pop     rbx
0x140055fbe  pop     rbp
0x140055fbf  retn
```
