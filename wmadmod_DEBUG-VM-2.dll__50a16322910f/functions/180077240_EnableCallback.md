# EnableCallback

- ea: `0x180077240`
- end: `0x180077341`
- name: `EnableCallback`
- size: `257`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011a38`
- `0x180077240`

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
0x180077240  push    rbx
0x180077242  sub     rsp, 20h
0x180077246  mov     r10, [rsp+28h+CallbackContext]
0x18007724b  xor     ebx, ebx
0x18007724d  test    r10, r10
0x180077250  jz      loc_18007733A
0x180077256  test    edx, edx
0x180077258  jz      loc_180077300
0x18007725e  cmp     edx, 1
0x180077261  jnz     loc_18007733A
0x180077267  mov     rax, [rsp+28h+MatchAllKeyword]
0x18007726c  mov     [r10+28h], r8b
0x180077270  mov     r8d, ebx
0x180077273  mov     [r10+18h], rax
0x180077277  mov     [r10+10h], r9
0x18007727b  mov     [r10+24h], edx
0x18007727f  cmp     bx, [r10+2Ah]
0x180077284  jnb     loc_18007733A
0x18007728a  mov     rax, [r10+40h]
0x18007728e  mov     cl, [r10+28h]
0x180077292  mov     r9d, r8d
0x180077295  cmp     [r9+rax], cl
0x180077299  jbe     short loc_18007729F
0x18007729b  test    cl, cl
0x18007729d  jnz     short loc_1800772BF
0x18007729f  mov     rax, [r10+38h]
0x1800772a3  mov     rcx, [rax+r9*8]
0x1800772a7  test    rcx, rcx
0x1800772aa  jz      short loc_1800772C4
0x1800772ac  test    [r10+10h], rcx
0x1800772b0  jz      short loc_1800772BF
0x1800772b2  mov     rax, [r10+18h]
0x1800772b6  and     rax, rcx
0x1800772b9  cmp     rax, [r10+18h]
0x1800772bd  jz      short loc_1800772C4
0x1800772bf  mov     r11b, bl
0x1800772c2  jmp     short loc_1800772C7
0x1800772c4  mov     r11b, 1
0x1800772c7  mov     rax, [r10+30h]
0x1800772cb  mov     ecx, r8d
0x1800772ce  shr     r9, 5
0x1800772d2  mov     edx, 1
0x1800772d7  shl     edx, cl
0x1800772d9  lea     rcx, [rax+r9*4]
0x1800772dd  test    r11b, r11b
0x1800772e0  jz      short loc_1800772E6
0x1800772e2  or      edx, [rcx]
0x1800772e4  jmp     short loc_1800772EA
0x1800772e6  not     edx
0x1800772e8  and     edx, [rcx]
0x1800772ea  mov     [rcx], edx
0x1800772ec  inc     r8d
0x1800772ef  movzx   eax, word ptr [r10+2Ah]
0x1800772f4  cmp     r8d, eax
0x1800772f7  jb      short loc_18007728A
0x1800772f9  add     rsp, 20h
0x1800772fd  pop     rbx
0x1800772fe  retn
0x180077300  mov     [r10+24h], ebx
0x180077304  mov     [r10+28h], bl
0x180077308  mov     [r10+10h], rbx
0x18007730c  mov     [r10+18h], rbx
0x180077310  cmp     [r10+2Ah], bx
0x180077315  jbe     short loc_18007733A
0x180077317  movzx   eax, word ptr [r10+2Ah]
0x18007731c  mov     ecx, 20h ; ' '
0x180077321  dec     eax
0x180077323  cdq
0x180077324  idiv    ecx
0x180077326  mov     rcx, [r10+30h]; void *
0x18007732a  xor     edx, edx; Val
0x18007732c  inc     eax
0x18007732e  movsxd  r8, eax
0x180077331  shl     r8, 2; Size
0x180077335  call    memset
0x18007733a  add     rsp, 20h
0x18007733e  pop     rbx
0x18007733f  retn
```
