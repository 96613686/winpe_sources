# McGenControlCallbackV2

- ea: `0x180003440`
- end: `0x180003542`
- name: `McGenControlCallbackV2`
- size: `258`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003440`
- `0x1800138c5`

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
0x180003440  push    rbx
0x180003442  sub     rsp, 20h
0x180003446  mov     r10, [rsp+28h+CallbackContext]
0x18000344b  xor     ebx, ebx
0x18000344d  test    r10, r10
0x180003450  jz      loc_18000353B
0x180003456  test    edx, edx
0x180003458  jz      loc_180003500
0x18000345e  cmp     edx, 1
0x180003461  jnz     loc_18000353B
0x180003467  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000346c  mov     [r10+28h], r8b
0x180003470  mov     r8d, ebx
0x180003473  mov     [r10+18h], rax
0x180003477  mov     [r10+10h], r9
0x18000347b  mov     [r10+24h], edx
0x18000347f  cmp     bx, [r10+2Ah]
0x180003484  jnb     loc_18000353B
0x18000348a  mov     rax, [r10+40h]
0x18000348e  mov     cl, [r10+28h]
0x180003492  mov     r9d, r8d
0x180003495  cmp     [r9+rax], cl
0x180003499  jbe     short loc_18000349F
0x18000349b  test    cl, cl
0x18000349d  jnz     short loc_1800034BF
0x18000349f  mov     rax, [r10+38h]
0x1800034a3  mov     rcx, [rax+r9*8]
0x1800034a7  test    rcx, rcx
0x1800034aa  jz      short loc_1800034C4
0x1800034ac  test    [r10+10h], rcx
0x1800034b0  jz      short loc_1800034BF
0x1800034b2  mov     rax, [r10+18h]
0x1800034b6  and     rax, rcx
0x1800034b9  cmp     rax, [r10+18h]
0x1800034bd  jz      short loc_1800034C4
0x1800034bf  mov     r11b, bl
0x1800034c2  jmp     short loc_1800034C7
0x1800034c4  mov     r11b, 1
0x1800034c7  mov     rax, [r10+30h]
0x1800034cb  mov     ecx, r8d
0x1800034ce  shr     r9, 5
0x1800034d2  mov     edx, 1
0x1800034d7  shl     edx, cl
0x1800034d9  lea     rcx, [rax+r9*4]
0x1800034dd  test    r11b, r11b
0x1800034e0  jz      short loc_1800034E6
0x1800034e2  or      edx, [rcx]
0x1800034e4  jmp     short loc_1800034EA
0x1800034e6  not     edx
0x1800034e8  and     edx, [rcx]
0x1800034ea  mov     [rcx], edx
0x1800034ec  inc     r8d
0x1800034ef  movzx   eax, word ptr [r10+2Ah]
0x1800034f4  cmp     r8d, eax
0x1800034f7  jb      short loc_18000348A
0x1800034f9  add     rsp, 20h
0x1800034fd  pop     rbx
0x1800034fe  retn
0x180003500  mov     [r10+24h], ebx
0x180003504  mov     [r10+28h], bl
0x180003508  mov     [r10+10h], rbx
0x18000350c  mov     [r10+18h], rbx
0x180003510  cmp     [r10+2Ah], bx
0x180003515  jbe     short loc_18000353B
0x180003517  movzx   eax, word ptr [r10+2Ah]
0x18000351c  mov     rcx, [r10+30h]; void *
0x180003520  dec     eax
0x180003522  cdq
0x180003523  and     edx, 1Fh
0x180003526  add     eax, edx
0x180003528  xor     edx, edx; Val
0x18000352a  sar     eax, 5
0x18000352d  inc     eax
0x18000352f  movsxd  r8, eax
0x180003532  shl     r8, 2; Size
0x180003536  call    memset_0
0x18000353b  add     rsp, 20h
0x18000353f  pop     rbx
0x180003540  retn
```
