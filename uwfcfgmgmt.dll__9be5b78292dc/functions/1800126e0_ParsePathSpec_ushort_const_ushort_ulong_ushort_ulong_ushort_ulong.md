# ParsePathSpec(ushort const *,ushort *,ulong,ushort *,ulong,ushort *,ulong)

- ea: `0x1800126e0`
- end: `0x18001292a`
- name: `?ParsePathSpec@@YAJPEBGPEAGK1K1K@Z`
- size: `586`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001384`
- `0x18000545c`
- `0x1800124d0`
- `0x180012640`
- `0x1800126e0`
- `0x18001afee`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180012808`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180012808`

## pseudocode

```c
__int64 __fastcall ParsePathSpec(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7)
{
  __int64 v7; // r12
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v11; // rsi
  signed int v12; // ebx
  __int64 v13; // rbx
  int v14; // eax
  const unsigned __int16 *v15; // r15
  __int64 v16; // rbp
  unsigned __int64 v17; // rbp
  unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rcx
  unsigned __int16 v20; // r11
  unsigned __int16 v21; // bx
  bool v22; // al
  __int64 v24; // rax
  unsigned __int16 *v25; // rcx
  __int64 v26; // r9
  unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // r8
  unsigned __int16 v29; // bx
  bool valid; // al
  __int64 v31; // rdx
  __int64 v32; // rax
  unsigned __int16 *v33; // rcx
  unsigned __int16 *v34; // rcx

  v7 = a3;
  v8 = a4;
  v11 = 0;
  if ( a1 && a4 && a6 )
  {
    if ( !a3 || !a5 || !a7 )
      goto LABEL_22;
    v13 = -1;
    do
      ++v13;
    while ( a1[v13] );
    v14 = wcsncmp_0(a1, L"\\\\?\\", 4u);
    v15 = a1 + 4;
    if ( v14 )
      v15 = a1;
    v16 = v13 - 4;
    if ( v14 )
      v16 = v13;
    if ( !v16 )
      goto LABEL_22;
    v17 = v16 + 1;
    v18 = (unsigned __int16 *)operator new[](saturated_mul(v17, 2u));
    v11 = v18;
    if ( !v18 )
    {
      v12 = -2147024882;
      goto LABEL_23;
    }
    v12 = StringCchCopyW(v18, v17, v15);
    if ( v12 < 0 )
      goto LABEL_23;
    *v8 = v20;
    *a2 = v20;
    if ( v17 >= 0x2D && (v21 = v11[44], v11[44] = v20, v22 = IsGuidMatch(v19, v11), v20 = 0, v11[44] = v21, v22) )
    {
      if ( (unsigned int)v7 > 0x7FFFFFFF )
      {
        *a2 = 0;
LABEL_22:
        v12 = -2147024809;
        goto LABEL_23;
      }
      v24 = 44;
      v25 = v11;
      v26 = v7;
      do
      {
        if ( !v24 )
          break;
        if ( !*v25 )
          break;
        *a2++ = *v25++;
        --v24;
        --v26;
      }
      while ( v26 );
      v27 = a2 - 1;
      v12 = v26 == 0 ? 0x8007007A : 0;
      if ( v26 )
        v27 = a2;
      *v27 = 0;
      if ( v26 )
      {
        v28 = v11 + 44;
LABEL_32:
        v12 = StringCchCopyW(a6, a7, v28);
      }
    }
    else
    {
      if ( v17 < 3 )
        goto LABEL_22;
      v29 = v11[2];
      v11[2] = v20;
      valid = IsValidDriveLetter(v11);
      v11[2] = v29;
      if ( !valid )
        goto LABEL_22;
      v31 = a5;
      if ( a5 > 0x7FFFFFFFuLL )
      {
        *v8 = 0;
        goto LABEL_22;
      }
      v32 = 2;
      v33 = v11;
      do
      {
        if ( !v32 )
          break;
        if ( !*v33 )
          break;
        *v8++ = *v33++;
        --v32;
        --v31;
      }
      while ( v31 );
      v34 = v8 - 1;
      v12 = v31 == 0 ? 0x8007007A : 0;
      if ( v31 )
        v34 = v8;
      *v34 = 0;
      if ( v31 )
      {
        v28 = v11 + 2;
        goto LABEL_32;
      }
    }
  }
  else
  {
    v12 = -2147467261;
  }
LABEL_23:
  operator delete[](v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800126e0  push    rbx
0x1800126e2  push    rbp
0x1800126e3  push    rsi
0x1800126e4  push    rdi
0x1800126e5  push    r12
0x1800126e7  push    r14
0x1800126e9  push    r15
0x1800126eb  sub     rsp, 20h
0x1800126ef  xor     eax, eax
0x1800126f1  mov     r12d, r8d
0x1800126f4  mov     rdi, r9
0x1800126f7  mov     r14, rdx
0x1800126fa  mov     rbp, rcx
0x1800126fd  mov     esi, eax
0x1800126ff  test    rcx, rcx
0x180012702  jnz     short loc_18001270E
0x180012704  mov     ebx, 80004003h
0x180012709  jmp     loc_180012805
0x18001270e  test    rdi, rdi
0x180012711  jz      short loc_180012704
0x180012713  cmp     [rsp+58h+arg_28], rax
0x18001271b  jz      short loc_180012704
0x18001271d  test    r8d, r8d
0x180012720  jz      loc_180012800
0x180012726  cmp     [rsp+58h+arg_20], eax
0x18001272d  jz      loc_180012800
0x180012733  cmp     [rsp+58h+arg_30], eax
0x18001273a  jz      loc_180012800
0x180012740  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012744  inc     rbx
0x180012747  cmp     [rcx+rbx*2], ax
0x18001274b  jnz     short loc_180012744
0x18001274d  mov     r8d, 4; MaxCount
0x180012753  lea     rdx, String2; "\\\\?\\"
0x18001275a  call    wcsncmp_0
0x18001275f  test    eax, eax
0x180012761  lea     r15, [rbp+8]
0x180012765  cmovnz  r15, rbp
0x180012769  lea     rbp, [rbx-4]
0x18001276d  cmovnz  rbp, rbx
0x180012771  test    rbp, rbp
0x180012774  jz      loc_180012800
0x18001277a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012781  inc     rbp
0x180012784  mov     eax, 2
0x180012789  mul     rbp
0x18001278c  cmovb   rax, rcx
0x180012790  mov     rcx, rax; unsigned __int64
0x180012793  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012798  xor     r11d, r11d
0x18001279b  mov     rsi, rax
0x18001279e  test    rax, rax
0x1800127a1  jnz     short loc_1800127AA
0x1800127a3  mov     ebx, 8007000Eh
0x1800127a8  jmp     short loc_180012805
0x1800127aa  mov     r8, r15; unsigned __int16 *
0x1800127ad  mov     rdx, rbp; unsigned __int64
0x1800127b0  mov     rcx, rsi; unsigned __int16 *
0x1800127b3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800127b8  mov     ebx, eax
0x1800127ba  test    eax, eax
0x1800127bc  js      short loc_180012805
0x1800127be  mov     [rdi], r11w
0x1800127c2  mov     [r14], r11w
0x1800127c6  cmp     rbp, 2Dh ; '-'
0x1800127ca  jb      loc_18001288B
0x1800127d0  lea     r15, [rsi+58h]
0x1800127d4  mov     rdx, rsi; unsigned __int16 *
0x1800127d7  movzx   ebx, word ptr [r15]
0x1800127db  mov     [r15], r11w
0x1800127df  call    ?IsGuidMatch@@YA_NPEBG0@Z; IsGuidMatch(ushort const *,ushort const *)
0x1800127e4  xor     r11d, r11d
0x1800127e7  mov     [r15], bx
0x1800127eb  test    al, al
0x1800127ed  jz      loc_18001288B
0x1800127f3  cmp     r12d, 7FFFFFFFh
0x1800127fa  jbe     short loc_18001281F
0x1800127fc  mov     [r14], r11w
0x180012800  mov     ebx, 80070057h
0x180012805  mov     rcx, rsi
0x180012808  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001280e  mov     eax, ebx
0x180012810  add     rsp, 20h
0x180012814  pop     r15
0x180012816  pop     r14
0x180012818  pop     r12
0x18001281a  pop     rdi
0x18001281b  pop     rsi
0x18001281c  pop     rbp
0x18001281d  pop     rbx
0x18001281e  retn
0x18001281f  mov     eax, 2Ch ; ','
0x180012824  mov     rcx, rsi
0x180012827  mov     r9, r12
0x18001282a  test    rax, rax
0x18001282d  jz      short loc_18001284C
0x18001282f  movzx   edx, word ptr [rcx]
0x180012832  test    dx, dx
0x180012835  jz      short loc_18001284C
0x180012837  mov     [r14], dx
0x18001283b  add     rcx, 2
0x18001283f  add     r14, 2
0x180012843  dec     rax
0x180012846  sub     r9, 1
0x18001284a  jnz     short loc_18001282A
0x18001284c  mov     rax, r9
0x18001284f  lea     rdx, [r14-2]
0x180012853  neg     rax
0x180012856  sbb     ebx, ebx
0x180012858  not     ebx
0x18001285a  and     ebx, 8007007Ah
0x180012860  test    r9, r9
0x180012863  cmovnz  rdx, r14
0x180012867  mov     [rdx], r11w
0x18001286b  jz      short loc_180012805
0x18001286d  mov     r8, r15; unsigned __int16 *
0x180012870  mov     edx, [rsp+58h+arg_30]; unsigned __int64
0x180012877  mov     rcx, [rsp+58h+arg_28]; unsigned __int16 *
0x18001287f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012884  mov     ebx, eax
0x180012886  jmp     loc_180012805
0x18001288b  cmp     rbp, 3
0x18001288f  jb      loc_180012800
0x180012895  lea     r14, [rsi+4]
0x180012899  mov     rcx, rsi; unsigned __int16 *
0x18001289c  movzx   ebx, word ptr [r14]
0x1800128a0  mov     [r14], r11w
0x1800128a4  call    ?IsValidDriveLetter@@YA_NPEBG@Z; IsValidDriveLetter(ushort const *)
0x1800128a9  xor     r9d, r9d
0x1800128ac  mov     [r14], bx
0x1800128b0  test    al, al
0x1800128b2  jz      loc_180012800
0x1800128b8  mov     edx, [rsp+58h+arg_20]
0x1800128bf  cmp     rdx, 7FFFFFFFh
0x1800128c6  jbe     short loc_1800128D1
0x1800128c8  mov     [rdi], r9w
0x1800128cc  jmp     loc_180012800
0x1800128d1  mov     eax, 2
0x1800128d6  mov     rcx, rsi
0x1800128d9  test    rax, rax
0x1800128dc  jz      short loc_1800128FD
0x1800128de  movzx   r8d, word ptr [rcx]
0x1800128e2  test    r8w, r8w
0x1800128e6  jz      short loc_1800128FD
0x1800128e8  mov     [rdi], r8w
0x1800128ec  add     rcx, 2
0x1800128f0  add     rdi, 2
0x1800128f4  dec     rax
0x1800128f7  sub     rdx, 1
0x1800128fb  jnz     short loc_1800128D9
0x1800128fd  mov     rax, rdx
0x180012900  lea     rcx, [rdi-2]
0x180012904  neg     rax
0x180012907  sbb     ebx, ebx
0x180012909  not     ebx
0x18001290b  and     ebx, 8007007Ah
0x180012911  test    rdx, rdx
0x180012914  cmovnz  rcx, rdi
0x180012918  mov     [rcx], r9w
0x18001291c  jz      loc_180012805
0x180012922  mov     r8, r14
0x180012925  jmp     loc_180012870
```
