# CList<CMcCoClients::Client,CNoLock>::DeleteAt(void * &)

- ea: `0x18000c2f0`
- end: `0x18000c38d`
- name: `?DeleteAt@?$CList@UClient@CMcCoClients@@VCNoLock@@@@QEAAPEAUClient@CMcCoClients@@AEAPEAX@Z`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b8e8`
- `0x18000c230`

## callees

- `0x18000c2f0`

## pseudocode

```c
__int64 __fastcall CList<CMcCoClients::Client,CNoLock>::DeleteAt(__int64 *a1, __int64 *a2)
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
        v6 = *(_QWORD *)(v4 + 2152);
        *a1 = v6;
        *(_QWORD *)(v6 + 2160) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 5);
        return v2;
      }
      if ( v2 != v5 )
      {
        *a2 = *(_QWORD *)(v2 + 2152);
        *(_QWORD *)(*(_QWORD *)(v2 + 2160) + 2152LL) = *(_QWORD *)(v2 + 2152);
        *(_QWORD *)(*(_QWORD *)(v2 + 2152) + 2160LL) = *(_QWORD *)(v2 + 2160);
        goto LABEL_10;
      }
      v7 = *(_QWORD *)(v5 + 2160);
      a1[1] = v7;
      *(_QWORD *)(v7 + 2152) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x18000c2f0  mov     r9, [rdx]
0x18000c2f3  xor     r10d, r10d
0x18000c2f6  mov     r8, rcx
0x18000c2f9  test    r9, r9
0x18000c2fc  jz      loc_18000C389
0x18000c302  mov     rax, [rcx]
0x18000c305  mov     rcx, [rcx+8]
0x18000c309  cmp     rax, rcx
0x18000c30c  jnz     short loc_18000C317
0x18000c30e  mov     [r8+8], r10
0x18000c312  mov     [r8], r10
0x18000c315  jmp     short loc_18000C34C
0x18000c317  cmp     r9, rax
0x18000c31a  jnz     short loc_18000C335
0x18000c31c  mov     rax, [rax+868h]
0x18000c323  mov     [r8], rax
0x18000c326  mov     [rax+870h], r10
0x18000c32d  mov     rax, [r8]
0x18000c330  mov     [rdx], rax
0x18000c333  jmp     short loc_18000C385
0x18000c335  cmp     r9, rcx
0x18000c338  jnz     short loc_18000C351
0x18000c33a  mov     rax, [rcx+870h]
0x18000c341  mov     [r8+8], rax
0x18000c345  mov     [rax+868h], r10
0x18000c34c  mov     [rdx], r10
0x18000c34f  jmp     short loc_18000C385
0x18000c351  mov     rax, [r9+868h]
0x18000c358  mov     [rdx], rax
0x18000c35b  mov     rdx, [r9+870h]
0x18000c362  mov     rcx, [r9+868h]
0x18000c369  mov     [rdx+868h], rcx
0x18000c370  mov     rdx, [r9+868h]
0x18000c377  mov     rcx, [r9+870h]
0x18000c37e  mov     [rdx+870h], rcx
0x18000c385  dec     dword ptr [r8+14h]
0x18000c389  mov     rax, r9
0x18000c38c  retn
```
