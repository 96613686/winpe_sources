# CList<CUdpEndpoint,CNoLock>::DeleteAt(void * &)

- ea: `0x1800028d0`
- end: `0x180002968`
- name: `?DeleteAt@?$CList@VCUdpEndpoint@@VCNoLock@@@@QEAAPEAVCUdpEndpoint@@AEAPEAX@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002798`
- `0x180003680`
- `0x180015144`

## callees

- `0x1800028d0`

## pseudocode

```c
__int64 __fastcall CList<CUdpEndpoint,CNoLock>::DeleteAt(__int64 *a1, __int64 *a2)
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
        v7 = *(_QWORD *)(v5 + 2304);
        *a1 = v7;
        *(_QWORD *)(v7 + 2312) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 5);
        return v2;
      }
      if ( v2 != v6 )
      {
        v9 = *(_QWORD *)(v2 + 2304);
        v10 = *(_QWORD *)(v2 + 2312);
        *a2 = v9;
        *(_QWORD *)(v10 + 2304) = v9;
        *(_QWORD *)(*(_QWORD *)(v2 + 2304) + 2312LL) = *(_QWORD *)(v2 + 2312);
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v6 + 2312);
      a1[1] = v8;
      *(_QWORD *)(v8 + 2304) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x1800028d0  mov     r9, [rdx]
0x1800028d3  mov     r10, rdx
0x1800028d6  xor     edx, edx
0x1800028d8  mov     r8, rcx
0x1800028db  test    r9, r9
0x1800028de  jz      loc_180002964
0x1800028e4  mov     rax, [rcx]
0x1800028e7  mov     rcx, [rcx+8]
0x1800028eb  cmp     rax, rcx
0x1800028ee  jnz     short loc_1800028F9
0x1800028f0  mov     [r8+8], rdx
0x1800028f4  mov     [r8], rdx
0x1800028f7  jmp     short loc_18000292E
0x1800028f9  cmp     r9, rax
0x1800028fc  jnz     short loc_180002917
0x1800028fe  mov     rax, [rax+900h]
0x180002905  mov     [r8], rax
0x180002908  mov     [rax+908h], rdx
0x18000290f  mov     rax, [r8]
0x180002912  mov     [r10], rax
0x180002915  jmp     short loc_180002960
0x180002917  cmp     r9, rcx
0x18000291a  jnz     short loc_180002933
0x18000291c  mov     rax, [rcx+908h]
0x180002923  mov     [r8+8], rax
0x180002927  mov     [rax+900h], rdx
0x18000292e  mov     [r10], rdx
0x180002931  jmp     short loc_180002960
0x180002933  mov     rdx, [r9+900h]
0x18000293a  mov     rcx, [r9+908h]
0x180002941  mov     [r10], rdx
0x180002944  mov     [rcx+900h], rdx
0x18000294b  mov     rdx, [r9+900h]
0x180002952  mov     rcx, [r9+908h]
0x180002959  mov     [rdx+908h], rcx
0x180002960  dec     dword ptr [r8+14h]
0x180002964  mov     rax, r9
0x180002967  retn
```
