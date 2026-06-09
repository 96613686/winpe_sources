# McGenControlCallbackV2

- ea: `0x180007420`
- end: `0x180007523`
- name: `McGenControlCallbackV2`
- size: `259`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007420`
- `0x180015c9d`

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
          v11 = 1 << (v7 & 0x1F);
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
0x180007420  push    rbx
0x180007422  sub     rsp, 20h
0x180007426  mov     r10, [rsp+28h+CallbackContext]
0x18000742b  xor     ebx, ebx
0x18000742d  test    r10, r10
0x180007430  jz      loc_18000751D
0x180007436  test    edx, edx
0x180007438  jz      loc_1800074E2
0x18000743e  cmp     edx, 1
0x180007441  jnz     loc_18000751D
0x180007447  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000744c  mov     [r10+28h], r8b
0x180007450  mov     r8d, ebx
0x180007453  mov     [r10+18h], rax
0x180007457  mov     [r10+10h], r9
0x18000745b  mov     [r10+24h], edx
0x18000745f  cmp     bx, [r10+2Ah]
0x180007464  jnb     loc_18000751D
0x18000746a  mov     rax, [r10+40h]
0x18000746e  mov     cl, [r10+28h]
0x180007472  mov     r9d, r8d
0x180007475  cmp     [r9+rax], cl
0x180007479  jbe     short loc_18000747F
0x18000747b  test    cl, cl
0x18000747d  jnz     short loc_18000749F
0x18000747f  mov     rax, [r10+38h]
0x180007483  mov     rcx, [rax+r9*8]
0x180007487  test    rcx, rcx
0x18000748a  jz      short loc_1800074A4
0x18000748c  test    [r10+10h], rcx
0x180007490  jz      short loc_18000749F
0x180007492  mov     rax, [r10+18h]
0x180007496  and     rax, rcx
0x180007499  cmp     rax, [r10+18h]
0x18000749d  jz      short loc_1800074A4
0x18000749f  mov     r11b, bl
0x1800074a2  jmp     short loc_1800074A7
0x1800074a4  mov     r11b, 1
0x1800074a7  mov     rax, [r10+30h]
0x1800074ab  mov     ecx, r8d
0x1800074ae  and     ecx, 1Fh
0x1800074b1  shr     r9, 5
0x1800074b5  mov     edx, 1
0x1800074ba  shl     edx, cl
0x1800074bc  lea     rcx, [rax+r9*4]
0x1800074c0  test    r11b, r11b
0x1800074c3  jz      short loc_1800074C9
0x1800074c5  or      edx, [rcx]
0x1800074c7  jmp     short loc_1800074CD
0x1800074c9  not     edx
0x1800074cb  and     edx, [rcx]
0x1800074cd  mov     [rcx], edx
0x1800074cf  inc     r8d
0x1800074d2  movzx   eax, word ptr [r10+2Ah]
0x1800074d7  cmp     r8d, eax
0x1800074da  jb      short loc_18000746A
0x1800074dc  add     rsp, 20h
0x1800074e0  pop     rbx
0x1800074e1  retn
0x1800074e2  mov     [r10+24h], ebx
0x1800074e6  mov     [r10+28h], bl
0x1800074ea  mov     [r10+10h], rbx
0x1800074ee  mov     [r10+18h], rbx
0x1800074f2  cmp     [r10+2Ah], bx
0x1800074f7  jbe     short loc_18000751D
0x1800074f9  movzx   eax, word ptr [r10+2Ah]
0x1800074fe  mov     rcx, [r10+30h]; void *
0x180007502  dec     eax
0x180007504  cdq
0x180007505  and     edx, 1Fh
0x180007508  add     eax, edx
0x18000750a  xor     edx, edx; Val
0x18000750c  sar     eax, 5
0x18000750f  inc     eax
0x180007511  movsxd  r8, eax
0x180007514  shl     r8, 2; Size
0x180007518  call    memset_0
0x18000751d  add     rsp, 20h
0x180007521  pop     rbx
0x180007522  retn
```
