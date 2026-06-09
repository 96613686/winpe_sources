# wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast::StopActivity(void)

- ea: `0x14004b2d0`
- end: `0x14004b55e`
- name: `?StopActivity@ShowAppTimeLimitToast@MonitorUILogger@Logging@UI@wpc@@MEAAXXZ`
- size: `654`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x14002af88`
- `0x14004b2d0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004b32a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004b4ba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004b32a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004b4ba`
- `KERNEL32!GetCurrentThreadId` at `0x14004b4f1`
- `KERNEL32!GetCurrentThreadId` at `0x14004b4f1`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast::StopActivity(
        wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast *this)
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
    v5 = wpc::UI::Logging::MonitorUILogger::Provider();
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
          (__int64)&word_1400D6466,
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
    v8 = wpc::UI::Logging::MonitorUILogger::Provider();
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
          (__int64)&unk_1400D6410,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast *)((char *)this + 288));
}

```

## disassembly

```asm
0x14004b2d0  push    rbp
0x14004b2d2  push    rbx
0x14004b2d3  push    rdi
0x14004b2d4  lea     rbp, [rsp-47h]
0x14004b2d9  sub     rsp, 100h
0x14004b2e0  mov     rbx, rcx
0x14004b2e3  mov     rdi, [rcx+110h]
0x14004b2ea  mov     eax, [rdi+48h]
0x14004b2ed  test    eax, eax
0x14004b2ef  jns     loc_14004B49B
0x14004b2f5  add     rdi, 50h ; 'P'
0x14004b2f9  cmp     eax, [rdi+8]
0x14004b2fc  jnz     loc_14004B49B
0x14004b302  test    rdi, rdi
0x14004b305  jz      loc_14004B49B
0x14004b30b  lea     rdx, [rbp+57h+SRWLock]
0x14004b30f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004b314  mov     rax, [rbx+110h]
0x14004b31b  mov     dword ptr [rax], 2
0x14004b321  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14004b325  test    rcx, rcx
0x14004b328  jz      short loc_14004B330
0x14004b32a  call    cs:__imp_ReleaseSRWLockExclusive
0x14004b330  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004b335  mov     r9, rax
0x14004b338  mov     ecx, [rax]
0x14004b33a  cmp     ecx, 4
0x14004b33d  jbe     loc_14004B540
0x14004b343  mov     rax, [rax+18h]
0x14004b347  mov     rcx, [r9+10h]
0x14004b34b  mov     rdx, 200000000000h
0x14004b355  test    rdx, rcx
0x14004b358  jz      loc_14004B540
0x14004b35e  mov     rcx, rax
0x14004b361  and     rcx, rdx
0x14004b364  cmp     rcx, rax
0x14004b367  jnz     loc_14004B540
0x14004b36d  mov     rax, [rdi+78h]
0x14004b371  mov     [rbp+57h+var_68], rax
0x14004b375  mov     rax, [rdi+70h]
0x14004b379  mov     [rbp+57h+var_60], rax
0x14004b37d  mov     eax, [rdi+68h]
0x14004b380  mov     dword ptr [rbp+57h+SRWLock], eax
0x14004b383  mov     rax, [rdi+60h]
0x14004b387  mov     [rbp+57h+var_58], rax
0x14004b38b  mov     rax, [rdi+58h]
0x14004b38f  mov     [rbp+57h+var_50], rax
0x14004b393  mov     eax, [rdi+50h]
0x14004b396  mov     [rbp+57h+arg_8], eax
0x14004b399  mov     rax, [rdi+48h]
0x14004b39d  mov     [rbp+57h+var_48], rax
0x14004b3a1  mov     eax, [rdi+20h]
0x14004b3a4  mov     dword ptr [rbp+57h+arg_10], eax
0x14004b3a7  mov     rax, [rdi+18h]
0x14004b3ab  mov     [rbp+57h+var_40], rax
0x14004b3af  mov     eax, [rdi]
0x14004b3b1  mov     [rbp+57h+arg_18], eax
0x14004b3b4  mov     rax, [rdi+80h]
0x14004b3bb  mov     [rbp+57h+var_38], rax
0x14004b3bf  mov     eax, [rdi+40h]
0x14004b3c2  mov     [rbp+57h+var_70], eax
0x14004b3c5  mov     rax, [rdi+38h]
0x14004b3c9  mov     [rbp+57h+var_30], rax
0x14004b3cd  mov     eax, [rdi+8]
0x14004b3d0  mov     [rbp+57h+var_6C], eax
0x14004b3d3  mov     eax, 1000000h
0x14004b3d8  mov     [rbp+57h+var_28], rax
0x14004b3dc  mov     [rbp+57h+var_20], rax
0x14004b3e0  mov     r8, [rbx+110h]
0x14004b3e7  add     r8, 8
0x14004b3eb  lea     rax, [rbp+57h+var_68]
0x14004b3ef  mov     [rsp+110h+var_78], rax
0x14004b3f7  lea     rax, [rbp+57h+var_60]
0x14004b3fb  mov     [rsp+110h+var_80], rax
0x14004b403  lea     rax, [rbp+57h+SRWLock]
0x14004b407  mov     [rsp+110h+var_88], rax
0x14004b40f  lea     rax, [rbp+57h+var_58]
0x14004b413  mov     [rsp+110h+var_90], rax
0x14004b41b  lea     rax, [rbp+57h+var_50]
0x14004b41f  mov     [rsp+110h+var_98], rax
0x14004b424  lea     rax, [rbp+57h+arg_8]
0x14004b428  mov     [rsp+110h+var_A0], rax
0x14004b42d  lea     rax, [rbp+57h+var_48]
0x14004b431  mov     [rsp+110h+var_A8], rax
0x14004b436  lea     rax, [rbp+57h+arg_10]
0x14004b43a  mov     [rsp+110h+var_B0], rax
0x14004b43f  lea     rax, [rbp+57h+var_40]
0x14004b443  mov     [rsp+110h+var_B8], rax
0x14004b448  lea     rax, [rbp+57h+arg_18]
0x14004b44c  mov     [rsp+110h+var_C0], rax
0x14004b451  lea     rax, [rbp+57h+var_38]
0x14004b455  mov     [rsp+110h+var_C8], rax
0x14004b45a  lea     rax, [rbp+57h+var_70]
0x14004b45e  mov     [rsp+110h+var_D0], rax
0x14004b463  lea     rax, [rbp+57h+var_30]
0x14004b467  mov     [rsp+110h+var_D8], rax
0x14004b46c  lea     rax, [rbp+57h+var_6C]
0x14004b470  mov     [rsp+110h+var_E0], rax
0x14004b475  lea     rax, [rbp+57h+var_28]
0x14004b479  mov     [rsp+110h+var_E8], rax
0x14004b47e  lea     rax, [rbp+57h+var_20]
0x14004b482  mov     [rsp+110h+var_F0], rax
0x14004b487  lea     rdx, word_1400D6466
0x14004b48e  mov     rcx, r9
0x14004b491  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14004b496  jmp     loc_14004B540
0x14004b49b  lea     rdx, [rbp+57h+SRWLock]
0x14004b49f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004b4a4  mov     rax, [rbx+110h]
0x14004b4ab  mov     dword ptr [rax], 2
0x14004b4b1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14004b4b5  test    rcx, rcx
0x14004b4b8  jz      short loc_14004B4C0
0x14004b4ba  call    cs:__imp_ReleaseSRWLockExclusive
0x14004b4c0  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004b4c5  mov     rdi, rax
0x14004b4c8  mov     ecx, [rax]
0x14004b4ca  cmp     ecx, 4
0x14004b4cd  jbe     short loc_14004B540
0x14004b4cf  mov     rax, [rax+18h]
0x14004b4d3  mov     rcx, [rdi+10h]
0x14004b4d7  mov     rdx, 200000000000h
0x14004b4e1  test    rdx, rcx
0x14004b4e4  jz      short loc_14004B540
0x14004b4e6  mov     rcx, rax
0x14004b4e9  and     rcx, rdx
0x14004b4ec  cmp     rcx, rax
0x14004b4ef  jnz     short loc_14004B540
0x14004b4f1  call    cs:__imp_GetCurrentThreadId
0x14004b4f7  mov     dword ptr [rbp+57h+SRWLock], eax
0x14004b4fa  mov     r8, [rbx+110h]
0x14004b501  mov     eax, [r8+48h]
0x14004b505  mov     [rbp+57h+arg_8], eax
0x14004b508  mov     eax, 1000000h
0x14004b50d  mov     [rbp+57h+arg_10], rax
0x14004b511  add     r8, 8
0x14004b515  lea     rax, [rbp+57h+SRWLock]
0x14004b519  mov     [rsp+110h+var_E0], rax
0x14004b51e  lea     rax, [rbp+57h+arg_8]
0x14004b522  mov     [rsp+110h+var_E8], rax
0x14004b527  lea     rax, [rbp+57h+arg_10]
0x14004b52b  mov     [rsp+110h+var_F0], rax
0x14004b530  lea     rdx, unk_1400D6410
0x14004b537  mov     rcx, rdi
0x14004b53a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004b53f  nop
0x14004b540  lea     rcx, [rbx+120h]; this
0x14004b547  cmp     dword ptr [rcx+18h], 0
0x14004b54b  jz      short loc_14004B553
0x14004b54d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14004b552  nop
0x14004b553  add     rsp, 100h
0x14004b55a  pop     rdi
0x14004b55b  pop     rbx
0x14004b55c  pop     rbp
0x14004b55d  retn
```
