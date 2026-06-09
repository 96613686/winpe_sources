# McGenControlCallbackV2

- ea: `0x180002600`
- end: `0x180002700`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002600`
- `0x180002866`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
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
        memset_0(*((void **)CallbackContext + 6), 0, 4LL * ((CallbackContext[21] - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x180002600  push    rbx
0x180002602  sub     rsp, 20h
0x180002606  mov     r10, [rsp+28h+CallbackContext]
0x18000260b  xor     ebx, ebx
0x18000260d  test    r10, r10
0x180002610  jz      loc_1800026FA
0x180002616  test    edx, edx
0x180002618  jz      loc_1800026BF
0x18000261e  cmp     edx, 1
0x180002621  jnz     loc_1800026FA
0x180002627  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000262c  mov     [r10+28h], r8b
0x180002630  mov     r8d, ebx
0x180002633  mov     [r10+18h], rax
0x180002637  mov     [r10+10h], r9
0x18000263b  mov     [r10+24h], edx
0x18000263f  cmp     bx, [r10+2Ah]
0x180002644  jnb     loc_1800026FA
0x18000264a  mov     rax, [r10+40h]
0x18000264e  mov     cl, [r10+28h]
0x180002652  mov     r9d, r8d
0x180002655  cmp     [r9+rax], cl
0x180002659  jbe     short loc_18000265F
0x18000265b  test    cl, cl
0x18000265d  jnz     short loc_18000267F
0x18000265f  mov     rax, [r10+38h]
0x180002663  mov     rcx, [rax+r9*8]
0x180002667  test    rcx, rcx
0x18000266a  jz      short loc_180002684
0x18000266c  test    [r10+10h], rcx
0x180002670  jz      short loc_18000267F
0x180002672  mov     rax, [r10+18h]
0x180002676  and     rax, rcx
0x180002679  cmp     rax, [r10+18h]
0x18000267d  jz      short loc_180002684
0x18000267f  mov     r11b, bl
0x180002682  jmp     short loc_180002687
0x180002684  mov     r11b, 1
0x180002687  mov     rax, [r10+30h]
0x18000268b  mov     ecx, r8d
0x18000268e  shr     r9, 5
0x180002692  mov     edx, 1
0x180002697  shl     edx, cl
0x180002699  lea     rcx, [rax+r9*4]
0x18000269d  test    r11b, r11b
0x1800026a0  jz      short loc_1800026A6
0x1800026a2  or      edx, [rcx]
0x1800026a4  jmp     short loc_1800026AA
0x1800026a6  not     edx
0x1800026a8  and     edx, [rcx]
0x1800026aa  mov     [rcx], edx
0x1800026ac  inc     r8d
0x1800026af  movzx   eax, word ptr [r10+2Ah]
0x1800026b4  cmp     r8d, eax
0x1800026b7  jb      short loc_18000264A
0x1800026b9  add     rsp, 20h
0x1800026bd  pop     rbx
0x1800026be  retn
0x1800026bf  mov     [r10+24h], ebx
0x1800026c3  mov     [r10+28h], bl
0x1800026c7  mov     [r10+10h], rbx
0x1800026cb  mov     [r10+18h], rbx
0x1800026cf  cmp     [r10+2Ah], bx
0x1800026d4  jbe     short loc_1800026FA
0x1800026d6  movzx   eax, word ptr [r10+2Ah]
0x1800026db  mov     rcx, [r10+30h]; void *
0x1800026df  dec     eax
0x1800026e1  cdq
0x1800026e2  and     edx, 1Fh
0x1800026e5  add     eax, edx
0x1800026e7  xor     edx, edx; Val
0x1800026e9  sar     eax, 5
0x1800026ec  inc     eax
0x1800026ee  movsxd  r8, eax
0x1800026f1  shl     r8, 2; Size
0x1800026f5  call    memset_0
0x1800026fa  add     rsp, 20h
0x1800026fe  pop     rbx
0x1800026ff  retn
```
