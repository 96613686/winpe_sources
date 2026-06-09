# McGenControlCallbackV2

- ea: `0x1800084f0`
- end: `0x1800085fc`
- name: `McGenControlCallbackV2`
- size: `268`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800084f0`
- `0x18000c836`

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
  unsigned __int8 v8; // r9
  __int64 v9; // rdx
  bool v10; // r9
  int v11; // edx
  int *v12; // r11
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
          v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
          v10 = (*(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8)
             && (!v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3));
          v11 = 1 << (v7 & 0x1F);
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
0x1800084f0  push    rbx
0x1800084f2  sub     rsp, 20h
0x1800084f6  mov     r10, [rsp+28h+CallbackContext]
0x1800084fb  xor     ebx, ebx
0x1800084fd  test    r10, r10
0x180008500  jz      loc_1800085F5
0x180008506  test    edx, edx
0x180008508  jz      loc_1800085BA
0x18000850e  cmp     edx, 1
0x180008511  jnz     loc_1800085F5
0x180008517  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000851c  mov     [r10+28h], r8b
0x180008520  mov     r8d, ebx
0x180008523  mov     [r10+18h], rax
0x180008527  mov     [r10+10h], r9
0x18000852b  mov     [r10+24h], edx
0x18000852f  cmp     bx, [r10+2Ah]
0x180008534  jnb     loc_1800085F5
0x18000853a  mov     rax, [r10+38h]
0x18000853e  mov     r9b, [r10+28h]
0x180008542  mov     ecx, r8d
0x180008545  mov     rdx, [rax+rcx*8]
0x180008549  mov     rax, [r10+40h]
0x18000854d  cmp     [rcx+rax], r9b
0x180008551  jbe     short loc_180008558
0x180008553  test    r9b, r9b
0x180008556  jnz     short loc_180008570
0x180008558  test    rdx, rdx
0x18000855b  jz      short loc_180008575
0x18000855d  test    [r10+10h], rdx
0x180008561  jz      short loc_180008570
0x180008563  mov     rax, [r10+18h]
0x180008567  and     rax, rdx
0x18000856a  cmp     rax, [r10+18h]
0x18000856e  jz      short loc_180008575
0x180008570  mov     r9b, bl
0x180008573  jmp     short loc_180008578
0x180008575  mov     r9b, 1
0x180008578  mov     rax, [r10+30h]
0x18000857c  mov     ecx, r8d
0x18000857f  and     ecx, 1Fh
0x180008582  mov     edx, 1
0x180008587  shl     edx, cl
0x180008589  mov     ecx, r8d
0x18000858c  shr     rcx, 5
0x180008590  lea     r11, [rax+rcx*4]
0x180008594  test    r9b, r9b
0x180008597  jz      short loc_18000859E
0x180008599  or      edx, [r11]
0x18000859c  jmp     short loc_1800085A3
0x18000859e  not     edx
0x1800085a0  and     edx, [r11]
0x1800085a3  mov     [r11], edx
0x1800085a6  inc     r8d
0x1800085a9  movzx   eax, word ptr [r10+2Ah]
0x1800085ae  cmp     r8d, eax
0x1800085b1  jb      short loc_18000853A
0x1800085b3  add     rsp, 20h
0x1800085b7  pop     rbx
0x1800085b8  retn
0x1800085ba  mov     [r10+24h], ebx
0x1800085be  mov     [r10+28h], bl
0x1800085c2  mov     [r10+10h], rbx
0x1800085c6  mov     [r10+18h], rbx
0x1800085ca  cmp     [r10+2Ah], bx
0x1800085cf  jbe     short loc_1800085F5
0x1800085d1  movzx   eax, word ptr [r10+2Ah]
0x1800085d6  mov     rcx, [r10+30h]; void *
0x1800085da  dec     eax
0x1800085dc  cdq
0x1800085dd  and     edx, 1Fh
0x1800085e0  add     eax, edx
0x1800085e2  xor     edx, edx; Val
0x1800085e4  sar     eax, 5
0x1800085e7  inc     eax
0x1800085e9  movsxd  r8, eax
0x1800085ec  shl     r8, 2; Size
0x1800085f0  call    memset_0
0x1800085f5  add     rsp, 20h
0x1800085f9  pop     rbx
0x1800085fa  retn
```
