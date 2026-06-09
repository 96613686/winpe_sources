# PAL_System_CritSecTerminate

- ea: `0x18001b3d8`
- end: `0x18001b404`
- name: `PAL_System_CritSecTerminate`
- size: `44`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a180`
- `0x18000ab84`
- `0x180036ab8`

## callees

- `0x18001b3d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b3ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b3ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b3f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b3f6`

## pseudocode

```c
__int64 __fastcall PAL_System_CritSecTerminate(struct _RTL_CRITICAL_SECTION *hMem)
{
  if ( !hMem )
    return 2147942487LL;
  DeleteCriticalSection(hMem);
  LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x18001b3d8  push    rbx
0x18001b3da  sub     rsp, 20h
0x18001b3de  mov     rbx, rcx
0x18001b3e1  test    rcx, rcx
0x18001b3e4  jnz     short loc_18001B3ED
0x18001b3e6  mov     eax, 80070057h
0x18001b3eb  jmp     short loc_18001B3FE
0x18001b3ed  call    cs:__imp_DeleteCriticalSection
0x18001b3f3  mov     rcx, rbx; hMem
0x18001b3f6  call    cs:__imp_LocalFree
0x18001b3fc  xor     eax, eax
0x18001b3fe  add     rsp, 20h
0x18001b402  pop     rbx
0x18001b403  retn
```
