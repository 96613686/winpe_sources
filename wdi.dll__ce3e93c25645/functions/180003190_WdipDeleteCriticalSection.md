# WdipDeleteCriticalSection

- ea: `0x180003190`
- end: `0x1800031b2`
- name: `WdipDeleteCriticalSection`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003100`

## callees

- `0x180003190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000319f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000319f`

## pseudocode

```c
void __fastcall WdipDeleteCriticalSection(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 40) == 1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)a1);
    *(_DWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x180003190  push    rbx
0x180003192  sub     rsp, 20h
0x180003196  cmp     dword ptr [rcx+28h], 1
0x18000319a  mov     rbx, rcx
0x18000319d  jnz     short loc_1800031AC
0x18000319f  call    cs:__imp_DeleteCriticalSection
0x1800031a5  mov     dword ptr [rbx+28h], 0
0x1800031ac  add     rsp, 20h
0x1800031b0  pop     rbx
0x1800031b1  retn
```
