# ULongLongToULong(unsigned __int64,ulong *)

- ea: `0x180009540`
- end: `0x18000955e`
- name: `?ULongLongToULong@@YAJ_KPEAK@Z`
- size: `30`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800098e0`
- `0x180009dc0`
- `0x18000bff0`
- `0x18000ed58`

## callees

- `0x180009540`

## pseudocode

```c
__int64 __fastcall ULongLongToULong(unsigned __int64 a1, unsigned int *a2)
{
  unsigned int v2; // r8d

  v2 = a1;
  if ( a1 > 0xFFFFFFFF )
    v2 = -1;
  *a2 = v2;
  return a1 > 0xFFFFFFFF ? 0x80070216 : 0;
}

```

## disassembly

```asm
0x180009540  mov     eax, 0FFFFFFFFh
0x180009545  mov     r8d, ecx
0x180009548  cmp     rcx, rax
0x18000954b  jbe     short loc_180009550
0x18000954d  mov     r8d, eax
0x180009550  cmp     rax, rcx
0x180009553  mov     [rdx], r8d
0x180009556  sbb     eax, eax
0x180009558  and     eax, 80070216h
0x18000955d  retn
```
