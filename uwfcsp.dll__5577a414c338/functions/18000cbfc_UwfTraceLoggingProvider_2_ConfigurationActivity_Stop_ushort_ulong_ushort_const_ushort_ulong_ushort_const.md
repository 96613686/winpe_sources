# UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ushort *,ulong,ushort const *>(ushort *,ulong,ushort const *)

- ea: `0x18000cbfc`
- end: `0x18000cfd1`
- name: `??$Stop@PEAGKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEAGKPEBG@Z`
- size: `981`
- prototype: `__int64 __fastcall(__int64, int *, int, int *)`
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
- `0x1800022a4`
- `0x18000946c`
- `0x180009644`
- `0x180009f60`
- `0x18000cbfc`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ce5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ce5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cea8`

## pseudocode

```c
__int64 __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned short *,unsigned long,unsigned short const *>(
        __int64 a1,
        int *a2,
        int a3,
        int *a4)
{
  __int64 v4; // r14
  int v9; // eax
  __int64 v10; // r14
  RTL_SRWLOCK *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r8
  int v18; // edi
  RTL_SRWLOCK *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r14
  __int64 v22; // rax
  DWORD CurrentThreadId; // eax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // ecx
  int v29; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v30; // [rsp+C4h] [rbp-7Ch] BYREF
  int v31; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-70h] BYREF
  PSRWLOCK v33; // [rsp+D8h] [rbp-68h] BYREF
  int v34; // [rsp+E0h] [rbp-60h] BYREF
  int v35; // [rsp+E4h] [rbp-5Ch] BYREF
  int v36; // [rsp+E8h] [rbp-58h] BYREF
  int v37; // [rsp+ECh] [rbp-54h] BYREF
  int *v38; // [rsp+F0h] [rbp-50h] BYREF
  int *v39; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v40; // [rsp+100h] [rbp-40h] BYREF
  __int64 v41; // [rsp+108h] [rbp-38h] BYREF
  __int64 v42; // [rsp+110h] [rbp-30h] BYREF
  __int64 v43; // [rsp+118h] [rbp-28h] BYREF
  __int64 v44; // [rsp+120h] [rbp-20h] BYREF
  __int64 v45; // [rsp+128h] [rbp-18h] BYREF
  __int64 v46; // [rsp+130h] [rbp-10h] BYREF
  __int64 v47; // [rsp+138h] [rbp-8h] BYREF
  __int64 v48; // [rsp+140h] [rbp+0h] BYREF
  char v49[32]; // [rsp+150h] [rbp+10h] BYREF
  PSRWLOCK *v50; // [rsp+170h] [rbp+30h]
  __int64 v51; // [rsp+178h] [rbp+38h]
  int *v52; // [rsp+180h] [rbp+40h]
  __int64 v53; // [rsp+188h] [rbp+48h]
  DWORD *v54; // [rsp+190h] [rbp+50h]
  __int64 v55; // [rsp+198h] [rbp+58h]
  int *v56; // [rsp+1A0h] [rbp+60h]
  __int64 v57; // [rsp+1A8h] [rbp+68h]
  int *v58; // [rsp+1B0h] [rbp+70h]
  int v59; // [rsp+1B8h] [rbp+78h]
  int v60; // [rsp+1BCh] [rbp+7Ch]
  PSRWLOCK *p_SRWLock; // [rsp+1C0h] [rbp+80h]
  __int64 v62; // [rsp+1C8h] [rbp+88h]
  int *v63; // [rsp+1D0h] [rbp+90h]
  int v64; // [rsp+1D8h] [rbp+98h]
  int v65; // [rsp+1DCh] [rbp+9Ch]

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
        v40 = *(_QWORD *)(v10 + 120);
        v41 = *(_QWORD *)(v10 + 112);
        v36 = *(_DWORD *)(v10 + 104);
        v17 = *(_QWORD *)(a1 + 272);
        v42 = *(_QWORD *)(v10 + 96);
        v43 = *(_QWORD *)(v10 + 88);
        v37 = *(_DWORD *)(v10 + 80);
        v44 = *(_QWORD *)(v10 + 72);
        v29 = *(_DWORD *)(v10 + 32);
        v45 = *(_QWORD *)(v10 + 24);
        v30 = *(_DWORD *)v10;
        v46 = *(_QWORD *)(v10 + 128);
        v31 = *(_DWORD *)(v10 + 64);
        v47 = *(_QWORD *)(v10 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v10 + 8);
        v38 = a4;
        v34 = a3;
        v39 = a2;
        v35 = 3;
        v48 = 0x1000000;
        v33 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v15,
          (unsigned int)&dword_1800236FC,
          v17 + 8,
          v15,
          (__int64)&v33,
          (__int64)&v48,
          (__int64)&SRWLock,
          (__int64)&v47,
          (__int64)&v31,
          (__int64)&v46,
          (__int64)&v30,
          (__int64)&v45,
          (__int64)&v29,
          (__int64)&v44,
          (__int64)&v37,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v36,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v35,
          (__int64)&v39,
          (__int64)&v34,
          (__int64)&v38);
      }
    }
  }
  else
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v33);
    v18 = 2;
    v19 = v33;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v19 )
      ReleaseSRWLockExclusive(v19);
    v20 = UwfTraceLoggingProvider<2>::Provider();
    v21 = v20;
    if ( *(_DWORD *)v20 > 5u )
    {
      v22 = *(_QWORD *)(v20 + 24);
      v13 = 0x400000000000LL;
      if ( (*(_QWORD *)(v21 + 16) & 0x400000000000LL) != 0 && (v22 & 0x400000000000LL) == v22 )
      {
        LODWORD(SRWLock) = a3;
        v31 = 3;
        CurrentThreadId = GetCurrentThreadId();
        v24 = *(_QWORD *)(a1 + 272);
        v30 = CurrentThreadId;
        v29 = *(_DWORD *)(v24 + 72);
        v25 = -1;
        v33 = 0;
        if ( a4 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *((_WORD *)a4 + v26) );
          v27 = 2 * v26 + 2;
        }
        else
        {
          a4 = &dword_18001F7A4;
          v27 = 2;
        }
        v64 = v27;
        p_SRWLock = &SRWLock;
        v63 = a4;
        v65 = 0;
        v62 = 4;
        if ( a2 )
        {
          do
            ++v25;
          while ( *((_WORD *)a2 + v25) );
          v18 = 2 * v25 + 2;
        }
        else
        {
          a2 = &dword_18001F7A4;
        }
        v58 = a2;
        v56 = &v31;
        v59 = v18;
        v54 = &v30;
        v60 = 0;
        v52 = &v29;
        v57 = 4;
        v50 = &v33;
        v55 = 4;
        v53 = 4;
        v51 = 8;
        tlgWriteTransfer_EventWriteTransfer(v21, &word_180023686, v24 + 8, 0, 9, v49);
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
0x18000cbfc  push    rbp
0x18000cbfe  push    rbx
0x18000cbff  push    rsi
0x18000cc00  push    rdi
0x18000cc01  push    r12
0x18000cc03  push    r13
0x18000cc05  push    r14
0x18000cc07  push    r15
0x18000cc09  lea     rbp, [rsp-0B8h]
0x18000cc11  sub     rsp, 1F8h
0x18000cc18  mov     rax, cs:__security_cookie
0x18000cc1f  xor     rax, rsp
0x18000cc22  mov     [rbp+0F0h+var_50], rax
0x18000cc29  mov     r14, [rcx+110h]
0x18000cc30  xor     r13d, r13d
0x18000cc33  mov     rsi, r9
0x18000cc36  mov     r12d, r8d
0x18000cc39  mov     r15, rdx
0x18000cc3c  mov     rbx, rcx
0x18000cc3f  mov     eax, [r14+48h]
0x18000cc43  test    eax, eax
0x18000cc45  jns     loc_18000CE3A
0x18000cc4b  add     r14, 50h ; 'P'
0x18000cc4f  cmp     eax, [r14+8]
0x18000cc53  jnz     loc_18000CE3A
0x18000cc59  test    r14, r14
0x18000cc5c  jz      loc_18000CE3A
0x18000cc62  lea     rdx, [rbp+0F0h+SRWLock]
0x18000cc66  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cc6b  mov     rax, [rbx+110h]
0x18000cc72  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x18000cc76  mov     dword ptr [rax], 2
0x18000cc7c  test    rcx, rcx
0x18000cc7f  jz      short loc_18000CC87
0x18000cc81  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc87  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000cc8c  mov     r9, rax
0x18000cc8f  mov     ecx, [rax]
0x18000cc91  cmp     ecx, 5
0x18000cc94  jbe     loc_18000CFA6
0x18000cc9a  mov     rax, [rax+18h]
0x18000cc9e  mov     rdx, 400000000000h
0x18000cca8  mov     rcx, [r9+10h]
0x18000ccac  test    rdx, rcx
0x18000ccaf  jz      loc_18000CFA6
0x18000ccb5  mov     rcx, rax
0x18000ccb8  and     rcx, rdx
0x18000ccbb  cmp     rcx, rax
0x18000ccbe  jnz     loc_18000CFA6
0x18000ccc4  mov     rax, [r14+78h]
0x18000ccc8  lea     rdx, dword_1800236FC
0x18000cccf  mov     [rbp+0F0h+var_130], rax
0x18000ccd3  mov     rcx, r9
0x18000ccd6  mov     rax, [r14+70h]
0x18000ccda  mov     [rbp+0F0h+var_128], rax
0x18000ccde  mov     eax, [r14+68h]
0x18000cce2  mov     [rbp+0F0h+var_148], eax
0x18000cce5  mov     rax, [r14+60h]
0x18000cce9  mov     r8, [rbx+110h]
0x18000ccf0  mov     [rbp+0F0h+var_120], rax
0x18000ccf4  add     r8, 8
0x18000ccf8  mov     rax, [r14+58h]
0x18000ccfc  mov     [rbp+0F0h+var_118], rax
0x18000cd00  mov     eax, [r14+50h]
0x18000cd04  mov     [rbp+0F0h+var_144], eax
0x18000cd07  mov     rax, [r14+48h]
0x18000cd0b  mov     [rbp+0F0h+var_110], rax
0x18000cd0f  mov     eax, [r14+20h]
0x18000cd13  mov     [rbp+0F0h+var_170], eax
0x18000cd16  mov     rax, [r14+18h]
0x18000cd1a  mov     [rbp+0F0h+var_108], rax
0x18000cd1e  mov     eax, [r14]
0x18000cd21  mov     [rbp+0F0h+var_16C], eax
0x18000cd24  mov     rax, [r14+80h]
0x18000cd2b  mov     [rbp+0F0h+var_100], rax
0x18000cd2f  mov     eax, [r14+40h]
0x18000cd33  mov     [rbp+0F0h+var_168], eax
0x18000cd36  mov     rax, [r14+38h]
0x18000cd3a  mov     [rbp+0F0h+var_F8], rax
0x18000cd3e  mov     eax, [r14+8]
0x18000cd42  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x18000cd45  lea     rax, [rbp+0F0h+var_140]
0x18000cd49  mov     [rsp+230h+var_178], rax
0x18000cd51  lea     rax, [rbp+0F0h+var_150]
0x18000cd55  mov     [rsp+230h+var_180], rax
0x18000cd5d  lea     rax, [rbp+0F0h+var_138]
0x18000cd61  mov     [rsp+230h+var_188], rax
0x18000cd69  lea     rax, [rbp+0F0h+var_14C]
0x18000cd6d  mov     [rsp+230h+var_190], rax
0x18000cd75  lea     rax, [rbp+0F0h+var_130]
0x18000cd79  mov     [rsp+230h+var_198], rax
0x18000cd81  lea     rax, [rbp+0F0h+var_128]
0x18000cd85  mov     [rsp+230h+var_1A0], rax
0x18000cd8d  lea     rax, [rbp+0F0h+var_148]
0x18000cd91  mov     [rsp+230h+var_1A8], rax
0x18000cd99  lea     rax, [rbp+0F0h+var_120]
0x18000cd9d  mov     [rsp+230h+var_1B0], rax
0x18000cda5  lea     rax, [rbp+0F0h+var_118]
0x18000cda9  mov     [rsp+230h+var_1B8], rax
0x18000cdae  lea     rax, [rbp+0F0h+var_144]
0x18000cdb2  mov     [rsp+230h+var_1C0], rax
0x18000cdb7  lea     rax, [rbp+0F0h+var_110]
0x18000cdbb  mov     [rsp+230h+var_1C8], rax
0x18000cdc0  lea     rax, [rbp+0F0h+var_170]
0x18000cdc4  mov     [rsp+230h+var_1D0], rax
0x18000cdc9  lea     rax, [rbp+0F0h+var_108]
0x18000cdcd  mov     [rsp+230h+var_1D8], rax
0x18000cdd2  lea     rax, [rbp+0F0h+var_16C]
0x18000cdd6  mov     [rsp+230h+var_1E0], rax
0x18000cddb  lea     rax, [rbp+0F0h+var_100]
0x18000cddf  mov     [rsp+230h+var_1E8], rax
0x18000cde4  lea     rax, [rbp+0F0h+var_168]
0x18000cde8  mov     [rsp+230h+var_1F0], rax
0x18000cded  lea     rax, [rbp+0F0h+var_F8]
0x18000cdf1  mov     [rsp+230h+var_1F8], rax
0x18000cdf6  lea     rax, [rbp+0F0h+SRWLock]
0x18000cdfa  mov     [rsp+230h+var_200], rax
0x18000cdff  lea     rax, [rbp+0F0h+var_F0]
0x18000ce03  mov     [rsp+230h+var_208], rax
0x18000ce08  lea     rax, [rbp+0F0h+var_158]
0x18000ce0c  mov     [rsp+230h+var_210], rax
0x18000ce11  mov     [rbp+0F0h+var_140], rsi
0x18000ce15  mov     [rbp+0F0h+var_150], r12d
0x18000ce19  mov     [rbp+0F0h+var_138], r15
0x18000ce1d  mov     [rbp+0F0h+var_14C], 3
0x18000ce24  mov     [rbp+0F0h+var_F0], 1000000h
0x18000ce2c  mov     [rbp+0F0h+var_158], r13
0x18000ce30  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U4@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564646@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000ce35  jmp     loc_18000CFA6
0x18000ce3a  lea     rdx, [rbp+0F0h+var_158]
0x18000ce3e  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ce43  mov     rax, [rbx+110h]
0x18000ce4a  mov     edi, 2
0x18000ce4f  mov     rcx, [rbp+0F0h+var_158]; SRWLock
0x18000ce53  mov     [rax], edi
0x18000ce55  test    rcx, rcx
0x18000ce58  jz      short loc_18000CE60
0x18000ce5a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ce60  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000ce65  mov     r14, rax
0x18000ce68  mov     ecx, [rax]
0x18000ce6a  cmp     ecx, 5
0x18000ce6d  jbe     loc_18000CFA6
0x18000ce73  mov     rax, [rax+18h]
0x18000ce77  mov     rdx, 400000000000h
0x18000ce81  mov     rcx, [r14+10h]
0x18000ce85  test    rdx, rcx
0x18000ce88  jz      loc_18000CFA6
0x18000ce8e  mov     rcx, rax
0x18000ce91  and     rcx, rdx
0x18000ce94  cmp     rcx, rax
0x18000ce97  jnz     loc_18000CFA6
0x18000ce9d  mov     dword ptr [rbp+0F0h+SRWLock], r12d
0x18000cea1  mov     [rbp+0F0h+var_168], 3
0x18000cea8  call    cs:__imp_GetCurrentThreadId
0x18000ceae  mov     r8, [rbx+110h]
0x18000ceb5  mov     [rbp+0F0h+var_16C], eax
0x18000ceb8  mov     eax, [r8+48h]
0x18000cebc  mov     [rbp+0F0h+var_170], eax
0x18000cebf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cec3  mov     [rbp+0F0h+var_158], r13
0x18000cec7  test    rsi, rsi
0x18000ceca  jz      short loc_18000CEE2
0x18000cecc  mov     rcx, rax
0x18000cecf  inc     rcx
0x18000ced2  cmp     [rsi+rcx*2], r13w
0x18000ced7  jnz     short loc_18000CECF
0x18000ced9  lea     ecx, ds:2[rcx*2]
0x18000cee0  jmp     short loc_18000CEEB
0x18000cee2  lea     rsi, dword_18001F7A4
0x18000cee9  mov     ecx, edi
0x18000ceeb  mov     [rbp+0F0h+var_58], ecx
0x18000cef1  lea     rcx, [rbp+0F0h+SRWLock]
0x18000cef5  mov     [rbp+0F0h+var_70], rcx
0x18000cefc  mov     [rbp+0F0h+var_60], rsi
0x18000cf03  mov     [rbp+0F0h+var_54], r13d
0x18000cf0a  mov     [rbp+0F0h+var_68], 4
0x18000cf15  test    r15, r15
0x18000cf18  jz      short loc_18000CF2D
0x18000cf1a  inc     rax
0x18000cf1d  cmp     [r15+rax*2], r13w
0x18000cf22  jnz     short loc_18000CF1A
0x18000cf24  lea     edi, ds:2[rax*2]
0x18000cf2b  jmp     short loc_18000CF34
0x18000cf2d  lea     r15, dword_18001F7A4
0x18000cf34  lea     rax, [rbp+0F0h+var_168]
0x18000cf38  mov     [rbp+0F0h+var_80], r15
0x18000cf3c  mov     [rbp+0F0h+var_90], rax
0x18000cf40  lea     rdx, word_180023686
0x18000cf47  lea     rax, [rbp+0F0h+var_16C]
0x18000cf4b  mov     [rbp+0F0h+var_78], edi
0x18000cf4e  mov     [rbp+0F0h+var_A0], rax
0x18000cf52  add     r8, 8
0x18000cf56  lea     rax, [rbp+0F0h+var_170]
0x18000cf5a  mov     [rbp+0F0h+var_74], r13d
0x18000cf5e  mov     [rbp+0F0h+var_B0], rax
0x18000cf62  xor     r9d, r9d
0x18000cf65  lea     rax, [rbp+0F0h+var_158]
0x18000cf69  mov     [rbp+0F0h+var_88], 4
0x18000cf71  mov     [rbp+0F0h+var_C0], rax
0x18000cf75  mov     rcx, r14
0x18000cf78  lea     rax, [rbp+0F0h+var_E0]
0x18000cf7c  mov     [rbp+0F0h+var_98], 4
0x18000cf84  mov     [rsp+230h+var_208], rax
0x18000cf89  mov     dword ptr [rsp+230h+var_210], 9
0x18000cf91  mov     [rbp+0F0h+var_A8], 4
0x18000cf99  mov     [rbp+0F0h+var_B8], 8
0x18000cfa1  call    _tlgWriteTransfer_EventWriteTransfer
0x18000cfa6  mov     rcx, rbx
0x18000cfa9  call    ?IgnoreCurrentThread@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000cfae  mov     rcx, [rbp+0F0h+var_50]
0x18000cfb5  xor     rcx, rsp; StackCookie
0x18000cfb8  call    __security_check_cookie
0x18000cfbd  add     rsp, 1F8h
0x18000cfc4  pop     r15
0x18000cfc6  pop     r14
0x18000cfc8  pop     r13
0x18000cfca  pop     r12
0x18000cfcc  pop     rdi
0x18000cfcd  pop     rsi
0x18000cfce  pop     rbx
0x18000cfcf  pop     rbp
0x18000cfd0  retn
```
