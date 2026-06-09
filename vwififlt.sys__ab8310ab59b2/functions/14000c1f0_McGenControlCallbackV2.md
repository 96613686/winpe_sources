# McGenControlCallbackV2

- ea: `0x14000c1f0`
- end: `0x14000c2ea`
- name: `McGenControlCallbackV2`
- size: `250`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000c1f0`
- `0x14000f500`

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
0x14000c1f0  push    rbx
0x14000c1f2  sub     rsp, 20h
0x14000c1f6  mov     r10, [rsp+28h+CallbackContext]
0x14000c1fb  xor     ebx, ebx
0x14000c1fd  test    r10, r10
0x14000c200  jz      loc_14000C29A
0x14000c206  test    edx, edx
0x14000c208  jz      loc_14000C2B0
0x14000c20e  cmp     edx, 1
0x14000c211  jnz     loc_14000C29A
0x14000c217  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000c21c  mov     [r10+28h], r8b
0x14000c220  mov     r8d, ebx
0x14000c223  mov     [r10+18h], rax
0x14000c227  mov     [r10+10h], r9
0x14000c22b  mov     [r10+24h], edx
0x14000c22f  cmp     bx, [r10+2Ah]
0x14000c234  jnb     short loc_14000C29A
0x14000c236  mov     rax, [r10+40h]
0x14000c23a  mov     cl, [r10+28h]
0x14000c23e  mov     r9d, r8d
0x14000c241  cmp     [r9+rax], cl
0x14000c245  ja      short loc_14000C2A7
0x14000c247  mov     rax, [r10+38h]
0x14000c24b  mov     rdx, [rax+r9*8]
0x14000c24f  test    rdx, rdx
0x14000c252  jz      short loc_14000C269
0x14000c254  test    [r10+10h], rdx
0x14000c258  jz      short loc_14000C2AB
0x14000c25a  mov     rcx, [r10+18h]
0x14000c25e  mov     rax, rcx
0x14000c261  and     rax, rdx
0x14000c264  cmp     rax, rcx
0x14000c267  jnz     short loc_14000C2AB
0x14000c269  mov     r11b, 1
0x14000c26c  mov     rax, [r10+30h]
0x14000c270  mov     ecx, r8d
0x14000c273  shr     r9, 5
0x14000c277  mov     edx, 1
0x14000c27c  shl     edx, cl
0x14000c27e  lea     rcx, [rax+r9*4]
0x14000c282  mov     eax, [rcx]
0x14000c284  test    r11b, r11b
0x14000c287  jz      short loc_14000C2A1
0x14000c289  or      edx, eax
0x14000c28b  mov     [rcx], edx
0x14000c28d  inc     r8d
0x14000c290  movzx   eax, word ptr [r10+2Ah]
0x14000c295  cmp     r8d, eax
0x14000c298  jb      short loc_14000C236
0x14000c29a  add     rsp, 20h
0x14000c29e  pop     rbx
0x14000c29f  retn
0x14000c2a1  not     edx
0x14000c2a3  and     edx, eax
0x14000c2a5  jmp     short loc_14000C28B
0x14000c2a7  test    cl, cl
0x14000c2a9  jz      short loc_14000C247
0x14000c2ab  mov     r11b, bl
0x14000c2ae  jmp     short loc_14000C26C
0x14000c2b0  movzx   eax, word ptr [r10+2Ah]
0x14000c2b5  mov     [r10+24h], ebx
0x14000c2b9  mov     [r10+28h], bl
0x14000c2bd  mov     [r10+10h], rbx
0x14000c2c1  mov     [r10+18h], rbx
0x14000c2c5  test    ax, ax
0x14000c2c8  jz      short loc_14000C29A
0x14000c2ca  dec     eax
0x14000c2cc  mov     ecx, 20h ; ' '
0x14000c2d1  cdq
0x14000c2d2  idiv    ecx
0x14000c2d4  mov     rcx, [r10+30h]; void *
0x14000c2d8  xor     edx, edx; Val
0x14000c2da  inc     eax
0x14000c2dc  movsxd  r8, eax
0x14000c2df  shl     r8, 2; Size
0x14000c2e3  call    memset
0x14000c2e8  jmp     short loc_14000C29A
```
