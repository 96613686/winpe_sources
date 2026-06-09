# EnableCallback

- ea: `0x1800a14d0`
- end: `0x1800a15d2`
- name: `EnableCallback`
- size: `258`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002050`
- `0x1800a14d0`

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
0x1800a14d0  push    rbx
0x1800a14d2  sub     rsp, 20h
0x1800a14d6  mov     r10, [rsp+28h+CallbackContext]
0x1800a14db  xor     ebx, ebx
0x1800a14dd  test    r10, r10
0x1800a14e0  jz      loc_1800A15CB
0x1800a14e6  test    edx, edx
0x1800a14e8  jz      loc_1800A1590
0x1800a14ee  cmp     edx, 1
0x1800a14f1  jnz     loc_1800A15CB
0x1800a14f7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800a14fc  mov     [r10+28h], r8b
0x1800a1500  mov     r8d, ebx
0x1800a1503  mov     [r10+18h], rax
0x1800a1507  mov     [r10+10h], r9
0x1800a150b  mov     [r10+24h], edx
0x1800a150f  cmp     bx, [r10+2Ah]
0x1800a1514  jnb     loc_1800A15CB
0x1800a151a  mov     rax, [r10+40h]
0x1800a151e  mov     cl, [r10+28h]
0x1800a1522  mov     r9d, r8d
0x1800a1525  cmp     [r9+rax], cl
0x1800a1529  jbe     short loc_1800A152F
0x1800a152b  test    cl, cl
0x1800a152d  jnz     short loc_1800A154F
0x1800a152f  mov     rax, [r10+38h]
0x1800a1533  mov     rcx, [rax+r9*8]
0x1800a1537  test    rcx, rcx
0x1800a153a  jz      short loc_1800A1554
0x1800a153c  test    [r10+10h], rcx
0x1800a1540  jz      short loc_1800A154F
0x1800a1542  mov     rax, [r10+18h]
0x1800a1546  and     rax, rcx
0x1800a1549  cmp     rax, [r10+18h]
0x1800a154d  jz      short loc_1800A1554
0x1800a154f  mov     r11b, bl
0x1800a1552  jmp     short loc_1800A1557
0x1800a1554  mov     r11b, 1
0x1800a1557  mov     rax, [r10+30h]
0x1800a155b  mov     ecx, r8d
0x1800a155e  shr     r9, 5
0x1800a1562  mov     edx, 1
0x1800a1567  shl     edx, cl
0x1800a1569  lea     rcx, [rax+r9*4]
0x1800a156d  test    r11b, r11b
0x1800a1570  jz      short loc_1800A1576
0x1800a1572  or      edx, [rcx]
0x1800a1574  jmp     short loc_1800A157A
0x1800a1576  not     edx
0x1800a1578  and     edx, [rcx]
0x1800a157a  mov     [rcx], edx
0x1800a157c  inc     r8d
0x1800a157f  movzx   eax, word ptr [r10+2Ah]
0x1800a1584  cmp     r8d, eax
0x1800a1587  jb      short loc_1800A151A
0x1800a1589  add     rsp, 20h
0x1800a158d  pop     rbx
0x1800a158e  retn
0x1800a1590  mov     [r10+24h], ebx
0x1800a1594  mov     [r10+28h], bl
0x1800a1598  mov     [r10+10h], rbx
0x1800a159c  mov     [r10+18h], rbx
0x1800a15a0  cmp     [r10+2Ah], bx
0x1800a15a5  jbe     short loc_1800A15CB
0x1800a15a7  movzx   eax, word ptr [r10+2Ah]
0x1800a15ac  mov     rcx, [r10+30h]; void *
0x1800a15b0  dec     eax
0x1800a15b2  cdq
0x1800a15b3  and     edx, 1Fh
0x1800a15b6  add     eax, edx
0x1800a15b8  xor     edx, edx; Val
0x1800a15ba  sar     eax, 5
0x1800a15bd  inc     eax
0x1800a15bf  movsxd  r8, eax
0x1800a15c2  shl     r8, 2; Size
0x1800a15c6  call    memset
0x1800a15cb  add     rsp, 20h
0x1800a15cf  pop     rbx
0x1800a15d0  retn
```
