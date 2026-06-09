# McGenControlCallbackV2

- ea: `0x18000a530`
- end: `0x18000a62f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004456`
- `0x18000a530`

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
0x18000a530  push    rbx
0x18000a532  sub     rsp, 20h
0x18000a536  mov     r10, [rsp+28h+CallbackContext]
0x18000a53b  xor     ebx, ebx
0x18000a53d  test    r10, r10
0x18000a540  jz      loc_18000A629
0x18000a546  test    edx, edx
0x18000a548  jz      loc_18000A5EF
0x18000a54e  cmp     edx, 1
0x18000a551  jnz     loc_18000A629
0x18000a557  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000a55c  mov     [r10+28h], r8b
0x18000a560  mov     r8d, ebx
0x18000a563  mov     [r10+18h], rax
0x18000a567  mov     [r10+10h], r9
0x18000a56b  mov     [r10+24h], edx
0x18000a56f  cmp     bx, [r10+2Ah]
0x18000a574  jnb     loc_18000A629
0x18000a57a  mov     rax, [r10+40h]
0x18000a57e  mov     cl, [r10+28h]
0x18000a582  mov     r9d, r8d
0x18000a585  cmp     [r9+rax], cl
0x18000a589  jbe     short loc_18000A58F
0x18000a58b  test    cl, cl
0x18000a58d  jnz     short loc_18000A5AF
0x18000a58f  mov     rax, [r10+38h]
0x18000a593  mov     rcx, [rax+r9*8]
0x18000a597  test    rcx, rcx
0x18000a59a  jz      short loc_18000A5B4
0x18000a59c  test    [r10+10h], rcx
0x18000a5a0  jz      short loc_18000A5AF
0x18000a5a2  mov     rax, [r10+18h]
0x18000a5a6  and     rax, rcx
0x18000a5a9  cmp     rax, [r10+18h]
0x18000a5ad  jz      short loc_18000A5B4
0x18000a5af  mov     r11b, bl
0x18000a5b2  jmp     short loc_18000A5B7
0x18000a5b4  mov     r11b, 1
0x18000a5b7  mov     rax, [r10+30h]
0x18000a5bb  mov     ecx, r8d
0x18000a5be  shr     r9, 5
0x18000a5c2  mov     edx, 1
0x18000a5c7  shl     edx, cl
0x18000a5c9  lea     rcx, [rax+r9*4]
0x18000a5cd  test    r11b, r11b
0x18000a5d0  jz      short loc_18000A5D6
0x18000a5d2  or      edx, [rcx]
0x18000a5d4  jmp     short loc_18000A5DA
0x18000a5d6  not     edx
0x18000a5d8  and     edx, [rcx]
0x18000a5da  mov     [rcx], edx
0x18000a5dc  inc     r8d
0x18000a5df  movzx   eax, word ptr [r10+2Ah]
0x18000a5e4  cmp     r8d, eax
0x18000a5e7  jb      short loc_18000A57A
0x18000a5e9  add     rsp, 20h
0x18000a5ed  pop     rbx
0x18000a5ee  retn
0x18000a5ef  mov     [r10+24h], ebx
0x18000a5f3  mov     [r10+28h], bl
0x18000a5f7  mov     [r10+10h], rbx
0x18000a5fb  mov     [r10+18h], rbx
0x18000a5ff  cmp     [r10+2Ah], bx
0x18000a604  jbe     short loc_18000A629
0x18000a606  movzx   eax, word ptr [r10+2Ah]
0x18000a60b  mov     ecx, 20h ; ' '
0x18000a610  dec     eax
0x18000a612  cdq
0x18000a613  idiv    ecx
0x18000a615  mov     rcx, [r10+30h]; void *
0x18000a619  xor     edx, edx; Val
0x18000a61b  inc     eax
0x18000a61d  movsxd  r8, eax
0x18000a620  shl     r8, 2; Size
0x18000a624  call    memset_0
0x18000a629  add     rsp, 20h
0x18000a62d  pop     rbx
0x18000a62e  retn
```
