# McGenControlCallbackV2

- ea: `0x180005d70`
- end: `0x180005e70`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000209e`
- `0x180005d70`

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
0x180005d70  push    rbx
0x180005d72  sub     rsp, 20h
0x180005d76  mov     r10, [rsp+28h+CallbackContext]
0x180005d7b  xor     ebx, ebx
0x180005d7d  test    r10, r10
0x180005d80  jz      loc_180005E6A
0x180005d86  test    edx, edx
0x180005d88  jz      loc_180005E2F
0x180005d8e  cmp     edx, 1
0x180005d91  jnz     loc_180005E6A
0x180005d97  mov     rax, [rsp+28h+MatchAllKeyword]
0x180005d9c  mov     [r10+28h], r8b
0x180005da0  mov     r8d, ebx
0x180005da3  mov     [r10+18h], rax
0x180005da7  mov     [r10+10h], r9
0x180005dab  mov     [r10+24h], edx
0x180005daf  cmp     bx, [r10+2Ah]
0x180005db4  jnb     loc_180005E6A
0x180005dba  mov     rax, [r10+40h]
0x180005dbe  mov     cl, [r10+28h]
0x180005dc2  mov     r9d, r8d
0x180005dc5  cmp     [r9+rax], cl
0x180005dc9  jbe     short loc_180005DCF
0x180005dcb  test    cl, cl
0x180005dcd  jnz     short loc_180005DEF
0x180005dcf  mov     rax, [r10+38h]
0x180005dd3  mov     rcx, [rax+r9*8]
0x180005dd7  test    rcx, rcx
0x180005dda  jz      short loc_180005DF4
0x180005ddc  test    [r10+10h], rcx
0x180005de0  jz      short loc_180005DEF
0x180005de2  mov     rax, [r10+18h]
0x180005de6  and     rax, rcx
0x180005de9  cmp     rax, [r10+18h]
0x180005ded  jz      short loc_180005DF4
0x180005def  mov     r11b, bl
0x180005df2  jmp     short loc_180005DF7
0x180005df4  mov     r11b, 1
0x180005df7  mov     rax, [r10+30h]
0x180005dfb  mov     ecx, r8d
0x180005dfe  shr     r9, 5
0x180005e02  mov     edx, 1
0x180005e07  shl     edx, cl
0x180005e09  lea     rcx, [rax+r9*4]
0x180005e0d  test    r11b, r11b
0x180005e10  jz      short loc_180005E16
0x180005e12  or      edx, [rcx]
0x180005e14  jmp     short loc_180005E1A
0x180005e16  not     edx
0x180005e18  and     edx, [rcx]
0x180005e1a  mov     [rcx], edx
0x180005e1c  inc     r8d
0x180005e1f  movzx   eax, word ptr [r10+2Ah]
0x180005e24  cmp     r8d, eax
0x180005e27  jb      short loc_180005DBA
0x180005e29  add     rsp, 20h
0x180005e2d  pop     rbx
0x180005e2e  retn
0x180005e2f  mov     [r10+24h], ebx
0x180005e33  mov     [r10+28h], bl
0x180005e37  mov     [r10+10h], rbx
0x180005e3b  mov     [r10+18h], rbx
0x180005e3f  cmp     [r10+2Ah], bx
0x180005e44  jbe     short loc_180005E6A
0x180005e46  movzx   eax, word ptr [r10+2Ah]
0x180005e4b  mov     rcx, [r10+30h]; void *
0x180005e4f  dec     eax
0x180005e51  cdq
0x180005e52  and     edx, 1Fh
0x180005e55  add     eax, edx
0x180005e57  xor     edx, edx; Val
0x180005e59  sar     eax, 5
0x180005e5c  inc     eax
0x180005e5e  movsxd  r8, eax
0x180005e61  shl     r8, 2; Size
0x180005e65  call    memset_0
0x180005e6a  add     rsp, 20h
0x180005e6e  pop     rbx
0x180005e6f  retn
```
