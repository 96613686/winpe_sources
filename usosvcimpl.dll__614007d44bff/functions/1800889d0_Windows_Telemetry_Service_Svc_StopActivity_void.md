# Windows::Telemetry::Service::Svc::StopActivity(void)

- ea: `0x1800889d0`
- end: `0x180088cb9`
- name: `?StopActivity@Svc@Service@Telemetry@Windows@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(Windows::Telemetry::Service::Svc *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000109c`
- `0x180001f10`
- `0x1800857a8`
- `0x1800889d0`
- `0x18008c454`
- `0x18008d138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088bcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088c57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088c57`

## pseudocode

```c
void __fastcall Windows::Telemetry::Service::Svc::StopActivity(Windows::Telemetry::Service::Svc *this)
{
  _DWORD **v1; // rsi
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rdi
  _DWORD **v6; // r14
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // r9
  _DWORD *v9; // r8
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  _DWORD *v13; // r8
  __int64 v14; // r9
  char *v15; // rbx
  void *v16; // rdx
  unsigned int v17; // r8d
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // [rsp+20h] [rbp-100h]
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-80h] BYREF
  int v22; // [rsp+A8h] [rbp-78h] BYREF
  int v23; // [rsp+ACh] [rbp-74h] BYREF
  int v24; // [rsp+B0h] [rbp-70h] BYREF
  int v25; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v26; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v31; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v32; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v33; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v34; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v35; // [rsp+100h] [rbp-20h] BYREF
  __int64 v36; // [rsp+108h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+8h]

  v1 = (_DWORD **)((char *)this + 272);
  v3 = *((_QWORD *)this + 34);
  v4 = *(_DWORD *)(v3 + 72);
  if ( v4 < 0 && (v5 = v3 + 80, v4 == *(_DWORD *)(v5 + 8)) )
  {
    v6 = (_DWORD **)((char *)this + 272);
    if ( v5 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        this,
        &SRWLock);
      v7 = SRWLock;
      **v1 = 2;
      if ( v7 )
        ReleaseSRWLockExclusive(v7);
      v8 = *((_QWORD *)Windows::Telemetry::ServiceBase::Instance() + 1);
      if ( *(_DWORD *)v8 > 5u
        && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
      {
        v9 = *v1;
        v28 = *(_QWORD *)(v5 + 120);
        v29 = *(_QWORD *)(v5 + 112);
        v23 = *(_DWORD *)(v5 + 104);
        v30 = *(_QWORD *)(v5 + 96);
        v31 = *(_QWORD *)(v5 + 88);
        v24 = *(_DWORD *)(v5 + 80);
        v32 = *(_QWORD *)(v5 + 72);
        v25 = *(_DWORD *)(v5 + 32);
        v33 = *(_QWORD *)(v5 + 24);
        LODWORD(v26) = *(_DWORD *)v5;
        v34 = *(_QWORD *)(v5 + 128);
        v22 = *(_DWORD *)(v5 + 64);
        v35 = *(_QWORD *)(v5 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v5 + 8);
        v36 = 0x1000000;
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
          v8,
          (int)&word_18013009E,
          (_DWORD)v9 + 8,
          v8,
          (__int64)&v27,
          (__int64)&v36,
          (__int64)&SRWLock,
          (const wchar_t **)&v35,
          (__int64)&v22,
          (const wchar_t **)&v34,
          (__int64)&v26,
          (const OLECHAR **)&v33,
          (__int64)&v25,
          (const wchar_t **)&v32,
          (__int64)&v24,
          (const wchar_t **)&v31,
          (const OLECHAR **)&v30,
          (__int64)&v23,
          (const wchar_t **)&v29,
          (const OLECHAR **)&v28);
      }
      goto LABEL_17;
    }
  }
  else
  {
    v6 = (_DWORD **)((char *)this + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v10 = SRWLock;
  **v6 = 2;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = *((_QWORD *)Windows::Telemetry::ServiceBase::Instance() + 1);
  if ( *(_DWORD *)v11 > 5u
    && (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v11 + 24) & 0x400000000000LL) == *(_QWORD *)(v11 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v13 = *v1;
    LODWORD(SRWLock) = CurrentThreadId;
    v22 = v13[18];
    v27 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (int)word_18013005A,
      (_DWORD)v13 + 8,
      v14,
      (__int64)&v27,
      (__int64)&v22,
      (__int64)&SRWLock);
  }
LABEL_17:
  if ( *((_DWORD *)this + 78) )
  {
    v15 = (char *)this + 288;
    if ( *((_DWORD *)v15 + 6) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v16, v17, (const char *)0x8007029CLL, v20);
    v18 = *(__int64 **)v15;
    *((_DWORD *)v15 + 6) = 0;
    while ( 1 )
    {
      v19 = *v18;
      if ( !*v18 )
        break;
      if ( (char *)v19 == v15 )
      {
        *v18 = *((_QWORD *)v15 + 2);
        break;
      }
      v18 = (__int64 *)(v19 + 16);
      *(_QWORD *)v15 = v19 + 16;
    }
    *(_QWORD *)v15 = 0;
  }
}

```

## disassembly

```asm
0x1800889d0  mov     [rsp-8+arg_8], rbx
0x1800889d5  mov     [rsp-8+arg_10], rsi
0x1800889da  push    rbp
0x1800889db  push    rdi
0x1800889dc  push    r14
0x1800889de  lea     rbp, [rsp+10h]
0x1800889e3  sub     rsp, 110h
0x1800889ea  lea     rsi, [rcx+110h]
0x1800889f1  mov     rbx, rcx
0x1800889f4  mov     rdi, [rsi]
0x1800889f7  mov     eax, [rdi+48h]
0x1800889fa  test    eax, eax
0x1800889fc  jns     loc_180088BA6
0x180088a02  add     rdi, 50h ; 'P'
0x180088a06  cmp     eax, [rdi+8]
0x180088a09  jnz     loc_180088BA6
0x180088a0f  mov     r14, rsi
0x180088a12  test    rdi, rdi
0x180088a15  jz      loc_180088BA9
0x180088a1b  lea     rdx, [rbp+SRWLock]
0x180088a1f  mov     [rbp+SRWLock], 0
0x180088a27  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180088a2c  mov     rax, [rsi]
0x180088a2f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180088a33  mov     dword ptr [rax], 2
0x180088a39  test    rcx, rcx
0x180088a3c  jz      short loc_180088A44
0x180088a3e  call    cs:__imp_ReleaseSRWLockExclusive
0x180088a44  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x180088a49  mov     r9, [rax+8]
0x180088a4d  cmp     dword ptr [r9], 5
0x180088a51  jbe     loc_180088C47
0x180088a57  mov     rcx, 400000000000h
0x180088a61  test    [r9+10h], rcx
0x180088a65  jz      loc_180088C47
0x180088a6b  mov     rax, [r9+18h]
0x180088a6f  and     rax, rcx
0x180088a72  cmp     rax, [r9+18h]
0x180088a76  jnz     loc_180088C47
0x180088a7c  mov     rax, [rdi+78h]
0x180088a80  lea     rdx, word_18013009E; int
0x180088a87  mov     r8, [rsi]
0x180088a8a  mov     rcx, r9; int
0x180088a8d  mov     [rbp+var_58], rax
0x180088a91  add     r8, 8; int
0x180088a95  mov     rax, [rdi+70h]
0x180088a99  mov     [rbp+var_50], rax
0x180088a9d  mov     eax, [rdi+68h]
0x180088aa0  mov     dword ptr [rbp+var_78+4], eax
0x180088aa3  mov     rax, [rdi+60h]
0x180088aa7  mov     [rbp+var_48], rax
0x180088aab  mov     rax, [rdi+58h]
0x180088aaf  mov     [rbp+var_40], rax
0x180088ab3  mov     eax, [rdi+50h]
0x180088ab6  mov     dword ptr [rbp+var_70], eax
0x180088ab9  mov     rax, [rdi+48h]
0x180088abd  mov     [rbp+var_38], rax
0x180088ac1  mov     eax, [rdi+20h]
0x180088ac4  mov     dword ptr [rbp+var_70+4], eax
0x180088ac7  mov     rax, [rdi+18h]
0x180088acb  mov     [rbp+var_30], rax
0x180088acf  mov     eax, [rdi]
0x180088ad1  mov     dword ptr [rbp+var_68], eax
0x180088ad4  mov     rax, [rdi+80h]
0x180088adb  mov     [rbp+var_28], rax
0x180088adf  mov     eax, [rdi+40h]
0x180088ae2  mov     dword ptr [rbp+var_78], eax
0x180088ae5  mov     rax, [rdi+38h]
0x180088ae9  mov     [rbp+var_20], rax
0x180088aed  mov     eax, [rdi+8]
0x180088af0  mov     dword ptr [rbp+SRWLock], eax
0x180088af3  mov     eax, 1000000h
0x180088af8  mov     [rbp+var_18], rax
0x180088afc  mov     [rbp+var_60], rax
0x180088b00  lea     rax, [rbp+var_58]
0x180088b04  mov     [rsp+120h+var_88], rax; __int64
0x180088b0c  lea     rax, [rbp+var_50]
0x180088b10  mov     [rsp+120h+var_90], rax; __int64
0x180088b18  lea     rax, [rbp+var_78+4]
0x180088b1c  mov     [rsp+120h+var_98], rax; __int64
0x180088b24  lea     rax, [rbp+var_48]
0x180088b28  mov     [rsp+120h+var_A0], rax; __int64
0x180088b30  lea     rax, [rbp+var_40]
0x180088b34  mov     [rsp+120h+var_A8], rax; __int64
0x180088b39  lea     rax, [rbp+var_70]
0x180088b3d  mov     [rsp+120h+var_B0], rax; __int64
0x180088b42  lea     rax, [rbp+var_38]
0x180088b46  mov     [rsp+120h+var_B8], rax; __int64
0x180088b4b  lea     rax, [rbp+var_70+4]
0x180088b4f  mov     [rsp+120h+var_C0], rax; __int64
0x180088b54  lea     rax, [rbp+var_30]
0x180088b58  mov     [rsp+120h+var_C8], rax; __int64
0x180088b5d  lea     rax, [rbp+var_68]
0x180088b61  mov     [rsp+120h+var_D0], rax; __int64
0x180088b66  lea     rax, [rbp+var_28]
0x180088b6a  mov     [rsp+120h+var_D8], rax; __int64
0x180088b6f  lea     rax, [rbp+var_78]
0x180088b73  mov     [rsp+120h+var_E0], rax; __int64
0x180088b78  lea     rax, [rbp+var_20]
0x180088b7c  mov     [rsp+120h+var_E8], rax; __int64
0x180088b81  lea     rax, [rbp+SRWLock]
0x180088b85  mov     [rsp+120h+var_F0], rax; __int64
0x180088b8a  lea     rax, [rbp+var_18]
0x180088b8e  mov     [rsp+120h+var_F8], rax; __int64
0x180088b93  lea     rax, [rbp+var_60]
0x180088b97  mov     [rsp+120h+var_100], rax; __int64
0x180088b9c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180088ba1  jmp     loc_180088C47
0x180088ba6  mov     r14, rsi
0x180088ba9  lea     rdx, [rbp+SRWLock]
0x180088bad  mov     [rbp+SRWLock], 0
0x180088bb5  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180088bba  mov     rax, [r14]
0x180088bbd  mov     rcx, [rbp+SRWLock]; SRWLock
0x180088bc1  mov     dword ptr [rax], 2
0x180088bc7  test    rcx, rcx
0x180088bca  jz      short loc_180088BD2
0x180088bcc  call    cs:__imp_ReleaseSRWLockExclusive
0x180088bd2  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x180088bd7  mov     rdi, [rax+8]
0x180088bdb  cmp     dword ptr [rdi], 5
0x180088bde  jbe     short loc_180088C47
0x180088be0  mov     rcx, 400000000000h
0x180088bea  test    [rdi+10h], rcx
0x180088bee  jz      short loc_180088C47
0x180088bf0  mov     rax, [rdi+18h]
0x180088bf4  and     rax, rcx
0x180088bf7  cmp     rax, [rdi+18h]
0x180088bfb  jnz     short loc_180088C47
0x180088bfd  call    cs:__imp_GetCurrentThreadId
0x180088c03  mov     r8, [rsi]
0x180088c06  lea     rdx, word_18013005A
0x180088c0d  mov     dword ptr [rbp+SRWLock], eax
0x180088c10  mov     rcx, rdi
0x180088c13  mov     eax, [r8+48h]
0x180088c17  add     r8, 8
0x180088c1b  mov     dword ptr [rbp+var_78], eax
0x180088c1e  mov     eax, 1000000h
0x180088c23  mov     [rbp+var_60], rax
0x180088c27  lea     rax, [rbp+SRWLock]
0x180088c2b  mov     [rsp+120h+var_F0], rax
0x180088c30  lea     rax, [rbp+var_78]
0x180088c34  mov     [rsp+120h+var_F8], rax
0x180088c39  lea     rax, [rbp+var_60]
0x180088c3d  mov     [rsp+120h+var_100], rax; int
0x180088c42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180088c47  cmp     dword ptr [rbx+138h], 0
0x180088c4e  jz      short loc_180088CA1
0x180088c50  add     rbx, 120h
0x180088c57  call    cs:__imp_GetCurrentThreadId
0x180088c5d  cmp     [rbx+18h], eax
0x180088c60  jz      short loc_180088C71
0x180088c62  mov     rcx, [rbp+8]; this
0x180088c66  mov     r9d, 8007029Ch; char *
0x180088c6c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180088c71  mov     rcx, [rbx]
0x180088c74  mov     dword ptr [rbx+18h], 0
0x180088c7b  jmp     short loc_180088C89
0x180088c7d  cmp     rax, rbx
0x180088c80  jz      short loc_180088C93
0x180088c82  lea     rcx, [rax+10h]
0x180088c86  mov     [rbx], rcx
0x180088c89  mov     rax, [rcx]
0x180088c8c  test    rax, rax
0x180088c8f  jnz     short loc_180088C7D
0x180088c91  jmp     short loc_180088C9A
0x180088c93  mov     rax, [rbx+10h]
0x180088c97  mov     [rcx], rax
0x180088c9a  mov     qword ptr [rbx], 0
0x180088ca1  lea     r11, [rsp+120h+var_10]
0x180088ca9  mov     rbx, [r11+28h]
0x180088cad  mov     rsi, [r11+30h]
0x180088cb1  mov     rsp, r11
0x180088cb4  pop     r14
0x180088cb6  pop     rdi
0x180088cb7  pop     rbp
0x180088cb8  retn
```
