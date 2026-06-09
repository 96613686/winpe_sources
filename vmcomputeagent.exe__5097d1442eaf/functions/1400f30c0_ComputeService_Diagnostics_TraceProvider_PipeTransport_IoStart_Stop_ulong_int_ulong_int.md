# ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)

- ea: `0x1400f30c0`
- end: `0x1400f33f2`
- name: `??$Stop@AEAKH@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400f4190`
- `0x1400f4440`

## callees

- `0x140001f4c`
- `0x140002410`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x1400f30c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3132`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3325`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3132`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f3325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f3367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f3367`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<unsigned long &,int>(
        __int64 a1,
        int *a2,
        int *a3)
{
  __int64 v6; // rdi
  int v7; // eax
  __int64 v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 v11; // r8
  int v12; // r9d
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-80h] BYREF
  int v14; // [rsp+D8h] [rbp-78h] BYREF
  DWORD CurrentThreadId; // [rsp+DCh] [rbp-74h] BYREF
  int v16; // [rsp+E0h] [rbp-70h] BYREF
  int v17; // [rsp+E4h] [rbp-6Ch] BYREF
  int v18; // [rsp+E8h] [rbp-68h] BYREF
  int v19; // [rsp+ECh] [rbp-64h] BYREF
  int v20; // [rsp+F0h] [rbp-60h] BYREF
  int v21; // [rsp+F4h] [rbp-5Ch] BYREF
  int v22; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+100h] [rbp-50h] BYREF
  __int64 v24; // [rsp+108h] [rbp-48h] BYREF
  __int64 v25; // [rsp+110h] [rbp-40h] BYREF
  __int64 v26; // [rsp+118h] [rbp-38h] BYREF
  __int64 v27; // [rsp+120h] [rbp-30h] BYREF
  __int64 v28; // [rsp+128h] [rbp-28h] BYREF
  __int64 v29; // [rsp+130h] [rbp-20h] BYREF
  __int64 v30; // [rsp+138h] [rbp-18h] BYREF
  __int64 v31; // [rsp+140h] [rbp-10h] BYREF
  __int64 v32; // [rsp+148h] [rbp-8h] BYREF
  __int64 v33; // [rsp+150h] [rbp+0h] BYREF

  v6 = *(_QWORD *)(a1 + 272);
  v7 = *(_DWORD *)(v6 + 72);
  if ( v7 < 0 && (v8 = v6 + 80, v7 == *(_DWORD *)(v8 + 8)) && v8 )
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **(_DWORD **)(a1 + 272) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v9 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v9 > 4u
      && (*(_QWORD *)(v9 + 16) & 0x200LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x200LL) == *(_QWORD *)(v9 + 24) )
    {
      v17 = *a3;
      v18 = *a2;
      v24 = *(_QWORD *)(v8 + 48);
      v19 = *(_DWORD *)(v8 + 68);
      v20 = *(_DWORD *)(v8 + 16);
      v25 = *(_QWORD *)(v8 + 120);
      v26 = *(_QWORD *)(v8 + 112);
      v21 = *(_DWORD *)(v8 + 104);
      v27 = *(_QWORD *)(v8 + 96);
      v28 = *(_QWORD *)(v8 + 88);
      v22 = *(_DWORD *)(v8 + 80);
      v29 = *(_QWORD *)(v8 + 72);
      v14 = *(_DWORD *)(v8 + 32);
      v30 = *(_QWORD *)(v8 + 24);
      CurrentThreadId = *(_DWORD *)v8;
      v31 = *(_QWORD *)(v8 + 128);
      v16 = *(_DWORD *)(v8 + 64);
      v32 = *(_QWORD *)(v8 + 56);
      LODWORD(SRWLock) = *(_DWORD *)(v8 + 8);
      v33 = 0x1000000;
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (int)&byte_14013C6A9,
        *(_QWORD *)(a1 + 272) + 8,
        (__int64)&v23,
        (__int64)&v33,
        (__int64)&SRWLock,
        (__int64)&v32,
        (__int64)&v16,
        (__int64)&v31,
        (__int64)&CurrentThreadId,
        (__int64)&v30,
        (__int64)&v14,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v21,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v24,
        (__int64)&v18,
        (__int64)&v17);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **(_DWORD **)(a1 + 272) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v10 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v10 > 4u
      && (*(_QWORD *)(v10 + 16) & 0x200LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x200LL) == *(_QWORD *)(v10 + 24) )
    {
      LODWORD(SRWLock) = *a3;
      v16 = *a2;
      CurrentThreadId = GetCurrentThreadId();
      v11 = *(_QWORD *)(a1 + 272);
      v14 = *(_DWORD *)(v11 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_14013C5F1,
        v11 + 8,
        v12,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&CurrentThreadId,
        (__int64)&v16,
        (__int64)&SRWLock);
    }
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x1400f30c0  mov     [rsp-8+arg_8], rbx
0x1400f30c5  mov     [rsp-8+arg_10], rsi
0x1400f30ca  push    rbp
0x1400f30cb  push    rdi
0x1400f30cc  push    r14
0x1400f30ce  lea     rbp, [rsp-10h]
0x1400f30d3  sub     rsp, 160h
0x1400f30da  mov     rsi, r8
0x1400f30dd  mov     r14, rdx
0x1400f30e0  mov     rbx, rcx
0x1400f30e3  mov     rdi, [rcx+110h]
0x1400f30ea  mov     eax, [rdi+48h]
0x1400f30ed  test    eax, eax
0x1400f30ef  jns     loc_1400F32FE
0x1400f30f5  add     rdi, 50h ; 'P'
0x1400f30f9  cmp     eax, [rdi+8]
0x1400f30fc  jnz     loc_1400F32FE
0x1400f3102  test    rdi, rdi
0x1400f3105  jz      loc_1400F32FE
0x1400f310b  mov     [rbp+20h+SRWLock], 0
0x1400f3113  lea     rdx, [rbp+20h+SRWLock]
0x1400f3117  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400f311c  mov     rax, [rbx+110h]
0x1400f3123  mov     dword ptr [rax], 2
0x1400f3129  mov     rcx, [rbp+20h+SRWLock]; SRWLock
0x1400f312d  test    rcx, rcx
0x1400f3130  jz      short loc_1400F3138
0x1400f3132  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f3138  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400f313d  mov     r9, [rax+8]
0x1400f3141  mov     eax, [r9]
0x1400f3144  cmp     eax, 4
0x1400f3147  jbe     loc_1400F33C7
0x1400f314d  mov     rdx, [r9+18h]
0x1400f3151  mov     rax, [r9+10h]
0x1400f3155  mov     ecx, 200h
0x1400f315a  test    rcx, rax
0x1400f315d  jz      loc_1400F33C7
0x1400f3163  mov     rax, rdx
0x1400f3166  and     rax, rcx
0x1400f3169  cmp     rax, rdx
0x1400f316c  jnz     loc_1400F33C7
0x1400f3172  mov     eax, [rsi]
0x1400f3174  mov     dword ptr [rbp+20h+var_90+4], eax
0x1400f3177  mov     eax, [r14]
0x1400f317a  mov     dword ptr [rbp+20h+var_88], eax
0x1400f317d  mov     rax, [rdi+30h]
0x1400f3181  mov     [rbp+20h+var_68], rax
0x1400f3185  mov     eax, [rdi+44h]
0x1400f3188  mov     dword ptr [rbp+20h+var_88+4], eax
0x1400f318b  mov     eax, [rdi+10h]
0x1400f318e  mov     [rbp+20h+var_80], eax
0x1400f3191  mov     rax, [rdi+78h]
0x1400f3195  mov     [rbp+20h+var_60], rax
0x1400f3199  mov     rax, [rdi+70h]
0x1400f319d  mov     [rbp+20h+var_58], rax
0x1400f31a1  mov     eax, [rdi+68h]
0x1400f31a4  mov     [rbp+20h+var_7C], eax
0x1400f31a7  mov     rax, [rdi+60h]
0x1400f31ab  mov     [rbp+20h+var_50], rax
0x1400f31af  mov     rax, [rdi+58h]
0x1400f31b3  mov     [rbp+20h+var_48], rax
0x1400f31b7  mov     eax, [rdi+50h]
0x1400f31ba  mov     [rbp+20h+var_78], eax
0x1400f31bd  mov     rax, [rdi+48h]
0x1400f31c1  mov     [rbp+20h+var_40], rax
0x1400f31c5  mov     eax, [rdi+20h]
0x1400f31c8  mov     dword ptr [rbp+20h+var_98], eax
0x1400f31cb  mov     rax, [rdi+18h]
0x1400f31cf  mov     [rbp+20h+var_38], rax
0x1400f31d3  mov     eax, [rdi]
0x1400f31d5  mov     dword ptr [rbp+20h+var_98+4], eax
0x1400f31d8  mov     rax, [rdi+80h]
0x1400f31df  mov     [rbp+20h+var_30], rax
0x1400f31e3  mov     eax, [rdi+40h]
0x1400f31e6  mov     dword ptr [rbp+20h+var_90], eax
0x1400f31e9  mov     rax, [rdi+38h]
0x1400f31ed  mov     [rbp+20h+var_28], rax
0x1400f31f1  mov     eax, [rdi+8]
0x1400f31f4  mov     dword ptr [rbp+20h+SRWLock], eax
0x1400f31f7  mov     [rbp+20h+var_20], 1000000h
0x1400f31ff  mov     [rbp+20h+var_70], 0
0x1400f3207  mov     r8, [rbx+110h]
0x1400f320e  add     r8, 8; int
0x1400f3212  lea     rax, [rbp+20h+var_90+4]
0x1400f3216  mov     [rsp+170h+var_B0], rax; __int64
0x1400f321e  lea     rax, [rbp+20h+var_88]
0x1400f3222  mov     [rsp+170h+var_B8], rax; __int64
0x1400f322a  lea     rax, [rbp+20h+var_68]
0x1400f322e  mov     [rsp+170h+var_C0], rax; __int64
0x1400f3236  lea     rax, [rbp+20h+var_88+4]
0x1400f323a  mov     [rsp+170h+var_C8], rax; __int64
0x1400f3242  lea     rax, [rbp+20h+var_80]
0x1400f3246  mov     [rsp+170h+var_D0], rax; __int64
0x1400f324e  lea     rax, [rbp+20h+var_60]
0x1400f3252  mov     [rsp+170h+var_D8], rax; __int64
0x1400f325a  lea     rax, [rbp+20h+var_58]
0x1400f325e  mov     [rsp+170h+var_E0], rax; __int64
0x1400f3266  lea     rax, [rbp+20h+var_7C]
0x1400f326a  mov     [rsp+170h+var_E8], rax; __int64
0x1400f3272  lea     rax, [rbp+20h+var_50]
0x1400f3276  mov     [rsp+170h+var_F0], rax; __int64
0x1400f327e  lea     rax, [rbp+20h+var_48]
0x1400f3282  mov     [rsp+170h+var_F8], rax; __int64
0x1400f3287  lea     rax, [rbp+20h+var_78]
0x1400f328b  mov     [rsp+170h+var_100], rax; __int64
0x1400f3290  lea     rax, [rbp+20h+var_40]
0x1400f3294  mov     [rsp+170h+var_108], rax; __int64
0x1400f3299  lea     rax, [rbp+20h+var_98]
0x1400f329d  mov     [rsp+170h+var_110], rax; __int64
0x1400f32a2  lea     rax, [rbp+20h+var_38]
0x1400f32a6  mov     [rsp+170h+var_118], rax; __int64
0x1400f32ab  lea     rax, [rbp+20h+var_98+4]
0x1400f32af  mov     [rsp+170h+var_120], rax; __int64
0x1400f32b4  lea     rax, [rbp+20h+var_30]
0x1400f32b8  mov     [rsp+170h+var_128], rax; __int64
0x1400f32bd  lea     rax, [rbp+20h+var_90]
0x1400f32c1  mov     [rsp+170h+var_130], rax; __int64
0x1400f32c6  lea     rax, [rbp+20h+var_28]
0x1400f32ca  mov     [rsp+170h+var_138], rax; __int64
0x1400f32cf  lea     rax, [rbp+20h+SRWLock]
0x1400f32d3  mov     [rsp+170h+var_140], rax; __int64
0x1400f32d8  lea     rax, [rbp+20h+var_20]
0x1400f32dc  mov     [rsp+170h+var_148], rax; __int64
0x1400f32e1  lea     rax, [rbp+20h+var_70]
0x1400f32e5  mov     [rsp+170h+var_150], rax; __int64
0x1400f32ea  lea     rdx, byte_14013C6A9; int
0x1400f32f1  mov     rcx, r9; int
0x1400f32f4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400f32f9  jmp     loc_1400F33C7
0x1400f32fe  mov     [rbp+20h+SRWLock], 0
0x1400f3306  lea     rdx, [rbp+20h+SRWLock]
0x1400f330a  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400f330f  mov     rax, [rbx+110h]
0x1400f3316  mov     dword ptr [rax], 2
0x1400f331c  mov     rcx, [rbp+20h+SRWLock]; SRWLock
0x1400f3320  test    rcx, rcx
0x1400f3323  jz      short loc_1400F332B
0x1400f3325  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f332b  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400f3330  mov     rdi, [rax+8]
0x1400f3334  mov     eax, [rdi]
0x1400f3336  cmp     eax, 4
0x1400f3339  jbe     loc_1400F33C7
0x1400f333f  mov     rdx, [rdi+18h]
0x1400f3343  mov     rax, [rdi+10h]
0x1400f3347  mov     ecx, 200h
0x1400f334c  test    rcx, rax
0x1400f334f  jz      short loc_1400F33C7
0x1400f3351  mov     rax, rdx
0x1400f3354  and     rax, rcx
0x1400f3357  cmp     rax, rdx
0x1400f335a  jnz     short loc_1400F33C7
0x1400f335c  mov     eax, [rsi]
0x1400f335e  mov     dword ptr [rbp+20h+SRWLock], eax
0x1400f3361  mov     eax, [r14]
0x1400f3364  mov     dword ptr [rbp+20h+var_90], eax
0x1400f3367  call    cs:__imp_GetCurrentThreadId
0x1400f336d  mov     dword ptr [rbp+20h+var_98+4], eax
0x1400f3370  mov     r8, [rbx+110h]
0x1400f3377  mov     eax, [r8+48h]
0x1400f337b  mov     dword ptr [rbp+20h+var_98], eax
0x1400f337e  mov     [rbp+20h+var_70], 0
0x1400f3386  add     r8, 8
0x1400f338a  lea     rax, [rbp+20h+SRWLock]
0x1400f338e  mov     [rsp+170h+var_130], rax
0x1400f3393  lea     rax, [rbp+20h+var_90]
0x1400f3397  mov     [rsp+170h+var_138], rax
0x1400f339c  lea     rax, [rbp+20h+var_98+4]
0x1400f33a0  mov     [rsp+170h+var_140], rax
0x1400f33a5  lea     rax, [rbp+20h+var_98]
0x1400f33a9  mov     [rsp+170h+var_148], rax
0x1400f33ae  lea     rax, [rbp+20h+var_70]
0x1400f33b2  mov     [rsp+170h+var_150], rax
0x1400f33b7  lea     rdx, byte_14013C5F1
0x1400f33be  mov     rcx, rdi
0x1400f33c1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400f33c6  nop
0x1400f33c7  lea     rcx, [rbx+120h]; this
0x1400f33ce  cmp     dword ptr [rcx+18h], 0
0x1400f33d2  jz      short loc_1400F33DA
0x1400f33d4  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400f33d9  nop
0x1400f33da  lea     r11, [rsp+170h+var_10]
0x1400f33e2  mov     rbx, [r11+28h]
0x1400f33e6  mov     rsi, [r11+30h]
0x1400f33ea  mov     rsp, r11
0x1400f33ed  pop     r14
0x1400f33ef  pop     rdi
0x1400f33f0  pop     rbp
0x1400f33f1  retn
```
