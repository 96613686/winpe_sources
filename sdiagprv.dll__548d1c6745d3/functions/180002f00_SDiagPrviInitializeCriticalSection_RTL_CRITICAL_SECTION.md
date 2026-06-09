# SDiagPrviInitializeCriticalSection(_RTL_CRITICAL_SECTION *)

- ea: `0x180002f00`
- end: `0x180002f1d`
- name: `?SDiagPrviInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002024`
- `0x180003540`
- `0x180007660`

## callees

- `0x180002f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002f08`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002f08`

## pseudocode

```c
__int64 __fastcall SDiagPrviInitializeCriticalSection(struct _RTL_CRITICAL_SECTION *a1)
{
  InitializeCriticalSection(a1);
  return 0;
}

```

## disassembly

```asm
0x180002f00  push    rbx
0x180002f02  sub     rsp, 20h
0x180002f06  xor     ebx, ebx
0x180002f08  call    cs:__imp_InitializeCriticalSection
0x180002f0e  jmp     short loc_180002F15
0x180002f10  mov     ebx, 8007000Eh
0x180002f15  mov     eax, ebx
0x180002f17  add     rsp, 20h
0x180002f1b  pop     rbx
0x180002f1c  retn
0x180018456  push    rbp
0x180018458  sub     rsp, 20h
0x18001845c  mov     rbp, rdx
0x18001845f  mov     rax, [rcx]
0x180018462  xor     ecx, ecx
0x180018464  cmp     dword ptr [rax], 0C0000017h
0x18001846a  setz    cl
0x18001846d  mov     eax, ecx
0x18001846f  add     rsp, 20h
0x180018473  pop     rbp
0x180018474  retn
```
