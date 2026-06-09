# utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)

- ea: `0x180013ef0`
- end: `0x180013f08`
- name: `??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001405c`
- `0x18001439c`
- `0x18001447c`
- `0x1800145bc`
- `0x180014740`
- `0x180017438`
- `0x18001744a`

## callees

- `0x180013ef0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180013efd`
- `KERNEL32!LeaveCriticalSection` at `0x180013efd`

## pseudocode

```c
void __fastcall utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
}

```

## disassembly

```asm
0x180013ef0  sub     rsp, 28h
0x180013ef4  cmp     byte ptr [rcx+8], 0
0x180013ef8  jz      short loc_180013F03
0x180013efa  mov     rcx, [rcx]; lpCriticalSection
0x180013efd  call    cs:__imp_LeaveCriticalSection
0x180013f03  add     rsp, 28h
0x180013f07  retn
```
