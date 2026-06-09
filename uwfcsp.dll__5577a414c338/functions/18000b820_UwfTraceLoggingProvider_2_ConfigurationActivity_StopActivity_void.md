# UwfTraceLoggingProvider<2>::ConfigurationActivity::StopActivity(void)

- ea: `0x18000b820`
- end: `0x18000bb00`
- name: `?StopActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001008`
- `0x180001ecc`
- `0x18000946c`
- `0x180009644`
- `0x180009f60`
- `0x18000b820`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b88f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b88f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba61`

## pseudocode

```c
void __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::StopActivity(__int64 a1)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v18; // [rsp+B0h] [rbp-70h] BYREF
  int v19; // [rsp+B8h] [rbp-68h] BYREF
  int v20; // [rsp+BCh] [rbp-64h] BYREF
  int v21; // [rsp+C0h] [rbp-60h] BYREF
  int v22; // [rsp+C4h] [rbp-5Ch] BYREF
  int *v23; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+D0h] [rbp-50h] BYREF
  int *v25; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-38h] BYREF
  int *v28; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v30; // [rsp+100h] [rbp-20h] BYREF
  __int64 v31; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v32[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v33; // [rsp+130h] [rbp+10h]
  __int64 v34; // [rsp+138h] [rbp+18h]
  int *v35; // [rsp+140h] [rbp+20h]
  __int64 v36; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v38; // [rsp+158h] [rbp+38h]

  v1 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    v5 = SRWLock;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = UwfTraceLoggingProvider<2>::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *(_QWORD *)(v6 + 24);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *(_QWORD *)(a1 + 272);
        v23 = (int *)*((_QWORD *)v4 + 15);
        v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v19 = v4[26];
        v25 = (int *)*((_QWORD *)v4 + 12);
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v20 = v4[20];
        v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v21 = v4[8];
        v28 = (int *)*((_QWORD *)v4 + 3);
        v22 = *v4;
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v16 = v4[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v31 = 0x1000000;
        v18 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&word_180022F86,
          v9 + 8,
          v7,
          (__int64)&v18,
          (__int64)&v31,
          (__int64)&SRWLock,
          &v30,
          (__int64)&v16,
          &v29,
          (__int64)&v22,
          &v28,
          (__int64)&v21,
          &v27,
          (__int64)&v20,
          &v26,
          &v25,
          (__int64)&v19,
          &v24,
          &v23);
      }
    }
  }
  else
  {
    wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v18);
    v10 = v18;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = UwfTraceLoggingProvider<2>::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *(_QWORD *)(v11 + 24);
      if ( (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *(_QWORD *)(a1 + 272);
        LODWORD(SRWLock) = CurrentThreadId;
        v38 = 4;
        v36 = 4;
        v16 = *(_DWORD *)(v15 + 72);
        p_SRWLock = &SRWLock;
        v35 = &v16;
        v33 = &v18;
        v18 = 0;
        v34 = 8;
        tlgWriteTransfer_EventWriteTransfer(v12, &unk_180022F30, v15 + 8, 0, 5, v32);
      }
    }
  }
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18000b820  mov     [rsp-8+arg_8], rbx
0x18000b825  mov     [rsp-8+arg_10], rdi
0x18000b82a  push    rbp
0x18000b82b  lea     rbp, [rsp-50h]
0x18000b830  sub     rsp, 170h
0x18000b837  mov     rax, cs:__security_cookie
0x18000b83e  xor     rax, rsp
0x18000b841  mov     [rbp+50h+var_10], rax
0x18000b845  mov     rdi, [rcx+110h]
0x18000b84c  mov     rbx, rcx
0x18000b84f  mov     eax, [rdi+48h]
0x18000b852  test    eax, eax
0x18000b854  jns     loc_18000BA03
0x18000b85a  add     rdi, 50h ; 'P'
0x18000b85e  cmp     eax, [rdi+8]
0x18000b861  jnz     loc_18000BA03
0x18000b867  test    rdi, rdi
0x18000b86a  jz      loc_18000BA03
0x18000b870  lea     rdx, [rbp+50h+SRWLock]
0x18000b874  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b879  mov     rax, [rbx+110h]
0x18000b880  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18000b884  mov     dword ptr [rax], 2
0x18000b88a  test    rcx, rcx
0x18000b88d  jz      short loc_18000B895
0x18000b88f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b895  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000b89a  mov     r9, rax
0x18000b89d  mov     ecx, [rax]
0x18000b89f  cmp     ecx, 5
0x18000b8a2  jbe     loc_18000BAD7
0x18000b8a8  mov     rax, [rax+18h]
0x18000b8ac  mov     rdx, 400000000000h
0x18000b8b6  mov     rcx, [r9+10h]
0x18000b8ba  test    rdx, rcx
0x18000b8bd  jz      loc_18000BAD7
0x18000b8c3  mov     rcx, rax
0x18000b8c6  and     rcx, rdx
0x18000b8c9  cmp     rcx, rax
0x18000b8cc  jnz     loc_18000BAD7
0x18000b8d2  mov     rax, [rdi+78h]
0x18000b8d6  lea     rdx, word_180022F86
0x18000b8dd  mov     r8, [rbx+110h]
0x18000b8e4  mov     rcx, r9
0x18000b8e7  mov     [rbp+50h+var_A8], rax
0x18000b8eb  add     r8, 8
0x18000b8ef  mov     rax, [rdi+70h]
0x18000b8f3  mov     [rbp+50h+var_A0], rax
0x18000b8f7  mov     eax, [rdi+68h]
0x18000b8fa  mov     [rbp+50h+var_B8], eax
0x18000b8fd  mov     rax, [rdi+60h]
0x18000b901  mov     [rbp+50h+var_98], rax
0x18000b905  mov     rax, [rdi+58h]
0x18000b909  mov     [rbp+50h+var_90], rax
0x18000b90d  mov     eax, [rdi+50h]
0x18000b910  mov     [rbp+50h+var_B4], eax
0x18000b913  mov     rax, [rdi+48h]
0x18000b917  mov     [rbp+50h+var_88], rax
0x18000b91b  mov     eax, [rdi+20h]
0x18000b91e  mov     [rbp+50h+var_B0], eax
0x18000b921  mov     rax, [rdi+18h]
0x18000b925  mov     [rbp+50h+var_80], rax
0x18000b929  mov     eax, [rdi]
0x18000b92b  mov     [rbp+50h+var_AC], eax
0x18000b92e  mov     rax, [rdi+80h]
0x18000b935  mov     [rbp+50h+var_78], rax
0x18000b939  mov     eax, [rdi+40h]
0x18000b93c  mov     [rbp+50h+var_D0], eax
0x18000b93f  mov     rax, [rdi+38h]
0x18000b943  mov     [rbp+50h+var_70], rax
0x18000b947  mov     eax, [rdi+8]
0x18000b94a  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000b94d  lea     rax, [rbp+50h+var_A8]
0x18000b951  mov     [rsp+170h+var_D8], rax
0x18000b959  lea     rax, [rbp+50h+var_A0]
0x18000b95d  mov     [rsp+170h+var_E0], rax
0x18000b965  lea     rax, [rbp+50h+var_B8]
0x18000b969  mov     [rsp+170h+var_E8], rax
0x18000b971  lea     rax, [rbp+50h+var_98]
0x18000b975  mov     [rsp+170h+var_F0], rax
0x18000b97d  lea     rax, [rbp+50h+var_90]
0x18000b981  mov     [rsp+170h+var_F8], rax
0x18000b986  lea     rax, [rbp+50h+var_B4]
0x18000b98a  mov     [rsp+170h+var_100], rax
0x18000b98f  lea     rax, [rbp+50h+var_88]
0x18000b993  mov     [rsp+170h+var_108], rax
0x18000b998  lea     rax, [rbp+50h+var_B0]
0x18000b99c  mov     [rsp+170h+var_110], rax
0x18000b9a1  lea     rax, [rbp+50h+var_80]
0x18000b9a5  mov     [rsp+170h+var_118], rax
0x18000b9aa  lea     rax, [rbp+50h+var_AC]
0x18000b9ae  mov     [rsp+170h+var_120], rax
0x18000b9b3  lea     rax, [rbp+50h+var_78]
0x18000b9b7  mov     [rsp+170h+var_128], rax
0x18000b9bc  lea     rax, [rbp+50h+var_D0]
0x18000b9c0  mov     [rsp+170h+var_130], rax
0x18000b9c5  lea     rax, [rbp+50h+var_70]
0x18000b9c9  mov     [rsp+170h+var_138], rax
0x18000b9ce  lea     rax, [rbp+50h+SRWLock]
0x18000b9d2  mov     [rsp+170h+var_140], rax
0x18000b9d7  lea     rax, [rbp+50h+var_68]
0x18000b9db  mov     [rsp+170h+var_148], rax
0x18000b9e0  lea     rax, [rbp+50h+var_C0]
0x18000b9e4  mov     [rsp+170h+var_150], rax
0x18000b9e9  mov     [rbp+50h+var_68], 1000000h
0x18000b9f1  mov     [rbp+50h+var_C0], 0
0x18000b9f9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000b9fe  jmp     loc_18000BAD7
0x18000ba03  lea     rdx, [rbp+50h+var_C0]
0x18000ba07  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ba0c  mov     rax, [rbx+110h]
0x18000ba13  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18000ba17  mov     dword ptr [rax], 2
0x18000ba1d  test    rcx, rcx
0x18000ba20  jz      short loc_18000BA28
0x18000ba22  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba28  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000ba2d  mov     rdi, rax
0x18000ba30  mov     ecx, [rax]
0x18000ba32  cmp     ecx, 5
0x18000ba35  jbe     loc_18000BAD7
0x18000ba3b  mov     rax, [rax+18h]
0x18000ba3f  mov     rdx, 400000000000h
0x18000ba49  mov     rcx, [rdi+10h]
0x18000ba4d  test    rdx, rcx
0x18000ba50  jz      loc_18000BAD7
0x18000ba56  mov     rcx, rax
0x18000ba59  and     rcx, rdx
0x18000ba5c  cmp     rcx, rax
0x18000ba5f  jnz     short loc_18000BAD7
0x18000ba61  call    cs:__imp_GetCurrentThreadId
0x18000ba67  mov     r8, [rbx+110h]
0x18000ba6e  lea     rdx, unk_180022F30
0x18000ba75  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000ba78  xor     r9d, r9d
0x18000ba7b  mov     rcx, rdi
0x18000ba7e  mov     [rbp+50h+var_18], 4
0x18000ba86  mov     [rbp+50h+var_28], 4
0x18000ba8e  mov     eax, [r8+48h]
0x18000ba92  add     r8, 8
0x18000ba96  mov     [rbp+50h+var_D0], eax
0x18000ba99  lea     rax, [rbp+50h+SRWLock]
0x18000ba9d  mov     [rbp+50h+var_20], rax
0x18000baa1  lea     rax, [rbp+50h+var_D0]
0x18000baa5  mov     [rbp+50h+var_30], rax
0x18000baa9  lea     rax, [rbp+50h+var_C0]
0x18000baad  mov     [rbp+50h+var_40], rax
0x18000bab1  lea     rax, [rbp+50h+var_60]
0x18000bab5  mov     [rsp+170h+var_148], rax
0x18000baba  mov     dword ptr [rsp+170h+var_150], 5
0x18000bac2  mov     [rbp+50h+var_C0], 0
0x18000baca  mov     [rbp+50h+var_38], 8
0x18000bad2  call    _tlgWriteTransfer_EventWriteTransfer
0x18000bad7  mov     rcx, rbx
0x18000bada  call    ?IgnoreCurrentThread@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000badf  mov     rcx, [rbp+50h+var_10]
0x18000bae3  xor     rcx, rsp; StackCookie
0x18000bae6  call    __security_check_cookie
0x18000baeb  lea     r11, [rsp+170h+var_s0]
0x18000baf3  mov     rbx, [r11+18h]
0x18000baf7  mov     rdi, [r11+20h]
0x18000bafb  mov     rsp, r11
0x18000bafe  pop     rbp
0x18000baff  retn
```
