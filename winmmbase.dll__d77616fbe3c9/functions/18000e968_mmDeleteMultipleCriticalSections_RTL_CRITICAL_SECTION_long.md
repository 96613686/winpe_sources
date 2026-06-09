# mmDeleteMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)

- ea: `0x18000e968`
- end: `0x18000e990`
- name: `?mmDeleteMultipleCriticalSections@@YAXPEAPEAU_RTL_CRITICAL_SECTION@@J@Z`
- size: `40`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ddc8`
- `0x18000fc30`

## callees

- `0x18000e968`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e97b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e97b`

## pseudocode

```c
void __fastcall mmDeleteMultipleCriticalSections(struct _RTL_CRITICAL_SECTION **a1)
{
  __int64 i; // rbx

  for ( i = 0; i != 7; ++i )
    DeleteCriticalSection((LPCRITICAL_SECTION)(&acs)[i]);
}

```

## disassembly

```asm
0x18000e968  push    rbx
0x18000e96a  sub     rsp, 20h
0x18000e96e  xor     ebx, ebx
0x18000e970  lea     rcx, ?acs@@3PAPEAU_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION * near * acs
0x18000e977  mov     rcx, [rcx+rbx*8]; lpCriticalSection
0x18000e97b  call    cs:__imp_DeleteCriticalSection
0x18000e981  inc     rbx
0x18000e984  cmp     rbx, 7
0x18000e988  jnz     short loc_18000E970
0x18000e98a  add     rsp, 20h
0x18000e98e  pop     rbx
0x18000e98f  retn
```
