# UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong>(ulong)

- ea: `0x18000745c`
- end: `0x180007782`
- name: `??$Stop@K@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXK@Z`
- size: `806`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800091c0`
- `0x18000e610`
- `0x18000ed30`

## callees

- `0x1800012bc`
- `0x180001ecc`
- `0x18000745c`
- `0x18000946c`
- `0x180009644`
- `0x180009f60`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800074ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000767f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800074ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000767f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076cc`

## pseudocode

```c
__int64 __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long>(__int64 a1, int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  __int64 v6; // rdi
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // r8
  RTL_SRWLOCK *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rax
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  int v21; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v22; // [rsp+B4h] [rbp-7Ch] BYREF
  int v23; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-70h] BYREF
  PSRWLOCK v25; // [rsp+C8h] [rbp-68h] BYREF
  int v26; // [rsp+D0h] [rbp-60h] BYREF
  int v27; // [rsp+D4h] [rbp-5Ch] BYREF
  int v28; // [rsp+D8h] [rbp-58h] BYREF
  int v29; // [rsp+DCh] [rbp-54h] BYREF
  __int64 v30; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v32; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v34; // [rsp+100h] [rbp-30h] BYREF
  __int64 v35; // [rsp+108h] [rbp-28h] BYREF
  __int64 v36; // [rsp+110h] [rbp-20h] BYREF
  __int64 v37; // [rsp+118h] [rbp-18h] BYREF
  __int64 v38; // [rsp+120h] [rbp-10h] BYREF
  char v39[32]; // [rsp+130h] [rbp+0h] BYREF
  PSRWLOCK *v40; // [rsp+150h] [rbp+20h]
  __int64 v41; // [rsp+158h] [rbp+28h]
  int *v42; // [rsp+160h] [rbp+30h]
  __int64 v43; // [rsp+168h] [rbp+38h]
  DWORD *v44; // [rsp+170h] [rbp+40h]
  __int64 v45; // [rsp+178h] [rbp+48h]
  int *v46; // [rsp+180h] [rbp+50h]
  __int64 v47; // [rsp+188h] [rbp+58h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+60h]
  __int64 v49; // [rsp+198h] [rbp+68h]

  v2 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = v2 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    v7 = SRWLock;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    v8 = UwfTraceLoggingProvider<2>::Provider();
    v11 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v12 = *(_QWORD *)(v8 + 24);
      v9 = 0x400000000000LL;
      if ( (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0 && (v12 & 0x400000000000LL) == v12 )
      {
        v30 = *(_QWORD *)(v6 + 120);
        v13 = *(_QWORD *)(a1 + 272);
        v31 = *(_QWORD *)(v6 + 112);
        v28 = *(_DWORD *)(v6 + 104);
        v32 = *(_QWORD *)(v6 + 96);
        v33 = *(_QWORD *)(v6 + 88);
        v29 = *(_DWORD *)(v6 + 80);
        v34 = *(_QWORD *)(v6 + 72);
        v21 = *(_DWORD *)(v6 + 32);
        v35 = *(_QWORD *)(v6 + 24);
        v22 = *(_DWORD *)v6;
        v36 = *(_QWORD *)(v6 + 128);
        v23 = *(_DWORD *)(v6 + 64);
        v37 = *(_QWORD *)(v6 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v6 + 8);
        v26 = a2;
        v27 = 1;
        v38 = 0x1000000;
        v25 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v11,
          (unsigned int)&unk_180022C38,
          v13 + 8,
          v11,
          (__int64)&v25,
          (__int64)&v38,
          (__int64)&SRWLock,
          (__int64)&v37,
          (__int64)&v23,
          (__int64)&v36,
          (__int64)&v22,
          (__int64)&v35,
          (__int64)&v21,
          (__int64)&v34,
          (__int64)&v29,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v28,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v27,
          (__int64)&v26);
      }
    }
  }
  else
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v25);
    v14 = v25;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    v15 = UwfTraceLoggingProvider<2>::Provider();
    v16 = v15;
    if ( *(_DWORD *)v15 > 5u )
    {
      v17 = *(_QWORD *)(v15 + 24);
      v9 = 0x400000000000LL;
      if ( (*(_QWORD *)(v16 + 16) & 0x400000000000LL) != 0 && (v17 & 0x400000000000LL) == v17 )
      {
        LODWORD(SRWLock) = a2;
        v23 = 1;
        CurrentThreadId = GetCurrentThreadId();
        v19 = *(_QWORD *)(a1 + 272);
        v22 = CurrentThreadId;
        v49 = 4;
        v47 = 4;
        v21 = *(_DWORD *)(v19 + 72);
        p_SRWLock = &SRWLock;
        v46 = &v23;
        v44 = &v22;
        v42 = &v21;
        v40 = &v25;
        v25 = 0;
        v45 = 4;
        v43 = 4;
        v41 = 8;
        tlgWriteTransfer_EventWriteTransfer(v16, &word_180022BCE, v19 + 8, 0, 7, v39);
      }
    }
  }
  return wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v9,
           v10,
           v11);
}

```

## disassembly

```asm
0x18000745c  push    rbp
0x18000745e  push    rbx
0x18000745f  push    rsi
0x180007460  push    rdi
0x180007461  lea     rbp, [rsp-88h]
0x180007469  sub     rsp, 1B8h
0x180007470  mov     rax, cs:__security_cookie
0x180007477  xor     rax, rsp
0x18000747a  mov     [rbp+0A0h+var_30], rax
0x18000747e  mov     rdi, [rcx+110h]
0x180007485  mov     esi, edx
0x180007487  mov     rbx, rcx
0x18000748a  mov     eax, [rdi+48h]
0x18000748d  test    eax, eax
0x18000748f  jns     loc_180007660
0x180007495  add     rdi, 50h ; 'P'
0x180007499  cmp     eax, [rdi+8]
0x18000749c  jnz     loc_180007660
0x1800074a2  test    rdi, rdi
0x1800074a5  jz      loc_180007660
0x1800074ab  lea     rdx, [rbp+0A0h+SRWLock]
0x1800074af  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800074b4  mov     rax, [rbx+110h]
0x1800074bb  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x1800074bf  mov     dword ptr [rax], 2
0x1800074c5  test    rcx, rcx
0x1800074c8  jz      short loc_1800074D0
0x1800074ca  call    cs:__imp_ReleaseSRWLockExclusive
0x1800074d0  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x1800074d5  mov     r9, rax
0x1800074d8  mov     ecx, [rax]
0x1800074da  cmp     ecx, 5
0x1800074dd  jbe     loc_180007762
0x1800074e3  mov     rax, [rax+18h]
0x1800074e7  mov     rdx, 400000000000h
0x1800074f1  mov     rcx, [r9+10h]
0x1800074f5  test    rdx, rcx
0x1800074f8  jz      loc_180007762
0x1800074fe  mov     rcx, rax
0x180007501  and     rcx, rdx
0x180007504  cmp     rcx, rax
0x180007507  jnz     loc_180007762
0x18000750d  mov     rax, [rdi+78h]
0x180007511  lea     rdx, unk_180022C38
0x180007518  mov     [rbp+0A0h+var_F0], rax
0x18000751c  mov     rcx, r9
0x18000751f  mov     rax, [rdi+70h]
0x180007523  mov     r8, [rbx+110h]
0x18000752a  mov     [rbp+0A0h+var_E8], rax
0x18000752e  add     r8, 8
0x180007532  mov     eax, [rdi+68h]
0x180007535  mov     [rbp+0A0h+var_F8], eax
0x180007538  mov     rax, [rdi+60h]
0x18000753c  mov     [rbp+0A0h+var_E0], rax
0x180007540  mov     rax, [rdi+58h]
0x180007544  mov     [rbp+0A0h+var_D8], rax
0x180007548  mov     eax, [rdi+50h]
0x18000754b  mov     [rbp+0A0h+var_F4], eax
0x18000754e  mov     rax, [rdi+48h]
0x180007552  mov     [rbp+0A0h+var_D0], rax
0x180007556  mov     eax, [rdi+20h]
0x180007559  mov     [rbp+0A0h+var_120], eax
0x18000755c  mov     rax, [rdi+18h]
0x180007560  mov     [rbp+0A0h+var_C8], rax
0x180007564  mov     eax, [rdi]
0x180007566  mov     [rbp+0A0h+var_11C], eax
0x180007569  mov     rax, [rdi+80h]
0x180007570  mov     [rbp+0A0h+var_C0], rax
0x180007574  mov     eax, [rdi+40h]
0x180007577  mov     [rbp+0A0h+var_118], eax
0x18000757a  mov     rax, [rdi+38h]
0x18000757e  mov     [rbp+0A0h+var_B8], rax
0x180007582  mov     eax, [rdi+8]
0x180007585  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x180007588  lea     rax, [rbp+0A0h+var_100]
0x18000758c  mov     [rsp+1D0h+var_128], rax
0x180007594  lea     rax, [rbp+0A0h+var_FC]
0x180007598  mov     [rsp+1D0h+var_130], rax
0x1800075a0  lea     rax, [rbp+0A0h+var_F0]
0x1800075a4  mov     [rsp+1D0h+var_138], rax
0x1800075ac  lea     rax, [rbp+0A0h+var_E8]
0x1800075b0  mov     [rsp+1D0h+var_140], rax
0x1800075b8  lea     rax, [rbp+0A0h+var_F8]
0x1800075bc  mov     [rsp+1D0h+var_148], rax
0x1800075c4  lea     rax, [rbp+0A0h+var_E0]
0x1800075c8  mov     [rsp+1D0h+var_150], rax
0x1800075d0  lea     rax, [rbp+0A0h+var_D8]
0x1800075d4  mov     [rsp+1D0h+var_158], rax
0x1800075d9  lea     rax, [rbp+0A0h+var_F4]
0x1800075dd  mov     [rsp+1D0h+var_160], rax
0x1800075e2  lea     rax, [rbp+0A0h+var_D0]
0x1800075e6  mov     [rsp+1D0h+var_168], rax
0x1800075eb  lea     rax, [rbp+0A0h+var_120]
0x1800075ef  mov     [rsp+1D0h+var_170], rax
0x1800075f4  lea     rax, [rbp+0A0h+var_C8]
0x1800075f8  mov     [rsp+1D0h+var_178], rax
0x1800075fd  lea     rax, [rbp+0A0h+var_11C]
0x180007601  mov     [rsp+1D0h+var_180], rax
0x180007606  lea     rax, [rbp+0A0h+var_C0]
0x18000760a  mov     [rsp+1D0h+var_188], rax
0x18000760f  lea     rax, [rbp+0A0h+var_118]
0x180007613  mov     [rsp+1D0h+var_190], rax
0x180007618  lea     rax, [rbp+0A0h+var_B8]
0x18000761c  mov     [rsp+1D0h+var_198], rax
0x180007621  lea     rax, [rbp+0A0h+SRWLock]
0x180007625  mov     [rsp+1D0h+var_1A0], rax
0x18000762a  lea     rax, [rbp+0A0h+var_B0]
0x18000762e  mov     [rsp+1D0h+var_1A8], rax
0x180007633  lea     rax, [rbp+0A0h+var_108]
0x180007637  mov     [rsp+1D0h+var_1B0], rax
0x18000763c  mov     [rbp+0A0h+var_100], esi
0x18000763f  mov     [rbp+0A0h+var_FC], 1
0x180007646  mov     [rbp+0A0h+var_B0], 1000000h
0x18000764e  mov     [rbp+0A0h+var_108], 0
0x180007656  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000765b  jmp     loc_180007762
0x180007660  lea     rdx, [rbp+0A0h+var_108]
0x180007664  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180007669  mov     rax, [rbx+110h]
0x180007670  mov     rcx, [rbp+0A0h+var_108]; SRWLock
0x180007674  mov     dword ptr [rax], 2
0x18000767a  test    rcx, rcx
0x18000767d  jz      short loc_180007685
0x18000767f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007685  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000768a  mov     rdi, rax
0x18000768d  mov     ecx, [rax]
0x18000768f  cmp     ecx, 5
0x180007692  jbe     loc_180007762
0x180007698  mov     rax, [rax+18h]
0x18000769c  mov     rdx, 400000000000h
0x1800076a6  mov     rcx, [rdi+10h]
0x1800076aa  test    rdx, rcx
0x1800076ad  jz      loc_180007762
0x1800076b3  mov     rcx, rax
0x1800076b6  and     rcx, rdx
0x1800076b9  cmp     rcx, rax
0x1800076bc  jnz     loc_180007762
0x1800076c2  mov     dword ptr [rbp+0A0h+SRWLock], esi
0x1800076c5  mov     [rbp+0A0h+var_118], 1
0x1800076cc  call    cs:__imp_GetCurrentThreadId
0x1800076d2  mov     r8, [rbx+110h]
0x1800076d9  lea     rdx, word_180022BCE
0x1800076e0  mov     [rbp+0A0h+var_11C], eax
0x1800076e3  xor     r9d, r9d
0x1800076e6  mov     rcx, rdi
0x1800076e9  mov     [rbp+0A0h+var_38], 4
0x1800076f1  mov     [rbp+0A0h+var_48], 4
0x1800076f9  mov     eax, [r8+48h]
0x1800076fd  add     r8, 8
0x180007701  mov     [rbp+0A0h+var_120], eax
0x180007704  lea     rax, [rbp+0A0h+SRWLock]
0x180007708  mov     [rbp+0A0h+var_40], rax
0x18000770c  lea     rax, [rbp+0A0h+var_118]
0x180007710  mov     [rbp+0A0h+var_50], rax
0x180007714  lea     rax, [rbp+0A0h+var_11C]
0x180007718  mov     [rbp+0A0h+var_60], rax
0x18000771c  lea     rax, [rbp+0A0h+var_120]
0x180007720  mov     [rbp+0A0h+var_70], rax
0x180007724  lea     rax, [rbp+0A0h+var_108]
0x180007728  mov     [rbp+0A0h+var_80], rax
0x18000772c  lea     rax, [rbp+0A0h+var_A0]
0x180007730  mov     [rsp+1D0h+var_1A8], rax
0x180007735  mov     dword ptr [rsp+1D0h+var_1B0], 7
0x18000773d  mov     [rbp+0A0h+var_108], 0
0x180007745  mov     [rbp+0A0h+var_58], 4
0x18000774d  mov     [rbp+0A0h+var_68], 4
0x180007755  mov     [rbp+0A0h+var_78], 8
0x18000775d  call    _tlgWriteTransfer_EventWriteTransfer
0x180007762  mov     rcx, rbx
0x180007765  call    ?IgnoreCurrentThread@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000776a  mov     rcx, [rbp+0A0h+var_30]
0x18000776e  xor     rcx, rsp; StackCookie
0x180007771  call    __security_check_cookie
0x180007776  add     rsp, 1B8h
0x18000777d  pop     rdi
0x18000777e  pop     rsi
0x18000777f  pop     rbx
0x180007780  pop     rbp
0x180007781  retn
```
