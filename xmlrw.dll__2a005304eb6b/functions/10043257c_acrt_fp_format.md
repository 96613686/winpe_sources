# __acrt_fp_format

- ea: `0x10043257c`
- end: `0x100432861`
- name: `__acrt_fp_format`
- size: `741`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char *Str@<rdx>, int@<r8d>, __int64, int, size_t, __int64, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x10042cfd4`

## callees

- `0x10042b0cc`
- `0x10042e504`
- `0x10042e5fc`
- `0x100431a44`
- `0x100431de4`
- `0x1004320d0`
- `0x100432308`
- `0x10043257c`

## pseudocode

```c
__int64 __fastcall _acrt_fp_format(
        __int64 *a1,
        char *Str,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        size_t a7,
        unsigned __int64 a8,
        int a9,
        __crt_cached_ptd_host *a10)
{
  rsize_t v10; // r11
  char *v11; // r10
  unsigned __int8 v13; // si
  __int64 v14; // rdx
  unsigned int v15; // r8d
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r8
  int v19; // edx
  int v20; // ebx
  size_t Size; // [rsp+28h] [rbp-30h]

  v10 = a3;
  v11 = Str;
  if ( !Str || !a3 || !a4 || !a5 )
  {
    *((_BYTE *)a10 + 48) = 1;
    *((_DWORD *)a10 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a10);
    return 22;
  }
  v13 = a6 == 65 || (unsigned int)(a6 - 69) <= 2;
  if ( (a8 & 8) != 0 || (v14 = *a1, (((unsigned __int64)*a1 >> 52) & 0x7FF) != 0x7FF) )
  {
    v19 = (a8 >> 4) & 1 | 2;
    v20 = (a8 & 0x20) != 0 ? a9 : 0;
    if ( a6 != 65 )
    {
      switch ( a6 )
      {
        case 'E':
          return fp_format_e((int)a1, (int)v11, a3, a4, a5, a7, v13, v19, v20, a10);
        case 'F':
          return fp_format_f(a1, v11, a3);
        case 'G':
          return fp_format_g(a1, v11, a3);
      }
      if ( a6 != 97 )
      {
        if ( a6 != 101 )
        {
          if ( a6 != 102 )
            return fp_format_g(a1, v11, a3);
          return fp_format_f(a1, v11, a3);
        }
        return fp_format_e((int)a1, (int)v11, a3, a4, a5, a7, v13, v19, v20, a10);
      }
    }
    LODWORD(Size) = a7;
    return fp_format_a(a1, v11, a3, a4, a5, Size, v13, v19, v20, a10);
  }
  v15 = 12;
  if ( (v14 & 0xFFFFFFFFFFFFFLL) != 0 )
  {
    if ( v14 < 0 && (v14 & 0xFFFFFFFFFFFFFLL) == 0x8000000000000LL )
      v16 = 12;
    else
      v16 = (-(__int64)((v14 & 0x8000000000000LL) != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 8;
  }
  else
  {
    v16 = 0;
  }
  v17 = (unsigned __int64)v14 >> 63;
  if ( v10 >= v17 + 4 )
  {
    v18 = -1;
    if ( (_BYTE)v17 )
    {
      *v11++ = 45;
      *v11 = 0;
      if ( v10 != -1 )
        --v10;
    }
    do
      ++v18;
    while ( (&off_10043EEB0[2 * (v13 ^ 1u)])[v16][v18] );
    if ( strcpy_s(v11, v10, (&(&off_10043EEB0[2 * (v13 ^ 1)])[v16])[v10 <= v18]) )
      invoke_watson(0, 0, 0, 0, 0);
    return 0;
  }
  else
  {
    *v11 = 0;
  }
  return v15;
}

```

## disassembly

```asm
0x10043257c  mov     [rsp+arg_0], rbx
0x100432581  mov     [rsp+arg_8], rsi
0x100432586  push    rdi
0x100432587  sub     rsp, 50h
0x10043258b  mov     r11, r8
0x10043258e  mov     r10, rdx
0x100432591  mov     rdi, rcx
0x100432594  test    rdx, rdx
0x100432597  jnz     short loc_1004325CC
0x100432599  mov     rcx, [rsp+58h+arg_48]
0x1004325a1  lea     ebx, [rdx+16h]
0x1004325a4  mov     [rsp+58h+Size], rcx; __crt_cached_ptd_host *
0x1004325a9  mov     byte ptr [rcx+30h], 1
0x1004325ad  mov     [rcx+2Ch], ebx
0x1004325b0  and     [rsp+58h+var_38], 0
0x1004325b6  xor     r9d, r9d; LineNo
0x1004325b9  xor     r8d, r8d; FileName
0x1004325bc  xor     edx, edx; FunctionName
0x1004325be  xor     ecx, ecx; Expression
0x1004325c0  call    _invalid_parameter_internal
0x1004325c5  mov     eax, ebx
0x1004325c7  jmp     loc_10043283B
0x1004325cc  test    r11, r11
0x1004325cf  jnz     short loc_1004325EC
0x1004325d1  mov     rax, [rsp+58h+arg_48]
0x1004325d9  mov     ebx, 16h
0x1004325de  mov     [rsp+58h+Size], rax
0x1004325e3  mov     byte ptr [rax+30h], 1
0x1004325e7  mov     [rax+2Ch], ebx
0x1004325ea  jmp     short loc_1004325B0
0x1004325ec  test    r9, r9
0x1004325ef  jz      short loc_1004325D1
0x1004325f1  mov     r8, [rsp+58h+arg_20]
0x1004325f9  test    r8, r8
0x1004325fc  jz      short loc_1004325D1
0x1004325fe  mov     ecx, [rsp+58h+arg_28]
0x100432605  cmp     ecx, 41h ; 'A'
0x100432608  jz      short loc_100432617
0x10043260a  lea     eax, [rcx-45h]
0x10043260d  cmp     eax, 2
0x100432610  jbe     short loc_100432617
0x100432612  xor     sil, sil
0x100432615  jmp     short loc_10043261A
0x100432617  mov     sil, 1
0x10043261a  mov     rbx, [rsp+58h+arg_38]
0x100432622  test    bl, 8
0x100432625  jnz     loc_100432711
0x10043262b  mov     rdx, [rdi]
0x10043262e  mov     rax, rdx
0x100432631  shr     rax, 34h
0x100432635  and     eax, 7FFh
0x10043263a  cmp     rax, 7FFh
0x100432640  jnz     loc_100432711
0x100432646  mov     rcx, 0FFFFFFFFFFFFFh
0x100432650  mov     rax, rdx
0x100432653  mov     r8d, 0Ch
0x100432659  and     rax, rcx
0x10043265c  jnz     short loc_100432662
0x10043265e  xor     ecx, ecx
0x100432660  jmp     short loc_10043268F
0x100432662  mov     rcx, 8000000000000h
0x10043266c  test    rdx, rdx
0x10043266f  jns     short loc_10043267B
0x100432671  cmp     rax, rcx
0x100432674  jnz     short loc_10043267B
0x100432676  mov     rcx, r8
0x100432679  jmp     short loc_10043268F
0x10043267b  mov     rax, rdx
0x10043267e  and     rax, rcx
0x100432681  neg     rax
0x100432684  sbb     rcx, rcx
0x100432687  and     rcx, 0FFFFFFFFFFFFFFFCh
0x10043268b  add     rcx, 8
0x10043268f  shr     rdx, 3Fh
0x100432693  lea     rax, [rdx+4]
0x100432697  cmp     r11, rax
0x10043269a  jnb     short loc_1004326A2
0x10043269c  mov     byte ptr [r10], 0
0x1004326a0  jmp     short loc_100432709
0x1004326a2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1004326a6  test    dl, dl
0x1004326a8  jz      short loc_1004326BD
0x1004326aa  mov     byte ptr [r10], 2Dh ; '-'
0x1004326ae  inc     r10
0x1004326b1  mov     byte ptr [r10], 0
0x1004326b5  cmp     r11, r8
0x1004326b8  jz      short loc_1004326BD
0x1004326ba  dec     r11
0x1004326bd  movzx   edx, sil
0x1004326c1  lea     rbx, off_10043EEB0; "INF"
0x1004326c8  xor     edx, 1
0x1004326cb  add     edx, edx
0x1004326cd  mov     eax, edx
0x1004326cf  add     rax, rcx
0x1004326d2  mov     r9, [rbx+rax*8]
0x1004326d6  inc     r8
0x1004326d9  cmp     byte ptr [r9+r8], 0
0x1004326de  jnz     short loc_1004326D6
0x1004326e0  xor     eax, eax
0x1004326e2  cmp     r11, r8
0x1004326e5  setbe   al
0x1004326e8  lea     r8d, [rdx+rax]
0x1004326ec  mov     rdx, r11; SizeInBytes
0x1004326ef  add     r8, rcx
0x1004326f2  mov     rcx, r10; Destination
0x1004326f5  mov     r8, [rbx+r8*8]; Source
0x1004326f9  call    strcpy_s
0x1004326fe  test    eax, eax
0x100432700  jnz     loc_10043284B
0x100432706  xor     r8d, r8d
0x100432709  mov     eax, r8d
0x10043270c  jmp     loc_10043283B
0x100432711  mov     rdx, rbx
0x100432714  and     bl, 20h
0x100432717  shr     rdx, 4
0x10043271b  and     edx, 1
0x10043271e  or      edx, 2
0x100432721  neg     bl
0x100432723  sbb     ebx, ebx
0x100432725  and     ebx, [rsp+58h+arg_40]
0x10043272c  sub     ecx, 41h ; 'A'
0x10043272f  jz      loc_100432803
0x100432735  sub     ecx, 4
0x100432738  jz      loc_1004327C9
0x10043273e  sub     ecx, 1
0x100432741  jz      short loc_100432798
0x100432743  sub     ecx, 1
0x100432746  jz      short loc_10043275B
0x100432748  sub     ecx, 1Ah
0x10043274b  jz      loc_100432803
0x100432751  sub     ecx, 4
0x100432754  jz      short loc_1004327C9
0x100432756  cmp     ecx, 1
0x100432759  jz      short loc_100432798
0x10043275b  mov     rax, [rsp+58h+arg_48]
0x100432763  mov     rcx, rdi
0x100432766  mov     [rsp+58h+var_10], rax
0x10043276b  mov     eax, dword ptr [rsp+58h+arg_30]
0x100432772  mov     [rsp+58h+var_18], ebx
0x100432776  mov     [rsp+58h+var_20], edx
0x10043277a  mov     rdx, r10
0x10043277d  mov     [rsp+58h+var_28], sil
0x100432782  mov     dword ptr [rsp+58h+Size], eax
0x100432786  mov     [rsp+58h+var_38], r8
0x10043278b  mov     r8, r11
0x10043278e  call    fp_format_g
0x100432793  jmp     loc_10043283B
0x100432798  mov     rax, [rsp+58h+arg_48]
0x1004327a0  mov     rdx, r10
0x1004327a3  mov     qword ptr [rsp+58h+var_20], rax
0x1004327a8  mov     rcx, rdi
0x1004327ab  mov     eax, dword ptr [rsp+58h+arg_30]
0x1004327b2  mov     dword ptr [rsp+58h+var_28], ebx
0x1004327b6  mov     dword ptr [rsp+58h+Size], eax
0x1004327ba  mov     [rsp+58h+var_38], r8
0x1004327bf  mov     r8, r11
0x1004327c2  call    fp_format_f
0x1004327c7  jmp     short loc_10043283B
0x1004327c9  mov     rax, [rsp+58h+arg_48]
0x1004327d1  mov     rcx, rdi; int
0x1004327d4  mov     [rsp+58h+var_10], rax; __crt_cached_ptd_host *
0x1004327d9  mov     eax, dword ptr [rsp+58h+arg_30]
0x1004327e0  mov     [rsp+58h+var_18], ebx; int
0x1004327e4  mov     [rsp+58h+var_20], edx; int
0x1004327e8  mov     rdx, r10; int
0x1004327eb  mov     [rsp+58h+var_28], sil; char
0x1004327f0  mov     dword ptr [rsp+58h+Size], eax; int
0x1004327f4  mov     [rsp+58h+var_38], r8; __int64
0x1004327f9  mov     r8, r11; int
0x1004327fc  call    fp_format_e
0x100432801  jmp     short loc_10043283B
0x100432803  mov     rax, [rsp+58h+arg_48]
0x10043280b  mov     rcx, rdi; int
0x10043280e  mov     [rsp+58h+var_10], rax; __crt_cached_ptd_host *
0x100432813  mov     eax, dword ptr [rsp+58h+arg_30]
0x10043281a  mov     [rsp+58h+var_18], ebx; int
0x10043281e  mov     [rsp+58h+var_20], edx; int
0x100432822  mov     rdx, r10; Str
0x100432825  mov     [rsp+58h+var_28], sil; char
0x10043282a  mov     dword ptr [rsp+58h+Size], eax; Size
0x10043282e  mov     [rsp+58h+var_38], r8; __int64
0x100432833  mov     r8, r11
0x100432836  call    fp_format_a
0x10043283b  mov     rbx, [rsp+58h+arg_0]
0x100432840  mov     rsi, [rsp+58h+arg_8]
0x100432845  add     rsp, 50h
0x100432849  pop     rdi
0x10043284a  retn
0x10043284b  and     [rsp+58h+var_38], 0
0x100432851  xor     r9d, r9d; LineNo
0x100432854  xor     r8d, r8d; FileName
0x100432857  xor     edx, edx; FunctionName
0x100432859  xor     ecx, ecx; Expression
0x10043285b  call    _invoke_watson
```
