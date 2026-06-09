# AddEnumToGuidList

- ea: `0x1400392c4`
- end: `0x14003949e`
- name: `AddEnumToGuidList`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400396d0`

## callees

- `0x140002bf0`
- `0x1400392c4`
- `0x1400400be`
- `0x1400400d6`
- `0x1400400ee`

## import_xrefs

- `msvcrt!free` at `0x1400393b2`
- `msvcrt!free` at `0x140039472`
- `msvcrt!free` at `0x1400393b2`
- `msvcrt!free` at `0x140039472`
- `msvcrt!strncpy_s` at `0x140039402`
- `msvcrt!strncpy_s` at `0x140039402`
- `msvcrt!malloc` at `0x140039354`
- `msvcrt!malloc` at `0x1400393ce`
- `msvcrt!malloc` at `0x140039426`
- `msvcrt!malloc` at `0x140039354`
- `msvcrt!malloc` at `0x1400393ce`
- `msvcrt!malloc` at `0x140039426`
- `msvcrt!fprintf` at `0x140039374`
- `msvcrt!fprintf` at `0x140039374`

## string_xrefs

- `0x14003943c`: `WPPFMT : error : Failed to add Enumeration entry : Memory allocation failed for Guid Enumeration Link.\n`

## pseudocode

```c
void __fastcall AddEnumToGuidList(__int64 a1, const char *a2, unsigned int a3)
{
  rsize_t v3; // rbp
  __int64 v6; // rsi
  unsigned __int16 v7; // di
  _QWORD *v8; // r14
  const char *v9; // r15
  __int64 v10; // rdi
  __int64 v11; // r15
  char *v12; // rax
  void *v13; // r12
  FILE *v14; // rax
  char *v15; // rax
  FILE *v16; // rax
  __int16 v17; // ax
  __int64 v18; // rbp
  char *v19; // rdi
  FILE *v20; // rax

  if ( a1 )
  {
    v3 = a3;
    if ( a3 <= 0x408 )
    {
      v6 = NextFreeEnum;
      v7 = 0;
      v8 = EnumHead;
      if ( NextFreeEnum )
      {
        while ( 1 )
        {
          v9 = (const char *)v8[3 * v7];
          if ( !strncmp_0(v9, a2, (unsigned int)v3) && !v9[v3] )
            break;
          if ( ++v7 >= (unsigned __int16)v6 )
            goto LABEL_7;
        }
        LODWORD(v6) = v7;
      }
      else
      {
LABEL_7:
        v10 = EnumCount;
        if ( (_WORD)v6 == EnumCount )
        {
          v11 = (unsigned __int16)(EnumCount + 16);
          v12 = (char *)malloc(24 * v11);
          v13 = v12;
          if ( !v12 )
          {
            v14 = _acrt_iob_func(2u);
            fprintf(
              v14,
              "WPPFMT : error : Failed to add Enumeration entry : Memory allocation failed for Enumeration entries.\n");
            return;
          }
          memset_0(&v12[24 * v6], 0, 0x180u);
          memcpy_0(v13, v8, 24 * v10);
          free(v8);
          EnumCount = v11;
          v8 = v13;
          EnumHead = v13;
        }
        v15 = (char *)malloc(v3 + 1);
        v8[3 * v6] = v15;
        if ( !v15 )
        {
          v16 = _acrt_iob_func(2u);
          fprintf(
            v16,
            "WPPFMT : error : Failed to add Enumeration entry : Memory allocation failed for Enumeration name.\n");
          return;
        }
        strncpy_s(v15, v3 + 1, a2, v3);
        ++NextFreeEnum;
      }
      v17 = *(_WORD *)(a1 + 8);
      if ( *(_WORD *)(a1 + 10) == v17 )
      {
        v18 = (unsigned __int16)(v17 + 16);
        v19 = (char *)malloc(4 * v18);
        if ( !v19 )
        {
          v20 = _acrt_iob_func(2u);
          fprintf(
            v20,
            "WPPFMT : error : Failed to add Enumeration entry : Memory allocation failed for Guid Enumeration Link.\n");
          return;
        }
        memset_0(&v19[4 * *(unsigned __int16 *)(a1 + 10)], 0, 0x40u);
        memcpy_0(v19, *(const void **)a1, 4LL * *(unsigned __int16 *)(a1 + 8));
        free(*(void **)a1);
        *(_QWORD *)a1 = v19;
        *(_WORD *)(a1 + 8) = v18;
      }
      *(_DWORD *)(*(_QWORD *)a1 + 4LL * (unsigned __int16)(*(_WORD *)(a1 + 10))++) = v6;
    }
  }
}

```

## disassembly

```asm
0x1400392c4  test    rcx, rcx
0x1400392c7  jz      locret_14003949D
0x1400392cd  push    rbx
0x1400392ce  push    rbp
0x1400392cf  push    rsi
0x1400392d0  push    rdi
0x1400392d1  push    r12
0x1400392d3  push    r13
0x1400392d5  push    r14
0x1400392d7  push    r15
0x1400392d9  sub     rsp, 28h
0x1400392dd  mov     ebp, r8d
0x1400392e0  mov     r13, rdx
0x1400392e3  mov     rbx, rcx
0x1400392e6  cmp     ebp, 408h
0x1400392ec  ja      loc_14003948D
0x1400392f2  movzx   esi, cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x1400392f9  xor     edi, edi
0x1400392fb  mov     r14, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x140039302  xor     eax, eax
0x140039304  cmp     ax, si
0x140039307  jnb     short loc_140039335
0x140039309  movzx   eax, di
0x14003930c  mov     r8d, ebp; MaxCount
0x14003930f  mov     rdx, r13; Str2
0x140039312  lea     rcx, [rax+rax*2]
0x140039316  mov     r15, [r14+rcx*8]
0x14003931a  mov     rcx, r15; Str1
0x14003931d  call    strncmp_0
0x140039322  test    eax, eax
0x140039324  jnz     short loc_14003932D
0x140039326  cmp     [rbp+r15+0], al
0x14003932b  jz      short loc_14003937F
0x14003932d  inc     di
0x140039330  cmp     di, si
0x140039333  jb      short loc_140039309
0x140039335  movzx   edi, cs:?EnumCount@@3GA; ushort EnumCount
0x14003933c  cmp     si, di
0x14003933f  jnz     loc_1400393CA
0x140039345  lea     eax, [rdi+10h]
0x140039348  movzx   r15d, ax
0x14003934c  lea     rcx, [r15+r15*2]
0x140039350  shl     rcx, 3; Size
0x140039354  call    cs:__imp_malloc
0x14003935a  mov     r12, rax
0x14003935d  test    rax, rax
0x140039360  jnz     short loc_140039387
0x140039362  lea     ecx, [rax+2]; Ix
0x140039365  call    __acrt_iob_func
0x14003936a  lea     rdx, aWppfmtErrorFai_0; "WPPFMT : error : Failed to add Enumerat"...
0x140039371  mov     rcx, rax; Stream
0x140039374  call    cs:__imp_fprintf
0x14003937a  jmp     loc_14003948D
0x14003937f  movzx   esi, di
0x140039382  jmp     loc_14003940F
0x140039387  lea     rdx, [rsi+rsi*2]
0x14003938b  mov     r8d, 180h; Size
0x140039391  lea     rcx, [rax+rdx*8]; void *
0x140039395  xor     edx, edx; Val
0x140039397  call    memset_0
0x14003939c  lea     r8, [rdi+rdi*2]
0x1400393a0  mov     rdx, r14; Src
0x1400393a3  shl     r8, 3; Size
0x1400393a7  mov     rcx, r12; void *
0x1400393aa  call    memcpy_0
0x1400393af  mov     rcx, r14; Block
0x1400393b2  call    cs:__imp_free
0x1400393b8  mov     cs:?EnumCount@@3GA, r15w; ushort EnumCount
0x1400393c0  mov     r14, r12
0x1400393c3  mov     cs:?EnumHead@@3PEAUENUMDATA@@EA, r12; ENUMDATA * EnumHead
0x1400393ca  lea     rcx, [rbp+1]; Size
0x1400393ce  call    cs:__imp_malloc
0x1400393d4  lea     rdx, [rsi+rsi*2]
0x1400393d8  mov     [r14+rdx*8], rax
0x1400393dc  test    rax, rax
0x1400393df  jnz     short loc_1400393F5
0x1400393e1  lea     ecx, [rax+2]; Ix
0x1400393e4  call    __acrt_iob_func
0x1400393e9  lea     rdx, aWppfmtErrorFai_5; "WPPFMT : error : Failed to add Enumerat"...
0x1400393f0  jmp     loc_140039371
0x1400393f5  mov     r9, rbp; MaxCount
0x1400393f8  lea     rdx, [rbp+1]; SizeInBytes
0x1400393fc  mov     r8, r13; Source
0x1400393ff  mov     rcx, rax; Destination
0x140039402  call    cs:__imp_strncpy_s
0x140039408  inc     cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x14003940f  movzx   eax, word ptr [rbx+8]
0x140039413  cmp     [rbx+0Ah], ax
0x140039417  jnz     short loc_14003947F
0x140039419  add     ax, 10h
0x14003941d  movzx   ebp, ax
0x140039420  mov     ecx, ebp
0x140039422  shl     rcx, 2; Size
0x140039426  call    cs:__imp_malloc
0x14003942c  mov     rdi, rax
0x14003942f  test    rax, rax
0x140039432  jnz     short loc_140039448
0x140039434  lea     ecx, [rax+2]; Ix
0x140039437  call    __acrt_iob_func
0x14003943c  lea     rdx, aWppfmtErrorFai_1; "WPPFMT : error : Failed to add Enumerat"...
0x140039443  jmp     loc_140039371
0x140039448  movzx   eax, word ptr [rbx+0Ah]
0x14003944c  xor     edx, edx; Val
0x14003944e  lea     rcx, [rdi+rax*4]; void *
0x140039452  lea     r8d, [rdx+40h]; Size
0x140039456  call    memset_0
0x14003945b  movzx   r8d, word ptr [rbx+8]
0x140039460  mov     rcx, rdi; void *
0x140039463  mov     rdx, [rbx]; Src
0x140039466  shl     r8, 2; Size
0x14003946a  call    memcpy_0
0x14003946f  mov     rcx, [rbx]; Block
0x140039472  call    cs:__imp_free
0x140039478  mov     [rbx], rdi
0x14003947b  mov     [rbx+8], bp
0x14003947f  movzx   ecx, word ptr [rbx+0Ah]
0x140039483  mov     rax, [rbx]
0x140039486  mov     [rax+rcx*4], esi
0x140039489  inc     word ptr [rbx+0Ah]
0x14003948d  add     rsp, 28h
0x140039491  pop     r15
0x140039493  pop     r14
0x140039495  pop     r13
0x140039497  pop     r12
0x140039499  pop     rdi
0x14003949a  pop     rsi
0x14003949b  pop     rbp
0x14003949c  pop     rbx
0x14003949d  retn
```
