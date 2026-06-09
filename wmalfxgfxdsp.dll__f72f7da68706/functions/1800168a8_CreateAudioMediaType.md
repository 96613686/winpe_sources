# CreateAudioMediaType

- ea: `0x1800168a8`
- end: `0x1800168c1`
- name: `CreateAudioMediaType`
- size: `25`
- prototype: `HRESULT __stdcall(const WAVEFORMATEX *pAudioFormat, UINT32 cbAudioFormatSize, IAudioMediaType **ppIAudioMediaType)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800063dc`

## callees

- `0x180016114`

## pseudocode

```c
HRESULT __stdcall CreateAudioMediaType(
        const WAVEFORMATEX *pAudioFormat,
        UINT32 cbAudioFormatSize,
        IAudioMediaType **ppIAudioMediaType)
{
  return CAudioMediaType::Create(pAudioFormat, cbAudioFormatSize, ppIAudioMediaType, 0.0, 0);
}

```

## disassembly

```asm
0x1800168a8  sub     rsp, 38h
0x1800168ac  xorps   xmm3, xmm3; float
0x1800168af  mov     [rsp+38h+var_18], 0; int
0x1800168b7  call    ?Create@CAudioMediaType@@SAJPEBUtWAVEFORMATEX@@IPEAPEAUIAudioMediaType@@MH@Z; CAudioMediaType::Create(tWAVEFORMATEX const *,uint,IAudioMediaType * *,float,int)
0x1800168bc  add     rsp, 38h
0x1800168c0  retn
```
