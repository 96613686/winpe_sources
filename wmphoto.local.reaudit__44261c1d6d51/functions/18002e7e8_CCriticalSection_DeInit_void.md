# CCriticalSection::DeInit(void)

- ea: `0x18002e7e8`
- end: `0x18002e80e`
- name: `?DeInit@CCriticalSection@@QEAAXXZ`
- size: `38`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18002e20c`
- `0x18002e2fc`
- `0x18002e5ac`
- `0x18002e5c8`
- `0x18002f510`
- `0x18003b890`
- `0x18003e550`
- `0x180044460`

## callees

- `0x18002e7e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e7f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e7f7`

## pseudocode

```c
void __fastcall CCriticalSection::DeInit(struct _RTL_CRITICAL_SECTION *this)
{
  if ( LOBYTE(this[1].DebugInfo) )
  {
    DeleteCriticalSection(this);
    LOBYTE(this[1].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x18002e7e8  push    rbx
0x18002e7ea  sub     rsp, 20h
0x18002e7ee  cmp     byte ptr [rcx+28h], 0
0x18002e7f2  mov     rbx, rcx
0x18002e7f5  jz      short loc_18002E807
0x18002e7f7  call    cs:__imp_DeleteCriticalSection
0x18002e7fe  nop     dword ptr [rax+rax+00h]
0x18002e803  mov     byte ptr [rbx+28h], 0
0x18002e807  add     rsp, 20h
0x18002e80b  pop     rbx
0x18002e80c  retn
```
