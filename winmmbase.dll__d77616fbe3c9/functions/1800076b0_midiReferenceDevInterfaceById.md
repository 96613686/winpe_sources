# midiReferenceDevInterfaceById

- ea: `0x1800076b0`
- end: `0x1800077e3`
- name: `midiReferenceDevInterfaceById`
- size: `307`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800087a0`
- `0x180009160`
- `0x18000e860`
- `0x180018bb0`
- `0x1800194d0`
- `0x180019740`
- `0x180019bc0`

## callees

- `0x18000233c`
- `0x180007560`
- `0x1800076b0`
- `0x180007d70`
- `0x18000dd28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800076ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800076ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000773b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000773b`

## pseudocode

```c
__int64 __fastcall midiReferenceDevInterfaceById(__int64 *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rsi
  __int64 v4; // rbx
  int v5; // ebp
  __int64 v6; // rdi
  __int64 v8; // rbx

  v2 = a2;
  if ( (a1 != &midioutdrvZ || !ValidateHandle(a2, 3)) && (a1 != &midiindrvZ || !ValidateHandle(v2, 4)) )
  {
    if ( (_DWORD)v2 == -1 )
      MidiMapperInit();
    EnterCriticalSection(&NumDevsCritSec);
    v4 = *a1;
    v5 = 2;
    if ( (_DWORD)v2 == -1 )
    {
      while ( (__int64 *)v4 != a1 )
      {
        if ( (*(_BYTE *)(v4 + 112) & 2) != 0 )
          goto LABEL_12;
        v4 = *(_QWORD *)v4;
      }
    }
    else if ( (__int64 *)v4 != a1 )
    {
      do
      {
        if ( (*(_BYTE *)(v4 + 112) & 2) == 0 )
        {
          if ( *(_DWORD *)(v4 + 88) > (unsigned int)v2 )
            break;
          LODWORD(v2) = v2 - *(_DWORD *)(v4 + 88);
        }
        v4 = *(_QWORD *)v4;
      }
      while ( (__int64 *)v4 != a1 );
      if ( (__int64 *)v4 != a1 )
      {
LABEL_12:
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 92));
        v5 = 0;
        goto LABEL_13;
      }
    }
    v4 = 0;
LABEL_13:
    LeaveCriticalSection(&NumDevsCritSec);
    if ( v5 )
      return 0;
    v6 = *(_QWORD *)(v4 + 104);
    if ( *(_QWORD *)(v4 + 96) )
      wdmDevInterfaceInc();
    mregDecUsagePtr((struct _MMDRV *)v4);
    return v6;
  }
  v8 = *(_QWORD *)(*(_QWORD *)v2 + 104LL);
  if ( *(_QWORD *)(*(_QWORD *)v2 + 96LL) )
    wdmDevInterfaceInc();
  return v8;
}

```

## disassembly

```asm
0x1800076b0  push    rbx
0x1800076b2  push    rbp
0x1800076b3  push    rsi
0x1800076b4  push    rdi
0x1800076b5  sub     rsp, 28h
0x1800076b9  lea     rax, midioutdrvZ
0x1800076c0  mov     rsi, rdx
0x1800076c3  mov     rdi, rcx
0x1800076c6  cmp     rcx, rax
0x1800076c9  jz      loc_18000776A
0x1800076cf  lea     rax, midiindrvZ
0x1800076d6  cmp     rdi, rax
0x1800076d9  jz      loc_180007794
0x1800076df  cmp     esi, 0FFFFFFFFh
0x1800076e2  jz      loc_1800077C4
0x1800076e8  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800076ef  call    cs:__imp_EnterCriticalSection
0x1800076f5  mov     rbx, [rdi]
0x1800076f8  mov     ebp, 2
0x1800076fd  cmp     esi, 0FFFFFFFFh
0x180007700  jz      loc_1800077B8
0x180007706  cmp     rbx, rdi
0x180007709  jz      loc_1800077BD
0x18000770f  test    [rbx+70h], bpl
0x180007713  jnz     short loc_18000771D
0x180007715  cmp     [rbx+58h], esi
0x180007718  ja      short loc_180007725
0x18000771a  sub     esi, [rbx+58h]
0x18000771d  mov     rbx, [rbx]
0x180007720  cmp     rbx, rdi
0x180007723  jnz     short loc_18000770F
0x180007725  cmp     rbx, rdi
0x180007728  jz      loc_1800077BD
0x18000772e  lock inc dword ptr [rbx+5Ch]
0x180007732  xor     ebp, ebp
0x180007734  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000773b  call    cs:__imp_LeaveCriticalSection
0x180007741  test    ebp, ebp
0x180007743  jnz     loc_1800077CE
0x180007749  mov     rcx, [rbx+60h]
0x18000774d  mov     rdi, [rbx+68h]
0x180007751  test    rcx, rcx
0x180007754  jnz     short loc_1800077D2
0x180007756  mov     rcx, rbx; struct _MMDRV *
0x180007759  call    mregDecUsagePtr
0x18000775e  mov     rax, rdi
0x180007761  add     rsp, 28h
0x180007765  pop     rdi
0x180007766  pop     rsi
0x180007767  pop     rbp
0x180007768  pop     rbx
0x180007769  retn
0x18000776a  mov     edx, 3
0x18000776f  mov     rcx, rsi
0x180007772  call    ValidateHandle
0x180007777  test    eax, eax
0x180007779  jz      loc_1800076CF
0x18000777f  mov     rax, [rsi]
0x180007782  mov     rcx, [rax+60h]
0x180007786  mov     rbx, [rax+68h]
0x18000778a  test    rcx, rcx
0x18000778d  jnz     short loc_1800077DC
0x18000778f  mov     rax, rbx
0x180007792  jmp     short loc_180007761
0x180007794  mov     edx, 4
0x180007799  mov     rcx, rsi
0x18000779c  call    ValidateHandle
0x1800077a1  test    eax, eax
0x1800077a3  jz      loc_1800076DF
0x1800077a9  jmp     short loc_18000777F
0x1800077ab  test    [rbx+70h], bpl
0x1800077af  jnz     loc_18000772E
0x1800077b5  mov     rbx, [rbx]
0x1800077b8  cmp     rbx, rdi
0x1800077bb  jnz     short loc_1800077AB
0x1800077bd  xor     ebx, ebx
0x1800077bf  jmp     loc_180007734
0x1800077c4  call    MidiMapperInit
0x1800077c9  jmp     loc_1800076E8
0x1800077ce  xor     eax, eax
0x1800077d0  jmp     short loc_180007761
0x1800077d2  call    wdmDevInterfaceInc
0x1800077d7  jmp     loc_180007756
0x1800077dc  call    wdmDevInterfaceInc
0x1800077e1  jmp     short loc_18000778F
```
