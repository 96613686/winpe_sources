# UdfInitializeCompoundDirContext

- ea: `0x14000a288`
- end: `0x14000a2e2`
- name: `UdfInitializeCompoundDirContext`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014cb8`
- `0x1400177ac`
- `0x14003269c`
- `0x140033548`
- `0x140034450`
- `0x14003f4c8`

## callees

- `0x14001c080`
- `0x140059090`

## pseudocode

```c
__int64 __fastcall UdfInitializeCompoundDirContext(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  UdfInitializeDirContext(a1, a2);
  memset((void *)(a2 + 152), 0, 0x60u);
  result = a2 + 288;
  *(_OWORD *)(a2 + 248) = 0;
  *(_OWORD *)(a2 + 264) = 0;
  *(_QWORD *)(a2 + 280) = 0;
  *(_QWORD *)(a2 + 128) = a2 + 288;
  *(_WORD *)(a2 + 136) = 104;
  return result;
}

```

## disassembly

```asm
0x14000a288  push    rbx
0x14000a28a  sub     rsp, 20h
0x14000a28e  mov     rbx, rdx
0x14000a291  call    UdfInitializeDirContext
0x14000a296  xor     edx, edx; Val
0x14000a298  lea     rcx, [rbx+98h]; void *
0x14000a29f  lea     r8d, [rdx+60h]; Size
0x14000a2a3  call    memset
0x14000a2a8  xorps   xmm0, xmm0
0x14000a2ab  lea     rax, [rbx+120h]
0x14000a2b2  movups  xmmword ptr [rbx+0F8h], xmm0
0x14000a2b9  movups  xmmword ptr [rbx+108h], xmm0
0x14000a2c0  mov     qword ptr [rbx+118h], 0
0x14000a2cb  mov     [rbx+80h], rax
0x14000a2d2  mov     word ptr [rbx+88h], 68h ; 'h'
0x14000a2db  add     rsp, 20h
0x14000a2df  pop     rbx
0x14000a2e0  retn
```
