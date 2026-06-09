# SymCryptCallbackAlloc

- ea: `0x180022c2c`
- end: `0x180022c6b`
- name: `SymCryptCallbackAlloc`
- size: `63`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180023390`
- `0x180023d70`
- `0x18002497c`
- `0x180024be8`
- `0x180025888`
- `0x180026108`
- `0x18002748c`
- `0x180027f10`
- `0x180028034`
- `0x1800282c0`
- `0x180028464`
- `0x18002859c`
- `0x18002e5c0`
- `0x18002efe8`

## callees

- `0x180022c2c`

## import_xrefs

- `securekernel!SkAllocatePool` at `0x180022c41`
- `securekernel!SkAllocatePool` at `0x180022c41`

## pseudocode

```c
unsigned __int64 __fastcall SymCryptCallbackAlloc(__int64 a1)
{
  unsigned __int64 v1; // rbx
  __int64 Pool; // rax

  v1 = 0;
  Pool = SkAllocatePool(1, a1 + 36, 1919109443);
  if ( Pool )
  {
    v1 = (Pool + 35) & 0xFFFFFFFFFFFFFFE0uLL;
    *(_DWORD *)(v1 - 4) = ((Pool + 35) & 0xFFFFFFE0) - Pool;
  }
  return v1;
}

```

## disassembly

```asm
0x180022c2c  push    rbx
0x180022c2e  sub     rsp, 20h
0x180022c32  lea     rdx, [rcx+24h]
0x180022c36  xor     ebx, ebx
0x180022c38  mov     r8d, 72634943h
0x180022c3e  lea     ecx, [rbx+1]
0x180022c41  call    cs:__imp_SkAllocatePool
0x180022c48  nop     dword ptr [rax+rax+00h]
0x180022c4d  test    rax, rax
0x180022c50  jz      short loc_180022C61
0x180022c52  lea     rbx, [rax+23h]
0x180022c56  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180022c5a  mov     ecx, ebx
0x180022c5c  sub     ecx, eax
0x180022c5e  mov     [rbx-4], ecx
0x180022c61  mov     rax, rbx
0x180022c64  add     rsp, 20h
0x180022c68  pop     rbx
0x180022c69  retn
```
