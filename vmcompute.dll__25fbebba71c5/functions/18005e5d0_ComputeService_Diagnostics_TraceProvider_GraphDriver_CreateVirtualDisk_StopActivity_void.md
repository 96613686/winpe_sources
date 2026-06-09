# ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::StopActivity(void)

- ea: `0x18005e5d0`
- end: `0x18005e8b9`
- name: `?StopActivity@GraphDriver_CreateVirtualDisk@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x180021d1c`
- `0x18005dc20`
- `0x18005e5d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e637`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e806`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e637`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e806`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e839`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::StopActivity(
        ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk *this)
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
    v5 = ComputeService::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x40) != 0 && (v7 & 0x40) == v7 )
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
          (int)&word_1800A1F4E,
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
    v8 = ComputeService::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x40) != 0 && (v10 & 0x40) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800A1E3D,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk *)((char *)this + 288));
}

```

## disassembly

```asm
0x18005e5d0  mov     [rsp-8+arg_8], rbx
0x18005e5d5  mov     [rsp-8+arg_10], rdi
0x18005e5da  push    rbp
0x18005e5db  mov     rbp, rsp
0x18005e5de  sub     rsp, 140h
0x18005e5e5  mov     rbx, rcx
0x18005e5e8  mov     rdi, [rcx+110h]
0x18005e5ef  mov     eax, [rdi+48h]
0x18005e5f2  test    eax, eax
0x18005e5f4  jns     loc_18005E7DF
0x18005e5fa  add     rdi, 50h ; 'P'
0x18005e5fe  cmp     eax, [rdi+8]
0x18005e601  jnz     loc_18005E7DF
0x18005e607  test    rdi, rdi
0x18005e60a  jz      loc_18005E7DF
0x18005e610  mov     [rbp+SRWLock], 0
0x18005e618  lea     rdx, [rbp+SRWLock]
0x18005e61c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005e621  mov     rax, [rbx+110h]
0x18005e628  mov     dword ptr [rax], 2
0x18005e62e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005e632  test    rcx, rcx
0x18005e635  jz      short loc_18005E643
0x18005e637  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e63e  nop     dword ptr [rax+rax+00h]
0x18005e643  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x18005e648  mov     r9, rax
0x18005e64b  mov     ecx, [rax]
0x18005e64d  cmp     ecx, 4
0x18005e650  jbe     loc_18005E890
0x18005e656  mov     rax, [rax+18h]
0x18005e65a  mov     rcx, [r9+10h]
0x18005e65e  test    cl, 40h
0x18005e661  jz      loc_18005E890
0x18005e667  mov     rcx, rax
0x18005e66a  and     ecx, 40h
0x18005e66d  cmp     rcx, rax
0x18005e670  jnz     loc_18005E890
0x18005e676  mov     rax, [rdi+30h]
0x18005e67a  mov     [rbp+var_50], rax
0x18005e67e  mov     eax, [rdi+44h]
0x18005e681  mov     dword ptr [rbp+var_78+4], eax
0x18005e684  mov     eax, [rdi+10h]
0x18005e687  mov     dword ptr [rbp+var_70], eax
0x18005e68a  mov     rax, [rdi+78h]
0x18005e68e  mov     [rbp+var_48], rax
0x18005e692  mov     rax, [rdi+70h]
0x18005e696  mov     [rbp+var_40], rax
0x18005e69a  mov     eax, [rdi+68h]
0x18005e69d  mov     dword ptr [rbp+var_70+4], eax
0x18005e6a0  mov     rax, [rdi+60h]
0x18005e6a4  mov     [rbp+var_38], rax
0x18005e6a8  mov     rax, [rdi+58h]
0x18005e6ac  mov     [rbp+var_30], rax
0x18005e6b0  mov     eax, [rdi+50h]
0x18005e6b3  mov     dword ptr [rbp+var_68], eax
0x18005e6b6  mov     rax, [rdi+48h]
0x18005e6ba  mov     [rbp+var_28], rax
0x18005e6be  mov     eax, [rdi+20h]
0x18005e6c1  mov     dword ptr [rbp+var_68+4], eax
0x18005e6c4  mov     rax, [rdi+18h]
0x18005e6c8  mov     [rbp+var_20], rax
0x18005e6cc  mov     eax, [rdi]
0x18005e6ce  mov     [rbp+var_60], eax
0x18005e6d1  mov     rax, [rdi+80h]
0x18005e6d8  mov     [rbp+var_18], rax
0x18005e6dc  mov     eax, [rdi+40h]
0x18005e6df  mov     dword ptr [rbp+var_78], eax
0x18005e6e2  mov     rax, [rdi+38h]
0x18005e6e6  mov     [rbp+var_10], rax
0x18005e6ea  mov     eax, [rdi+8]
0x18005e6ed  mov     dword ptr [rbp+SRWLock], eax
0x18005e6f0  mov     [rbp+var_8], 1000000h
0x18005e6f8  mov     [rbp+var_58], 0
0x18005e700  mov     r8, [rbx+110h]
0x18005e707  add     r8, 8; int
0x18005e70b  lea     rax, [rbp+var_50]
0x18005e70f  mov     [rsp+140h+var_90], rax; __int64
0x18005e717  lea     rax, [rbp+var_78+4]
0x18005e71b  mov     [rsp+140h+var_98], rax; __int64
0x18005e723  lea     rax, [rbp+var_70]
0x18005e727  mov     [rsp+140h+var_A0], rax; __int64
0x18005e72f  lea     rax, [rbp+var_48]
0x18005e733  mov     [rsp+140h+var_A8], rax; __int64
0x18005e73b  lea     rax, [rbp+var_40]
0x18005e73f  mov     [rsp+140h+var_B0], rax; __int64
0x18005e747  lea     rax, [rbp+var_70+4]
0x18005e74b  mov     [rsp+140h+var_B8], rax; __int64
0x18005e753  lea     rax, [rbp+var_38]
0x18005e757  mov     [rsp+140h+var_C0], rax; __int64
0x18005e75f  lea     rax, [rbp+var_30]
0x18005e763  mov     [rsp+140h+var_C8], rax; __int64
0x18005e768  lea     rax, [rbp+var_68]
0x18005e76c  mov     [rsp+140h+var_D0], rax; __int64
0x18005e771  lea     rax, [rbp+var_28]
0x18005e775  mov     [rsp+140h+var_D8], rax; __int64
0x18005e77a  lea     rax, [rbp+var_68+4]
0x18005e77e  mov     [rsp+140h+var_E0], rax; __int64
0x18005e783  lea     rax, [rbp+var_20]
0x18005e787  mov     [rsp+140h+var_E8], rax; __int64
0x18005e78c  lea     rax, [rbp+var_60]
0x18005e790  mov     [rsp+140h+var_F0], rax; __int64
0x18005e795  lea     rax, [rbp+var_18]
0x18005e799  mov     [rsp+140h+var_F8], rax; __int64
0x18005e79e  lea     rax, [rbp+var_78]
0x18005e7a2  mov     [rsp+140h+var_100], rax; __int64
0x18005e7a7  lea     rax, [rbp+var_10]
0x18005e7ab  mov     [rsp+140h+var_108], rax; __int64
0x18005e7b0  lea     rax, [rbp+SRWLock]
0x18005e7b4  mov     [rsp+140h+var_110], rax; __int64
0x18005e7b9  lea     rax, [rbp+var_8]
0x18005e7bd  mov     [rsp+140h+var_118], rax; __int64
0x18005e7c2  lea     rax, [rbp+var_58]
0x18005e7c6  mov     [rsp+140h+var_120], rax; __int64
0x18005e7cb  lea     rdx, word_1800A1F4E; int
0x18005e7d2  mov     rcx, r9; int
0x18005e7d5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005e7da  jmp     loc_18005E890
0x18005e7df  mov     [rbp+SRWLock], 0
0x18005e7e7  lea     rdx, [rbp+SRWLock]
0x18005e7eb  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005e7f0  mov     rax, [rbx+110h]
0x18005e7f7  mov     dword ptr [rax], 2
0x18005e7fd  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005e801  test    rcx, rcx
0x18005e804  jz      short loc_18005E812
0x18005e806  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e80d  nop     dword ptr [rax+rax+00h]
0x18005e812  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x18005e817  mov     rdi, rax
0x18005e81a  mov     ecx, [rax]
0x18005e81c  cmp     ecx, 4
0x18005e81f  jbe     short loc_18005E890
0x18005e821  mov     rax, [rax+18h]
0x18005e825  mov     rcx, [rdi+10h]
0x18005e829  test    cl, 40h
0x18005e82c  jz      short loc_18005E890
0x18005e82e  mov     rcx, rax
0x18005e831  and     ecx, 40h
0x18005e834  cmp     rcx, rax
0x18005e837  jnz     short loc_18005E890
0x18005e839  call    cs:__imp_GetCurrentThreadId
0x18005e840  nop     dword ptr [rax+rax+00h]
0x18005e845  mov     dword ptr [rbp+SRWLock], eax
0x18005e848  mov     r8, [rbx+110h]
0x18005e84f  mov     eax, [r8+48h]
0x18005e853  mov     dword ptr [rbp+var_78], eax
0x18005e856  mov     [rbp+var_58], 0
0x18005e85e  add     r8, 8
0x18005e862  lea     rax, [rbp+SRWLock]
0x18005e866  mov     [rsp+140h+var_110], rax
0x18005e86b  lea     rax, [rbp+var_78]
0x18005e86f  mov     [rsp+140h+var_118], rax
0x18005e874  lea     rax, [rbp+var_58]
0x18005e878  mov     [rsp+140h+var_120], rax
0x18005e87d  xor     r9d, r9d
0x18005e880  lea     rdx, byte_1800A1E3D
0x18005e887  mov     rcx, rdi
0x18005e88a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005e88f  nop
0x18005e890  lea     rcx, [rbx+120h]; this
0x18005e897  cmp     dword ptr [rcx+18h], 0
0x18005e89b  jz      short loc_18005E8A3
0x18005e89d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005e8a2  nop
0x18005e8a3  lea     r11, [rsp+140h+var_s0]
0x18005e8ab  mov     rbx, [r11+18h]
0x18005e8af  mov     rdi, [r11+20h]
0x18005e8b3  mov     rsp, r11
0x18005e8b6  pop     rbp
0x18005e8b7  retn
```
