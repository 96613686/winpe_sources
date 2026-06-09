# McGenControlCallbackV2

- ea: `0x1800046d0`
- end: `0x1800047e4`
- name: `McGenControlCallbackV2`
- size: `276`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800033b4`
- `0x1800046d0`
- `0x18000f594`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        LPCGUID SourceId,
        __int64 IsEnabled,
        __int64 Level,
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
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
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
      else if ( (_DWORD)IsEnabled == 2 )
      {
        TraceState(SourceId, IsEnabled, Level);
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
0x1800046d0  push    rbx
0x1800046d2  sub     rsp, 20h
0x1800046d6  mov     r10, [rsp+28h+CallbackContext]
0x1800046db  xor     ebx, ebx
0x1800046dd  test    r10, r10
0x1800046e0  jz      loc_1800047DE
0x1800046e6  mov     eax, edx
0x1800046e8  test    edx, edx
0x1800046ea  jz      loc_1800047A4
0x1800046f0  cmp     eax, 1
0x1800046f3  jz      short loc_180004708
0x1800046f5  cmp     edx, 2
0x1800046f8  jnz     loc_1800047DE
0x1800046fe  add     rsp, 20h
0x180004702  pop     rbx
0x180004703  jmp     TraceState
0x180004708  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000470d  mov     [r10+28h], r8b
0x180004711  mov     r8d, ebx
0x180004714  mov     [r10+18h], rax
0x180004718  mov     [r10+10h], r9
0x18000471c  mov     dword ptr [r10+24h], 1
0x180004724  cmp     bx, [r10+2Ah]
0x180004729  jnb     loc_1800047DE
0x18000472f  mov     rax, [r10+40h]
0x180004733  mov     cl, [r10+28h]
0x180004737  mov     r9d, r8d
0x18000473a  cmp     [r9+rax], cl
0x18000473e  jbe     short loc_180004744
0x180004740  test    cl, cl
0x180004742  jnz     short loc_180004764
0x180004744  mov     rax, [r10+38h]
0x180004748  mov     rcx, [rax+r9*8]
0x18000474c  test    rcx, rcx
0x18000474f  jz      short loc_180004769
0x180004751  test    [r10+10h], rcx
0x180004755  jz      short loc_180004764
0x180004757  mov     rax, [r10+18h]
0x18000475b  and     rax, rcx
0x18000475e  cmp     rax, [r10+18h]
0x180004762  jz      short loc_180004769
0x180004764  mov     r11b, bl
0x180004767  jmp     short loc_18000476C
0x180004769  mov     r11b, 1
0x18000476c  mov     rax, [r10+30h]
0x180004770  mov     ecx, r8d
0x180004773  shr     r9, 5
0x180004777  mov     edx, 1
0x18000477c  shl     edx, cl
0x18000477e  lea     rcx, [rax+r9*4]
0x180004782  test    r11b, r11b
0x180004785  jz      short loc_18000478B
0x180004787  or      edx, [rcx]
0x180004789  jmp     short loc_18000478F
0x18000478b  not     edx
0x18000478d  and     edx, [rcx]
0x18000478f  mov     [rcx], edx
0x180004791  inc     r8d
0x180004794  movzx   eax, word ptr [r10+2Ah]
0x180004799  cmp     r8d, eax
0x18000479c  jb      short loc_18000472F
0x18000479e  add     rsp, 20h
0x1800047a2  pop     rbx
0x1800047a3  retn
0x1800047a4  mov     [r10+24h], ebx
0x1800047a8  mov     [r10+28h], bl
0x1800047ac  mov     [r10+10h], rbx
0x1800047b0  mov     [r10+18h], rbx
0x1800047b4  cmp     [r10+2Ah], bx
0x1800047b9  jbe     short loc_1800047DE
0x1800047bb  movzx   eax, word ptr [r10+2Ah]
0x1800047c0  mov     ecx, 20h ; ' '
0x1800047c5  dec     eax
0x1800047c7  cdq
0x1800047c8  idiv    ecx
0x1800047ca  mov     rcx, [r10+30h]; void *
0x1800047ce  xor     edx, edx; Val
0x1800047d0  inc     eax
0x1800047d2  movsxd  r8, eax
0x1800047d5  shl     r8, 2; Size
0x1800047d9  call    memset_0
0x1800047de  add     rsp, 20h
0x1800047e2  pop     rbx
0x1800047e3  retn
```
