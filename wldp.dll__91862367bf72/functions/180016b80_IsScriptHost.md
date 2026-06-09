# IsScriptHost

- ea: `0x180016b80`
- end: `0x180016c60`
- name: `IsScriptHost`
- size: `224`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800201f4`

## callees

- `0x180016b80`
- `0x1800229ec`
- `0x18002e5d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016ba2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016ba2`

## string_xrefs

- `0x180016c4e`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
char __fastcall IsScriptHost(void *Buf1)
{
  const char *v2; // r9
  char v3; // di
  _BYTE *v4; // rbp
  _BYTE *v5; // rbx
  _BYTE *v6; // rsi
  char v7; // cl
  _BYTE *v8; // rax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !InitOnceExecuteOnce(&InitOnce, (PINIT_ONCE_FN)ConstructHostList, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
      v2);
  v3 = 1;
  v4 = *(_BYTE **)qword_18005B060;
  v5 = *(_BYTE **)qword_18005B060;
  v6 = *(_BYTE **)(*(_QWORD *)qword_18005B060 + 8LL);
  if ( !v6[25] )
  {
    do
    {
      if ( memcmp_0(v6 + 32, Buf1, 0x10u) < 0 )
      {
        v7 = 1;
      }
      else
      {
        v7 = 0;
        v5 = v6;
      }
      v8 = v6 + 16;
      if ( !v7 )
        v8 = v6;
      v6 = *(_BYTE **)v8;
    }
    while ( !*(_BYTE *)(*(_QWORD *)v8 + 25LL) );
  }
  if ( v5[25] || memcmp_0(Buf1, v5 + 32, 0x10u) < 0 )
    v5 = v4;
  if ( v5 == v4 || !v5[48] )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x180016b80  push    rbx
0x180016b82  push    rbp
0x180016b83  push    rsi
0x180016b84  push    rdi
0x180016b85  push    r14
0x180016b87  sub     rsp, 40h
0x180016b8b  mov     r14, rcx
0x180016b8e  lea     rdx, ConstructHostList; InitFn
0x180016b95  lea     rcx, InitOnce; InitOnce
0x180016b9c  xor     r9d, r9d; Context
0x180016b9f  xor     r8d, r8d; Parameter
0x180016ba2  call    cs:__imp_InitOnceExecuteOnce
0x180016ba8  test    eax, eax
0x180016baa  jz      loc_180016C49
0x180016bb0  mov     rax, cs:qword_18005B060
0x180016bb7  mov     dil, 1
0x180016bba  mov     rbp, [rax]
0x180016bbd  xor     eax, eax
0x180016bbf  mov     [rsp+68h+var_3C], eax
0x180016bc3  mov     rbx, rbp
0x180016bc6  mov     rsi, [rbp+8]
0x180016bca  cmp     [rsi+19h], al
0x180016bcd  jnz     short loc_180016BFD
0x180016bcf  lea     rcx, [rsi+20h]; Buf1
0x180016bd3  mov     r8d, 10h; Size
0x180016bd9  mov     rdx, r14; Buf2
0x180016bdc  call    memcmp_0
0x180016be1  test    eax, eax
0x180016be3  js      short loc_180016C38
0x180016be5  xor     cl, cl
0x180016be7  mov     rbx, rsi
0x180016bea  test    cl, cl
0x180016bec  lea     rax, [rsi+10h]
0x180016bf0  cmovz   rax, rsi
0x180016bf4  mov     rsi, [rax]
0x180016bf7  cmp     byte ptr [rsi+19h], 0
0x180016bfb  jz      short loc_180016BCF
0x180016bfd  cmp     byte ptr [rbx+19h], 0
0x180016c01  jnz     short loc_180016C45
0x180016c03  lea     rdx, [rbx+20h]; Buf2
0x180016c07  mov     r8d, 10h; Size
0x180016c0d  mov     rcx, r14; Buf1
0x180016c10  call    memcmp_0
0x180016c15  test    eax, eax
0x180016c17  js      short loc_180016C45
0x180016c19  mov     al, dil
0x180016c1c  test    al, al
0x180016c1e  cmovz   rbx, rbp
0x180016c22  cmp     rbx, rbp
0x180016c25  jnz     short loc_180016C3D
0x180016c27  xor     dil, dil
0x180016c2a  mov     al, dil
0x180016c2d  add     rsp, 40h
0x180016c31  pop     r14
0x180016c33  pop     rdi
0x180016c34  pop     rsi
0x180016c35  pop     rbp
0x180016c36  pop     rbx
0x180016c37  retn
0x180016c38  mov     cl, dil
0x180016c3b  jmp     short loc_180016BEA
0x180016c3d  cmp     byte ptr [rbx+30h], 0
0x180016c41  jnz     short loc_180016C2A
0x180016c43  jmp     short loc_180016C27
0x180016c45  xor     al, al
0x180016c47  jmp     short loc_180016C1C
0x180016c49  mov     rcx, [rsp+68h]; this
0x180016c4e  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x180016c55  mov     edx, 88h; void *
0x180016c5a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
