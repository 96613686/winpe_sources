# McGenControlCallbackV2

- ea: `0x180007750`
- end: `0x18000784f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006ec2`
- `0x180007750`

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
0x180007750  push    rbx
0x180007752  sub     rsp, 20h
0x180007756  mov     r10, [rsp+28h+CallbackContext]
0x18000775b  xor     ebx, ebx
0x18000775d  test    r10, r10
0x180007760  jz      loc_180007849
0x180007766  test    edx, edx
0x180007768  jz      loc_18000780F
0x18000776e  cmp     edx, 1
0x180007771  jnz     loc_180007849
0x180007777  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000777c  mov     [r10+28h], r8b
0x180007780  mov     r8d, ebx
0x180007783  mov     [r10+18h], rax
0x180007787  mov     [r10+10h], r9
0x18000778b  mov     [r10+24h], edx
0x18000778f  cmp     bx, [r10+2Ah]
0x180007794  jnb     loc_180007849
0x18000779a  mov     rax, [r10+40h]
0x18000779e  mov     cl, [r10+28h]
0x1800077a2  mov     r9d, r8d
0x1800077a5  cmp     [r9+rax], cl
0x1800077a9  jbe     short loc_1800077AF
0x1800077ab  test    cl, cl
0x1800077ad  jnz     short loc_1800077CF
0x1800077af  mov     rax, [r10+38h]
0x1800077b3  mov     rcx, [rax+r9*8]
0x1800077b7  test    rcx, rcx
0x1800077ba  jz      short loc_1800077D4
0x1800077bc  test    [r10+10h], rcx
0x1800077c0  jz      short loc_1800077CF
0x1800077c2  mov     rax, [r10+18h]
0x1800077c6  and     rax, rcx
0x1800077c9  cmp     rax, [r10+18h]
0x1800077cd  jz      short loc_1800077D4
0x1800077cf  mov     r11b, bl
0x1800077d2  jmp     short loc_1800077D7
0x1800077d4  mov     r11b, 1
0x1800077d7  mov     rax, [r10+30h]
0x1800077db  mov     ecx, r8d
0x1800077de  shr     r9, 5
0x1800077e2  mov     edx, 1
0x1800077e7  shl     edx, cl
0x1800077e9  lea     rcx, [rax+r9*4]
0x1800077ed  test    r11b, r11b
0x1800077f0  jz      short loc_1800077F6
0x1800077f2  or      edx, [rcx]
0x1800077f4  jmp     short loc_1800077FA
0x1800077f6  not     edx
0x1800077f8  and     edx, [rcx]
0x1800077fa  mov     [rcx], edx
0x1800077fc  inc     r8d
0x1800077ff  movzx   eax, word ptr [r10+2Ah]
0x180007804  cmp     r8d, eax
0x180007807  jb      short loc_18000779A
0x180007809  add     rsp, 20h
0x18000780d  pop     rbx
0x18000780e  retn
0x18000780f  mov     [r10+24h], ebx
0x180007813  mov     [r10+28h], bl
0x180007817  mov     [r10+10h], rbx
0x18000781b  mov     [r10+18h], rbx
0x18000781f  cmp     [r10+2Ah], bx
0x180007824  jbe     short loc_180007849
0x180007826  movzx   eax, word ptr [r10+2Ah]
0x18000782b  mov     ecx, 20h ; ' '
0x180007830  dec     eax
0x180007832  cdq
0x180007833  idiv    ecx
0x180007835  mov     rcx, [r10+30h]; void *
0x180007839  xor     edx, edx; Val
0x18000783b  inc     eax
0x18000783d  movsxd  r8, eax
0x180007840  shl     r8, 2; Size
0x180007844  call    memset_0
0x180007849  add     rsp, 20h
0x18000784d  pop     rbx
0x18000784e  retn
```
