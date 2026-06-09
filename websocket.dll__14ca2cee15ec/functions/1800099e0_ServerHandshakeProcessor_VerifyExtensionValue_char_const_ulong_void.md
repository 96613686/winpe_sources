# ServerHandshakeProcessor::VerifyExtensionValue(char const *,ulong,void *)

- ea: `0x1800099e0`
- end: `0x180009a3d`
- name: `?VerifyExtensionValue@ServerHandshakeProcessor@@CAJPEBDKPEAX@Z`
- size: `93`
- prototype: `__int64 __fastcall(char *, unsigned int, char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002578`
- `0x1800099e0`
- `0x18000b394`
- `0x18000b4f4`

## pseudocode

```c
__int64 __fastcall ServerHandshakeProcessor::VerifyExtensionValue(char *a1, unsigned int a2, char *a3)
{
  int v6; // eax
  unsigned int v7; // ebx

  Sqm::OnExtensionRequested(a1, a2);
  v6 = ListVerifier::VerifyValue((ListVerifier *)(a3 + 32), a1, a2, 3, 2);
  v7 = v6;
  if ( v6 < 0 )
    Trace::Error(v6, 0xD0000011);
  return v7;
}

```

## disassembly

```asm
0x1800099e0  mov     [rsp+arg_0], rbx
0x1800099e5  mov     [rsp+arg_8], rsi
0x1800099ea  push    rdi
0x1800099eb  sub     rsp, 30h
0x1800099ef  mov     rbx, r8
0x1800099f2  mov     edi, edx
0x1800099f4  mov     rsi, rcx
0x1800099f7  call    ?OnExtensionRequested@Sqm@@SAXPEBDK@Z; Sqm::OnExtensionRequested(char const *,ulong)
0x1800099fc  lea     rcx, [rbx+20h]; this
0x180009a00  mov     [rsp+38h+var_18], 2; unsigned int
0x180009a08  mov     r9d, 3; unsigned int
0x180009a0e  mov     r8d, edi; unsigned int
0x180009a11  mov     rdx, rsi; char *
0x180009a14  call    ?VerifyValue@ListVerifier@@QEAAJPEBDKKK@Z; ListVerifier::VerifyValue(char const *,ulong,ulong,ulong)
0x180009a19  mov     ebx, eax
0x180009a1b  test    eax, eax
0x180009a1d  jns     short loc_180009A2B
0x180009a1f  mov     edx, 0D0000011h; unsigned int
0x180009a24  mov     ecx, eax; int
0x180009a26  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x180009a2b  mov     rsi, [rsp+38h+arg_8]
0x180009a30  mov     eax, ebx
0x180009a32  mov     rbx, [rsp+38h+arg_0]
0x180009a37  add     rsp, 30h
0x180009a3b  pop     rdi
0x180009a3c  retn
```
