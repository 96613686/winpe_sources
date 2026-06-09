# create_environment_char_

- ea: `0x10041a87c`
- end: `0x10041a98b`
- name: `create_environment_char_`
- size: `271`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10041a800`

## callees

- `0x10041a87c`
- `0x10041a994`
- `0x10041b13c`
- `0x10041c06c`
- `0x10041c1d0`
- `0x10041c24c`

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
0x10041a87c  mov     rax, rsp
0x10041a87f  mov     [rax+8], rbx
0x10041a883  mov     [rax+10h], rbp
0x10041a887  mov     [rax+18h], rsi
0x10041a88b  mov     [rax+20h], rdi
0x10041a88f  push    r14
0x10041a891  sub     rsp, 30h
0x10041a895  mov     rsi, rcx
0x10041a898  xor     ecx, ecx
0x10041a89a  mov     r8, rsi
0x10041a89d  mov     dl, [rsi]
0x10041a89f  jmp     short loc_10041A8C6
0x10041a8a1  cmp     dl, 3Dh ; '='
0x10041a8a4  lea     rax, [rcx+1]
0x10041a8a8  cmovz   rax, rcx
0x10041a8ac  mov     rcx, rax
0x10041a8af  or      rax, 0FFFFFFFFFFFFFFFFh
0x10041a8b3  inc     rax
0x10041a8b6  cmp     byte ptr [r8+rax], 0
0x10041a8bb  jnz     short loc_10041A8B3
0x10041a8bd  inc     r8
0x10041a8c0  add     r8, rax
0x10041a8c3  mov     dl, [r8]
0x10041a8c6  test    dl, dl
0x10041a8c8  jnz     short loc_10041A8A1
0x10041a8ca  inc     rcx; Count
0x10041a8cd  mov     edx, 8; Size
0x10041a8d2  call    _calloc_base
0x10041a8d7  mov     rbx, rax
0x10041a8da  test    rax, rax
0x10041a8dd  jnz     short loc_10041A8EA
0x10041a8df  xor     ecx, ecx; Block
0x10041a8e1  call    _free_base
0x10041a8e6  xor     eax, eax
0x10041a8e8  jmp     short loc_10041A95C
0x10041a8ea  mov     r14, rbx
0x10041a8ed  mov     al, [rsi]
0x10041a8ef  test    al, al
0x10041a8f1  jz      short loc_10041A952
0x10041a8f3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x10041a8f7  inc     rbp
0x10041a8fa  cmp     byte ptr [rsi+rbp], 0
0x10041a8fe  jnz     short loc_10041A8F7
0x10041a900  inc     rbp
0x10041a903  cmp     al, 3Dh ; '='
0x10041a905  jz      short loc_10041A93C
0x10041a907  mov     edx, 1; Size
0x10041a90c  mov     rcx, rbp; Count
0x10041a90f  call    _calloc_base
0x10041a914  mov     rdi, rax
0x10041a917  test    rax, rax
0x10041a91a  jz      short loc_10041A941
0x10041a91c  mov     r8, rsi; Source
0x10041a91f  mov     rdx, rbp; SizeInBytes
0x10041a922  mov     rcx, rax; Destination
0x10041a925  call    strcpy_s
0x10041a92a  xor     ecx, ecx; Expression
0x10041a92c  test    eax, eax
0x10041a92e  jnz     short loc_10041A977
0x10041a930  mov     [r14], rdi
0x10041a933  add     r14, 8
0x10041a937  call    _free_base
0x10041a93c  add     rsi, rbp
0x10041a93f  jmp     short loc_10041A8ED
0x10041a941  mov     rcx, rbx; Block
0x10041a944  call    free_environment_wchar_t_
0x10041a949  xor     ecx, ecx; Block
0x10041a94b  call    _free_base
0x10041a950  jmp     short loc_10041A8DF
0x10041a952  xor     ecx, ecx; Block
0x10041a954  call    _free_base
0x10041a959  mov     rax, rbx
0x10041a95c  mov     rbx, [rsp+38h+arg_0]
0x10041a961  mov     rbp, [rsp+38h+arg_8]
0x10041a966  mov     rsi, [rsp+38h+arg_10]
0x10041a96b  mov     rdi, [rsp+38h+arg_18]
0x10041a970  add     rsp, 30h
0x10041a974  pop     r14
0x10041a976  retn
0x10041a977  and     [rsp+38h+var_18], 0
0x10041a97d  xor     r9d, r9d; LineNo
0x10041a980  xor     r8d, r8d; FileName
0x10041a983  xor     edx, edx; FunctionName
0x10041a985  call    _invoke_watson
```
