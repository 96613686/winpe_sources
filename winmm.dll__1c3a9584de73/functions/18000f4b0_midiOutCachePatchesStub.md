# midiOutCachePatchesStub

- ea: `0x18000f4b0`
- end: `0x18000f4b7`
- name: `midiOutCachePatchesStub`
- size: `7`
- prototype: `MMRESULT __stdcall(HMIDIOUT hmo, UINT uBank, LPWORD pwpa, UINT fuCache)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiOutCachePatches` at `0x18000f4b0`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall midiOutCachePatchesStub(HMIDIOUT hmo, UINT uBank, LPWORD pwpa, UINT fuCache)
{
  return midiOutCachePatches(hmo, uBank, pwpa, fuCache);
}

```

## disassembly

```asm
0x18000f4b0  jmp     cs:__imp_midiOutCachePatches
```
