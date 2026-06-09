# CCriticalSection::Destroy(void)

- ea: `0x18000b418`
- end: `0x18000b441`
- name: `?Destroy@CCriticalSection@@QEAAXXZ`
- size: `41`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b34c`
- `0x18000b3b4`
- `0x18000cfa0`

## callees

- `0x18000b418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b427`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b427`

## pseudocode

```c
void __fastcall CCriticalSection::Destroy(struct _RTL_CRITICAL_SECTION *this)
{
  if ( LODWORD(this[1].DebugInfo) == 1 )
  {
    DeleteCriticalSection(this);
    LODWORD(this[1].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x18000b418  push    rbx
0x18000b41a  sub     rsp, 20h
0x18000b41e  cmp     dword ptr [rcx+28h], 1
0x18000b422  mov     rbx, rcx
0x18000b425  jnz     short loc_18000B43A
0x18000b427  call    cs:__imp_DeleteCriticalSection
0x18000b42e  nop     dword ptr [rax+rax+00h]
0x18000b433  mov     dword ptr [rbx+28h], 0
0x18000b43a  add     rsp, 20h
0x18000b43e  pop     rbx
0x18000b43f  retn
```
