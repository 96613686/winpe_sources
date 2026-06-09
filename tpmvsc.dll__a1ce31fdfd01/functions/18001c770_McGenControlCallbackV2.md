# McGenControlCallbackV2

- ea: `0x18001c770`
- end: `0x18001c86f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002a90`
- `0x18001c770`

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
0x18001c770  push    rbx
0x18001c772  sub     rsp, 20h
0x18001c776  mov     r10, [rsp+28h+CallbackContext]
0x18001c77b  xor     ebx, ebx
0x18001c77d  test    r10, r10
0x18001c780  jz      loc_18001C869
0x18001c786  test    edx, edx
0x18001c788  jz      loc_18001C82F
0x18001c78e  cmp     edx, 1
0x18001c791  jnz     loc_18001C869
0x18001c797  mov     rax, [rsp+28h+MatchAllKeyword]
0x18001c79c  mov     [r10+28h], r8b
0x18001c7a0  mov     r8d, ebx
0x18001c7a3  mov     [r10+18h], rax
0x18001c7a7  mov     [r10+10h], r9
0x18001c7ab  mov     [r10+24h], edx
0x18001c7af  cmp     bx, [r10+2Ah]
0x18001c7b4  jnb     loc_18001C869
0x18001c7ba  mov     rax, [r10+40h]
0x18001c7be  mov     cl, [r10+28h]
0x18001c7c2  mov     r9d, r8d
0x18001c7c5  cmp     [r9+rax], cl
0x18001c7c9  jbe     short loc_18001C7CF
0x18001c7cb  test    cl, cl
0x18001c7cd  jnz     short loc_18001C7EF
0x18001c7cf  mov     rax, [r10+38h]
0x18001c7d3  mov     rcx, [rax+r9*8]
0x18001c7d7  test    rcx, rcx
0x18001c7da  jz      short loc_18001C7F4
0x18001c7dc  test    [r10+10h], rcx
0x18001c7e0  jz      short loc_18001C7EF
0x18001c7e2  mov     rax, [r10+18h]
0x18001c7e6  and     rax, rcx
0x18001c7e9  cmp     rax, [r10+18h]
0x18001c7ed  jz      short loc_18001C7F4
0x18001c7ef  mov     r11b, bl
0x18001c7f2  jmp     short loc_18001C7F7
0x18001c7f4  mov     r11b, 1
0x18001c7f7  mov     rax, [r10+30h]
0x18001c7fb  mov     ecx, r8d
0x18001c7fe  shr     r9, 5
0x18001c802  mov     edx, 1
0x18001c807  shl     edx, cl
0x18001c809  lea     rcx, [rax+r9*4]
0x18001c80d  test    r11b, r11b
0x18001c810  jz      short loc_18001C816
0x18001c812  or      edx, [rcx]
0x18001c814  jmp     short loc_18001C81A
0x18001c816  not     edx
0x18001c818  and     edx, [rcx]
0x18001c81a  mov     [rcx], edx
0x18001c81c  inc     r8d
0x18001c81f  movzx   eax, word ptr [r10+2Ah]
0x18001c824  cmp     r8d, eax
0x18001c827  jb      short loc_18001C7BA
0x18001c829  add     rsp, 20h
0x18001c82d  pop     rbx
0x18001c82e  retn
0x18001c82f  mov     [r10+24h], ebx
0x18001c833  mov     [r10+28h], bl
0x18001c837  mov     [r10+10h], rbx
0x18001c83b  mov     [r10+18h], rbx
0x18001c83f  cmp     [r10+2Ah], bx
0x18001c844  jbe     short loc_18001C869
0x18001c846  movzx   eax, word ptr [r10+2Ah]
0x18001c84b  mov     ecx, 20h ; ' '
0x18001c850  dec     eax
0x18001c852  cdq
0x18001c853  idiv    ecx
0x18001c855  mov     rcx, [r10+30h]; void *
0x18001c859  xor     edx, edx; Val
0x18001c85b  inc     eax
0x18001c85d  movsxd  r8, eax
0x18001c860  shl     r8, 2; Size
0x18001c864  call    memset_0
0x18001c869  add     rsp, 20h
0x18001c86d  pop     rbx
0x18001c86e  retn
```
