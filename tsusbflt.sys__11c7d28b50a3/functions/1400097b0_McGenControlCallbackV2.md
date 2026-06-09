# McGenControlCallbackV2

- ea: `0x1400097b0`
- end: `0x1400098af`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400097b0`
- `0x14000ab00`

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
0x1400097b0  push    rbx
0x1400097b2  sub     rsp, 20h
0x1400097b6  mov     r10, [rsp+28h+CallbackContext]
0x1400097bb  xor     ebx, ebx
0x1400097bd  test    r10, r10
0x1400097c0  jz      loc_1400098A8
0x1400097c6  test    edx, edx
0x1400097c8  jz      loc_14000986F
0x1400097ce  cmp     edx, 1
0x1400097d1  jnz     loc_1400098A8
0x1400097d7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400097dc  mov     [r10+28h], r8b
0x1400097e0  mov     r8d, ebx
0x1400097e3  mov     [r10+18h], rax
0x1400097e7  mov     [r10+10h], r9
0x1400097eb  mov     [r10+24h], edx
0x1400097ef  cmp     bx, [r10+2Ah]
0x1400097f4  jnb     loc_1400098A8
0x1400097fa  mov     rax, [r10+40h]
0x1400097fe  mov     cl, [r10+28h]
0x140009802  mov     r9d, r8d
0x140009805  cmp     [r9+rax], cl
0x140009809  jbe     short loc_14000980F
0x14000980b  test    cl, cl
0x14000980d  jnz     short loc_140009831
0x14000980f  mov     rax, [r10+38h]
0x140009813  mov     rdx, [rax+r9*8]
0x140009817  test    rdx, rdx
0x14000981a  jz      short loc_140009836
0x14000981c  test    [r10+10h], rdx
0x140009820  jz      short loc_140009831
0x140009822  mov     rcx, [r10+18h]
0x140009826  mov     rax, rcx
0x140009829  and     rax, rdx
0x14000982c  cmp     rax, rcx
0x14000982f  jz      short loc_140009836
0x140009831  mov     r11b, bl
0x140009834  jmp     short loc_140009839
0x140009836  mov     r11b, 1
0x140009839  mov     rax, [r10+30h]
0x14000983d  mov     ecx, r8d
0x140009840  shr     r9, 5
0x140009844  mov     edx, 1
0x140009849  shl     edx, cl
0x14000984b  lea     rcx, [rax+r9*4]
0x14000984f  mov     eax, [rcx]
0x140009851  test    r11b, r11b
0x140009854  jz      short loc_14000985A
0x140009856  or      edx, eax
0x140009858  jmp     short loc_14000985E
0x14000985a  not     edx
0x14000985c  and     edx, eax
0x14000985e  mov     [rcx], edx
0x140009860  inc     r8d
0x140009863  movzx   eax, word ptr [r10+2Ah]
0x140009868  cmp     r8d, eax
0x14000986b  jb      short loc_1400097FA
0x14000986d  jmp     short loc_1400098A8
0x14000986f  movzx   eax, word ptr [r10+2Ah]
0x140009874  mov     [r10+24h], ebx
0x140009878  mov     [r10+28h], bl
0x14000987c  mov     [r10+10h], rbx
0x140009880  mov     [r10+18h], rbx
0x140009884  test    ax, ax
0x140009887  jz      short loc_1400098A8
0x140009889  mov     rcx, [r10+30h]; void *
0x14000988d  dec     eax
0x14000988f  cdq
0x140009890  and     edx, 1Fh
0x140009893  add     eax, edx
0x140009895  xor     edx, edx; Val
0x140009897  sar     eax, 5
0x14000989a  inc     eax
0x14000989c  movsxd  r8, eax
0x14000989f  shl     r8, 2; Size
0x1400098a3  call    memset
0x1400098a8  add     rsp, 20h
0x1400098ac  pop     rbx
0x1400098ad  retn
```
