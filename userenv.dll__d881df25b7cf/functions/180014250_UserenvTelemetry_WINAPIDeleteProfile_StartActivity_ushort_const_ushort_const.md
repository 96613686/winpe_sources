# UserenvTelemetry::WINAPIDeleteProfile::StartActivity(ushort const *,ushort const *)

- ea: `0x180014250`
- end: `0x180014341`
- name: `?StartActivity@WINAPIDeleteProfile@UserenvTelemetry@@QEAAXPEBG0@Z`
- size: `241`
- prototype: `void __fastcall(UserenvTelemetry::WINAPIDeleteProfile *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009f74`

## callees

- `0x180001b84`
- `0x180001d68`
- `0x18000d718`
- `0x18000d8ec`
- `0x180013c58`
- `0x180014250`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800142a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800142a6`

## pseudocode

```c
void __fastcall UserenvTelemetry::WINAPIDeleteProfile::StartActivity(
        UserenvTelemetry::WINAPIDeleteProfile *this,
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
      (unsigned int)byte_180021799,
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
0x180014250  mov     [rsp+arg_8], rbx
0x180014255  push    rbp
0x180014256  push    rsi
0x180014257  push    rdi
0x180014258  sub     rsp, 50h
0x18001425c  mov     rsi, r8
0x18001425f  mov     rbp, rdx
0x180014262  mov     rbx, rcx
0x180014265  call    ?zInternalStart@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001426a  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x18001426f  mov     rdi, rax
0x180014272  mov     r9d, [rax]
0x180014275  cmp     r9d, 5
0x180014279  jbe     loc_18001432D
0x18001427f  mov     rdx, 400000000000h
0x180014289  mov     rcx, rax
0x18001428c  call    _tlgKeywordOn
0x180014291  test    al, al
0x180014293  jz      loc_18001432D
0x180014299  mov     [rsp+68h+arg_18], rsi
0x1800142a1  mov     [rsp+68h+var_28], rbp
0x1800142a6  call    cs:__imp_GetCurrentThreadId
0x1800142ad  nop     dword ptr [rax+rax+00h]
0x1800142b2  mov     r8, [rbx+110h]
0x1800142b9  mov     [rsp+68h+arg_0], eax
0x1800142bd  mov     [rsp+68h+var_20], 1000000h
0x1800142c6  cmp     byte ptr [r8+4], 0
0x1800142cb  jz      short loc_1800142EC
0x1800142cd  lea     r9, [r8+18h]
0x1800142d1  cmp     dword ptr [r9], 0
0x1800142d5  jnz     short loc_1800142EF
0x1800142d7  cmp     dword ptr [r9+4], 0
0x1800142dc  jnz     short loc_1800142EF
0x1800142de  cmp     dword ptr [r9+8], 0
0x1800142e3  jnz     short loc_1800142EF
0x1800142e5  cmp     dword ptr [r9+0Ch], 0
0x1800142ea  jnz     short loc_1800142EF
0x1800142ec  xor     r9d, r9d
0x1800142ef  lea     rax, [rsp+68h+arg_18]
0x1800142f7  add     r8, 8
0x1800142fb  mov     [rsp+68h+var_30], rax
0x180014300  lea     rdx, byte_180021799
0x180014307  lea     rax, [rsp+68h+var_28]
0x18001430c  mov     rcx, rdi
0x18001430f  mov     [rsp+68h+var_38], rax
0x180014314  lea     rax, [rsp+68h+arg_0]
0x180014319  mov     [rsp+68h+var_40], rax
0x18001431e  lea     rax, [rsp+68h+var_20]
0x180014323  mov     [rsp+68h+var_48], rax
0x180014328  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001432d  mov     rcx, rbx
0x180014330  mov     rbx, [rsp+68h+arg_8]
0x180014335  add     rsp, 50h
0x180014339  pop     rdi
0x18001433a  pop     rsi
0x18001433b  pop     rbp
0x18001433c  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
