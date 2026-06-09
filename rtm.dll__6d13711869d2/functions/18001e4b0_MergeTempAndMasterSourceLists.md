# MergeTempAndMasterSourceLists

- ea: `0x18001e4b0`
- end: `0x18001e59a`
- name: `MergeTempAndMasterSourceLists`
- size: `234`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180019de0`
- `0x18001a360`
- `0x18001c0c8`
- `0x18001cf18`
- `0x18001ed64`

## callees

- `0x18001e4b0`

## pseudocode

```c
void __fastcall MergeTempAndMasterSourceLists(__int64 a1)
{
  _QWORD *v2; // r11
  _QWORD *v3; // r8
  _QWORD *i; // r9
  _QWORD *v5; // rcx
  __int64 v6; // rax
  _QWORD *v7; // rax
  int v8; // esi
  unsigned int v9; // ebx
  int v10; // edx
  _QWORD *v11; // rax

  if ( *(_DWORD *)(a1 + 52) )
  {
    v2 = (_QWORD *)(a1 + 56);
    v3 = (_QWORD *)(a1 + 72);
LABEL_3:
    for ( i = (_QWORD *)*v3; ; i[1] = v5 )
    {
      v5 = (_QWORD *)*v2;
      if ( (_QWORD *)*v2 == v2 )
        break;
      if ( (_QWORD *)v5[1] != v2 )
        goto LABEL_20;
      v6 = *v5;
      if ( *(_QWORD **)(*v5 + 8LL) != v5 )
        goto LABEL_20;
      *v2 = v6;
      *(_QWORD *)(v6 + 8) = v2;
      if ( (_QWORD *)*v3 == v3 )
      {
        v7 = (_QWORD *)v3[1];
        if ( (_QWORD *)*v7 != v3 )
LABEL_20:
          __fastfail(3u);
        *v5 = v3;
        v5[1] = v7;
        *v7 = v5;
        v3[1] = v5;
        goto LABEL_3;
      }
      if ( i != v3 )
      {
        v8 = *((unsigned __int8 *)v5 + 104);
        do
        {
          v9 = *((_DWORD *)i + 26);
          v10 = v8 - (unsigned __int8)v9;
          if ( v8 == (unsigned __int8)v9 )
          {
            v10 = (v5[13] & 0xFF00) - (i[13] & 0xFF00);
            if ( !v10 )
            {
              v10 = (v5[13] & 0xFF0000) - (v9 & 0xFF0000);
              if ( !v10 )
                v10 = ((*((_DWORD *)v5 + 26) >> 8) & 0xFF0000) - ((v9 >> 8) & 0xFF0000);
            }
          }
          if ( v10 < 0 )
            break;
          i = (_QWORD *)*i;
        }
        while ( i != v3 );
      }
      v11 = (_QWORD *)i[1];
      if ( (_QWORD *)*v11 != i )
        goto LABEL_20;
      *v5 = i;
      v5[1] = v11;
      *v11 = v5;
    }
    *(_DWORD *)(a1 + 52) = 0;
  }
}

```

## disassembly

```asm
0x18001e4b0  push    rbx
0x18001e4b2  push    rbp
0x18001e4b3  push    rsi
0x18001e4b4  cmp     dword ptr [rcx+34h], 0
0x18001e4b8  mov     r10, rcx
0x18001e4bb  jz      loc_18001E596
0x18001e4c1  lea     r11, [rcx+38h]
0x18001e4c5  mov     ebp, 0FF0000h
0x18001e4ca  lea     r8, [rcx+48h]
0x18001e4ce  mov     r9, [r8]
0x18001e4d1  mov     rcx, [r11]
0x18001e4d4  cmp     rcx, r11
0x18001e4d7  jz      loc_18001E58E
0x18001e4dd  cmp     [rcx+8], r11
0x18001e4e1  jnz     loc_18001E587
0x18001e4e7  mov     rax, [rcx]
0x18001e4ea  cmp     [rax+8], rcx
0x18001e4ee  jnz     loc_18001E587
0x18001e4f4  mov     [r11], rax
0x18001e4f7  mov     [rax+8], r11
0x18001e4fb  cmp     [r8], r8
0x18001e4fe  jnz     short loc_18001E519
0x18001e500  mov     rax, [r8+8]
0x18001e504  cmp     [rax], r8
0x18001e507  jnz     short loc_18001E587
0x18001e509  mov     [rcx], r8
0x18001e50c  mov     [rcx+8], rax
0x18001e510  mov     [rax], rcx
0x18001e513  mov     [r8+8], rcx
0x18001e517  jmp     short loc_18001E4CE
0x18001e519  cmp     r9, r8
0x18001e51c  jz      short loc_18001E56B
0x18001e51e  movzx   esi, byte ptr [rcx+68h]
0x18001e522  mov     ebx, [r9+68h]
0x18001e526  mov     edx, esi
0x18001e528  movzx   eax, bl
0x18001e52b  sub     edx, eax
0x18001e52d  jnz     short loc_18001E55F
0x18001e52f  mov     edx, [rcx+68h]
0x18001e532  mov     eax, ebx
0x18001e534  and     eax, 0FF00h
0x18001e539  and     edx, 0FF00h
0x18001e53f  sub     edx, eax
0x18001e541  jnz     short loc_18001E55F
0x18001e543  mov     edx, [rcx+68h]
0x18001e546  mov     eax, ebx
0x18001e548  and     eax, ebp
0x18001e54a  and     edx, ebp
0x18001e54c  sub     edx, eax
0x18001e54e  jnz     short loc_18001E55F
0x18001e550  mov     edx, [rcx+68h]
0x18001e553  shr     edx, 8
0x18001e556  shr     ebx, 8
0x18001e559  and     edx, ebp
0x18001e55b  and     ebx, ebp
0x18001e55d  sub     edx, ebx
0x18001e55f  test    edx, edx
0x18001e561  js      short loc_18001E56B
0x18001e563  mov     r9, [r9]
0x18001e566  cmp     r9, r8
0x18001e569  jnz     short loc_18001E522
0x18001e56b  mov     rax, [r9+8]
0x18001e56f  cmp     [rax], r9
0x18001e572  jnz     short loc_18001E587
0x18001e574  mov     [rcx], r9
0x18001e577  mov     [rcx+8], rax
0x18001e57b  mov     [rax], rcx
0x18001e57e  mov     [r9+8], rcx
0x18001e582  jmp     loc_18001E4D1
0x18001e587  mov     ecx, 3
0x18001e58c  int     29h; Win8: RtlFailFast(ecx)
0x18001e58e  mov     dword ptr [r10+34h], 0
0x18001e596  pop     rsi
0x18001e597  pop     rbp
0x18001e598  pop     rbx
0x18001e599  retn
```
