# McGenControlCallbackV2

- ea: `0x140004830`
- end: `0x14000492e`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004830`
- `0x140005540`

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
0x140004830  push    rbx
0x140004832  sub     rsp, 20h
0x140004836  mov     r10, [rsp+28h+CallbackContext]
0x14000483b  xor     ebx, ebx
0x14000483d  test    r10, r10
0x140004840  jz      loc_140004927
0x140004846  test    edx, edx
0x140004848  jz      loc_1400048EF
0x14000484e  cmp     edx, 1
0x140004851  jnz     loc_140004927
0x140004857  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000485c  mov     [r10+28h], r8b
0x140004860  mov     r8d, ebx
0x140004863  mov     [r10+18h], rax
0x140004867  mov     [r10+10h], r9
0x14000486b  mov     [r10+24h], edx
0x14000486f  cmp     bx, [r10+2Ah]
0x140004874  jnb     loc_140004927
0x14000487a  mov     rax, [r10+40h]
0x14000487e  mov     cl, [r10+28h]
0x140004882  mov     r9d, r8d
0x140004885  cmp     [r9+rax], cl
0x140004889  jbe     short loc_14000488F
0x14000488b  test    cl, cl
0x14000488d  jnz     short loc_1400048B1
0x14000488f  mov     rax, [r10+38h]
0x140004893  mov     rdx, [rax+r9*8]
0x140004897  test    rdx, rdx
0x14000489a  jz      short loc_1400048B6
0x14000489c  test    [r10+10h], rdx
0x1400048a0  jz      short loc_1400048B1
0x1400048a2  mov     rcx, [r10+18h]
0x1400048a6  mov     rax, rcx
0x1400048a9  and     rax, rdx
0x1400048ac  cmp     rax, rcx
0x1400048af  jz      short loc_1400048B6
0x1400048b1  mov     r11b, bl
0x1400048b4  jmp     short loc_1400048B9
0x1400048b6  mov     r11b, 1
0x1400048b9  mov     rax, [r10+30h]
0x1400048bd  mov     ecx, r8d
0x1400048c0  shr     r9, 5
0x1400048c4  mov     edx, 1
0x1400048c9  shl     edx, cl
0x1400048cb  lea     rcx, [rax+r9*4]
0x1400048cf  mov     eax, [rcx]
0x1400048d1  test    r11b, r11b
0x1400048d4  jz      short loc_1400048DA
0x1400048d6  or      edx, eax
0x1400048d8  jmp     short loc_1400048DE
0x1400048da  not     edx
0x1400048dc  and     edx, eax
0x1400048de  mov     [rcx], edx
0x1400048e0  inc     r8d
0x1400048e3  movzx   eax, word ptr [r10+2Ah]
0x1400048e8  cmp     r8d, eax
0x1400048eb  jb      short loc_14000487A
0x1400048ed  jmp     short loc_140004927
0x1400048ef  movzx   eax, word ptr [r10+2Ah]
0x1400048f4  mov     [r10+24h], ebx
0x1400048f8  mov     [r10+28h], bl
0x1400048fc  mov     [r10+10h], rbx
0x140004900  mov     [r10+18h], rbx
0x140004904  test    ax, ax
0x140004907  jz      short loc_140004927
0x140004909  dec     eax
0x14000490b  mov     ecx, 20h ; ' '
0x140004910  cdq
0x140004911  idiv    ecx
0x140004913  mov     rcx, [r10+30h]; void *
0x140004917  xor     edx, edx; Val
0x140004919  inc     eax
0x14000491b  movsxd  r8, eax
0x14000491e  shl     r8, 2; Size
0x140004922  call    memset
0x140004927  add     rsp, 20h
0x14000492b  pop     rbx
0x14000492c  retn
```
