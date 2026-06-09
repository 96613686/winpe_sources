# UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ulong,ushort const *>(ulong,ulong,ushort const *)

- ea: `0x18000c8d8`
- end: `0x18000cbf4`
- name: `??$Stop@KKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKKPEBG@Z`
- size: `796`
- prototype: `__int64 __fastcall(__int64, int, int, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000dcb0`
- `0x18000e300`
- `0x18000f340`
- `0x18000f8a0`

## callees

- `0x180001f6c`
- `0x180002934`
- `0x18000946c`
- `0x180009644`
- `0x180009f60`
- `0x18000c8d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c940`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c940`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb6c`

## pseudocode

```c
__int64 __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4)
{
  __int64 v4; // rdi
  int v9; // eax
  __int64 v10; // rdi
  RTL_SRWLOCK *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r8
  RTL_SRWLOCK *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 v21; // rax
  DWORD CurrentThreadId; // eax
  __int64 v23; // r8
  int v24; // r9d
  int v26; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v27; // [rsp+C4h] [rbp-7Ch] BYREF
  int v28; // [rsp+C8h] [rbp-78h] BYREF
  int v29; // [rsp+CCh] [rbp-74h] BYREF
  int v30; // [rsp+D0h] [rbp-70h] BYREF
  int v31; // [rsp+D4h] [rbp-6Ch] BYREF
  int v32; // [rsp+D8h] [rbp-68h] BYREF
  int v33; // [rsp+DCh] [rbp-64h] BYREF
  __int64 v34; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+100h] [rbp-40h] BYREF
  __int64 v39; // [rsp+108h] [rbp-38h] BYREF
  __int64 v40; // [rsp+110h] [rbp-30h] BYREF
  __int64 v41; // [rsp+118h] [rbp-28h] BYREF
  __int64 v42; // [rsp+120h] [rbp-20h] BYREF
  __int64 v43; // [rsp+128h] [rbp-18h] BYREF
  _QWORD v44[8]; // [rsp+130h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+180h] [rbp+40h] BYREF

  v4 = *(_QWORD *)(a1 + 272);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = v4 + 80, v9 == *(_DWORD *)(v10 + 8)) && v10 )
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    v11 = SRWLock;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = UwfTraceLoggingProvider<2>::Provider();
    v15 = v12;
    if ( *(_DWORD *)v12 > 5u )
    {
      v16 = *(_QWORD *)(v12 + 24);
      v13 = 0x400000000000LL;
      if ( (*(_QWORD *)(v15 + 16) & 0x400000000000LL) != 0 && (v16 & 0x400000000000LL) == v16 )
      {
        v37 = *(_QWORD *)(v10 + 120);
        v38 = *(_QWORD *)(v10 + 112);
        v32 = *(_DWORD *)(v10 + 104);
        v17 = *(_QWORD *)(a1 + 272);
        v39 = *(_QWORD *)(v10 + 96);
        v40 = *(_QWORD *)(v10 + 88);
        v33 = *(_DWORD *)(v10 + 80);
        v41 = *(_QWORD *)(v10 + 72);
        v26 = *(_DWORD *)(v10 + 32);
        v42 = *(_QWORD *)(v10 + 24);
        v27 = *(_DWORD *)v10;
        v43 = *(_QWORD *)(v10 + 128);
        v28 = *(_DWORD *)(v10 + 64);
        v44[0] = *(_QWORD *)(v10 + 56);
        v29 = *(_DWORD *)(v10 + 8);
        v36 = a4;
        LODWORD(SRWLock) = a3;
        v30 = a2;
        v31 = 3;
        v34 = 0x1000000;
        v35 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v15,
          (unsigned int)&byte_1800238BF,
          v17 + 8,
          v15,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v29,
          (__int64)v44,
          (__int64)&v28,
          (__int64)&v43,
          (__int64)&v27,
          (__int64)&v42,
          (__int64)&v26,
          (__int64)&v41,
          (__int64)&v33,
          (__int64)&v40,
          (__int64)&v39,
          (__int64)&v32,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v36);
      }
    }
  }
  else
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    v18 = SRWLock;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v18 )
      ReleaseSRWLockExclusive(v18);
    v19 = UwfTraceLoggingProvider<2>::Provider();
    v20 = v19;
    if ( *(_DWORD *)v19 > 5u )
    {
      v21 = *(_QWORD *)(v19 + 24);
      v13 = 0x400000000000LL;
      if ( (*(_QWORD *)(v20 + 16) & 0x400000000000LL) != 0 && (v21 & 0x400000000000LL) == v21 )
      {
        v35 = a4;
        LODWORD(SRWLock) = a3;
        v29 = a2;
        v28 = 3;
        CurrentThreadId = GetCurrentThreadId();
        v23 = *(_QWORD *)(a1 + 272);
        v27 = CurrentThreadId;
        v26 = *(_DWORD *)(v23 + 72);
        v34 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v20,
          (unsigned int)byte_180023849,
          v23 + 8,
          v24,
          (__int64)&v34,
          (__int64)&v26,
          (__int64)&v27,
          (__int64)&v28,
          (__int64)&v29,
          (__int64)&SRWLock,
          (__int64)&v35);
      }
    }
  }
  return wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v13,
           v14,
           v15);
}

```

## disassembly

```asm
0x18000c8d8  push    rbp
0x18000c8da  push    rbx
0x18000c8db  push    rsi
0x18000c8dc  push    rdi
0x18000c8dd  push    r14
0x18000c8df  push    r15
0x18000c8e1  lea     rbp, [rsp-8]
0x18000c8e6  sub     rsp, 148h
0x18000c8ed  mov     rdi, [rcx+110h]
0x18000c8f4  mov     rsi, r9
0x18000c8f7  mov     r14d, r8d
0x18000c8fa  mov     r15d, edx
0x18000c8fd  mov     rbx, rcx
0x18000c900  mov     eax, [rdi+48h]
0x18000c903  test    eax, eax
0x18000c905  jns     loc_18000CAF7
0x18000c90b  add     rdi, 50h ; 'P'
0x18000c90f  cmp     eax, [rdi+8]
0x18000c912  jnz     loc_18000CAF7
0x18000c918  test    rdi, rdi
0x18000c91b  jz      loc_18000CAF7
0x18000c921  lea     rdx, [rbp+30h+SRWLock]
0x18000c925  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c92a  mov     rax, [rbx+110h]
0x18000c931  mov     rcx, [rbp+30h+SRWLock]; SRWLock
0x18000c935  mov     dword ptr [rax], 2
0x18000c93b  test    rcx, rcx
0x18000c93e  jz      short loc_18000C946
0x18000c940  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c946  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000c94b  mov     r9, rax
0x18000c94e  mov     ecx, [rax]
0x18000c950  cmp     ecx, 5
0x18000c953  jbe     loc_18000CBDD
0x18000c959  mov     rax, [rax+18h]
0x18000c95d  mov     rdx, 400000000000h
0x18000c967  mov     rcx, [r9+10h]
0x18000c96b  test    rdx, rcx
0x18000c96e  jz      loc_18000CBDD
0x18000c974  mov     rcx, rax
0x18000c977  and     rcx, rdx
0x18000c97a  cmp     rcx, rax
0x18000c97d  jnz     loc_18000CBDD
0x18000c983  mov     rax, [rdi+78h]
0x18000c987  lea     rdx, byte_1800238BF
0x18000c98e  mov     [rbp+30h+var_78], rax
0x18000c992  mov     rcx, r9
0x18000c995  mov     rax, [rdi+70h]
0x18000c999  mov     [rbp+30h+var_70], rax
0x18000c99d  mov     eax, [rdi+68h]
0x18000c9a0  mov     [rbp+30h+var_98], eax
0x18000c9a3  mov     rax, [rdi+60h]
0x18000c9a7  mov     r8, [rbx+110h]
0x18000c9ae  mov     [rbp+30h+var_68], rax
0x18000c9b2  add     r8, 8
0x18000c9b6  mov     rax, [rdi+58h]
0x18000c9ba  mov     [rbp+30h+var_60], rax
0x18000c9be  mov     eax, [rdi+50h]
0x18000c9c1  mov     [rbp+30h+var_94], eax
0x18000c9c4  mov     rax, [rdi+48h]
0x18000c9c8  mov     [rbp+30h+var_58], rax
0x18000c9cc  mov     eax, [rdi+20h]
0x18000c9cf  mov     [rbp+30h+var_B0], eax
0x18000c9d2  mov     rax, [rdi+18h]
0x18000c9d6  mov     [rbp+30h+var_50], rax
0x18000c9da  mov     eax, [rdi]
0x18000c9dc  mov     [rbp+30h+var_AC], eax
0x18000c9df  mov     rax, [rdi+80h]
0x18000c9e6  mov     [rbp+30h+var_48], rax
0x18000c9ea  mov     eax, [rdi+40h]
0x18000c9ed  mov     [rbp+30h+var_A8], eax
0x18000c9f0  mov     rax, [rdi+38h]
0x18000c9f4  mov     [rbp+30h+var_40], rax
0x18000c9f8  mov     eax, [rdi+8]
0x18000c9fb  mov     [rbp+30h+var_A4], eax
0x18000c9fe  lea     rax, [rbp+30h+var_80]
0x18000ca02  mov     [rsp+170h+var_B8], rax
0x18000ca0a  lea     rax, [rbp+30h+SRWLock]
0x18000ca0e  mov     [rsp+170h+var_C0], rax
0x18000ca16  lea     rax, [rbp+30h+var_A0]
0x18000ca1a  mov     [rsp+170h+var_C8], rax
0x18000ca22  lea     rax, [rbp+30h+var_9C]
0x18000ca26  mov     [rsp+170h+var_D0], rax
0x18000ca2e  lea     rax, [rbp+30h+var_78]
0x18000ca32  mov     [rsp+170h+var_D8], rax
0x18000ca3a  lea     rax, [rbp+30h+var_70]
0x18000ca3e  mov     [rsp+170h+var_E0], rax
0x18000ca46  lea     rax, [rbp+30h+var_98]
0x18000ca4a  mov     [rsp+170h+var_E8], rax
0x18000ca52  lea     rax, [rbp+30h+var_68]
0x18000ca56  mov     [rsp+170h+var_F0], rax
0x18000ca5e  lea     rax, [rbp+30h+var_60]
0x18000ca62  mov     [rsp+170h+var_F8], rax
0x18000ca67  lea     rax, [rbp+30h+var_94]
0x18000ca6b  mov     [rsp+170h+var_100], rax
0x18000ca70  lea     rax, [rbp+30h+var_58]
0x18000ca74  mov     [rsp+170h+var_108], rax
0x18000ca79  lea     rax, [rbp+30h+var_B0]
0x18000ca7d  mov     [rsp+170h+var_110], rax
0x18000ca82  lea     rax, [rbp+30h+var_50]
0x18000ca86  mov     [rsp+170h+var_118], rax
0x18000ca8b  lea     rax, [rbp+30h+var_AC]
0x18000ca8f  mov     [rsp+170h+var_120], rax
0x18000ca94  lea     rax, [rbp+30h+var_48]
0x18000ca98  mov     [rsp+170h+var_128], rax
0x18000ca9d  lea     rax, [rbp+30h+var_A8]
0x18000caa1  mov     [rsp+170h+var_130], rax
0x18000caa6  lea     rax, [rbp+30h+var_40]
0x18000caaa  mov     [rsp+170h+var_138], rax
0x18000caaf  lea     rax, [rbp+30h+var_A4]
0x18000cab3  mov     [rsp+170h+var_140], rax
0x18000cab8  lea     rax, [rbp+30h+var_90]
0x18000cabc  mov     [rsp+170h+var_148], rax
0x18000cac1  lea     rax, [rbp+30h+var_88]
0x18000cac5  mov     [rsp+170h+var_150], rax
0x18000caca  mov     [rbp+30h+var_80], rsi
0x18000cace  mov     dword ptr [rbp+30h+SRWLock], r14d
0x18000cad2  mov     [rbp+30h+var_A0], r15d
0x18000cad6  mov     [rbp+30h+var_9C], 3
0x18000cadd  mov     [rbp+30h+var_90], 1000000h
0x18000cae5  mov     [rbp+30h+var_88], 0
0x18000caed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564446@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000caf2  jmp     loc_18000CBDD
0x18000caf7  lea     rdx, [rbp+30h+SRWLock]
0x18000cafb  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cb00  mov     rax, [rbx+110h]
0x18000cb07  mov     rcx, [rbp+30h+SRWLock]; SRWLock
0x18000cb0b  mov     dword ptr [rax], 2
0x18000cb11  test    rcx, rcx
0x18000cb14  jz      short loc_18000CB1C
0x18000cb16  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cb1c  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000cb21  mov     rdi, rax
0x18000cb24  mov     ecx, [rax]
0x18000cb26  cmp     ecx, 5
0x18000cb29  jbe     loc_18000CBDD
0x18000cb2f  mov     rax, [rax+18h]
0x18000cb33  mov     rdx, 400000000000h
0x18000cb3d  mov     rcx, [rdi+10h]
0x18000cb41  test    rdx, rcx
0x18000cb44  jz      loc_18000CBDD
0x18000cb4a  mov     rcx, rax
0x18000cb4d  and     rcx, rdx
0x18000cb50  cmp     rcx, rax
0x18000cb53  jnz     loc_18000CBDD
0x18000cb59  mov     [rbp+30h+var_88], rsi
0x18000cb5d  mov     dword ptr [rbp+30h+SRWLock], r14d
0x18000cb61  mov     [rbp+30h+var_A4], r15d
0x18000cb65  mov     [rbp+30h+var_A8], 3
0x18000cb6c  call    cs:__imp_GetCurrentThreadId
0x18000cb72  mov     r8, [rbx+110h]
0x18000cb79  lea     rdx, byte_180023849
0x18000cb80  mov     [rbp+30h+var_AC], eax
0x18000cb83  mov     rcx, rdi
0x18000cb86  mov     eax, [r8+48h]
0x18000cb8a  add     r8, 8
0x18000cb8e  mov     [rbp+30h+var_B0], eax
0x18000cb91  lea     rax, [rbp+30h+var_88]
0x18000cb95  mov     [rsp+170h+var_120], rax
0x18000cb9a  lea     rax, [rbp+30h+SRWLock]
0x18000cb9e  mov     [rsp+170h+var_128], rax
0x18000cba3  lea     rax, [rbp+30h+var_A4]
0x18000cba7  mov     [rsp+170h+var_130], rax
0x18000cbac  lea     rax, [rbp+30h+var_A8]
0x18000cbb0  mov     [rsp+170h+var_138], rax
0x18000cbb5  lea     rax, [rbp+30h+var_AC]
0x18000cbb9  mov     [rsp+170h+var_140], rax
0x18000cbbe  lea     rax, [rbp+30h+var_B0]
0x18000cbc2  mov     [rsp+170h+var_148], rax
0x18000cbc7  lea     rax, [rbp+30h+var_90]
0x18000cbcb  mov     [rsp+170h+var_150], rax
0x18000cbd0  mov     [rbp+30h+var_90], 0
0x18000cbd8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4444AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000cbdd  mov     rcx, rbx
0x18000cbe0  add     rsp, 148h
0x18000cbe7  pop     r15
0x18000cbe9  pop     r14
0x18000cbeb  pop     rdi
0x18000cbec  pop     rsi
0x18000cbed  pop     rbx
0x18000cbee  pop     rbp
0x18000cbef  jmp     ?IgnoreCurrentThread@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
