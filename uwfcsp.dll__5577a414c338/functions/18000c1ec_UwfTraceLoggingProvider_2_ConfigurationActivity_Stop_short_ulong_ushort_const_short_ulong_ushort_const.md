# UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<short,ulong,ushort const *>(short,ulong,ushort const *)

- ea: `0x18000c1ec`
- end: `0x18000c5ae`
- name: `??$Stop@FKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXFKPEBG@Z`
- size: `962`
- prototype: `__int64 __fastcall(__int64, __int16, int, int *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000dcb0`
- `0x18000e300`
- `0x18000f340`
- `0x18000f8a0`

## callees

- `0x180001ecc`
- `0x180002600`
- `0x18000946c`
- `0x180009644`
- `0x180009f60`
- `0x18000c1ec`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c276`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c449`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c276`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c449`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c49c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c49c`

## pseudocode

```c
__int64 __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<short,unsigned long,unsigned short const *>(
        __int64 a1,
        __int16 a2,
        int a3,
        int *a4)
{
  __int64 v4; // rsi
  int v9; // eax
  __int64 v10; // rsi
  RTL_SRWLOCK *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r8
  RTL_SRWLOCK *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rsi
  __int64 v21; // rax
  DWORD CurrentThreadId; // eax
  __int64 v23; // r8
  __int64 v24; // rax
  int v25; // eax
  _WORD v27[2]; // [rsp+C0h] [rbp-80h] BYREF
  int v28; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v29; // [rsp+C8h] [rbp-78h] BYREF
  int v30; // [rsp+CCh] [rbp-74h] BYREF
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-70h] BYREF
  PSRWLOCK v32; // [rsp+D8h] [rbp-68h] BYREF
  int v33; // [rsp+E0h] [rbp-60h] BYREF
  int v34; // [rsp+E4h] [rbp-5Ch] BYREF
  int v35; // [rsp+E8h] [rbp-58h] BYREF
  int v36; // [rsp+ECh] [rbp-54h] BYREF
  int *v37; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v39; // [rsp+100h] [rbp-40h] BYREF
  __int64 v40; // [rsp+108h] [rbp-38h] BYREF
  __int64 v41; // [rsp+110h] [rbp-30h] BYREF
  __int64 v42; // [rsp+118h] [rbp-28h] BYREF
  __int64 v43; // [rsp+120h] [rbp-20h] BYREF
  __int64 v44; // [rsp+128h] [rbp-18h] BYREF
  __int64 v45; // [rsp+130h] [rbp-10h] BYREF
  __int64 v46; // [rsp+138h] [rbp-8h] BYREF
  char v47[32]; // [rsp+140h] [rbp+0h] BYREF
  PSRWLOCK *v48; // [rsp+160h] [rbp+20h]
  __int64 v49; // [rsp+168h] [rbp+28h]
  int *v50; // [rsp+170h] [rbp+30h]
  __int64 v51; // [rsp+178h] [rbp+38h]
  DWORD *v52; // [rsp+180h] [rbp+40h]
  __int64 v53; // [rsp+188h] [rbp+48h]
  int *v54; // [rsp+190h] [rbp+50h]
  __int64 v55; // [rsp+198h] [rbp+58h]
  _WORD *v56; // [rsp+1A0h] [rbp+60h]
  __int64 v57; // [rsp+1A8h] [rbp+68h]
  PSRWLOCK *p_SRWLock; // [rsp+1B0h] [rbp+70h]
  __int64 v59; // [rsp+1B8h] [rbp+78h]
  int *v60; // [rsp+1C0h] [rbp+80h]
  int v61; // [rsp+1C8h] [rbp+88h]
  int v62; // [rsp+1CCh] [rbp+8Ch]

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
        v38 = *(_QWORD *)(v10 + 120);
        v39 = *(_QWORD *)(v10 + 112);
        v35 = *(_DWORD *)(v10 + 104);
        v17 = *(_QWORD *)(a1 + 272);
        v40 = *(_QWORD *)(v10 + 96);
        v41 = *(_QWORD *)(v10 + 88);
        v36 = *(_DWORD *)(v10 + 80);
        v42 = *(_QWORD *)(v10 + 72);
        v28 = *(_DWORD *)(v10 + 32);
        v43 = *(_QWORD *)(v10 + 24);
        v29 = *(_DWORD *)v10;
        v44 = *(_QWORD *)(v10 + 128);
        v30 = *(_DWORD *)(v10 + 64);
        v45 = *(_QWORD *)(v10 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v10 + 8);
        v37 = a4;
        v33 = a3;
        v27[0] = a2;
        v34 = 3;
        v46 = 0x1000000;
        v32 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v15,
          (unsigned int)&word_180023376,
          v17 + 8,
          v15,
          (__int64)&v32,
          (__int64)&v46,
          (__int64)&SRWLock,
          (__int64)&v45,
          (__int64)&v30,
          (__int64)&v44,
          (__int64)&v29,
          (__int64)&v43,
          (__int64)&v28,
          (__int64)&v42,
          (__int64)&v36,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v35,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v34,
          (__int64)v27,
          (__int64)&v33,
          (__int64)&v37);
      }
    }
  }
  else
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v32);
    v18 = v32;
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
        LODWORD(SRWLock) = a3;
        v27[0] = a2;
        v30 = 3;
        CurrentThreadId = GetCurrentThreadId();
        v23 = *(_QWORD *)(a1 + 272);
        v29 = CurrentThreadId;
        v28 = *(_DWORD *)(v23 + 72);
        v32 = 0;
        if ( a4 )
        {
          v24 = -1;
          do
            ++v24;
          while ( *((_WORD *)a4 + v24) );
          v25 = 2 * v24 + 2;
        }
        else
        {
          a4 = &dword_18001F7A4;
          v25 = 2;
        }
        v61 = v25;
        v60 = a4;
        p_SRWLock = &SRWLock;
        v62 = 0;
        v56 = v27;
        v59 = 4;
        v54 = &v30;
        v57 = 2;
        v52 = &v29;
        v50 = &v28;
        v48 = &v32;
        v55 = 4;
        v53 = 4;
        v51 = 4;
        v49 = 8;
        tlgWriteTransfer_EventWriteTransfer(v20, &unk_180023300, v23 + 8, 0, 9, v47);
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
0x18000c1ec  mov     [rsp-8+arg_8], rbx
0x18000c1f1  mov     [rsp-8+arg_10], rsi
0x18000c1f6  push    rbp
0x18000c1f7  push    r12
0x18000c1f9  push    r13
0x18000c1fb  push    r14
0x18000c1fd  push    r15
0x18000c1ff  lea     rbp, [rsp-0A0h]
0x18000c207  sub     rsp, 1E0h
0x18000c20e  mov     rax, cs:__security_cookie
0x18000c215  xor     rax, rsp
0x18000c218  mov     [rbp+0C0h+var_30], rax
0x18000c21f  mov     rsi, [rcx+110h]
0x18000c226  xor     r13d, r13d
0x18000c229  mov     r14, r9
0x18000c22c  mov     r15d, r8d
0x18000c22f  movzx   r12d, dx
0x18000c233  mov     rbx, rcx
0x18000c236  mov     eax, [rsi+48h]
0x18000c239  test    eax, eax
0x18000c23b  jns     loc_18000C42A
0x18000c241  add     rsi, 50h ; 'P'
0x18000c245  cmp     eax, [rsi+8]
0x18000c248  jnz     loc_18000C42A
0x18000c24e  test    rsi, rsi
0x18000c251  jz      loc_18000C42A
0x18000c257  lea     rdx, [rbp+0C0h+SRWLock]
0x18000c25b  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c260  mov     rax, [rbx+110h]
0x18000c267  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x18000c26b  mov     dword ptr [rax], 2
0x18000c271  test    rcx, rcx
0x18000c274  jz      short loc_18000C27C
0x18000c276  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c27c  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000c281  mov     r9, rax
0x18000c284  mov     ecx, [rax]
0x18000c286  cmp     ecx, 5
0x18000c289  jbe     loc_18000C57A
0x18000c28f  mov     rax, [rax+18h]
0x18000c293  mov     rdx, 400000000000h
0x18000c29d  mov     rcx, [r9+10h]
0x18000c2a1  test    rdx, rcx
0x18000c2a4  jz      loc_18000C57A
0x18000c2aa  mov     rcx, rax
0x18000c2ad  and     rcx, rdx
0x18000c2b0  cmp     rcx, rax
0x18000c2b3  jnz     loc_18000C57A
0x18000c2b9  mov     rax, [rsi+78h]
0x18000c2bd  lea     rdx, word_180023376
0x18000c2c4  mov     [rbp+0C0h+var_108], rax
0x18000c2c8  mov     rcx, r9
0x18000c2cb  mov     rax, [rsi+70h]
0x18000c2cf  mov     [rbp+0C0h+var_100], rax
0x18000c2d3  mov     eax, [rsi+68h]
0x18000c2d6  mov     [rbp+0C0h+var_118], eax
0x18000c2d9  mov     rax, [rsi+60h]
0x18000c2dd  mov     r8, [rbx+110h]
0x18000c2e4  mov     [rbp+0C0h+var_F8], rax
0x18000c2e8  add     r8, 8
0x18000c2ec  mov     rax, [rsi+58h]
0x18000c2f0  mov     [rbp+0C0h+var_F0], rax
0x18000c2f4  mov     eax, [rsi+50h]
0x18000c2f7  mov     [rbp+0C0h+var_114], eax
0x18000c2fa  mov     rax, [rsi+48h]
0x18000c2fe  mov     [rbp+0C0h+var_E8], rax
0x18000c302  mov     eax, [rsi+20h]
0x18000c305  mov     [rbp+0C0h+var_13C], eax
0x18000c308  mov     rax, [rsi+18h]
0x18000c30c  mov     [rbp+0C0h+var_E0], rax
0x18000c310  mov     eax, [rsi]
0x18000c312  mov     [rbp+0C0h+var_138], eax
0x18000c315  mov     rax, [rsi+80h]
0x18000c31c  mov     [rbp+0C0h+var_D8], rax
0x18000c320  mov     eax, [rsi+40h]
0x18000c323  mov     [rbp+0C0h+var_134], eax
0x18000c326  mov     rax, [rsi+38h]
0x18000c32a  mov     [rbp+0C0h+var_D0], rax
0x18000c32e  mov     eax, [rsi+8]
0x18000c331  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x18000c334  lea     rax, [rbp+0C0h+var_110]
0x18000c338  mov     [rsp+200h+var_148], rax
0x18000c340  lea     rax, [rbp+0C0h+var_120]
0x18000c344  mov     [rsp+200h+var_150], rax
0x18000c34c  lea     rax, [rbp+0C0h+var_140]
0x18000c350  mov     [rsp+200h+var_158], rax
0x18000c358  lea     rax, [rbp+0C0h+var_11C]
0x18000c35c  mov     [rsp+200h+var_160], rax
0x18000c364  lea     rax, [rbp+0C0h+var_108]
0x18000c368  mov     [rsp+200h+var_168], rax
0x18000c370  lea     rax, [rbp+0C0h+var_100]
0x18000c374  mov     [rsp+200h+var_170], rax
0x18000c37c  lea     rax, [rbp+0C0h+var_118]
0x18000c380  mov     [rsp+200h+var_178], rax
0x18000c388  lea     rax, [rbp+0C0h+var_F8]
0x18000c38c  mov     [rsp+200h+var_180], rax
0x18000c394  lea     rax, [rbp+0C0h+var_F0]
0x18000c398  mov     [rsp+200h+var_188], rax
0x18000c39d  lea     rax, [rbp+0C0h+var_114]
0x18000c3a1  mov     [rsp+200h+var_190], rax
0x18000c3a6  lea     rax, [rbp+0C0h+var_E8]
0x18000c3aa  mov     [rsp+200h+var_198], rax
0x18000c3af  lea     rax, [rbp+0C0h+var_13C]
0x18000c3b3  mov     [rsp+200h+var_1A0], rax
0x18000c3b8  lea     rax, [rbp+0C0h+var_E0]
0x18000c3bc  mov     [rsp+200h+var_1A8], rax
0x18000c3c1  lea     rax, [rbp+0C0h+var_138]
0x18000c3c5  mov     [rsp+200h+var_1B0], rax
0x18000c3ca  lea     rax, [rbp+0C0h+var_D8]
0x18000c3ce  mov     [rsp+200h+var_1B8], rax
0x18000c3d3  lea     rax, [rbp+0C0h+var_134]
0x18000c3d7  mov     [rsp+200h+var_1C0], rax
0x18000c3dc  lea     rax, [rbp+0C0h+var_D0]
0x18000c3e0  mov     [rsp+200h+var_1C8], rax
0x18000c3e5  lea     rax, [rbp+0C0h+SRWLock]
0x18000c3e9  mov     [rsp+200h+var_1D0], rax
0x18000c3ee  lea     rax, [rbp+0C0h+var_C8]
0x18000c3f2  mov     [rsp+200h+var_1D8], rax
0x18000c3f7  lea     rax, [rbp+0C0h+var_128]
0x18000c3fb  mov     [rsp+200h+var_1E0], rax
0x18000c400  mov     [rbp+0C0h+var_110], r14
0x18000c404  mov     [rbp+0C0h+var_120], r15d
0x18000c408  mov     [rbp+0C0h+var_140], r12w
0x18000c40d  mov     [rbp+0C0h+var_11C], 3
0x18000c414  mov     [rbp+0C0h+var_C8], 1000000h
0x18000c41c  mov     [rbp+0C0h+var_128], r13
0x18000c420  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U?$_tlgWrapperByVal@$01@@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564AEBU?$_tlgWrapperByVal@$01@@46@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000c425  jmp     loc_18000C57A
0x18000c42a  lea     rdx, [rbp+0C0h+var_128]
0x18000c42e  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c433  mov     rax, [rbx+110h]
0x18000c43a  mov     rcx, [rbp+0C0h+var_128]; SRWLock
0x18000c43e  mov     dword ptr [rax], 2
0x18000c444  test    rcx, rcx
0x18000c447  jz      short loc_18000C44F
0x18000c449  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c44f  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000c454  mov     rsi, rax
0x18000c457  mov     ecx, [rax]
0x18000c459  cmp     ecx, 5
0x18000c45c  jbe     loc_18000C57A
0x18000c462  mov     rax, [rax+18h]
0x18000c466  mov     rdx, 400000000000h
0x18000c470  mov     rcx, [rsi+10h]
0x18000c474  test    rdx, rcx
0x18000c477  jz      loc_18000C57A
0x18000c47d  mov     rcx, rax
0x18000c480  and     rcx, rdx
0x18000c483  cmp     rcx, rax
0x18000c486  jnz     loc_18000C57A
0x18000c48c  mov     dword ptr [rbp+0C0h+SRWLock], r15d
0x18000c490  mov     [rbp+0C0h+var_140], r12w
0x18000c495  mov     [rbp+0C0h+var_134], 3
0x18000c49c  call    cs:__imp_GetCurrentThreadId
0x18000c4a2  mov     r8, [rbx+110h]
0x18000c4a9  mov     [rbp+0C0h+var_138], eax
0x18000c4ac  mov     eax, [r8+48h]
0x18000c4b0  mov     [rbp+0C0h+var_13C], eax
0x18000c4b3  mov     [rbp+0C0h+var_128], r13
0x18000c4b7  test    r14, r14
0x18000c4ba  jz      short loc_18000C4D3
0x18000c4bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c4c0  inc     rax
0x18000c4c3  cmp     [r14+rax*2], r13w
0x18000c4c8  jnz     short loc_18000C4C0
0x18000c4ca  lea     eax, ds:2[rax*2]
0x18000c4d1  jmp     short loc_18000C4DF
0x18000c4d3  lea     r14, dword_18001F7A4
0x18000c4da  mov     eax, 2
0x18000c4df  mov     [rbp+0C0h+var_38], eax
0x18000c4e5  lea     rdx, unk_180023300
0x18000c4ec  lea     rax, [rbp+0C0h+SRWLock]
0x18000c4f0  mov     [rbp+0C0h+var_40], r14
0x18000c4f7  mov     [rbp+0C0h+var_50], rax
0x18000c4fb  add     r8, 8
0x18000c4ff  lea     rax, [rbp+0C0h+var_140]
0x18000c503  mov     [rbp+0C0h+var_34], r13d
0x18000c50a  mov     [rbp+0C0h+var_60], rax
0x18000c50e  xor     r9d, r9d
0x18000c511  lea     rax, [rbp+0C0h+var_134]
0x18000c515  mov     [rbp+0C0h+var_48], 4
0x18000c51d  mov     [rbp+0C0h+var_70], rax
0x18000c521  mov     rcx, rsi
0x18000c524  lea     rax, [rbp+0C0h+var_138]
0x18000c528  mov     [rbp+0C0h+var_58], 2
0x18000c530  mov     [rbp+0C0h+var_80], rax
0x18000c534  lea     rax, [rbp+0C0h+var_13C]
0x18000c538  mov     [rbp+0C0h+var_90], rax
0x18000c53c  lea     rax, [rbp+0C0h+var_128]
0x18000c540  mov     [rbp+0C0h+var_A0], rax
0x18000c544  lea     rax, [rbp+0C0h+var_C0]
0x18000c548  mov     [rsp+200h+var_1D8], rax
0x18000c54d  mov     dword ptr [rsp+200h+var_1E0], 9
0x18000c555  mov     [rbp+0C0h+var_68], 4
0x18000c55d  mov     [rbp+0C0h+var_78], 4
0x18000c565  mov     [rbp+0C0h+var_88], 4
0x18000c56d  mov     [rbp+0C0h+var_98], 8
0x18000c575  call    _tlgWriteTransfer_EventWriteTransfer
0x18000c57a  mov     rcx, rbx
0x18000c57d  call    ?IgnoreCurrentThread@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000c582  mov     rcx, [rbp+0C0h+var_30]
0x18000c589  xor     rcx, rsp; StackCookie
0x18000c58c  call    __security_check_cookie
0x18000c591  lea     r11, [rsp+200h+var_20]
0x18000c599  mov     rbx, [r11+38h]
0x18000c59d  mov     rsi, [r11+40h]
0x18000c5a1  mov     rsp, r11
0x18000c5a4  pop     r15
0x18000c5a6  pop     r14
0x18000c5a8  pop     r13
0x18000c5aa  pop     r12
0x18000c5ac  pop     rbp
0x18000c5ad  retn
```
