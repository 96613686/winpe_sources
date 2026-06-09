# ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StartActivity<ushort const *>(ushort const * &&)

- ea: `0x180052630`
- end: `0x180052797`
- name: `??$StartActivity@PEBG@ComputeStorage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLib@@QEAAX$$QEAPEBG@Z`
- size: `359`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800542e4`

## callees

- `0x1800022c0`
- `0x18001c384`
- `0x18001ed48`
- `0x180020fa4`
- `0x180052630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800526b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800526b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800526f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800526f8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005268c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005268c`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StartActivity<unsigned short const *>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  RTL_SRWLOCK *v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  const struct _tlgProvider_t *v8; // rbx
  __int64 v9; // rax
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h] BYREF
  __int64 v12; // [rsp+50h] [rbp-18h] BYREF

  SRWLock = 0;
  wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
  if ( *(_DWORD *)v5 > 4u && (*((_QWORD *)v5 + 2) & 0x40) != 0 && (*((_QWORD *)v5 + 3) & 0x40LL) == *((_QWORD *)v5 + 3) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  v6 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  v7 = ComputeLib::Diagnostics::TraceProvider::Provider();
  v8 = v7;
  if ( *(_DWORD *)v7 > 4u )
  {
    v9 = *((_QWORD *)v7 + 3);
    if ( (*((_QWORD *)v8 + 2) & 0x40) != 0 && (v9 & 0x40) == v9 )
    {
      v11 = *a2;
      LODWORD(SRWLock) = GetCurrentThreadId();
      v12 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (int)v8,
        (__int64)&v12,
        (__int64)&SRWLock,
        (__int64)&v11);
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180052630  mov     rax, rsp
0x180052633  mov     [rax+10h], rbx
0x180052637  mov     [rax+18h], rsi
0x18005263b  push    rdi
0x18005263c  sub     rsp, 60h
0x180052640  mov     rsi, rdx
0x180052643  mov     qword ptr [rax-28h], 0
0x18005264b  lea     rdx, [rax-28h]
0x18005264f  mov     rdi, rcx
0x180052652  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180052657  mov     rbx, [rdi+110h]
0x18005265e  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x180052663  mov     r8d, [rax]
0x180052666  cmp     r8d, 4
0x18005266a  jbe     short loc_18005269A
0x18005266c  mov     rcx, [rax+18h]
0x180052670  mov     rax, [rax+10h]
0x180052674  test    al, 40h
0x180052676  jz      short loc_18005269A
0x180052678  mov     rax, rcx
0x18005267b  and     eax, 40h
0x18005267e  cmp     rax, rcx
0x180052681  jnz     short loc_18005269A
0x180052683  lea     rdx, [rbx+8]; ActivityId
0x180052687  mov     ecx, 3; ControlCode
0x18005268c  call    cs:__imp_EventActivityIdControl
0x180052693  nop     dword ptr [rax+rax+00h]
0x180052698  jmp     short loc_1800526A1
0x18005269a  xorps   xmm0, xmm0
0x18005269d  movups  xmmword ptr [rbx+8], xmm0
0x1800526a1  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x1800526a6  mov     dword ptr [rbx], 1
0x1800526ac  test    rcx, rcx
0x1800526af  jz      short loc_1800526BD
0x1800526b1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800526b8  nop     dword ptr [rax+rax+00h]
0x1800526bd  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x1800526c2  mov     rbx, rax
0x1800526c5  mov     ecx, [rax]
0x1800526c7  cmp     ecx, 4
0x1800526ca  jbe     loc_180052772
0x1800526d0  mov     rax, [rax+18h]
0x1800526d4  mov     rcx, [rbx+10h]
0x1800526d8  test    cl, 40h
0x1800526db  jz      loc_180052772
0x1800526e1  mov     rcx, rax
0x1800526e4  and     ecx, 40h
0x1800526e7  cmp     rcx, rax
0x1800526ea  jnz     loc_180052772
0x1800526f0  mov     rax, [rsi]
0x1800526f3  mov     [rsp+68h+var_20], rax
0x1800526f8  call    cs:__imp_GetCurrentThreadId
0x1800526ff  nop     dword ptr [rax+rax+00h]
0x180052704  mov     r8, [rdi+110h]
0x18005270b  mov     dword ptr [rsp+68h+SRWLock], eax
0x18005270f  mov     [rsp+68h+var_18], 0
0x180052718  cmp     byte ptr [r8+4], 0
0x18005271d  jz      short loc_18005273E
0x18005271f  lea     r9, [r8+18h]
0x180052723  cmp     dword ptr [r9], 0
0x180052727  jnz     short loc_180052741
0x180052729  cmp     dword ptr [r9+4], 0
0x18005272e  jnz     short loc_180052741
0x180052730  cmp     dword ptr [r9+8], 0
0x180052735  jnz     short loc_180052741
0x180052737  cmp     dword ptr [r9+0Ch], 0
0x18005273c  jnz     short loc_180052741
0x18005273e  xor     r9d, r9d
0x180052741  lea     rax, [rsp+68h+var_20]
0x180052746  add     r8, 8
0x18005274a  mov     [rsp+68h+var_38], rax; __int64
0x18005274f  lea     rdx, word_1800A19E6
0x180052756  lea     rax, [rsp+68h+SRWLock]
0x18005275b  mov     rcx, rbx; int
0x18005275e  mov     [rsp+68h+var_40], rax; __int64
0x180052763  lea     rax, [rsp+68h+var_18]
0x180052768  mov     [rsp+68h+var_48], rax; __int64
0x18005276d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180052772  lea     rcx, [rdi+120h]; this
0x180052779  cmp     dword ptr [rcx+18h], 0
0x18005277d  jnz     short loc_180052784
0x18005277f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180052784  lea     r11, [rsp+68h+var_8]
0x180052789  mov     rbx, [r11+18h]
0x18005278d  mov     rsi, [r11+20h]
0x180052791  mov     rsp, r11
0x180052794  pop     rdi
0x180052795  retn
```
