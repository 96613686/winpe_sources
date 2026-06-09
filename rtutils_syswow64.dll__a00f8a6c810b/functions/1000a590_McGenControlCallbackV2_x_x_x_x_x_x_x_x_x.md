# McGenControlCallbackV2(x,x,x,x,x,x,x,x,x)

- ea: `0x1000a590`
- end: `0x1000a69b`
- name: `_McGenControlCallbackV2@36`
- size: `267`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x10004567`
- `0x1000a590`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        unsigned __int16 *CallbackContext)
{
  unsigned int v7; // edx
  int v8; // eax
  unsigned __int8 v9; // cl
  int v10; // edi
  int v11; // ebx
  bool v12; // bl
  char v13; // di
  int *v14; // ecx
  int v15; // eax
  int v16; // eax
  int v17; // eax

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        v7 = 0;
        *((_BYTE *)CallbackContext + 40) = Level;
        *((_DWORD *)CallbackContext + 4) = MatchAnyKeyword;
        *((_DWORD *)CallbackContext + 6) = MatchAllKeyword;
        *((_DWORD *)CallbackContext + 5) = HIDWORD(MatchAnyKeyword);
        *((_DWORD *)CallbackContext + 7) = HIDWORD(MatchAllKeyword);
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < CallbackContext[21]; ++v7 )
        {
          v8 = *((_DWORD *)CallbackContext + 12);
          v9 = *((_BYTE *)CallbackContext + 40);
          v10 = *(_DWORD *)(v8 + 8 * v7);
          v11 = *(_DWORD *)(v8 + 8 * v7 + 4);
          v12 = (*(_BYTE *)(v7 + *((_DWORD *)CallbackContext + 13)) <= v9 || !v9)
             && (!(v11 | v10)
              || v11 & *((_DWORD *)CallbackContext + 5) | *((_DWORD *)CallbackContext + 4) & v10
              && (v10 & *((_DWORD *)CallbackContext + 6)) == *((_DWORD *)CallbackContext + 6)
              && (v11 & *((_DWORD *)CallbackContext + 7)) == *((_DWORD *)CallbackContext + 7));
          v13 = v7 & 0x1F;
          v14 = (int *)(*((_DWORD *)CallbackContext + 11) + 4 * (v7 >> 5));
          v15 = *v14;
          if ( v12 )
            v16 = v15 | (1 << v13);
          else
            v16 = v15 & ~(1 << v13);
          *v14 = v16;
        }
      }
    }
    else
    {
      v17 = CallbackContext[21];
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_DWORD *)CallbackContext + 4) = 0;
      *((_DWORD *)CallbackContext + 5) = 0;
      *((_DWORD *)CallbackContext + 6) = 0;
      *((_DWORD *)CallbackContext + 7) = 0;
      if ( (_WORD)v17 )
        memset(*((void **)CallbackContext + 11), 0, 4 * ((v17 - 1) / 32) + 4);
    }
  }
}

```

## disassembly

```asm
0x1000a590  mov     edi, edi
0x1000a592  push    ebp
0x1000a593  mov     ebp, esp
0x1000a595  push    esi
0x1000a596  mov     esi, [ebp+CallbackContext]
0x1000a599  test    esi, esi
0x1000a59b  jz      loc_1000A696
0x1000a5a1  mov     eax, [ebp+IsEnabled]
0x1000a5a4  push    ebx
0x1000a5a5  xor     ebx, ebx
0x1000a5a7  sub     eax, ebx
0x1000a5a9  jz      loc_1000A65F
0x1000a5af  sub     eax, 1
0x1000a5b2  jnz     loc_1000A695
0x1000a5b8  mov     al, [ebp+Level]
0x1000a5bb  mov     edx, ebx
0x1000a5bd  mov     ecx, dword ptr [ebp+MatchAnyKeyword+4]
0x1000a5c0  mov     [esi+28h], al
0x1000a5c3  mov     eax, dword ptr [ebp+MatchAnyKeyword]
0x1000a5c6  mov     [esi+10h], eax
0x1000a5c9  mov     eax, dword ptr [ebp+MatchAllKeyword]
0x1000a5cc  mov     [esi+18h], eax
0x1000a5cf  xor     eax, eax
0x1000a5d1  mov     [esi+14h], ecx
0x1000a5d4  mov     ecx, dword ptr [ebp+MatchAllKeyword+4]
0x1000a5d7  mov     [esi+1Ch], ecx
0x1000a5da  mov     dword ptr [esi+24h], 1
0x1000a5e1  cmp     ax, [esi+2Ah]
0x1000a5e5  jnb     loc_1000A695
0x1000a5eb  push    edi
0x1000a5ec  mov     eax, [esi+30h]
0x1000a5ef  mov     cl, [esi+28h]
0x1000a5f2  mov     edi, [eax+edx*8]
0x1000a5f5  mov     ebx, [eax+edx*8+4]
0x1000a5f9  mov     eax, [esi+34h]
0x1000a5fc  cmp     [edx+eax], cl
0x1000a5ff  jbe     short loc_1000A605
0x1000a601  test    cl, cl
0x1000a603  jnz     short loc_1000A62D
0x1000a605  mov     eax, edi
0x1000a607  or      eax, ebx
0x1000a609  jz      short loc_1000A631
0x1000a60b  mov     eax, [esi+14h]
0x1000a60e  mov     ecx, edi
0x1000a610  and     ecx, [esi+10h]
0x1000a613  and     eax, ebx
0x1000a615  or      ecx, eax
0x1000a617  jz      short loc_1000A62D
0x1000a619  mov     eax, [esi+18h]
0x1000a61c  mov     ecx, [esi+1Ch]
0x1000a61f  and     eax, edi
0x1000a621  and     ecx, ebx
0x1000a623  cmp     eax, [esi+18h]
0x1000a626  jnz     short loc_1000A62D
0x1000a628  cmp     ecx, [esi+1Ch]
0x1000a62b  jz      short loc_1000A631
0x1000a62d  xor     bl, bl
0x1000a62f  jmp     short loc_1000A633
0x1000a631  mov     bl, 1
0x1000a633  mov     eax, [esi+2Ch]
0x1000a636  mov     ecx, edx
0x1000a638  shr     ecx, 5
0x1000a63b  mov     edi, edx
0x1000a63d  and     edi, 1Fh
0x1000a640  lea     ecx, [eax+ecx*4]
0x1000a643  mov     eax, [ecx]
0x1000a645  test    bl, bl
0x1000a647  jz      short loc_1000A64E
0x1000a649  bts     eax, edi
0x1000a64c  jmp     short loc_1000A651
0x1000a64e  btr     eax, edi
0x1000a651  mov     [ecx], eax
0x1000a653  inc     edx
0x1000a654  movzx   eax, word ptr [esi+2Ah]
0x1000a658  cmp     edx, eax
0x1000a65a  jb      short loc_1000A5EC
0x1000a65c  pop     edi
0x1000a65d  jmp     short loc_1000A695
0x1000a65f  movzx   eax, word ptr [esi+2Ah]
0x1000a663  mov     [esi+24h], ebx
0x1000a666  mov     [esi+28h], bl
0x1000a669  mov     [esi+10h], ebx
0x1000a66c  mov     [esi+14h], ebx
0x1000a66f  mov     [esi+18h], ebx
0x1000a672  mov     [esi+1Ch], ebx
0x1000a675  test    ax, ax
0x1000a678  jz      short loc_1000A695
0x1000a67a  dec     eax
0x1000a67b  push    20h ; ' '
0x1000a67d  pop     ecx
0x1000a67e  cdq
0x1000a67f  idiv    ecx
0x1000a681  lea     eax, ds:4[eax*4]
0x1000a688  push    eax; Size
0x1000a689  push    ebx; Val
0x1000a68a  push    dword ptr [esi+2Ch]; void *
0x1000a68d  call    _memset
0x1000a692  add     esp, 0Ch
0x1000a695  pop     ebx
0x1000a696  pop     esi
0x1000a697  pop     ebp
0x1000a698  retn    24h ; '$'
```
