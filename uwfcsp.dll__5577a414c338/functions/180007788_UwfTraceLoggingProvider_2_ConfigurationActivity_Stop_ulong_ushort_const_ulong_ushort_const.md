# UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ushort const *>(ulong,ushort const *)

- ea: `0x180007788`
- end: `0x180007b12`
- name: `??$Stop@KPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKPEBG@Z`
- size: `906`
- prototype: `__int64 __fastcall(__int64, int, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008ee0`
- `0x18000d2d0`
- `0x18000e9f0`

## callees

- `0x180001594`
- `0x180001ecc`
- `0x180007788`
- `0x18000946c`
- `0x180009644`
- `0x180009f60`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007810`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800079d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007810`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800079d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a1f`

## pseudocode

```c
__int64 __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned short const *>(
        __int64 a1,
        int a2,
        int *a3)
{
  __int64 v3; // r14
  int v7; // eax
  __int64 v8; // r14
  RTL_SRWLOCK *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // r8
  int v16; // edi
  RTL_SRWLOCK *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r14
  __int64 v20; // rax
  DWORD CurrentThreadId; // eax
  __int64 v22; // r8
  __int64 v23; // rdi
  int v25; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v26; // [rsp+C4h] [rbp-7Ch] BYREF
  int v27; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-70h] BYREF
  PSRWLOCK v29; // [rsp+D8h] [rbp-68h] BYREF
  int v30; // [rsp+E0h] [rbp-60h] BYREF
  int v31; // [rsp+E4h] [rbp-5Ch] BYREF
  int v32; // [rsp+E8h] [rbp-58h] BYREF
  int v33; // [rsp+ECh] [rbp-54h] BYREF
  int *v34; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v35; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+100h] [rbp-40h] BYREF
  __int64 v37; // [rsp+108h] [rbp-38h] BYREF
  __int64 v38; // [rsp+110h] [rbp-30h] BYREF
  __int64 v39; // [rsp+118h] [rbp-28h] BYREF
  __int64 v40; // [rsp+120h] [rbp-20h] BYREF
  __int64 v41; // [rsp+128h] [rbp-18h] BYREF
  __int64 v42; // [rsp+130h] [rbp-10h] BYREF
  __int64 v43; // [rsp+138h] [rbp-8h] BYREF
  char v44[32]; // [rsp+140h] [rbp+0h] BYREF
  PSRWLOCK *v45; // [rsp+160h] [rbp+20h]
  __int64 v46; // [rsp+168h] [rbp+28h]
  int *v47; // [rsp+170h] [rbp+30h]
  __int64 v48; // [rsp+178h] [rbp+38h]
  DWORD *v49; // [rsp+180h] [rbp+40h]
  __int64 v50; // [rsp+188h] [rbp+48h]
  int *v51; // [rsp+190h] [rbp+50h]
  __int64 v52; // [rsp+198h] [rbp+58h]
  PSRWLOCK *p_SRWLock; // [rsp+1A0h] [rbp+60h]
  __int64 v54; // [rsp+1A8h] [rbp+68h]
  int *v55; // [rsp+1B0h] [rbp+70h]
  int v56; // [rsp+1B8h] [rbp+78h]
  int v57; // [rsp+1BCh] [rbp+7Ch]

  v3 = *(_QWORD *)(a1 + 272);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = v3 + 80, v7 == *(_DWORD *)(v8 + 8)) && v8 )
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    v9 = SRWLock;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = UwfTraceLoggingProvider<2>::Provider();
    v13 = v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      v14 = *(_QWORD *)(v10 + 24);
      v11 = 0x400000000000LL;
      if ( (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0 && (v14 & 0x400000000000LL) == v14 )
      {
        v35 = *(_QWORD *)(v8 + 120);
        v36 = *(_QWORD *)(v8 + 112);
        v15 = *(_QWORD *)(a1 + 272);
        v32 = *(_DWORD *)(v8 + 104);
        v37 = *(_QWORD *)(v8 + 96);
        v38 = *(_QWORD *)(v8 + 88);
        v33 = *(_DWORD *)(v8 + 80);
        v39 = *(_QWORD *)(v8 + 72);
        v25 = *(_DWORD *)(v8 + 32);
        v40 = *(_QWORD *)(v8 + 24);
        v26 = *(_DWORD *)v8;
        v41 = *(_QWORD *)(v8 + 128);
        v27 = *(_DWORD *)(v8 + 64);
        v42 = *(_QWORD *)(v8 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v8 + 8);
        v34 = a3;
        v30 = a2;
        v31 = 2;
        v43 = 0x1000000;
        v29 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v13,
          (unsigned int)byte_180022DE9,
          v15 + 8,
          v13,
          (__int64)&v29,
          (__int64)&v43,
          (__int64)&SRWLock,
          (__int64)&v42,
          (__int64)&v27,
          (__int64)&v41,
          (__int64)&v26,
          (__int64)&v40,
          (__int64)&v25,
          (__int64)&v39,
          (__int64)&v33,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&v32,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v34);
      }
    }
  }
  else
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v29);
    v16 = 2;
    v17 = v29;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v18 = UwfTraceLoggingProvider<2>::Provider();
    v19 = v18;
    if ( *(_DWORD *)v18 > 5u )
    {
      v20 = *(_QWORD *)(v18 + 24);
      v11 = 0x400000000000LL;
      if ( (*(_QWORD *)(v19 + 16) & 0x400000000000LL) != 0 && (v20 & 0x400000000000LL) == v20 )
      {
        LODWORD(SRWLock) = a2;
        v27 = 2;
        CurrentThreadId = GetCurrentThreadId();
        v22 = *(_QWORD *)(a1 + 272);
        v26 = CurrentThreadId;
        v25 = *(_DWORD *)(v22 + 72);
        v29 = 0;
        if ( a3 )
        {
          v23 = -1;
          do
            ++v23;
          while ( *((_WORD *)a3 + v23) );
          v16 = 2 * v23 + 2;
        }
        else
        {
          a3 = &dword_18001F7A4;
        }
        v55 = a3;
        p_SRWLock = &SRWLock;
        v56 = v16;
        v51 = &v27;
        v57 = 0;
        v49 = &v26;
        v54 = 4;
        v47 = &v25;
        v52 = 4;
        v45 = &v29;
        v50 = 4;
        v48 = 4;
        v46 = 8;
        tlgWriteTransfer_EventWriteTransfer(v19, byte_180022D79, v22 + 8, 0, 8, v44);
      }
    }
  }
  return wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v11,
           v12,
           v13);
}

```

## disassembly

```asm
0x180007788  mov     [rsp-8+arg_8], rbx
0x18000778d  mov     [rsp-8+arg_10], rsi
0x180007792  push    rbp
0x180007793  push    rdi
0x180007794  push    r12
0x180007796  push    r14
0x180007798  push    r15
0x18000779a  lea     rbp, [rsp-90h]
0x1800077a2  sub     rsp, 1D0h
0x1800077a9  mov     rax, cs:__security_cookie
0x1800077b0  xor     rax, rsp
0x1800077b3  mov     [rbp+0B0h+var_30], rax
0x1800077ba  mov     r14, [rcx+110h]
0x1800077c1  xor     r12d, r12d
0x1800077c4  mov     rsi, r8
0x1800077c7  mov     r15d, edx
0x1800077ca  mov     rbx, rcx
0x1800077cd  mov     eax, [r14+48h]
0x1800077d1  test    eax, eax
0x1800077d3  jns     loc_1800079B5
0x1800077d9  add     r14, 50h ; 'P'
0x1800077dd  cmp     eax, [r14+8]
0x1800077e1  jnz     loc_1800079B5
0x1800077e7  test    r14, r14
0x1800077ea  jz      loc_1800079B5
0x1800077f0  lea     rdx, [rbp+0B0h+SRWLock]
0x1800077f4  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800077f9  mov     rax, [rbx+110h]
0x180007800  lea     edi, [r12+2]
0x180007805  mov     rcx, [rbp+0B0h+SRWLock]; SRWLock
0x180007809  mov     [rax], edi
0x18000780b  test    rcx, rcx
0x18000780e  jz      short loc_180007816
0x180007810  call    cs:__imp_ReleaseSRWLockExclusive
0x180007816  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000781b  mov     r9, rax
0x18000781e  mov     ecx, [rax]
0x180007820  cmp     ecx, 5
0x180007823  jbe     loc_180007ADF
0x180007829  mov     rax, [rax+18h]
0x18000782d  mov     rdx, 400000000000h
0x180007837  mov     rcx, [r9+10h]
0x18000783b  test    rdx, rcx
0x18000783e  jz      loc_180007ADF
0x180007844  mov     rcx, rax
0x180007847  and     rcx, rdx
0x18000784a  cmp     rcx, rax
0x18000784d  jnz     loc_180007ADF
0x180007853  mov     rax, [r14+78h]
0x180007857  lea     rdx, byte_180022DE9
0x18000785e  mov     [rbp+0B0h+var_F8], rax
0x180007862  mov     rcx, r9
0x180007865  mov     rax, [r14+70h]
0x180007869  mov     [rbp+0B0h+var_F0], rax
0x18000786d  mov     eax, [r14+68h]
0x180007871  mov     r8, [rbx+110h]
0x180007878  mov     [rbp+0B0h+var_108], eax
0x18000787b  add     r8, 8
0x18000787f  mov     rax, [r14+60h]
0x180007883  mov     [rbp+0B0h+var_E8], rax
0x180007887  mov     rax, [r14+58h]
0x18000788b  mov     [rbp+0B0h+var_E0], rax
0x18000788f  mov     eax, [r14+50h]
0x180007893  mov     [rbp+0B0h+var_104], eax
0x180007896  mov     rax, [r14+48h]
0x18000789a  mov     [rbp+0B0h+var_D8], rax
0x18000789e  mov     eax, [r14+20h]
0x1800078a2  mov     [rbp+0B0h+var_130], eax
0x1800078a5  mov     rax, [r14+18h]
0x1800078a9  mov     [rbp+0B0h+var_D0], rax
0x1800078ad  mov     eax, [r14]
0x1800078b0  mov     [rbp+0B0h+var_12C], eax
0x1800078b3  mov     rax, [r14+80h]
0x1800078ba  mov     [rbp+0B0h+var_C8], rax
0x1800078be  mov     eax, [r14+40h]
0x1800078c2  mov     [rbp+0B0h+var_128], eax
0x1800078c5  mov     rax, [r14+38h]
0x1800078c9  mov     [rbp+0B0h+var_C0], rax
0x1800078cd  mov     eax, [r14+8]
0x1800078d1  mov     dword ptr [rbp+0B0h+SRWLock], eax
0x1800078d4  lea     rax, [rbp+0B0h+var_100]
0x1800078d8  mov     [rsp+1F0h+var_140], rax
0x1800078e0  lea     rax, [rbp+0B0h+var_110]
0x1800078e4  mov     [rsp+1F0h+var_148], rax
0x1800078ec  lea     rax, [rbp+0B0h+var_10C]
0x1800078f0  mov     [rsp+1F0h+var_150], rax
0x1800078f8  lea     rax, [rbp+0B0h+var_F8]
0x1800078fc  mov     [rsp+1F0h+var_158], rax
0x180007904  lea     rax, [rbp+0B0h+var_F0]
0x180007908  mov     [rsp+1F0h+var_160], rax
0x180007910  lea     rax, [rbp+0B0h+var_108]
0x180007914  mov     [rsp+1F0h+var_168], rax
0x18000791c  lea     rax, [rbp+0B0h+var_E8]
0x180007920  mov     [rsp+1F0h+var_170], rax
0x180007928  lea     rax, [rbp+0B0h+var_E0]
0x18000792c  mov     [rsp+1F0h+var_178], rax
0x180007931  lea     rax, [rbp+0B0h+var_104]
0x180007935  mov     [rsp+1F0h+var_180], rax
0x18000793a  lea     rax, [rbp+0B0h+var_D8]
0x18000793e  mov     [rsp+1F0h+var_188], rax
0x180007943  lea     rax, [rbp+0B0h+var_130]
0x180007947  mov     [rsp+1F0h+var_190], rax
0x18000794c  lea     rax, [rbp+0B0h+var_D0]
0x180007950  mov     [rsp+1F0h+var_198], rax
0x180007955  lea     rax, [rbp+0B0h+var_12C]
0x180007959  mov     [rsp+1F0h+var_1A0], rax
0x18000795e  lea     rax, [rbp+0B0h+var_C8]
0x180007962  mov     [rsp+1F0h+var_1A8], rax
0x180007967  lea     rax, [rbp+0B0h+var_128]
0x18000796b  mov     [rsp+1F0h+var_1B0], rax
0x180007970  lea     rax, [rbp+0B0h+var_C0]
0x180007974  mov     [rsp+1F0h+var_1B8], rax
0x180007979  lea     rax, [rbp+0B0h+SRWLock]
0x18000797d  mov     [rsp+1F0h+var_1C0], rax
0x180007982  lea     rax, [rbp+0B0h+var_B8]
0x180007986  mov     [rsp+1F0h+var_1C8], rax
0x18000798b  lea     rax, [rbp+0B0h+var_118]
0x18000798f  mov     [rsp+1F0h+var_1D0], rax
0x180007994  mov     [rbp+0B0h+var_100], rsi
0x180007998  mov     [rbp+0B0h+var_110], r15d
0x18000799c  mov     [rbp+0B0h+var_10C], edi
0x18000799f  mov     [rbp+0B0h+var_B8], 1000000h
0x1800079a7  mov     [rbp+0B0h+var_118], r12
0x1800079ab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456446@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800079b0  jmp     loc_180007ADF
0x1800079b5  lea     rdx, [rbp+0B0h+var_118]
0x1800079b9  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800079be  mov     rax, [rbx+110h]
0x1800079c5  mov     edi, 2
0x1800079ca  mov     rcx, [rbp+0B0h+var_118]; SRWLock
0x1800079ce  mov     [rax], edi
0x1800079d0  test    rcx, rcx
0x1800079d3  jz      short loc_1800079DB
0x1800079d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800079db  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x1800079e0  mov     r14, rax
0x1800079e3  mov     ecx, [rax]
0x1800079e5  cmp     ecx, 5
0x1800079e8  jbe     loc_180007ADF
0x1800079ee  mov     rax, [rax+18h]
0x1800079f2  mov     rdx, 400000000000h
0x1800079fc  mov     rcx, [r14+10h]
0x180007a00  test    rdx, rcx
0x180007a03  jz      loc_180007ADF
0x180007a09  mov     rcx, rax
0x180007a0c  and     rcx, rdx
0x180007a0f  cmp     rcx, rax
0x180007a12  jnz     loc_180007ADF
0x180007a18  mov     dword ptr [rbp+0B0h+SRWLock], r15d
0x180007a1c  mov     [rbp+0B0h+var_128], edi
0x180007a1f  call    cs:__imp_GetCurrentThreadId
0x180007a25  mov     r8, [rbx+110h]
0x180007a2c  mov     [rbp+0B0h+var_12C], eax
0x180007a2f  mov     eax, [r8+48h]
0x180007a33  mov     [rbp+0B0h+var_130], eax
0x180007a36  mov     [rbp+0B0h+var_118], r12
0x180007a3a  test    rsi, rsi
0x180007a3d  jz      short loc_180007A56
0x180007a3f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007a43  inc     rdi
0x180007a46  cmp     [rsi+rdi*2], r12w
0x180007a4b  jnz     short loc_180007A43
0x180007a4d  lea     edi, ds:2[rdi*2]
0x180007a54  jmp     short loc_180007A5D
0x180007a56  lea     rsi, dword_18001F7A4
0x180007a5d  lea     rax, [rbp+0B0h+SRWLock]
0x180007a61  mov     [rbp+0B0h+var_40], rsi
0x180007a65  mov     [rbp+0B0h+var_50], rax
0x180007a69  lea     rdx, byte_180022D79
0x180007a70  lea     rax, [rbp+0B0h+var_128]
0x180007a74  mov     [rbp+0B0h+var_38], edi
0x180007a77  mov     [rbp+0B0h+var_60], rax
0x180007a7b  add     r8, 8
0x180007a7f  lea     rax, [rbp+0B0h+var_12C]
0x180007a83  mov     [rbp+0B0h+var_34], r12d
0x180007a87  mov     [rbp+0B0h+var_70], rax
0x180007a8b  xor     r9d, r9d
0x180007a8e  lea     rax, [rbp+0B0h+var_130]
0x180007a92  mov     [rbp+0B0h+var_48], 4
0x180007a9a  mov     [rbp+0B0h+var_80], rax
0x180007a9e  mov     rcx, r14
0x180007aa1  lea     rax, [rbp+0B0h+var_118]
0x180007aa5  mov     [rbp+0B0h+var_58], 4
0x180007aad  mov     [rbp+0B0h+var_90], rax
0x180007ab1  lea     rax, [rbp+0B0h+var_B0]
0x180007ab5  mov     [rsp+1F0h+var_1C8], rax
0x180007aba  mov     dword ptr [rsp+1F0h+var_1D0], 8
0x180007ac2  mov     [rbp+0B0h+var_68], 4
0x180007aca  mov     [rbp+0B0h+var_78], 4
0x180007ad2  mov     [rbp+0B0h+var_88], 8
0x180007ada  call    _tlgWriteTransfer_EventWriteTransfer
0x180007adf  mov     rcx, rbx
0x180007ae2  call    ?IgnoreCurrentThread@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180007ae7  mov     rcx, [rbp+0B0h+var_30]
0x180007aee  xor     rcx, rsp; StackCookie
0x180007af1  call    __security_check_cookie
0x180007af6  lea     r11, [rsp+1F0h+var_20]
0x180007afe  mov     rbx, [r11+38h]
0x180007b02  mov     rsi, [r11+40h]
0x180007b06  mov     rsp, r11
0x180007b09  pop     r15
0x180007b0b  pop     r14
0x180007b0d  pop     r12
0x180007b0f  pop     rdi
0x180007b10  pop     rbp
0x180007b11  retn
```
