# wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x18001cf28`
- end: `0x18001cf43`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VFontEmbeddingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `27`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c2fc`
- `0x180025f60`
- `0x180025ffc`
- `0x180026098`

## callees

- `0x18001cf28`
- `0x18001cf4c`

## pseudocode

```c
void __fastcall wil::ActivityBase<FontEmbeddingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  v1 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
  if ( !*((_DWORD *)v1 + 6) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v1);
}

```

## disassembly

```asm
0x18001cf28  sub     rsp, 28h
0x18001cf2c  add     rcx, 120h; this
0x18001cf33  cmp     dword ptr [rcx+18h], 0
0x18001cf37  jnz     short loc_18001CF3E
0x18001cf39  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001cf3e  add     rsp, 28h
0x18001cf42  retn
```
