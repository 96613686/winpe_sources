# CCriticalSection::Destroy(void)

- ea: `0x18000e2e4`
- end: `0x18000e306`
- name: `?Destroy@CCriticalSection@@QEAAXXZ`
- size: `34`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e1b8`

## callees

- `0x18000e2e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e2f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e2f3`

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
0x18000e2e4  push    rbx
0x18000e2e6  sub     rsp, 20h
0x18000e2ea  cmp     dword ptr [rcx+28h], 1
0x18000e2ee  mov     rbx, rcx
0x18000e2f1  jnz     short loc_18000E300
0x18000e2f3  call    cs:__imp_DeleteCriticalSection
0x18000e2f9  mov     dword ptr [rbx+28h], 0
0x18000e300  add     rsp, 20h
0x18000e304  pop     rbx
0x18000e305  retn
```
