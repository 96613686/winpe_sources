# wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140055930`
- end: `0x140055a6f`
- name: `?Stop@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `319`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x14004f61c`
- `0x140055a78`
- `0x140056268`
- `0x1400a300e`
- `0x1400a32a9`
- `0x1400a333b`

## callees

- `0x1400015d0`
- `0x140006314`
- `0x140012bd4`
- `0x140018560`
- `0x140019420`
- `0x1400544c4`
- `0x140055930`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14005597f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14005597f`
- `KERNEL32!GetCurrentThreadId` at `0x1400559d2`
- `KERNEL32!GetCurrentThreadId` at `0x1400559d2`

## pseudocode

```c
void __fastcall wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // r9
  const struct wil::FailureInfo *v11; // rdx
  _BYTE v12[184]; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  int v14; // [rsp+110h] [rbp+18h] BYREF
  __int64 v15; // [rsp+118h] [rbp+20h] BYREF

  wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v11);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    v7 = TraceLog::Providers::ScreenTime::Provider();
    v8 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u )
    {
      v9 = *((_QWORD *)v7 + 3);
      if ( (*(_QWORD *)(v8 + 16) & 0x200000000000LL) != 0 && (v9 & 0x200000000000LL) == v9 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v14 = a2;
        v15 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (__int64)&byte_1400D65BF,
          *(_QWORD *)(a1 + 272) + 8LL,
          v10,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&SRWLock);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x140055930  mov     rax, rsp
0x140055933  push    rbx
0x140055934  push    rsi
0x140055935  push    rdi
0x140055936  sub     rsp, 0E0h
0x14005593d  mov     esi, edx
0x14005593f  mov     rbx, rcx
0x140055942  lea     rdx, [rax+8]
0x140055946  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14005594b  mov     rax, [rbx+110h]
0x140055952  mov     edi, [rax+0F8h]
0x140055958  cmp     edi, 1
0x14005595b  jl      loc_140055A52
0x140055961  cmp     dword ptr [rax+48h], 0
0x140055965  jl      short loc_14005596A
0x140055967  mov     [rax+48h], esi
0x14005596a  dec     edi
0x14005596c  mov     [rax+0F8h], edi
0x140055972  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x14005597a  test    rcx, rcx
0x14005597d  jz      short loc_140055985
0x14005597f  call    cs:__imp_ReleaseSRWLockExclusive
0x140055985  test    edi, edi
0x140055987  jnz     short loc_14005599D
0x140055989  mov     rax, [rbx]
0x14005598c  mov     rcx, rbx
0x14005598f  mov     rax, [rax+8]
0x140055993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055998  jmp     loc_140055A34
0x14005599d  call    ?Provider@ScreenTime@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::ScreenTime::Provider(void)
0x1400559a2  mov     rdi, rax
0x1400559a5  mov     ecx, [rax]
0x1400559a7  cmp     ecx, 5
0x1400559aa  jbe     loc_140055A34
0x1400559b0  mov     rax, [rax+18h]
0x1400559b4  mov     rcx, [rdi+10h]
0x1400559b8  mov     rdx, 200000000000h
0x1400559c2  test    rdx, rcx
0x1400559c5  jz      short loc_140055A34
0x1400559c7  mov     rcx, rax
0x1400559ca  and     rcx, rdx
0x1400559cd  cmp     rcx, rax
0x1400559d0  jnz     short loc_140055A34
0x1400559d2  call    cs:__imp_GetCurrentThreadId
0x1400559d8  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x1400559df  mov     [rsp+0F8h+arg_10], esi
0x1400559e6  mov     [rsp+0F8h+arg_18], 1000000h
0x1400559f2  mov     r8, [rbx+110h]
0x1400559f9  add     r8, 8
0x1400559fd  lea     rax, [rsp+0F8h+SRWLock]
0x140055a05  mov     [rsp+0F8h+var_C8], rax
0x140055a0a  lea     rax, [rsp+0F8h+arg_10]
0x140055a12  mov     [rsp+0F8h+var_D0], rax
0x140055a17  lea     rax, [rsp+0F8h+arg_18]
0x140055a1f  mov     [rsp+0F8h+var_D8], rax
0x140055a24  lea     rdx, byte_1400D65BF
0x140055a2b  mov     rcx, rdi
0x140055a2e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140055a33  nop
0x140055a34  lea     rcx, [rbx+120h]; this
0x140055a3b  cmp     dword ptr [rcx+18h], 0
0x140055a3f  jz      short loc_140055A47
0x140055a41  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140055a46  nop
0x140055a47  add     rsp, 0E0h
0x140055a4e  pop     rdi
0x140055a4f  pop     rsi
0x140055a50  pop     rbx
0x140055a51  retn
0x140055a52  xor     edx, edx; Val
0x140055a54  mov     r8d, 98h; Size
0x140055a5a  lea     rcx, [rsp+0F8h+var_B8]; void *
0x140055a5f  call    memset_0
0x140055a64  lea     rcx, [rsp+0F8h+var_B8]; this
0x140055a69  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
