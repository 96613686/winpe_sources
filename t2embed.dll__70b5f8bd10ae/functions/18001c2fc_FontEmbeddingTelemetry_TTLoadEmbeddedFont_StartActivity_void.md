# FontEmbeddingTelemetry::TTLoadEmbeddedFont::StartActivity(void)

- ea: `0x18001c2fc`
- end: `0x18001c392`
- name: `?StartActivity@TTLoadEmbeddedFont@FontEmbeddingTelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(FontEmbeddingTelemetry::TTLoadEmbeddedFont *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c044`

## callees

- `0x180001968`
- `0x18001bc80`
- `0x18001c024`
- `0x18001c2fc`
- `0x18001cf28`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001c31d`
- `KERNEL32!GetCurrentThreadId` at `0x18001c31d`

## pseudocode

```c
void __fastcall FontEmbeddingTelemetry::TTLoadEmbeddedFont::StartActivity(
        FontEmbeddingTelemetry::TTLoadEmbeddedFont *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = FontEmbeddingTelemetryProvider::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    v7 = CurrentThreadId;
    v8 = 0;
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)word_18002D66A,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18001c2fc  mov     [rsp+arg_10], rbx
0x18001c301  push    rdi
0x18001c302  sub     rsp, 30h
0x18001c306  mov     rbx, rcx
0x18001c309  call    ?zInternalStart@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c30e  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x18001c313  mov     rdi, rax
0x18001c316  mov     edx, [rax]
0x18001c318  cmp     edx, 5
0x18001c31b  jbe     short loc_18001C380
0x18001c31d  call    cs:__imp_GetCurrentThreadId
0x18001c323  mov     r8, [rbx+110h]
0x18001c32a  mov     [rsp+38h+arg_0], eax
0x18001c32e  xor     eax, eax
0x18001c330  mov     [rsp+38h+arg_8], rax
0x18001c335  cmp     [r8+4], al
0x18001c339  jz      short loc_18001C356
0x18001c33b  lea     r9, [r8+18h]
0x18001c33f  cmp     [r9], eax
0x18001c342  jnz     short loc_18001C359
0x18001c344  cmp     [r9+4], eax
0x18001c348  jnz     short loc_18001C359
0x18001c34a  cmp     [r9+8], eax
0x18001c34e  jnz     short loc_18001C359
0x18001c350  cmp     [r9+0Ch], eax
0x18001c354  jnz     short loc_18001C359
0x18001c356  mov     r9, rax
0x18001c359  lea     rax, [rsp+38h+arg_0]
0x18001c35e  add     r8, 8
0x18001c362  mov     [rsp+38h+var_10], rax
0x18001c367  lea     rdx, word_18002D66A
0x18001c36e  lea     rax, [rsp+38h+arg_8]
0x18001c373  mov     rcx, rdi
0x18001c376  mov     [rsp+38h+var_18], rax
0x18001c37b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001c380  mov     rcx, rbx
0x18001c383  mov     rbx, [rsp+38h+arg_10]
0x18001c388  add     rsp, 30h
0x18001c38c  pop     rdi
0x18001c38d  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
