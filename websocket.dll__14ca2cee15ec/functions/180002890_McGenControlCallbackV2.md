# McGenControlCallbackV2

- ea: `0x180002890`
- end: `0x180002990`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001fa4`
- `0x180002890`

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
0x180002890  push    rbx
0x180002892  sub     rsp, 20h
0x180002896  mov     r10, [rsp+28h+CallbackContext]
0x18000289b  xor     ebx, ebx
0x18000289d  test    r10, r10
0x1800028a0  jz      loc_18000298A
0x1800028a6  test    edx, edx
0x1800028a8  jz      loc_18000294F
0x1800028ae  cmp     edx, 1
0x1800028b1  jnz     loc_18000298A
0x1800028b7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800028bc  mov     [r10+28h], r8b
0x1800028c0  mov     r8d, ebx
0x1800028c3  mov     [r10+18h], rax
0x1800028c7  mov     [r10+10h], r9
0x1800028cb  mov     [r10+24h], edx
0x1800028cf  cmp     bx, [r10+2Ah]
0x1800028d4  jnb     loc_18000298A
0x1800028da  mov     rax, [r10+40h]
0x1800028de  mov     cl, [r10+28h]
0x1800028e2  mov     r9d, r8d
0x1800028e5  cmp     [r9+rax], cl
0x1800028e9  jbe     short loc_1800028EF
0x1800028eb  test    cl, cl
0x1800028ed  jnz     short loc_18000290F
0x1800028ef  mov     rax, [r10+38h]
0x1800028f3  mov     rcx, [rax+r9*8]
0x1800028f7  test    rcx, rcx
0x1800028fa  jz      short loc_180002914
0x1800028fc  test    [r10+10h], rcx
0x180002900  jz      short loc_18000290F
0x180002902  mov     rax, [r10+18h]
0x180002906  and     rax, rcx
0x180002909  cmp     rax, [r10+18h]
0x18000290d  jz      short loc_180002914
0x18000290f  mov     r11b, bl
0x180002912  jmp     short loc_180002917
0x180002914  mov     r11b, 1
0x180002917  mov     rax, [r10+30h]
0x18000291b  mov     ecx, r8d
0x18000291e  shr     r9, 5
0x180002922  mov     edx, 1
0x180002927  shl     edx, cl
0x180002929  lea     rcx, [rax+r9*4]
0x18000292d  test    r11b, r11b
0x180002930  jz      short loc_180002936
0x180002932  or      edx, [rcx]
0x180002934  jmp     short loc_18000293A
0x180002936  not     edx
0x180002938  and     edx, [rcx]
0x18000293a  mov     [rcx], edx
0x18000293c  inc     r8d
0x18000293f  movzx   eax, word ptr [r10+2Ah]
0x180002944  cmp     r8d, eax
0x180002947  jb      short loc_1800028DA
0x180002949  add     rsp, 20h
0x18000294d  pop     rbx
0x18000294e  retn
0x18000294f  mov     [r10+24h], ebx
0x180002953  mov     [r10+28h], bl
0x180002957  mov     [r10+10h], rbx
0x18000295b  mov     [r10+18h], rbx
0x18000295f  cmp     [r10+2Ah], bx
0x180002964  jbe     short loc_18000298A
0x180002966  movzx   eax, word ptr [r10+2Ah]
0x18000296b  mov     rcx, [r10+30h]; void *
0x18000296f  dec     eax
0x180002971  cdq
0x180002972  and     edx, 1Fh
0x180002975  add     eax, edx
0x180002977  xor     edx, edx; Val
0x180002979  sar     eax, 5
0x18000297c  inc     eax
0x18000297e  movsxd  r8, eax
0x180002981  shl     r8, 2; Size
0x180002985  call    memset_0
0x18000298a  add     rsp, 20h
0x18000298e  pop     rbx
0x18000298f  retn
```
