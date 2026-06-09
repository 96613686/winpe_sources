# FontEmbeddingTelemetry::TTEmbedFont::StartActivity(void)

- ea: `0x180025f60`
- end: `0x180025ff6`
- name: `?StartActivity@TTEmbedFont@FontEmbeddingTelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(FontEmbeddingTelemetry::TTEmbedFont *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027180`

## callees

- `0x180001968`
- `0x18001bc80`
- `0x18001c024`
- `0x18001cf28`
- `0x180025f60`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180025f81`
- `KERNEL32!GetCurrentThreadId` at `0x180025f81`

## pseudocode

```c
void __fastcall FontEmbeddingTelemetry::TTEmbedFont::StartActivity(FontEmbeddingTelemetry::TTEmbedFont *this)
{
  const struct _tlgProvider_t *v2; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v4; // r8
  int v5; // r9d
  DWORD v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = FontEmbeddingTelemetryProvider::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = *((_QWORD *)this + 34);
    v6 = CurrentThreadId;
    v7 = 0;
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v2,
      (unsigned int)&word_18002DC46,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&v6);
  }
  wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180025f60  mov     [rsp+arg_10], rbx
0x180025f65  push    rdi
0x180025f66  sub     rsp, 30h
0x180025f6a  mov     rbx, rcx
0x180025f6d  call    ?zInternalStart@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180025f72  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x180025f77  mov     rdi, rax
0x180025f7a  mov     edx, [rax]
0x180025f7c  cmp     edx, 5
0x180025f7f  jbe     short loc_180025FE4
0x180025f81  call    cs:__imp_GetCurrentThreadId
0x180025f87  mov     r8, [rbx+110h]
0x180025f8e  mov     [rsp+38h+arg_0], eax
0x180025f92  xor     eax, eax
0x180025f94  mov     [rsp+38h+arg_8], rax
0x180025f99  cmp     [r8+4], al
0x180025f9d  jz      short loc_180025FBA
0x180025f9f  lea     r9, [r8+18h]
0x180025fa3  cmp     [r9], eax
0x180025fa6  jnz     short loc_180025FBD
0x180025fa8  cmp     [r9+4], eax
0x180025fac  jnz     short loc_180025FBD
0x180025fae  cmp     [r9+8], eax
0x180025fb2  jnz     short loc_180025FBD
0x180025fb4  cmp     [r9+0Ch], eax
0x180025fb8  jnz     short loc_180025FBD
0x180025fba  mov     r9, rax
0x180025fbd  lea     rax, [rsp+38h+arg_0]
0x180025fc2  add     r8, 8
0x180025fc6  mov     [rsp+38h+var_10], rax
0x180025fcb  lea     rdx, word_18002DC46
0x180025fd2  lea     rax, [rsp+38h+arg_8]
0x180025fd7  mov     rcx, rdi
0x180025fda  mov     [rsp+38h+var_18], rax
0x180025fdf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180025fe4  mov     rcx, rbx
0x180025fe7  mov     rbx, [rsp+38h+arg_10]
0x180025fec  add     rsp, 30h
0x180025ff0  pop     rdi
0x180025ff1  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
