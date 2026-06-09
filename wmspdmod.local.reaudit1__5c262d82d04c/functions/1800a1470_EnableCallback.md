# EnableCallback

- ea: `0x1800a1470`
- end: `0x1800a1572`
- name: `EnableCallback`
- size: `258`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002050`
- `0x1800a1470`

## pseudocode

```c
void __fastcall EnableCallback(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        unsigned __int16 *CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rcx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // edx

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < CallbackContext[21]; ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          v10 = 0;
          if ( *(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8 )
          {
            v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
            if ( !v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
            {
              v10 = 1;
            }
          }
          v11 = 1 << v7;
          v12 = (int *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
          if ( v10 )
            v13 = *v12 | v11;
          else
            v13 = *v12 & ~v11;
          *v12 = v13;
        }
      }
    }
    else
    {
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( CallbackContext[21] )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((CallbackContext[21] - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x1800a1470  push    rbx
0x1800a1472  sub     rsp, 20h
0x1800a1476  mov     r10, [rsp+28h+CallbackContext]
0x1800a147b  xor     ebx, ebx
0x1800a147d  test    r10, r10
0x1800a1480  jz      loc_1800A156B
0x1800a1486  test    edx, edx
0x1800a1488  jz      loc_1800A1530
0x1800a148e  cmp     edx, 1
0x1800a1491  jnz     loc_1800A156B
0x1800a1497  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800a149c  mov     [r10+28h], r8b
0x1800a14a0  mov     r8d, ebx
0x1800a14a3  mov     [r10+18h], rax
0x1800a14a7  mov     [r10+10h], r9
0x1800a14ab  mov     [r10+24h], edx
0x1800a14af  cmp     bx, [r10+2Ah]
0x1800a14b4  jnb     loc_1800A156B
0x1800a14ba  mov     rax, [r10+40h]
0x1800a14be  mov     cl, [r10+28h]
0x1800a14c2  mov     r9d, r8d
0x1800a14c5  cmp     [r9+rax], cl
0x1800a14c9  jbe     short loc_1800A14CF
0x1800a14cb  test    cl, cl
0x1800a14cd  jnz     short loc_1800A14EF
0x1800a14cf  mov     rax, [r10+38h]
0x1800a14d3  mov     rcx, [rax+r9*8]
0x1800a14d7  test    rcx, rcx
0x1800a14da  jz      short loc_1800A14F4
0x1800a14dc  test    [r10+10h], rcx
0x1800a14e0  jz      short loc_1800A14EF
0x1800a14e2  mov     rax, [r10+18h]
0x1800a14e6  and     rax, rcx
0x1800a14e9  cmp     rax, [r10+18h]
0x1800a14ed  jz      short loc_1800A14F4
0x1800a14ef  mov     r11b, bl
0x1800a14f2  jmp     short loc_1800A14F7
0x1800a14f4  mov     r11b, 1
0x1800a14f7  mov     rax, [r10+30h]
0x1800a14fb  mov     ecx, r8d
0x1800a14fe  shr     r9, 5
0x1800a1502  mov     edx, 1
0x1800a1507  shl     edx, cl
0x1800a1509  lea     rcx, [rax+r9*4]
0x1800a150d  test    r11b, r11b
0x1800a1510  jz      short loc_1800A1516
0x1800a1512  or      edx, [rcx]
0x1800a1514  jmp     short loc_1800A151A
0x1800a1516  not     edx
0x1800a1518  and     edx, [rcx]
0x1800a151a  mov     [rcx], edx
0x1800a151c  inc     r8d
0x1800a151f  movzx   eax, word ptr [r10+2Ah]
0x1800a1524  cmp     r8d, eax
0x1800a1527  jb      short loc_1800A14BA
0x1800a1529  add     rsp, 20h
0x1800a152d  pop     rbx
0x1800a152e  retn
0x1800a1530  mov     [r10+24h], ebx
0x1800a1534  mov     [r10+28h], bl
0x1800a1538  mov     [r10+10h], rbx
0x1800a153c  mov     [r10+18h], rbx
0x1800a1540  cmp     [r10+2Ah], bx
0x1800a1545  jbe     short loc_1800A156B
0x1800a1547  movzx   eax, word ptr [r10+2Ah]
0x1800a154c  mov     rcx, [r10+30h]; void *
0x1800a1550  dec     eax
0x1800a1552  cdq
0x1800a1553  and     edx, 1Fh
0x1800a1556  add     eax, edx
0x1800a1558  xor     edx, edx; Val
0x1800a155a  sar     eax, 5
0x1800a155d  inc     eax
0x1800a155f  movsxd  r8, eax
0x1800a1562  shl     r8, 2; Size
0x1800a1566  call    memset
0x1800a156b  add     rsp, 20h
0x1800a156f  pop     rbx
0x1800a1570  retn
```
