# McGenControlCallbackV2

- ea: `0x180024150`
- end: `0x18002424f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180024150`
- `0x180024629`

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
0x180024150  push    rbx
0x180024152  sub     rsp, 20h
0x180024156  mov     r10, [rsp+28h+CallbackContext]
0x18002415b  xor     ebx, ebx
0x18002415d  test    r10, r10
0x180024160  jz      loc_180024249
0x180024166  test    edx, edx
0x180024168  jz      loc_18002420F
0x18002416e  cmp     edx, 1
0x180024171  jnz     loc_180024249
0x180024177  mov     rax, [rsp+28h+MatchAllKeyword]
0x18002417c  mov     [r10+28h], r8b
0x180024180  mov     r8d, ebx
0x180024183  mov     [r10+18h], rax
0x180024187  mov     [r10+10h], r9
0x18002418b  mov     [r10+24h], edx
0x18002418f  cmp     bx, [r10+2Ah]
0x180024194  jnb     loc_180024249
0x18002419a  mov     rax, [r10+40h]
0x18002419e  mov     cl, [r10+28h]
0x1800241a2  mov     r9d, r8d
0x1800241a5  cmp     [r9+rax], cl
0x1800241a9  jbe     short loc_1800241AF
0x1800241ab  test    cl, cl
0x1800241ad  jnz     short loc_1800241CF
0x1800241af  mov     rax, [r10+38h]
0x1800241b3  mov     rcx, [rax+r9*8]
0x1800241b7  test    rcx, rcx
0x1800241ba  jz      short loc_1800241D4
0x1800241bc  test    [r10+10h], rcx
0x1800241c0  jz      short loc_1800241CF
0x1800241c2  mov     rax, [r10+18h]
0x1800241c6  and     rax, rcx
0x1800241c9  cmp     rax, [r10+18h]
0x1800241cd  jz      short loc_1800241D4
0x1800241cf  mov     r11b, bl
0x1800241d2  jmp     short loc_1800241D7
0x1800241d4  mov     r11b, 1
0x1800241d7  mov     rax, [r10+30h]
0x1800241db  mov     ecx, r8d
0x1800241de  shr     r9, 5
0x1800241e2  mov     edx, 1
0x1800241e7  shl     edx, cl
0x1800241e9  lea     rcx, [rax+r9*4]
0x1800241ed  test    r11b, r11b
0x1800241f0  jz      short loc_1800241F6
0x1800241f2  or      edx, [rcx]
0x1800241f4  jmp     short loc_1800241FA
0x1800241f6  not     edx
0x1800241f8  and     edx, [rcx]
0x1800241fa  mov     [rcx], edx
0x1800241fc  inc     r8d
0x1800241ff  movzx   eax, word ptr [r10+2Ah]
0x180024204  cmp     r8d, eax
0x180024207  jb      short loc_18002419A
0x180024209  add     rsp, 20h
0x18002420d  pop     rbx
0x18002420e  retn
0x18002420f  mov     [r10+24h], ebx
0x180024213  mov     [r10+28h], bl
0x180024217  mov     [r10+10h], rbx
0x18002421b  mov     [r10+18h], rbx
0x18002421f  cmp     [r10+2Ah], bx
0x180024224  jbe     short loc_180024249
0x180024226  movzx   eax, word ptr [r10+2Ah]
0x18002422b  mov     ecx, 20h ; ' '
0x180024230  dec     eax
0x180024232  cdq
0x180024233  idiv    ecx
0x180024235  mov     rcx, [r10+30h]; void *
0x180024239  xor     edx, edx; Val
0x18002423b  inc     eax
0x18002423d  movsxd  r8, eax
0x180024240  shl     r8, 2; Size
0x180024244  call    memset_0
0x180024249  add     rsp, 20h
0x18002424d  pop     rbx
0x18002424e  retn
```
