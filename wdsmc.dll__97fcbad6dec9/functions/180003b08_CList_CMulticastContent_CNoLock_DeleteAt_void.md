# CList<CMulticastContent,CNoLock>::DeleteAt(void * &)

- ea: `0x180003b08`
- end: `0x180003ba0`
- name: `?DeleteAt@?$CList@VCMulticastContent@@VCNoLock@@@@QEAAPEAVCMulticastContent@@AEAPEAX@Z`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002810`
- `0x180002c70`
- `0x180003868`

## callees

- `0x180003b08`

## pseudocode

```c
__int64 __fastcall CList<CMulticastContent,CNoLock>::DeleteAt(__int64 *a1, __int64 *a2)
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
        v7 = *(_QWORD *)(v5 + 3080);
        *a1 = v7;
        *(_QWORD *)(v7 + 3088) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 5);
        return v2;
      }
      if ( v2 != v6 )
      {
        v9 = *(_QWORD *)(v2 + 3080);
        v10 = *(_QWORD *)(v2 + 3088);
        *a2 = v9;
        *(_QWORD *)(v10 + 3080) = v9;
        *(_QWORD *)(*(_QWORD *)(v2 + 3080) + 3088LL) = *(_QWORD *)(v2 + 3088);
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v6 + 3088);
      a1[1] = v8;
      *(_QWORD *)(v8 + 3080) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x180003b08  mov     r9, [rdx]
0x180003b0b  mov     r10, rdx
0x180003b0e  xor     edx, edx
0x180003b10  mov     r8, rcx
0x180003b13  test    r9, r9
0x180003b16  jz      loc_180003B9C
0x180003b1c  mov     rax, [rcx]
0x180003b1f  mov     rcx, [rcx+8]
0x180003b23  cmp     rax, rcx
0x180003b26  jnz     short loc_180003B31
0x180003b28  mov     [r8+8], rdx
0x180003b2c  mov     [r8], rdx
0x180003b2f  jmp     short loc_180003B66
0x180003b31  cmp     r9, rax
0x180003b34  jnz     short loc_180003B4F
0x180003b36  mov     rax, [rax+0C08h]
0x180003b3d  mov     [r8], rax
0x180003b40  mov     [rax+0C10h], rdx
0x180003b47  mov     rax, [r8]
0x180003b4a  mov     [r10], rax
0x180003b4d  jmp     short loc_180003B98
0x180003b4f  cmp     r9, rcx
0x180003b52  jnz     short loc_180003B6B
0x180003b54  mov     rax, [rcx+0C10h]
0x180003b5b  mov     [r8+8], rax
0x180003b5f  mov     [rax+0C08h], rdx
0x180003b66  mov     [r10], rdx
0x180003b69  jmp     short loc_180003B98
0x180003b6b  mov     rdx, [r9+0C08h]
0x180003b72  mov     rcx, [r9+0C10h]
0x180003b79  mov     [r10], rdx
0x180003b7c  mov     [rcx+0C08h], rdx
0x180003b83  mov     rdx, [r9+0C08h]
0x180003b8a  mov     rcx, [r9+0C10h]
0x180003b91  mov     [rdx+0C10h], rcx
0x180003b98  dec     dword ptr [r8+14h]
0x180003b9c  mov     rax, r9
0x180003b9f  retn
```
