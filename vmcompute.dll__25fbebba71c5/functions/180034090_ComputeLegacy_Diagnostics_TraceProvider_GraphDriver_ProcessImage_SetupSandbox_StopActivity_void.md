# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox::StopActivity(void)

- ea: `0x180034090`
- end: `0x180034376`
- name: `?StopActivity@GraphDriver_ProcessImage_SetupSandbox@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x180034090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800340f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800342c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800340f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800342c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800342f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800342f6`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v9; // [rsp+C8h] [rbp-78h] BYREF
  int v10; // [rsp+CCh] [rbp-74h] BYREF
  int v11; // [rsp+D0h] [rbp-70h] BYREF
  int v12; // [rsp+D4h] [rbp-6Ch] BYREF
  int v13; // [rsp+D8h] [rbp-68h] BYREF
  int v14; // [rsp+DCh] [rbp-64h] BYREF
  int v15; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+100h] [rbp-40h] BYREF
  __int64 v20; // [rsp+108h] [rbp-38h] BYREF
  __int64 v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23; // [rsp+120h] [rbp-20h] BYREF
  __int64 v24; // [rsp+128h] [rbp-18h] BYREF
  __int64 v25; // [rsp+130h] [rbp-10h] BYREF
  __int64 v26; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u
      && (*(_QWORD *)(v5 + 16) & 0x40) != 0
      && (*(_QWORD *)(v5 + 24) & 0x40LL) == *(_QWORD *)(v5 + 24) )
    {
      v17 = *((_QWORD *)v4 + 6);
      v10 = v4[17];
      v11 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v19 = *((_QWORD *)v4 + 14);
      v12 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v13 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v9 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v26 = 0x1000000;
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (int)&byte_18009EBE7,
        *((_QWORD *)this + 34) + 8,
        (__int64)&v16,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v25,
        (__int64)&v9,
        (__int64)&v24,
        (__int64)&v15,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v12,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v17);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 4u
      && (*(_QWORD *)(v6 + 16) & 0x40) != 0
      && (*(_QWORD *)(v6 + 24) & 0x40LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)byte_18009EFE5,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_SetupSandbox *)((char *)this + 288));
}

```

## disassembly

```asm
0x180034090  mov     [rsp-8+arg_8], rbx
0x180034095  mov     [rsp-8+arg_10], rdi
0x18003409a  push    rbp
0x18003409b  mov     rbp, rsp
0x18003409e  sub     rsp, 140h
0x1800340a5  mov     rbx, rcx
0x1800340a8  mov     rdi, [rcx+110h]
0x1800340af  mov     eax, [rdi+48h]
0x1800340b2  test    eax, eax
0x1800340b4  jns     loc_18003429C
0x1800340ba  add     rdi, 50h ; 'P'
0x1800340be  cmp     eax, [rdi+8]
0x1800340c1  jnz     loc_18003429C
0x1800340c7  test    rdi, rdi
0x1800340ca  jz      loc_18003429C
0x1800340d0  mov     [rbp+SRWLock], 0
0x1800340d8  lea     rdx, [rbp+SRWLock]
0x1800340dc  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800340e1  mov     rax, [rbx+110h]
0x1800340e8  mov     dword ptr [rax], 2
0x1800340ee  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800340f2  test    rcx, rcx
0x1800340f5  jz      short loc_180034103
0x1800340f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800340fe  nop     dword ptr [rax+rax+00h]
0x180034103  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180034108  mov     rcx, [rax+8]; int
0x18003410c  mov     eax, [rcx]
0x18003410e  cmp     eax, 4
0x180034111  jbe     loc_18003434D
0x180034117  mov     rdx, [rcx+18h]
0x18003411b  mov     rax, [rcx+10h]
0x18003411f  test    al, 40h
0x180034121  jz      loc_18003434D
0x180034127  mov     rax, rdx
0x18003412a  and     eax, 40h
0x18003412d  cmp     rax, rdx
0x180034130  jnz     loc_18003434D
0x180034136  mov     rax, [rdi+30h]
0x18003413a  mov     [rbp+var_50], rax
0x18003413e  mov     eax, [rdi+44h]
0x180034141  mov     dword ptr [rbp+var_78+4], eax
0x180034144  mov     eax, [rdi+10h]
0x180034147  mov     dword ptr [rbp+var_70], eax
0x18003414a  mov     rax, [rdi+78h]
0x18003414e  mov     [rbp+var_48], rax
0x180034152  mov     rax, [rdi+70h]
0x180034156  mov     [rbp+var_40], rax
0x18003415a  mov     eax, [rdi+68h]
0x18003415d  mov     dword ptr [rbp+var_70+4], eax
0x180034160  mov     rax, [rdi+60h]
0x180034164  mov     [rbp+var_38], rax
0x180034168  mov     rax, [rdi+58h]
0x18003416c  mov     [rbp+var_30], rax
0x180034170  mov     eax, [rdi+50h]
0x180034173  mov     dword ptr [rbp+var_68], eax
0x180034176  mov     rax, [rdi+48h]
0x18003417a  mov     [rbp+var_28], rax
0x18003417e  mov     eax, [rdi+20h]
0x180034181  mov     dword ptr [rbp+var_68+4], eax
0x180034184  mov     rax, [rdi+18h]
0x180034188  mov     [rbp+var_20], rax
0x18003418c  mov     eax, [rdi]
0x18003418e  mov     [rbp+var_60], eax
0x180034191  mov     rax, [rdi+80h]
0x180034198  mov     [rbp+var_18], rax
0x18003419c  mov     eax, [rdi+40h]
0x18003419f  mov     dword ptr [rbp+var_78], eax
0x1800341a2  mov     rax, [rdi+38h]
0x1800341a6  mov     [rbp+var_10], rax
0x1800341aa  mov     eax, [rdi+8]
0x1800341ad  mov     dword ptr [rbp+SRWLock], eax
0x1800341b0  mov     [rbp+var_8], 1000000h
0x1800341b8  mov     [rbp+var_58], 0
0x1800341c0  mov     r8, [rbx+110h]
0x1800341c7  add     r8, 8; int
0x1800341cb  lea     rax, [rbp+var_50]
0x1800341cf  mov     [rsp+140h+var_90], rax; __int64
0x1800341d7  lea     rax, [rbp+var_78+4]
0x1800341db  mov     [rsp+140h+var_98], rax; __int64
0x1800341e3  lea     rax, [rbp+var_70]
0x1800341e7  mov     [rsp+140h+var_A0], rax; __int64
0x1800341ef  lea     rax, [rbp+var_48]
0x1800341f3  mov     [rsp+140h+var_A8], rax; __int64
0x1800341fb  lea     rax, [rbp+var_40]
0x1800341ff  mov     [rsp+140h+var_B0], rax; __int64
0x180034207  lea     rax, [rbp+var_70+4]
0x18003420b  mov     [rsp+140h+var_B8], rax; __int64
0x180034213  lea     rax, [rbp+var_38]
0x180034217  mov     [rsp+140h+var_C0], rax; __int64
0x18003421f  lea     rax, [rbp+var_30]
0x180034223  mov     [rsp+140h+var_C8], rax; __int64
0x180034228  lea     rax, [rbp+var_68]
0x18003422c  mov     [rsp+140h+var_D0], rax; __int64
0x180034231  lea     rax, [rbp+var_28]
0x180034235  mov     [rsp+140h+var_D8], rax; __int64
0x18003423a  lea     rax, [rbp+var_68+4]
0x18003423e  mov     [rsp+140h+var_E0], rax; __int64
0x180034243  lea     rax, [rbp+var_20]
0x180034247  mov     [rsp+140h+var_E8], rax; __int64
0x18003424c  lea     rax, [rbp+var_60]
0x180034250  mov     [rsp+140h+var_F0], rax; __int64
0x180034255  lea     rax, [rbp+var_18]
0x180034259  mov     [rsp+140h+var_F8], rax; __int64
0x18003425e  lea     rax, [rbp+var_78]
0x180034262  mov     [rsp+140h+var_100], rax; __int64
0x180034267  lea     rax, [rbp+var_10]
0x18003426b  mov     [rsp+140h+var_108], rax; __int64
0x180034270  lea     rax, [rbp+SRWLock]
0x180034274  mov     [rsp+140h+var_110], rax; __int64
0x180034279  lea     rax, [rbp+var_8]
0x18003427d  mov     [rsp+140h+var_118], rax; __int64
0x180034282  lea     rax, [rbp+var_58]
0x180034286  mov     [rsp+140h+var_120], rax; __int64
0x18003428b  lea     rdx, byte_18009EBE7; int
0x180034292  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180034297  jmp     loc_18003434D
0x18003429c  mov     [rbp+SRWLock], 0
0x1800342a4  lea     rdx, [rbp+SRWLock]
0x1800342a8  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800342ad  mov     rax, [rbx+110h]
0x1800342b4  mov     dword ptr [rax], 2
0x1800342ba  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800342be  test    rcx, rcx
0x1800342c1  jz      short loc_1800342CF
0x1800342c3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800342ca  nop     dword ptr [rax+rax+00h]
0x1800342cf  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x1800342d4  mov     rdi, [rax+8]
0x1800342d8  mov     eax, [rdi]
0x1800342da  cmp     eax, 4
0x1800342dd  jbe     short loc_18003434D
0x1800342df  mov     rcx, [rdi+18h]
0x1800342e3  mov     rax, [rdi+10h]
0x1800342e7  test    al, 40h
0x1800342e9  jz      short loc_18003434D
0x1800342eb  mov     rax, rcx
0x1800342ee  and     eax, 40h
0x1800342f1  cmp     rax, rcx
0x1800342f4  jnz     short loc_18003434D
0x1800342f6  call    cs:__imp_GetCurrentThreadId
0x1800342fd  nop     dword ptr [rax+rax+00h]
0x180034302  mov     dword ptr [rbp+SRWLock], eax
0x180034305  mov     r8, [rbx+110h]
0x18003430c  mov     eax, [r8+48h]
0x180034310  mov     dword ptr [rbp+var_78], eax
0x180034313  mov     [rbp+var_58], 0
0x18003431b  add     r8, 8
0x18003431f  lea     rax, [rbp+SRWLock]
0x180034323  mov     [rsp+140h+var_110], rax
0x180034328  lea     rax, [rbp+var_78]
0x18003432c  mov     [rsp+140h+var_118], rax
0x180034331  lea     rax, [rbp+var_58]
0x180034335  mov     [rsp+140h+var_120], rax
0x18003433a  xor     r9d, r9d
0x18003433d  lea     rdx, byte_18009EFE5
0x180034344  mov     rcx, rdi
0x180034347  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003434c  nop
0x18003434d  lea     rcx, [rbx+120h]; this
0x180034354  cmp     dword ptr [rcx+18h], 0
0x180034358  jz      short loc_180034360
0x18003435a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003435f  nop
0x180034360  lea     r11, [rsp+140h+var_s0]
0x180034368  mov     rbx, [r11+18h]
0x18003436c  mov     rdi, [r11+20h]
0x180034370  mov     rsp, r11
0x180034373  pop     rbp
0x180034374  retn
```
