# GetInfo

- ea: `0x1800023ec`
- end: `0x1800024d6`
- name: `GetInfo`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cc0`

## callees

- `0x1800023ec`

## pseudocode

```c
__int64 __fastcall GetInfo(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 v4; // r9
  __int64 v5; // rcx
  TCHAR *v6; // r11
  _WORD *v7; // rax
  __int64 v8; // r10
  _WORD *v9; // rcx
  __int64 v10; // rax
  _WORD *v11; // rdx
  TCHAR *v12; // rcx
  bool v13; // zf
  _WORD *v14; // rcx

  if ( !a2 )
    return 568;
  if ( a3 < 0x238 )
    return 0;
  v4 = 2147483646;
  *(_DWORD *)a2 = 568;
  v5 = 2147483646;
  strcpy((char *)(a2 + 4), "vidcY411");
  *(_BYTE *)(a2 + 13) = 0;
  *(_WORD *)(a2 + 14) = 0;
  v6 = &szName[32];
  *(_DWORD *)(a2 + 16) = 0x10000;
  v7 = (_WORD *)(a2 + 56);
  *(_DWORD *)(a2 + 20) = 260;
  v8 = 128;
  do
  {
    if ( !v5 )
      break;
    if ( !*(_WORD *)v6 )
      break;
    *v7 = *(_WORD *)v6;
    v6 += 2;
    ++v7;
    --v5;
    --v8;
  }
  while ( v8 );
  v9 = v7 - 1;
  if ( v8 )
    v9 = v7;
  v10 = 16;
  v11 = (_WORD *)(a2 + 24);
  *v9 = 0;
  v12 = szName;
  do
  {
    if ( !v4 )
      break;
    if ( !*(_WORD *)v12 )
      break;
    *v11 = *(_WORD *)v12;
    v12 += 2;
    ++v11;
    --v4;
    --v10;
  }
  while ( v10 );
  v13 = v10 == 0;
  v14 = v11 - 1;
  result = 568;
  if ( !v13 )
    v14 = v11;
  *v14 = 0;
  return result;
}

```

## disassembly

```asm
0x1800023ec  mov     [rsp+arg_0], rbx
0x1800023f1  mov     [rsp+arg_8], rdi
0x1800023f6  xor     edi, edi
0x1800023f8  mov     eax, r8d
0x1800023fb  test    rdx, rdx
0x1800023fe  jnz     short loc_18000240A
0x180002400  mov     eax, 238h
0x180002405  jmp     loc_1800024CB
0x18000240a  mov     r8d, 238h
0x180002410  cmp     eax, r8d
0x180002413  jnb     short loc_18000241C
0x180002415  xor     eax, eax
0x180002417  jmp     loc_1800024CB
0x18000241c  mov     r9d, 7FFFFFFEh
0x180002422  mov     [rdx], r8d
0x180002425  mov     ecx, r9d
0x180002428  mov     dword ptr [rdx+4], 63646976h
0x18000242f  mov     qword ptr [rdx+8], 31313459h
0x180002437  lea     r11, szName+20h
0x18000243e  mov     dword ptr [rdx+10h], 10000h
0x180002445  lea     rax, [rdx+38h]
0x180002449  mov     dword ptr [rdx+14h], 104h
0x180002450  mov     r10d, 80h
0x180002456  test    rcx, rcx
0x180002459  jz      short loc_180002478
0x18000245b  movzx   ebx, word ptr [r11]
0x18000245f  test    bx, bx
0x180002462  jz      short loc_180002478
0x180002464  mov     [rax], bx
0x180002467  add     r11, 2
0x18000246b  add     rax, 2
0x18000246f  dec     rcx
0x180002472  sub     r10, 1
0x180002476  jnz     short loc_180002456
0x180002478  test    r10, r10
0x18000247b  lea     rcx, [rax-2]
0x18000247f  cmovnz  rcx, rax
0x180002483  mov     eax, 10h
0x180002488  add     rdx, 18h
0x18000248c  mov     [rcx], di
0x18000248f  lea     rcx, szName
0x180002496  test    r9, r9
0x180002499  jz      short loc_1800024BA
0x18000249b  movzx   r10d, word ptr [rcx]
0x18000249f  test    r10w, r10w
0x1800024a3  jz      short loc_1800024BA
0x1800024a5  mov     [rdx], r10w
0x1800024a9  add     rcx, 2
0x1800024ad  add     rdx, 2
0x1800024b1  dec     r9
0x1800024b4  sub     rax, 1
0x1800024b8  jnz     short loc_180002496
0x1800024ba  test    rax, rax
0x1800024bd  lea     rcx, [rdx-2]
0x1800024c1  mov     eax, r8d
0x1800024c4  cmovnz  rcx, rdx
0x1800024c8  mov     [rcx], di
0x1800024cb  mov     rbx, [rsp+arg_0]
0x1800024d0  mov     rdi, [rsp+arg_8]
0x1800024d5  retn
```
