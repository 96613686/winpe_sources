# mciGetDeviceIDW

- ea: `0x180015260`
- end: `0x18001527e`
- name: `mciGetDeviceIDW`
- size: `30`
- prototype: `MCIDEVICEID __stdcall(LPCWSTR pszDevice)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fb24`
- `0x180010504`

## callees

- `0x180013e9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015269`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015269`

## pseudocode

```c
MCIDEVICEID __stdcall mciGetDeviceIDW(LPCWSTR pszDevice)
{
  DWORD CurrentThreadId; // eax

  CurrentThreadId = GetCurrentThreadId();
  return mciGetDeviceIDInternal(pszDevice, (void *)CurrentThreadId);
}

```

## disassembly

```asm
0x180015260  push    rbx
0x180015262  sub     rsp, 20h
0x180015266  mov     rbx, rcx
0x180015269  call    cs:__imp_GetCurrentThreadId
0x18001526f  mov     edx, eax; void *
0x180015271  mov     rcx, rbx; lpString2
0x180015274  add     rsp, 20h
0x180015278  pop     rbx
0x180015279  jmp     ?mciGetDeviceIDInternal@@YAIPEBGPEAX@Z; mciGetDeviceIDInternal(ushort const *,void *)
```
