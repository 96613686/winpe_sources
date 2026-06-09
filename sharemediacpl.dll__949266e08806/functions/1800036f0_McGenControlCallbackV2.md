# McGenControlCallbackV2

- ea: `0x1800036f0`
- end: `0x1800037f0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000291e`
- `0x1800036f0`

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
0x1800036f0  push    rbx
0x1800036f2  sub     rsp, 20h
0x1800036f6  mov     r10, [rsp+28h+CallbackContext]
0x1800036fb  xor     ebx, ebx
0x1800036fd  test    r10, r10
0x180003700  jz      loc_1800037EA
0x180003706  test    edx, edx
0x180003708  jz      loc_1800037AF
0x18000370e  cmp     edx, 1
0x180003711  jnz     loc_1800037EA
0x180003717  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000371c  mov     [r10+28h], r8b
0x180003720  mov     r8d, ebx
0x180003723  mov     [r10+18h], rax
0x180003727  mov     [r10+10h], r9
0x18000372b  mov     [r10+24h], edx
0x18000372f  cmp     bx, [r10+2Ah]
0x180003734  jnb     loc_1800037EA
0x18000373a  mov     rax, [r10+40h]
0x18000373e  mov     cl, [r10+28h]
0x180003742  mov     r9d, r8d
0x180003745  cmp     [r9+rax], cl
0x180003749  jbe     short loc_18000374F
0x18000374b  test    cl, cl
0x18000374d  jnz     short loc_18000376F
0x18000374f  mov     rax, [r10+38h]
0x180003753  mov     rcx, [rax+r9*8]
0x180003757  test    rcx, rcx
0x18000375a  jz      short loc_180003774
0x18000375c  test    [r10+10h], rcx
0x180003760  jz      short loc_18000376F
0x180003762  mov     rax, [r10+18h]
0x180003766  and     rax, rcx
0x180003769  cmp     rax, [r10+18h]
0x18000376d  jz      short loc_180003774
0x18000376f  mov     r11b, bl
0x180003772  jmp     short loc_180003777
0x180003774  mov     r11b, 1
0x180003777  mov     rax, [r10+30h]
0x18000377b  mov     ecx, r8d
0x18000377e  shr     r9, 5
0x180003782  mov     edx, 1
0x180003787  shl     edx, cl
0x180003789  lea     rcx, [rax+r9*4]
0x18000378d  test    r11b, r11b
0x180003790  jz      short loc_180003796
0x180003792  or      edx, [rcx]
0x180003794  jmp     short loc_18000379A
0x180003796  not     edx
0x180003798  and     edx, [rcx]
0x18000379a  mov     [rcx], edx
0x18000379c  inc     r8d
0x18000379f  movzx   eax, word ptr [r10+2Ah]
0x1800037a4  cmp     r8d, eax
0x1800037a7  jb      short loc_18000373A
0x1800037a9  add     rsp, 20h
0x1800037ad  pop     rbx
0x1800037ae  retn
0x1800037af  mov     [r10+24h], ebx
0x1800037b3  mov     [r10+28h], bl
0x1800037b7  mov     [r10+10h], rbx
0x1800037bb  mov     [r10+18h], rbx
0x1800037bf  cmp     [r10+2Ah], bx
0x1800037c4  jbe     short loc_1800037EA
0x1800037c6  movzx   eax, word ptr [r10+2Ah]
0x1800037cb  mov     rcx, [r10+30h]; void *
0x1800037cf  dec     eax
0x1800037d1  cdq
0x1800037d2  and     edx, 1Fh
0x1800037d5  add     eax, edx
0x1800037d7  xor     edx, edx; Val
0x1800037d9  sar     eax, 5
0x1800037dc  inc     eax
0x1800037de  movsxd  r8, eax
0x1800037e1  shl     r8, 2; Size
0x1800037e5  call    memset_0
0x1800037ea  add     rsp, 20h
0x1800037ee  pop     rbx
0x1800037ef  retn
```
