# TraceLog::Providers::ScreenTime::RequestLocalTimeException::StopActivity(void)

- ea: `0x140055a90`
- end: `0x140055d20`
- name: `?StopActivity@RequestLocalTimeException@ScreenTime@Providers@TraceLog@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(TraceLog::Providers::ScreenTime::RequestLocalTimeException *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x1400544c4`
- `0x140055a90`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140055aea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140055c7d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140055aea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140055c7d`
- `KERNEL32!GetCurrentThreadId` at `0x140055cb4`
- `KERNEL32!GetCurrentThreadId` at `0x140055cb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TraceLog::Providers::ScreenTime::RequestLocalTimeException::StopActivity(
        TraceLog::Providers::ScreenTime::RequestLocalTimeException *this)
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
          (__int64)&unk_1400D6A10,
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
          (__int64)&dword_1400D6994,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((TraceLog::Providers::ScreenTime::RequestLocalTimeException *)((char *)this + 288));
}

```

## disassembly

```asm
0x140055a90  push    rbp
0x140055a92  push    rbx
0x140055a93  push    rdi
0x140055a94  lea     rbp, [rsp-47h]
0x140055a99  sub     rsp, 100h
0x140055aa0  mov     rbx, rcx
0x140055aa3  mov     rdi, [rcx+110h]
0x140055aaa  mov     eax, [rdi+48h]
0x140055aad  test    eax, eax
0x140055aaf  jns     loc_140055C5E
0x140055ab5  add     rdi, 50h ; 'P'
0x140055ab9  cmp     eax, [rdi+8]
0x140055abc  jnz     loc_140055C5E
0x140055ac2  test    rdi, rdi
0x140055ac5  jz      loc_140055C5E
0x140055acb  lea     rdx, [rbp+57h+SRWLock]
0x140055acf  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140055ad4  mov     rax, [rbx+110h]
0x140055adb  mov     dword ptr [rax], 2
0x140055ae1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140055ae5  test    rcx, rcx
0x140055ae8  jz      short loc_140055AF0
0x140055aea  call    cs:__imp_ReleaseSRWLockExclusive
0x140055af0  call    ?Provider@ScreenTime@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::ScreenTime::Provider(void)
0x140055af5  mov     r9, rax
0x140055af8  mov     ecx, [rax]
0x140055afa  cmp     ecx, 5
0x140055afd  jbe     loc_140055D02
0x140055b03  mov     rax, [rax+18h]
0x140055b07  mov     rcx, [r9+10h]
0x140055b0b  mov     rdx, 200000000000h
0x140055b15  test    rdx, rcx
0x140055b18  jz      loc_140055D02
0x140055b1e  mov     rcx, rax
0x140055b21  and     rcx, rdx
0x140055b24  cmp     rcx, rax
0x140055b27  jnz     loc_140055D02
0x140055b2d  mov     rax, [rdi+78h]
0x140055b31  mov     [rbp+57h+var_68], rax
0x140055b35  mov     rax, [rdi+70h]
0x140055b39  mov     [rbp+57h+var_60], rax
0x140055b3d  mov     eax, [rdi+68h]
0x140055b40  mov     dword ptr [rbp+57h+SRWLock], eax
0x140055b43  mov     rax, [rdi+60h]
0x140055b47  mov     [rbp+57h+var_58], rax
0x140055b4b  mov     rax, [rdi+58h]
0x140055b4f  mov     [rbp+57h+var_50], rax
0x140055b53  mov     eax, [rdi+50h]
0x140055b56  mov     [rbp+57h+arg_8], eax
0x140055b59  mov     rax, [rdi+48h]
0x140055b5d  mov     [rbp+57h+var_48], rax
0x140055b61  mov     eax, [rdi+20h]
0x140055b64  mov     dword ptr [rbp+57h+arg_10], eax
0x140055b67  mov     rax, [rdi+18h]
0x140055b6b  mov     [rbp+57h+var_40], rax
0x140055b6f  mov     eax, [rdi]
0x140055b71  mov     [rbp+57h+arg_18], eax
0x140055b74  mov     rax, [rdi+80h]
0x140055b7b  mov     [rbp+57h+var_38], rax
0x140055b7f  mov     eax, [rdi+40h]
0x140055b82  mov     [rbp+57h+var_70], eax
0x140055b85  mov     rax, [rdi+38h]
0x140055b89  mov     [rbp+57h+var_30], rax
0x140055b8d  mov     eax, [rdi+8]
0x140055b90  mov     [rbp+57h+var_6C], eax
0x140055b93  mov     [rbp+57h+var_28], 1000000h
0x140055b9b  mov     [rbp+57h+var_20], 0
0x140055ba3  mov     r8, [rbx+110h]
0x140055baa  add     r8, 8
0x140055bae  lea     rax, [rbp+57h+var_68]
0x140055bb2  mov     [rsp+110h+var_78], rax
0x140055bba  lea     rax, [rbp+57h+var_60]
0x140055bbe  mov     [rsp+110h+var_80], rax
0x140055bc6  lea     rax, [rbp+57h+SRWLock]
0x140055bca  mov     [rsp+110h+var_88], rax
0x140055bd2  lea     rax, [rbp+57h+var_58]
0x140055bd6  mov     [rsp+110h+var_90], rax
0x140055bde  lea     rax, [rbp+57h+var_50]
0x140055be2  mov     [rsp+110h+var_98], rax
0x140055be7  lea     rax, [rbp+57h+arg_8]
0x140055beb  mov     [rsp+110h+var_A0], rax
0x140055bf0  lea     rax, [rbp+57h+var_48]
0x140055bf4  mov     [rsp+110h+var_A8], rax
0x140055bf9  lea     rax, [rbp+57h+arg_10]
0x140055bfd  mov     [rsp+110h+var_B0], rax
0x140055c02  lea     rax, [rbp+57h+var_40]
0x140055c06  mov     [rsp+110h+var_B8], rax
0x140055c0b  lea     rax, [rbp+57h+arg_18]
0x140055c0f  mov     [rsp+110h+var_C0], rax
0x140055c14  lea     rax, [rbp+57h+var_38]
0x140055c18  mov     [rsp+110h+var_C8], rax
0x140055c1d  lea     rax, [rbp+57h+var_70]
0x140055c21  mov     [rsp+110h+var_D0], rax
0x140055c26  lea     rax, [rbp+57h+var_30]
0x140055c2a  mov     [rsp+110h+var_D8], rax
0x140055c2f  lea     rax, [rbp+57h+var_6C]
0x140055c33  mov     [rsp+110h+var_E0], rax
0x140055c38  lea     rax, [rbp+57h+var_28]
0x140055c3c  mov     [rsp+110h+var_E8], rax
0x140055c41  lea     rax, [rbp+57h+var_20]
0x140055c45  mov     [rsp+110h+var_F0], rax
0x140055c4a  lea     rdx, unk_1400D6A10
0x140055c51  mov     rcx, r9
0x140055c54  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140055c59  jmp     loc_140055D02
0x140055c5e  lea     rdx, [rbp+57h+SRWLock]
0x140055c62  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140055c67  mov     rax, [rbx+110h]
0x140055c6e  mov     dword ptr [rax], 2
0x140055c74  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140055c78  test    rcx, rcx
0x140055c7b  jz      short loc_140055C83
0x140055c7d  call    cs:__imp_ReleaseSRWLockExclusive
0x140055c83  call    ?Provider@ScreenTime@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::ScreenTime::Provider(void)
0x140055c88  mov     rdi, rax
0x140055c8b  mov     ecx, [rax]
0x140055c8d  cmp     ecx, 5
0x140055c90  jbe     short loc_140055D02
0x140055c92  mov     rax, [rax+18h]
0x140055c96  mov     rcx, [rdi+10h]
0x140055c9a  mov     rdx, 200000000000h
0x140055ca4  test    rdx, rcx
0x140055ca7  jz      short loc_140055D02
0x140055ca9  mov     rcx, rax
0x140055cac  and     rcx, rdx
0x140055caf  cmp     rcx, rax
0x140055cb2  jnz     short loc_140055D02
0x140055cb4  call    cs:__imp_GetCurrentThreadId
0x140055cba  mov     dword ptr [rbp+57h+SRWLock], eax
0x140055cbd  mov     r8, [rbx+110h]
0x140055cc4  mov     eax, [r8+48h]
0x140055cc8  mov     [rbp+57h+arg_8], eax
0x140055ccb  mov     [rbp+57h+arg_10], 0
0x140055cd3  add     r8, 8
0x140055cd7  lea     rax, [rbp+57h+SRWLock]
0x140055cdb  mov     [rsp+110h+var_E0], rax
0x140055ce0  lea     rax, [rbp+57h+arg_8]
0x140055ce4  mov     [rsp+110h+var_E8], rax
0x140055ce9  lea     rax, [rbp+57h+arg_10]
0x140055ced  mov     [rsp+110h+var_F0], rax
0x140055cf2  lea     rdx, dword_1400D6994
0x140055cf9  mov     rcx, rdi
0x140055cfc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140055d01  nop
0x140055d02  lea     rcx, [rbx+120h]; this
0x140055d09  cmp     dword ptr [rcx+18h], 0
0x140055d0d  jz      short loc_140055D15
0x140055d0f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140055d14  nop
0x140055d15  add     rsp, 100h
0x140055d1c  pop     rdi
0x140055d1d  pop     rbx
0x140055d1e  pop     rbp
0x140055d1f  retn
```
