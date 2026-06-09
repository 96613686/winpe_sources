# UserenvTelemetry::WINAPIDeleteProfile::StartActivity(ushort const *,ushort const *)

- ea: `0x1800131ac`
- end: `0x180013297`
- name: `?StartActivity@WINAPIDeleteProfile@UserenvTelemetry@@QEAAXPEBG0@Z`
- size: `235`
- prototype: `void __fastcall(UserenvTelemetry::WINAPIDeleteProfile *this, const size_t *, const size_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000965c`

## callees

- `0x180001b84`
- `0x180001d58`
- `0x18000cba4`
- `0x18000cc14`
- `0x180012b98`
- `0x1800131ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013202`

## pseudocode

```c
void __fastcall UserenvTelemetry::WINAPIDeleteProfile::StartActivity(
        UserenvTelemetry::WINAPIDeleteProfile *this,
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
      (int)byte_180020759,
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
0x1800131ac  mov     [rsp+arg_8], rbx
0x1800131b1  push    rbp
0x1800131b2  push    rsi
0x1800131b3  push    rdi
0x1800131b4  sub     rsp, 50h
0x1800131b8  mov     rsi, r8
0x1800131bb  mov     rbp, rdx
0x1800131be  mov     rbx, rcx
0x1800131c1  call    ?zInternalStart@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800131c6  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x1800131cb  mov     rdi, rax
0x1800131ce  mov     r9d, [rax]
0x1800131d1  cmp     r9d, 5
0x1800131d5  jbe     loc_180013283
0x1800131db  mov     rdx, 400000000000h
0x1800131e5  mov     rcx, rax
0x1800131e8  call    _tlgKeywordOn
0x1800131ed  test    al, al
0x1800131ef  jz      loc_180013283
0x1800131f5  mov     [rsp+68h+arg_18], rsi
0x1800131fd  mov     [rsp+68h+var_28], rbp
0x180013202  call    cs:__imp_GetCurrentThreadId
0x180013208  mov     r8, [rbx+110h]
0x18001320f  mov     [rsp+68h+arg_0], eax
0x180013213  mov     [rsp+68h+var_20], 1000000h
0x18001321c  cmp     byte ptr [r8+4], 0
0x180013221  jz      short loc_180013242
0x180013223  lea     r9, [r8+18h]
0x180013227  cmp     dword ptr [r9], 0
0x18001322b  jnz     short loc_180013245
0x18001322d  cmp     dword ptr [r9+4], 0
0x180013232  jnz     short loc_180013245
0x180013234  cmp     dword ptr [r9+8], 0
0x180013239  jnz     short loc_180013245
0x18001323b  cmp     dword ptr [r9+0Ch], 0
0x180013240  jnz     short loc_180013245
0x180013242  xor     r9d, r9d
0x180013245  lea     rax, [rsp+68h+arg_18]
0x18001324d  add     r8, 8
0x180013251  mov     [rsp+68h+var_30], rax
0x180013256  lea     rdx, byte_180020759
0x18001325d  lea     rax, [rsp+68h+var_28]
0x180013262  mov     rcx, rdi
0x180013265  mov     [rsp+68h+var_38], rax
0x18001326a  lea     rax, [rsp+68h+arg_0]
0x18001326f  mov     [rsp+68h+var_40], rax
0x180013274  lea     rax, [rsp+68h+var_20]
0x180013279  mov     [rsp+68h+var_48], rax
0x18001327e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180013283  mov     rcx, rbx
0x180013286  mov     rbx, [rsp+68h+arg_8]
0x18001328b  add     rsp, 50h
0x18001328f  pop     rdi
0x180013290  pop     rsi
0x180013291  pop     rbp
0x180013292  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
