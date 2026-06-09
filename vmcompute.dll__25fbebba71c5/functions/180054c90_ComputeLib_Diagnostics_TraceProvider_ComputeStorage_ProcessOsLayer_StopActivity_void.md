# ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StopActivity(void)

- ea: `0x180054c90`
- end: `0x180054f79`
- name: `?StopActivity@ComputeStorage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x180054c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054cf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054ec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054cf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054ec6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054ef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054ef9`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer *this)
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
          (int)&word_1800A1C32,
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
          (unsigned int)&dword_1800A1A44,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer *)((char *)this + 288));
}

```

## disassembly

```asm
0x180054c90  mov     [rsp-8+arg_8], rbx
0x180054c95  mov     [rsp-8+arg_10], rdi
0x180054c9a  push    rbp
0x180054c9b  mov     rbp, rsp
0x180054c9e  sub     rsp, 140h
0x180054ca5  mov     rbx, rcx
0x180054ca8  mov     rdi, [rcx+110h]
0x180054caf  mov     eax, [rdi+48h]
0x180054cb2  test    eax, eax
0x180054cb4  jns     loc_180054E9F
0x180054cba  add     rdi, 50h ; 'P'
0x180054cbe  cmp     eax, [rdi+8]
0x180054cc1  jnz     loc_180054E9F
0x180054cc7  test    rdi, rdi
0x180054cca  jz      loc_180054E9F
0x180054cd0  mov     [rbp+SRWLock], 0
0x180054cd8  lea     rdx, [rbp+SRWLock]
0x180054cdc  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180054ce1  mov     rax, [rbx+110h]
0x180054ce8  mov     dword ptr [rax], 2
0x180054cee  mov     rcx, [rbp+SRWLock]; SRWLock
0x180054cf2  test    rcx, rcx
0x180054cf5  jz      short loc_180054D03
0x180054cf7  call    cs:__imp_ReleaseSRWLockExclusive
0x180054cfe  nop     dword ptr [rax+rax+00h]
0x180054d03  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x180054d08  mov     r9, rax
0x180054d0b  mov     ecx, [rax]
0x180054d0d  cmp     ecx, 4
0x180054d10  jbe     loc_180054F50
0x180054d16  mov     rax, [rax+18h]
0x180054d1a  mov     rcx, [r9+10h]
0x180054d1e  test    cl, 40h
0x180054d21  jz      loc_180054F50
0x180054d27  mov     rcx, rax
0x180054d2a  and     ecx, 40h
0x180054d2d  cmp     rcx, rax
0x180054d30  jnz     loc_180054F50
0x180054d36  mov     rax, [rdi+30h]
0x180054d3a  mov     [rbp+var_50], rax
0x180054d3e  mov     eax, [rdi+44h]
0x180054d41  mov     dword ptr [rbp+var_78+4], eax
0x180054d44  mov     eax, [rdi+10h]
0x180054d47  mov     dword ptr [rbp+var_70], eax
0x180054d4a  mov     rax, [rdi+78h]
0x180054d4e  mov     [rbp+var_48], rax
0x180054d52  mov     rax, [rdi+70h]
0x180054d56  mov     [rbp+var_40], rax
0x180054d5a  mov     eax, [rdi+68h]
0x180054d5d  mov     dword ptr [rbp+var_70+4], eax
0x180054d60  mov     rax, [rdi+60h]
0x180054d64  mov     [rbp+var_38], rax
0x180054d68  mov     rax, [rdi+58h]
0x180054d6c  mov     [rbp+var_30], rax
0x180054d70  mov     eax, [rdi+50h]
0x180054d73  mov     dword ptr [rbp+var_68], eax
0x180054d76  mov     rax, [rdi+48h]
0x180054d7a  mov     [rbp+var_28], rax
0x180054d7e  mov     eax, [rdi+20h]
0x180054d81  mov     dword ptr [rbp+var_68+4], eax
0x180054d84  mov     rax, [rdi+18h]
0x180054d88  mov     [rbp+var_20], rax
0x180054d8c  mov     eax, [rdi]
0x180054d8e  mov     [rbp+var_60], eax
0x180054d91  mov     rax, [rdi+80h]
0x180054d98  mov     [rbp+var_18], rax
0x180054d9c  mov     eax, [rdi+40h]
0x180054d9f  mov     dword ptr [rbp+var_78], eax
0x180054da2  mov     rax, [rdi+38h]
0x180054da6  mov     [rbp+var_10], rax
0x180054daa  mov     eax, [rdi+8]
0x180054dad  mov     dword ptr [rbp+SRWLock], eax
0x180054db0  mov     [rbp+var_8], 1000000h
0x180054db8  mov     [rbp+var_58], 0
0x180054dc0  mov     r8, [rbx+110h]
0x180054dc7  add     r8, 8; int
0x180054dcb  lea     rax, [rbp+var_50]
0x180054dcf  mov     [rsp+140h+var_90], rax; __int64
0x180054dd7  lea     rax, [rbp+var_78+4]
0x180054ddb  mov     [rsp+140h+var_98], rax; __int64
0x180054de3  lea     rax, [rbp+var_70]
0x180054de7  mov     [rsp+140h+var_A0], rax; __int64
0x180054def  lea     rax, [rbp+var_48]
0x180054df3  mov     [rsp+140h+var_A8], rax; __int64
0x180054dfb  lea     rax, [rbp+var_40]
0x180054dff  mov     [rsp+140h+var_B0], rax; __int64
0x180054e07  lea     rax, [rbp+var_70+4]
0x180054e0b  mov     [rsp+140h+var_B8], rax; __int64
0x180054e13  lea     rax, [rbp+var_38]
0x180054e17  mov     [rsp+140h+var_C0], rax; __int64
0x180054e1f  lea     rax, [rbp+var_30]
0x180054e23  mov     [rsp+140h+var_C8], rax; __int64
0x180054e28  lea     rax, [rbp+var_68]
0x180054e2c  mov     [rsp+140h+var_D0], rax; __int64
0x180054e31  lea     rax, [rbp+var_28]
0x180054e35  mov     [rsp+140h+var_D8], rax; __int64
0x180054e3a  lea     rax, [rbp+var_68+4]
0x180054e3e  mov     [rsp+140h+var_E0], rax; __int64
0x180054e43  lea     rax, [rbp+var_20]
0x180054e47  mov     [rsp+140h+var_E8], rax; __int64
0x180054e4c  lea     rax, [rbp+var_60]
0x180054e50  mov     [rsp+140h+var_F0], rax; __int64
0x180054e55  lea     rax, [rbp+var_18]
0x180054e59  mov     [rsp+140h+var_F8], rax; __int64
0x180054e5e  lea     rax, [rbp+var_78]
0x180054e62  mov     [rsp+140h+var_100], rax; __int64
0x180054e67  lea     rax, [rbp+var_10]
0x180054e6b  mov     [rsp+140h+var_108], rax; __int64
0x180054e70  lea     rax, [rbp+SRWLock]
0x180054e74  mov     [rsp+140h+var_110], rax; __int64
0x180054e79  lea     rax, [rbp+var_8]
0x180054e7d  mov     [rsp+140h+var_118], rax; __int64
0x180054e82  lea     rax, [rbp+var_58]
0x180054e86  mov     [rsp+140h+var_120], rax; __int64
0x180054e8b  lea     rdx, word_1800A1C32; int
0x180054e92  mov     rcx, r9; int
0x180054e95  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180054e9a  jmp     loc_180054F50
0x180054e9f  mov     [rbp+SRWLock], 0
0x180054ea7  lea     rdx, [rbp+SRWLock]
0x180054eab  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180054eb0  mov     rax, [rbx+110h]
0x180054eb7  mov     dword ptr [rax], 2
0x180054ebd  mov     rcx, [rbp+SRWLock]; SRWLock
0x180054ec1  test    rcx, rcx
0x180054ec4  jz      short loc_180054ED2
0x180054ec6  call    cs:__imp_ReleaseSRWLockExclusive
0x180054ecd  nop     dword ptr [rax+rax+00h]
0x180054ed2  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x180054ed7  mov     rdi, rax
0x180054eda  mov     ecx, [rax]
0x180054edc  cmp     ecx, 4
0x180054edf  jbe     short loc_180054F50
0x180054ee1  mov     rax, [rax+18h]
0x180054ee5  mov     rcx, [rdi+10h]
0x180054ee9  test    cl, 40h
0x180054eec  jz      short loc_180054F50
0x180054eee  mov     rcx, rax
0x180054ef1  and     ecx, 40h
0x180054ef4  cmp     rcx, rax
0x180054ef7  jnz     short loc_180054F50
0x180054ef9  call    cs:__imp_GetCurrentThreadId
0x180054f00  nop     dword ptr [rax+rax+00h]
0x180054f05  mov     dword ptr [rbp+SRWLock], eax
0x180054f08  mov     r8, [rbx+110h]
0x180054f0f  mov     eax, [r8+48h]
0x180054f13  mov     dword ptr [rbp+var_78], eax
0x180054f16  mov     [rbp+var_58], 0
0x180054f1e  add     r8, 8
0x180054f22  lea     rax, [rbp+SRWLock]
0x180054f26  mov     [rsp+140h+var_110], rax
0x180054f2b  lea     rax, [rbp+var_78]
0x180054f2f  mov     [rsp+140h+var_118], rax
0x180054f34  lea     rax, [rbp+var_58]
0x180054f38  mov     [rsp+140h+var_120], rax
0x180054f3d  xor     r9d, r9d
0x180054f40  lea     rdx, dword_1800A1A44
0x180054f47  mov     rcx, rdi
0x180054f4a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180054f4f  nop
0x180054f50  lea     rcx, [rbx+120h]; this
0x180054f57  cmp     dword ptr [rcx+18h], 0
0x180054f5b  jz      short loc_180054F63
0x180054f5d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180054f62  nop
0x180054f63  lea     r11, [rsp+140h+var_s0]
0x180054f6b  mov     rbx, [r11+18h]
0x180054f6f  mov     rdi, [r11+20h]
0x180054f73  mov     rsp, r11
0x180054f76  pop     rbp
0x180054f77  retn
```
