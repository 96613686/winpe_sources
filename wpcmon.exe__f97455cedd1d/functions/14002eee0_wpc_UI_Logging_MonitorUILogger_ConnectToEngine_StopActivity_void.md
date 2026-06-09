# wpc::UI::Logging::MonitorUILogger::ConnectToEngine::StopActivity(void)

- ea: `0x14002eee0`
- end: `0x14002f15a`
- name: `?StopActivity@ConnectToEngine@MonitorUILogger@Logging@UI@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::ConnectToEngine *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400012bc`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x14002af88`
- `0x14002eee0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14002ef3a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14002f0d8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14002ef3a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14002f0d8`
- `KERNEL32!GetCurrentThreadId` at `0x14002f0ed`
- `KERNEL32!GetCurrentThreadId` at `0x14002f0ed`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::ConnectToEngine::StopActivity(
        wpc::UI::Logging::MonitorUILogger::ConnectToEngine *this)
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
        (__int64)byte_1400D571B,
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
        (__int64)byte_1400D56CB,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::UI::Logging::MonitorUILogger::ConnectToEngine *)((char *)this + 288));
}

```

## disassembly

```asm
0x14002eee0  push    rbp
0x14002eee2  push    rbx
0x14002eee3  push    rdi
0x14002eee4  lea     rbp, [rsp+10h]
0x14002eee9  sub     rsp, 130h
0x14002eef0  mov     rbx, rcx
0x14002eef3  mov     rdi, [rcx+110h]
0x14002eefa  mov     eax, [rdi+48h]
0x14002eefd  test    eax, eax
0x14002eeff  jns     loc_14002F0B9
0x14002ef05  add     rdi, 50h ; 'P'
0x14002ef09  cmp     eax, [rdi+8]
0x14002ef0c  jnz     loc_14002F0B9
0x14002ef12  test    rdi, rdi
0x14002ef15  jz      loc_14002F0B9
0x14002ef1b  lea     rdx, [rbp+SRWLock]
0x14002ef1f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002ef24  mov     rax, [rbx+110h]
0x14002ef2b  mov     dword ptr [rax], 2
0x14002ef31  mov     rcx, [rbp+SRWLock]; SRWLock
0x14002ef35  test    rcx, rcx
0x14002ef38  jz      short loc_14002EF40
0x14002ef3a  call    cs:__imp_ReleaseSRWLockExclusive
0x14002ef40  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14002ef45  mov     r9, rax
0x14002ef48  mov     ecx, [rax]
0x14002ef4a  cmp     ecx, 4
0x14002ef4d  jbe     loc_14002F13C
0x14002ef53  mov     rcx, [rdi+30h]
0x14002ef57  mov     [rbp+var_70], rcx
0x14002ef5b  mov     ecx, [rdi+44h]
0x14002ef5e  mov     dword ptr [rbp+SRWLock], ecx
0x14002ef61  mov     ecx, [rdi+10h]
0x14002ef64  mov     [rbp+arg_8], ecx
0x14002ef67  mov     rcx, [rdi+78h]
0x14002ef6b  mov     [rbp+var_68], rcx
0x14002ef6f  mov     rax, [rdi+70h]
0x14002ef73  mov     [rbp+var_60], rax
0x14002ef77  mov     eax, [rdi+68h]
0x14002ef7a  mov     dword ptr [rbp+arg_10], eax
0x14002ef7d  mov     rax, [rdi+60h]
0x14002ef81  mov     [rbp+var_58], rax
0x14002ef85  mov     rax, [rdi+58h]
0x14002ef89  mov     [rbp+var_50], rax
0x14002ef8d  mov     eax, [rdi+50h]
0x14002ef90  mov     [rbp+arg_18], eax
0x14002ef93  mov     rax, [rdi+48h]
0x14002ef97  mov     [rbp+var_48], rax
0x14002ef9b  mov     eax, [rdi+20h]
0x14002ef9e  mov     [rbp+var_80], eax
0x14002efa1  mov     rax, [rdi+18h]
0x14002efa5  mov     [rbp+var_40], rax
0x14002efa9  mov     eax, [rdi]
0x14002efab  mov     [rbp+var_7C], eax
0x14002efae  mov     rax, [rdi+80h]
0x14002efb5  mov     [rbp+var_38], rax
0x14002efb9  mov     eax, [rdi+40h]
0x14002efbc  mov     [rbp+var_78], eax
0x14002efbf  mov     rax, [rdi+38h]
0x14002efc3  mov     [rbp+var_30], rax
0x14002efc7  mov     eax, [rdi+8]
0x14002efca  mov     [rbp+var_74], eax
0x14002efcd  mov     eax, 1000000h
0x14002efd2  mov     [rbp+var_28], rax
0x14002efd6  mov     [rbp+var_20], rax
0x14002efda  mov     r8, [rbx+110h]
0x14002efe1  add     r8, 8
0x14002efe5  lea     rax, [rbp+var_70]
0x14002efe9  mov     [rsp+140h+var_90], rax
0x14002eff1  lea     rax, [rbp+SRWLock]
0x14002eff5  mov     [rsp+140h+var_98], rax
0x14002effd  lea     rax, [rbp+arg_8]
0x14002f001  mov     [rsp+140h+var_A0], rax
0x14002f009  lea     rax, [rbp+var_68]
0x14002f00d  mov     [rsp+140h+var_A8], rax
0x14002f015  lea     rax, [rbp+var_60]
0x14002f019  mov     [rsp+140h+var_B0], rax
0x14002f021  lea     rax, [rbp+arg_10]
0x14002f025  mov     [rsp+140h+var_B8], rax
0x14002f02d  lea     rax, [rbp+var_58]
0x14002f031  mov     [rsp+140h+var_C0], rax
0x14002f039  lea     rax, [rbp+var_50]
0x14002f03d  mov     [rsp+140h+var_C8], rax
0x14002f042  lea     rax, [rbp+arg_18]
0x14002f046  mov     [rsp+140h+var_D0], rax
0x14002f04b  lea     rax, [rbp+var_48]
0x14002f04f  mov     [rsp+140h+var_D8], rax
0x14002f054  lea     rax, [rbp+var_80]
0x14002f058  mov     [rsp+140h+var_E0], rax
0x14002f05d  lea     rax, [rbp+var_40]
0x14002f061  mov     [rsp+140h+var_E8], rax
0x14002f066  lea     rax, [rbp+var_7C]
0x14002f06a  mov     [rsp+140h+var_F0], rax
0x14002f06f  lea     rax, [rbp+var_38]
0x14002f073  mov     [rsp+140h+var_F8], rax
0x14002f078  lea     rax, [rbp+var_78]
0x14002f07c  mov     [rsp+140h+var_100], rax
0x14002f081  lea     rax, [rbp+var_30]
0x14002f085  mov     [rsp+140h+var_108], rax
0x14002f08a  lea     rax, [rbp+var_74]
0x14002f08e  mov     [rsp+140h+var_110], rax
0x14002f093  lea     rax, [rbp+var_28]
0x14002f097  mov     [rsp+140h+var_118], rax
0x14002f09c  lea     rax, [rbp+var_20]
0x14002f0a0  mov     [rsp+140h+var_120], rax
0x14002f0a5  lea     rdx, byte_1400D571B
0x14002f0ac  mov     rcx, r9
0x14002f0af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14002f0b4  jmp     loc_14002F13C
0x14002f0b9  lea     rdx, [rbp+SRWLock]
0x14002f0bd  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002f0c2  mov     rax, [rbx+110h]
0x14002f0c9  mov     dword ptr [rax], 2
0x14002f0cf  mov     rcx, [rbp+SRWLock]; SRWLock
0x14002f0d3  test    rcx, rcx
0x14002f0d6  jz      short loc_14002F0DE
0x14002f0d8  call    cs:__imp_ReleaseSRWLockExclusive
0x14002f0de  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14002f0e3  mov     rdi, rax
0x14002f0e6  mov     ecx, [rax]
0x14002f0e8  cmp     ecx, 4
0x14002f0eb  jbe     short loc_14002F13C
0x14002f0ed  call    cs:__imp_GetCurrentThreadId
0x14002f0f3  mov     dword ptr [rbp+SRWLock], eax
0x14002f0f6  mov     r8, [rbx+110h]
0x14002f0fd  mov     ecx, [r8+48h]
0x14002f101  mov     [rbp+arg_8], ecx
0x14002f104  mov     eax, 1000000h
0x14002f109  mov     [rbp+arg_10], rax
0x14002f10d  add     r8, 8
0x14002f111  lea     rax, [rbp+SRWLock]
0x14002f115  mov     [rsp+140h+var_110], rax
0x14002f11a  lea     rax, [rbp+arg_8]
0x14002f11e  mov     [rsp+140h+var_118], rax
0x14002f123  lea     rax, [rbp+arg_10]
0x14002f127  mov     [rsp+140h+var_120], rax
0x14002f12c  lea     rdx, byte_1400D56CB
0x14002f133  mov     rcx, rdi
0x14002f136  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002f13b  nop
0x14002f13c  lea     rcx, [rbx+120h]; this
0x14002f143  cmp     dword ptr [rcx+18h], 0
0x14002f147  jz      short loc_14002F14F
0x14002f149  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14002f14e  nop
0x14002f14f  add     rsp, 130h
0x14002f156  pop     rdi
0x14002f157  pop     rbx
0x14002f158  pop     rbp
0x14002f159  retn
```
