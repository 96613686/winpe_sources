# InstanceInitializeResourceDescriptor

- ea: `0x140029844`
- end: `0x1400298e5`
- name: `InstanceInitializeResourceDescriptor`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140029390`

## callees

- `0x140029844`

## pseudocode

```c
__int64 __fastcall InstanceInitializeResourceDescriptor(__int64 a1, char a2, unsigned __int64 a3)
{
  __int64 result; // rax
  __int64 v4; // rdx

  *(_DWORD *)(a1 + 2) = 1;
  *(_WORD *)(a1 + 6) = 0;
  *(_BYTE *)a1 = a2;
  if ( a3 >= 0x100000000LL )
  {
    result = 0x1000000000000LL;
    *(_BYTE *)(a1 + 1) = 7;
    v4 = -1;
    *(_QWORD *)(a1 + 16) = 0;
    if ( a3 >= 0x1000000000000LL )
    {
      result = 0xFFFFFFFFLL;
      *(_WORD *)(a1 + 4) = 2048;
      *(_DWORD *)(a1 + 12) = 1;
      a3 = (a3 + 0xFFFFFFFF) >> 32;
    }
    else
    {
      *(_WORD *)(a1 + 4) = 1024;
      a3 = (a3 + 0xFFFF) >> 16;
      *(_DWORD *)(a1 + 12) = 16;
    }
  }
  else
  {
    result = -1;
    *(_DWORD *)(a1 + 12) = 0x100000;
    *(_QWORD *)(a1 + 16) = 0;
    v4 = 0xFFFFFFFFFLL;
    *(_BYTE *)(a1 + 1) = 3;
    if ( (unsigned int)a3 > 0x10000000 )
      v4 = -1;
  }
  *(_DWORD *)(a1 + 8) = a3;
  *(_QWORD *)(a1 + 24) = v4;
  return result;
}

```

## disassembly

```asm
0x140029844  xor     r9d, r9d
0x140029847  mov     dword ptr [rcx+2], 1
0x14002984e  mov     rax, 100000000h
0x140029858  mov     [rcx+6], r9w
0x14002985d  mov     [rcx], dl
0x14002985f  cmp     r8, rax
0x140029862  jnb     short loc_14002988E
0x140029864  or      rax, 0FFFFFFFFFFFFFFFFh
0x140029868  mov     dword ptr [rcx+0Ch], 100000h
0x14002986f  cmp     r8d, 10000000h
0x140029876  mov     [rcx+10h], r9
0x14002987a  mov     rdx, 0FFFFFFFFFh
0x140029884  mov     byte ptr [rcx+1], 3
0x140029888  cmova   rdx, rax
0x14002988c  jmp     short loc_1400298DC
0x14002988e  mov     rax, 1000000000000h
0x140029898  mov     byte ptr [rcx+1], 7
0x14002989c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400298a0  mov     [rcx+10h], r9
0x1400298a4  cmp     r8, rax
0x1400298a7  jnb     short loc_1400298C3
0x1400298a9  add     r8, 0FFFFh
0x1400298b0  mov     word ptr [rcx+4], 400h
0x1400298b6  shr     r8, 10h
0x1400298ba  mov     dword ptr [rcx+0Ch], 10h
0x1400298c1  jmp     short loc_1400298DC
0x1400298c3  mov     eax, 0FFFFFFFFh
0x1400298c8  mov     word ptr [rcx+4], 800h
0x1400298ce  add     r8, rax
0x1400298d1  mov     dword ptr [rcx+0Ch], 1
0x1400298d8  shr     r8, 20h
0x1400298dc  mov     [rcx+8], r8d
0x1400298e0  mov     [rcx+18h], rdx
0x1400298e4  retn
```
