# CList<CMulticastSessionGroup,CNoLock>::DeleteAt(void * &)

- ea: `0x180004f58`
- end: `0x180004ff0`
- name: `?DeleteAt@?$CList@VCMulticastSessionGroup@@VCNoLock@@@@QEAAPEAVCMulticastSessionGroup@@AEAPEAX@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000433c`
- `0x180004438`

## callees

- `0x180004f58`

## pseudocode

```c
__int64 __fastcall CList<CMulticastSessionGroup,CNoLock>::DeleteAt(__int64 *a1, __int64 *a2)
{
  __int64 v2; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx

  v2 = *a2;
  if ( *a2 )
  {
    v5 = *a1;
    v6 = a1[1];
    if ( v5 == v6 )
    {
      a1[1] = 0;
      *a1 = 0;
    }
    else
    {
      if ( v2 == v5 )
      {
        v7 = *(_QWORD *)(v5 + 320);
        *a1 = v7;
        *(_QWORD *)(v7 + 328) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 5);
        return v2;
      }
      if ( v2 != v6 )
      {
        v9 = *(_QWORD *)(v2 + 320);
        v10 = *(_QWORD *)(v2 + 328);
        *a2 = v9;
        *(_QWORD *)(v10 + 320) = v9;
        *(_QWORD *)(*(_QWORD *)(v2 + 320) + 328LL) = *(_QWORD *)(v2 + 328);
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v6 + 328);
      a1[1] = v8;
      *(_QWORD *)(v8 + 320) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x180004f58  mov     r9, [rdx]
0x180004f5b  mov     r10, rdx
0x180004f5e  xor     edx, edx
0x180004f60  mov     r8, rcx
0x180004f63  test    r9, r9
0x180004f66  jz      loc_180004FEC
0x180004f6c  mov     rax, [rcx]
0x180004f6f  mov     rcx, [rcx+8]
0x180004f73  cmp     rax, rcx
0x180004f76  jnz     short loc_180004F81
0x180004f78  mov     [r8+8], rdx
0x180004f7c  mov     [r8], rdx
0x180004f7f  jmp     short loc_180004FB6
0x180004f81  cmp     r9, rax
0x180004f84  jnz     short loc_180004F9F
0x180004f86  mov     rax, [rax+140h]
0x180004f8d  mov     [r8], rax
0x180004f90  mov     [rax+148h], rdx
0x180004f97  mov     rax, [r8]
0x180004f9a  mov     [r10], rax
0x180004f9d  jmp     short loc_180004FE8
0x180004f9f  cmp     r9, rcx
0x180004fa2  jnz     short loc_180004FBB
0x180004fa4  mov     rax, [rcx+148h]
0x180004fab  mov     [r8+8], rax
0x180004faf  mov     [rax+140h], rdx
0x180004fb6  mov     [r10], rdx
0x180004fb9  jmp     short loc_180004FE8
0x180004fbb  mov     rdx, [r9+140h]
0x180004fc2  mov     rcx, [r9+148h]
0x180004fc9  mov     [r10], rdx
0x180004fcc  mov     [rcx+140h], rdx
0x180004fd3  mov     rdx, [r9+140h]
0x180004fda  mov     rcx, [r9+148h]
0x180004fe1  mov     [rdx+148h], rcx
0x180004fe8  dec     dword ptr [r8+14h]
0x180004fec  mov     rax, r9
0x180004fef  retn
```
