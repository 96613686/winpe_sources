# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume::StopActivity(void)

- ea: `0x180032910`
- end: `0x180032bf6`
- name: `?StopActivity@GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x180032910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032977`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032b43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032977`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032b43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032b76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032b76`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume *this)
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
        (int)&dword_18009EA74,
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
        (unsigned int)byte_18009E27B,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume *)((char *)this + 288));
}

```

## disassembly

```asm
0x180032910  mov     [rsp-8+arg_8], rbx
0x180032915  mov     [rsp-8+arg_10], rdi
0x18003291a  push    rbp
0x18003291b  mov     rbp, rsp
0x18003291e  sub     rsp, 140h
0x180032925  mov     rbx, rcx
0x180032928  mov     rdi, [rcx+110h]
0x18003292f  mov     eax, [rdi+48h]
0x180032932  test    eax, eax
0x180032934  jns     loc_180032B1C
0x18003293a  add     rdi, 50h ; 'P'
0x18003293e  cmp     eax, [rdi+8]
0x180032941  jnz     loc_180032B1C
0x180032947  test    rdi, rdi
0x18003294a  jz      loc_180032B1C
0x180032950  mov     [rbp+SRWLock], 0
0x180032958  lea     rdx, [rbp+SRWLock]
0x18003295c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032961  mov     rax, [rbx+110h]
0x180032968  mov     dword ptr [rax], 2
0x18003296e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180032972  test    rcx, rcx
0x180032975  jz      short loc_180032983
0x180032977  call    cs:__imp_ReleaseSRWLockExclusive
0x18003297e  nop     dword ptr [rax+rax+00h]
0x180032983  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180032988  mov     rcx, [rax+8]; int
0x18003298c  mov     eax, [rcx]
0x18003298e  cmp     eax, 4
0x180032991  jbe     loc_180032BCD
0x180032997  mov     rdx, [rcx+18h]
0x18003299b  mov     rax, [rcx+10h]
0x18003299f  test    al, 40h
0x1800329a1  jz      loc_180032BCD
0x1800329a7  mov     rax, rdx
0x1800329aa  and     eax, 40h
0x1800329ad  cmp     rax, rdx
0x1800329b0  jnz     loc_180032BCD
0x1800329b6  mov     rax, [rdi+30h]
0x1800329ba  mov     [rbp+var_50], rax
0x1800329be  mov     eax, [rdi+44h]
0x1800329c1  mov     dword ptr [rbp+var_78+4], eax
0x1800329c4  mov     eax, [rdi+10h]
0x1800329c7  mov     dword ptr [rbp+var_70], eax
0x1800329ca  mov     rax, [rdi+78h]
0x1800329ce  mov     [rbp+var_48], rax
0x1800329d2  mov     rax, [rdi+70h]
0x1800329d6  mov     [rbp+var_40], rax
0x1800329da  mov     eax, [rdi+68h]
0x1800329dd  mov     dword ptr [rbp+var_70+4], eax
0x1800329e0  mov     rax, [rdi+60h]
0x1800329e4  mov     [rbp+var_38], rax
0x1800329e8  mov     rax, [rdi+58h]
0x1800329ec  mov     [rbp+var_30], rax
0x1800329f0  mov     eax, [rdi+50h]
0x1800329f3  mov     dword ptr [rbp+var_68], eax
0x1800329f6  mov     rax, [rdi+48h]
0x1800329fa  mov     [rbp+var_28], rax
0x1800329fe  mov     eax, [rdi+20h]
0x180032a01  mov     dword ptr [rbp+var_68+4], eax
0x180032a04  mov     rax, [rdi+18h]
0x180032a08  mov     [rbp+var_20], rax
0x180032a0c  mov     eax, [rdi]
0x180032a0e  mov     [rbp+var_60], eax
0x180032a11  mov     rax, [rdi+80h]
0x180032a18  mov     [rbp+var_18], rax
0x180032a1c  mov     eax, [rdi+40h]
0x180032a1f  mov     dword ptr [rbp+var_78], eax
0x180032a22  mov     rax, [rdi+38h]
0x180032a26  mov     [rbp+var_10], rax
0x180032a2a  mov     eax, [rdi+8]
0x180032a2d  mov     dword ptr [rbp+SRWLock], eax
0x180032a30  mov     [rbp+var_8], 1000000h
0x180032a38  mov     [rbp+var_58], 0
0x180032a40  mov     r8, [rbx+110h]
0x180032a47  add     r8, 8; int
0x180032a4b  lea     rax, [rbp+var_50]
0x180032a4f  mov     [rsp+140h+var_90], rax; __int64
0x180032a57  lea     rax, [rbp+var_78+4]
0x180032a5b  mov     [rsp+140h+var_98], rax; __int64
0x180032a63  lea     rax, [rbp+var_70]
0x180032a67  mov     [rsp+140h+var_A0], rax; __int64
0x180032a6f  lea     rax, [rbp+var_48]
0x180032a73  mov     [rsp+140h+var_A8], rax; __int64
0x180032a7b  lea     rax, [rbp+var_40]
0x180032a7f  mov     [rsp+140h+var_B0], rax; __int64
0x180032a87  lea     rax, [rbp+var_70+4]
0x180032a8b  mov     [rsp+140h+var_B8], rax; __int64
0x180032a93  lea     rax, [rbp+var_38]
0x180032a97  mov     [rsp+140h+var_C0], rax; __int64
0x180032a9f  lea     rax, [rbp+var_30]
0x180032aa3  mov     [rsp+140h+var_C8], rax; __int64
0x180032aa8  lea     rax, [rbp+var_68]
0x180032aac  mov     [rsp+140h+var_D0], rax; __int64
0x180032ab1  lea     rax, [rbp+var_28]
0x180032ab5  mov     [rsp+140h+var_D8], rax; __int64
0x180032aba  lea     rax, [rbp+var_68+4]
0x180032abe  mov     [rsp+140h+var_E0], rax; __int64
0x180032ac3  lea     rax, [rbp+var_20]
0x180032ac7  mov     [rsp+140h+var_E8], rax; __int64
0x180032acc  lea     rax, [rbp+var_60]
0x180032ad0  mov     [rsp+140h+var_F0], rax; __int64
0x180032ad5  lea     rax, [rbp+var_18]
0x180032ad9  mov     [rsp+140h+var_F8], rax; __int64
0x180032ade  lea     rax, [rbp+var_78]
0x180032ae2  mov     [rsp+140h+var_100], rax; __int64
0x180032ae7  lea     rax, [rbp+var_10]
0x180032aeb  mov     [rsp+140h+var_108], rax; __int64
0x180032af0  lea     rax, [rbp+SRWLock]
0x180032af4  mov     [rsp+140h+var_110], rax; __int64
0x180032af9  lea     rax, [rbp+var_8]
0x180032afd  mov     [rsp+140h+var_118], rax; __int64
0x180032b02  lea     rax, [rbp+var_58]
0x180032b06  mov     [rsp+140h+var_120], rax; __int64
0x180032b0b  lea     rdx, dword_18009EA74; int
0x180032b12  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180032b17  jmp     loc_180032BCD
0x180032b1c  mov     [rbp+SRWLock], 0
0x180032b24  lea     rdx, [rbp+SRWLock]
0x180032b28  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032b2d  mov     rax, [rbx+110h]
0x180032b34  mov     dword ptr [rax], 2
0x180032b3a  mov     rcx, [rbp+SRWLock]; SRWLock
0x180032b3e  test    rcx, rcx
0x180032b41  jz      short loc_180032B4F
0x180032b43  call    cs:__imp_ReleaseSRWLockExclusive
0x180032b4a  nop     dword ptr [rax+rax+00h]
0x180032b4f  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180032b54  mov     rdi, [rax+8]
0x180032b58  mov     eax, [rdi]
0x180032b5a  cmp     eax, 4
0x180032b5d  jbe     short loc_180032BCD
0x180032b5f  mov     rcx, [rdi+18h]
0x180032b63  mov     rax, [rdi+10h]
0x180032b67  test    al, 40h
0x180032b69  jz      short loc_180032BCD
0x180032b6b  mov     rax, rcx
0x180032b6e  and     eax, 40h
0x180032b71  cmp     rax, rcx
0x180032b74  jnz     short loc_180032BCD
0x180032b76  call    cs:__imp_GetCurrentThreadId
0x180032b7d  nop     dword ptr [rax+rax+00h]
0x180032b82  mov     dword ptr [rbp+SRWLock], eax
0x180032b85  mov     r8, [rbx+110h]
0x180032b8c  mov     eax, [r8+48h]
0x180032b90  mov     dword ptr [rbp+var_78], eax
0x180032b93  mov     [rbp+var_58], 0
0x180032b9b  add     r8, 8
0x180032b9f  lea     rax, [rbp+SRWLock]
0x180032ba3  mov     [rsp+140h+var_110], rax
0x180032ba8  lea     rax, [rbp+var_78]
0x180032bac  mov     [rsp+140h+var_118], rax
0x180032bb1  lea     rax, [rbp+var_58]
0x180032bb5  mov     [rsp+140h+var_120], rax
0x180032bba  xor     r9d, r9d
0x180032bbd  lea     rdx, byte_18009E27B
0x180032bc4  mov     rcx, rdi
0x180032bc7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180032bcc  nop
0x180032bcd  lea     rcx, [rbx+120h]; this
0x180032bd4  cmp     dword ptr [rcx+18h], 0
0x180032bd8  jz      short loc_180032BE0
0x180032bda  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180032bdf  nop
0x180032be0  lea     r11, [rsp+140h+var_s0]
0x180032be8  mov     rbx, [r11+18h]
0x180032bec  mov     rdi, [r11+20h]
0x180032bf0  mov     rsp, r11
0x180032bf3  pop     rbp
0x180032bf4  retn
```
