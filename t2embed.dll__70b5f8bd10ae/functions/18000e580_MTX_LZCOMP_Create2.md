# MTX_LZCOMP_Create2

- ea: `0x18000e580`
- end: `0x18000e5dd`
- name: `MTX_LZCOMP_Create2`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000de70`
- `0x18000e12c`

## callees

- `0x180006400`
- `0x18000e580`

## pseudocode

```c
__int64 __fastcall MTX_LZCOMP_Create2(__int64 a1, int a2)
{
  __int64 result; // rax

  result = MTX_mem_malloc(a1, 152);
  *(_QWORD *)(result + 144) = a1;
  *(_QWORD *)result = 0;
  *(_DWORD *)(result + 64) = a2;
  if ( a2 < 7232 )
    *(_DWORD *)(result + 64) = 7232;
  *(_BYTE *)(result + 8) = 0;
  *(_QWORD *)(result + 120) = 0;
  *(_QWORD *)(result + 112) = 0;
  *(_QWORD *)(result + 136) = 0;
  *(_DWORD *)(result + 128) = 4095;
  return result;
}

```

## disassembly

```asm
0x18000e580  mov     [rsp+arg_0], rbx
0x18000e585  push    rdi
0x18000e586  sub     rsp, 20h
0x18000e58a  mov     edi, edx
0x18000e58c  mov     rbx, rcx
0x18000e58f  mov     edx, 98h
0x18000e594  call    MTX_mem_malloc
0x18000e599  xor     ecx, ecx
0x18000e59b  mov     edx, 1C40h
0x18000e5a0  mov     [rax+90h], rbx
0x18000e5a7  mov     [rax], rcx
0x18000e5aa  mov     [rax+40h], edi
0x18000e5ad  cmp     edi, edx
0x18000e5af  jl      short loc_18000E5D8
0x18000e5b1  mov     rbx, [rsp+28h+arg_0]
0x18000e5b6  mov     [rax+8], cl
0x18000e5b9  mov     [rax+78h], rcx
0x18000e5bd  mov     [rax+70h], rcx
0x18000e5c1  mov     [rax+88h], rcx
0x18000e5c8  mov     dword ptr [rax+80h], 0FFFh
0x18000e5d2  add     rsp, 20h
0x18000e5d6  pop     rdi
0x18000e5d7  retn
0x18000e5d8  mov     [rax+40h], edx
0x18000e5db  jmp     short loc_18000E5B1
```
