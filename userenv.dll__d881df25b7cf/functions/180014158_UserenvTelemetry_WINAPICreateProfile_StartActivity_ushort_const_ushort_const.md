# UserenvTelemetry::WINAPICreateProfile::StartActivity(ushort const *,ushort const *)

- ea: `0x180014158`
- end: `0x180014249`
- name: `?StartActivity@WINAPICreateProfile@UserenvTelemetry@@QEAAXPEBG0@Z`
- size: `241`
- prototype: `void __fastcall(UserenvTelemetry::WINAPICreateProfile *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180014c70`

## callees

- `0x180001b84`
- `0x180001d68`
- `0x18000d718`
- `0x18000d8ec`
- `0x180013c58`
- `0x180014158`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141ae`

## pseudocode

```c
void __fastcall UserenvTelemetry::WINAPICreateProfile::StartActivity(
        UserenvTelemetry::WINAPICreateProfile *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // edi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // r9d
  const unsigned __int16 *v11; // [rsp+40h] [rbp-28h] BYREF
  __int64 v12[4]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v13; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v14; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = ProfileAPILogging::Provider();
  v7 = (int)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
  {
    v14 = a3;
    v11 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v13 = CurrentThreadId;
    v12[0] = 0x1000000;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v7,
      (unsigned int)&word_180021816,
      v9 + 8,
      v10,
      (__int64)v12,
      (__int64)&v13,
      (__int64)&v11,
      (__int64)&v14);
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180014158  mov     [rsp+arg_8], rbx
0x18001415d  push    rbp
0x18001415e  push    rsi
0x18001415f  push    rdi
0x180014160  sub     rsp, 50h
0x180014164  mov     rsi, r8
0x180014167  mov     rbp, rdx
0x18001416a  mov     rbx, rcx
0x18001416d  call    ?zInternalStart@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180014172  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x180014177  mov     rdi, rax
0x18001417a  mov     r9d, [rax]
0x18001417d  cmp     r9d, 5
0x180014181  jbe     loc_180014235
0x180014187  mov     rdx, 400000000000h
0x180014191  mov     rcx, rax
0x180014194  call    _tlgKeywordOn
0x180014199  test    al, al
0x18001419b  jz      loc_180014235
0x1800141a1  mov     [rsp+68h+arg_18], rsi
0x1800141a9  mov     [rsp+68h+var_28], rbp
0x1800141ae  call    cs:__imp_GetCurrentThreadId
0x1800141b5  nop     dword ptr [rax+rax+00h]
0x1800141ba  mov     r8, [rbx+110h]
0x1800141c1  mov     [rsp+68h+arg_0], eax
0x1800141c5  mov     [rsp+68h+var_20], 1000000h
0x1800141ce  cmp     byte ptr [r8+4], 0
0x1800141d3  jz      short loc_1800141F4
0x1800141d5  lea     r9, [r8+18h]
0x1800141d9  cmp     dword ptr [r9], 0
0x1800141dd  jnz     short loc_1800141F7
0x1800141df  cmp     dword ptr [r9+4], 0
0x1800141e4  jnz     short loc_1800141F7
0x1800141e6  cmp     dword ptr [r9+8], 0
0x1800141eb  jnz     short loc_1800141F7
0x1800141ed  cmp     dword ptr [r9+0Ch], 0
0x1800141f2  jnz     short loc_1800141F7
0x1800141f4  xor     r9d, r9d
0x1800141f7  lea     rax, [rsp+68h+arg_18]
0x1800141ff  add     r8, 8
0x180014203  mov     [rsp+68h+var_30], rax
0x180014208  lea     rdx, word_180021816
0x18001420f  lea     rax, [rsp+68h+var_28]
0x180014214  mov     rcx, rdi
0x180014217  mov     [rsp+68h+var_38], rax
0x18001421c  lea     rax, [rsp+68h+arg_0]
0x180014221  mov     [rsp+68h+var_40], rax
0x180014226  lea     rax, [rsp+68h+var_20]
0x18001422b  mov     [rsp+68h+var_48], rax
0x180014230  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180014235  mov     rcx, rbx
0x180014238  mov     rbx, [rsp+68h+arg_8]
0x18001423d  add     rsp, 50h
0x180014241  pop     rdi
0x180014242  pop     rsi
0x180014243  pop     rbp
0x180014244  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
