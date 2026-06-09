# MUTX::~MUTX(void)

- ea: `0x1800428c4`
- end: `0x1800428e0`
- name: `??1MUTX@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(MUTX *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800140e4`
- `0x18003e024`
- `0x18004289c`
- `0x180051d7c`
- `0x180066c20`

## callees

- `0x1800428c4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800428ce`
- `KERNEL32!DeleteCriticalSection` at `0x1800428ce`

## pseudocode

```c
void __fastcall MUTX::~MUTX(struct _RTL_CRITICAL_SECTION *this)
{
  if ( BYTE1(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800428c4  sub     rsp, 28h
0x1800428c8  cmp     byte ptr [rcx+29h], 0
0x1800428cc  jz      short loc_1800428DA
0x1800428ce  call    cs:__imp_DeleteCriticalSection
0x1800428d5  nop     dword ptr [rax+rax+00h]
0x1800428da  add     rsp, 28h
0x1800428de  retn
```
