# CList<CMulticastNamespace,CNoLock>::DeleteAt(void * &)

- ea: `0x180008698`
- end: `0x180008730`
- name: `?DeleteAt@?$CList@VCMulticastNamespace@@VCNoLock@@@@QEAAPEAVCMulticastNamespace@@AEAPEAX@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a4c`
- `0x180007a24`

## callees

- `0x180008698`

## pseudocode

```c
__int64 __fastcall CList<CMulticastNamespace,CNoLock>::DeleteAt(__int64 *a1, __int64 *a2)
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
        v7 = *(_QWORD *)(v5 + 456);
        *a1 = v7;
        *(_QWORD *)(v7 + 464) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 5);
        return v2;
      }
      if ( v2 != v6 )
      {
        v9 = *(_QWORD *)(v2 + 456);
        v10 = *(_QWORD *)(v2 + 464);
        *a2 = v9;
        *(_QWORD *)(v10 + 456) = v9;
        *(_QWORD *)(*(_QWORD *)(v2 + 456) + 464LL) = *(_QWORD *)(v2 + 464);
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v6 + 464);
      a1[1] = v8;
      *(_QWORD *)(v8 + 456) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x180008698  mov     r9, [rdx]
0x18000869b  mov     r10, rdx
0x18000869e  xor     edx, edx
0x1800086a0  mov     r8, rcx
0x1800086a3  test    r9, r9
0x1800086a6  jz      loc_18000872C
0x1800086ac  mov     rax, [rcx]
0x1800086af  mov     rcx, [rcx+8]
0x1800086b3  cmp     rax, rcx
0x1800086b6  jnz     short loc_1800086C1
0x1800086b8  mov     [r8+8], rdx
0x1800086bc  mov     [r8], rdx
0x1800086bf  jmp     short loc_1800086F6
0x1800086c1  cmp     r9, rax
0x1800086c4  jnz     short loc_1800086DF
0x1800086c6  mov     rax, [rax+1C8h]
0x1800086cd  mov     [r8], rax
0x1800086d0  mov     [rax+1D0h], rdx
0x1800086d7  mov     rax, [r8]
0x1800086da  mov     [r10], rax
0x1800086dd  jmp     short loc_180008728
0x1800086df  cmp     r9, rcx
0x1800086e2  jnz     short loc_1800086FB
0x1800086e4  mov     rax, [rcx+1D0h]
0x1800086eb  mov     [r8+8], rax
0x1800086ef  mov     [rax+1C8h], rdx
0x1800086f6  mov     [r10], rdx
0x1800086f9  jmp     short loc_180008728
0x1800086fb  mov     rdx, [r9+1C8h]
0x180008702  mov     rcx, [r9+1D0h]
0x180008709  mov     [r10], rdx
0x18000870c  mov     [rcx+1C8h], rdx
0x180008713  mov     rdx, [r9+1C8h]
0x18000871a  mov     rcx, [r9+1D0h]
0x180008721  mov     [rdx+1D0h], rcx
0x180008728  dec     dword ptr [r8+14h]
0x18000872c  mov     rax, r9
0x18000872f  retn
```
