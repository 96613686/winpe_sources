# wpc::UI::Internal::UILogger::ShowSystemToast::StopActivity(void)

- ea: `0x14008b5d0`
- end: `0x14008b85e`
- name: `?StopActivity@ShowSystemToast@UILogger@Internal@UI@wpc@@MEAAXXZ`
- size: `654`
- prototype: `void __fastcall(wpc::UI::Internal::UILogger::ShowSystemToast *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x14008b114`
- `0x14008b5d0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14008b62a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14008b7ba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14008b62a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14008b7ba`
- `KERNEL32!GetCurrentThreadId` at `0x14008b7f1`
- `KERNEL32!GetCurrentThreadId` at `0x14008b7f1`

## pseudocode

```c
void __fastcall wpc::UI::Internal::UILogger::ShowSystemToast::StopActivity(
        wpc::UI::Internal::UILogger::ShowSystemToast *this)
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
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
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
    v5 = wpc::UI::Internal::UILogger::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 4u )
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
        v24[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)qword_1400D7248,
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
    v8 = wpc::UI::Internal::UILogger::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0 && (v10 & 0x200000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v26 = *(_DWORD *)(v11 + 72);
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (__int64)qword_1400D71F8,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::UI::Internal::UILogger::ShowSystemToast *)((char *)this + 288));
}

```

## disassembly

```asm
0x14008b5d0  push    rbp
0x14008b5d2  push    rbx
0x14008b5d3  push    rdi
0x14008b5d4  lea     rbp, [rsp-47h]
0x14008b5d9  sub     rsp, 100h
0x14008b5e0  mov     rbx, rcx
0x14008b5e3  mov     rdi, [rcx+110h]
0x14008b5ea  mov     eax, [rdi+48h]
0x14008b5ed  test    eax, eax
0x14008b5ef  jns     loc_14008B79B
0x14008b5f5  add     rdi, 50h ; 'P'
0x14008b5f9  cmp     eax, [rdi+8]
0x14008b5fc  jnz     loc_14008B79B
0x14008b602  test    rdi, rdi
0x14008b605  jz      loc_14008B79B
0x14008b60b  lea     rdx, [rbp+57h+SRWLock]
0x14008b60f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14008b614  mov     rax, [rbx+110h]
0x14008b61b  mov     dword ptr [rax], 2
0x14008b621  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14008b625  test    rcx, rcx
0x14008b628  jz      short loc_14008B630
0x14008b62a  call    cs:__imp_ReleaseSRWLockExclusive
0x14008b630  call    ?Provider@UILogger@Internal@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Internal::UILogger::Provider(void)
0x14008b635  mov     r9, rax
0x14008b638  mov     ecx, [rax]
0x14008b63a  cmp     ecx, 4
0x14008b63d  jbe     loc_14008B840
0x14008b643  mov     rax, [rax+18h]
0x14008b647  mov     rcx, [r9+10h]
0x14008b64b  mov     rdx, 200000000000h
0x14008b655  test    rdx, rcx
0x14008b658  jz      loc_14008B840
0x14008b65e  mov     rcx, rax
0x14008b661  and     rcx, rdx
0x14008b664  cmp     rcx, rax
0x14008b667  jnz     loc_14008B840
0x14008b66d  mov     rax, [rdi+78h]
0x14008b671  mov     [rbp+57h+var_68], rax
0x14008b675  mov     rax, [rdi+70h]
0x14008b679  mov     [rbp+57h+var_60], rax
0x14008b67d  mov     eax, [rdi+68h]
0x14008b680  mov     dword ptr [rbp+57h+SRWLock], eax
0x14008b683  mov     rax, [rdi+60h]
0x14008b687  mov     [rbp+57h+var_58], rax
0x14008b68b  mov     rax, [rdi+58h]
0x14008b68f  mov     [rbp+57h+var_50], rax
0x14008b693  mov     eax, [rdi+50h]
0x14008b696  mov     [rbp+57h+arg_8], eax
0x14008b699  mov     rax, [rdi+48h]
0x14008b69d  mov     [rbp+57h+var_48], rax
0x14008b6a1  mov     eax, [rdi+20h]
0x14008b6a4  mov     dword ptr [rbp+57h+arg_10], eax
0x14008b6a7  mov     rax, [rdi+18h]
0x14008b6ab  mov     [rbp+57h+var_40], rax
0x14008b6af  mov     eax, [rdi]
0x14008b6b1  mov     [rbp+57h+arg_18], eax
0x14008b6b4  mov     rax, [rdi+80h]
0x14008b6bb  mov     [rbp+57h+var_38], rax
0x14008b6bf  mov     eax, [rdi+40h]
0x14008b6c2  mov     [rbp+57h+var_70], eax
0x14008b6c5  mov     rax, [rdi+38h]
0x14008b6c9  mov     [rbp+57h+var_30], rax
0x14008b6cd  mov     eax, [rdi+8]
0x14008b6d0  mov     [rbp+57h+var_6C], eax
0x14008b6d3  mov     eax, 1000000h
0x14008b6d8  mov     [rbp+57h+var_28], rax
0x14008b6dc  mov     [rbp+57h+var_20], rax
0x14008b6e0  mov     r8, [rbx+110h]
0x14008b6e7  add     r8, 8
0x14008b6eb  lea     rax, [rbp+57h+var_68]
0x14008b6ef  mov     [rsp+110h+var_78], rax
0x14008b6f7  lea     rax, [rbp+57h+var_60]
0x14008b6fb  mov     [rsp+110h+var_80], rax
0x14008b703  lea     rax, [rbp+57h+SRWLock]
0x14008b707  mov     [rsp+110h+var_88], rax
0x14008b70f  lea     rax, [rbp+57h+var_58]
0x14008b713  mov     [rsp+110h+var_90], rax
0x14008b71b  lea     rax, [rbp+57h+var_50]
0x14008b71f  mov     [rsp+110h+var_98], rax
0x14008b724  lea     rax, [rbp+57h+arg_8]
0x14008b728  mov     [rsp+110h+var_A0], rax
0x14008b72d  lea     rax, [rbp+57h+var_48]
0x14008b731  mov     [rsp+110h+var_A8], rax
0x14008b736  lea     rax, [rbp+57h+arg_10]
0x14008b73a  mov     [rsp+110h+var_B0], rax
0x14008b73f  lea     rax, [rbp+57h+var_40]
0x14008b743  mov     [rsp+110h+var_B8], rax
0x14008b748  lea     rax, [rbp+57h+arg_18]
0x14008b74c  mov     [rsp+110h+var_C0], rax
0x14008b751  lea     rax, [rbp+57h+var_38]
0x14008b755  mov     [rsp+110h+var_C8], rax
0x14008b75a  lea     rax, [rbp+57h+var_70]
0x14008b75e  mov     [rsp+110h+var_D0], rax
0x14008b763  lea     rax, [rbp+57h+var_30]
0x14008b767  mov     [rsp+110h+var_D8], rax
0x14008b76c  lea     rax, [rbp+57h+var_6C]
0x14008b770  mov     [rsp+110h+var_E0], rax
0x14008b775  lea     rax, [rbp+57h+var_28]
0x14008b779  mov     [rsp+110h+var_E8], rax
0x14008b77e  lea     rax, [rbp+57h+var_20]
0x14008b782  mov     [rsp+110h+var_F0], rax
0x14008b787  lea     rdx, qword_1400D7248
0x14008b78e  mov     rcx, r9
0x14008b791  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14008b796  jmp     loc_14008B840
0x14008b79b  lea     rdx, [rbp+57h+SRWLock]
0x14008b79f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14008b7a4  mov     rax, [rbx+110h]
0x14008b7ab  mov     dword ptr [rax], 2
0x14008b7b1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14008b7b5  test    rcx, rcx
0x14008b7b8  jz      short loc_14008B7C0
0x14008b7ba  call    cs:__imp_ReleaseSRWLockExclusive
0x14008b7c0  call    ?Provider@UILogger@Internal@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Internal::UILogger::Provider(void)
0x14008b7c5  mov     rdi, rax
0x14008b7c8  mov     ecx, [rax]
0x14008b7ca  cmp     ecx, 4
0x14008b7cd  jbe     short loc_14008B840
0x14008b7cf  mov     rax, [rax+18h]
0x14008b7d3  mov     rcx, [rdi+10h]
0x14008b7d7  mov     rdx, 200000000000h
0x14008b7e1  test    rdx, rcx
0x14008b7e4  jz      short loc_14008B840
0x14008b7e6  mov     rcx, rax
0x14008b7e9  and     rcx, rdx
0x14008b7ec  cmp     rcx, rax
0x14008b7ef  jnz     short loc_14008B840
0x14008b7f1  call    cs:__imp_GetCurrentThreadId
0x14008b7f7  mov     dword ptr [rbp+57h+SRWLock], eax
0x14008b7fa  mov     r8, [rbx+110h]
0x14008b801  mov     eax, [r8+48h]
0x14008b805  mov     [rbp+57h+arg_8], eax
0x14008b808  mov     eax, 1000000h
0x14008b80d  mov     [rbp+57h+arg_10], rax
0x14008b811  add     r8, 8
0x14008b815  lea     rax, [rbp+57h+SRWLock]
0x14008b819  mov     [rsp+110h+var_E0], rax
0x14008b81e  lea     rax, [rbp+57h+arg_8]
0x14008b822  mov     [rsp+110h+var_E8], rax
0x14008b827  lea     rax, [rbp+57h+arg_10]
0x14008b82b  mov     [rsp+110h+var_F0], rax
0x14008b830  lea     rdx, qword_1400D71F8
0x14008b837  mov     rcx, rdi
0x14008b83a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14008b83f  nop
0x14008b840  lea     rcx, [rbx+120h]; this
0x14008b847  cmp     dword ptr [rcx+18h], 0
0x14008b84b  jz      short loc_14008B853
0x14008b84d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14008b852  nop
0x14008b853  add     rsp, 100h
0x14008b85a  pop     rdi
0x14008b85b  pop     rbx
0x14008b85c  pop     rbp
0x14008b85d  retn
```
