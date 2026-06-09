# ServerHandshakeProcessor::VerifyProtocolValue(char const *,ulong,void *)

- ea: `0x180009a50`
- end: `0x180009a8f`
- name: `?VerifyProtocolValue@ServerHandshakeProcessor@@CAJPEBDKPEAX@Z`
- size: `63`
- prototype: `__int64 __fastcall(char *, unsigned int, ListVerifier *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002578`
- `0x180009a50`
- `0x18000b4f4`

## pseudocode

```c
__int64 __fastcall ServerHandshakeProcessor::VerifyProtocolValue(char *a1, unsigned int a2, ListVerifier *this)
{
  int v3; // eax
  unsigned int v4; // ebx

  v3 = ListVerifier::VerifyValue(this, a1, a2, 1, 0);
  v4 = v3;
  if ( v3 < 0 )
    Trace::Error(v3, 0xD0000010);
  return v4;
}

```

## disassembly

```asm
0x180009a50  push    rbx
0x180009a52  sub     rsp, 30h
0x180009a56  mov     rax, r8
0x180009a59  mov     [rsp+38h+var_18], 0; unsigned int
0x180009a61  mov     r8d, edx; unsigned int
0x180009a64  mov     r9d, 1; unsigned int
0x180009a6a  mov     rdx, rcx; char *
0x180009a6d  mov     rcx, rax; this
0x180009a70  call    ?VerifyValue@ListVerifier@@QEAAJPEBDKKK@Z; ListVerifier::VerifyValue(char const *,ulong,ulong,ulong)
0x180009a75  mov     ebx, eax
0x180009a77  test    eax, eax
0x180009a79  jns     short loc_180009A87
0x180009a7b  mov     edx, 0D0000010h; unsigned int
0x180009a80  mov     ecx, eax; int
0x180009a82  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x180009a87  mov     eax, ebx
0x180009a89  add     rsp, 30h
0x180009a8d  pop     rbx
0x180009a8e  retn
```
