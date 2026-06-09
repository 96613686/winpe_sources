# WerpAllocateMem

- ea: `0x14000d174`
- end: `0x14000d1c8`
- name: `WerpAllocateMem`
- size: `84`
- prototype: `PVOID __fastcall(int)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c6f0`
- `0x14000d070`
- `0x14000d558`
- `0x14000d68c`
- `0x14000da6c`
- `0x14000eb08`
- `0x14000f640`
- `0x14000f6d8`
- `0x14000f8bc`
- `0x14000fda8`
- `0x1400100f4`
- `0x140012080`
- `0x1400122c0`
- `0x140012588`

## callees

- `0x140002c40`
- `0x14000d174`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d18f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d18f`

## pseudocode

```c
PVOID __fastcall WerpAllocateMem(int a1)
{
  size_t v1; // rdi
  PVOID PoolWithTag; // rax
  PVOID v3; // rbx

  v1 = a1;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, a1, 0x7765726Bu);
  v3 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v1);
  return v3;
}

```

## disassembly

```asm
0x14000d174  mov     [rsp+arg_0], rbx
0x14000d179  push    rdi
0x14000d17a  sub     rsp, 20h
0x14000d17e  movsxd  rdi, ecx
0x14000d181  mov     r8d, 7765726Bh; Tag
0x14000d187  mov     rdx, rdi; NumberOfBytes
0x14000d18a  mov     ecx, 401h; PoolType
0x14000d18f  call    cs:__imp_ExAllocatePoolWithTag
0x14000d196  nop     dword ptr [rax+rax+00h]
0x14000d19b  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000d1a2  mov     rbx, rax
0x14000d1a5  jnz     short loc_14000D1B9
0x14000d1a7  test    rax, rax
0x14000d1aa  jz      short loc_14000D1B9
0x14000d1ac  mov     r8, rdi; Size
0x14000d1af  xor     edx, edx; Val
0x14000d1b1  mov     rcx, rax; void *
0x14000d1b4  call    memset
0x14000d1b9  mov     rax, rbx
0x14000d1bc  mov     rbx, [rsp+28h+arg_0]
0x14000d1c1  add     rsp, 20h
0x14000d1c5  pop     rdi
0x14000d1c6  retn
```
