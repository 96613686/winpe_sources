# RtlReallocateLBlob

- ea: `0x180008954`
- end: `0x180008aa4`
- name: `RtlReallocateLBlob`
- size: `336`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007cc0`

## callees

- `0x180007568`
- `0x180008954`
- `0x1800093f0`
- `0x180009430`

## string_xrefs

- `0x1800089f3`: `Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)`
- `0x180008a3e`: `Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))`

## pseudocode

```c
__int64 __fastcall RtlReallocateLBlob(__int64 a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rax
  __int64 StringRoutine; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx

  v4 = a2;
  if ( a3 )
  {
    a2 = a3[2];
    if ( a2 || !*a3 )
    {
      v5 = a3[1];
      if ( *a3 <= v5 )
      {
        if ( a2 )
        {
          if ( v5 >= v4 )
            return 0;
          StringRoutine = anonymous_namespace_::OurRtlReallocateStringRoutine(v4);
          if ( !StringRoutine )
          {
LABEL_8:
            RtlReportErrorOrigination(v8, v7, 3221225495LL);
            return 3221225495LL;
          }
        }
        else
        {
          StringRoutine = anonymous_namespace_::OurRtlAllocateStringRoutine(v4);
          if ( !StringRoutine )
            goto LABEL_8;
        }
        a3[2] = StringRoutine;
        a3[1] = v4;
        if ( *a3 > v4 )
          *a3 = v4;
        return 0;
      }
    }
  }
  RtlReportErrorOrigination(a1, a2, 3221225485LL);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180008954  mov     [rsp-8+arg_0], rbx
0x180008959  mov     [rsp-8+arg_18], rdi
0x18000895e  push    rbp
0x18000895f  mov     rbp, rsp
0x180008962  sub     rsp, 40h
0x180008966  mov     rbx, r8
0x180008969  mov     rdi, rdx
0x18000896c  test    r8, r8
0x18000896f  jnz     short loc_18000899B
0x180008971  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180008978  mov     [rbp+var_10], 82h
0x180008980  mov     [rbp+var_20], rax
0x180008984  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x18000898b  mov     [rbp+var_18], rax
0x18000898f  lea     rax, aNotNullCheckFa_18; "Not-null check failed: Blob"
0x180008996  jmp     loc_180008A80
0x18000899b  mov     rdx, [r8+10h]
0x18000899f  test    rdx, rdx
0x1800089a2  jnz     short loc_1800089AD
0x1800089a4  cmp     [r8], rdx
0x1800089a7  jnz     loc_180008A5B
0x1800089ad  mov     rax, [r8+8]
0x1800089b1  cmp     [r8], rax
0x1800089b4  ja      loc_180008A5B
0x1800089ba  test    rdx, rdx
0x1800089bd  jz      short loc_180008A13
0x1800089bf  cmp     rax, rdi
0x1800089c2  jnb     loc_180008A57
0x1800089c8  mov     rcx, rdi
0x1800089cb  call    _anonymous_namespace___OurRtlReallocateStringRoutine
0x1800089d0  test    rax, rax
0x1800089d3  jnz     short loc_180008A47
0x1800089d5  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x1800089dc  mov     [rbp+var_10], 94h
0x1800089e4  mov     [rbp+var_20], rax
0x1800089e8  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x1800089ef  mov     [rbp+var_18], rax
0x1800089f3  lea     rax, aTempRtlrealloc; "Temp = (*RtlReallocateStringRoutine)(By"...
0x1800089fa  mov     r8d, 0C0000017h
0x180008a00  mov     [rbp+var_8], rax
0x180008a04  call    RtlReportErrorOrigination
0x180008a09  mov     eax, 0C0000017h
0x180008a0e  jmp     loc_180008A94
0x180008a13  mov     rcx, rdi
0x180008a16  call    _anonymous_namespace___OurRtlAllocateStringRoutine
0x180008a1b  test    rax, rax
0x180008a1e  jnz     short loc_180008A47
0x180008a20  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180008a27  mov     [rbp+var_10], 99h
0x180008a2f  mov     [rbp+var_20], rax
0x180008a33  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x180008a3a  mov     [rbp+var_18], rax
0x180008a3e  lea     rax, aTempPucharRtla; "Temp = (PUCHAR)((*RtlAllocateStringRout"...
0x180008a45  jmp     short loc_1800089FA
0x180008a47  mov     [rbx+10h], rax
0x180008a4b  mov     [rbx+8], rdi
0x180008a4f  cmp     [rbx], rdi
0x180008a52  jbe     short loc_180008A57
0x180008a54  mov     [rbx], rdi
0x180008a57  xor     eax, eax
0x180008a59  jmp     short loc_180008A94
0x180008a5b  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180008a62  mov     [rbp+var_10], 83h
0x180008a6a  mov     [rbp+var_20], rax
0x180008a6e  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x180008a75  mov     [rbp+var_18], rax
0x180008a79  lea     rax, aRtlislblobvali_0; "::RtlIsLBlobValid(Blob)"
0x180008a80  mov     r8d, 0C000000Dh
0x180008a86  mov     [rbp+var_8], rax
0x180008a8a  call    RtlReportErrorOrigination
0x180008a8f  mov     eax, 0C000000Dh
0x180008a94  mov     rbx, [rsp+40h+arg_0]
0x180008a99  mov     rdi, [rsp+40h+arg_18]
0x180008a9e  add     rsp, 40h
0x180008aa2  pop     rbp
0x180008aa3  retn
```
