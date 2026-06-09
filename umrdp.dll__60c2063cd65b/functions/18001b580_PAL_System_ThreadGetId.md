# PAL_System_ThreadGetId

- ea: `0x18001b580`
- end: `0x18001b5a5`
- name: `PAL_System_ThreadGetId`
- size: `37`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b848`
- `0x18001b984`
- `0x180038980`
- `0x1800392d0`
- `0x18003b620`
- `0x18003c4c0`
- `0x18003cf20`

## callees

- `0x18001b580`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b595`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b595`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetId(DWORD *a1)
{
  if ( !a1 )
    return 2147942487LL;
  *a1 = GetCurrentThreadId();
  return 0;
}

```

## disassembly

```asm
0x18001b580  push    rbx
0x18001b582  sub     rsp, 20h
0x18001b586  mov     rbx, rcx
0x18001b589  test    rcx, rcx
0x18001b58c  jnz     short loc_18001B595
0x18001b58e  mov     eax, 80070057h
0x18001b593  jmp     short loc_18001B59F
0x18001b595  call    cs:__imp_GetCurrentThreadId
0x18001b59b  mov     [rbx], eax
0x18001b59d  xor     eax, eax
0x18001b59f  add     rsp, 20h
0x18001b5a3  pop     rbx
0x18001b5a4  retn
```
