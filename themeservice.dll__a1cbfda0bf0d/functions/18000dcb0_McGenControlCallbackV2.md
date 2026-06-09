# McGenControlCallbackV2

- ea: `0x18000dcb0`
- end: `0x18000ddaf`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dcb0`
- `0x18000f9da`

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
0x18000dcb0  push    rbx
0x18000dcb2  sub     rsp, 20h
0x18000dcb6  mov     r10, [rsp+28h+CallbackContext]
0x18000dcbb  xor     ebx, ebx
0x18000dcbd  test    r10, r10
0x18000dcc0  jz      loc_18000DDA9
0x18000dcc6  test    edx, edx
0x18000dcc8  jz      loc_18000DD6F
0x18000dcce  cmp     edx, 1
0x18000dcd1  jnz     loc_18000DDA9
0x18000dcd7  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000dcdc  mov     [r10+28h], r8b
0x18000dce0  mov     r8d, ebx
0x18000dce3  mov     [r10+18h], rax
0x18000dce7  mov     [r10+10h], r9
0x18000dceb  mov     [r10+24h], edx
0x18000dcef  cmp     bx, [r10+2Ah]
0x18000dcf4  jnb     loc_18000DDA9
0x18000dcfa  mov     rax, [r10+40h]
0x18000dcfe  mov     cl, [r10+28h]
0x18000dd02  mov     r9d, r8d
0x18000dd05  cmp     [r9+rax], cl
0x18000dd09  jbe     short loc_18000DD0F
0x18000dd0b  test    cl, cl
0x18000dd0d  jnz     short loc_18000DD2F
0x18000dd0f  mov     rax, [r10+38h]
0x18000dd13  mov     rcx, [rax+r9*8]
0x18000dd17  test    rcx, rcx
0x18000dd1a  jz      short loc_18000DD34
0x18000dd1c  test    [r10+10h], rcx
0x18000dd20  jz      short loc_18000DD2F
0x18000dd22  mov     rax, [r10+18h]
0x18000dd26  and     rax, rcx
0x18000dd29  cmp     rax, [r10+18h]
0x18000dd2d  jz      short loc_18000DD34
0x18000dd2f  mov     r11b, bl
0x18000dd32  jmp     short loc_18000DD37
0x18000dd34  mov     r11b, 1
0x18000dd37  mov     rax, [r10+30h]
0x18000dd3b  mov     ecx, r8d
0x18000dd3e  shr     r9, 5
0x18000dd42  mov     edx, 1
0x18000dd47  shl     edx, cl
0x18000dd49  lea     rcx, [rax+r9*4]
0x18000dd4d  test    r11b, r11b
0x18000dd50  jz      short loc_18000DD56
0x18000dd52  or      edx, [rcx]
0x18000dd54  jmp     short loc_18000DD5A
0x18000dd56  not     edx
0x18000dd58  and     edx, [rcx]
0x18000dd5a  mov     [rcx], edx
0x18000dd5c  inc     r8d
0x18000dd5f  movzx   eax, word ptr [r10+2Ah]
0x18000dd64  cmp     r8d, eax
0x18000dd67  jb      short loc_18000DCFA
0x18000dd69  add     rsp, 20h
0x18000dd6d  pop     rbx
0x18000dd6e  retn
0x18000dd6f  mov     [r10+24h], ebx
0x18000dd73  mov     [r10+28h], bl
0x18000dd77  mov     [r10+10h], rbx
0x18000dd7b  mov     [r10+18h], rbx
0x18000dd7f  cmp     [r10+2Ah], bx
0x18000dd84  jbe     short loc_18000DDA9
0x18000dd86  movzx   eax, word ptr [r10+2Ah]
0x18000dd8b  mov     ecx, 20h ; ' '
0x18000dd90  dec     eax
0x18000dd92  cdq
0x18000dd93  idiv    ecx
0x18000dd95  mov     rcx, [r10+30h]; void *
0x18000dd99  xor     edx, edx; Val
0x18000dd9b  inc     eax
0x18000dd9d  movsxd  r8, eax
0x18000dda0  shl     r8, 2; Size
0x18000dda4  call    memset_0
0x18000dda9  add     rsp, 20h
0x18000ddad  pop     rbx
0x18000ddae  retn
```
