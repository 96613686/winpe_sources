# McGenControlCallbackV2

- ea: `0x18000d610`
- end: `0x18000d710`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d610`
- `0x18000e97a`

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
0x18000d610  push    rbx
0x18000d612  sub     rsp, 20h
0x18000d616  mov     r10, [rsp+28h+CallbackContext]
0x18000d61b  xor     ebx, ebx
0x18000d61d  test    r10, r10
0x18000d620  jz      loc_18000D70A
0x18000d626  test    edx, edx
0x18000d628  jz      loc_18000D6CF
0x18000d62e  cmp     edx, 1
0x18000d631  jnz     loc_18000D70A
0x18000d637  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000d63c  mov     [r10+28h], r8b
0x18000d640  mov     r8d, ebx
0x18000d643  mov     [r10+18h], rax
0x18000d647  mov     [r10+10h], r9
0x18000d64b  mov     [r10+24h], edx
0x18000d64f  cmp     bx, [r10+2Ah]
0x18000d654  jnb     loc_18000D70A
0x18000d65a  mov     rax, [r10+40h]
0x18000d65e  mov     cl, [r10+28h]
0x18000d662  mov     r9d, r8d
0x18000d665  cmp     [r9+rax], cl
0x18000d669  jbe     short loc_18000D66F
0x18000d66b  test    cl, cl
0x18000d66d  jnz     short loc_18000D68F
0x18000d66f  mov     rax, [r10+38h]
0x18000d673  mov     rcx, [rax+r9*8]
0x18000d677  test    rcx, rcx
0x18000d67a  jz      short loc_18000D694
0x18000d67c  test    [r10+10h], rcx
0x18000d680  jz      short loc_18000D68F
0x18000d682  mov     rax, [r10+18h]
0x18000d686  and     rax, rcx
0x18000d689  cmp     rax, [r10+18h]
0x18000d68d  jz      short loc_18000D694
0x18000d68f  mov     r11b, bl
0x18000d692  jmp     short loc_18000D697
0x18000d694  mov     r11b, 1
0x18000d697  mov     rax, [r10+30h]
0x18000d69b  mov     ecx, r8d
0x18000d69e  shr     r9, 5
0x18000d6a2  mov     edx, 1
0x18000d6a7  shl     edx, cl
0x18000d6a9  lea     rcx, [rax+r9*4]
0x18000d6ad  test    r11b, r11b
0x18000d6b0  jz      short loc_18000D6B6
0x18000d6b2  or      edx, [rcx]
0x18000d6b4  jmp     short loc_18000D6BA
0x18000d6b6  not     edx
0x18000d6b8  and     edx, [rcx]
0x18000d6ba  mov     [rcx], edx
0x18000d6bc  inc     r8d
0x18000d6bf  movzx   eax, word ptr [r10+2Ah]
0x18000d6c4  cmp     r8d, eax
0x18000d6c7  jb      short loc_18000D65A
0x18000d6c9  add     rsp, 20h
0x18000d6cd  pop     rbx
0x18000d6ce  retn
0x18000d6cf  mov     [r10+24h], ebx
0x18000d6d3  mov     [r10+28h], bl
0x18000d6d7  mov     [r10+10h], rbx
0x18000d6db  mov     [r10+18h], rbx
0x18000d6df  cmp     [r10+2Ah], bx
0x18000d6e4  jbe     short loc_18000D70A
0x18000d6e6  movzx   eax, word ptr [r10+2Ah]
0x18000d6eb  mov     rcx, [r10+30h]; void *
0x18000d6ef  dec     eax
0x18000d6f1  cdq
0x18000d6f2  and     edx, 1Fh
0x18000d6f5  add     eax, edx
0x18000d6f7  xor     edx, edx; Val
0x18000d6f9  sar     eax, 5
0x18000d6fc  inc     eax
0x18000d6fe  movsxd  r8, eax
0x18000d701  shl     r8, 2; Size
0x18000d705  call    memset_0
0x18000d70a  add     rsp, 20h
0x18000d70e  pop     rbx
0x18000d70f  retn
```
