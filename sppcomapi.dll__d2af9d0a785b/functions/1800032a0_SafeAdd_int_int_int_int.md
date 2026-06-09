# SafeAdd<int>(int,int,int *)

- ea: `0x1800032a0`
- end: `0x18000330f`
- name: `??$SafeAdd@H@@YAJHHPEAH@Z`
- size: `111`
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

- `0x1800032a0`
- `0x180003520`
- `0x180004288`

## pseudocode

```c
__int64 __fastcall SafeAdd<int>(int a1, __int64 a2, int *a3)
{
  int v4; // edi
  int v5; // ebx

  if ( a1 < 0 )
  {
    v5 = -2147024809;
    goto LABEL_10;
  }
  v4 = a1 + 1;
  if ( a1 + 1 < (unsigned int)a1 )
  {
    v5 = -2147024362;
    v4 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  else
  {
    v5 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v5 < 0 )
    goto LABEL_10;
  if ( v4 < 0 )
  {
    v5 = -2147024362;
LABEL_10:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_11;
  }
  *a3 = v4;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800032a0  mov     [rsp+arg_0], rbx
0x1800032a5  mov     [rsp+arg_8], rsi
0x1800032aa  push    rdi
0x1800032ab  sub     rsp, 20h
0x1800032af  mov     rsi, r8
0x1800032b2  test    ecx, ecx
0x1800032b4  js      short loc_1800032E9
0x1800032b6  lea     edi, [rcx+1]
0x1800032b9  cmp     edi, ecx
0x1800032bb  jb      short loc_1800032C1
0x1800032bd  xor     ebx, ebx
0x1800032bf  jmp     short loc_1800032CF
0x1800032c1  mov     ebx, 80070216h
0x1800032c6  xor     edi, edi
0x1800032c8  mov     ecx, ebx
0x1800032ca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800032cf  mov     ecx, ebx
0x1800032d1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800032d6  test    ebx, ebx
0x1800032d8  js      short loc_1800032EE
0x1800032da  test    edi, edi
0x1800032dc  jns     short loc_1800032E5
0x1800032de  mov     ebx, 80070216h
0x1800032e3  jmp     short loc_1800032EE
0x1800032e5  mov     [rsi], edi
0x1800032e7  jmp     short loc_1800032F5
0x1800032e9  mov     ebx, 80070057h
0x1800032ee  mov     ecx, ebx
0x1800032f0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800032f5  mov     ecx, ebx
0x1800032f7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800032fc  mov     rsi, [rsp+28h+arg_8]
0x180003301  mov     eax, ebx
0x180003303  mov     rbx, [rsp+28h+arg_0]
0x180003308  add     rsp, 20h
0x18000330c  pop     rdi
0x18000330d  retn
```
