# DataPackageTracing::DelayedRenderActivity::StopActivity(void)

- ea: `0x18004e6b0`
- end: `0x18004e9f0`
- name: `?StopActivity@DelayedRenderActivity@DataPackageTracing@@MEAAXXZ`
- size: `832`
- prototype: `void __fastcall(DataPackageTracing::DelayedRenderActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800013a4`
- `0x180001d2c`
- `0x180002ad0`
- `0x18003a774`
- `0x18003daf8`
- `0x18004e6b0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e71f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e8b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e71f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e8b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e8f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e978`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e8f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e978`

## string_xrefs

- `0x18004e993`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DataPackageTracing::DelayedRenderActivity::StopActivity(
        DataPackageTracing::DelayedRenderActivity *this)
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
  char *v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+B0h] [rbp-70h] BYREF
  int v18; // [rsp+B8h] [rbp-68h] BYREF
  int v19; // [rsp+BCh] [rbp-64h] BYREF
  int v20; // [rsp+C0h] [rbp-60h] BYREF
  int v21; // [rsp+C4h] [rbp-5Ch] BYREF
  __int64 v22; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v29; // [rsp+100h] [rbp-20h] BYREF
  __int64 v30; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v31[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v32; // [rsp+130h] [rbp+10h]
  __int64 v33; // [rsp+138h] [rbp+18h]
  int *v34; // [rsp+140h] [rbp+20h]
  __int64 v35; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v37; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = DataPackageTracing::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v18 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v19 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v20 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v21 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v15 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v17 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v6,
          (unsigned int)&unk_18009AED0,
          *((_QWORD *)this + 34) + 8,
          (_DWORD)v6,
          (__int64)&v17,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v15,
          (__int64)&v28,
          (__int64)&v21,
          (__int64)&v27,
          (__int64)&v20,
          (__int64)&v26,
          (__int64)&v19,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v18,
          (__int64)&v23,
          (__int64)&v22);
      }
    }
  }
  else
  {
    wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v17);
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v8 = DataPackageTracing::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v15 = *(_DWORD *)(v11 + 72);
        v17 = 0;
        p_SRWLock = &SRWLock;
        v37 = 4;
        v34 = &v15;
        v35 = 4;
        v32 = &v17;
        v33 = 8;
        tlgWriteTransfer_EventWriteTransfer(v9, byte_18009A749, v11 + 8, 0, 5, v31);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( *((_DWORD *)v12 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v12 + 6) = 0;
    v13 = *(__int64 **)v12;
    while ( 1 )
    {
      v14 = *v13;
      if ( !*v13 )
        break;
      if ( (char *)v14 == v12 )
      {
        *v13 = *((_QWORD *)v12 + 2);
        break;
      }
      v13 = (__int64 *)(v14 + 16);
      *(_QWORD *)v12 = v14 + 16;
    }
    *(_QWORD *)v12 = 0;
  }
}

```

## disassembly

```asm
0x18004e6b0  mov     [rsp-8+arg_8], rbx
0x18004e6b5  mov     [rsp-8+arg_10], rdi
0x18004e6ba  push    rbp
0x18004e6bb  lea     rbp, [rsp-50h]
0x18004e6c0  sub     rsp, 170h
0x18004e6c7  mov     rax, cs:__security_cookie
0x18004e6ce  xor     rax, rsp
0x18004e6d1  mov     [rbp+50h+var_10], rax
0x18004e6d5  mov     rbx, rcx
0x18004e6d8  mov     rdi, [rcx+110h]
0x18004e6df  mov     eax, [rdi+48h]
0x18004e6e2  test    eax, eax
0x18004e6e4  jns     loc_18004E893
0x18004e6ea  add     rdi, 50h ; 'P'
0x18004e6ee  cmp     eax, [rdi+8]
0x18004e6f1  jnz     loc_18004E893
0x18004e6f7  test    rdi, rdi
0x18004e6fa  jz      loc_18004E893
0x18004e700  lea     rdx, [rbp+50h+SRWLock]
0x18004e704  call    ?LockExclusive@?$ActivityBase@VDataPackageTracing@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004e709  mov     rax, [rbx+110h]
0x18004e710  mov     dword ptr [rax], 2
0x18004e716  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18004e71a  test    rcx, rcx
0x18004e71d  jz      short loc_18004E725
0x18004e71f  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e725  call    ?Provider@DataPackageTracing@@SAPEBU_tlgProvider_t@@XZ; DataPackageTracing::Provider(void)
0x18004e72a  mov     r9, rax
0x18004e72d  mov     ecx, [rax]
0x18004e72f  cmp     ecx, 5
0x18004e732  jbe     loc_18004E968
0x18004e738  mov     rax, [rax+18h]
0x18004e73c  mov     rcx, [r9+10h]
0x18004e740  mov     rdx, 400000000000h
0x18004e74a  test    rdx, rcx
0x18004e74d  jz      loc_18004E968
0x18004e753  mov     rcx, rax
0x18004e756  and     rcx, rdx
0x18004e759  cmp     rcx, rax
0x18004e75c  jnz     loc_18004E968
0x18004e762  mov     rax, [rdi+78h]
0x18004e766  mov     [rbp+50h+var_A8], rax
0x18004e76a  mov     rax, [rdi+70h]
0x18004e76e  mov     [rbp+50h+var_A0], rax
0x18004e772  mov     eax, [rdi+68h]
0x18004e775  mov     [rbp+50h+var_B8], eax
0x18004e778  mov     rax, [rdi+60h]
0x18004e77c  mov     [rbp+50h+var_98], rax
0x18004e780  mov     rax, [rdi+58h]
0x18004e784  mov     [rbp+50h+var_90], rax
0x18004e788  mov     eax, [rdi+50h]
0x18004e78b  mov     [rbp+50h+var_B4], eax
0x18004e78e  mov     rax, [rdi+48h]
0x18004e792  mov     [rbp+50h+var_88], rax
0x18004e796  mov     eax, [rdi+20h]
0x18004e799  mov     [rbp+50h+var_B0], eax
0x18004e79c  mov     rax, [rdi+18h]
0x18004e7a0  mov     [rbp+50h+var_80], rax
0x18004e7a4  mov     eax, [rdi]
0x18004e7a6  mov     [rbp+50h+var_AC], eax
0x18004e7a9  mov     rax, [rdi+80h]
0x18004e7b0  mov     [rbp+50h+var_78], rax
0x18004e7b4  mov     eax, [rdi+40h]
0x18004e7b7  mov     [rbp+50h+var_D0], eax
0x18004e7ba  mov     rax, [rdi+38h]
0x18004e7be  mov     [rbp+50h+var_70], rax
0x18004e7c2  mov     eax, [rdi+8]
0x18004e7c5  mov     dword ptr [rbp+50h+SRWLock], eax
0x18004e7c8  mov     [rbp+50h+var_68], 1000000h
0x18004e7d0  mov     [rbp+50h+var_C0], 0
0x18004e7d8  mov     r8, [rbx+110h]
0x18004e7df  add     r8, 8
0x18004e7e3  lea     rax, [rbp+50h+var_A8]
0x18004e7e7  mov     [rsp+170h+var_D8], rax
0x18004e7ef  lea     rax, [rbp+50h+var_A0]
0x18004e7f3  mov     [rsp+170h+var_E0], rax
0x18004e7fb  lea     rax, [rbp+50h+var_B8]
0x18004e7ff  mov     [rsp+170h+var_E8], rax
0x18004e807  lea     rax, [rbp+50h+var_98]
0x18004e80b  mov     [rsp+170h+var_F0], rax
0x18004e813  lea     rax, [rbp+50h+var_90]
0x18004e817  mov     [rsp+170h+var_F8], rax
0x18004e81c  lea     rax, [rbp+50h+var_B4]
0x18004e820  mov     [rsp+170h+var_100], rax
0x18004e825  lea     rax, [rbp+50h+var_88]
0x18004e829  mov     [rsp+170h+var_108], rax
0x18004e82e  lea     rax, [rbp+50h+var_B0]
0x18004e832  mov     [rsp+170h+var_110], rax
0x18004e837  lea     rax, [rbp+50h+var_80]
0x18004e83b  mov     [rsp+170h+var_118], rax
0x18004e840  lea     rax, [rbp+50h+var_AC]
0x18004e844  mov     [rsp+170h+var_120], rax
0x18004e849  lea     rax, [rbp+50h+var_78]
0x18004e84d  mov     [rsp+170h+var_128], rax
0x18004e852  lea     rax, [rbp+50h+var_D0]
0x18004e856  mov     [rsp+170h+var_130], rax
0x18004e85b  lea     rax, [rbp+50h+var_70]
0x18004e85f  mov     [rsp+170h+var_138], rax
0x18004e864  lea     rax, [rbp+50h+SRWLock]
0x18004e868  mov     [rsp+170h+var_140], rax
0x18004e86d  lea     rax, [rbp+50h+var_68]
0x18004e871  mov     [rsp+170h+var_148], rax
0x18004e876  lea     rax, [rbp+50h+var_C0]
0x18004e87a  mov     [rsp+170h+var_150], rax
0x18004e87f  lea     rdx, unk_18009AED0
0x18004e886  mov     rcx, r9
0x18004e889  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18004e88e  jmp     loc_18004E968
0x18004e893  lea     rdx, [rbp+50h+var_C0]
0x18004e897  call    ?LockExclusive@?$ActivityBase@VDataPackageTracing@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004e89c  mov     rax, [rbx+110h]
0x18004e8a3  mov     dword ptr [rax], 2
0x18004e8a9  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18004e8ad  test    rcx, rcx
0x18004e8b0  jz      short loc_18004E8B8
0x18004e8b2  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e8b8  call    ?Provider@DataPackageTracing@@SAPEBU_tlgProvider_t@@XZ; DataPackageTracing::Provider(void)
0x18004e8bd  mov     rdi, rax
0x18004e8c0  mov     ecx, [rax]
0x18004e8c2  cmp     ecx, 5
0x18004e8c5  jbe     loc_18004E968
0x18004e8cb  mov     rax, [rax+18h]
0x18004e8cf  mov     rcx, [rdi+10h]
0x18004e8d3  mov     rdx, 400000000000h
0x18004e8dd  test    rdx, rcx
0x18004e8e0  jz      loc_18004E968
0x18004e8e6  mov     rcx, rax
0x18004e8e9  and     rcx, rdx
0x18004e8ec  cmp     rcx, rax
0x18004e8ef  jnz     short loc_18004E968
0x18004e8f1  call    cs:__imp_GetCurrentThreadId
0x18004e8f7  mov     dword ptr [rbp+50h+SRWLock], eax
0x18004e8fa  mov     r8, [rbx+110h]
0x18004e901  mov     eax, [r8+48h]
0x18004e905  mov     [rbp+50h+var_D0], eax
0x18004e908  mov     [rbp+50h+var_C0], 0
0x18004e910  lea     rax, [rbp+50h+SRWLock]
0x18004e914  mov     [rbp+50h+var_20], rax
0x18004e918  mov     [rbp+50h+var_18], 4
0x18004e920  lea     rax, [rbp+50h+var_D0]
0x18004e924  mov     [rbp+50h+var_30], rax
0x18004e928  mov     [rbp+50h+var_28], 4
0x18004e930  lea     rax, [rbp+50h+var_C0]
0x18004e934  mov     [rbp+50h+var_40], rax
0x18004e938  mov     [rbp+50h+var_38], 8
0x18004e940  add     r8, 8
0x18004e944  lea     rax, [rbp+50h+var_60]
0x18004e948  mov     [rsp+170h+var_148], rax
0x18004e94d  mov     dword ptr [rsp+170h+var_150], 5
0x18004e955  xor     r9d, r9d
0x18004e958  lea     rdx, byte_18009A749
0x18004e95f  mov     rcx, rdi
0x18004e962  call    _tlgWriteTransfer_EventWriteTransfer
0x18004e967  nop
0x18004e968  cmp     dword ptr [rbx+138h], 0
0x18004e96f  jz      short loc_18004E9CF
0x18004e971  add     rbx, 120h
0x18004e978  call    cs:__imp_GetCurrentThreadId
0x18004e97e  cmp     [rbx+18h], eax
0x18004e981  jz      short loc_18004E99F
0x18004e983  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18004e98a  test    rax, rax
0x18004e98d  jz      short loc_18004E99F
0x18004e98f  mov     rdx, [rbp+58h]
0x18004e993  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18004e99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e99f  mov     dword ptr [rbx+18h], 0
0x18004e9a6  mov     rcx, [rbx]
0x18004e9a9  jmp     short loc_18004E9B7
0x18004e9ab  cmp     rax, rbx
0x18004e9ae  jz      short loc_18004E9C1
0x18004e9b0  lea     rcx, [rax+10h]
0x18004e9b4  mov     [rbx], rcx
0x18004e9b7  mov     rax, [rcx]
0x18004e9ba  test    rax, rax
0x18004e9bd  jnz     short loc_18004E9AB
0x18004e9bf  jmp     short loc_18004E9C8
0x18004e9c1  mov     rax, [rbx+10h]
0x18004e9c5  mov     [rcx], rax
0x18004e9c8  mov     qword ptr [rbx], 0
0x18004e9cf  mov     rcx, [rbp+50h+var_10]
0x18004e9d3  xor     rcx, rsp; StackCookie
0x18004e9d6  call    __security_check_cookie
0x18004e9db  lea     r11, [rsp+170h+var_s0]
0x18004e9e3  mov     rbx, [r11+18h]
0x18004e9e7  mov     rdi, [r11+20h]
0x18004e9eb  mov     rsp, r11
0x18004e9ee  pop     rbp
0x18004e9ef  retn
```
