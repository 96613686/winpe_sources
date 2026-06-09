# McGenControlCallbackV2

- ea: `0x1800156c0`
- end: `0x1800157c0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000266c`
- `0x1800156c0`

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
0x1800156c0  push    rbx
0x1800156c2  sub     rsp, 20h
0x1800156c6  mov     r10, [rsp+28h+CallbackContext]
0x1800156cb  xor     ebx, ebx
0x1800156cd  test    r10, r10
0x1800156d0  jz      loc_1800157BA
0x1800156d6  test    edx, edx
0x1800156d8  jz      loc_18001577F
0x1800156de  cmp     edx, 1
0x1800156e1  jnz     loc_1800157BA
0x1800156e7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800156ec  mov     [r10+28h], r8b
0x1800156f0  mov     r8d, ebx
0x1800156f3  mov     [r10+18h], rax
0x1800156f7  mov     [r10+10h], r9
0x1800156fb  mov     [r10+24h], edx
0x1800156ff  cmp     bx, [r10+2Ah]
0x180015704  jnb     loc_1800157BA
0x18001570a  mov     rax, [r10+40h]
0x18001570e  mov     cl, [r10+28h]
0x180015712  mov     r9d, r8d
0x180015715  cmp     [r9+rax], cl
0x180015719  jbe     short loc_18001571F
0x18001571b  test    cl, cl
0x18001571d  jnz     short loc_18001573F
0x18001571f  mov     rax, [r10+38h]
0x180015723  mov     rcx, [rax+r9*8]
0x180015727  test    rcx, rcx
0x18001572a  jz      short loc_180015744
0x18001572c  test    [r10+10h], rcx
0x180015730  jz      short loc_18001573F
0x180015732  mov     rax, [r10+18h]
0x180015736  and     rax, rcx
0x180015739  cmp     rax, [r10+18h]
0x18001573d  jz      short loc_180015744
0x18001573f  mov     r11b, bl
0x180015742  jmp     short loc_180015747
0x180015744  mov     r11b, 1
0x180015747  mov     rax, [r10+30h]
0x18001574b  mov     ecx, r8d
0x18001574e  shr     r9, 5
0x180015752  mov     edx, 1
0x180015757  shl     edx, cl
0x180015759  lea     rcx, [rax+r9*4]
0x18001575d  test    r11b, r11b
0x180015760  jz      short loc_180015766
0x180015762  or      edx, [rcx]
0x180015764  jmp     short loc_18001576A
0x180015766  not     edx
0x180015768  and     edx, [rcx]
0x18001576a  mov     [rcx], edx
0x18001576c  inc     r8d
0x18001576f  movzx   eax, word ptr [r10+2Ah]
0x180015774  cmp     r8d, eax
0x180015777  jb      short loc_18001570A
0x180015779  add     rsp, 20h
0x18001577d  pop     rbx
0x18001577e  retn
0x18001577f  mov     [r10+24h], ebx
0x180015783  mov     [r10+28h], bl
0x180015787  mov     [r10+10h], rbx
0x18001578b  mov     [r10+18h], rbx
0x18001578f  cmp     [r10+2Ah], bx
0x180015794  jbe     short loc_1800157BA
0x180015796  movzx   eax, word ptr [r10+2Ah]
0x18001579b  mov     rcx, [r10+30h]; void *
0x18001579f  dec     eax
0x1800157a1  cdq
0x1800157a2  and     edx, 1Fh
0x1800157a5  add     eax, edx
0x1800157a7  xor     edx, edx; Val
0x1800157a9  sar     eax, 5
0x1800157ac  inc     eax
0x1800157ae  movsxd  r8, eax
0x1800157b1  shl     r8, 2; Size
0x1800157b5  call    memset_0
0x1800157ba  add     rsp, 20h
0x1800157be  pop     rbx
0x1800157bf  retn
```
