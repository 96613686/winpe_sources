# McGenControlCallbackV2

- ea: `0x1400102b0`
- end: `0x1400103ae`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400102b0`
- `0x140012280`

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
0x1400102b0  push    rbx
0x1400102b2  sub     rsp, 20h
0x1400102b6  mov     r10, [rsp+28h+CallbackContext]
0x1400102bb  xor     ebx, ebx
0x1400102bd  test    r10, r10
0x1400102c0  jz      loc_1400103A7
0x1400102c6  test    edx, edx
0x1400102c8  jz      loc_14001036F
0x1400102ce  cmp     edx, 1
0x1400102d1  jnz     loc_1400103A7
0x1400102d7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400102dc  mov     [r10+28h], r8b
0x1400102e0  mov     r8d, ebx
0x1400102e3  mov     [r10+18h], rax
0x1400102e7  mov     [r10+10h], r9
0x1400102eb  mov     [r10+24h], edx
0x1400102ef  cmp     bx, [r10+2Ah]
0x1400102f4  jnb     loc_1400103A7
0x1400102fa  mov     rax, [r10+40h]
0x1400102fe  mov     cl, [r10+28h]
0x140010302  mov     r9d, r8d
0x140010305  cmp     [r9+rax], cl
0x140010309  jbe     short loc_14001030F
0x14001030b  test    cl, cl
0x14001030d  jnz     short loc_140010331
0x14001030f  mov     rax, [r10+38h]
0x140010313  mov     rdx, [rax+r9*8]
0x140010317  test    rdx, rdx
0x14001031a  jz      short loc_140010336
0x14001031c  test    [r10+10h], rdx
0x140010320  jz      short loc_140010331
0x140010322  mov     rcx, [r10+18h]
0x140010326  mov     rax, rcx
0x140010329  and     rax, rdx
0x14001032c  cmp     rax, rcx
0x14001032f  jz      short loc_140010336
0x140010331  mov     r11b, bl
0x140010334  jmp     short loc_140010339
0x140010336  mov     r11b, 1
0x140010339  mov     rax, [r10+30h]
0x14001033d  mov     ecx, r8d
0x140010340  shr     r9, 5
0x140010344  mov     edx, 1
0x140010349  shl     edx, cl
0x14001034b  lea     rcx, [rax+r9*4]
0x14001034f  mov     eax, [rcx]
0x140010351  test    r11b, r11b
0x140010354  jz      short loc_14001035A
0x140010356  or      edx, eax
0x140010358  jmp     short loc_14001035E
0x14001035a  not     edx
0x14001035c  and     edx, eax
0x14001035e  mov     [rcx], edx
0x140010360  inc     r8d
0x140010363  movzx   eax, word ptr [r10+2Ah]
0x140010368  cmp     r8d, eax
0x14001036b  jb      short loc_1400102FA
0x14001036d  jmp     short loc_1400103A7
0x14001036f  movzx   eax, word ptr [r10+2Ah]
0x140010374  mov     [r10+24h], ebx
0x140010378  mov     [r10+28h], bl
0x14001037c  mov     [r10+10h], rbx
0x140010380  mov     [r10+18h], rbx
0x140010384  test    ax, ax
0x140010387  jz      short loc_1400103A7
0x140010389  dec     eax
0x14001038b  mov     ecx, 20h ; ' '
0x140010390  cdq
0x140010391  idiv    ecx
0x140010393  mov     rcx, [r10+30h]; void *
0x140010397  xor     edx, edx; Val
0x140010399  inc     eax
0x14001039b  movsxd  r8, eax
0x14001039e  shl     r8, 2; Size
0x1400103a2  call    memset
0x1400103a7  add     rsp, 20h
0x1400103ab  pop     rbx
0x1400103ac  retn
```
