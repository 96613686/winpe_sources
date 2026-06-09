# ComputeLib::Diagnostics::TraceProvider::ClientLib_CompleteAllOperations::StopActivity(void)

- ea: `0x18003f460`
- end: `0x18003f753`
- name: `?StopActivity@ClientLib_CompleteAllOperations@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_CompleteAllOperations *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x18003f460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f4c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f69b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f4c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f69b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f6d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f6d3`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_CompleteAllOperations::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_CompleteAllOperations *this)
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
          (int)&unk_1800A0870,
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
          (unsigned int)&byte_1800A0DC7,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_CompleteAllOperations *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003f460  mov     [rsp-8+arg_8], rbx
0x18003f465  mov     [rsp-8+arg_10], rdi
0x18003f46a  push    rbp
0x18003f46b  mov     rbp, rsp
0x18003f46e  sub     rsp, 140h
0x18003f475  mov     rbx, rcx
0x18003f478  mov     rdi, [rcx+110h]
0x18003f47f  mov     eax, [rdi+48h]
0x18003f482  test    eax, eax
0x18003f484  jns     loc_18003F674
0x18003f48a  add     rdi, 50h ; 'P'
0x18003f48e  cmp     eax, [rdi+8]
0x18003f491  jnz     loc_18003F674
0x18003f497  test    rdi, rdi
0x18003f49a  jz      loc_18003F674
0x18003f4a0  mov     [rbp+SRWLock], 0
0x18003f4a8  lea     rdx, [rbp+SRWLock]
0x18003f4ac  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003f4b1  mov     rax, [rbx+110h]
0x18003f4b8  mov     dword ptr [rax], 2
0x18003f4be  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003f4c2  test    rcx, rcx
0x18003f4c5  jz      short loc_18003F4D3
0x18003f4c7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f4ce  nop     dword ptr [rax+rax+00h]
0x18003f4d3  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003f4d8  mov     r9, rax
0x18003f4db  mov     ecx, [rax]
0x18003f4dd  cmp     ecx, 4
0x18003f4e0  jbe     loc_18003F72A
0x18003f4e6  mov     rax, [rax+18h]
0x18003f4ea  mov     rcx, [r9+10h]
0x18003f4ee  mov     edx, 10000h
0x18003f4f3  test    rdx, rcx
0x18003f4f6  jz      loc_18003F72A
0x18003f4fc  mov     rcx, rax
0x18003f4ff  and     rcx, rdx
0x18003f502  cmp     rcx, rax
0x18003f505  jnz     loc_18003F72A
0x18003f50b  mov     rax, [rdi+30h]
0x18003f50f  mov     [rbp+var_50], rax
0x18003f513  mov     eax, [rdi+44h]
0x18003f516  mov     dword ptr [rbp+var_78+4], eax
0x18003f519  mov     eax, [rdi+10h]
0x18003f51c  mov     dword ptr [rbp+var_70], eax
0x18003f51f  mov     rax, [rdi+78h]
0x18003f523  mov     [rbp+var_48], rax
0x18003f527  mov     rax, [rdi+70h]
0x18003f52b  mov     [rbp+var_40], rax
0x18003f52f  mov     eax, [rdi+68h]
0x18003f532  mov     dword ptr [rbp+var_70+4], eax
0x18003f535  mov     rax, [rdi+60h]
0x18003f539  mov     [rbp+var_38], rax
0x18003f53d  mov     rax, [rdi+58h]
0x18003f541  mov     [rbp+var_30], rax
0x18003f545  mov     eax, [rdi+50h]
0x18003f548  mov     dword ptr [rbp+var_68], eax
0x18003f54b  mov     rax, [rdi+48h]
0x18003f54f  mov     [rbp+var_28], rax
0x18003f553  mov     eax, [rdi+20h]
0x18003f556  mov     dword ptr [rbp+var_68+4], eax
0x18003f559  mov     rax, [rdi+18h]
0x18003f55d  mov     [rbp+var_20], rax
0x18003f561  mov     eax, [rdi]
0x18003f563  mov     [rbp+var_60], eax
0x18003f566  mov     rax, [rdi+80h]
0x18003f56d  mov     [rbp+var_18], rax
0x18003f571  mov     eax, [rdi+40h]
0x18003f574  mov     dword ptr [rbp+var_78], eax
0x18003f577  mov     rax, [rdi+38h]
0x18003f57b  mov     [rbp+var_10], rax
0x18003f57f  mov     eax, [rdi+8]
0x18003f582  mov     dword ptr [rbp+SRWLock], eax
0x18003f585  mov     [rbp+var_8], 1000000h
0x18003f58d  mov     [rbp+var_58], 0
0x18003f595  mov     r8, [rbx+110h]
0x18003f59c  add     r8, 8; int
0x18003f5a0  lea     rax, [rbp+var_50]
0x18003f5a4  mov     [rsp+140h+var_90], rax; __int64
0x18003f5ac  lea     rax, [rbp+var_78+4]
0x18003f5b0  mov     [rsp+140h+var_98], rax; __int64
0x18003f5b8  lea     rax, [rbp+var_70]
0x18003f5bc  mov     [rsp+140h+var_A0], rax; __int64
0x18003f5c4  lea     rax, [rbp+var_48]
0x18003f5c8  mov     [rsp+140h+var_A8], rax; __int64
0x18003f5d0  lea     rax, [rbp+var_40]
0x18003f5d4  mov     [rsp+140h+var_B0], rax; __int64
0x18003f5dc  lea     rax, [rbp+var_70+4]
0x18003f5e0  mov     [rsp+140h+var_B8], rax; __int64
0x18003f5e8  lea     rax, [rbp+var_38]
0x18003f5ec  mov     [rsp+140h+var_C0], rax; __int64
0x18003f5f4  lea     rax, [rbp+var_30]
0x18003f5f8  mov     [rsp+140h+var_C8], rax; __int64
0x18003f5fd  lea     rax, [rbp+var_68]
0x18003f601  mov     [rsp+140h+var_D0], rax; __int64
0x18003f606  lea     rax, [rbp+var_28]
0x18003f60a  mov     [rsp+140h+var_D8], rax; __int64
0x18003f60f  lea     rax, [rbp+var_68+4]
0x18003f613  mov     [rsp+140h+var_E0], rax; __int64
0x18003f618  lea     rax, [rbp+var_20]
0x18003f61c  mov     [rsp+140h+var_E8], rax; __int64
0x18003f621  lea     rax, [rbp+var_60]
0x18003f625  mov     [rsp+140h+var_F0], rax; __int64
0x18003f62a  lea     rax, [rbp+var_18]
0x18003f62e  mov     [rsp+140h+var_F8], rax; __int64
0x18003f633  lea     rax, [rbp+var_78]
0x18003f637  mov     [rsp+140h+var_100], rax; __int64
0x18003f63c  lea     rax, [rbp+var_10]
0x18003f640  mov     [rsp+140h+var_108], rax; __int64
0x18003f645  lea     rax, [rbp+SRWLock]
0x18003f649  mov     [rsp+140h+var_110], rax; __int64
0x18003f64e  lea     rax, [rbp+var_8]
0x18003f652  mov     [rsp+140h+var_118], rax; __int64
0x18003f657  lea     rax, [rbp+var_58]
0x18003f65b  mov     [rsp+140h+var_120], rax; __int64
0x18003f660  lea     rdx, unk_1800A0870; int
0x18003f667  mov     rcx, r9; int
0x18003f66a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003f66f  jmp     loc_18003F72A
0x18003f674  mov     [rbp+SRWLock], 0
0x18003f67c  lea     rdx, [rbp+SRWLock]
0x18003f680  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003f685  mov     rax, [rbx+110h]
0x18003f68c  mov     dword ptr [rax], 2
0x18003f692  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003f696  test    rcx, rcx
0x18003f699  jz      short loc_18003F6A7
0x18003f69b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f6a2  nop     dword ptr [rax+rax+00h]
0x18003f6a7  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003f6ac  mov     rdi, rax
0x18003f6af  mov     ecx, [rax]
0x18003f6b1  cmp     ecx, 4
0x18003f6b4  jbe     short loc_18003F72A
0x18003f6b6  mov     rax, [rax+18h]
0x18003f6ba  mov     rcx, [rdi+10h]
0x18003f6be  mov     edx, 10000h
0x18003f6c3  test    rdx, rcx
0x18003f6c6  jz      short loc_18003F72A
0x18003f6c8  mov     rcx, rax
0x18003f6cb  and     rcx, rdx
0x18003f6ce  cmp     rcx, rax
0x18003f6d1  jnz     short loc_18003F72A
0x18003f6d3  call    cs:__imp_GetCurrentThreadId
0x18003f6da  nop     dword ptr [rax+rax+00h]
0x18003f6df  mov     dword ptr [rbp+SRWLock], eax
0x18003f6e2  mov     r8, [rbx+110h]
0x18003f6e9  mov     eax, [r8+48h]
0x18003f6ed  mov     dword ptr [rbp+var_78], eax
0x18003f6f0  mov     [rbp+var_58], 0
0x18003f6f8  add     r8, 8
0x18003f6fc  lea     rax, [rbp+SRWLock]
0x18003f700  mov     [rsp+140h+var_110], rax
0x18003f705  lea     rax, [rbp+var_78]
0x18003f709  mov     [rsp+140h+var_118], rax
0x18003f70e  lea     rax, [rbp+var_58]
0x18003f712  mov     [rsp+140h+var_120], rax
0x18003f717  xor     r9d, r9d
0x18003f71a  lea     rdx, byte_1800A0DC7
0x18003f721  mov     rcx, rdi
0x18003f724  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003f729  nop
0x18003f72a  lea     rcx, [rbx+120h]; this
0x18003f731  cmp     dword ptr [rcx+18h], 0
0x18003f735  jz      short loc_18003F73D
0x18003f737  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003f73c  nop
0x18003f73d  lea     r11, [rsp+140h+var_s0]
0x18003f745  mov     rbx, [r11+18h]
0x18003f749  mov     rdi, [r11+20h]
0x18003f74d  mov     rsp, r11
0x18003f750  pop     rbp
0x18003f751  retn
```
