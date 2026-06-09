# McGenControlCallbackV2

- ea: `0x180006720`
- end: `0x18000684e`
- name: `McGenControlCallbackV2`
- size: `302`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, ULONGLONG *CallbackContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006620`
- `0x180006720`
- `0x18000cfbe`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        ULONGLONG *CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rcx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // edx

  if ( !CallbackContext )
    return;
  if ( !IsEnabled )
  {
    *((_DWORD *)CallbackContext + 9) = 0;
    *((_BYTE *)CallbackContext + 40) = 0;
    CallbackContext[2] = 0;
    CallbackContext[3] = 0;
    if ( *((_WORD *)CallbackContext + 21) )
      memset_0((void *)CallbackContext[6], 0, 4LL * ((*((unsigned __int16 *)CallbackContext + 21) - 1) / 32 + 1));
    goto LABEL_22;
  }
  if ( IsEnabled == 1 )
  {
    *((_BYTE *)CallbackContext + 40) = Level;
    v7 = 0;
    CallbackContext[3] = MatchAllKeyword;
    CallbackContext[2] = MatchAnyKeyword;
    for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
    {
      v8 = *((_BYTE *)CallbackContext + 40);
      v10 = 0;
      if ( *(_BYTE *)(v7 + CallbackContext[8]) <= v8 || !v8 )
      {
        v9 = *(_QWORD *)(CallbackContext[7] + 8LL * v7);
        if ( !v9 || (v9 & CallbackContext[2]) != 0 && (v9 & CallbackContext[3]) == CallbackContext[3] )
          v10 = 1;
      }
      v11 = 1 << v7;
      v12 = (int *)(CallbackContext[6] + 4 * ((unsigned __int64)v7 >> 5));
      if ( v10 )
        v13 = *v12 | v11;
      else
        v13 = *v12 & ~v11;
      *v12 = v13;
    }
  }
  else if ( IsEnabled - 1 >= 2 )
  {
    return;
  }
  if ( CallbackContext == &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context )
LABEL_22:
    SetLibParams();
}

```

## disassembly

```asm
0x180006720  push    rbx
0x180006722  sub     rsp, 20h
0x180006726  mov     r10, [rsp+28h+CallbackContext]
0x18000672b  xor     ebx, ebx
0x18000672d  test    r10, r10
0x180006730  jz      loc_180006848
0x180006736  mov     eax, edx
0x180006738  test    edx, edx
0x18000673a  jz      loc_180006809
0x180006740  cmp     eax, 1
0x180006743  jz      short loc_180006765
0x180006745  test    edx, edx
0x180006747  jz      loc_180006843
0x18000674d  sub     edx, 1
0x180006750  jz      loc_1800067F7
0x180006756  cmp     edx, 1
0x180006759  jz      loc_1800067F7
0x18000675f  add     rsp, 20h
0x180006763  pop     rbx
0x180006764  retn
0x180006765  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000676a  mov     [r10+28h], r8b
0x18000676e  mov     r8d, ebx
0x180006771  mov     [r10+18h], rax
0x180006775  mov     [r10+10h], r9
0x180006779  mov     dword ptr [r10+24h], 1
0x180006781  cmp     bx, [r10+2Ah]
0x180006786  jnb     short loc_1800067F7
0x180006788  mov     rax, [r10+40h]
0x18000678c  mov     cl, [r10+28h]
0x180006790  mov     r9d, r8d
0x180006793  cmp     [r9+rax], cl
0x180006797  jbe     short loc_18000679D
0x180006799  test    cl, cl
0x18000679b  jnz     short loc_1800067BD
0x18000679d  mov     rax, [r10+38h]
0x1800067a1  mov     rcx, [rax+r9*8]
0x1800067a5  test    rcx, rcx
0x1800067a8  jz      short loc_1800067C2
0x1800067aa  test    [r10+10h], rcx
0x1800067ae  jz      short loc_1800067BD
0x1800067b0  mov     rax, [r10+18h]
0x1800067b4  and     rax, rcx
0x1800067b7  cmp     rax, [r10+18h]
0x1800067bb  jz      short loc_1800067C2
0x1800067bd  mov     r11b, bl
0x1800067c0  jmp     short loc_1800067C5
0x1800067c2  mov     r11b, 1
0x1800067c5  mov     rax, [r10+30h]
0x1800067c9  mov     ecx, r8d
0x1800067cc  shr     r9, 5
0x1800067d0  mov     edx, 1
0x1800067d5  shl     edx, cl
0x1800067d7  lea     rcx, [rax+r9*4]
0x1800067db  test    r11b, r11b
0x1800067de  jz      short loc_1800067E4
0x1800067e0  or      edx, [rcx]
0x1800067e2  jmp     short loc_1800067E8
0x1800067e4  not     edx
0x1800067e6  and     edx, [rcx]
0x1800067e8  mov     [rcx], edx
0x1800067ea  inc     r8d
0x1800067ed  movzx   eax, word ptr [r10+2Ah]
0x1800067f2  cmp     r8d, eax
0x1800067f5  jb      short loc_180006788
0x1800067f7  lea     rax, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800067fe  cmp     r10, rax
0x180006801  jz      short loc_180006843
0x180006803  add     rsp, 20h
0x180006807  pop     rbx
0x180006808  retn
0x180006809  mov     [r10+24h], ebx
0x18000680d  mov     [r10+28h], bl
0x180006811  mov     [r10+10h], rbx
0x180006815  mov     [r10+18h], rbx
0x180006819  cmp     [r10+2Ah], bx
0x18000681e  jbe     short loc_180006843
0x180006820  movzx   eax, word ptr [r10+2Ah]
0x180006825  mov     ecx, 20h ; ' '
0x18000682a  dec     eax
0x18000682c  cdq
0x18000682d  idiv    ecx
0x18000682f  mov     rcx, [r10+30h]; void *
0x180006833  xor     edx, edx; Val
0x180006835  inc     eax
0x180006837  movsxd  r8, eax
0x18000683a  shl     r8, 2; Size
0x18000683e  call    memset_0
0x180006843  call    ?SetLibParams@@YAXXZ; SetLibParams(void)
0x180006848  add     rsp, 20h
0x18000684c  pop     rbx
0x18000684d  retn
```
