# tson::input_archive::search(void)

- ea: `0x180018644`
- end: `0x18001874d`
- name: `?search@input_archive@tson@@AEAA_NXZ`
- size: `265`
- prototype: `bool __fastcall(tson::input_archive *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ec38`
- `0x18000ed68`
- `0x18000eff8`
- `0x18000f4e0`
- `0x180015a68`
- `0x180016c40`
- `0x180016d60`
- `0x180016e88`
- `0x180017524`
- `0x180018eac`

## callees

- `0x180018644`
- `0x1800198a4`

## pseudocode

```c
char __fastcall tson::input_archive::search(tson::input_archive *this)
{
  const char *v1; // r10
  char *v2; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned __int8 *v6; // rax
  unsigned __int8 v7; // r8
  int v8; // r8d
  _BYTE *v9; // r9
  _BYTE *v10; // r8
  int *v11; // rbx
  unsigned __int64 v13; // rax

  v1 = (const char *)*((_QWORD *)this + 2);
  v2 = (char *)this + 32;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 25) = 0;
  v4 = *((_QWORD *)this + 17);
  if ( v4 )
    v2 = &v2[4 * v4 - 4];
  else
    *v2 = 1;
  if ( *((_DWORD *)v2 + 1) == 1 )
    return 1;
  v5 = *(_QWORD *)this;
  v6 = *(unsigned __int8 **)(*(_QWORD *)this + 8LL);
  if ( (unsigned __int64)v6 >= *(_QWORD *)(*(_QWORD *)this + 16LL) )
    v7 = 0;
  else
    v7 = *v6;
  v8 = v7 - 6;
  if ( v8 )
  {
    if ( (unsigned int)(v8 - 1) >= 2 )
    {
      if ( !v1 )
      {
        v1 = "-";
        *((_BYTE *)this + 24) = 1;
      }
      v9 = *(_BYTE **)(v5 + 8);
      v10 = &v9[*((unsigned __int8 *)this + 24) + 2];
      if ( (unsigned __int64)v10 > *(_QWORD *)(v5 + 16) )
      {
        *(_BYTE *)(v5 + 24) = 1;
      }
      else
      {
        *(_QWORD *)(v5 + 8) = v10;
        if ( v9 )
        {
          v11 = (int *)((char *)this + 8);
          if ( *v9 != 5 && *v11 >= 0 )
            *v11 = -2147023267;
          if ( (v9[1] != *((_BYTE *)this + 24) || memcmp_0(v1, v9 + 2, *((unsigned __int8 *)this + 24))) && *v11 >= 0 )
            *v11 = -2147023092;
        }
      }
      return 1;
    }
    *((_BYTE *)this + 25) = 1;
  }
  v13 = *(_QWORD *)(v5 + 8);
  if ( v13 >= *(_QWORD *)(v5 + 16) )
    *(_BYTE *)(v5 + 24) = 1;
  else
    *(_QWORD *)(v5 + 8) = v13 + 1;
  return 0;
}

```

## disassembly

```asm
0x180018644  push    rbx
0x180018646  sub     rsp, 20h
0x18001864a  mov     r10, [rcx+10h]
0x18001864e  lea     rax, [rcx+20h]
0x180018652  mov     qword ptr [rcx+10h], 0
0x18001865a  mov     rdx, rcx
0x18001865d  mov     byte ptr [rcx+19h], 0
0x180018661  mov     rcx, [rax+68h]
0x180018665  test    rcx, rcx
0x180018668  jz      short loc_180018674
0x18001866a  lea     rax, [rax+rcx*4]
0x18001866e  add     rax, 0FFFFFFFFFFFFFFFCh
0x180018672  jmp     short loc_180018677
0x180018674  mov     byte ptr [rax], 1
0x180018677  cmp     dword ptr [rax+4], 1
0x18001867b  jz      loc_180018720
0x180018681  mov     rcx, [rdx]
0x180018684  mov     rax, [rcx+8]
0x180018688  cmp     rax, [rcx+10h]
0x18001868c  jnb     short loc_180018693
0x18001868e  mov     r8b, [rax]
0x180018691  jmp     short loc_180018696
0x180018693  xor     r8b, r8b
0x180018696  movzx   r8d, r8b
0x18001869a  sub     r8d, 6
0x18001869e  jz      loc_180018732
0x1800186a4  sub     r8d, 1
0x1800186a8  jz      loc_18001872E
0x1800186ae  cmp     r8d, 1
0x1800186b2  jz      short loc_18001872E
0x1800186b4  test    r10, r10
0x1800186b7  jnz     short loc_1800186C4
0x1800186b9  lea     r10, asc_18001DA6C; "-"
0x1800186c0  mov     byte ptr [rdx+18h], 1
0x1800186c4  movzx   r8d, byte ptr [rdx+18h]
0x1800186c9  mov     r9, [rcx+8]
0x1800186cd  add     r8, 2
0x1800186d1  add     r8, r9
0x1800186d4  cmp     r8, [rcx+10h]
0x1800186d8  ja      short loc_180018728
0x1800186da  mov     [rcx+8], r8
0x1800186de  test    r9, r9
0x1800186e1  jz      short loc_180018720
0x1800186e3  cmp     byte ptr [r9], 5
0x1800186e7  lea     rbx, [rdx+8]
0x1800186eb  jz      short loc_1800186F8
0x1800186ed  cmp     dword ptr [rbx], 0
0x1800186f0  jl      short loc_1800186F8
0x1800186f2  mov     dword ptr [rbx], 8007065Dh
0x1800186f8  movzx   eax, byte ptr [rdx+18h]
0x1800186fc  cmp     [r9+1], al
0x180018700  jnz     short loc_180018715
0x180018702  mov     r8d, eax; Size
0x180018705  lea     rdx, [r9+2]; Buf2
0x180018709  mov     rcx, r10; Buf1
0x18001870c  call    memcmp_0
0x180018711  test    eax, eax
0x180018713  jz      short loc_180018720
0x180018715  cmp     dword ptr [rbx], 0
0x180018718  jl      short loc_180018720
0x18001871a  mov     dword ptr [rbx], 8007070Ch
0x180018720  mov     al, 1
0x180018722  add     rsp, 20h
0x180018726  pop     rbx
0x180018727  retn
0x180018728  mov     byte ptr [rcx+18h], 1
0x18001872c  jmp     short loc_180018720
0x18001872e  mov     byte ptr [rdx+19h], 1
0x180018732  mov     rax, [rcx+8]
0x180018736  cmp     rax, [rcx+10h]
0x18001873a  jnb     short loc_180018745
0x18001873c  inc     rax
0x18001873f  mov     [rcx+8], rax
0x180018743  jmp     short loc_180018749
0x180018745  mov     byte ptr [rcx+18h], 1
0x180018749  xor     al, al
0x18001874b  jmp     short loc_180018722
```
