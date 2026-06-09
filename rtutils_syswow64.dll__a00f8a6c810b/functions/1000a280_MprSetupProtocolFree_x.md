# MprSetupProtocolFree(x)

- ea: `0x1000a280`
- end: `0x1000a2a8`
- name: `_MprSetupProtocolFree@4`
- size: `40`
- prototype: `DWORD __stdcall(LPVOID lpBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1000a280`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000a29c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000a29c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000a295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000a295`

## pseudocode

```c
DWORD __stdcall MprSetupProtocolFree(LPVOID lpBuffer)
{
  HANDLE ProcessHeap; // eax

  if ( !lpBuffer )
    return 87;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpBuffer);
  return 0;
}

```

## disassembly

```asm
0x1000a280  mov     edi, edi
0x1000a282  push    ebp
0x1000a283  mov     ebp, esp
0x1000a285  cmp     [ebp+lpBuffer], 0
0x1000a289  jnz     short loc_1000A290
0x1000a28b  push    57h ; 'W'
0x1000a28d  pop     eax
0x1000a28e  jmp     short loc_1000A2A4
0x1000a290  push    [ebp+lpBuffer]; lpMem
0x1000a293  push    0; dwFlags
0x1000a295  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000a29b  push    eax; hHeap
0x1000a29c  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000a2a2  xor     eax, eax
0x1000a2a4  pop     ebp
0x1000a2a5  retn    4
```
