# AddEnumToGuidList

- ea: `0x180047790`
- end: `0x18004795c`
- name: `AddEnumToGuidList`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180047bd0`

## callees

- `0x1800212ea`
- `0x18002143c`
- `0x180021490`
- `0x180021724`
- `0x180023b05`
- `0x180047790`
- `0x180049fc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047874`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047930`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047874`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047930`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004781f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180047890`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800478e4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004781f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180047890`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800478e4`

## string_xrefs

- `0x1800478fa`: `WPPFMT : error : Failed to add Enumeration entry : Memory allocation failed for Guid Enumeration Link.\n`

## pseudocode

```c
void __fastcall AddEnumToGuidList(__int64 a1, const char *a2, unsigned int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rsi
  unsigned __int16 v7; // di
  _QWORD *v8; // r14
  const char *v9; // r15
  __int64 v10; // rdi
  __int64 v11; // r15
  char *v12; // rax
  void *v13; // r12
  FILE *v14; // rax
  void *v15; // rax
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
      while ( v7 < (unsigned __int16)v6 )
      {
        v9 = (const char *)v8[3 * v7];
        if ( !strncmp_0(v9, a2, (unsigned int)v3) && !v9[v3] )
        {
          LODWORD(v6) = v7;
          goto LABEL_17;
        }
        ++v7;
      }
      v10 = EnumCount;
      if ( (_WORD)v6 == EnumCount )
      {
        v11 = (unsigned __int16)(EnumCount + 16);
        v12 = (char *)malloc(24 * v11);
        v13 = v12;
        if ( !v12 )
        {
          v14 = o___acrt_iob_func_0(2u);
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
      v15 = malloc(v3 + 1);
      v8[3 * v6] = v15;
      if ( !v15 )
      {
        v16 = o___acrt_iob_func_0(2u);
        fprintf(
          v16,
          "WPPFMT : error : Failed to add Enumeration entry : Memory allocation failed for Enumeration name.\n");
        return;
      }
      o_strncpy_s_0(v15, v3 + 1, a2, v3);
      ++NextFreeEnum;
LABEL_17:
      v17 = *(_WORD *)(a1 + 8);
      if ( *(_WORD *)(a1 + 10) == v17 )
      {
        v18 = (unsigned __int16)(v17 + 16);
        v19 = (char *)malloc(4 * v18);
        if ( !v19 )
        {
          v20 = o___acrt_iob_func_0(2u);
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
0x180047790  test    rcx, rcx
0x180047793  jz      locret_18004795B
0x180047799  push    rbx
0x18004779a  push    rbp
0x18004779b  push    rsi
0x18004779c  push    rdi
0x18004779d  push    r12
0x18004779f  push    r13
0x1800477a1  push    r14
0x1800477a3  push    r15
0x1800477a5  sub     rsp, 28h
0x1800477a9  mov     ebp, r8d
0x1800477ac  mov     r13, rdx
0x1800477af  mov     rbx, rcx
0x1800477b2  cmp     ebp, 408h
0x1800477b8  ja      loc_18004794B
0x1800477be  movzx   esi, cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x1800477c5  xor     edi, edi
0x1800477c7  mov     r14, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x1800477ce  cmp     di, si
0x1800477d1  jnb     short loc_180047804
0x1800477d3  movzx   eax, di
0x1800477d6  mov     r8d, ebp; MaxCount
0x1800477d9  mov     rdx, r13; Str2
0x1800477dc  lea     rcx, [rax+rax*2]
0x1800477e0  mov     r15, [r14+rcx*8]
0x1800477e4  mov     rcx, r15; Str1
0x1800477e7  call    strncmp_0
0x1800477ec  test    eax, eax
0x1800477ee  jnz     short loc_1800477F7
0x1800477f0  cmp     [rbp+r15+0], al
0x1800477f5  jz      short loc_1800477FC
0x1800477f7  inc     di
0x1800477fa  jmp     short loc_1800477CE
0x1800477fc  movzx   esi, di
0x1800477ff  jmp     loc_1800478CD
0x180047804  movzx   edi, cs:?EnumCount@@3GA; ushort EnumCount
0x18004780b  cmp     si, di
0x18004780e  jnz     short loc_18004788C
0x180047810  lea     eax, [rdi+10h]
0x180047813  movzx   r15d, ax
0x180047817  lea     rcx, [r15+r15*2]
0x18004781b  shl     rcx, 3; Size
0x18004781f  call    cs:__imp_malloc
0x180047825  mov     r12, rax
0x180047828  test    rax, rax
0x18004782b  jnz     short loc_180047849
0x18004782d  lea     ecx, [rax+2]; Ix
0x180047830  call    _o___acrt_iob_func_0
0x180047835  lea     rdx, aWppfmtErrorFai_0; "WPPFMT : error : Failed to add Enumerat"...
0x18004783c  mov     rcx, rax; Stream
0x18004783f  call    fprintf
0x180047844  jmp     loc_18004794B
0x180047849  lea     rdx, [rsi+rsi*2]
0x18004784d  mov     r8d, 180h; Size
0x180047853  lea     rcx, [rax+rdx*8]; void *
0x180047857  xor     edx, edx; Val
0x180047859  call    memset_0
0x18004785e  lea     r8, [rdi+rdi*2]
0x180047862  mov     rdx, r14; Src
0x180047865  shl     r8, 3; Size
0x180047869  mov     rcx, r12; void *
0x18004786c  call    memcpy_0
0x180047871  mov     rcx, r14; Block
0x180047874  call    cs:__imp_free
0x18004787a  mov     cs:?EnumCount@@3GA, r15w; ushort EnumCount
0x180047882  mov     r14, r12
0x180047885  mov     cs:?EnumHead@@3PEAUENUMDATA@@EA, r12; ENUMDATA * EnumHead
0x18004788c  lea     rcx, [rbp+1]; Size
0x180047890  call    cs:__imp_malloc
0x180047896  lea     rdx, [rsi+rsi*2]
0x18004789a  mov     [r14+rdx*8], rax
0x18004789e  test    rax, rax
0x1800478a1  jnz     short loc_1800478B4
0x1800478a3  lea     ecx, [rax+2]; Ix
0x1800478a6  call    _o___acrt_iob_func_0
0x1800478ab  lea     rdx, aWppfmtErrorFai_5; "WPPFMT : error : Failed to add Enumerat"...
0x1800478b2  jmp     short loc_18004783C
0x1800478b4  mov     r9, rbp
0x1800478b7  lea     rdx, [rbp+1]
0x1800478bb  mov     r8, r13
0x1800478be  mov     rcx, rax
0x1800478c1  call    _o_strncpy_s_0
0x1800478c6  inc     cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x1800478cd  movzx   eax, word ptr [rbx+8]
0x1800478d1  cmp     [rbx+0Ah], ax
0x1800478d5  jnz     short loc_18004793D
0x1800478d7  add     ax, 10h
0x1800478db  movzx   ebp, ax
0x1800478de  mov     ecx, ebp
0x1800478e0  shl     rcx, 2; Size
0x1800478e4  call    cs:__imp_malloc
0x1800478ea  mov     rdi, rax
0x1800478ed  test    rax, rax
0x1800478f0  jnz     short loc_180047906
0x1800478f2  lea     ecx, [rax+2]; Ix
0x1800478f5  call    _o___acrt_iob_func_0
0x1800478fa  lea     rdx, aWppfmtErrorFai_1; "WPPFMT : error : Failed to add Enumerat"...
0x180047901  jmp     loc_18004783C
0x180047906  movzx   eax, word ptr [rbx+0Ah]
0x18004790a  xor     edx, edx; Val
0x18004790c  lea     rcx, [rdi+rax*4]; void *
0x180047910  lea     r8d, [rdx+40h]; Size
0x180047914  call    memset_0
0x180047919  movzx   r8d, word ptr [rbx+8]
0x18004791e  mov     rcx, rdi; void *
0x180047921  mov     rdx, [rbx]; Src
0x180047924  shl     r8, 2; Size
0x180047928  call    memcpy_0
0x18004792d  mov     rcx, [rbx]; Block
0x180047930  call    cs:__imp_free
0x180047936  mov     [rbx], rdi
0x180047939  mov     [rbx+8], bp
0x18004793d  movzx   ecx, word ptr [rbx+0Ah]
0x180047941  mov     rax, [rbx]
0x180047944  mov     [rax+rcx*4], esi
0x180047947  inc     word ptr [rbx+0Ah]
0x18004794b  add     rsp, 28h
0x18004794f  pop     r15
0x180047951  pop     r14
0x180047953  pop     r13
0x180047955  pop     r12
0x180047957  pop     rdi
0x180047958  pop     rsi
0x180047959  pop     rbp
0x18004795a  pop     rbx
0x18004795b  retn
```
