# ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification::StopActivity(void)

- ea: `0x18003f760`
- end: `0x18003fa53`
- name: `?StopActivity@ClientLib_HcsNotification@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x18003f760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f7c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f99b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f7c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f9d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f9d3`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  int v15; // [rsp+D0h] [rbp-70h] BYREF
  int v16; // [rsp+D4h] [rbp-6Ch] BYREF
  int v17; // [rsp+D8h] [rbp-68h] BYREF
  int v18; // [rsp+DCh] [rbp-64h] BYREF
  int v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+128h] [rbp-18h] BYREF
  __int64 v29; // [rsp+130h] [rbp-10h] BYREF
  __int64 v30; // [rsp+138h] [rbp-8h] BYREF

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
    v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x10000LL) != 0 && (v7 & 0x10000) == v7 )
      {
        v21 = *((_QWORD *)v4 + 6);
        v14 = v4[17];
        v15 = v4[4];
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v16 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v17 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v18 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v19 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v6,
          (int)&byte_1800A0329,
          *((_QWORD *)this + 34) + 8,
          (__int64)&v20,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v13,
          (__int64)&v28,
          (__int64)&v19,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v16,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v21);
      }
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
    v8 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x10000LL) != 0 && (v10 & 0x10000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800A0B15,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003f760  mov     [rsp-8+arg_8], rbx
0x18003f765  mov     [rsp-8+arg_10], rdi
0x18003f76a  push    rbp
0x18003f76b  mov     rbp, rsp
0x18003f76e  sub     rsp, 140h
0x18003f775  mov     rbx, rcx
0x18003f778  mov     rdi, [rcx+110h]
0x18003f77f  mov     eax, [rdi+48h]
0x18003f782  test    eax, eax
0x18003f784  jns     loc_18003F974
0x18003f78a  add     rdi, 50h ; 'P'
0x18003f78e  cmp     eax, [rdi+8]
0x18003f791  jnz     loc_18003F974
0x18003f797  test    rdi, rdi
0x18003f79a  jz      loc_18003F974
0x18003f7a0  mov     [rbp+SRWLock], 0
0x18003f7a8  lea     rdx, [rbp+SRWLock]
0x18003f7ac  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003f7b1  mov     rax, [rbx+110h]
0x18003f7b8  mov     dword ptr [rax], 2
0x18003f7be  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003f7c2  test    rcx, rcx
0x18003f7c5  jz      short loc_18003F7D3
0x18003f7c7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f7ce  nop     dword ptr [rax+rax+00h]
0x18003f7d3  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003f7d8  mov     r9, rax
0x18003f7db  mov     ecx, [rax]
0x18003f7dd  cmp     ecx, 4
0x18003f7e0  jbe     loc_18003FA2A
0x18003f7e6  mov     rax, [rax+18h]
0x18003f7ea  mov     rcx, [r9+10h]
0x18003f7ee  mov     edx, 10000h
0x18003f7f3  test    rdx, rcx
0x18003f7f6  jz      loc_18003FA2A
0x18003f7fc  mov     rcx, rax
0x18003f7ff  and     rcx, rdx
0x18003f802  cmp     rcx, rax
0x18003f805  jnz     loc_18003FA2A
0x18003f80b  mov     rax, [rdi+30h]
0x18003f80f  mov     [rbp+var_50], rax
0x18003f813  mov     eax, [rdi+44h]
0x18003f816  mov     dword ptr [rbp+var_78+4], eax
0x18003f819  mov     eax, [rdi+10h]
0x18003f81c  mov     dword ptr [rbp+var_70], eax
0x18003f81f  mov     rax, [rdi+78h]
0x18003f823  mov     [rbp+var_48], rax
0x18003f827  mov     rax, [rdi+70h]
0x18003f82b  mov     [rbp+var_40], rax
0x18003f82f  mov     eax, [rdi+68h]
0x18003f832  mov     dword ptr [rbp+var_70+4], eax
0x18003f835  mov     rax, [rdi+60h]
0x18003f839  mov     [rbp+var_38], rax
0x18003f83d  mov     rax, [rdi+58h]
0x18003f841  mov     [rbp+var_30], rax
0x18003f845  mov     eax, [rdi+50h]
0x18003f848  mov     dword ptr [rbp+var_68], eax
0x18003f84b  mov     rax, [rdi+48h]
0x18003f84f  mov     [rbp+var_28], rax
0x18003f853  mov     eax, [rdi+20h]
0x18003f856  mov     dword ptr [rbp+var_68+4], eax
0x18003f859  mov     rax, [rdi+18h]
0x18003f85d  mov     [rbp+var_20], rax
0x18003f861  mov     eax, [rdi]
0x18003f863  mov     [rbp+var_60], eax
0x18003f866  mov     rax, [rdi+80h]
0x18003f86d  mov     [rbp+var_18], rax
0x18003f871  mov     eax, [rdi+40h]
0x18003f874  mov     dword ptr [rbp+var_78], eax
0x18003f877  mov     rax, [rdi+38h]
0x18003f87b  mov     [rbp+var_10], rax
0x18003f87f  mov     eax, [rdi+8]
0x18003f882  mov     dword ptr [rbp+SRWLock], eax
0x18003f885  mov     [rbp+var_8], 1000000h
0x18003f88d  mov     [rbp+var_58], 0
0x18003f895  mov     r8, [rbx+110h]
0x18003f89c  add     r8, 8; int
0x18003f8a0  lea     rax, [rbp+var_50]
0x18003f8a4  mov     [rsp+140h+var_90], rax; __int64
0x18003f8ac  lea     rax, [rbp+var_78+4]
0x18003f8b0  mov     [rsp+140h+var_98], rax; __int64
0x18003f8b8  lea     rax, [rbp+var_70]
0x18003f8bc  mov     [rsp+140h+var_A0], rax; __int64
0x18003f8c4  lea     rax, [rbp+var_48]
0x18003f8c8  mov     [rsp+140h+var_A8], rax; __int64
0x18003f8d0  lea     rax, [rbp+var_40]
0x18003f8d4  mov     [rsp+140h+var_B0], rax; __int64
0x18003f8dc  lea     rax, [rbp+var_70+4]
0x18003f8e0  mov     [rsp+140h+var_B8], rax; __int64
0x18003f8e8  lea     rax, [rbp+var_38]
0x18003f8ec  mov     [rsp+140h+var_C0], rax; __int64
0x18003f8f4  lea     rax, [rbp+var_30]
0x18003f8f8  mov     [rsp+140h+var_C8], rax; __int64
0x18003f8fd  lea     rax, [rbp+var_68]
0x18003f901  mov     [rsp+140h+var_D0], rax; __int64
0x18003f906  lea     rax, [rbp+var_28]
0x18003f90a  mov     [rsp+140h+var_D8], rax; __int64
0x18003f90f  lea     rax, [rbp+var_68+4]
0x18003f913  mov     [rsp+140h+var_E0], rax; __int64
0x18003f918  lea     rax, [rbp+var_20]
0x18003f91c  mov     [rsp+140h+var_E8], rax; __int64
0x18003f921  lea     rax, [rbp+var_60]
0x18003f925  mov     [rsp+140h+var_F0], rax; __int64
0x18003f92a  lea     rax, [rbp+var_18]
0x18003f92e  mov     [rsp+140h+var_F8], rax; __int64
0x18003f933  lea     rax, [rbp+var_78]
0x18003f937  mov     [rsp+140h+var_100], rax; __int64
0x18003f93c  lea     rax, [rbp+var_10]
0x18003f940  mov     [rsp+140h+var_108], rax; __int64
0x18003f945  lea     rax, [rbp+SRWLock]
0x18003f949  mov     [rsp+140h+var_110], rax; __int64
0x18003f94e  lea     rax, [rbp+var_8]
0x18003f952  mov     [rsp+140h+var_118], rax; __int64
0x18003f957  lea     rax, [rbp+var_58]
0x18003f95b  mov     [rsp+140h+var_120], rax; __int64
0x18003f960  lea     rdx, byte_1800A0329; int
0x18003f967  mov     rcx, r9; int
0x18003f96a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003f96f  jmp     loc_18003FA2A
0x18003f974  mov     [rbp+SRWLock], 0
0x18003f97c  lea     rdx, [rbp+SRWLock]
0x18003f980  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003f985  mov     rax, [rbx+110h]
0x18003f98c  mov     dword ptr [rax], 2
0x18003f992  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003f996  test    rcx, rcx
0x18003f999  jz      short loc_18003F9A7
0x18003f99b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f9a2  nop     dword ptr [rax+rax+00h]
0x18003f9a7  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003f9ac  mov     rdi, rax
0x18003f9af  mov     ecx, [rax]
0x18003f9b1  cmp     ecx, 4
0x18003f9b4  jbe     short loc_18003FA2A
0x18003f9b6  mov     rax, [rax+18h]
0x18003f9ba  mov     rcx, [rdi+10h]
0x18003f9be  mov     edx, 10000h
0x18003f9c3  test    rdx, rcx
0x18003f9c6  jz      short loc_18003FA2A
0x18003f9c8  mov     rcx, rax
0x18003f9cb  and     rcx, rdx
0x18003f9ce  cmp     rcx, rax
0x18003f9d1  jnz     short loc_18003FA2A
0x18003f9d3  call    cs:__imp_GetCurrentThreadId
0x18003f9da  nop     dword ptr [rax+rax+00h]
0x18003f9df  mov     dword ptr [rbp+SRWLock], eax
0x18003f9e2  mov     r8, [rbx+110h]
0x18003f9e9  mov     eax, [r8+48h]
0x18003f9ed  mov     dword ptr [rbp+var_78], eax
0x18003f9f0  mov     [rbp+var_58], 0
0x18003f9f8  add     r8, 8
0x18003f9fc  lea     rax, [rbp+SRWLock]
0x18003fa00  mov     [rsp+140h+var_110], rax
0x18003fa05  lea     rax, [rbp+var_78]
0x18003fa09  mov     [rsp+140h+var_118], rax
0x18003fa0e  lea     rax, [rbp+var_58]
0x18003fa12  mov     [rsp+140h+var_120], rax
0x18003fa17  xor     r9d, r9d
0x18003fa1a  lea     rdx, byte_1800A0B15
0x18003fa21  mov     rcx, rdi
0x18003fa24  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003fa29  nop
0x18003fa2a  lea     rcx, [rbx+120h]; this
0x18003fa31  cmp     dword ptr [rcx+18h], 0
0x18003fa35  jz      short loc_18003FA3D
0x18003fa37  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003fa3c  nop
0x18003fa3d  lea     r11, [rsp+140h+var_s0]
0x18003fa45  mov     rbx, [r11+18h]
0x18003fa49  mov     rdi, [r11+20h]
0x18003fa4d  mov     rsp, r11
0x18003fa50  pop     rbp
0x18003fa51  retn
```
