# ClientHandshakeProcessor::VerifyProtocolValue(char const *,ulong,void *)

- ea: `0x18000ac20`
- end: `0x18000ac5d`
- name: `?VerifyProtocolValue@ClientHandshakeProcessor@@CAJPEBDKPEAX@Z`
- size: `61`
- prototype: `__int64 __fastcall(const char *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002578`
- `0x18000ac20`
- `0x18000b4f4`

## pseudocode

```c
__int64 __fastcall ClientHandshakeProcessor::VerifyProtocolValue(char *a1, unsigned int a2, char *a3)
{
  signed int v3; // eax
  unsigned int v4; // ebx

  v3 = ListVerifier::VerifyValue((ListVerifier *)(a3 + 24), a1, a2, 1, 1);
  v4 = v3;
  if ( v3 < 0 )
    Trace::Error(v3, 0xD0000010);
  return v4;
}

```

## disassembly

```asm
0x18000ac20  push    rbx
0x18000ac22  sub     rsp, 30h
0x18000ac26  mov     rax, rcx
0x18000ac29  mov     r9d, 1; unsigned int
0x18000ac2f  lea     rcx, [r8+18h]; this
0x18000ac33  mov     [rsp+38h+var_18], r9d; unsigned int
0x18000ac38  mov     r8d, edx; unsigned int
0x18000ac3b  mov     rdx, rax; char *
0x18000ac3e  call    ?VerifyValue@ListVerifier@@QEAAJPEBDKKK@Z; ListVerifier::VerifyValue(char const *,ulong,ulong,ulong)
0x18000ac43  mov     ebx, eax
0x18000ac45  test    eax, eax
0x18000ac47  jns     short loc_18000AC55
0x18000ac49  mov     edx, 0D0000010h; unsigned int
0x18000ac4e  mov     ecx, eax; int
0x18000ac50  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000ac55  mov     eax, ebx
0x18000ac57  add     rsp, 30h
0x18000ac5b  pop     rbx
0x18000ac5c  retn
```
