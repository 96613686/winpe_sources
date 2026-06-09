# wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18001d4e8`
- end: `0x18001d503`
- name: `?IgnoreCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `27`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c41c`
- `0x180026140`
- `0x180026380`
- `0x1800265c0`
- `0x180026800`

## callees

- `0x18001d4e8`
- `0x180026a34`

## pseudocode

```c
void __fastcall wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  v1 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
  if ( *((_DWORD *)v1 + 6) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x18001d4e8  sub     rsp, 28h
0x18001d4ec  add     rcx, 120h; this
0x18001d4f3  cmp     dword ptr [rcx+18h], 0
0x18001d4f7  jz      short loc_18001D4FE
0x18001d4f9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001d4fe  add     rsp, 28h
0x18001d502  retn
```
