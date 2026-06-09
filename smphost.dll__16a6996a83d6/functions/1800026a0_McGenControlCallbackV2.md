# McGenControlCallbackV2

- ea: `0x1800026a0`
- end: `0x1800027a2`
- name: `McGenControlCallbackV2`
- size: `258`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800026a0`
- `0x180002926`

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
0x1800026a0  push    rbx
0x1800026a2  sub     rsp, 20h
0x1800026a6  mov     r10, [rsp+28h+CallbackContext]
0x1800026ab  xor     ebx, ebx
0x1800026ad  test    r10, r10
0x1800026b0  jz      loc_18000279B
0x1800026b6  test    edx, edx
0x1800026b8  jz      loc_180002760
0x1800026be  cmp     edx, 1
0x1800026c1  jnz     loc_18000279B
0x1800026c7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800026cc  mov     [r10+28h], r8b
0x1800026d0  mov     r8d, ebx
0x1800026d3  mov     [r10+18h], rax
0x1800026d7  mov     [r10+10h], r9
0x1800026db  mov     [r10+24h], edx
0x1800026df  cmp     bx, [r10+2Ah]
0x1800026e4  jnb     loc_18000279B
0x1800026ea  mov     rax, [r10+40h]
0x1800026ee  mov     cl, [r10+28h]
0x1800026f2  mov     r9d, r8d
0x1800026f5  cmp     [r9+rax], cl
0x1800026f9  jbe     short loc_1800026FF
0x1800026fb  test    cl, cl
0x1800026fd  jnz     short loc_18000271F
0x1800026ff  mov     rax, [r10+38h]
0x180002703  mov     rcx, [rax+r9*8]
0x180002707  test    rcx, rcx
0x18000270a  jz      short loc_180002724
0x18000270c  test    [r10+10h], rcx
0x180002710  jz      short loc_18000271F
0x180002712  mov     rax, [r10+18h]
0x180002716  and     rax, rcx
0x180002719  cmp     rax, [r10+18h]
0x18000271d  jz      short loc_180002724
0x18000271f  mov     r11b, bl
0x180002722  jmp     short loc_180002727
0x180002724  mov     r11b, 1
0x180002727  mov     rax, [r10+30h]
0x18000272b  mov     ecx, r8d
0x18000272e  shr     r9, 5
0x180002732  mov     edx, 1
0x180002737  shl     edx, cl
0x180002739  lea     rcx, [rax+r9*4]
0x18000273d  test    r11b, r11b
0x180002740  jz      short loc_180002746
0x180002742  or      edx, [rcx]
0x180002744  jmp     short loc_18000274A
0x180002746  not     edx
0x180002748  and     edx, [rcx]
0x18000274a  mov     [rcx], edx
0x18000274c  inc     r8d
0x18000274f  movzx   eax, word ptr [r10+2Ah]
0x180002754  cmp     r8d, eax
0x180002757  jb      short loc_1800026EA
0x180002759  add     rsp, 20h
0x18000275d  pop     rbx
0x18000275e  retn
0x180002760  mov     [r10+24h], ebx
0x180002764  mov     [r10+28h], bl
0x180002768  mov     [r10+10h], rbx
0x18000276c  mov     [r10+18h], rbx
0x180002770  cmp     [r10+2Ah], bx
0x180002775  jbe     short loc_18000279B
0x180002777  movzx   eax, word ptr [r10+2Ah]
0x18000277c  mov     rcx, [r10+30h]; void *
0x180002780  dec     eax
0x180002782  cdq
0x180002783  and     edx, 1Fh
0x180002786  add     eax, edx
0x180002788  xor     edx, edx; Val
0x18000278a  sar     eax, 5
0x18000278d  inc     eax
0x18000278f  movsxd  r8, eax
0x180002792  shl     r8, 2; Size
0x180002796  call    memset_0
0x18000279b  add     rsp, 20h
0x18000279f  pop     rbx
0x1800027a0  retn
```
