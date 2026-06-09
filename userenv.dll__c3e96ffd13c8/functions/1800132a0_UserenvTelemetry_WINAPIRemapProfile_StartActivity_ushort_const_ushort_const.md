# UserenvTelemetry::WINAPIRemapProfile::StartActivity(ushort const *,ushort const *)

- ea: `0x1800132a0`
- end: `0x18001338b`
- name: `?StartActivity@WINAPIRemapProfile@UserenvTelemetry@@QEAAXPEBG0@Z`
- size: `235`
- prototype: `void __fastcall(UserenvTelemetry::WINAPIRemapProfile *this, const size_t *, const size_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013d50`

## callees

- `0x180001b84`
- `0x180001d58`
- `0x18000cba4`
- `0x18000cc14`
- `0x180012b98`
- `0x1800132a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800132f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800132f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UserenvTelemetry::WINAPIRemapProfile::StartActivity(
        UserenvTelemetry::WINAPIRemapProfile *this,
        const size_t *a2,
        const size_t *a3)
{
  __int64 v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  const size_t *v13; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14[4]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v15; // [rsp+70h] [rbp+8h] BYREF
  const size_t *v16; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v7 = ProfileAPILogging::Provider(v6);
  v9 = (int)v7;
  if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v8) )
  {
    v16 = a3;
    v13 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    v15 = CurrentThreadId;
    v14[0] = 0x1000000;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v9,
      (int)byte_180020BC1,
      v11 + 8,
      v12,
      (__int64)v14,
      (__int64)&v15,
      &v13,
      &v16);
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800132a0  mov     [rsp+arg_8], rbx
0x1800132a5  push    rbp
0x1800132a6  push    rsi
0x1800132a7  push    rdi
0x1800132a8  sub     rsp, 50h
0x1800132ac  mov     rsi, r8
0x1800132af  mov     rbp, rdx
0x1800132b2  mov     rbx, rcx
0x1800132b5  call    ?zInternalStart@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800132ba  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x1800132bf  mov     rdi, rax
0x1800132c2  mov     r9d, [rax]
0x1800132c5  cmp     r9d, 5
0x1800132c9  jbe     loc_180013377
0x1800132cf  mov     rdx, 400000000000h
0x1800132d9  mov     rcx, rax
0x1800132dc  call    _tlgKeywordOn
0x1800132e1  test    al, al
0x1800132e3  jz      loc_180013377
0x1800132e9  mov     [rsp+68h+arg_18], rsi
0x1800132f1  mov     [rsp+68h+var_28], rbp
0x1800132f6  call    cs:__imp_GetCurrentThreadId
0x1800132fc  mov     r8, [rbx+110h]
0x180013303  mov     [rsp+68h+arg_0], eax
0x180013307  mov     [rsp+68h+var_20], 1000000h
0x180013310  cmp     byte ptr [r8+4], 0
0x180013315  jz      short loc_180013336
0x180013317  lea     r9, [r8+18h]
0x18001331b  cmp     dword ptr [r9], 0
0x18001331f  jnz     short loc_180013339
0x180013321  cmp     dword ptr [r9+4], 0
0x180013326  jnz     short loc_180013339
0x180013328  cmp     dword ptr [r9+8], 0
0x18001332d  jnz     short loc_180013339
0x18001332f  cmp     dword ptr [r9+0Ch], 0
0x180013334  jnz     short loc_180013339
0x180013336  xor     r9d, r9d
0x180013339  lea     rax, [rsp+68h+arg_18]
0x180013341  add     r8, 8
0x180013345  mov     [rsp+68h+var_30], rax
0x18001334a  lea     rdx, byte_180020BC1
0x180013351  lea     rax, [rsp+68h+var_28]
0x180013356  mov     rcx, rdi
0x180013359  mov     [rsp+68h+var_38], rax
0x18001335e  lea     rax, [rsp+68h+arg_0]
0x180013363  mov     [rsp+68h+var_40], rax
0x180013368  lea     rax, [rsp+68h+var_20]
0x18001336d  mov     [rsp+68h+var_48], rax
0x180013372  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180013377  mov     rcx, rbx
0x18001337a  mov     rbx, [rsp+68h+arg_8]
0x18001337f  add     rsp, 50h
0x180013383  pop     rdi
0x180013384  pop     rsi
0x180013385  pop     rbp
0x180013386  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
