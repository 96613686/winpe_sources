# EnableCallback

- ea: `0x180077200`
- end: `0x180077301`
- name: `EnableCallback`
- size: `257`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011a38`
- `0x180077200`

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
0x180077200  push    rbx
0x180077202  sub     rsp, 20h
0x180077206  mov     r10, [rsp+28h+CallbackContext]
0x18007720b  xor     ebx, ebx
0x18007720d  test    r10, r10
0x180077210  jz      loc_1800772FA
0x180077216  test    edx, edx
0x180077218  jz      loc_1800772C0
0x18007721e  cmp     edx, 1
0x180077221  jnz     loc_1800772FA
0x180077227  mov     rax, [rsp+28h+MatchAllKeyword]
0x18007722c  mov     [r10+28h], r8b
0x180077230  mov     r8d, ebx
0x180077233  mov     [r10+18h], rax
0x180077237  mov     [r10+10h], r9
0x18007723b  mov     [r10+24h], edx
0x18007723f  cmp     bx, [r10+2Ah]
0x180077244  jnb     loc_1800772FA
0x18007724a  mov     rax, [r10+40h]
0x18007724e  mov     cl, [r10+28h]
0x180077252  mov     r9d, r8d
0x180077255  cmp     [r9+rax], cl
0x180077259  jbe     short loc_18007725F
0x18007725b  test    cl, cl
0x18007725d  jnz     short loc_18007727F
0x18007725f  mov     rax, [r10+38h]
0x180077263  mov     rcx, [rax+r9*8]
0x180077267  test    rcx, rcx
0x18007726a  jz      short loc_180077284
0x18007726c  test    [r10+10h], rcx
0x180077270  jz      short loc_18007727F
0x180077272  mov     rax, [r10+18h]
0x180077276  and     rax, rcx
0x180077279  cmp     rax, [r10+18h]
0x18007727d  jz      short loc_180077284
0x18007727f  mov     r11b, bl
0x180077282  jmp     short loc_180077287
0x180077284  mov     r11b, 1
0x180077287  mov     rax, [r10+30h]
0x18007728b  mov     ecx, r8d
0x18007728e  shr     r9, 5
0x180077292  mov     edx, 1
0x180077297  shl     edx, cl
0x180077299  lea     rcx, [rax+r9*4]
0x18007729d  test    r11b, r11b
0x1800772a0  jz      short loc_1800772A6
0x1800772a2  or      edx, [rcx]
0x1800772a4  jmp     short loc_1800772AA
0x1800772a6  not     edx
0x1800772a8  and     edx, [rcx]
0x1800772aa  mov     [rcx], edx
0x1800772ac  inc     r8d
0x1800772af  movzx   eax, word ptr [r10+2Ah]
0x1800772b4  cmp     r8d, eax
0x1800772b7  jb      short loc_18007724A
0x1800772b9  add     rsp, 20h
0x1800772bd  pop     rbx
0x1800772be  retn
0x1800772c0  mov     [r10+24h], ebx
0x1800772c4  mov     [r10+28h], bl
0x1800772c8  mov     [r10+10h], rbx
0x1800772cc  mov     [r10+18h], rbx
0x1800772d0  cmp     [r10+2Ah], bx
0x1800772d5  jbe     short loc_1800772FA
0x1800772d7  movzx   eax, word ptr [r10+2Ah]
0x1800772dc  mov     ecx, 20h ; ' '
0x1800772e1  dec     eax
0x1800772e3  cdq
0x1800772e4  idiv    ecx
0x1800772e6  mov     rcx, [r10+30h]; void *
0x1800772ea  xor     edx, edx; Val
0x1800772ec  inc     eax
0x1800772ee  movsxd  r8, eax
0x1800772f1  shl     r8, 2; Size
0x1800772f5  call    memset
0x1800772fa  add     rsp, 20h
0x1800772fe  pop     rbx
0x1800772ff  retn
```
