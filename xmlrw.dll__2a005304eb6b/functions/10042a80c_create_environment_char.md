# create_environment_char_

- ea: `0x10042a80c`
- end: `0x10042a91b`
- name: `create_environment_char_`
- size: `271`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10042a790`

## callees

- `0x10042a80c`
- `0x10042a924`
- `0x10042b0cc`
- `0x10042e5fc`
- `0x10042e760`
- `0x10042e7dc`

## pseudocode

```c
void *__fastcall create_environment_char_(char *Source)
{
  __int64 v2; // rcx
  char *v3; // r8
  char i; // dl
  __int64 v5; // rax
  __int64 v6; // rax
  void *v7; // rax
  void *v8; // rbx
  char **v10; // r14
  __int64 v11; // rbp
  size_t v12; // rbp
  char *v13; // rax
  char *v14; // rdi

  v2 = 0;
  v3 = Source;
  for ( i = *Source; i; i = *v3 )
  {
    v5 = v2 + 1;
    if ( i == 61 )
      v5 = v2;
    v2 = v5;
    v6 = -1;
    do
      ++v6;
    while ( v3[v6] );
    v3 += v6 + 1;
  }
  v7 = calloc_base(v2 + 1, 8u);
  v8 = v7;
  if ( v7 )
  {
    v10 = (char **)v7;
    while ( *Source )
    {
      v11 = -1;
      do
        ++v11;
      while ( Source[v11] );
      v12 = v11 + 1;
      if ( *Source != 61 )
      {
        v13 = (char *)calloc_base(v12, 1u);
        v14 = v13;
        if ( !v13 )
        {
          free_environment_wchar_t_(v8);
          free_base(0);
          goto LABEL_9;
        }
        if ( strcpy_s(v13, v12, Source) )
          invoke_watson(0, 0, 0, 0, 0);
        *v10++ = v14;
        free_base(0);
      }
      Source += v12;
    }
    free_base(0);
    return v8;
  }
  else
  {
LABEL_9:
    free_base(0);
    return 0;
  }
}

```

## disassembly

```asm
0x10042a80c  mov     rax, rsp
0x10042a80f  mov     [rax+8], rbx
0x10042a813  mov     [rax+10h], rbp
0x10042a817  mov     [rax+18h], rsi
0x10042a81b  mov     [rax+20h], rdi
0x10042a81f  push    r14
0x10042a821  sub     rsp, 30h
0x10042a825  mov     rsi, rcx
0x10042a828  xor     ecx, ecx
0x10042a82a  mov     r8, rsi
0x10042a82d  mov     dl, [rsi]
0x10042a82f  jmp     short loc_10042A856
0x10042a831  cmp     dl, 3Dh ; '='
0x10042a834  lea     rax, [rcx+1]
0x10042a838  cmovz   rax, rcx
0x10042a83c  mov     rcx, rax
0x10042a83f  or      rax, 0FFFFFFFFFFFFFFFFh
0x10042a843  inc     rax
0x10042a846  cmp     byte ptr [r8+rax], 0
0x10042a84b  jnz     short loc_10042A843
0x10042a84d  inc     r8
0x10042a850  add     r8, rax
0x10042a853  mov     dl, [r8]
0x10042a856  test    dl, dl
0x10042a858  jnz     short loc_10042A831
0x10042a85a  inc     rcx; Count
0x10042a85d  mov     edx, 8; Size
0x10042a862  call    _calloc_base
0x10042a867  mov     rbx, rax
0x10042a86a  test    rax, rax
0x10042a86d  jnz     short loc_10042A87A
0x10042a86f  xor     ecx, ecx; Block
0x10042a871  call    _free_base
0x10042a876  xor     eax, eax
0x10042a878  jmp     short loc_10042A8EC
0x10042a87a  mov     r14, rbx
0x10042a87d  mov     al, [rsi]
0x10042a87f  test    al, al
0x10042a881  jz      short loc_10042A8E2
0x10042a883  or      rbp, 0FFFFFFFFFFFFFFFFh
0x10042a887  inc     rbp
0x10042a88a  cmp     byte ptr [rsi+rbp], 0
0x10042a88e  jnz     short loc_10042A887
0x10042a890  inc     rbp
0x10042a893  cmp     al, 3Dh ; '='
0x10042a895  jz      short loc_10042A8CC
0x10042a897  mov     edx, 1; Size
0x10042a89c  mov     rcx, rbp; Count
0x10042a89f  call    _calloc_base
0x10042a8a4  mov     rdi, rax
0x10042a8a7  test    rax, rax
0x10042a8aa  jz      short loc_10042A8D1
0x10042a8ac  mov     r8, rsi; Source
0x10042a8af  mov     rdx, rbp; SizeInBytes
0x10042a8b2  mov     rcx, rax; Destination
0x10042a8b5  call    strcpy_s
0x10042a8ba  xor     ecx, ecx; Expression
0x10042a8bc  test    eax, eax
0x10042a8be  jnz     short loc_10042A907
0x10042a8c0  mov     [r14], rdi
0x10042a8c3  add     r14, 8
0x10042a8c7  call    _free_base
0x10042a8cc  add     rsi, rbp
0x10042a8cf  jmp     short loc_10042A87D
0x10042a8d1  mov     rcx, rbx; Block
0x10042a8d4  call    free_environment_wchar_t_
0x10042a8d9  xor     ecx, ecx; Block
0x10042a8db  call    _free_base
0x10042a8e0  jmp     short loc_10042A86F
0x10042a8e2  xor     ecx, ecx; Block
0x10042a8e4  call    _free_base
0x10042a8e9  mov     rax, rbx
0x10042a8ec  mov     rbx, [rsp+38h+arg_0]
0x10042a8f1  mov     rbp, [rsp+38h+arg_8]
0x10042a8f6  mov     rsi, [rsp+38h+arg_10]
0x10042a8fb  mov     rdi, [rsp+38h+arg_18]
0x10042a900  add     rsp, 30h
0x10042a904  pop     r14
0x10042a906  retn
0x10042a907  and     [rsp+38h+var_18], 0
0x10042a90d  xor     r9d, r9d; LineNo
0x10042a910  xor     r8d, r8d; FileName
0x10042a913  xor     edx, edx; FunctionName
0x10042a915  call    _invoke_watson
```
