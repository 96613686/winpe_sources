# McGenControlCallbackV2

- ea: `0x140001640`
- end: `0x14000173f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001640`
- `0x140002c40`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
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
          v13 = *v12;
          if ( v10 )
            v14 = v13 | v11;
          else
            v14 = v13 & ~v11;
          *v12 = v14;
        }
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x140001640  push    rbx
0x140001642  sub     rsp, 20h
0x140001646  mov     r10, [rsp+28h+CallbackContext]
0x14000164b  xor     ebx, ebx
0x14000164d  test    r10, r10
0x140001650  jz      loc_140001738
0x140001656  test    edx, edx
0x140001658  jz      loc_1400016FF
0x14000165e  cmp     edx, 1
0x140001661  jnz     loc_140001738
0x140001667  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000166c  mov     [r10+28h], r8b
0x140001670  mov     r8d, ebx
0x140001673  mov     [r10+18h], rax
0x140001677  mov     [r10+10h], r9
0x14000167b  mov     [r10+24h], edx
0x14000167f  cmp     bx, [r10+2Ah]
0x140001684  jnb     loc_140001738
0x14000168a  mov     rax, [r10+40h]
0x14000168e  mov     cl, [r10+28h]
0x140001692  mov     r9d, r8d
0x140001695  cmp     [r9+rax], cl
0x140001699  jbe     short loc_14000169F
0x14000169b  test    cl, cl
0x14000169d  jnz     short loc_1400016C1
0x14000169f  mov     rax, [r10+38h]
0x1400016a3  mov     rdx, [rax+r9*8]
0x1400016a7  test    rdx, rdx
0x1400016aa  jz      short loc_1400016C6
0x1400016ac  test    [r10+10h], rdx
0x1400016b0  jz      short loc_1400016C1
0x1400016b2  mov     rcx, [r10+18h]
0x1400016b6  mov     rax, rcx
0x1400016b9  and     rax, rdx
0x1400016bc  cmp     rax, rcx
0x1400016bf  jz      short loc_1400016C6
0x1400016c1  mov     r11b, bl
0x1400016c4  jmp     short loc_1400016C9
0x1400016c6  mov     r11b, 1
0x1400016c9  mov     rax, [r10+30h]
0x1400016cd  mov     ecx, r8d
0x1400016d0  shr     r9, 5
0x1400016d4  mov     edx, 1
0x1400016d9  shl     edx, cl
0x1400016db  lea     rcx, [rax+r9*4]
0x1400016df  mov     eax, [rcx]
0x1400016e1  test    r11b, r11b
0x1400016e4  jz      short loc_1400016EA
0x1400016e6  or      edx, eax
0x1400016e8  jmp     short loc_1400016EE
0x1400016ea  not     edx
0x1400016ec  and     edx, eax
0x1400016ee  mov     [rcx], edx
0x1400016f0  inc     r8d
0x1400016f3  movzx   eax, word ptr [r10+2Ah]
0x1400016f8  cmp     r8d, eax
0x1400016fb  jb      short loc_14000168A
0x1400016fd  jmp     short loc_140001738
0x1400016ff  movzx   eax, word ptr [r10+2Ah]
0x140001704  mov     [r10+24h], ebx
0x140001708  mov     [r10+28h], bl
0x14000170c  mov     [r10+10h], rbx
0x140001710  mov     [r10+18h], rbx
0x140001714  test    ax, ax
0x140001717  jz      short loc_140001738
0x140001719  mov     rcx, [r10+30h]; void *
0x14000171d  dec     eax
0x14000171f  cdq
0x140001720  and     edx, 1Fh
0x140001723  add     eax, edx
0x140001725  xor     edx, edx; Val
0x140001727  sar     eax, 5
0x14000172a  inc     eax
0x14000172c  movsxd  r8, eax
0x14000172f  shl     r8, 2; Size
0x140001733  call    memset
0x140001738  add     rsp, 20h
0x14000173c  pop     rbx
0x14000173d  retn
```
