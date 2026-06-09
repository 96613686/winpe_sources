# TraceCloseClientFileW(x)

- ea: `0x10006fac`
- end: `0x10006fd0`
- name: `_TraceCloseClientFileW@4`
- size: `36`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x100023a6`
- `0x100027e0`
- `0x100075de`
- `0x10007af9`
- `0x100080a7`

## callees

- `0x10006fac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10006fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10006fbc`

## pseudocode

```c
int __thiscall TraceCloseClientFileW(HANDLE *this)
{
  if ( this[58] )
  {
    CloseHandle(this[58]);
    this[58] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x10006fac  mov     edi, edi
0x10006fae  push    esi
0x10006faf  mov     esi, ecx
0x10006fb1  mov     eax, [esi+0E8h]
0x10006fb7  test    eax, eax
0x10006fb9  jz      short loc_10006FCC
0x10006fbb  push    eax; hObject
0x10006fbc  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10006fc2  mov     dword ptr [esi+0E8h], 0
0x10006fcc  xor     eax, eax
0x10006fce  pop     esi
0x10006fcf  retn
```
