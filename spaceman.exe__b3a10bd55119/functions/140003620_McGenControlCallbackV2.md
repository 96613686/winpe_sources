# McGenControlCallbackV2

- ea: `0x140003620`
- end: `0x140003720`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003620`
- `0x14000d1be`

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
0x140003620  push    rbx
0x140003622  sub     rsp, 20h
0x140003626  mov     r10, [rsp+28h+CallbackContext]
0x14000362b  xor     ebx, ebx
0x14000362d  test    r10, r10
0x140003630  jz      loc_14000371A
0x140003636  test    edx, edx
0x140003638  jz      loc_1400036DF
0x14000363e  cmp     edx, 1
0x140003641  jnz     loc_14000371A
0x140003647  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000364c  mov     [r10+28h], r8b
0x140003650  mov     r8d, ebx
0x140003653  mov     [r10+18h], rax
0x140003657  mov     [r10+10h], r9
0x14000365b  mov     [r10+24h], edx
0x14000365f  cmp     bx, [r10+2Ah]
0x140003664  jnb     loc_14000371A
0x14000366a  mov     rax, [r10+40h]
0x14000366e  mov     cl, [r10+28h]
0x140003672  mov     r9d, r8d
0x140003675  cmp     [r9+rax], cl
0x140003679  jbe     short loc_14000367F
0x14000367b  test    cl, cl
0x14000367d  jnz     short loc_14000369F
0x14000367f  mov     rax, [r10+38h]
0x140003683  mov     rcx, [rax+r9*8]
0x140003687  test    rcx, rcx
0x14000368a  jz      short loc_1400036A4
0x14000368c  test    [r10+10h], rcx
0x140003690  jz      short loc_14000369F
0x140003692  mov     rax, [r10+18h]
0x140003696  and     rax, rcx
0x140003699  cmp     rax, [r10+18h]
0x14000369d  jz      short loc_1400036A4
0x14000369f  mov     r11b, bl
0x1400036a2  jmp     short loc_1400036A7
0x1400036a4  mov     r11b, 1
0x1400036a7  mov     rax, [r10+30h]
0x1400036ab  mov     ecx, r8d
0x1400036ae  shr     r9, 5
0x1400036b2  mov     edx, 1
0x1400036b7  shl     edx, cl
0x1400036b9  lea     rcx, [rax+r9*4]
0x1400036bd  test    r11b, r11b
0x1400036c0  jz      short loc_1400036C6
0x1400036c2  or      edx, [rcx]
0x1400036c4  jmp     short loc_1400036CA
0x1400036c6  not     edx
0x1400036c8  and     edx, [rcx]
0x1400036ca  mov     [rcx], edx
0x1400036cc  inc     r8d
0x1400036cf  movzx   eax, word ptr [r10+2Ah]
0x1400036d4  cmp     r8d, eax
0x1400036d7  jb      short loc_14000366A
0x1400036d9  add     rsp, 20h
0x1400036dd  pop     rbx
0x1400036de  retn
0x1400036df  mov     [r10+24h], ebx
0x1400036e3  mov     [r10+28h], bl
0x1400036e7  mov     [r10+10h], rbx
0x1400036eb  mov     [r10+18h], rbx
0x1400036ef  cmp     [r10+2Ah], bx
0x1400036f4  jbe     short loc_14000371A
0x1400036f6  movzx   eax, word ptr [r10+2Ah]
0x1400036fb  mov     rcx, [r10+30h]; void *
0x1400036ff  dec     eax
0x140003701  cdq
0x140003702  and     edx, 1Fh
0x140003705  add     eax, edx
0x140003707  xor     edx, edx; Val
0x140003709  sar     eax, 5
0x14000370c  inc     eax
0x14000370e  movsxd  r8, eax
0x140003711  shl     r8, 2; Size
0x140003715  call    memset_0
0x14000371a  add     rsp, 20h
0x14000371e  pop     rbx
0x14000371f  retn
```
