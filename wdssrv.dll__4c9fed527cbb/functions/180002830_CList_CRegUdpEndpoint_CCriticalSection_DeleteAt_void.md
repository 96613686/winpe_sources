# CList<CRegUdpEndpoint,CCriticalSection>::DeleteAt(void * &)

- ea: `0x180002830`
- end: `0x1800028c8`
- name: `?DeleteAt@?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@QEAAPEAVCRegUdpEndpoint@@AEAPEAX@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000263c`
- `0x1800033c0`

## callees

- `0x180002830`

## pseudocode

```c
__int64 __fastcall CList<CRegUdpEndpoint,CCriticalSection>::DeleteAt(__int64 *a1, __int64 *a2)
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
        v7 = *(_QWORD *)(v5 + 2080);
        *a1 = v7;
        *(_QWORD *)(v7 + 2088) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 14);
        return v2;
      }
      if ( v2 != v6 )
      {
        v9 = *(_QWORD *)(v2 + 2080);
        v10 = *(_QWORD *)(v2 + 2088);
        *a2 = v9;
        *(_QWORD *)(v10 + 2080) = v9;
        *(_QWORD *)(*(_QWORD *)(v2 + 2080) + 2088LL) = *(_QWORD *)(v2 + 2088);
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v6 + 2088);
      a1[1] = v8;
      *(_QWORD *)(v8 + 2080) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x180002830  mov     r9, [rdx]
0x180002833  mov     r10, rdx
0x180002836  xor     edx, edx
0x180002838  mov     r8, rcx
0x18000283b  test    r9, r9
0x18000283e  jz      loc_1800028C4
0x180002844  mov     rax, [rcx]
0x180002847  mov     rcx, [rcx+8]
0x18000284b  cmp     rax, rcx
0x18000284e  jnz     short loc_180002859
0x180002850  mov     [r8+8], rdx
0x180002854  mov     [r8], rdx
0x180002857  jmp     short loc_18000288E
0x180002859  cmp     r9, rax
0x18000285c  jnz     short loc_180002877
0x18000285e  mov     rax, [rax+820h]
0x180002865  mov     [r8], rax
0x180002868  mov     [rax+828h], rdx
0x18000286f  mov     rax, [r8]
0x180002872  mov     [r10], rax
0x180002875  jmp     short loc_1800028C0
0x180002877  cmp     r9, rcx
0x18000287a  jnz     short loc_180002893
0x18000287c  mov     rax, [rcx+828h]
0x180002883  mov     [r8+8], rax
0x180002887  mov     [rax+820h], rdx
0x18000288e  mov     [r10], rdx
0x180002891  jmp     short loc_1800028C0
0x180002893  mov     rdx, [r9+820h]
0x18000289a  mov     rcx, [r9+828h]
0x1800028a1  mov     [r10], rdx
0x1800028a4  mov     [rcx+820h], rdx
0x1800028ab  mov     rdx, [r9+820h]
0x1800028b2  mov     rcx, [r9+828h]
0x1800028b9  mov     [rdx+828h], rcx
0x1800028c0  dec     dword ptr [r8+38h]
0x1800028c4  mov     rax, r9
0x1800028c7  retn
```
