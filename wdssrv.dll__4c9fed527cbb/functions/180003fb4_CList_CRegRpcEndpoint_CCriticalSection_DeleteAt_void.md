# CList<CRegRpcEndpoint,CCriticalSection>::DeleteAt(void * &)

- ea: `0x180003fb4`
- end: `0x18000404c`
- name: `?DeleteAt@?$CList@VCRegRpcEndpoint@@VCCriticalSection@@@@QEAAPEAVCRegRpcEndpoint@@AEAPEAX@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e04`
- `0x180005ec0`

## callees

- `0x180003fb4`

## pseudocode

```c
__int64 __fastcall CList<CRegRpcEndpoint,CCriticalSection>::DeleteAt(__int64 *a1, __int64 *a2)
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
        v7 = *(_QWORD *)(v5 + 1824);
        *a1 = v7;
        *(_QWORD *)(v7 + 1832) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 14);
        return v2;
      }
      if ( v2 != v6 )
      {
        v9 = *(_QWORD *)(v2 + 1824);
        v10 = *(_QWORD *)(v2 + 1832);
        *a2 = v9;
        *(_QWORD *)(v10 + 1824) = v9;
        *(_QWORD *)(*(_QWORD *)(v2 + 1824) + 1832LL) = *(_QWORD *)(v2 + 1832);
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v6 + 1832);
      a1[1] = v8;
      *(_QWORD *)(v8 + 1824) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x180003fb4  mov     r9, [rdx]
0x180003fb7  mov     r10, rdx
0x180003fba  xor     edx, edx
0x180003fbc  mov     r8, rcx
0x180003fbf  test    r9, r9
0x180003fc2  jz      loc_180004048
0x180003fc8  mov     rax, [rcx]
0x180003fcb  mov     rcx, [rcx+8]
0x180003fcf  cmp     rax, rcx
0x180003fd2  jnz     short loc_180003FDD
0x180003fd4  mov     [r8+8], rdx
0x180003fd8  mov     [r8], rdx
0x180003fdb  jmp     short loc_180004012
0x180003fdd  cmp     r9, rax
0x180003fe0  jnz     short loc_180003FFB
0x180003fe2  mov     rax, [rax+720h]
0x180003fe9  mov     [r8], rax
0x180003fec  mov     [rax+728h], rdx
0x180003ff3  mov     rax, [r8]
0x180003ff6  mov     [r10], rax
0x180003ff9  jmp     short loc_180004044
0x180003ffb  cmp     r9, rcx
0x180003ffe  jnz     short loc_180004017
0x180004000  mov     rax, [rcx+728h]
0x180004007  mov     [r8+8], rax
0x18000400b  mov     [rax+720h], rdx
0x180004012  mov     [r10], rdx
0x180004015  jmp     short loc_180004044
0x180004017  mov     rdx, [r9+720h]
0x18000401e  mov     rcx, [r9+728h]
0x180004025  mov     [r10], rdx
0x180004028  mov     [rcx+720h], rdx
0x18000402f  mov     rdx, [r9+720h]
0x180004036  mov     rcx, [r9+728h]
0x18000403d  mov     [rdx+728h], rcx
0x180004044  dec     dword ptr [r8+38h]
0x180004048  mov     rax, r9
0x18000404b  retn
```
