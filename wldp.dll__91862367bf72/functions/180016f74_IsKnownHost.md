# IsKnownHost

- ea: `0x180016f74`
- end: `0x18001704c`
- name: `IsKnownHost`
- size: `216`
- prototype: `char __fastcall(void *Buf1)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002e5f0`
- `0x18002e8b0`
- `0x18002ecc0`
- `0x18002f2f0`

## callees

- `0x180016f74`
- `0x1800229ec`
- `0x18002e5d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016f96`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016f96`

## string_xrefs

- `0x18001703a`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
char __fastcall IsKnownHost(void *Buf1)
{
  const char *v2; // r9
  char v3; // si
  __int64 *v4; // r14
  __int64 *v5; // rdi
  __int64 *v6; // rbx
  char v7; // cl
  __int64 *v8; // rax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !InitOnceExecuteOnce(&InitOnce, ConstructHostList, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
      v2);
  if ( !Buf1 )
    return 0;
  v3 = 1;
  v4 = *(__int64 **)qword_18005B060;
  v5 = *(__int64 **)qword_18005B060;
  v6 = *(__int64 **)(*(_QWORD *)qword_18005B060 + 8LL);
  if ( !*((_BYTE *)v6 + 25) )
  {
    do
    {
      if ( memcmp_0(v6 + 4, Buf1, 0x10u) < 0 )
      {
        v7 = 1;
      }
      else
      {
        v7 = 0;
        v5 = v6;
      }
      v8 = v6 + 2;
      if ( !v7 )
        v8 = v6;
      v6 = (__int64 *)*v8;
    }
    while ( !*(_BYTE *)(*v8 + 25) );
  }
  if ( *((_BYTE *)v5 + 25) || memcmp_0(Buf1, v5 + 4, 0x10u) < 0 || v5 == v4 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x180016f74  push    rbx
0x180016f76  push    rbp
0x180016f77  push    rsi
0x180016f78  push    rdi
0x180016f79  push    r14
0x180016f7b  sub     rsp, 40h
0x180016f7f  mov     rbp, rcx
0x180016f82  lea     rdx, ConstructHostList; InitFn
0x180016f89  lea     rcx, InitOnce; InitOnce
0x180016f90  xor     r9d, r9d; Context
0x180016f93  xor     r8d, r8d; Parameter
0x180016f96  call    cs:__imp_InitOnceExecuteOnce
0x180016f9c  test    eax, eax
0x180016f9e  jz      loc_180017035
0x180016fa4  test    rbp, rbp
0x180016fa7  jz      loc_180017031
0x180016fad  mov     rax, cs:qword_18005B060
0x180016fb4  mov     sil, 1
0x180016fb7  mov     r14, [rax]
0x180016fba  xor     eax, eax
0x180016fbc  mov     [rsp+68h+var_3C], eax
0x180016fc0  mov     rdi, r14
0x180016fc3  mov     rbx, [r14+8]
0x180016fc7  cmp     [rbx+19h], al
0x180016fca  jnz     short loc_180016FFA
0x180016fcc  lea     rcx, [rbx+20h]; Buf1
0x180016fd0  mov     r8d, 10h; Size
0x180016fd6  mov     rdx, rbp; Buf2
0x180016fd9  call    memcmp_0
0x180016fde  test    eax, eax
0x180016fe0  js      short loc_18001702C
0x180016fe2  xor     cl, cl
0x180016fe4  mov     rdi, rbx
0x180016fe7  test    cl, cl
0x180016fe9  lea     rax, [rbx+10h]
0x180016fed  cmovz   rax, rbx
0x180016ff1  mov     rbx, [rax]
0x180016ff4  cmp     byte ptr [rbx+19h], 0
0x180016ff8  jz      short loc_180016FCC
0x180016ffa  cmp     byte ptr [rdi+19h], 0
0x180016ffe  jnz     short loc_18001701B
0x180017000  lea     rdx, [rdi+20h]; Buf2
0x180017004  mov     r8d, 10h; Size
0x18001700a  mov     rcx, rbp; Buf1
0x18001700d  call    memcmp_0
0x180017012  test    eax, eax
0x180017014  js      short loc_18001701B
0x180017016  cmp     rdi, r14
0x180017019  jnz     short loc_18001701E
0x18001701b  xor     sil, sil
0x18001701e  mov     al, sil
0x180017021  add     rsp, 40h
0x180017025  pop     r14
0x180017027  pop     rdi
0x180017028  pop     rsi
0x180017029  pop     rbp
0x18001702a  pop     rbx
0x18001702b  retn
0x18001702c  mov     cl, sil
0x18001702f  jmp     short loc_180016FE7
0x180017031  xor     al, al
0x180017033  jmp     short loc_180017021
0x180017035  mov     rcx, [rsp+68h]; this
0x18001703a  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x180017041  mov     edx, 69h ; 'i'; void *
0x180017046  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
