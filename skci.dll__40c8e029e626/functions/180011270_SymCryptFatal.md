# SymCryptFatal

- ea: `0x180011270`
- end: `0x180011297`
- name: `SymCryptFatal`
- size: `39`
- prototype: `void __fastcall __noreturn(ULONG_PTR BugCheckParameter1)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180013b9c`
- `0x180013da8`
- `0x1800144c0`
- `0x180022c74`
- `0x180028174`
- `0x1800282c0`
- `0x180028464`
- `0x18002859c`
- `0x18002b8e0`

## import_xrefs

- `securekernel!KeBugCheckEx` at `0x18001128a`
- `securekernel!KeBugCheckEx` at `0x18001128a`

## pseudocode

```c
void __fastcall __noreturn SymCryptFatal(ULONG_PTR BugCheckParameter1)
{
  KeBugCheckEx(0x171u, (unsigned int)BugCheckParameter1, 0, 0, 0);
}

```

## disassembly

```asm
0x180011270  sub     rsp, 38h
0x180011274  mov     edx, ecx; BugCheckParameter1
0x180011276  xor     r9d, r9d; BugCheckParameter3
0x180011279  mov     ecx, 171h; BugCheckCode
0x18001127e  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x180011287  xor     r8d, r8d; BugCheckParameter2
0x18001128a  call    cs:__imp_KeBugCheckEx
```
