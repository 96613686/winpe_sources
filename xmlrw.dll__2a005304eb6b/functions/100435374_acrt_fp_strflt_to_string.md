# __acrt_fp_strflt_to_string

- ea: `0x100435374`
- end: `0x100435484`
- name: `__acrt_fp_strflt_to_string`
- size: `272`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, int, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x100431de4`
- `0x1004320d0`
- `0x100432308`

## callees

- `0x100425d50`
- `0x10042e504`
- `0x10043529c`
- `0x100435374`

## pseudocode

```c
__int64 __fastcall _acrt_fp_strflt_to_string(
        char *a1,
        unsigned __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __crt_cached_ptd_host *a7)
{
  unsigned int v9; // ebx
  int v11; // eax
  char *v12; // rcx
  char *v13; // rbx
  char *v14; // rdx
  char v15; // al
  __int64 v16; // r8

  if ( !a1 || !a2 )
    goto LABEL_2;
  v11 = 0;
  *a1 = 0;
  if ( a3 > 0 )
    v11 = a3;
  if ( a2 <= v11 + 1 )
  {
    v9 = 34;
    goto LABEL_3;
  }
  if ( !a4 )
  {
LABEL_2:
    v9 = 22;
LABEL_3:
    *((_DWORD *)a7 + 11) = v9;
    *((_BYTE *)a7 + 48) = 1;
    invalid_parameter_internal(0, 0, 0, 0, 0, a7);
    return v9;
  }
  v12 = *(char **)(a4 + 8);
  v13 = a1 + 1;
  v14 = v12;
  *a1 = 48;
  while ( a3 > 0 )
  {
    v15 = *v14;
    if ( *v14 )
      ++v14;
    else
      v15 = 48;
    *v13++ = v15;
    --a3;
  }
  *v13 = 0;
  if ( a3 >= 0 && (unsigned __int8)should_round_up_0((_DWORD)v12, (_DWORD)v14, *(_DWORD *)a4, a5, a6) )
  {
    while ( *--v13 == 57 )
      *v13 = 48;
    ++*v13;
  }
  if ( *a1 == 49 )
  {
    ++*(_DWORD *)(a4 + 4);
  }
  else
  {
    v16 = -1;
    do
      ++v16;
    while ( a1[v16 + 1] );
    memmove(a1, a1 + 1, v16 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x100435374  mov     [rsp+arg_0], rbx
0x100435379  mov     [rsp+arg_8], rbp
0x10043537e  mov     [rsp+arg_10], rsi
0x100435383  push    rdi
0x100435384  sub     rsp, 30h
0x100435388  mov     rdi, r9
0x10043538b  mov     rsi, rcx
0x10043538e  test    rcx, rcx
0x100435391  jnz     short loc_1004353C5
0x100435393  mov     ebx, 16h
0x100435398  mov     rax, [rsp+38h+arg_30]
0x10043539d  xor     r9d, r9d; LineNo
0x1004353a0  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x1004353a5  xor     r8d, r8d; FileName
0x1004353a8  and     [rsp+38h+var_18], 0
0x1004353ae  xor     edx, edx; FunctionName
0x1004353b0  xor     ecx, ecx; Expression
0x1004353b2  mov     [rax+2Ch], ebx
0x1004353b5  mov     byte ptr [rax+30h], 1
0x1004353b9  call    _invalid_parameter_internal
0x1004353be  mov     eax, ebx
0x1004353c0  jmp     loc_10043546F
0x1004353c5  test    rdx, rdx
0x1004353c8  jz      short loc_100435393
0x1004353ca  xor     eax, eax
0x1004353cc  mov     byte ptr [rcx], 0
0x1004353cf  test    r8d, r8d
0x1004353d2  cmovg   eax, r8d
0x1004353d6  inc     eax
0x1004353d8  cdqe
0x1004353da  cmp     rdx, rax
0x1004353dd  ja      short loc_1004353E6
0x1004353df  mov     ebx, 22h ; '"'
0x1004353e4  jmp     short loc_100435398
0x1004353e6  test    rdi, rdi
0x1004353e9  jz      short loc_100435393
0x1004353eb  mov     rcx, [r9+8]
0x1004353ef  lea     rbx, [rsi+1]
0x1004353f3  mov     rdx, rcx
0x1004353f6  mov     byte ptr [rsi], 30h ; '0'
0x1004353f9  jmp     short loc_100435410
0x1004353fb  mov     al, [rdx]
0x1004353fd  test    al, al
0x1004353ff  jz      short loc_100435406
0x100435401  inc     rdx
0x100435404  jmp     short loc_100435408
0x100435406  mov     al, 30h ; '0'
0x100435408  mov     [rbx], al
0x10043540a  inc     rbx
0x10043540d  dec     r8d
0x100435410  test    r8d, r8d
0x100435413  jg      short loc_1004353FB
0x100435415  mov     byte ptr [rbx], 0
0x100435418  js      short loc_100435445
0x10043541a  mov     eax, [rsp+38h+arg_28]
0x10043541e  mov     r9d, [rsp+38h+arg_20]
0x100435423  mov     r8d, [rdi]
0x100435426  mov     dword ptr [rsp+38h+var_18], eax
0x10043542a  call    should_round_up_0
0x10043542f  test    al, al
0x100435431  jz      short loc_100435445
0x100435433  jmp     short loc_100435438
0x100435435  mov     byte ptr [rbx], 30h ; '0'
0x100435438  dec     rbx
0x10043543b  mov     al, [rbx]
0x10043543d  cmp     al, 39h ; '9'
0x10043543f  jz      short loc_100435435
0x100435441  inc     al
0x100435443  mov     [rbx], al
0x100435445  cmp     byte ptr [rsi], 31h ; '1'
0x100435448  jnz     short loc_10043544F
0x10043544a  inc     dword ptr [rdi+4]
0x10043544d  jmp     short loc_10043546D
0x10043544f  or      r8, 0FFFFFFFFFFFFFFFFh
0x100435453  inc     r8
0x100435456  cmp     byte ptr [r8+rsi+1], 0
0x10043545c  jnz     short loc_100435453
0x10043545e  inc     r8; Size
0x100435461  lea     rdx, [rsi+1]; Src
0x100435465  mov     rcx, rsi; void *
0x100435468  call    memmove
0x10043546d  xor     eax, eax
0x10043546f  mov     rbx, [rsp+38h+arg_0]
0x100435474  mov     rbp, [rsp+38h+arg_8]
0x100435479  mov     rsi, [rsp+38h+arg_10]
0x10043547e  add     rsp, 30h
0x100435482  pop     rdi
0x100435483  retn
```
