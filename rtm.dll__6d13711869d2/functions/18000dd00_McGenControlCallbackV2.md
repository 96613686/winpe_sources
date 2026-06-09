# McGenControlCallbackV2

- ea: `0x18000dd00`
- end: `0x18000de2f`
- name: `McGenControlCallbackV2`
- size: `303`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000dd00`
- `0x18000dea0`
- `0x18001f952`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        ULONGLONG SourceId,
        __int64 IsEnabled,
        __int64 Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        ULONGLONG *CallbackContext)
{
  unsigned __int8 v7; // cl
  __int64 v8; // rcx
  bool v9; // r11
  int v10; // edx

  if ( !CallbackContext )
    return;
  if ( !(_DWORD)IsEnabled )
  {
    *((_DWORD *)CallbackContext + 9) = 0;
    *((_BYTE *)CallbackContext + 40) = 0;
    CallbackContext[2] = 0;
    CallbackContext[3] = 0;
    if ( *((_WORD *)CallbackContext + 21) )
      memset_0((void *)CallbackContext[6], 0, 4LL * ((*((unsigned __int16 *)CallbackContext + 21) - 1) / 32 + 1));
    goto LABEL_22;
  }
  if ( (_DWORD)IsEnabled == 1 )
  {
    *((_BYTE *)CallbackContext + 40) = Level;
    Level = 0;
    CallbackContext[3] = MatchAllKeyword;
    CallbackContext[2] = MatchAnyKeyword;
    for ( *((_DWORD *)CallbackContext + 9) = 1;
          (unsigned int)Level < *((unsigned __int16 *)CallbackContext + 21);
          Level = (unsigned int)(Level + 1) )
    {
      v7 = *((_BYTE *)CallbackContext + 40);
      v9 = 0;
      if ( *(_BYTE *)((unsigned int)Level + CallbackContext[8]) <= v7 || !v7 )
      {
        v8 = *(_QWORD *)(CallbackContext[7] + 8LL * (unsigned int)Level);
        if ( !v8 || (v8 & CallbackContext[2]) != 0 && (v8 & CallbackContext[3]) == CallbackContext[3] )
          v9 = 1;
      }
      MatchAnyKeyword = (unsigned __int64)(unsigned int)Level >> 5;
      v10 = 1 << Level;
      SourceId = CallbackContext[6] + 4 * MatchAnyKeyword;
      if ( v9 )
        IsEnabled = *(_DWORD *)SourceId | (unsigned int)v10;
      else
        IsEnabled = *(_DWORD *)SourceId & (unsigned int)~v10;
      *(_DWORD *)SourceId = IsEnabled;
    }
  }
  else
  {
    IsEnabled = (unsigned int)(IsEnabled - 1);
    if ( (unsigned int)IsEnabled >= 2 )
      return;
  }
  if ( CallbackContext == &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context )
LABEL_22:
    SetLibParams(SourceId, IsEnabled, Level, MatchAnyKeyword);
}

```

## disassembly

```asm
0x18000dd00  push    rbx
0x18000dd02  sub     rsp, 20h
0x18000dd06  mov     r10, [rsp+28h+CallbackContext]
0x18000dd0b  xor     ebx, ebx
0x18000dd0d  test    r10, r10
0x18000dd10  jz      loc_18000DE29
0x18000dd16  mov     eax, edx
0x18000dd18  test    edx, edx
0x18000dd1a  jz      loc_18000DDE9
0x18000dd20  cmp     eax, 1
0x18000dd23  jz      short loc_18000DD45
0x18000dd25  test    edx, edx
0x18000dd27  jz      loc_18000DE24
0x18000dd2d  sub     edx, 1
0x18000dd30  jz      loc_18000DDD7
0x18000dd36  cmp     edx, 1
0x18000dd39  jz      loc_18000DDD7
0x18000dd3f  add     rsp, 20h
0x18000dd43  pop     rbx
0x18000dd44  retn
0x18000dd45  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000dd4a  mov     [r10+28h], r8b
0x18000dd4e  mov     r8d, ebx
0x18000dd51  mov     [r10+18h], rax
0x18000dd55  mov     [r10+10h], r9
0x18000dd59  mov     dword ptr [r10+24h], 1
0x18000dd61  cmp     bx, [r10+2Ah]
0x18000dd66  jnb     short loc_18000DDD7
0x18000dd68  mov     rax, [r10+40h]
0x18000dd6c  mov     cl, [r10+28h]
0x18000dd70  mov     r9d, r8d
0x18000dd73  cmp     [r9+rax], cl
0x18000dd77  jbe     short loc_18000DD7D
0x18000dd79  test    cl, cl
0x18000dd7b  jnz     short loc_18000DD9D
0x18000dd7d  mov     rax, [r10+38h]
0x18000dd81  mov     rcx, [rax+r9*8]
0x18000dd85  test    rcx, rcx
0x18000dd88  jz      short loc_18000DDA2
0x18000dd8a  test    [r10+10h], rcx
0x18000dd8e  jz      short loc_18000DD9D
0x18000dd90  mov     rax, [r10+18h]
0x18000dd94  and     rax, rcx
0x18000dd97  cmp     rax, [r10+18h]
0x18000dd9b  jz      short loc_18000DDA2
0x18000dd9d  mov     r11b, bl
0x18000dda0  jmp     short loc_18000DDA5
0x18000dda2  mov     r11b, 1
0x18000dda5  mov     rax, [r10+30h]
0x18000dda9  mov     ecx, r8d
0x18000ddac  shr     r9, 5
0x18000ddb0  mov     edx, 1
0x18000ddb5  shl     edx, cl
0x18000ddb7  lea     rcx, [rax+r9*4]
0x18000ddbb  test    r11b, r11b
0x18000ddbe  jz      short loc_18000DDC4
0x18000ddc0  or      edx, [rcx]
0x18000ddc2  jmp     short loc_18000DDC8
0x18000ddc4  not     edx
0x18000ddc6  and     edx, [rcx]
0x18000ddc8  mov     [rcx], edx
0x18000ddca  inc     r8d
0x18000ddcd  movzx   eax, word ptr [r10+2Ah]
0x18000ddd2  cmp     r8d, eax
0x18000ddd5  jb      short loc_18000DD68
0x18000ddd7  lea     rax, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ddde  cmp     r10, rax
0x18000dde1  jz      short loc_18000DE24
0x18000dde3  add     rsp, 20h
0x18000dde7  pop     rbx
0x18000dde8  retn
0x18000dde9  mov     [r10+24h], ebx
0x18000dded  mov     [r10+28h], bl
0x18000ddf1  mov     [r10+10h], rbx
0x18000ddf5  mov     [r10+18h], rbx
0x18000ddf9  cmp     [r10+2Ah], bx
0x18000ddfe  jbe     short loc_18000DE24
0x18000de00  movzx   eax, word ptr [r10+2Ah]
0x18000de05  mov     rcx, [r10+30h]; void *
0x18000de09  dec     eax
0x18000de0b  cdq
0x18000de0c  and     edx, 1Fh
0x18000de0f  add     eax, edx
0x18000de11  xor     edx, edx; Val
0x18000de13  sar     eax, 5
0x18000de16  inc     eax
0x18000de18  movsxd  r8, eax
0x18000de1b  shl     r8, 2; Size
0x18000de1f  call    memset_0
0x18000de24  call    SetLibParams
0x18000de29  add     rsp, 20h
0x18000de2d  pop     rbx
0x18000de2e  retn
```
