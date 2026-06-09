# SsSetField

- ea: `0x180012734`
- end: `0x18001290e`
- name: `SsSetField`
- size: `474`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012938`
- `0x180015500`
- `0x180024130`
- `0x18002c110`

## callees

- `0x180012734`
- `0x180024db8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800128d8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800128ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800128d8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800128ec`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180012880`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180012880`

## string_xrefs

- `0x1800128e5`: `Comment`

## pseudocode

```c
__int64 __fastcall SsSetField(_QWORD *a1, BYTE **a2, char a3, _BYTE *a4)
{
  int v6; // ecx
  __int128 *v9; // r10
  int v10; // ecx
  int v11; // ecx
  int v12; // eax
  __int16 v13; // r9
  __int16 *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r10d
  BYTE *v17; // r8
  __int64 v18; // r11
  BYTE *v19; // rax
  int v20; // r11d
  int v21; // r9d
  unsigned int v22; // ecx
  char v23; // al
  __int64 v25; // rcx

  v6 = *((_DWORD *)a1 + 4);
  if ( (unsigned int)(v6 - 500) >= 0x64 )
  {
    v9 = &SsData;
  }
  else
  {
    v9 = &xmmword_18005CC08;
    if ( v6 == 598 )
      v9 = (__int128 *)&dword_18005CCF0;
  }
  v10 = *((_DWORD *)a1 + 2);
  if ( !v10 )
  {
    v23 = *(_BYTE *)a2;
    if ( *(_BYTE *)a2 < 2u )
    {
      v25 = *((unsigned int *)a1 + 3);
      if ( (_DWORD)v25 == 48 && v23 && !*((_BYTE *)v9 + v25) && a4 )
        *a4 = 1;
      *((_BYTE *)v9 + v25) = v23;
      goto LABEL_45;
    }
    return 87;
  }
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 != 1 )
      goto LABEL_45;
    v12 = *((_DWORD *)a1 + 3);
    switch ( v12 )
    {
      case 8:
        v13 = WideCharStr;
        v14 = (__int16 *)&WideCharStr;
        v15 = 260;
        v16 = 260;
        break;
      case 32:
        v13 = word_18005D560[0];
        v14 = word_18005D560;
        v16 = 256;
        v15 = 257;
        break;
      case 64:
        v13 = word_18005D762[0];
        v14 = word_18005D762;
        v16 = 260;
        v15 = 261;
        break;
      case 72:
        v13 = pszDest;
        v14 = (__int16 *)&pszDest;
        v16 = 15;
        v15 = 260;
        break;
      default:
        return 87;
    }
    v17 = *a2;
    if ( !*a2 )
      goto LABEL_21;
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)&v17[2 * v18] );
    if ( (unsigned int)v18 <= v16 )
    {
LABEL_21:
      if ( v12 == 32 )
      {
        if ( v17 )
        {
          v19 = *a2;
          do
          {
            v20 = *(unsigned __int16 *)&v19[(char *)v14 - (char *)v17];
            v21 = *(unsigned __int16 *)v19 - v20;
            if ( v21 )
              break;
            v19 += 2;
          }
          while ( v20 );
          if ( !v21 )
          {
LABEL_33:
            _o_wcscpy_s(v14, v15);
            goto LABEL_45;
          }
        }
        else if ( !v13 )
        {
LABEL_32:
          *(_DWORD *)v14 = 0;
          goto LABEL_45;
        }
        if ( a4 )
          *a4 = 1;
      }
      if ( !v17 )
        goto LABEL_32;
      goto LABEL_33;
    }
    return 87;
  }
  v22 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 > *((_DWORD *)a1 + 11) || v22 < *((_DWORD *)a1 + 10) )
    return 87;
  *(_DWORD *)((char *)v9 + *((unsigned int *)a1 + 3)) = v22;
LABEL_45:
  if ( a3 && (unsigned int)_o__wcsicmp(*a1, L"Disc") )
  {
    if ( (unsigned int)_o__wcsicmp(*a1, L"Comment") )
      SsAddParameterToRegistry((__int64)a1, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x180012734  push    rbx
0x180012736  push    rbp
0x180012737  push    rsi
0x180012738  push    rdi
0x180012739  push    r14
0x18001273b  sub     rsp, 20h
0x18001273f  mov     rbx, rcx
0x180012742  mov     rdi, r9
0x180012745  mov     ecx, [rcx+10h]
0x180012748  mov     bpl, r8b
0x18001274b  mov     rsi, rdx
0x18001274e  lea     eax, [rcx-1F4h]
0x180012754  cmp     eax, 64h ; 'd'
0x180012757  jnb     short loc_180012773
0x180012759  cmp     ecx, 256h
0x18001275f  lea     rax, dword_18005CCF0
0x180012766  lea     r10, xmmword_18005CC08
0x18001276d  cmovz   r10, rax
0x180012771  jmp     short loc_18001277A
0x180012773  lea     r10, SsData
0x18001277a  mov     ecx, [rbx+8]
0x18001277d  xor     r14d, r14d
0x180012780  test    ecx, ecx
0x180012782  jz      loc_18001289D
0x180012788  sub     ecx, 1
0x18001278b  jz      loc_180012888
0x180012791  cmp     ecx, 1
0x180012794  jnz     loc_1800128C9
0x18001279a  mov     eax, [rbx+0Ch]
0x18001279d  cmp     eax, 8
0x1800127a0  jnz     short loc_1800127BB
0x1800127a2  movzx   r9d, cs:WideCharStr
0x1800127aa  lea     rcx, WideCharStr
0x1800127b1  mov     edx, 104h
0x1800127b6  mov     r10d, edx
0x1800127b9  jmp     short loc_18001281C
0x1800127bb  cmp     eax, 20h ; ' '
0x1800127be  jnz     short loc_1800127DB
0x1800127c0  movzx   r9d, cs:word_18005D560
0x1800127c8  lea     rcx, word_18005D560
0x1800127cf  mov     r10d, 100h
0x1800127d5  lea     edx, [r10+1]
0x1800127d9  jmp     short loc_18001281C
0x1800127db  cmp     eax, 40h ; '@'
0x1800127de  jnz     short loc_1800127FB
0x1800127e0  movzx   r9d, cs:word_18005D762
0x1800127e8  lea     rcx, word_18005D762
0x1800127ef  mov     r10d, 104h
0x1800127f5  lea     edx, [r10+1]
0x1800127f9  jmp     short loc_18001281C
0x1800127fb  cmp     eax, 48h ; 'H'
0x1800127fe  jnz     loc_1800128A3
0x180012804  movzx   r9d, cs:pszDest
0x18001280c  lea     rcx, pszDest
0x180012813  lea     r10d, [rax-39h]
0x180012817  mov     edx, 104h
0x18001281c  mov     r8, [rsi]
0x18001281f  test    r8, r8
0x180012822  jz      short loc_180012837
0x180012824  or      r11, 0FFFFFFFFFFFFFFFFh
0x180012828  inc     r11
0x18001282b  cmp     [r8+r11*2], r14w
0x180012830  jnz     short loc_180012828
0x180012832  cmp     r11d, r10d
0x180012835  ja      short loc_1800128A3
0x180012837  cmp     eax, 20h ; ' '
0x18001283a  jnz     short loc_180012876
0x18001283c  test    r8, r8
0x18001283f  jnz     short loc_180012849
0x180012841  test    r9w, r9w
0x180012845  jz      short loc_18001287B
0x180012847  jmp     short loc_18001286E
0x180012849  mov     r10, rcx
0x18001284c  mov     rax, r8
0x18001284f  sub     r10, r8
0x180012852  movzx   r9d, word ptr [rax]
0x180012856  movzx   r11d, word ptr [rax+r10]
0x18001285b  sub     r9d, r11d
0x18001285e  jnz     short loc_180012869
0x180012860  add     rax, 2
0x180012864  test    r11d, r11d
0x180012867  jnz     short loc_180012852
0x180012869  test    r9d, r9d
0x18001286c  jz      short loc_180012880
0x18001286e  test    rdi, rdi
0x180012871  jz      short loc_180012876
0x180012873  mov     byte ptr [rdi], 1
0x180012876  test    r8, r8
0x180012879  jnz     short loc_180012880
0x18001287b  mov     [rcx], r14d
0x18001287e  jmp     short loc_1800128C9
0x180012880  call    cs:__imp__o_wcscpy_s
0x180012886  jmp     short loc_1800128C9
0x180012888  mov     ecx, [rdx]
0x18001288a  cmp     ecx, [rbx+2Ch]
0x18001288d  ja      short loc_1800128A3
0x18001288f  cmp     ecx, [rbx+28h]
0x180012892  jb      short loc_1800128A3
0x180012894  mov     eax, [rbx+0Ch]
0x180012897  mov     [rax+r10], ecx
0x18001289b  jmp     short loc_1800128C9
0x18001289d  mov     al, [rdx]
0x18001289f  cmp     al, 2
0x1800128a1  jb      short loc_1800128AA
0x1800128a3  mov     eax, 57h ; 'W'
0x1800128a8  jmp     short loc_180012903
0x1800128aa  mov     ecx, [rbx+0Ch]
0x1800128ad  cmp     ecx, 30h ; '0'
0x1800128b0  jnz     short loc_1800128C5
0x1800128b2  test    al, al
0x1800128b4  jz      short loc_1800128C5
0x1800128b6  cmp     [rcx+r10], r14b
0x1800128ba  jnz     short loc_1800128C5
0x1800128bc  test    rdi, rdi
0x1800128bf  jz      short loc_1800128C5
0x1800128c1  mov     byte ptr [r9], 1
0x1800128c5  mov     [rcx+r10], al
0x1800128c9  test    bpl, bpl
0x1800128cc  jz      short loc_180012901
0x1800128ce  mov     rcx, [rbx]
0x1800128d1  lea     rdx, aDisc_0; "Disc"
0x1800128d8  call    cs:__imp__o__wcsicmp
0x1800128de  test    eax, eax
0x1800128e0  jz      short loc_180012901
0x1800128e2  mov     rcx, [rbx]
0x1800128e5  lea     rdx, aComment; "Comment"
0x1800128ec  call    cs:__imp__o__wcsicmp
0x1800128f2  test    eax, eax
0x1800128f4  jz      short loc_180012901
0x1800128f6  mov     rdx, rsi
0x1800128f9  mov     rcx, rbx
0x1800128fc  call    SsAddParameterToRegistry
0x180012901  xor     eax, eax
0x180012903  add     rsp, 20h
0x180012907  pop     r14
0x180012909  pop     rdi
0x18001290a  pop     rsi
0x18001290b  pop     rbp
0x18001290c  pop     rbx
0x18001290d  retn
```
