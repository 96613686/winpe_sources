# TextLogEnumerateOpenSections

- ea: `0x18000b890`
- end: `0x18000b8f2`
- name: `TextLogEnumerateOpenSections`
- size: `98`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b360`
- `0x18000b5f0`
- `0x18000b7a0`
- `0x1800167b0`
- `0x180016d08`
- `0x180016d84`
- `0x180017408`

## callees

- `0x18000b890`

## pseudocode

```c
__int64 __fastcall TextLogEnumerateOpenSections(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // r9d
  unsigned __int64 v4; // r10
  unsigned __int64 v5; // rax

  if ( a2 > 0x2710 )
    return 0;
  v3 = 0;
  v4 = 20LL * (a2 + 1);
  if ( v4 > (unsigned int)(*(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16)) )
    return 0;
  v5 = *(_QWORD *)(a1 + 24) - v4;
  if ( *(_DWORD *)v5 == -522186479 )
  {
    *(_OWORD *)a3 = *(_OWORD *)v5;
    *(_DWORD *)(a3 + 16) = *(_DWORD *)(v5 + 16);
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x18000b890  sub     rsp, 18h
0x18000b894  cmp     edx, 2710h
0x18000b89a  ja      short loc_18000B8EE
0x18000b89c  xor     r9d, r9d
0x18000b89f  mov     [rsp+18h+var_18], r9d
0x18000b8a3  lea     eax, [rdx+1]
0x18000b8a6  lea     r10, [rax+rax*4]
0x18000b8aa  shl     r10, 2
0x18000b8ae  mov     eax, [rcx+18h]
0x18000b8b1  sub     eax, [rcx+10h]
0x18000b8b4  cmp     r10, rax
0x18000b8b7  ja      short loc_18000B8EE
0x18000b8b9  mov     rax, [rcx+18h]
0x18000b8bd  sub     rax, r10
0x18000b8c0  cmp     dword ptr [rax], 0E0E01111h
0x18000b8c6  jnz     short loc_18000B8E0
0x18000b8c8  movups  xmm0, xmmword ptr [rax]
0x18000b8cb  movups  xmmword ptr [r8], xmm0
0x18000b8cf  mov     eax, [rax+10h]
0x18000b8d2  mov     [r8+10h], eax
0x18000b8d6  mov     r9d, 1
0x18000b8dc  mov     [rsp+18h+var_18], r9d
0x18000b8e0  jmp     short loc_18000B8E6
0x18000b8e2  mov     r9d, [rsp+18h+var_18]
0x18000b8e6  mov     eax, r9d
0x18000b8e9  add     rsp, 18h
0x18000b8ed  retn
0x18000b8ee  xor     eax, eax
0x18000b8f0  jmp     short loc_18000B8E9
```
