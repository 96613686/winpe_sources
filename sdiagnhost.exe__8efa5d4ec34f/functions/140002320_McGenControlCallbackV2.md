# McGenControlCallbackV2

- ea: `0x140002320`
- end: `0x140002420`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001c8f`
- `0x140002320`

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
0x140002320  push    rbx
0x140002322  sub     rsp, 20h
0x140002326  mov     r10, [rsp+28h+CallbackContext]
0x14000232b  xor     ebx, ebx
0x14000232d  test    r10, r10
0x140002330  jz      loc_14000241A
0x140002336  test    edx, edx
0x140002338  jz      loc_1400023DF
0x14000233e  cmp     edx, 1
0x140002341  jnz     loc_14000241A
0x140002347  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000234c  mov     [r10+28h], r8b
0x140002350  mov     r8d, ebx
0x140002353  mov     [r10+18h], rax
0x140002357  mov     [r10+10h], r9
0x14000235b  mov     [r10+24h], edx
0x14000235f  cmp     bx, [r10+2Ah]
0x140002364  jnb     loc_14000241A
0x14000236a  mov     rax, [r10+40h]
0x14000236e  mov     cl, [r10+28h]
0x140002372  mov     r9d, r8d
0x140002375  cmp     [r9+rax], cl
0x140002379  jbe     short loc_14000237F
0x14000237b  test    cl, cl
0x14000237d  jnz     short loc_14000239F
0x14000237f  mov     rax, [r10+38h]
0x140002383  mov     rcx, [rax+r9*8]
0x140002387  test    rcx, rcx
0x14000238a  jz      short loc_1400023A4
0x14000238c  test    [r10+10h], rcx
0x140002390  jz      short loc_14000239F
0x140002392  mov     rax, [r10+18h]
0x140002396  and     rax, rcx
0x140002399  cmp     rax, [r10+18h]
0x14000239d  jz      short loc_1400023A4
0x14000239f  mov     r11b, bl
0x1400023a2  jmp     short loc_1400023A7
0x1400023a4  mov     r11b, 1
0x1400023a7  mov     rax, [r10+30h]
0x1400023ab  mov     ecx, r8d
0x1400023ae  shr     r9, 5
0x1400023b2  mov     edx, 1
0x1400023b7  shl     edx, cl
0x1400023b9  lea     rcx, [rax+r9*4]
0x1400023bd  test    r11b, r11b
0x1400023c0  jz      short loc_1400023C6
0x1400023c2  or      edx, [rcx]
0x1400023c4  jmp     short loc_1400023CA
0x1400023c6  not     edx
0x1400023c8  and     edx, [rcx]
0x1400023ca  mov     [rcx], edx
0x1400023cc  inc     r8d
0x1400023cf  movzx   eax, word ptr [r10+2Ah]
0x1400023d4  cmp     r8d, eax
0x1400023d7  jb      short loc_14000236A
0x1400023d9  add     rsp, 20h
0x1400023dd  pop     rbx
0x1400023de  retn
0x1400023df  mov     [r10+24h], ebx
0x1400023e3  mov     [r10+28h], bl
0x1400023e7  mov     [r10+10h], rbx
0x1400023eb  mov     [r10+18h], rbx
0x1400023ef  cmp     [r10+2Ah], bx
0x1400023f4  jbe     short loc_14000241A
0x1400023f6  movzx   eax, word ptr [r10+2Ah]
0x1400023fb  mov     rcx, [r10+30h]; void *
0x1400023ff  dec     eax
0x140002401  cdq
0x140002402  and     edx, 1Fh
0x140002405  add     eax, edx
0x140002407  xor     edx, edx; Val
0x140002409  sar     eax, 5
0x14000240c  inc     eax
0x14000240e  movsxd  r8, eax
0x140002411  shl     r8, 2; Size
0x140002415  call    memset_0
0x14000241a  add     rsp, 20h
0x14000241e  pop     rbx
0x14000241f  retn
```
