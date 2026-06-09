# FontEmbeddingTelemetry::TTEmbedFontFromFileA::StartActivity(void)

- ea: `0x180026098`
- end: `0x18002612e`
- name: `?StartActivity@TTEmbedFontFromFileA@FontEmbeddingTelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(FontEmbeddingTelemetry::TTEmbedFontFromFileA *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027278`

## callees

- `0x180001968`
- `0x18001bc80`
- `0x18001c024`
- `0x18001cf28`
- `0x180026098`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800260b9`
- `KERNEL32!GetCurrentThreadId` at `0x1800260b9`

## pseudocode

```c
void __fastcall FontEmbeddingTelemetry::TTEmbedFontFromFileA::StartActivity(
        FontEmbeddingTelemetry::TTEmbedFontFromFileA *this)
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
      (unsigned int)byte_18002D8BD,
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
0x180026098  mov     [rsp+arg_10], rbx
0x18002609d  push    rdi
0x18002609e  sub     rsp, 30h
0x1800260a2  mov     rbx, rcx
0x1800260a5  call    ?zInternalStart@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800260aa  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x1800260af  mov     rdi, rax
0x1800260b2  mov     edx, [rax]
0x1800260b4  cmp     edx, 5
0x1800260b7  jbe     short loc_18002611C
0x1800260b9  call    cs:__imp_GetCurrentThreadId
0x1800260bf  mov     r8, [rbx+110h]
0x1800260c6  mov     [rsp+38h+arg_0], eax
0x1800260ca  xor     eax, eax
0x1800260cc  mov     [rsp+38h+arg_8], rax
0x1800260d1  cmp     [r8+4], al
0x1800260d5  jz      short loc_1800260F2
0x1800260d7  lea     r9, [r8+18h]
0x1800260db  cmp     [r9], eax
0x1800260de  jnz     short loc_1800260F5
0x1800260e0  cmp     [r9+4], eax
0x1800260e4  jnz     short loc_1800260F5
0x1800260e6  cmp     [r9+8], eax
0x1800260ea  jnz     short loc_1800260F5
0x1800260ec  cmp     [r9+0Ch], eax
0x1800260f0  jnz     short loc_1800260F5
0x1800260f2  mov     r9, rax
0x1800260f5  lea     rax, [rsp+38h+arg_0]
0x1800260fa  add     r8, 8
0x1800260fe  mov     [rsp+38h+var_10], rax
0x180026103  lea     rdx, byte_18002D8BD
0x18002610a  lea     rax, [rsp+38h+arg_8]
0x18002610f  mov     rcx, rdi
0x180026112  mov     [rsp+38h+var_18], rax
0x180026117  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002611c  mov     rcx, rbx
0x18002611f  mov     rbx, [rsp+38h+arg_10]
0x180026124  add     rsp, 30h
0x180026128  pop     rdi
0x180026129  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
