# cset_auto_compress

- ea: `0x140003f80`
- end: `0x14000414e`
- name: `cset_auto_compress`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001f9c`

## callees

- `0x140003f00`
- `0x140003f80`
- `0x140004160`
- `0x1400041b0`
- `0x1400071a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x140003f93`
- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x140003f93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000409a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400040bb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400040ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140004115`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000409a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400040bb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400040ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140004115`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400040d8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400040d8`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140004042`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140004042`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140004078`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140004078`

## pseudocode

```c
__int64 __fastcall cset_auto_compress(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  char *v4; // rsi
  void **v5; // r15
  const char *v6; // rcx
  int v7; // ebp
  __int64 suffix_code; // rax
  __int64 v9; // rax
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  _BYTE *v14; // rcx
  __int64 v15; // rdx
  char v16; // al
  char *v17; // rax
  char *v18; // rdi
  unsigned int i; // edi
  char *v20; // rax
  char *v21; // rdi
  int v22; // r9d
  int j; // r10d
  __int64 v24; // r8
  __int64 v25; // rdx
  _OWORD *v26; // rcx
  __int64 result; // rax

  v3 = _o__strdup(a2);
  v4 = (char *)v3;
  if ( !v3 )
    goto LABEL_28;
  v5 = *(void ***)(a1 + 8);
  v6 = (const char *)v3;
  v7 = *(_DWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  while ( 1 )
  {
    v17 = strrchr(v6, 46);
    v18 = v17;
    if ( !v17 )
      break;
    suffix_code = get_suffix_code(off_140009770, v17);
    if ( suffix_code )
    {
      cset_add_filter(a1, 0, suffix_code);
      *v18 = 0;
    }
    else
    {
      v9 = get_suffix_code(off_140009900, v18);
      if ( v9 )
      {
        cset_set_format(a1, v9);
        break;
      }
      v10 = get_suffix_code(off_140009840, v18);
      if ( !v10 )
        break;
      v11 = -1;
      *v18 = 0;
      v12 = -1;
      do
        ++v12;
      while ( v4[v12] );
      do
        ++v11;
      while ( *(_BYTE *)(v10 + v11) );
      v13 = _o_realloc(v4, v11 + v12 + 1);
      v4 = (char *)v13;
      if ( !v13 )
        goto LABEL_28;
      v14 = (_BYTE *)(v13 - 1);
      do
        ++v14;
      while ( *v14 );
      v15 = 0;
      do
      {
        v16 = *(_BYTE *)(v10 + v15);
        v14[v15++] = v16;
      }
      while ( v16 );
    }
    v6 = v4;
  }
  free(v4);
  if ( !*(_QWORD *)(a1 + 8) )
  {
    *(_QWORD *)(a1 + 8) = v5;
    result = 0;
    *(_DWORD *)(a1 + 16) = v7;
    return result;
  }
  for ( i = 0; (int)i < v7; ++i )
    free(v5[2 * i + 1]);
  free(v5);
  v20 = (char *)malloc(16LL * *(int *)(a1 + 16));
  v21 = v20;
  if ( !v20 )
LABEL_28:
    lafe_errc(1);
  v22 = *(_DWORD *)(a1 + 16);
  for ( j = 0; ; ++j )
  {
    v26 = *(_OWORD **)(a1 + 8);
    if ( v22 <= 0 )
      break;
    v24 = (unsigned int)v22--;
    v25 = 2LL * j;
    *(_OWORD *)&v20[8 * v25] = v26[v24 - 1];
  }
  free(v26);
  result = 1;
  *(_QWORD *)(a1 + 8) = v21;
  return result;
}

```

## disassembly

```asm
0x140003f80  push    rbx
0x140003f82  push    rbp
0x140003f83  push    rsi
0x140003f84  push    rdi
0x140003f85  push    r14
0x140003f87  push    r15
0x140003f89  sub     rsp, 28h
0x140003f8d  mov     rbx, rcx
0x140003f90  mov     rcx, rdx
0x140003f93  call    cs:__imp__o__strdup
0x140003f99  mov     rsi, rax
0x140003f9c  test    rax, rax
0x140003f9f  jz      loc_14000413C
0x140003fa5  mov     r15, [rbx+8]
0x140003fa9  mov     rcx, rax
0x140003fac  mov     ebp, [rbx+10h]
0x140003faf  mov     qword ptr [rbx+8], 0
0x140003fb7  mov     dword ptr [rbx+10h], 0
0x140003fbe  jmp     loc_140004073
0x140003fc3  mov     rdx, rdi
0x140003fc6  lea     rcx, off_140009770; ".Z"
0x140003fcd  call    get_suffix_code
0x140003fd2  test    rax, rax
0x140003fd5  jz      short loc_140003FEC
0x140003fd7  mov     r8, rax
0x140003fda  xor     edx, edx
0x140003fdc  mov     rcx, rbx
0x140003fdf  call    _cset_add_filter
0x140003fe4  mov     byte ptr [rdi], 0
0x140003fe7  jmp     loc_140004070
0x140003fec  mov     rdx, rdi
0x140003fef  lea     rcx, off_140009900; ".7z"
0x140003ff6  call    get_suffix_code
0x140003ffb  test    rax, rax
0x140003ffe  jnz     loc_14000408C
0x140004004  mov     rdx, rdi
0x140004007  lea     rcx, off_140009840; ".taz"
0x14000400e  call    get_suffix_code
0x140004013  mov     r14, rax
0x140004016  test    rax, rax
0x140004019  jz      short loc_140004097
0x14000401b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000401f  mov     byte ptr [rdi], 0
0x140004022  mov     rcx, rax
0x140004025  inc     rcx
0x140004028  cmp     byte ptr [rsi+rcx], 0
0x14000402c  jnz     short loc_140004025
0x14000402e  inc     rax
0x140004031  cmp     byte ptr [r14+rax], 0
0x140004036  jnz     short loc_14000402E
0x140004038  lea     rdx, [rcx+1]
0x14000403c  mov     rcx, rsi
0x14000403f  add     rdx, rax
0x140004042  call    cs:__imp__o_realloc
0x140004048  mov     rsi, rax
0x14000404b  test    rax, rax
0x14000404e  jz      loc_14000413C
0x140004054  lea     rcx, [rax-1]
0x140004058  inc     rcx
0x14000405b  cmp     byte ptr [rcx], 0
0x14000405e  jnz     short loc_140004058
0x140004060  xor     edx, edx
0x140004062  mov     al, [r14+rdx]
0x140004066  mov     [rcx+rdx], al
0x140004069  inc     rdx
0x14000406c  test    al, al
0x14000406e  jnz     short loc_140004062
0x140004070  mov     rcx, rsi; Str
0x140004073  mov     edx, 2Eh ; '.'; Ch
0x140004078  call    cs:__imp_strrchr
0x14000407e  mov     rdi, rax
0x140004081  test    rax, rax
0x140004084  jnz     loc_140003FC3
0x14000408a  jmp     short loc_140004097
0x14000408c  mov     rdx, rax
0x14000408f  mov     rcx, rbx
0x140004092  call    cset_set_format
0x140004097  mov     rcx, rsi; Block
0x14000409a  call    cs:__imp_free
0x1400040a0  cmp     qword ptr [rbx+8], 0
0x1400040a5  jz      loc_140004131
0x1400040ab  xor     edi, edi
0x1400040ad  test    ebp, ebp
0x1400040af  jle     short loc_1400040C7
0x1400040b1  mov     ecx, edi
0x1400040b3  add     rcx, rcx
0x1400040b6  mov     rcx, [r15+rcx*8+8]; Block
0x1400040bb  call    cs:__imp_free
0x1400040c1  inc     edi
0x1400040c3  cmp     edi, ebp
0x1400040c5  jl      short loc_1400040B1
0x1400040c7  mov     rcx, r15; Block
0x1400040ca  call    cs:__imp_free
0x1400040d0  movsxd  rcx, dword ptr [rbx+10h]
0x1400040d4  shl     rcx, 4; Size
0x1400040d8  call    cs:__imp_malloc
0x1400040de  mov     rdi, rax
0x1400040e1  test    rax, rax
0x1400040e4  jz      short loc_14000413C
0x1400040e6  mov     r9d, [rbx+10h]
0x1400040ea  xor     r10d, r10d
0x1400040ed  jmp     short loc_14000410C
0x1400040ef  mov     r8d, r9d
0x1400040f2  dec     r9d
0x1400040f5  add     r8, r8
0x1400040f8  movsxd  rdx, r10d
0x1400040fb  add     rdx, rdx
0x1400040fe  inc     r10d
0x140004101  movups  xmm0, xmmword ptr [rcx+r8*8-10h]
0x140004107  movdqu  xmmword ptr [rax+rdx*8], xmm0
0x14000410c  mov     rcx, [rbx+8]; Block
0x140004110  test    r9d, r9d
0x140004113  jg      short loc_1400040EF
0x140004115  call    cs:__imp_free
0x14000411b  mov     eax, 1
0x140004120  mov     [rbx+8], rdi
0x140004124  add     rsp, 28h
0x140004128  pop     r15
0x14000412a  pop     r14
0x14000412c  pop     rdi
0x14000412d  pop     rsi
0x14000412e  pop     rbp
0x14000412f  pop     rbx
0x140004130  retn
0x140004131  mov     [rbx+8], r15
0x140004135  xor     eax, eax
0x140004137  mov     [rbx+10h], ebp
0x14000413a  jmp     short loc_140004124
0x14000413c  xor     edx, edx
0x14000413e  lea     r8, aNoMemory; "No memory"
0x140004145  lea     ecx, [rdx+1]; Code
0x140004148  call    lafe_errc
```
