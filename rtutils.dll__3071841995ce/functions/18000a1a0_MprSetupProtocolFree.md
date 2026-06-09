# MprSetupProtocolFree

- ea: `0x18000a1a0`
- end: `0x18000a1cf`
- name: `MprSetupProtocolFree`
- size: `47`
- prototype: `DWORD __stdcall(LPVOID lpBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a1a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1c1`

## pseudocode

```c
DWORD __stdcall MprSetupProtocolFree(LPVOID lpBuffer)
{
  HANDLE ProcessHeap; // rax

  if ( !lpBuffer )
    return 87;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpBuffer);
  return 0;
}

```

## disassembly

```asm
0x18000a1a0  push    rbx
0x18000a1a2  sub     rsp, 20h
0x18000a1a6  mov     rbx, rcx
0x18000a1a9  test    rcx, rcx
0x18000a1ac  jnz     short loc_18000A1B3
0x18000a1ae  lea     eax, [rcx+57h]
0x18000a1b1  jmp     short loc_18000A1C9
0x18000a1b3  call    cs:__imp_GetProcessHeap
0x18000a1b9  mov     r8, rbx; lpMem
0x18000a1bc  xor     edx, edx; dwFlags
0x18000a1be  mov     rcx, rax; hHeap
0x18000a1c1  call    cs:__imp_HeapFree
0x18000a1c7  xor     eax, eax
0x18000a1c9  add     rsp, 20h
0x18000a1cd  pop     rbx
0x18000a1ce  retn
```
