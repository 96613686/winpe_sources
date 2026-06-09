# WhesvcTelemetryProvider::WhesvcStartActivity::StopActivity(void)

- ea: `0x18000b750`
- end: `0x18000ba30`
- name: `?StopActivity@WhesvcStartActivity@WhesvcTelemetryProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(WhesvcTelemetryProvider::WhesvcStartActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001008`
- `0x1800018dc`
- `0x1800032e0`
- `0x18000a920`
- `0x18000a9ac`
- `0x18000ae4c`
- `0x18000b750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b991`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b952`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b952`

## pseudocode

```c
void __fastcall WhesvcTelemetryProvider::WhesvcStartActivity::StopActivity(
        WhesvcTelemetryProvider::WhesvcStartActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
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
  const wchar_t *v23; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+D0h] [rbp-50h] BYREF
  const wchar_t *v25; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-38h] BYREF
  const wchar_t *v28; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v30; // [rsp+100h] [rbp-20h] BYREF
  __int64 v31; // [rsp+108h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v33; // [rsp+130h] [rbp+10h]
  __int64 v34; // [rsp+138h] [rbp+18h]
  int *v35; // [rsp+140h] [rbp+20h]
  __int64 v36; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v38; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = WhesvcTelemetryProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v23 = (const wchar_t *)*((_QWORD *)v4 + 15);
        v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v19 = v4[26];
        v25 = (const wchar_t *)*((_QWORD *)v4 + 12);
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v20 = v4[20];
        v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v21 = v4[8];
        v28 = (const wchar_t *)*((_QWORD *)v4 + 3);
        v22 = *v4;
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v16 = v4[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v31 = 0x1000000;
        v18 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)word_18002D492,
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
    wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v18);
    v10 = v18;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = WhesvcTelemetryProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v38 = 4;
        v36 = 4;
        v16 = *(_DWORD *)(v15 + 72);
        p_SRWLock = &SRWLock;
        v35 = &v16;
        v33 = &v18;
        v18 = 0;
        v34 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v12,
          (unsigned __int8 *)byte_18002D5BD,
          (const GUID *)(v15 + 8),
          0,
          5u,
          &v32);
      }
    }
  }
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000b750  mov     [rsp-8+arg_8], rbx
0x18000b755  mov     [rsp-8+arg_10], rdi
0x18000b75a  push    rbp
0x18000b75b  lea     rbp, [rsp-50h]
0x18000b760  sub     rsp, 170h
0x18000b767  mov     rax, cs:__security_cookie
0x18000b76e  xor     rax, rsp
0x18000b771  mov     [rbp+50h+var_10], rax
0x18000b775  mov     rdi, [rcx+110h]
0x18000b77c  mov     rbx, rcx
0x18000b77f  mov     eax, [rdi+48h]
0x18000b782  test    eax, eax
0x18000b784  jns     loc_18000B933
0x18000b78a  add     rdi, 50h ; 'P'
0x18000b78e  cmp     eax, [rdi+8]
0x18000b791  jnz     loc_18000B933
0x18000b797  test    rdi, rdi
0x18000b79a  jz      loc_18000B933
0x18000b7a0  lea     rdx, [rbp+50h+SRWLock]
0x18000b7a4  call    ?LockExclusive@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b7a9  mov     rax, [rbx+110h]
0x18000b7b0  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18000b7b4  mov     dword ptr [rax], 2
0x18000b7ba  test    rcx, rcx
0x18000b7bd  jz      short loc_18000B7C5
0x18000b7bf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b7c5  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x18000b7ca  mov     r9, rax
0x18000b7cd  mov     ecx, [rax]
0x18000b7cf  cmp     ecx, 5
0x18000b7d2  jbe     loc_18000BA07
0x18000b7d8  mov     rax, [rax+18h]
0x18000b7dc  mov     rdx, 200000000000h
0x18000b7e6  mov     rcx, [r9+10h]
0x18000b7ea  test    rdx, rcx
0x18000b7ed  jz      loc_18000BA07
0x18000b7f3  mov     rcx, rax
0x18000b7f6  and     rcx, rdx
0x18000b7f9  cmp     rcx, rax
0x18000b7fc  jnz     loc_18000BA07
0x18000b802  mov     rax, [rdi+78h]
0x18000b806  lea     rdx, word_18002D492
0x18000b80d  mov     r8, [rbx+110h]
0x18000b814  mov     rcx, r9
0x18000b817  mov     [rbp+50h+var_A8], rax
0x18000b81b  add     r8, 8
0x18000b81f  mov     rax, [rdi+70h]
0x18000b823  mov     [rbp+50h+var_A0], rax
0x18000b827  mov     eax, [rdi+68h]
0x18000b82a  mov     [rbp+50h+var_B8], eax
0x18000b82d  mov     rax, [rdi+60h]
0x18000b831  mov     [rbp+50h+var_98], rax
0x18000b835  mov     rax, [rdi+58h]
0x18000b839  mov     [rbp+50h+var_90], rax
0x18000b83d  mov     eax, [rdi+50h]
0x18000b840  mov     [rbp+50h+var_B4], eax
0x18000b843  mov     rax, [rdi+48h]
0x18000b847  mov     [rbp+50h+var_88], rax
0x18000b84b  mov     eax, [rdi+20h]
0x18000b84e  mov     [rbp+50h+var_B0], eax
0x18000b851  mov     rax, [rdi+18h]
0x18000b855  mov     [rbp+50h+var_80], rax
0x18000b859  mov     eax, [rdi]
0x18000b85b  mov     [rbp+50h+var_AC], eax
0x18000b85e  mov     rax, [rdi+80h]
0x18000b865  mov     [rbp+50h+var_78], rax
0x18000b869  mov     eax, [rdi+40h]
0x18000b86c  mov     [rbp+50h+var_D0], eax
0x18000b86f  mov     rax, [rdi+38h]
0x18000b873  mov     [rbp+50h+var_70], rax
0x18000b877  mov     eax, [rdi+8]
0x18000b87a  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000b87d  lea     rax, [rbp+50h+var_A8]
0x18000b881  mov     [rsp+170h+var_D8], rax
0x18000b889  lea     rax, [rbp+50h+var_A0]
0x18000b88d  mov     [rsp+170h+var_E0], rax
0x18000b895  lea     rax, [rbp+50h+var_B8]
0x18000b899  mov     [rsp+170h+var_E8], rax
0x18000b8a1  lea     rax, [rbp+50h+var_98]
0x18000b8a5  mov     [rsp+170h+var_F0], rax
0x18000b8ad  lea     rax, [rbp+50h+var_90]
0x18000b8b1  mov     [rsp+170h+var_F8], rax
0x18000b8b6  lea     rax, [rbp+50h+var_B4]
0x18000b8ba  mov     [rsp+170h+var_100], rax
0x18000b8bf  lea     rax, [rbp+50h+var_88]
0x18000b8c3  mov     [rsp+170h+var_108], rax
0x18000b8c8  lea     rax, [rbp+50h+var_B0]
0x18000b8cc  mov     [rsp+170h+var_110], rax
0x18000b8d1  lea     rax, [rbp+50h+var_80]
0x18000b8d5  mov     [rsp+170h+var_118], rax
0x18000b8da  lea     rax, [rbp+50h+var_AC]
0x18000b8de  mov     [rsp+170h+var_120], rax
0x18000b8e3  lea     rax, [rbp+50h+var_78]
0x18000b8e7  mov     [rsp+170h+var_128], rax
0x18000b8ec  lea     rax, [rbp+50h+var_D0]
0x18000b8f0  mov     [rsp+170h+var_130], rax
0x18000b8f5  lea     rax, [rbp+50h+var_70]
0x18000b8f9  mov     [rsp+170h+var_138], rax
0x18000b8fe  lea     rax, [rbp+50h+SRWLock]
0x18000b902  mov     [rsp+170h+var_140], rax
0x18000b907  lea     rax, [rbp+50h+var_68]
0x18000b90b  mov     [rsp+170h+var_148], rax
0x18000b910  lea     rax, [rbp+50h+var_C0]
0x18000b914  mov     [rsp+170h+var_150], rax
0x18000b919  mov     [rbp+50h+var_68], 1000000h
0x18000b921  mov     [rbp+50h+var_C0], 0
0x18000b929  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000b92e  jmp     loc_18000BA07
0x18000b933  lea     rdx, [rbp+50h+var_C0]
0x18000b937  call    ?LockExclusive@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b93c  mov     rax, [rbx+110h]
0x18000b943  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18000b947  mov     dword ptr [rax], 2
0x18000b94d  test    rcx, rcx
0x18000b950  jz      short loc_18000B958
0x18000b952  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b958  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x18000b95d  mov     rdi, rax
0x18000b960  mov     ecx, [rax]
0x18000b962  cmp     ecx, 5
0x18000b965  jbe     loc_18000BA07
0x18000b96b  mov     rax, [rax+18h]
0x18000b96f  mov     rdx, 200000000000h
0x18000b979  mov     rcx, [rdi+10h]
0x18000b97d  test    rdx, rcx
0x18000b980  jz      loc_18000BA07
0x18000b986  mov     rcx, rax
0x18000b989  and     rcx, rdx
0x18000b98c  cmp     rcx, rax
0x18000b98f  jnz     short loc_18000BA07
0x18000b991  call    cs:__imp_GetCurrentThreadId
0x18000b997  mov     r8, [rbx+110h]
0x18000b99e  lea     rdx, byte_18002D5BD
0x18000b9a5  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000b9a8  xor     r9d, r9d
0x18000b9ab  mov     rcx, rdi
0x18000b9ae  mov     [rbp+50h+var_18], 4
0x18000b9b6  mov     [rbp+50h+var_28], 4
0x18000b9be  mov     eax, [r8+48h]
0x18000b9c2  add     r8, 8
0x18000b9c6  mov     [rbp+50h+var_D0], eax
0x18000b9c9  lea     rax, [rbp+50h+SRWLock]
0x18000b9cd  mov     [rbp+50h+var_20], rax
0x18000b9d1  lea     rax, [rbp+50h+var_D0]
0x18000b9d5  mov     [rbp+50h+var_30], rax
0x18000b9d9  lea     rax, [rbp+50h+var_C0]
0x18000b9dd  mov     [rbp+50h+var_40], rax
0x18000b9e1  lea     rax, [rbp+50h+var_60]
0x18000b9e5  mov     [rsp+170h+var_148], rax
0x18000b9ea  mov     dword ptr [rsp+170h+var_150], 5
0x18000b9f2  mov     [rbp+50h+var_C0], 0
0x18000b9fa  mov     [rbp+50h+var_38], 8
0x18000ba02  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ba07  mov     rcx, rbx
0x18000ba0a  call    ?IgnoreCurrentThread@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000ba0f  mov     rcx, [rbp+50h+var_10]
0x18000ba13  xor     rcx, rsp; StackCookie
0x18000ba16  call    __security_check_cookie
0x18000ba1b  lea     r11, [rsp+170h+var_s0]
0x18000ba23  mov     rbx, [r11+18h]
0x18000ba27  mov     rdi, [r11+20h]
0x18000ba2b  mov     rsp, r11
0x18000ba2e  pop     rbp
0x18000ba2f  retn
```
