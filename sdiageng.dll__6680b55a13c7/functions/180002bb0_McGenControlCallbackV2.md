# McGenControlCallbackV2

- ea: `0x180002bb0`
- end: `0x180002cb0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002bb0`
- `0x180029882`

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
0x180002bb0  push    rbx
0x180002bb2  sub     rsp, 20h
0x180002bb6  mov     r10, [rsp+28h+CallbackContext]
0x180002bbb  xor     ebx, ebx
0x180002bbd  test    r10, r10
0x180002bc0  jz      loc_180002CAA
0x180002bc6  test    edx, edx
0x180002bc8  jz      loc_180002C6F
0x180002bce  cmp     edx, 1
0x180002bd1  jnz     loc_180002CAA
0x180002bd7  mov     rax, [rsp+28h+MatchAllKeyword]
0x180002bdc  mov     [r10+28h], r8b
0x180002be0  mov     r8d, ebx
0x180002be3  mov     [r10+18h], rax
0x180002be7  mov     [r10+10h], r9
0x180002beb  mov     [r10+24h], edx
0x180002bef  cmp     bx, [r10+2Ah]
0x180002bf4  jnb     loc_180002CAA
0x180002bfa  mov     rax, [r10+40h]
0x180002bfe  mov     cl, [r10+28h]
0x180002c02  mov     r9d, r8d
0x180002c05  cmp     [r9+rax], cl
0x180002c09  jbe     short loc_180002C0F
0x180002c0b  test    cl, cl
0x180002c0d  jnz     short loc_180002C2F
0x180002c0f  mov     rax, [r10+38h]
0x180002c13  mov     rcx, [rax+r9*8]
0x180002c17  test    rcx, rcx
0x180002c1a  jz      short loc_180002C34
0x180002c1c  test    [r10+10h], rcx
0x180002c20  jz      short loc_180002C2F
0x180002c22  mov     rax, [r10+18h]
0x180002c26  and     rax, rcx
0x180002c29  cmp     rax, [r10+18h]
0x180002c2d  jz      short loc_180002C34
0x180002c2f  mov     r11b, bl
0x180002c32  jmp     short loc_180002C37
0x180002c34  mov     r11b, 1
0x180002c37  mov     rax, [r10+30h]
0x180002c3b  mov     ecx, r8d
0x180002c3e  shr     r9, 5
0x180002c42  mov     edx, 1
0x180002c47  shl     edx, cl
0x180002c49  lea     rcx, [rax+r9*4]
0x180002c4d  test    r11b, r11b
0x180002c50  jz      short loc_180002C56
0x180002c52  or      edx, [rcx]
0x180002c54  jmp     short loc_180002C5A
0x180002c56  not     edx
0x180002c58  and     edx, [rcx]
0x180002c5a  mov     [rcx], edx
0x180002c5c  inc     r8d
0x180002c5f  movzx   eax, word ptr [r10+2Ah]
0x180002c64  cmp     r8d, eax
0x180002c67  jb      short loc_180002BFA
0x180002c69  add     rsp, 20h
0x180002c6d  pop     rbx
0x180002c6e  retn
0x180002c6f  mov     [r10+24h], ebx
0x180002c73  mov     [r10+28h], bl
0x180002c77  mov     [r10+10h], rbx
0x180002c7b  mov     [r10+18h], rbx
0x180002c7f  cmp     [r10+2Ah], bx
0x180002c84  jbe     short loc_180002CAA
0x180002c86  movzx   eax, word ptr [r10+2Ah]
0x180002c8b  mov     rcx, [r10+30h]; void *
0x180002c8f  dec     eax
0x180002c91  cdq
0x180002c92  and     edx, 1Fh
0x180002c95  add     eax, edx
0x180002c97  xor     edx, edx; Val
0x180002c99  sar     eax, 5
0x180002c9c  inc     eax
0x180002c9e  movsxd  r8, eax
0x180002ca1  shl     r8, 2; Size
0x180002ca5  call    memset_0
0x180002caa  add     rsp, 20h
0x180002cae  pop     rbx
0x180002caf  retn
```
