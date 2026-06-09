# FontEmbeddingTelemetry::TTEmbedFontEx::StartActivity(void)

- ea: `0x180025ffc`
- end: `0x180026092`
- name: `?StartActivity@TTEmbedFontEx@FontEmbeddingTelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(FontEmbeddingTelemetry::TTEmbedFontEx *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800271fc`

## callees

- `0x180001968`
- `0x18001bc80`
- `0x18001c024`
- `0x18001cf28`
- `0x180025ffc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002601d`
- `KERNEL32!GetCurrentThreadId` at `0x18002601d`

## pseudocode

```c
void __fastcall FontEmbeddingTelemetry::TTEmbedFontEx::StartActivity(FontEmbeddingTelemetry::TTEmbedFontEx *this)
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
      (unsigned int)byte_18002D231,
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
0x180025ffc  mov     [rsp+arg_10], rbx
0x180026001  push    rdi
0x180026002  sub     rsp, 30h
0x180026006  mov     rbx, rcx
0x180026009  call    ?zInternalStart@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002600e  call    ?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontEmbeddingTelemetryProvider::Provider(void)
0x180026013  mov     rdi, rax
0x180026016  mov     edx, [rax]
0x180026018  cmp     edx, 5
0x18002601b  jbe     short loc_180026080
0x18002601d  call    cs:__imp_GetCurrentThreadId
0x180026023  mov     r8, [rbx+110h]
0x18002602a  mov     [rsp+38h+arg_0], eax
0x18002602e  xor     eax, eax
0x180026030  mov     [rsp+38h+arg_8], rax
0x180026035  cmp     [r8+4], al
0x180026039  jz      short loc_180026056
0x18002603b  lea     r9, [r8+18h]
0x18002603f  cmp     [r9], eax
0x180026042  jnz     short loc_180026059
0x180026044  cmp     [r9+4], eax
0x180026048  jnz     short loc_180026059
0x18002604a  cmp     [r9+8], eax
0x18002604e  jnz     short loc_180026059
0x180026050  cmp     [r9+0Ch], eax
0x180026054  jnz     short loc_180026059
0x180026056  mov     r9, rax
0x180026059  lea     rax, [rsp+38h+arg_0]
0x18002605e  add     r8, 8
0x180026062  mov     [rsp+38h+var_10], rax
0x180026067  lea     rdx, byte_18002D231
0x18002606e  lea     rax, [rsp+38h+arg_8]
0x180026073  mov     rcx, rdi
0x180026076  mov     [rsp+38h+var_18], rax
0x18002607b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180026080  mov     rcx, rbx
0x180026083  mov     rbx, [rsp+38h+arg_10]
0x180026088  add     rsp, 30h
0x18002608c  pop     rdi
0x18002608d  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
