# McGenControlCallbackV2

- ea: `0x18000f1b0`
- end: `0x18000f2bc`
- name: `McGenControlCallbackV2`
- size: `268`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f1b0`
- `0x18001c12a`

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
0x18000f1b0  push    rbx
0x18000f1b2  sub     rsp, 20h
0x18000f1b6  mov     r10, [rsp+28h+CallbackContext]
0x18000f1bb  xor     ebx, ebx
0x18000f1bd  test    r10, r10
0x18000f1c0  jz      loc_18000F2B5
0x18000f1c6  test    edx, edx
0x18000f1c8  jz      loc_18000F27A
0x18000f1ce  cmp     edx, 1
0x18000f1d1  jnz     loc_18000F2B5
0x18000f1d7  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000f1dc  mov     [r10+28h], r8b
0x18000f1e0  mov     r8d, ebx
0x18000f1e3  mov     [r10+18h], rax
0x18000f1e7  mov     [r10+10h], r9
0x18000f1eb  mov     [r10+24h], edx
0x18000f1ef  cmp     bx, [r10+2Ah]
0x18000f1f4  jnb     loc_18000F2B5
0x18000f1fa  mov     rax, [r10+38h]
0x18000f1fe  mov     r9b, [r10+28h]
0x18000f202  mov     ecx, r8d
0x18000f205  mov     rdx, [rax+rcx*8]
0x18000f209  mov     rax, [r10+40h]
0x18000f20d  cmp     [rcx+rax], r9b
0x18000f211  jbe     short loc_18000F218
0x18000f213  test    r9b, r9b
0x18000f216  jnz     short loc_18000F230
0x18000f218  test    rdx, rdx
0x18000f21b  jz      short loc_18000F235
0x18000f21d  test    [r10+10h], rdx
0x18000f221  jz      short loc_18000F230
0x18000f223  mov     rax, [r10+18h]
0x18000f227  and     rax, rdx
0x18000f22a  cmp     rax, [r10+18h]
0x18000f22e  jz      short loc_18000F235
0x18000f230  mov     r9b, bl
0x18000f233  jmp     short loc_18000F238
0x18000f235  mov     r9b, 1
0x18000f238  mov     rax, [r10+30h]
0x18000f23c  mov     ecx, r8d
0x18000f23f  and     ecx, 1Fh
0x18000f242  mov     edx, 1
0x18000f247  shl     edx, cl
0x18000f249  mov     ecx, r8d
0x18000f24c  shr     rcx, 5
0x18000f250  lea     r11, [rax+rcx*4]
0x18000f254  test    r9b, r9b
0x18000f257  jz      short loc_18000F25E
0x18000f259  or      edx, [r11]
0x18000f25c  jmp     short loc_18000F263
0x18000f25e  not     edx
0x18000f260  and     edx, [r11]
0x18000f263  mov     [r11], edx
0x18000f266  inc     r8d
0x18000f269  movzx   eax, word ptr [r10+2Ah]
0x18000f26e  cmp     r8d, eax
0x18000f271  jb      short loc_18000F1FA
0x18000f273  add     rsp, 20h
0x18000f277  pop     rbx
0x18000f278  retn
0x18000f27a  mov     [r10+24h], ebx
0x18000f27e  mov     [r10+28h], bl
0x18000f282  mov     [r10+10h], rbx
0x18000f286  mov     [r10+18h], rbx
0x18000f28a  cmp     [r10+2Ah], bx
0x18000f28f  jbe     short loc_18000F2B5
0x18000f291  movzx   eax, word ptr [r10+2Ah]
0x18000f296  mov     rcx, [r10+30h]; void *
0x18000f29a  dec     eax
0x18000f29c  cdq
0x18000f29d  and     edx, 1Fh
0x18000f2a0  add     eax, edx
0x18000f2a2  xor     edx, edx; Val
0x18000f2a4  sar     eax, 5
0x18000f2a7  inc     eax
0x18000f2a9  movsxd  r8, eax
0x18000f2ac  shl     r8, 2; Size
0x18000f2b0  call    memset_0
0x18000f2b5  add     rsp, 20h
0x18000f2b9  pop     rbx
0x18000f2ba  retn
```
