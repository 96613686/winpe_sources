# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess::StopActivity(void)

- ea: `0x18004b3f0`
- end: `0x18004b6d9`
- name: `?StopActivity@VmFileUtilities_GrantVmGroupAccess@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x18004b3f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b626`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b626`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b659`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b659`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess *this)
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
          (int)&byte_1800A1389,
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
      if ( (*((_QWORD *)v9 + 2) & 0x40) != 0 && (v10 & 0x40) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800A1203,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004b3f0  mov     [rsp-8+arg_8], rbx
0x18004b3f5  mov     [rsp-8+arg_10], rdi
0x18004b3fa  push    rbp
0x18004b3fb  mov     rbp, rsp
0x18004b3fe  sub     rsp, 140h
0x18004b405  mov     rbx, rcx
0x18004b408  mov     rdi, [rcx+110h]
0x18004b40f  mov     eax, [rdi+48h]
0x18004b412  test    eax, eax
0x18004b414  jns     loc_18004B5FF
0x18004b41a  add     rdi, 50h ; 'P'
0x18004b41e  cmp     eax, [rdi+8]
0x18004b421  jnz     loc_18004B5FF
0x18004b427  test    rdi, rdi
0x18004b42a  jz      loc_18004B5FF
0x18004b430  mov     [rbp+SRWLock], 0
0x18004b438  lea     rdx, [rbp+SRWLock]
0x18004b43c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b441  mov     rax, [rbx+110h]
0x18004b448  mov     dword ptr [rax], 2
0x18004b44e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004b452  test    rcx, rcx
0x18004b455  jz      short loc_18004B463
0x18004b457  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b45e  nop     dword ptr [rax+rax+00h]
0x18004b463  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b468  mov     r9, rax
0x18004b46b  mov     ecx, [rax]
0x18004b46d  cmp     ecx, 4
0x18004b470  jbe     loc_18004B6B0
0x18004b476  mov     rax, [rax+18h]
0x18004b47a  mov     rcx, [r9+10h]
0x18004b47e  test    cl, 40h
0x18004b481  jz      loc_18004B6B0
0x18004b487  mov     rcx, rax
0x18004b48a  and     ecx, 40h
0x18004b48d  cmp     rcx, rax
0x18004b490  jnz     loc_18004B6B0
0x18004b496  mov     rax, [rdi+30h]
0x18004b49a  mov     [rbp+var_50], rax
0x18004b49e  mov     eax, [rdi+44h]
0x18004b4a1  mov     dword ptr [rbp+var_78+4], eax
0x18004b4a4  mov     eax, [rdi+10h]
0x18004b4a7  mov     dword ptr [rbp+var_70], eax
0x18004b4aa  mov     rax, [rdi+78h]
0x18004b4ae  mov     [rbp+var_48], rax
0x18004b4b2  mov     rax, [rdi+70h]
0x18004b4b6  mov     [rbp+var_40], rax
0x18004b4ba  mov     eax, [rdi+68h]
0x18004b4bd  mov     dword ptr [rbp+var_70+4], eax
0x18004b4c0  mov     rax, [rdi+60h]
0x18004b4c4  mov     [rbp+var_38], rax
0x18004b4c8  mov     rax, [rdi+58h]
0x18004b4cc  mov     [rbp+var_30], rax
0x18004b4d0  mov     eax, [rdi+50h]
0x18004b4d3  mov     dword ptr [rbp+var_68], eax
0x18004b4d6  mov     rax, [rdi+48h]
0x18004b4da  mov     [rbp+var_28], rax
0x18004b4de  mov     eax, [rdi+20h]
0x18004b4e1  mov     dword ptr [rbp+var_68+4], eax
0x18004b4e4  mov     rax, [rdi+18h]
0x18004b4e8  mov     [rbp+var_20], rax
0x18004b4ec  mov     eax, [rdi]
0x18004b4ee  mov     [rbp+var_60], eax
0x18004b4f1  mov     rax, [rdi+80h]
0x18004b4f8  mov     [rbp+var_18], rax
0x18004b4fc  mov     eax, [rdi+40h]
0x18004b4ff  mov     dword ptr [rbp+var_78], eax
0x18004b502  mov     rax, [rdi+38h]
0x18004b506  mov     [rbp+var_10], rax
0x18004b50a  mov     eax, [rdi+8]
0x18004b50d  mov     dword ptr [rbp+SRWLock], eax
0x18004b510  mov     [rbp+var_8], 1000000h
0x18004b518  mov     [rbp+var_58], 0
0x18004b520  mov     r8, [rbx+110h]
0x18004b527  add     r8, 8; int
0x18004b52b  lea     rax, [rbp+var_50]
0x18004b52f  mov     [rsp+140h+var_90], rax; __int64
0x18004b537  lea     rax, [rbp+var_78+4]
0x18004b53b  mov     [rsp+140h+var_98], rax; __int64
0x18004b543  lea     rax, [rbp+var_70]
0x18004b547  mov     [rsp+140h+var_A0], rax; __int64
0x18004b54f  lea     rax, [rbp+var_48]
0x18004b553  mov     [rsp+140h+var_A8], rax; __int64
0x18004b55b  lea     rax, [rbp+var_40]
0x18004b55f  mov     [rsp+140h+var_B0], rax; __int64
0x18004b567  lea     rax, [rbp+var_70+4]
0x18004b56b  mov     [rsp+140h+var_B8], rax; __int64
0x18004b573  lea     rax, [rbp+var_38]
0x18004b577  mov     [rsp+140h+var_C0], rax; __int64
0x18004b57f  lea     rax, [rbp+var_30]
0x18004b583  mov     [rsp+140h+var_C8], rax; __int64
0x18004b588  lea     rax, [rbp+var_68]
0x18004b58c  mov     [rsp+140h+var_D0], rax; __int64
0x18004b591  lea     rax, [rbp+var_28]
0x18004b595  mov     [rsp+140h+var_D8], rax; __int64
0x18004b59a  lea     rax, [rbp+var_68+4]
0x18004b59e  mov     [rsp+140h+var_E0], rax; __int64
0x18004b5a3  lea     rax, [rbp+var_20]
0x18004b5a7  mov     [rsp+140h+var_E8], rax; __int64
0x18004b5ac  lea     rax, [rbp+var_60]
0x18004b5b0  mov     [rsp+140h+var_F0], rax; __int64
0x18004b5b5  lea     rax, [rbp+var_18]
0x18004b5b9  mov     [rsp+140h+var_F8], rax; __int64
0x18004b5be  lea     rax, [rbp+var_78]
0x18004b5c2  mov     [rsp+140h+var_100], rax; __int64
0x18004b5c7  lea     rax, [rbp+var_10]
0x18004b5cb  mov     [rsp+140h+var_108], rax; __int64
0x18004b5d0  lea     rax, [rbp+SRWLock]
0x18004b5d4  mov     [rsp+140h+var_110], rax; __int64
0x18004b5d9  lea     rax, [rbp+var_8]
0x18004b5dd  mov     [rsp+140h+var_118], rax; __int64
0x18004b5e2  lea     rax, [rbp+var_58]
0x18004b5e6  mov     [rsp+140h+var_120], rax; __int64
0x18004b5eb  lea     rdx, byte_1800A1389; int
0x18004b5f2  mov     rcx, r9; int
0x18004b5f5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004b5fa  jmp     loc_18004B6B0
0x18004b5ff  mov     [rbp+SRWLock], 0
0x18004b607  lea     rdx, [rbp+SRWLock]
0x18004b60b  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b610  mov     rax, [rbx+110h]
0x18004b617  mov     dword ptr [rax], 2
0x18004b61d  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004b621  test    rcx, rcx
0x18004b624  jz      short loc_18004B632
0x18004b626  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b62d  nop     dword ptr [rax+rax+00h]
0x18004b632  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b637  mov     rdi, rax
0x18004b63a  mov     ecx, [rax]
0x18004b63c  cmp     ecx, 4
0x18004b63f  jbe     short loc_18004B6B0
0x18004b641  mov     rax, [rax+18h]
0x18004b645  mov     rcx, [rdi+10h]
0x18004b649  test    cl, 40h
0x18004b64c  jz      short loc_18004B6B0
0x18004b64e  mov     rcx, rax
0x18004b651  and     ecx, 40h
0x18004b654  cmp     rcx, rax
0x18004b657  jnz     short loc_18004B6B0
0x18004b659  call    cs:__imp_GetCurrentThreadId
0x18004b660  nop     dword ptr [rax+rax+00h]
0x18004b665  mov     dword ptr [rbp+SRWLock], eax
0x18004b668  mov     r8, [rbx+110h]
0x18004b66f  mov     eax, [r8+48h]
0x18004b673  mov     dword ptr [rbp+var_78], eax
0x18004b676  mov     [rbp+var_58], 0
0x18004b67e  add     r8, 8
0x18004b682  lea     rax, [rbp+SRWLock]
0x18004b686  mov     [rsp+140h+var_110], rax
0x18004b68b  lea     rax, [rbp+var_78]
0x18004b68f  mov     [rsp+140h+var_118], rax
0x18004b694  lea     rax, [rbp+var_58]
0x18004b698  mov     [rsp+140h+var_120], rax
0x18004b69d  xor     r9d, r9d
0x18004b6a0  lea     rdx, byte_1800A1203
0x18004b6a7  mov     rcx, rdi
0x18004b6aa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004b6af  nop
0x18004b6b0  lea     rcx, [rbx+120h]; this
0x18004b6b7  cmp     dword ptr [rcx+18h], 0
0x18004b6bb  jz      short loc_18004B6C3
0x18004b6bd  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004b6c2  nop
0x18004b6c3  lea     r11, [rsp+140h+var_s0]
0x18004b6cb  mov     rbx, [r11+18h]
0x18004b6cf  mov     rdi, [r11+20h]
0x18004b6d3  mov     rsp, r11
0x18004b6d6  pop     rbp
0x18004b6d7  retn
```
