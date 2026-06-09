# McGenControlCallbackV2

- ea: `0x140001380`
- end: `0x14000147f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001380`
- `0x140001b40`

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
0x140001380  push    rbx
0x140001382  sub     rsp, 20h
0x140001386  mov     r10, [rsp+28h+CallbackContext]
0x14000138b  xor     ebx, ebx
0x14000138d  test    r10, r10
0x140001390  jz      loc_140001478
0x140001396  test    edx, edx
0x140001398  jz      loc_14000143F
0x14000139e  cmp     edx, 1
0x1400013a1  jnz     loc_140001478
0x1400013a7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400013ac  mov     [r10+28h], r8b
0x1400013b0  mov     r8d, ebx
0x1400013b3  mov     [r10+18h], rax
0x1400013b7  mov     [r10+10h], r9
0x1400013bb  mov     [r10+24h], edx
0x1400013bf  cmp     bx, [r10+2Ah]
0x1400013c4  jnb     loc_140001478
0x1400013ca  mov     rax, [r10+40h]
0x1400013ce  mov     cl, [r10+28h]
0x1400013d2  mov     r9d, r8d
0x1400013d5  cmp     [r9+rax], cl
0x1400013d9  jbe     short loc_1400013DF
0x1400013db  test    cl, cl
0x1400013dd  jnz     short loc_140001401
0x1400013df  mov     rax, [r10+38h]
0x1400013e3  mov     rdx, [rax+r9*8]
0x1400013e7  test    rdx, rdx
0x1400013ea  jz      short loc_140001406
0x1400013ec  test    [r10+10h], rdx
0x1400013f0  jz      short loc_140001401
0x1400013f2  mov     rcx, [r10+18h]
0x1400013f6  mov     rax, rcx
0x1400013f9  and     rax, rdx
0x1400013fc  cmp     rax, rcx
0x1400013ff  jz      short loc_140001406
0x140001401  mov     r11b, bl
0x140001404  jmp     short loc_140001409
0x140001406  mov     r11b, 1
0x140001409  mov     rax, [r10+30h]
0x14000140d  mov     ecx, r8d
0x140001410  shr     r9, 5
0x140001414  mov     edx, 1
0x140001419  shl     edx, cl
0x14000141b  lea     rcx, [rax+r9*4]
0x14000141f  mov     eax, [rcx]
0x140001421  test    r11b, r11b
0x140001424  jz      short loc_14000142A
0x140001426  or      edx, eax
0x140001428  jmp     short loc_14000142E
0x14000142a  not     edx
0x14000142c  and     edx, eax
0x14000142e  mov     [rcx], edx
0x140001430  inc     r8d
0x140001433  movzx   eax, word ptr [r10+2Ah]
0x140001438  cmp     r8d, eax
0x14000143b  jb      short loc_1400013CA
0x14000143d  jmp     short loc_140001478
0x14000143f  movzx   eax, word ptr [r10+2Ah]
0x140001444  mov     [r10+24h], ebx
0x140001448  mov     [r10+28h], bl
0x14000144c  mov     [r10+10h], rbx
0x140001450  mov     [r10+18h], rbx
0x140001454  test    ax, ax
0x140001457  jz      short loc_140001478
0x140001459  mov     rcx, [r10+30h]; void *
0x14000145d  dec     eax
0x14000145f  cdq
0x140001460  and     edx, 1Fh
0x140001463  add     eax, edx
0x140001465  xor     edx, edx; Val
0x140001467  sar     eax, 5
0x14000146a  inc     eax
0x14000146c  movsxd  r8, eax
0x14000146f  shl     r8, 2; Size
0x140001473  call    memset
0x140001478  add     rsp, 20h
0x14000147c  pop     rbx
0x14000147d  retn
```
