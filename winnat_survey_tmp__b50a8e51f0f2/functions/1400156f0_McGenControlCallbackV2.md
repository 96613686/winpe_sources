# McGenControlCallbackV2

- ea: `0x1400156f0`
- end: `0x140015812`
- name: `McGenControlCallbackV2`
- size: `290`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400156f0`
- `0x14001f440`
- `0x140031ee8`

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
      _InterlockedExchange64(&qword_140026480, 0);
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
0x1400156f0  push    rbx
0x1400156f2  sub     rsp, 20h
0x1400156f6  mov     r10, [rsp+28h+CallbackContext]
0x1400156fb  xor     ebx, ebx
0x1400156fd  test    r10, r10
0x140015700  jz      loc_14001580B
0x140015706  mov     eax, edx
0x140015708  test    edx, edx
0x14001570a  jz      loc_1400157D3
0x140015710  cmp     eax, 1
0x140015713  jz      short loc_14001572C
0x140015715  sub     edx, 1
0x140015718  jz      loc_1400157C2
0x14001571e  cmp     edx, 1
0x140015721  jz      loc_1400157CC
0x140015727  jmp     loc_14001580B
0x14001572c  mov     rax, [rsp+28h+MatchAllKeyword]
0x140015731  mov     [r10+28h], r8b
0x140015735  mov     r8d, ebx
0x140015738  mov     [r10+18h], rax
0x14001573c  mov     [r10+10h], r9
0x140015740  mov     dword ptr [r10+24h], 1
0x140015748  cmp     bx, [r10+2Ah]
0x14001574d  jnb     short loc_1400157C2
0x14001574f  mov     rax, [r10+40h]
0x140015753  mov     cl, [r10+28h]
0x140015757  mov     r9d, r8d
0x14001575a  cmp     [r9+rax], cl
0x14001575e  jbe     short loc_140015764
0x140015760  test    cl, cl
0x140015762  jnz     short loc_140015786
0x140015764  mov     rax, [r10+38h]
0x140015768  mov     rdx, [rax+r9*8]
0x14001576c  test    rdx, rdx
0x14001576f  jz      short loc_14001578B
0x140015771  test    [r10+10h], rdx
0x140015775  jz      short loc_140015786
0x140015777  mov     rcx, [r10+18h]
0x14001577b  mov     rax, rcx
0x14001577e  and     rax, rdx
0x140015781  cmp     rax, rcx
0x140015784  jz      short loc_14001578B
0x140015786  mov     r11b, bl
0x140015789  jmp     short loc_14001578E
0x14001578b  mov     r11b, 1
0x14001578e  mov     rax, [r10+30h]
0x140015792  mov     ecx, r8d
0x140015795  shr     r9, 5
0x140015799  mov     edx, 1
0x14001579e  shl     edx, cl
0x1400157a0  lea     rcx, [rax+r9*4]
0x1400157a4  mov     eax, [rcx]
0x1400157a6  test    r11b, r11b
0x1400157a9  jz      short loc_1400157AF
0x1400157ab  or      edx, eax
0x1400157ad  jmp     short loc_1400157B3
0x1400157af  not     edx
0x1400157b1  and     edx, eax
0x1400157b3  mov     [rcx], edx
0x1400157b5  inc     r8d
0x1400157b8  movzx   eax, word ptr [r10+2Ah]
0x1400157bd  cmp     r8d, eax
0x1400157c0  jb      short loc_14001574F
0x1400157c2  mov     rax, rbx
0x1400157c5  xchg    rax, cs:qword_140026480
0x1400157cc  call    SlbNatEtwRundown
0x1400157d1  jmp     short loc_14001580B
0x1400157d3  movzx   eax, word ptr [r10+2Ah]
0x1400157d8  mov     [r10+24h], ebx
0x1400157dc  mov     [r10+28h], bl
0x1400157e0  mov     [r10+10h], rbx
0x1400157e4  mov     [r10+18h], rbx
0x1400157e8  test    ax, ax
0x1400157eb  jz      short loc_14001580B
0x1400157ed  dec     eax
0x1400157ef  mov     ecx, 20h ; ' '
0x1400157f4  cdq
0x1400157f5  idiv    ecx
0x1400157f7  mov     rcx, [r10+30h]; void *
0x1400157fb  xor     edx, edx; Val
0x1400157fd  inc     eax
0x1400157ff  movsxd  r8, eax
0x140015802  shl     r8, 2; Size
0x140015806  call    memset
0x14001580b  add     rsp, 20h
0x14001580f  pop     rbx
0x140015810  retn
```
