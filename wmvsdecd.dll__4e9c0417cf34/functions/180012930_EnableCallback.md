# EnableCallback

- ea: `0x180012930`
- end: `0x180012a31`
- name: `EnableCallback`
- size: `257`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f78`
- `0x180012930`

## pseudocode

```c
void __fastcall EnableCallback(
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
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((CallbackContext[21] - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x180012930  push    rbx
0x180012932  sub     rsp, 20h
0x180012936  mov     r10, [rsp+28h+CallbackContext]
0x18001293b  xor     ebx, ebx
0x18001293d  test    r10, r10
0x180012940  jz      loc_180012A2A
0x180012946  test    edx, edx
0x180012948  jz      loc_1800129F0
0x18001294e  cmp     edx, 1
0x180012951  jnz     loc_180012A2A
0x180012957  mov     rax, [rsp+28h+MatchAllKeyword]
0x18001295c  mov     [r10+28h], r8b
0x180012960  mov     r8d, ebx
0x180012963  mov     [r10+18h], rax
0x180012967  mov     [r10+10h], r9
0x18001296b  mov     [r10+24h], edx
0x18001296f  cmp     bx, [r10+2Ah]
0x180012974  jnb     loc_180012A2A
0x18001297a  mov     rax, [r10+40h]
0x18001297e  mov     cl, [r10+28h]
0x180012982  mov     r9d, r8d
0x180012985  cmp     [r9+rax], cl
0x180012989  jbe     short loc_18001298F
0x18001298b  test    cl, cl
0x18001298d  jnz     short loc_1800129AF
0x18001298f  mov     rax, [r10+38h]
0x180012993  mov     rcx, [rax+r9*8]
0x180012997  test    rcx, rcx
0x18001299a  jz      short loc_1800129B4
0x18001299c  test    [r10+10h], rcx
0x1800129a0  jz      short loc_1800129AF
0x1800129a2  mov     rax, [r10+18h]
0x1800129a6  and     rax, rcx
0x1800129a9  cmp     rax, [r10+18h]
0x1800129ad  jz      short loc_1800129B4
0x1800129af  mov     r11b, bl
0x1800129b2  jmp     short loc_1800129B7
0x1800129b4  mov     r11b, 1
0x1800129b7  mov     rax, [r10+30h]
0x1800129bb  mov     ecx, r8d
0x1800129be  shr     r9, 5
0x1800129c2  mov     edx, 1
0x1800129c7  shl     edx, cl
0x1800129c9  lea     rcx, [rax+r9*4]
0x1800129cd  test    r11b, r11b
0x1800129d0  jz      short loc_1800129D6
0x1800129d2  or      edx, [rcx]
0x1800129d4  jmp     short loc_1800129DA
0x1800129d6  not     edx
0x1800129d8  and     edx, [rcx]
0x1800129da  mov     [rcx], edx
0x1800129dc  inc     r8d
0x1800129df  movzx   eax, word ptr [r10+2Ah]
0x1800129e4  cmp     r8d, eax
0x1800129e7  jb      short loc_18001297A
0x1800129e9  add     rsp, 20h
0x1800129ed  pop     rbx
0x1800129ee  retn
0x1800129f0  mov     [r10+24h], ebx
0x1800129f4  mov     [r10+28h], bl
0x1800129f8  mov     [r10+10h], rbx
0x1800129fc  mov     [r10+18h], rbx
0x180012a00  cmp     [r10+2Ah], bx
0x180012a05  jbe     short loc_180012A2A
0x180012a07  movzx   eax, word ptr [r10+2Ah]
0x180012a0c  mov     ecx, 20h ; ' '
0x180012a11  dec     eax
0x180012a13  cdq
0x180012a14  idiv    ecx
0x180012a16  mov     rcx, [r10+30h]; void *
0x180012a1a  xor     edx, edx; Val
0x180012a1c  inc     eax
0x180012a1e  movsxd  r8, eax
0x180012a21  shl     r8, 2; Size
0x180012a25  call    memset
0x180012a2a  add     rsp, 20h
0x180012a2e  pop     rbx
0x180012a2f  retn
```
