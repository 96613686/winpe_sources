# RtlStringCchLengthW

- ea: `0x14001b8f0`
- end: `0x14001b923`
- name: `RtlStringCchLengthW`
- size: `51`
- prototype: `NTSTATUS __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001b33c`
- `0x14001c728`
- `0x14001c8a4`

## callees

- `0x14001b8f0`
- `0x14001b984`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  NTSTATUS result; // eax

  if ( psz && cchMax <= 0x7FFFFFFF )
  {
    result = RtlStringLengthWorkerW(psz, cchMax, pcchLength);
    if ( result >= 0 )
      return result;
  }
  else
  {
    result = -1073741811;
  }
  if ( pcchLength )
    *pcchLength = 0;
  return result;
}

```

## disassembly

```asm
0x14001b8f0  sub     rsp, 28h
0x14001b8f4  test    rcx, rcx
0x14001b8f7  jz      short loc_14001B90D
0x14001b8f9  cmp     rdx, 7FFFFFFFh
0x14001b900  ja      short loc_14001B90D
0x14001b902  call    RtlStringLengthWorkerW
0x14001b907  test    eax, eax
0x14001b909  jns     short loc_14001B91E
0x14001b90b  jmp     short loc_14001B912
0x14001b90d  mov     eax, 0C000000Dh
0x14001b912  test    r8, r8
0x14001b915  jz      short loc_14001B91E
0x14001b917  mov     qword ptr [r8], 0
0x14001b91e  add     rsp, 28h
0x14001b922  retn
```
