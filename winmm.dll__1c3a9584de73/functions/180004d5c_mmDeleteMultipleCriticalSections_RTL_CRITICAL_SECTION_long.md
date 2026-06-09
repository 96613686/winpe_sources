# mmDeleteMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)

- ea: `0x180004d5c`
- end: `0x180004d84`
- name: `?mmDeleteMultipleCriticalSections@@YAXPEAPEAU_RTL_CRITICAL_SECTION@@J@Z`
- size: `40`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004774`
- `0x180004940`

## callees

- `0x180004d5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004d6f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004d6f`

## pseudocode

```c
void __fastcall mmDeleteMultipleCriticalSections(struct _RTL_CRITICAL_SECTION **a1)
{
  __int64 i; // rbx

  for ( i = 0; i != 6; ++i )
    DeleteCriticalSection((LPCRITICAL_SECTION)(&acs)[i]);
}

```

## disassembly

```asm
0x180004d5c  push    rbx
0x180004d5e  sub     rsp, 20h
0x180004d62  xor     ebx, ebx
0x180004d64  lea     rcx, ?acs@@3PAPEAU_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION * near * acs
0x180004d6b  mov     rcx, [rcx+rbx*8]; lpCriticalSection
0x180004d6f  call    cs:__imp_DeleteCriticalSection
0x180004d75  inc     rbx
0x180004d78  cmp     rbx, 6
0x180004d7c  jnz     short loc_180004D64
0x180004d7e  add     rsp, 20h
0x180004d82  pop     rbx
0x180004d83  retn
```
