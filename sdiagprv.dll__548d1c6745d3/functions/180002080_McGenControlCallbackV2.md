# McGenControlCallbackV2

- ea: `0x180002080`
- end: `0x18000217f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002080`
- `0x1800180be`

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
0x180002080  push    rbx
0x180002082  sub     rsp, 20h
0x180002086  mov     r10, [rsp+28h+CallbackContext]
0x18000208b  xor     ebx, ebx
0x18000208d  test    r10, r10
0x180002090  jz      loc_180002179
0x180002096  test    edx, edx
0x180002098  jz      loc_18000213F
0x18000209e  cmp     edx, 1
0x1800020a1  jnz     loc_180002179
0x1800020a7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800020ac  mov     [r10+28h], r8b
0x1800020b0  mov     r8d, ebx
0x1800020b3  mov     [r10+18h], rax
0x1800020b7  mov     [r10+10h], r9
0x1800020bb  mov     [r10+24h], edx
0x1800020bf  cmp     bx, [r10+2Ah]
0x1800020c4  jnb     loc_180002179
0x1800020ca  mov     rax, [r10+40h]
0x1800020ce  mov     cl, [r10+28h]
0x1800020d2  mov     r9d, r8d
0x1800020d5  cmp     [r9+rax], cl
0x1800020d9  jbe     short loc_1800020DF
0x1800020db  test    cl, cl
0x1800020dd  jnz     short loc_1800020FF
0x1800020df  mov     rax, [r10+38h]
0x1800020e3  mov     rcx, [rax+r9*8]
0x1800020e7  test    rcx, rcx
0x1800020ea  jz      short loc_180002104
0x1800020ec  test    [r10+10h], rcx
0x1800020f0  jz      short loc_1800020FF
0x1800020f2  mov     rax, [r10+18h]
0x1800020f6  and     rax, rcx
0x1800020f9  cmp     rax, [r10+18h]
0x1800020fd  jz      short loc_180002104
0x1800020ff  mov     r11b, bl
0x180002102  jmp     short loc_180002107
0x180002104  mov     r11b, 1
0x180002107  mov     rax, [r10+30h]
0x18000210b  mov     ecx, r8d
0x18000210e  shr     r9, 5
0x180002112  mov     edx, 1
0x180002117  shl     edx, cl
0x180002119  lea     rcx, [rax+r9*4]
0x18000211d  test    r11b, r11b
0x180002120  jz      short loc_180002126
0x180002122  or      edx, [rcx]
0x180002124  jmp     short loc_18000212A
0x180002126  not     edx
0x180002128  and     edx, [rcx]
0x18000212a  mov     [rcx], edx
0x18000212c  inc     r8d
0x18000212f  movzx   eax, word ptr [r10+2Ah]
0x180002134  cmp     r8d, eax
0x180002137  jb      short loc_1800020CA
0x180002139  add     rsp, 20h
0x18000213d  pop     rbx
0x18000213e  retn
0x18000213f  mov     [r10+24h], ebx
0x180002143  mov     [r10+28h], bl
0x180002147  mov     [r10+10h], rbx
0x18000214b  mov     [r10+18h], rbx
0x18000214f  cmp     [r10+2Ah], bx
0x180002154  jbe     short loc_180002179
0x180002156  movzx   eax, word ptr [r10+2Ah]
0x18000215b  mov     ecx, 20h ; ' '
0x180002160  dec     eax
0x180002162  cdq
0x180002163  idiv    ecx
0x180002165  mov     rcx, [r10+30h]; void *
0x180002169  xor     edx, edx; Val
0x18000216b  inc     eax
0x18000216d  movsxd  r8, eax
0x180002170  shl     r8, 2; Size
0x180002174  call    memset_0
0x180002179  add     rsp, 20h
0x18000217d  pop     rbx
0x18000217e  retn
```
