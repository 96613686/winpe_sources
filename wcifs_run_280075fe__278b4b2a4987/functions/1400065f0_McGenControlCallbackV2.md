# McGenControlCallbackV2

- ea: `0x1400065f0`
- end: `0x1400066ee`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400065f0`
- `0x1400080c0`

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
0x1400065f0  push    rbx
0x1400065f2  sub     rsp, 20h
0x1400065f6  mov     r10, [rsp+28h+CallbackContext]
0x1400065fb  xor     ebx, ebx
0x1400065fd  test    r10, r10
0x140006600  jz      loc_1400066E7
0x140006606  test    edx, edx
0x140006608  jz      loc_1400066AF
0x14000660e  cmp     edx, 1
0x140006611  jnz     loc_1400066E7
0x140006617  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000661c  mov     [r10+28h], r8b
0x140006620  mov     r8d, ebx
0x140006623  mov     [r10+18h], rax
0x140006627  mov     [r10+10h], r9
0x14000662b  mov     [r10+24h], edx
0x14000662f  cmp     bx, [r10+2Ah]
0x140006634  jnb     loc_1400066E7
0x14000663a  mov     rax, [r10+40h]
0x14000663e  mov     cl, [r10+28h]
0x140006642  mov     r9d, r8d
0x140006645  cmp     [r9+rax], cl
0x140006649  jbe     short loc_14000664F
0x14000664b  test    cl, cl
0x14000664d  jnz     short loc_140006671
0x14000664f  mov     rax, [r10+38h]
0x140006653  mov     rdx, [rax+r9*8]
0x140006657  test    rdx, rdx
0x14000665a  jz      short loc_140006676
0x14000665c  test    [r10+10h], rdx
0x140006660  jz      short loc_140006671
0x140006662  mov     rcx, [r10+18h]
0x140006666  mov     rax, rcx
0x140006669  and     rax, rdx
0x14000666c  cmp     rax, rcx
0x14000666f  jz      short loc_140006676
0x140006671  mov     r11b, bl
0x140006674  jmp     short loc_140006679
0x140006676  mov     r11b, 1
0x140006679  mov     rax, [r10+30h]
0x14000667d  mov     ecx, r8d
0x140006680  shr     r9, 5
0x140006684  mov     edx, 1
0x140006689  shl     edx, cl
0x14000668b  lea     rcx, [rax+r9*4]
0x14000668f  mov     eax, [rcx]
0x140006691  test    r11b, r11b
0x140006694  jz      short loc_14000669A
0x140006696  or      edx, eax
0x140006698  jmp     short loc_14000669E
0x14000669a  not     edx
0x14000669c  and     edx, eax
0x14000669e  mov     [rcx], edx
0x1400066a0  inc     r8d
0x1400066a3  movzx   eax, word ptr [r10+2Ah]
0x1400066a8  cmp     r8d, eax
0x1400066ab  jb      short loc_14000663A
0x1400066ad  jmp     short loc_1400066E7
0x1400066af  movzx   eax, word ptr [r10+2Ah]
0x1400066b4  mov     [r10+24h], ebx
0x1400066b8  mov     [r10+28h], bl
0x1400066bc  mov     [r10+10h], rbx
0x1400066c0  mov     [r10+18h], rbx
0x1400066c4  test    ax, ax
0x1400066c7  jz      short loc_1400066E7
0x1400066c9  dec     eax
0x1400066cb  mov     ecx, 20h ; ' '
0x1400066d0  cdq
0x1400066d1  idiv    ecx
0x1400066d3  mov     rcx, [r10+30h]; void *
0x1400066d7  xor     edx, edx; Val
0x1400066d9  inc     eax
0x1400066db  movsxd  r8, eax
0x1400066de  shl     r8, 2; Size
0x1400066e2  call    memset
0x1400066e7  add     rsp, 20h
0x1400066eb  pop     rbx
0x1400066ec  retn
```
