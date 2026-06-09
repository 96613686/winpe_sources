# SkAllocatePoolHelper

- ea: `0x180006f10`
- end: `0x180006f72`
- name: `SkAllocatePoolHelper`
- size: `98`
- prototype: `void *__fastcall(__int16, size_t, __int64)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x180010ab0`
- `0x180010f70`
- `0x1800124a0`
- `0x18004421c`
- `0x180044500`
- `0x180044c90`
- `0x180044fe4`
- `0x1800455c8`
- `0x18004640c`
- `0x18004673c`
- `0x18004762c`
- `0x1800479a8`
- `0x180048ae0`
- `0x180048c50`
- `0x180048d3c`
- `0x18004a128`
- `0x18004b63c`

## callees

- `0x180006f10`
- `0x180033950`

## import_xrefs

- `securekernel!SkAllocatePool` at `0x180006f37`
- `securekernel!SkAllocatePool` at `0x180006f37`

## pseudocode

```c
void *__fastcall SkAllocatePoolHelper(__int16 a1, size_t a2, __int64 a3)
{
  __int64 v4; // rcx
  void *result; // rax
  void *v7; // rbx

  v4 = 512;
  if ( (a1 & 0x100) != 0 )
    v4 = 1;
  result = (void *)SkAllocatePool(v4, a2, a3);
  v7 = result;
  if ( result )
  {
    if ( (a1 & 2) == 0 )
    {
      memset_0(result, 0, a2);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006f10  mov     [rsp+arg_0], rbx
0x180006f15  mov     [rsp+arg_8], rsi
0x180006f1a  push    rdi
0x180006f1b  sub     rsp, 20h
0x180006f1f  mov     rdi, rcx
0x180006f22  mov     eax, 1
0x180006f27  mov     ecx, 200h
0x180006f2c  bt      rdi, 8
0x180006f31  mov     rsi, rdx
0x180006f34  cmovb   ecx, eax
0x180006f37  call    cs:__imp_SkAllocatePool
0x180006f3e  nop     dword ptr [rax+rax+00h]
0x180006f43  mov     rbx, rax
0x180006f46  test    rax, rax
0x180006f49  jz      short loc_180006F61
0x180006f4b  test    dil, 2
0x180006f4f  jnz     short loc_180006F61
0x180006f51  mov     r8, rsi; Size
0x180006f54  xor     edx, edx; Val
0x180006f56  mov     rcx, rax; void *
0x180006f59  call    memset_0
0x180006f5e  mov     rax, rbx
0x180006f61  mov     rbx, [rsp+28h+arg_0]
0x180006f66  mov     rsi, [rsp+28h+arg_8]
0x180006f6b  add     rsp, 20h
0x180006f6f  pop     rdi
0x180006f70  retn
```
