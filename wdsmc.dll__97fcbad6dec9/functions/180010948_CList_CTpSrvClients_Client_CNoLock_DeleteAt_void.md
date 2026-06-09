# CList<CTpSrvClients::Client,CNoLock>::DeleteAt(void * &)

- ea: `0x180010948`
- end: `0x1800109e5`
- name: `?DeleteAt@?$CList@UClient@CTpSrvClients@@VCNoLock@@@@QEAAPEAUClient@CTpSrvClients@@AEAPEAX@Z`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fddc`
- `0x180010884`

## callees

- `0x180010948`

## pseudocode

```c
__int64 __fastcall CList<CTpSrvClients::Client,CNoLock>::DeleteAt(__int64 *a1, __int64 *a2)
{
  __int64 v2; // r9
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rax

  v2 = *a2;
  if ( *a2 )
  {
    v4 = *a1;
    v5 = a1[1];
    if ( v4 == v5 )
    {
      a1[1] = 0;
      *a1 = 0;
    }
    else
    {
      if ( v2 == v4 )
      {
        v6 = *(_QWORD *)(v4 + 3224);
        *a1 = v6;
        *(_QWORD *)(v6 + 3232) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 5);
        return v2;
      }
      if ( v2 != v5 )
      {
        *a2 = *(_QWORD *)(v2 + 3224);
        *(_QWORD *)(*(_QWORD *)(v2 + 3232) + 3224LL) = *(_QWORD *)(v2 + 3224);
        *(_QWORD *)(*(_QWORD *)(v2 + 3224) + 3232LL) = *(_QWORD *)(v2 + 3232);
        goto LABEL_10;
      }
      v7 = *(_QWORD *)(v5 + 3232);
      a1[1] = v7;
      *(_QWORD *)(v7 + 3224) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x180010948  mov     r9, [rdx]
0x18001094b  xor     r10d, r10d
0x18001094e  mov     r8, rcx
0x180010951  test    r9, r9
0x180010954  jz      loc_1800109E1
0x18001095a  mov     rax, [rcx]
0x18001095d  mov     rcx, [rcx+8]
0x180010961  cmp     rax, rcx
0x180010964  jnz     short loc_18001096F
0x180010966  mov     [r8+8], r10
0x18001096a  mov     [r8], r10
0x18001096d  jmp     short loc_1800109A4
0x18001096f  cmp     r9, rax
0x180010972  jnz     short loc_18001098D
0x180010974  mov     rax, [rax+0C98h]
0x18001097b  mov     [r8], rax
0x18001097e  mov     [rax+0CA0h], r10
0x180010985  mov     rax, [r8]
0x180010988  mov     [rdx], rax
0x18001098b  jmp     short loc_1800109DD
0x18001098d  cmp     r9, rcx
0x180010990  jnz     short loc_1800109A9
0x180010992  mov     rax, [rcx+0CA0h]
0x180010999  mov     [r8+8], rax
0x18001099d  mov     [rax+0C98h], r10
0x1800109a4  mov     [rdx], r10
0x1800109a7  jmp     short loc_1800109DD
0x1800109a9  mov     rax, [r9+0C98h]
0x1800109b0  mov     [rdx], rax
0x1800109b3  mov     rdx, [r9+0CA0h]
0x1800109ba  mov     rcx, [r9+0C98h]
0x1800109c1  mov     [rdx+0C98h], rcx
0x1800109c8  mov     rdx, [r9+0C98h]
0x1800109cf  mov     rcx, [r9+0CA0h]
0x1800109d6  mov     [rdx+0CA0h], rcx
0x1800109dd  dec     dword ptr [r8+14h]
0x1800109e1  mov     rax, r9
0x1800109e4  retn
```
