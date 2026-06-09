# CSpClassFactory::DetachProduct(CSpClassFactoryProduct *)

- ea: `0x18000b670`
- end: `0x18000b6d2`
- name: `?DetachProduct@CSpClassFactory@@IEAAJPEAVCSpClassFactoryProduct@@@Z`
- size: `98`
- prototype: `__int64 __fastcall(CSpClassFactory *__hidden this, struct CSpClassFactoryProduct *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800092d0`
- `0x180009344`
- `0x180009670`
- `0x18000e06c`

## callees

- `0x18000b670`

## pseudocode

```c
__int64 __fastcall CSpClassFactory::DetachProduct(CSpClassFactory *this, struct CSpClassFactoryProduct *a2)
{
  __int64 *v2; // r8
  __int64 v3; // r10
  unsigned int v4; // r9d
  _QWORD *v5; // r10

  if ( a2 && *((CSpClassFactory **)a2 + 1) == this && (v2 = (__int64 *)*((_QWORD *)a2 + 2)) != 0 )
  {
    v3 = *v2;
    v4 = 0;
    if ( v2 == *((__int64 **)this + 1) )
      *((_QWORD *)this + 1) = v3;
    else
      *(_QWORD *)v2[1] = v3;
    v5 = (_QWORD *)v2[1];
    if ( v2 == *((__int64 **)this + 2) )
      *((_QWORD *)this + 2) = v5;
    else
      *(_QWORD *)(*v2 + 8) = v5;
    *v2 = *((_QWORD *)this + 4);
    --*((_DWORD *)this + 6);
    *((_QWORD *)this + 4) = v2;
    *((_QWORD *)a2 + 2) = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18000b670  test    rdx, rdx
0x18000b673  jz      short loc_18000B6C8
0x18000b675  cmp     [rdx+8], rcx
0x18000b679  jnz     short loc_18000B6C8
0x18000b67b  mov     r8, [rdx+10h]
0x18000b67f  test    r8, r8
0x18000b682  jz      short loc_18000B6C8
0x18000b684  mov     r10, [r8]
0x18000b687  xor     r9d, r9d
0x18000b68a  cmp     r8, [rcx+8]
0x18000b68e  jnz     short loc_18000B696
0x18000b690  mov     [rcx+8], r10
0x18000b694  jmp     short loc_18000B69D
0x18000b696  mov     rax, [r8+8]
0x18000b69a  mov     [rax], r10
0x18000b69d  mov     r10, [r8+8]
0x18000b6a1  cmp     r8, [rcx+10h]
0x18000b6a5  jnz     short loc_18000B6AD
0x18000b6a7  mov     [rcx+10h], r10
0x18000b6ab  jmp     short loc_18000B6B4
0x18000b6ad  mov     rax, [r8]
0x18000b6b0  mov     [rax+8], r10
0x18000b6b4  mov     rax, [rcx+20h]
0x18000b6b8  mov     [r8], rax
0x18000b6bb  dec     dword ptr [rcx+18h]
0x18000b6be  mov     [rcx+20h], r8
0x18000b6c2  mov     [rdx+10h], r9
0x18000b6c6  jmp     short loc_18000B6CE
0x18000b6c8  mov     r9d, 80070057h
0x18000b6ce  mov     eax, r9d
0x18000b6d1  retn
```
