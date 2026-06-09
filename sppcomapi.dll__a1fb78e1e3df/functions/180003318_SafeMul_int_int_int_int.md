# SafeMul<int>(int,int,int *)

- ea: `0x180003318`
- end: `0x18000338f`
- name: `??$SafeMul@H@@YAJHHPEAH@Z`
- size: `119`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000405c`
- `0x18001ca2c`
- `0x18001cc48`
- `0x18001e9c4`
- `0x18001eb40`
- `0x180037118`

## callees

- `0x180003318`
- `0x180003520`
- `0x180004288`

## pseudocode

```c
__int64 __fastcall SafeMul<int>(int a1, __int64 a2, int *a3)
{
  int v4; // edi
  int v5; // ebx

  if ( a1 < 0 )
  {
    v5 = -2147024809;
    goto LABEL_12;
  }
  if ( a1 )
  {
    v4 = 2 * a1;
    if ( (unsigned int)(2 * a1) >> 1 != a1 )
    {
      v5 = -2147024362;
      v4 = 0;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
      goto LABEL_7;
    }
  }
  else
  {
    v4 = 0;
  }
  v5 = 0;
LABEL_7:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v5 < 0 )
  {
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_13;
  }
  if ( v4 < 0 )
  {
    v5 = -2147024362;
    goto LABEL_12;
  }
  *a3 = v4;
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003318  mov     [rsp+arg_0], rbx
0x18000331d  mov     [rsp+arg_8], rsi
0x180003322  push    rdi
0x180003323  sub     rsp, 20h
0x180003327  mov     rsi, r8
0x18000332a  test    ecx, ecx
0x18000332c  js      short loc_180003369
0x18000332e  jz      short loc_18000334B
0x180003330  lea     edi, [rcx+rcx]
0x180003333  mov     eax, edi
0x180003335  shr     eax, 1
0x180003337  cmp     eax, ecx
0x180003339  jz      short loc_18000334D
0x18000333b  mov     ebx, 80070216h
0x180003340  xor     edi, edi
0x180003342  mov     ecx, ebx
0x180003344  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003349  jmp     short loc_18000334F
0x18000334b  xor     edi, edi
0x18000334d  xor     ebx, ebx
0x18000334f  mov     ecx, ebx
0x180003351  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003356  test    ebx, ebx
0x180003358  js      short loc_18000336E
0x18000335a  test    edi, edi
0x18000335c  jns     short loc_180003365
0x18000335e  mov     ebx, 80070216h
0x180003363  jmp     short loc_18000336E
0x180003365  mov     [rsi], edi
0x180003367  jmp     short loc_180003375
0x180003369  mov     ebx, 80070057h
0x18000336e  mov     ecx, ebx
0x180003370  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003375  mov     ecx, ebx
0x180003377  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000337c  mov     rsi, [rsp+28h+arg_8]
0x180003381  mov     eax, ebx
0x180003383  mov     rbx, [rsp+28h+arg_0]
0x180003388  add     rsp, 20h
0x18000338c  pop     rdi
0x18000338d  retn
```
