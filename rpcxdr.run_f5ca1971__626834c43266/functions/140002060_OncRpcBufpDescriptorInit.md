# OncRpcBufpDescriptorInit

- ea: `0x140002060`
- end: `0x1400020b8`
- name: `OncRpcBufpDescriptorInit`
- size: `88`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001804`
- `0x140001920`
- `0x140001a2c`
- `0x140001adc`

## callees

- `0x140002060`

## pseudocode

```c
__int64 __fastcall OncRpcBufpDescriptorInit(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int64 result; // rax

  *(_DWORD *)a1 = 1396982354;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 4) = 0;
  *(_WORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = a2;
  *(_QWORD *)(a1 + 32) = a1 + 24;
  *(_QWORD *)(a1 + 24) = a1 + 24;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  if ( a3 )
    result = *a3;
  else
    result = 4;
  *(_DWORD *)(a1 + 84) = result;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  return result;
}

```

## disassembly

```asm
0x140002060  xor     r9d, r9d
0x140002063  mov     dword ptr [rcx], 53444252h
0x140002069  mov     [rcx+10h], r9
0x14000206d  lea     rax, [rcx+18h]
0x140002071  mov     [rcx+4], r9d
0x140002075  mov     [rcx+8], r9w
0x14000207a  mov     [rcx+10h], rdx
0x14000207e  mov     [rax+8], rax
0x140002082  mov     [rax], rax
0x140002085  mov     [rcx+28h], r9
0x140002089  mov     [rcx+30h], r9
0x14000208d  mov     [rcx+38h], r9
0x140002091  mov     [rcx+40h], r9
0x140002095  mov     [rcx+48h], r9
0x140002099  mov     [rcx+50h], r9d
0x14000209d  mov     [rcx+58h], r9
0x1400020a1  test    r8, r8
0x1400020a4  jz      short loc_1400020AB
0x1400020a6  mov     eax, [r8]
0x1400020a9  jmp     short loc_1400020B0
0x1400020ab  mov     eax, 4
0x1400020b0  mov     [rcx+54h], eax
0x1400020b3  lock inc dword ptr [rcx+4]
0x1400020b7  retn
```
