# McGenControlCallbackV2

- ea: `0x1800037f0`
- end: `0x1800038f0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800037f0`
- `0x180003bb2`

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
0x1800037f0  push    rbx
0x1800037f2  sub     rsp, 20h
0x1800037f6  mov     r10, [rsp+28h+CallbackContext]
0x1800037fb  xor     ebx, ebx
0x1800037fd  test    r10, r10
0x180003800  jz      loc_1800038EA
0x180003806  test    edx, edx
0x180003808  jz      loc_1800038AF
0x18000380e  cmp     edx, 1
0x180003811  jnz     loc_1800038EA
0x180003817  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000381c  mov     [r10+28h], r8b
0x180003820  mov     r8d, ebx
0x180003823  mov     [r10+18h], rax
0x180003827  mov     [r10+10h], r9
0x18000382b  mov     [r10+24h], edx
0x18000382f  cmp     bx, [r10+2Ah]
0x180003834  jnb     loc_1800038EA
0x18000383a  mov     rax, [r10+40h]
0x18000383e  mov     cl, [r10+28h]
0x180003842  mov     r9d, r8d
0x180003845  cmp     [r9+rax], cl
0x180003849  jbe     short loc_18000384F
0x18000384b  test    cl, cl
0x18000384d  jnz     short loc_18000386F
0x18000384f  mov     rax, [r10+38h]
0x180003853  mov     rcx, [rax+r9*8]
0x180003857  test    rcx, rcx
0x18000385a  jz      short loc_180003874
0x18000385c  test    [r10+10h], rcx
0x180003860  jz      short loc_18000386F
0x180003862  mov     rax, [r10+18h]
0x180003866  and     rax, rcx
0x180003869  cmp     rax, [r10+18h]
0x18000386d  jz      short loc_180003874
0x18000386f  mov     r11b, bl
0x180003872  jmp     short loc_180003877
0x180003874  mov     r11b, 1
0x180003877  mov     rax, [r10+30h]
0x18000387b  mov     ecx, r8d
0x18000387e  shr     r9, 5
0x180003882  mov     edx, 1
0x180003887  shl     edx, cl
0x180003889  lea     rcx, [rax+r9*4]
0x18000388d  test    r11b, r11b
0x180003890  jz      short loc_180003896
0x180003892  or      edx, [rcx]
0x180003894  jmp     short loc_18000389A
0x180003896  not     edx
0x180003898  and     edx, [rcx]
0x18000389a  mov     [rcx], edx
0x18000389c  inc     r8d
0x18000389f  movzx   eax, word ptr [r10+2Ah]
0x1800038a4  cmp     r8d, eax
0x1800038a7  jb      short loc_18000383A
0x1800038a9  add     rsp, 20h
0x1800038ad  pop     rbx
0x1800038ae  retn
0x1800038af  mov     [r10+24h], ebx
0x1800038b3  mov     [r10+28h], bl
0x1800038b7  mov     [r10+10h], rbx
0x1800038bb  mov     [r10+18h], rbx
0x1800038bf  cmp     [r10+2Ah], bx
0x1800038c4  jbe     short loc_1800038EA
0x1800038c6  movzx   eax, word ptr [r10+2Ah]
0x1800038cb  mov     rcx, [r10+30h]; void *
0x1800038cf  dec     eax
0x1800038d1  cdq
0x1800038d2  and     edx, 1Fh
0x1800038d5  add     eax, edx
0x1800038d7  xor     edx, edx; Val
0x1800038d9  sar     eax, 5
0x1800038dc  inc     eax
0x1800038de  movsxd  r8, eax
0x1800038e1  shl     r8, 2; Size
0x1800038e5  call    memset_0
0x1800038ea  add     rsp, 20h
0x1800038ee  pop     rbx
0x1800038ef  retn
```
