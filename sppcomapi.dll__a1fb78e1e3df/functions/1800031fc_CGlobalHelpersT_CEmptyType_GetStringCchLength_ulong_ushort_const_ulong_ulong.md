# CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)

- ea: `0x1800031fc`
- end: `0x180003299`
- name: `??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180003950`
- `0x180003c18`
- `0x18000f3d0`
- `0x18001aae4`
- `0x18001e840`
- `0x18001ecb0`
- `0x18001f2a0`
- `0x180023134`
- `0x180036c54`
- `0x1800376c0`
- `0x18003b0e8`
- `0x18003b354`

## callees

- `0x1800031fc`
- `0x180003520`
- `0x180004288`

## pseudocode

```c
__int64 __fastcall CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(_WORD *a1, _DWORD *a2)
{
  __int64 v3; // r8
  int v4; // ebx
  __int64 v5; // rcx
  int v6; // edi

  if ( !a1 )
  {
    v4 = -2147024809;
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_13;
  }
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*a1 )
      break;
    ++a1;
    --v3;
  }
  while ( v3 );
  v4 = v3 == 0 ? 0x80070057 : 0;
  if ( !v3 )
    goto LABEL_12;
  v6 = v3 != 0 ? 0x7FFFFFFF - v3 : 0;
  v5 = (0x7FFFFFFF - v3) & -(__int64)(v3 != 0);
  if ( v5 == (unsigned int)v5 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v4 = 0;
  }
  else
  {
    v4 = -2147024362;
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v4 < 0 )
    goto LABEL_12;
  *a2 = v6;
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800031fc  push    rbx
0x1800031fe  push    rbp
0x1800031ff  push    rsi
0x180003200  push    rdi
0x180003201  sub     rsp, 28h
0x180003205  xor     ebp, ebp
0x180003207  mov     rsi, rdx
0x18000320a  test    rcx, rcx
0x18000320d  jz      short loc_18000327A
0x18000320f  mov     r9d, 7FFFFFFFh
0x180003215  mov     r8d, r9d
0x180003218  cmp     [rcx], bp
0x18000321b  jz      short loc_180003227
0x18000321d  add     rcx, 2
0x180003221  sub     r8, 1
0x180003225  jnz     short loc_180003218
0x180003227  mov     rax, r8
0x18000322a  neg     rax
0x18000322d  mov     rax, r8
0x180003230  sbb     ebx, ebx
0x180003232  sub     r9, r8
0x180003235  not     ebx
0x180003237  and     ebx, 80070057h
0x18000323d  neg     rax
0x180003240  sbb     rcx, rcx
0x180003243  and     rcx, r9
0x180003246  test    r8, r8
0x180003249  jz      short loc_18000327F
0x18000324b  mov     edi, ecx
0x18000324d  cmp     rcx, rdi
0x180003250  jz      short loc_180003262
0x180003252  mov     ebx, 80070216h
0x180003257  mov     edi, ebp
0x180003259  mov     ecx, ebx
0x18000325b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003260  jmp     short loc_18000326B
0x180003262  xor     ecx, ecx
0x180003264  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003269  mov     ebx, ebp
0x18000326b  mov     ecx, ebx
0x18000326d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003272  test    ebx, ebx
0x180003274  js      short loc_18000327F
0x180003276  mov     [rsi], edi
0x180003278  jmp     short loc_180003286
0x18000327a  mov     ebx, 80070057h
0x18000327f  mov     ecx, ebx
0x180003281  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003286  mov     ecx, ebx
0x180003288  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000328d  mov     eax, ebx
0x18000328f  add     rsp, 28h
0x180003293  pop     rdi
0x180003294  pop     rsi
0x180003295  pop     rbp
0x180003296  pop     rbx
0x180003297  retn
```
