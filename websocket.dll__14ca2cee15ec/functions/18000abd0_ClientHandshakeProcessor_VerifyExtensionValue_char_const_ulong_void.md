# ClientHandshakeProcessor::VerifyExtensionValue(char const *,ulong,void *)

- ea: `0x18000abd0`
- end: `0x18000ac0d`
- name: `?VerifyExtensionValue@ClientHandshakeProcessor@@CAJPEBDKPEAX@Z`
- size: `61`
- prototype: `__int64 __fastcall(const char *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002578`
- `0x18000abd0`
- `0x18000b4f4`

## pseudocode

```c
__int64 __fastcall ClientHandshakeProcessor::VerifyExtensionValue(char *a1, unsigned int a2, char *a3)
{
  signed int v3; // eax
  unsigned int v4; // ebx

  v3 = ListVerifier::VerifyValue((ListVerifier *)(a3 + 56), a1, a2, 3, 3);
  v4 = v3;
  if ( v3 < 0 )
    Trace::Error(v3, 0xD0000011);
  return v4;
}

```

## disassembly

```asm
0x18000abd0  push    rbx
0x18000abd2  sub     rsp, 30h
0x18000abd6  mov     rax, rcx
0x18000abd9  mov     r9d, 3; unsigned int
0x18000abdf  lea     rcx, [r8+38h]; this
0x18000abe3  mov     [rsp+38h+var_18], r9d; unsigned int
0x18000abe8  mov     r8d, edx; unsigned int
0x18000abeb  mov     rdx, rax; char *
0x18000abee  call    ?VerifyValue@ListVerifier@@QEAAJPEBDKKK@Z; ListVerifier::VerifyValue(char const *,ulong,ulong,ulong)
0x18000abf3  mov     ebx, eax
0x18000abf5  test    eax, eax
0x18000abf7  jns     short loc_18000AC05
0x18000abf9  mov     edx, 0D0000011h; unsigned int
0x18000abfe  mov     ecx, eax; int
0x18000ac00  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000ac05  mov     eax, ebx
0x18000ac07  add     rsp, 30h
0x18000ac0b  pop     rbx
0x18000ac0c  retn
```
