# RtlCopyLUtf8StringToLUnicodeString

- ea: `0x1800092dc`
- end: `0x1800093c1`
- name: `RtlCopyLUtf8StringToLUnicodeString`
- size: `229`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015b40`

## callees

- `0x180007568`
- `0x180008e30`
- `0x1800092dc`
- `0x1800093c8`

## string_xrefs

- `0x180009316`: `RtlCopyLUtf8StringToLUnicodeString`
- `0x180009346`: `RtlCopyLUtf8StringToLUnicodeString`
- `0x180009395`: `RtlCopyLUtf8StringToLUnicodeString`

## pseudocode

```c
__int64 __fastcall RtlCopyLUtf8StringToLUnicodeString(__int64 a1, _QWORD *a2, __int64 a3)
{
  bool v3; // zf
  int v4; // eax
  unsigned int v5; // ecx

  if ( !a2 || (v3 = a2[2] == 0, *a2 = 0, v3) && a2[1] || !(unsigned __int8)RtlIsLUtf8StringValid(a1, a2, a3) )
  {
    RtlReportErrorOrigination(a1, a2, 3221225485LL);
    return 3221225485LL;
  }
  else
  {
    v4 = RtlTranscodeLBlobs(0, 0, 106, a1, 1014, (__int64)a2);
    v5 = 0;
    if ( v4 < 0 )
      return (unsigned int)v4;
    return v5;
  }
}

```

## disassembly

```asm
0x1800092dc  push    rbp
0x1800092de  mov     rbp, rsp
0x1800092e1  sub     rsp, 50h
0x1800092e5  test    rdx, rdx
0x1800092e8  jz      loc_180009382
0x1800092ee  cmp     qword ptr [rdx+10h], 0
0x1800092f3  mov     qword ptr [rdx], 0
0x1800092fa  jnz     short loc_18000932A
0x1800092fc  cmp     qword ptr [rdx+8], 0
0x180009301  jz      short loc_18000932A
0x180009303  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lutf8_string.cp"...
0x18000930a  mov     [rbp+var_10], 0F0h
0x180009312  mov     [rbp+var_20], rax
0x180009316  lea     rax, aRtlcopylutf8st; "RtlCopyLUtf8StringToLUnicodeString"
0x18000931d  mov     [rbp+var_18], rax
0x180009321  lea     rax, aDestinationBuf; "(Destination->Buffer != 0) || (Destinat"...
0x180009328  jmp     short loc_1800093A7
0x18000932a  call    RtlIsLUtf8StringValid
0x18000932f  test    al, al
0x180009331  jnz     short loc_18000935A
0x180009333  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lutf8_string.cp"...
0x18000933a  mov     [rbp+var_10], 0F1h
0x180009342  mov     [rbp+var_20], rax
0x180009346  lea     rax, aRtlcopylutf8st; "RtlCopyLUtf8StringToLUnicodeString"
0x18000934d  mov     [rbp+var_18], rax
0x180009351  lea     rax, aRtlislutf8stri_0; "RtlIsLUtf8StringValid(Source)"
0x180009358  jmp     short loc_1800093A7
0x18000935a  mov     [rsp+50h+var_28], rdx
0x18000935f  mov     r9, rcx
0x180009362  xor     edx, edx
0x180009364  mov     [rsp+50h+var_30], 3F6h
0x18000936c  xor     ecx, ecx
0x18000936e  lea     r8d, [rdx+6Ah]
0x180009372  call    RtlTranscodeLBlobs
0x180009377  xor     ecx, ecx
0x180009379  test    eax, eax
0x18000937b  cmovs   ecx, eax
0x18000937e  mov     eax, ecx
0x180009380  jmp     short loc_1800093BB
0x180009382  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lutf8_string.cp"...
0x180009389  mov     [rbp+var_10], 0EFh
0x180009391  mov     [rbp+var_20], rax
0x180009395  lea     rax, aRtlcopylutf8st; "RtlCopyLUtf8StringToLUnicodeString"
0x18000939c  mov     [rbp+var_18], rax
0x1800093a0  lea     rax, aNotNullCheckFa_6; "Not-null check failed: Destination"
0x1800093a7  mov     r8d, 0C000000Dh
0x1800093ad  mov     [rbp+var_8], rax
0x1800093b1  call    RtlReportErrorOrigination
0x1800093b6  mov     eax, 0C000000Dh
0x1800093bb  add     rsp, 50h
0x1800093bf  pop     rbp
0x1800093c0  retn
```
