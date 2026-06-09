# CSmHashTable<CTpSrvClients::Client,CNoLock,113>::FindItem<ulong>(ulong,ulong)

- ea: `0x1800108e8`
- end: `0x18001093f`
- name: `??$FindItem@K@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@QEAAPEAUClient@CTpSrvClients@@KK@Z`
- size: `87`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e528`
- `0x18000e65c`
- `0x18000fa3c`
- `0x1800100f8`
- `0x180010240`
- `0x1800139d8`

## callees

- `0x1800108e8`

## pseudocode

```c
__int64 __fastcall CSmHashTable<CTpSrvClients::Client,CNoLock,113>::FindItem<unsigned long>(
        __int64 a1,
        unsigned int a2,
        int a3)
{
  __int64 v3; // r10
  __int64 v4; // rax

  v3 = 0;
  v4 = *(_QWORD *)(a1 + 24LL * (a2 % 0x71) + 8);
  while ( v4 )
  {
    v3 = v4;
    v4 = *(_QWORD *)(v4 + 3224);
    if ( *(_DWORD *)(v3 + 3240) == a2 && *(_DWORD *)(v3 + 1148) == a3 )
      break;
    v3 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1800108e8  mov     r9, rcx
0x1800108eb  mov     r11d, edx
0x1800108ee  mov     eax, 21FB7813h
0x1800108f3  mov     ecx, r11d
0x1800108f6  mul     edx
0x1800108f8  mov     eax, r11d
0x1800108fb  xor     r10d, r10d
0x1800108fe  sub     eax, edx
0x180010900  shr     eax, 1
0x180010902  add     eax, edx
0x180010904  shr     eax, 6
0x180010907  imul    eax, 71h ; 'q'
0x18001090a  sub     ecx, eax
0x18001090c  lea     rcx, [rcx+rcx*2]
0x180010910  mov     rax, [r9+rcx*8+8]
0x180010915  jmp     short loc_180010936
0x180010917  mov     r10, rax
0x18001091a  mov     rax, [rax+0C98h]
0x180010921  cmp     [r10+0CA8h], r11d
0x180010928  jnz     short loc_180010933
0x18001092a  cmp     [r10+47Ch], r8d
0x180010931  jz      short loc_18001093B
0x180010933  xor     r10d, r10d
0x180010936  test    rax, rax
0x180010939  jnz     short loc_180010917
0x18001093b  mov     rax, r10
0x18001093e  retn
```
