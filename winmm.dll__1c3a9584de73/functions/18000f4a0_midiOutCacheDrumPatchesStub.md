# midiOutCacheDrumPatchesStub

- ea: `0x18000f4a0`
- end: `0x18000f4a7`
- name: `midiOutCacheDrumPatchesStub`
- size: `7`
- prototype: `MMRESULT __stdcall(HMIDIOUT hmo, UINT uPatch, LPWORD pwkya, UINT fuCache)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiOutCacheDrumPatches` at `0x18000f4a0`

## pseudocode

```c
// attributes: thunk
MMRESULT __stdcall midiOutCacheDrumPatchesStub(HMIDIOUT hmo, UINT uPatch, LPWORD pwkya, UINT fuCache)
{
  return midiOutCacheDrumPatches(hmo, uPatch, pwkya, fuCache);
}

```

## disassembly

```asm
0x18000f4a0  jmp     cs:__imp_midiOutCacheDrumPatches
```
