# wil::ActivityBase<wpc::UI::Logging::MonitorUILogger,1,35184372088832,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x14004ac60`
- end: `0x14004ad9f`
- name: `?Stop@?$ActivityBase@VMonitorUILogger@Logging@UI@wpc@@$00$0CAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `319`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x14004620c`
- `0x1400465cc`
- `0x14004c410`

## callees

- `0x1400015d0`
- `0x140006314`
- `0x140012bd4`
- `0x140018560`
- `0x140019420`
- `0x14002af88`
- `0x14004ac60`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004acaf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004acaf`
- `KERNEL32!GetCurrentThreadId` at `0x14004ad02`
- `KERNEL32!GetCurrentThreadId` at `0x14004ad02`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<wpc::UI::Logging::MonitorUILogger,1,35184372088832,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
    v7 = wpc::UI::Logging::MonitorUILogger::Provider();
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
          (__int64)byte_1400D5E59,
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
0x14004ac60  mov     rax, rsp
0x14004ac63  push    rbx
0x14004ac64  push    rsi
0x14004ac65  push    rdi
0x14004ac66  sub     rsp, 0E0h
0x14004ac6d  mov     esi, edx
0x14004ac6f  mov     rbx, rcx
0x14004ac72  lea     rdx, [rax+8]
0x14004ac76  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004ac7b  mov     rax, [rbx+110h]
0x14004ac82  mov     edi, [rax+0F8h]
0x14004ac88  cmp     edi, 1
0x14004ac8b  jl      loc_14004AD82
0x14004ac91  cmp     dword ptr [rax+48h], 0
0x14004ac95  jl      short loc_14004AC9A
0x14004ac97  mov     [rax+48h], esi
0x14004ac9a  dec     edi
0x14004ac9c  mov     [rax+0F8h], edi
0x14004aca2  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x14004acaa  test    rcx, rcx
0x14004acad  jz      short loc_14004ACB5
0x14004acaf  call    cs:__imp_ReleaseSRWLockExclusive
0x14004acb5  test    edi, edi
0x14004acb7  jnz     short loc_14004ACCD
0x14004acb9  mov     rax, [rbx]
0x14004acbc  mov     rcx, rbx
0x14004acbf  mov     rax, [rax+8]
0x14004acc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004acc8  jmp     loc_14004AD64
0x14004accd  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004acd2  mov     rdi, rax
0x14004acd5  mov     ecx, [rax]
0x14004acd7  cmp     ecx, 5
0x14004acda  jbe     loc_14004AD64
0x14004ace0  mov     rax, [rax+18h]
0x14004ace4  mov     rcx, [rdi+10h]
0x14004ace8  mov     rdx, 200000000000h
0x14004acf2  test    rdx, rcx
0x14004acf5  jz      short loc_14004AD64
0x14004acf7  mov     rcx, rax
0x14004acfa  and     rcx, rdx
0x14004acfd  cmp     rcx, rax
0x14004ad00  jnz     short loc_14004AD64
0x14004ad02  call    cs:__imp_GetCurrentThreadId
0x14004ad08  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x14004ad0f  mov     [rsp+0F8h+arg_10], esi
0x14004ad16  mov     [rsp+0F8h+arg_18], 1000000h
0x14004ad22  mov     r8, [rbx+110h]
0x14004ad29  add     r8, 8
0x14004ad2d  lea     rax, [rsp+0F8h+SRWLock]
0x14004ad35  mov     [rsp+0F8h+var_C8], rax
0x14004ad3a  lea     rax, [rsp+0F8h+arg_10]
0x14004ad42  mov     [rsp+0F8h+var_D0], rax
0x14004ad47  lea     rax, [rsp+0F8h+arg_18]
0x14004ad4f  mov     [rsp+0F8h+var_D8], rax
0x14004ad54  lea     rdx, byte_1400D5E59
0x14004ad5b  mov     rcx, rdi
0x14004ad5e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004ad63  nop
0x14004ad64  lea     rcx, [rbx+120h]; this
0x14004ad6b  cmp     dword ptr [rcx+18h], 0
0x14004ad6f  jz      short loc_14004AD77
0x14004ad71  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14004ad76  nop
0x14004ad77  add     rsp, 0E0h
0x14004ad7e  pop     rdi
0x14004ad7f  pop     rsi
0x14004ad80  pop     rbx
0x14004ad81  retn
0x14004ad82  xor     edx, edx; Val
0x14004ad84  mov     r8d, 98h; Size
0x14004ad8a  lea     rcx, [rsp+0F8h+var_B8]; void *
0x14004ad8f  call    memset_0
0x14004ad94  lea     rcx, [rsp+0F8h+var_B8]; this
0x14004ad99  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
