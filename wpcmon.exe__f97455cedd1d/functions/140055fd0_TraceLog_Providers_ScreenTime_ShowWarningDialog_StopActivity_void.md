# TraceLog::Providers::ScreenTime::ShowWarningDialog::StopActivity(void)

- ea: `0x140055fd0`
- end: `0x140056260`
- name: `?StopActivity@ShowWarningDialog@ScreenTime@Providers@TraceLog@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(TraceLog::Providers::ScreenTime::ShowWarningDialog *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x1400544c4`
- `0x140055fd0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14005602a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400561bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14005602a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400561bd`
- `KERNEL32!GetCurrentThreadId` at `0x1400561f4`
- `KERNEL32!GetCurrentThreadId` at `0x1400561f4`

## pseudocode

```c
void __fastcall TraceLog::Providers::ScreenTime::ShowWarningDialog::StopActivity(
        TraceLog::Providers::ScreenTime::ShowWarningDialog *this)
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
          (__int64)&byte_1400D6C1F,
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
          (__int64)word_1400D6B8A,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((TraceLog::Providers::ScreenTime::ShowWarningDialog *)((char *)this + 288));
}

```

## disassembly

```asm
0x140055fd0  push    rbp
0x140055fd2  push    rbx
0x140055fd3  push    rdi
0x140055fd4  lea     rbp, [rsp-47h]
0x140055fd9  sub     rsp, 100h
0x140055fe0  mov     rbx, rcx
0x140055fe3  mov     rdi, [rcx+110h]
0x140055fea  mov     eax, [rdi+48h]
0x140055fed  test    eax, eax
0x140055fef  jns     loc_14005619E
0x140055ff5  add     rdi, 50h ; 'P'
0x140055ff9  cmp     eax, [rdi+8]
0x140055ffc  jnz     loc_14005619E
0x140056002  test    rdi, rdi
0x140056005  jz      loc_14005619E
0x14005600b  lea     rdx, [rbp+57h+SRWLock]
0x14005600f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140056014  mov     rax, [rbx+110h]
0x14005601b  mov     dword ptr [rax], 2
0x140056021  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140056025  test    rcx, rcx
0x140056028  jz      short loc_140056030
0x14005602a  call    cs:__imp_ReleaseSRWLockExclusive
0x140056030  call    ?Provider@ScreenTime@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::ScreenTime::Provider(void)
0x140056035  mov     r9, rax
0x140056038  mov     ecx, [rax]
0x14005603a  cmp     ecx, 5
0x14005603d  jbe     loc_140056242
0x140056043  mov     rax, [rax+18h]
0x140056047  mov     rcx, [r9+10h]
0x14005604b  mov     rdx, 200000000000h
0x140056055  test    rdx, rcx
0x140056058  jz      loc_140056242
0x14005605e  mov     rcx, rax
0x140056061  and     rcx, rdx
0x140056064  cmp     rcx, rax
0x140056067  jnz     loc_140056242
0x14005606d  mov     rax, [rdi+78h]
0x140056071  mov     [rbp+57h+var_68], rax
0x140056075  mov     rax, [rdi+70h]
0x140056079  mov     [rbp+57h+var_60], rax
0x14005607d  mov     eax, [rdi+68h]
0x140056080  mov     dword ptr [rbp+57h+SRWLock], eax
0x140056083  mov     rax, [rdi+60h]
0x140056087  mov     [rbp+57h+var_58], rax
0x14005608b  mov     rax, [rdi+58h]
0x14005608f  mov     [rbp+57h+var_50], rax
0x140056093  mov     eax, [rdi+50h]
0x140056096  mov     [rbp+57h+arg_8], eax
0x140056099  mov     rax, [rdi+48h]
0x14005609d  mov     [rbp+57h+var_48], rax
0x1400560a1  mov     eax, [rdi+20h]
0x1400560a4  mov     dword ptr [rbp+57h+arg_10], eax
0x1400560a7  mov     rax, [rdi+18h]
0x1400560ab  mov     [rbp+57h+var_40], rax
0x1400560af  mov     eax, [rdi]
0x1400560b1  mov     [rbp+57h+arg_18], eax
0x1400560b4  mov     rax, [rdi+80h]
0x1400560bb  mov     [rbp+57h+var_38], rax
0x1400560bf  mov     eax, [rdi+40h]
0x1400560c2  mov     [rbp+57h+var_70], eax
0x1400560c5  mov     rax, [rdi+38h]
0x1400560c9  mov     [rbp+57h+var_30], rax
0x1400560cd  mov     eax, [rdi+8]
0x1400560d0  mov     [rbp+57h+var_6C], eax
0x1400560d3  mov     [rbp+57h+var_28], 1000000h
0x1400560db  mov     [rbp+57h+var_20], 0
0x1400560e3  mov     r8, [rbx+110h]
0x1400560ea  add     r8, 8
0x1400560ee  lea     rax, [rbp+57h+var_68]
0x1400560f2  mov     [rsp+110h+var_78], rax
0x1400560fa  lea     rax, [rbp+57h+var_60]
0x1400560fe  mov     [rsp+110h+var_80], rax
0x140056106  lea     rax, [rbp+57h+SRWLock]
0x14005610a  mov     [rsp+110h+var_88], rax
0x140056112  lea     rax, [rbp+57h+var_58]
0x140056116  mov     [rsp+110h+var_90], rax
0x14005611e  lea     rax, [rbp+57h+var_50]
0x140056122  mov     [rsp+110h+var_98], rax
0x140056127  lea     rax, [rbp+57h+arg_8]
0x14005612b  mov     [rsp+110h+var_A0], rax
0x140056130  lea     rax, [rbp+57h+var_48]
0x140056134  mov     [rsp+110h+var_A8], rax
0x140056139  lea     rax, [rbp+57h+arg_10]
0x14005613d  mov     [rsp+110h+var_B0], rax
0x140056142  lea     rax, [rbp+57h+var_40]
0x140056146  mov     [rsp+110h+var_B8], rax
0x14005614b  lea     rax, [rbp+57h+arg_18]
0x14005614f  mov     [rsp+110h+var_C0], rax
0x140056154  lea     rax, [rbp+57h+var_38]
0x140056158  mov     [rsp+110h+var_C8], rax
0x14005615d  lea     rax, [rbp+57h+var_70]
0x140056161  mov     [rsp+110h+var_D0], rax
0x140056166  lea     rax, [rbp+57h+var_30]
0x14005616a  mov     [rsp+110h+var_D8], rax
0x14005616f  lea     rax, [rbp+57h+var_6C]
0x140056173  mov     [rsp+110h+var_E0], rax
0x140056178  lea     rax, [rbp+57h+var_28]
0x14005617c  mov     [rsp+110h+var_E8], rax
0x140056181  lea     rax, [rbp+57h+var_20]
0x140056185  mov     [rsp+110h+var_F0], rax
0x14005618a  lea     rdx, byte_1400D6C1F
0x140056191  mov     rcx, r9
0x140056194  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140056199  jmp     loc_140056242
0x14005619e  lea     rdx, [rbp+57h+SRWLock]
0x1400561a2  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400561a7  mov     rax, [rbx+110h]
0x1400561ae  mov     dword ptr [rax], 2
0x1400561b4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400561b8  test    rcx, rcx
0x1400561bb  jz      short loc_1400561C3
0x1400561bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1400561c3  call    ?Provider@ScreenTime@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::ScreenTime::Provider(void)
0x1400561c8  mov     rdi, rax
0x1400561cb  mov     ecx, [rax]
0x1400561cd  cmp     ecx, 5
0x1400561d0  jbe     short loc_140056242
0x1400561d2  mov     rax, [rax+18h]
0x1400561d6  mov     rcx, [rdi+10h]
0x1400561da  mov     rdx, 200000000000h
0x1400561e4  test    rdx, rcx
0x1400561e7  jz      short loc_140056242
0x1400561e9  mov     rcx, rax
0x1400561ec  and     rcx, rdx
0x1400561ef  cmp     rcx, rax
0x1400561f2  jnz     short loc_140056242
0x1400561f4  call    cs:__imp_GetCurrentThreadId
0x1400561fa  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400561fd  mov     r8, [rbx+110h]
0x140056204  mov     eax, [r8+48h]
0x140056208  mov     [rbp+57h+arg_8], eax
0x14005620b  mov     [rbp+57h+arg_10], 0
0x140056213  add     r8, 8
0x140056217  lea     rax, [rbp+57h+SRWLock]
0x14005621b  mov     [rsp+110h+var_E0], rax
0x140056220  lea     rax, [rbp+57h+arg_8]
0x140056224  mov     [rsp+110h+var_E8], rax
0x140056229  lea     rax, [rbp+57h+arg_10]
0x14005622d  mov     [rsp+110h+var_F0], rax
0x140056232  lea     rdx, word_1400D6B8A
0x140056239  mov     rcx, rdi
0x14005623c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140056241  nop
0x140056242  lea     rcx, [rbx+120h]; this
0x140056249  cmp     dword ptr [rcx+18h], 0
0x14005624d  jz      short loc_140056255
0x14005624f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140056254  nop
0x140056255  add     rsp, 100h
0x14005625c  pop     rdi
0x14005625d  pop     rbx
0x14005625e  pop     rbp
0x14005625f  retn
```
