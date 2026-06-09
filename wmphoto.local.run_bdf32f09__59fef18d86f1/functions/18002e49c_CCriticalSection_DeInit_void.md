# CCriticalSection::DeInit(void)

- ea: `0x18002e49c`
- end: `0x18002e4bb`
- name: `?DeInit@CCriticalSection@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18002deec`
- `0x18002dfdc`
- `0x18002e27c`
- `0x18002e298`
- `0x18002f310`
- `0x18003b0d4`
- `0x18003ddd0`

## callees

- `0x18002e49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e4ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e4ab`

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
0x18002e49c  push    rbx
0x18002e49e  sub     rsp, 20h
0x18002e4a2  cmp     byte ptr [rcx+28h], 0
0x18002e4a6  mov     rbx, rcx
0x18002e4a9  jz      short loc_18002E4B5
0x18002e4ab  call    cs:__imp_DeleteCriticalSection
0x18002e4b1  mov     byte ptr [rbx+28h], 0
0x18002e4b5  add     rsp, 20h
0x18002e4b9  pop     rbx
0x18002e4ba  retn
```
