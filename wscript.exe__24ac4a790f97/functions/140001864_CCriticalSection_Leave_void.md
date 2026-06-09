# CCriticalSection::Leave(void)

- ea: `0x140001864`
- end: `0x140001889`
- name: `?Leave@CCriticalSection@@QEAAXXZ`
- size: `37`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400019f0`
- `0x140001b40`
- `0x140001bd0`
- `0x140002310`
- `0x140002bd0`
- `0x140002cd0`
- `0x140007b3c`

## callees

- `0x140001864`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140001873`
- `KERNEL32!LeaveCriticalSection` at `0x140001873`

## pseudocode

```c
void __fastcall CCriticalSection::Leave(struct _RTL_CRITICAL_SECTION *this)
{
  if ( !LOBYTE(this[1].DebugInfo) )
    LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x140001864  mov     [rsp+arg_0], rcx
0x140001869  sub     rsp, 28h
0x14000186d  cmp     byte ptr [rcx+28h], 0
0x140001871  jnz     short loc_140001884
0x140001873  call    cs:__imp_LeaveCriticalSection
0x140001879  jmp     short loc_140001884
0x14000187b  mov     rax, [rsp+28h+arg_0]
0x140001880  mov     byte ptr [rax+28h], 1
0x140001884  add     rsp, 28h
0x140001888  retn
```
