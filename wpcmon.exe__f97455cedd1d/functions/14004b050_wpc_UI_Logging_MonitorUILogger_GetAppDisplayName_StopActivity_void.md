# wpc::UI::Logging::MonitorUILogger::GetAppDisplayName::StopActivity(void)

- ea: `0x14004b050`
- end: `0x14004b2ca`
- name: `?StopActivity@GetAppDisplayName@MonitorUILogger@Logging@UI@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::GetAppDisplayName *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400012bc`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x14002af88`
- `0x14004b050`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004b0aa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004b248`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004b0aa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004b248`
- `KERNEL32!GetCurrentThreadId` at `0x14004b25d`
- `KERNEL32!GetCurrentThreadId` at `0x14004b25d`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::GetAppDisplayName::StopActivity(
        wpc::UI::Logging::MonitorUILogger::GetAppDisplayName *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v13; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v14; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v15; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v16; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v19; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

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
    if ( *(_DWORD *)v5 > 4u )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)word_1400D6052,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v10,
        &v19,
        (__int64)&v9,
        &v18,
        (__int64)&v27,
        &v17,
        &v16,
        (__int64)&v26,
        &v15,
        &v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        &v13);
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
    v6 = wpc::UI::Logging::MonitorUILogger::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&word_1400D619E,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::UI::Logging::MonitorUILogger::GetAppDisplayName *)((char *)this + 288));
}

```

## disassembly

```asm
0x14004b050  push    rbp
0x14004b052  push    rbx
0x14004b053  push    rdi
0x14004b054  lea     rbp, [rsp+10h]
0x14004b059  sub     rsp, 130h
0x14004b060  mov     rbx, rcx
0x14004b063  mov     rdi, [rcx+110h]
0x14004b06a  mov     eax, [rdi+48h]
0x14004b06d  test    eax, eax
0x14004b06f  jns     loc_14004B229
0x14004b075  add     rdi, 50h ; 'P'
0x14004b079  cmp     eax, [rdi+8]
0x14004b07c  jnz     loc_14004B229
0x14004b082  test    rdi, rdi
0x14004b085  jz      loc_14004B229
0x14004b08b  lea     rdx, [rbp+SRWLock]
0x14004b08f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004b094  mov     rax, [rbx+110h]
0x14004b09b  mov     dword ptr [rax], 2
0x14004b0a1  mov     rcx, [rbp+SRWLock]; SRWLock
0x14004b0a5  test    rcx, rcx
0x14004b0a8  jz      short loc_14004B0B0
0x14004b0aa  call    cs:__imp_ReleaseSRWLockExclusive
0x14004b0b0  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004b0b5  mov     r9, rax
0x14004b0b8  mov     ecx, [rax]
0x14004b0ba  cmp     ecx, 4
0x14004b0bd  jbe     loc_14004B2AC
0x14004b0c3  mov     rcx, [rdi+30h]
0x14004b0c7  mov     [rbp+var_70], rcx
0x14004b0cb  mov     ecx, [rdi+44h]
0x14004b0ce  mov     dword ptr [rbp+SRWLock], ecx
0x14004b0d1  mov     ecx, [rdi+10h]
0x14004b0d4  mov     [rbp+arg_8], ecx
0x14004b0d7  mov     rcx, [rdi+78h]
0x14004b0db  mov     [rbp+var_68], rcx
0x14004b0df  mov     rax, [rdi+70h]
0x14004b0e3  mov     [rbp+var_60], rax
0x14004b0e7  mov     eax, [rdi+68h]
0x14004b0ea  mov     dword ptr [rbp+arg_10], eax
0x14004b0ed  mov     rax, [rdi+60h]
0x14004b0f1  mov     [rbp+var_58], rax
0x14004b0f5  mov     rax, [rdi+58h]
0x14004b0f9  mov     [rbp+var_50], rax
0x14004b0fd  mov     eax, [rdi+50h]
0x14004b100  mov     [rbp+arg_18], eax
0x14004b103  mov     rax, [rdi+48h]
0x14004b107  mov     [rbp+var_48], rax
0x14004b10b  mov     eax, [rdi+20h]
0x14004b10e  mov     [rbp+var_80], eax
0x14004b111  mov     rax, [rdi+18h]
0x14004b115  mov     [rbp+var_40], rax
0x14004b119  mov     eax, [rdi]
0x14004b11b  mov     [rbp+var_7C], eax
0x14004b11e  mov     rax, [rdi+80h]
0x14004b125  mov     [rbp+var_38], rax
0x14004b129  mov     eax, [rdi+40h]
0x14004b12c  mov     [rbp+var_78], eax
0x14004b12f  mov     rax, [rdi+38h]
0x14004b133  mov     [rbp+var_30], rax
0x14004b137  mov     eax, [rdi+8]
0x14004b13a  mov     [rbp+var_74], eax
0x14004b13d  mov     eax, 1000000h
0x14004b142  mov     [rbp+var_28], rax
0x14004b146  mov     [rbp+var_20], rax
0x14004b14a  mov     r8, [rbx+110h]
0x14004b151  add     r8, 8
0x14004b155  lea     rax, [rbp+var_70]
0x14004b159  mov     [rsp+140h+var_90], rax
0x14004b161  lea     rax, [rbp+SRWLock]
0x14004b165  mov     [rsp+140h+var_98], rax
0x14004b16d  lea     rax, [rbp+arg_8]
0x14004b171  mov     [rsp+140h+var_A0], rax
0x14004b179  lea     rax, [rbp+var_68]
0x14004b17d  mov     [rsp+140h+var_A8], rax
0x14004b185  lea     rax, [rbp+var_60]
0x14004b189  mov     [rsp+140h+var_B0], rax
0x14004b191  lea     rax, [rbp+arg_10]
0x14004b195  mov     [rsp+140h+var_B8], rax
0x14004b19d  lea     rax, [rbp+var_58]
0x14004b1a1  mov     [rsp+140h+var_C0], rax
0x14004b1a9  lea     rax, [rbp+var_50]
0x14004b1ad  mov     [rsp+140h+var_C8], rax
0x14004b1b2  lea     rax, [rbp+arg_18]
0x14004b1b6  mov     [rsp+140h+var_D0], rax
0x14004b1bb  lea     rax, [rbp+var_48]
0x14004b1bf  mov     [rsp+140h+var_D8], rax
0x14004b1c4  lea     rax, [rbp+var_80]
0x14004b1c8  mov     [rsp+140h+var_E0], rax
0x14004b1cd  lea     rax, [rbp+var_40]
0x14004b1d1  mov     [rsp+140h+var_E8], rax
0x14004b1d6  lea     rax, [rbp+var_7C]
0x14004b1da  mov     [rsp+140h+var_F0], rax
0x14004b1df  lea     rax, [rbp+var_38]
0x14004b1e3  mov     [rsp+140h+var_F8], rax
0x14004b1e8  lea     rax, [rbp+var_78]
0x14004b1ec  mov     [rsp+140h+var_100], rax
0x14004b1f1  lea     rax, [rbp+var_30]
0x14004b1f5  mov     [rsp+140h+var_108], rax
0x14004b1fa  lea     rax, [rbp+var_74]
0x14004b1fe  mov     [rsp+140h+var_110], rax
0x14004b203  lea     rax, [rbp+var_28]
0x14004b207  mov     [rsp+140h+var_118], rax
0x14004b20c  lea     rax, [rbp+var_20]
0x14004b210  mov     [rsp+140h+var_120], rax
0x14004b215  lea     rdx, word_1400D6052
0x14004b21c  mov     rcx, r9
0x14004b21f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14004b224  jmp     loc_14004B2AC
0x14004b229  lea     rdx, [rbp+SRWLock]
0x14004b22d  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004b232  mov     rax, [rbx+110h]
0x14004b239  mov     dword ptr [rax], 2
0x14004b23f  mov     rcx, [rbp+SRWLock]; SRWLock
0x14004b243  test    rcx, rcx
0x14004b246  jz      short loc_14004B24E
0x14004b248  call    cs:__imp_ReleaseSRWLockExclusive
0x14004b24e  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004b253  mov     rdi, rax
0x14004b256  mov     ecx, [rax]
0x14004b258  cmp     ecx, 4
0x14004b25b  jbe     short loc_14004B2AC
0x14004b25d  call    cs:__imp_GetCurrentThreadId
0x14004b263  mov     dword ptr [rbp+SRWLock], eax
0x14004b266  mov     r8, [rbx+110h]
0x14004b26d  mov     ecx, [r8+48h]
0x14004b271  mov     [rbp+arg_8], ecx
0x14004b274  mov     eax, 1000000h
0x14004b279  mov     [rbp+arg_10], rax
0x14004b27d  add     r8, 8
0x14004b281  lea     rax, [rbp+SRWLock]
0x14004b285  mov     [rsp+140h+var_110], rax
0x14004b28a  lea     rax, [rbp+arg_8]
0x14004b28e  mov     [rsp+140h+var_118], rax
0x14004b293  lea     rax, [rbp+arg_10]
0x14004b297  mov     [rsp+140h+var_120], rax
0x14004b29c  lea     rdx, word_1400D619E
0x14004b2a3  mov     rcx, rdi
0x14004b2a6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004b2ab  nop
0x14004b2ac  lea     rcx, [rbx+120h]; this
0x14004b2b3  cmp     dword ptr [rcx+18h], 0
0x14004b2b7  jz      short loc_14004B2BF
0x14004b2b9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14004b2be  nop
0x14004b2bf  add     rsp, 130h
0x14004b2c6  pop     rdi
0x14004b2c7  pop     rbx
0x14004b2c8  pop     rbp
0x14004b2c9  retn
```
