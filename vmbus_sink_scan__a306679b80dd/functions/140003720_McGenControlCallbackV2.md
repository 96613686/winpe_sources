# McGenControlCallbackV2

- ea: `0x140003720`
- end: `0x14000381e`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003720`
- `0x140017540`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
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
          v13 = *v12;
          if ( v10 )
            v14 = v13 | v11;
          else
            v14 = v13 & ~v11;
          *v12 = v14;
        }
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x140003720  push    rbx
0x140003722  sub     rsp, 20h
0x140003726  mov     r10, [rsp+28h+CallbackContext]
0x14000372b  xor     ebx, ebx
0x14000372d  test    r10, r10
0x140003730  jz      loc_140003817
0x140003736  test    edx, edx
0x140003738  jz      loc_1400037DF
0x14000373e  cmp     edx, 1
0x140003741  jnz     loc_140003817
0x140003747  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000374c  mov     [r10+28h], r8b
0x140003750  mov     r8d, ebx
0x140003753  mov     [r10+18h], rax
0x140003757  mov     [r10+10h], r9
0x14000375b  mov     [r10+24h], edx
0x14000375f  cmp     bx, [r10+2Ah]
0x140003764  jnb     loc_140003817
0x14000376a  mov     rax, [r10+40h]
0x14000376e  mov     cl, [r10+28h]
0x140003772  mov     r9d, r8d
0x140003775  cmp     [r9+rax], cl
0x140003779  jbe     short loc_14000377F
0x14000377b  test    cl, cl
0x14000377d  jnz     short loc_1400037A1
0x14000377f  mov     rax, [r10+38h]
0x140003783  mov     rdx, [rax+r9*8]
0x140003787  test    rdx, rdx
0x14000378a  jz      short loc_1400037A6
0x14000378c  test    [r10+10h], rdx
0x140003790  jz      short loc_1400037A1
0x140003792  mov     rcx, [r10+18h]
0x140003796  mov     rax, rcx
0x140003799  and     rax, rdx
0x14000379c  cmp     rax, rcx
0x14000379f  jz      short loc_1400037A6
0x1400037a1  mov     r11b, bl
0x1400037a4  jmp     short loc_1400037A9
0x1400037a6  mov     r11b, 1
0x1400037a9  mov     rax, [r10+30h]
0x1400037ad  mov     ecx, r8d
0x1400037b0  shr     r9, 5
0x1400037b4  mov     edx, 1
0x1400037b9  shl     edx, cl
0x1400037bb  lea     rcx, [rax+r9*4]
0x1400037bf  mov     eax, [rcx]
0x1400037c1  test    r11b, r11b
0x1400037c4  jz      short loc_1400037CA
0x1400037c6  or      edx, eax
0x1400037c8  jmp     short loc_1400037CE
0x1400037ca  not     edx
0x1400037cc  and     edx, eax
0x1400037ce  mov     [rcx], edx
0x1400037d0  inc     r8d
0x1400037d3  movzx   eax, word ptr [r10+2Ah]
0x1400037d8  cmp     r8d, eax
0x1400037db  jb      short loc_14000376A
0x1400037dd  jmp     short loc_140003817
0x1400037df  movzx   eax, word ptr [r10+2Ah]
0x1400037e4  mov     [r10+24h], ebx
0x1400037e8  mov     [r10+28h], bl
0x1400037ec  mov     [r10+10h], rbx
0x1400037f0  mov     [r10+18h], rbx
0x1400037f4  test    ax, ax
0x1400037f7  jz      short loc_140003817
0x1400037f9  dec     eax
0x1400037fb  mov     ecx, 20h ; ' '
0x140003800  cdq
0x140003801  idiv    ecx
0x140003803  mov     rcx, [r10+30h]; void *
0x140003807  xor     edx, edx; Val
0x140003809  inc     eax
0x14000380b  movsxd  r8, eax
0x14000380e  shl     r8, 2; Size
0x140003812  call    memset
0x140003817  add     rsp, 20h
0x14000381b  pop     rbx
0x14000381c  retn
```
