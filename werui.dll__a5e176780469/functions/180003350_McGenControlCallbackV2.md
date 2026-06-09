# McGenControlCallbackV2

- ea: `0x180003350`
- end: `0x18000344f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003350`
- `0x180016c1e`

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
0x180003350  push    rbx
0x180003352  sub     rsp, 20h
0x180003356  mov     r10, [rsp+28h+CallbackContext]
0x18000335b  xor     ebx, ebx
0x18000335d  test    r10, r10
0x180003360  jz      loc_180003449
0x180003366  test    edx, edx
0x180003368  jz      loc_18000340F
0x18000336e  cmp     edx, 1
0x180003371  jnz     loc_180003449
0x180003377  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000337c  mov     [r10+28h], r8b
0x180003380  mov     r8d, ebx
0x180003383  mov     [r10+18h], rax
0x180003387  mov     [r10+10h], r9
0x18000338b  mov     [r10+24h], edx
0x18000338f  cmp     bx, [r10+2Ah]
0x180003394  jnb     loc_180003449
0x18000339a  mov     rax, [r10+40h]
0x18000339e  mov     cl, [r10+28h]
0x1800033a2  mov     r9d, r8d
0x1800033a5  cmp     [r9+rax], cl
0x1800033a9  jbe     short loc_1800033AF
0x1800033ab  test    cl, cl
0x1800033ad  jnz     short loc_1800033CF
0x1800033af  mov     rax, [r10+38h]
0x1800033b3  mov     rcx, [rax+r9*8]
0x1800033b7  test    rcx, rcx
0x1800033ba  jz      short loc_1800033D4
0x1800033bc  test    [r10+10h], rcx
0x1800033c0  jz      short loc_1800033CF
0x1800033c2  mov     rax, [r10+18h]
0x1800033c6  and     rax, rcx
0x1800033c9  cmp     rax, [r10+18h]
0x1800033cd  jz      short loc_1800033D4
0x1800033cf  mov     r11b, bl
0x1800033d2  jmp     short loc_1800033D7
0x1800033d4  mov     r11b, 1
0x1800033d7  mov     rax, [r10+30h]
0x1800033db  mov     ecx, r8d
0x1800033de  shr     r9, 5
0x1800033e2  mov     edx, 1
0x1800033e7  shl     edx, cl
0x1800033e9  lea     rcx, [rax+r9*4]
0x1800033ed  test    r11b, r11b
0x1800033f0  jz      short loc_1800033F6
0x1800033f2  or      edx, [rcx]
0x1800033f4  jmp     short loc_1800033FA
0x1800033f6  not     edx
0x1800033f8  and     edx, [rcx]
0x1800033fa  mov     [rcx], edx
0x1800033fc  inc     r8d
0x1800033ff  movzx   eax, word ptr [r10+2Ah]
0x180003404  cmp     r8d, eax
0x180003407  jb      short loc_18000339A
0x180003409  add     rsp, 20h
0x18000340d  pop     rbx
0x18000340e  retn
0x18000340f  mov     [r10+24h], ebx
0x180003413  mov     [r10+28h], bl
0x180003417  mov     [r10+10h], rbx
0x18000341b  mov     [r10+18h], rbx
0x18000341f  cmp     [r10+2Ah], bx
0x180003424  jbe     short loc_180003449
0x180003426  movzx   eax, word ptr [r10+2Ah]
0x18000342b  mov     ecx, 20h ; ' '
0x180003430  dec     eax
0x180003432  cdq
0x180003433  idiv    ecx
0x180003435  mov     rcx, [r10+30h]; void *
0x180003439  xor     edx, edx; Val
0x18000343b  inc     eax
0x18000343d  movsxd  r8, eax
0x180003440  shl     r8, 2; Size
0x180003444  call    memset_0
0x180003449  add     rsp, 20h
0x18000344d  pop     rbx
0x18000344e  retn
```
