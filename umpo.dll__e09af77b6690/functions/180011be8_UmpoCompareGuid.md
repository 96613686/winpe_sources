# UmpoCompareGuid

- ea: `0x180011be8`
- end: `0x180011c14`
- name: `UmpoCompareGuid`
- size: `44`
- prototype: `_BOOL8 __fastcall(const void *, const void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800121ac`

## callees

- `0x180011be8`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180011bfe`
- `ntdll!RtlCompareMemory` at `0x180011bfe`

## pseudocode

```c
_BOOL8 __fastcall UmpoCompareGuid(const void *a1, const void *a2)
{
  return a1 == a2 || RtlCompareMemory(a1, a2, 0x10u) == 16;
}

```

## disassembly

```asm
0x180011be8  sub     rsp, 28h
0x180011bec  cmp     rcx, rdx
0x180011bef  jnz     short loc_180011BF8
0x180011bf1  mov     eax, 1
0x180011bf6  jmp     short loc_180011C0F
0x180011bf8  mov     r8d, 10h; Length
0x180011bfe  call    cs:__imp_RtlCompareMemory
0x180011c04  xor     ecx, ecx
0x180011c06  cmp     rax, 10h
0x180011c0a  setz    cl
0x180011c0d  mov     eax, ecx
0x180011c0f  add     rsp, 28h
0x180011c13  retn
```
