# McGenControlCallbackV2

- ea: `0x140016070`
- end: `0x140016192`
- name: `McGenControlCallbackV2`
- size: `290`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140016070`
- `0x14001f980`
- `0x140033018`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned __int8 v7; // cl
  __int64 v8; // rdx
  bool v9; // r11
  int v10; // edx
  unsigned int Data1; // eax
  int v12; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        *(_QWORD *)&Level = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        *((_DWORD *)CallbackContext + 9) = 1;
        if ( *((_WORD *)CallbackContext + 21) )
        {
          do
          {
            v7 = *((_BYTE *)CallbackContext + 40);
            v9 = 0;
            if ( *(_BYTE *)(Level + *((_QWORD *)CallbackContext + 8)) <= v7 || !v7 )
            {
              v8 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * Level);
              if ( !v8
                || (v8 & *((_QWORD *)CallbackContext + 2)) != 0
                && (v8 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
              {
                v9 = 1;
              }
            }
            MatchAnyKeyword = (unsigned __int64)Level >> 5;
            v10 = 1 << Level;
            SourceId = (LPCGUID)(*((_QWORD *)CallbackContext + 6) + 4 * MatchAnyKeyword);
            Data1 = SourceId->Data1;
            if ( v9 )
              *(_QWORD *)&ControlCode = Data1 | v10;
            else
              *(_QWORD *)&ControlCode = Data1 & ~v10;
            SourceId->Data1 = ControlCode;
            *(_QWORD *)&Level = (unsigned int)(Level + 1);
          }
          while ( Level < (unsigned int)*((unsigned __int16 *)CallbackContext + 21) );
        }
      }
      else
      {
        *(_QWORD *)&ControlCode = ControlCode - 1;
        if ( ControlCode )
        {
          if ( ControlCode != 1 )
            return;
LABEL_20:
          SlbNatEtwRundown(SourceId, *(_QWORD *)&ControlCode, Level, MatchAnyKeyword);
          return;
        }
      }
      _InterlockedExchange64(&qword_140027480, 0);
      goto LABEL_20;
    }
    v12 = *((unsigned __int16 *)CallbackContext + 21);
    *((_DWORD *)CallbackContext + 9) = 0;
    *((_BYTE *)CallbackContext + 40) = 0;
    *((_QWORD *)CallbackContext + 2) = 0;
    *((_QWORD *)CallbackContext + 3) = 0;
    if ( (_WORD)v12 )
      memset(*((void **)CallbackContext + 6), 0, 4LL * ((v12 - 1) / 32 + 1));
  }
}

```

## disassembly

```asm
0x140016070  push    rbx
0x140016072  sub     rsp, 20h
0x140016076  mov     r10, [rsp+28h+CallbackContext]
0x14001607b  xor     ebx, ebx
0x14001607d  test    r10, r10
0x140016080  jz      loc_14001618B
0x140016086  mov     eax, edx
0x140016088  test    edx, edx
0x14001608a  jz      loc_140016153
0x140016090  cmp     eax, 1
0x140016093  jz      short loc_1400160AC
0x140016095  sub     edx, 1
0x140016098  jz      loc_140016142
0x14001609e  cmp     edx, 1
0x1400160a1  jz      loc_14001614C
0x1400160a7  jmp     loc_14001618B
0x1400160ac  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400160b1  mov     [r10+28h], r8b
0x1400160b5  mov     r8d, ebx
0x1400160b8  mov     [r10+18h], rax
0x1400160bc  mov     [r10+10h], r9
0x1400160c0  mov     dword ptr [r10+24h], 1
0x1400160c8  cmp     bx, [r10+2Ah]
0x1400160cd  jnb     short loc_140016142
0x1400160cf  mov     rax, [r10+40h]
0x1400160d3  mov     cl, [r10+28h]
0x1400160d7  mov     r9d, r8d
0x1400160da  cmp     [r9+rax], cl
0x1400160de  jbe     short loc_1400160E4
0x1400160e0  test    cl, cl
0x1400160e2  jnz     short loc_140016106
0x1400160e4  mov     rax, [r10+38h]
0x1400160e8  mov     rdx, [rax+r9*8]
0x1400160ec  test    rdx, rdx
0x1400160ef  jz      short loc_14001610B
0x1400160f1  test    [r10+10h], rdx
0x1400160f5  jz      short loc_140016106
0x1400160f7  mov     rcx, [r10+18h]
0x1400160fb  mov     rax, rcx
0x1400160fe  and     rax, rdx
0x140016101  cmp     rax, rcx
0x140016104  jz      short loc_14001610B
0x140016106  mov     r11b, bl
0x140016109  jmp     short loc_14001610E
0x14001610b  mov     r11b, 1
0x14001610e  mov     rax, [r10+30h]
0x140016112  mov     ecx, r8d
0x140016115  shr     r9, 5
0x140016119  mov     edx, 1
0x14001611e  shl     edx, cl
0x140016120  lea     rcx, [rax+r9*4]
0x140016124  mov     eax, [rcx]
0x140016126  test    r11b, r11b
0x140016129  jz      short loc_14001612F
0x14001612b  or      edx, eax
0x14001612d  jmp     short loc_140016133
0x14001612f  not     edx
0x140016131  and     edx, eax
0x140016133  mov     [rcx], edx
0x140016135  inc     r8d
0x140016138  movzx   eax, word ptr [r10+2Ah]
0x14001613d  cmp     r8d, eax
0x140016140  jb      short loc_1400160CF
0x140016142  mov     rax, rbx
0x140016145  xchg    rax, cs:qword_140027480
0x14001614c  call    SlbNatEtwRundown
0x140016151  jmp     short loc_14001618B
0x140016153  movzx   eax, word ptr [r10+2Ah]
0x140016158  mov     [r10+24h], ebx
0x14001615c  mov     [r10+28h], bl
0x140016160  mov     [r10+10h], rbx
0x140016164  mov     [r10+18h], rbx
0x140016168  test    ax, ax
0x14001616b  jz      short loc_14001618B
0x14001616d  dec     eax
0x14001616f  mov     ecx, 20h ; ' '
0x140016174  cdq
0x140016175  idiv    ecx
0x140016177  mov     rcx, [r10+30h]; void *
0x14001617b  xor     edx, edx; Val
0x14001617d  inc     eax
0x14001617f  movsxd  r8, eax
0x140016182  shl     r8, 2; Size
0x140016186  call    memset
0x14001618b  add     rsp, 20h
0x14001618f  pop     rbx
0x140016190  retn
```
