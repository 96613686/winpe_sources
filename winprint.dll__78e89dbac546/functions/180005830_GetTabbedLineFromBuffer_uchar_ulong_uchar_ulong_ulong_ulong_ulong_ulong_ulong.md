# GetTabbedLineFromBuffer(uchar *,ulong,uchar *,ulong,ulong,ulong,ulong *,ulong *,ulong *)

- ea: `0x180005830`
- end: `0x180005ab4`
- name: `?GetTabbedLineFromBuffer@@YAPEAEPEAEK0KKKPEAK11@Z`
- size: `644`
- prototype: `unsigned __int8 *__fastcall(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, UINT CodePage, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005abc`

## callees

- `0x180005830`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x18000592c`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x18000595d`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x18000592c`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x18000595d`

## pseudocode

```c
unsigned __int8 *__fastcall GetTabbedLineFromBuffer(
        unsigned __int8 *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5,
        UINT CodePage,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int *a9)
{
  unsigned __int8 *v9; // rdi
  unsigned __int8 *v11; // r14
  int v12; // ecx
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rbp
  int v16; // edx
  unsigned __int8 *v17; // r13
  int v18; // r9d
  BYTE v19; // dl
  unsigned int v20; // r8d
  unsigned __int8 *v21; // r15
  unsigned __int8 v22; // al
  BOOL v23; // eax
  unsigned int v24; // edx
  unsigned int v25; // eax
  unsigned int v26; // ecx
  int v27; // r8d
  int v29; // [rsp+68h] [rbp+10h]

  v9 = a3;
  v11 = &a3[a4];
  v12 = *a8;
  v13 = a2;
  if ( *a8 && (v14 = *a9, (*a9 & 2) != 0) )
  {
    LODWORD(v15) = 0;
    v16 = *a8;
    do
    {
      if ( v9 >= v11 )
        goto LABEL_7;
      *v9 = 32;
      LODWORD(v15) = v15 + 1;
      ++v9;
      --v16;
    }
    while ( v16 );
    if ( v9 >= v11 )
    {
LABEL_7:
      *a8 = v12 - a4;
      *a9 = v14 | 0x60;
      *a7 = v15;
      return a1;
    }
    *a9 = v14 & 0xFFFFFFFD;
  }
  else
  {
    v15 = *a7;
    v9 += v15;
  }
  v17 = &a1[v13];
  v18 = a5 - v12;
  v29 = a5 - v12;
  while ( a1 < v17 )
  {
    v19 = *a1;
    v20 = *a9;
    switch ( *a1 )
    {
      case 9u:
        v20 &= ~1u;
        *a9 = v20;
        if ( v9 >= v11 )
          goto LABEL_40;
        ++a1;
        v24 = (v18 + (int)v15) % a5;
        v25 = 0;
        v26 = a5 - v24;
        if ( a5 != v24 )
        {
          while ( v9 < v11 )
          {
            *v9 = 32;
            ++v25;
            ++v9;
            if ( v25 >= v26 )
            {
              if ( v9 < v11 )
                goto LABEL_31;
              break;
            }
          }
          v20 |= 2u;
LABEL_40:
          *a8 = (a5 + *a8 - a4 % a5) % a5;
LABEL_41:
          v27 = v20 | 0x60;
          goto LABEL_42;
        }
LABEL_31:
        LODWORD(v15) = v26 + v15;
        break;
      case 0xAu:
        ++a1;
        if ( (v20 & 1) == 0 )
        {
          if ( (v20 & 0x80u) != 0 )
          {
            *a8 = 0;
            goto LABEL_41;
          }
          v27 = v20 | 0x20;
LABEL_42:
          *a9 = v27;
          goto LABEL_44;
        }
        *a9 = v20 & 0xFFFFFFFE;
        break;
      case 0xCu:
        *a8 = 0;
        *a9 = v20 & 0xFFFFFFEE | 0x10;
        ++a1;
        goto LABEL_44;
      case 0xDu:
        ++a1;
        *a8 = 0;
        *a9 = v20 | ((v20 & 0x100) != 0 ? 97 : 64);
        goto LABEL_44;
      default:
        v20 &= ~1u;
        *a9 = v20;
        if ( v9 >= v11 )
          goto LABEL_40;
        v21 = v9 + 1;
        if ( v9 + 1 >= v11 && IsDBCSLeadByteEx(CodePage, v19) )
        {
          v20 = *a9;
          goto LABEL_40;
        }
        v22 = *a1;
        LODWORD(v15) = v15 + 1;
        ++a1;
        *v9++ = v22;
        if ( a1 >= v17 )
          goto LABEL_43;
        v23 = IsDBCSLeadByteEx(CodePage, *a1);
        v18 = v29;
        if ( v23 )
        {
          if ( a1 + 1 >= v17 )
          {
            *a9 |= 8u;
            goto LABEL_44;
          }
          if ( v21 < v11 )
          {
            v9 = v21 + 1;
            *v21 = *a1;
            LODWORD(v15) = v15 + 1;
            ++a1;
          }
        }
        break;
    }
  }
LABEL_43:
  a1 = 0;
LABEL_44:
  *a7 = v15;
  return a1;
}

```

## disassembly

```asm
0x180005830  mov     [rsp+arg_0], rbx
0x180005835  mov     [rsp+arg_18], r9d
0x18000583a  push    rbp
0x18000583b  push    rsi
0x18000583c  push    rdi
0x18000583d  push    r12
0x18000583f  push    r13
0x180005841  push    r14
0x180005843  push    r15
0x180005845  sub     rsp, 20h
0x180005849  mov     r12, [rsp+58h+arg_38]
0x180005851  mov     rdi, r8
0x180005854  mov     rsi, [rsp+58h+arg_40]
0x18000585c  mov     rbx, rcx
0x18000585f  mov     r14d, r9d
0x180005862  add     r14, rdi
0x180005865  mov     r10d, r9d
0x180005868  mov     ecx, [r12]
0x18000586c  mov     r8d, edx
0x18000586f  test    ecx, ecx
0x180005871  jz      short loc_1800058B6
0x180005873  mov     eax, [rsi]
0x180005875  test    al, 2
0x180005877  jz      short loc_1800058B6
0x180005879  xor     ebp, ebp
0x18000587b  mov     edx, ecx
0x18000587d  cmp     rdi, r14
0x180005880  jnb     short loc_180005894
0x180005882  mov     byte ptr [rdi], 20h ; ' '
0x180005885  inc     ebp
0x180005887  inc     rdi
0x18000588a  add     edx, 0FFFFFFFFh
0x18000588d  jnz     short loc_18000587D
0x18000588f  cmp     rdi, r14
0x180005892  jb      short loc_1800058AF
0x180005894  mov     rdx, [rsp+58h+arg_30]
0x18000589c  sub     ecx, r10d
0x18000589f  or      eax, 60h
0x1800058a2  mov     [r12], ecx
0x1800058a6  mov     [rsi], eax
0x1800058a8  mov     [rdx], ebp
0x1800058aa  jmp     loc_180005A9C
0x1800058af  and     eax, 0FFFFFFFDh
0x1800058b2  mov     [rsi], eax
0x1800058b4  jmp     short loc_1800058C3
0x1800058b6  mov     rdx, [rsp+58h+arg_30]
0x1800058be  mov     ebp, [rdx]
0x1800058c0  add     rdi, rbp
0x1800058c3  mov     r9d, [rsp+58h+arg_20]
0x1800058cb  lea     r13, [rbx+r8]
0x1800058cf  sub     r9d, ecx
0x1800058d2  mov     [rsp+58h+arg_8], r9d
0x1800058d7  cmp     rbx, r13
0x1800058da  jnb     loc_180005A90
0x1800058e0  movzx   edx, byte ptr [rbx]; TestChar
0x1800058e3  mov     r8d, [rsi]
0x1800058e6  mov     ecx, edx
0x1800058e8  sub     ecx, 9
0x1800058eb  jz      loc_1800059B1
0x1800058f1  sub     ecx, 1
0x1800058f4  jz      loc_180005998
0x1800058fa  sub     ecx, 2
0x1800058fd  jz      loc_180005A2F
0x180005903  cmp     ecx, 1
0x180005906  jz      loc_180005A0B
0x18000590c  and     r8d, 0FFFFFFFEh
0x180005910  mov     [rsi], r8d
0x180005913  cmp     rdi, r14
0x180005916  jnb     loc_180005A60
0x18000591c  lea     r15, [rdi+1]
0x180005920  cmp     r15, r14
0x180005923  jb      short loc_18000593F
0x180005925  mov     ecx, [rsp+58h+CodePage]; CodePage
0x18000592c  call    cs:__imp_IsDBCSLeadByteEx
0x180005932  test    eax, eax
0x180005934  jnz     loc_1800059FE
0x18000593a  mov     r9d, [rsp+58h+arg_8]
0x18000593f  mov     al, [rbx]
0x180005941  inc     ebp
0x180005943  inc     rbx
0x180005946  mov     [rdi], al
0x180005948  mov     rdi, r15
0x18000594b  cmp     rbx, r13
0x18000594e  jnb     loc_180005A90
0x180005954  mov     dl, [rbx]; TestChar
0x180005956  mov     ecx, [rsp+58h+CodePage]; CodePage
0x18000595d  call    cs:__imp_IsDBCSLeadByteEx
0x180005963  mov     r9d, [rsp+58h+arg_8]
0x180005968  test    eax, eax
0x18000596a  jz      loc_1800058D7
0x180005970  lea     rcx, [rbx+1]
0x180005974  cmp     rcx, r13
0x180005977  jnb     loc_180005A03
0x18000597d  cmp     r15, r14
0x180005980  jnb     loc_1800058D7
0x180005986  mov     al, [rbx]
0x180005988  inc     rdi
0x18000598b  mov     [r15], al
0x18000598e  inc     ebp
0x180005990  mov     rbx, rcx
0x180005993  jmp     loc_1800058D7
0x180005998  inc     rbx
0x18000599b  test    r8b, 1
0x18000599f  jz      loc_180005A47
0x1800059a5  and     r8d, 0FFFFFFFEh
0x1800059a9  mov     [rsi], r8d
0x1800059ac  jmp     loc_1800058D7
0x1800059b1  and     r8d, 0FFFFFFFEh
0x1800059b5  mov     [rsi], r8d
0x1800059b8  cmp     rdi, r14
0x1800059bb  jnb     loc_180005A60
0x1800059c1  mov     ecx, [rsp+58h+arg_20]
0x1800059c8  lea     eax, [r9+rbp]
0x1800059cc  xor     edx, edx
0x1800059ce  inc     rbx
0x1800059d1  div     [rsp+58h+arg_20]
0x1800059d8  mov     eax, 0
0x1800059dd  sub     ecx, edx
0x1800059df  jz      short loc_1800059F7
0x1800059e1  cmp     rdi, r14
0x1800059e4  jnb     short loc_180005A5C
0x1800059e6  mov     byte ptr [rdi], 20h ; ' '
0x1800059e9  inc     eax
0x1800059eb  inc     rdi
0x1800059ee  cmp     eax, ecx
0x1800059f0  jb      short loc_1800059E1
0x1800059f2  cmp     rdi, r14
0x1800059f5  jnb     short loc_180005A5C
0x1800059f7  add     ebp, ecx
0x1800059f9  jmp     loc_1800058D7
0x1800059fe  mov     r8d, [rsi]
0x180005a01  jmp     short loc_180005A60
0x180005a03  or      dword ptr [rsi], 8
0x180005a06  jmp     loc_180005A92
0x180005a0b  inc     rbx
0x180005a0e  mov     dword ptr [r12], 0
0x180005a16  mov     eax, r8d
0x180005a19  and     eax, 100h
0x180005a1e  neg     eax
0x180005a20  sbb     ecx, ecx
0x180005a22  and     ecx, 21h
0x180005a25  add     ecx, 40h ; '@'
0x180005a28  or      ecx, r8d
0x180005a2b  mov     [rsi], ecx
0x180005a2d  jmp     short loc_180005A92
0x180005a2f  and     r8d, 0FFFFFFFEh
0x180005a33  mov     dword ptr [r12], 0
0x180005a3b  or      r8d, 10h
0x180005a3f  mov     [rsi], r8d
0x180005a42  inc     rbx
0x180005a45  jmp     short loc_180005A92
0x180005a47  test    r8b, r8b
0x180005a4a  jns     short loc_180005A56
0x180005a4c  mov     dword ptr [r12], 0
0x180005a54  jmp     short loc_180005A87
0x180005a56  or      r8d, 20h
0x180005a5a  jmp     short loc_180005A8B
0x180005a5c  or      r8d, 2
0x180005a60  mov     eax, [rsp+58h+arg_18]
0x180005a64  xor     edx, edx
0x180005a66  div     [rsp+58h+arg_20]
0x180005a6d  mov     eax, [r12]
0x180005a71  sub     eax, edx
0x180005a73  xor     edx, edx
0x180005a75  add     eax, [rsp+58h+arg_20]
0x180005a7c  div     [rsp+58h+arg_20]
0x180005a83  mov     [r12], edx
0x180005a87  or      r8d, 60h
0x180005a8b  mov     [rsi], r8d
0x180005a8e  jmp     short loc_180005A92
0x180005a90  xor     ebx, ebx
0x180005a92  mov     rax, [rsp+58h+arg_30]
0x180005a9a  mov     [rax], ebp
0x180005a9c  mov     rax, rbx
0x180005a9f  mov     rbx, [rsp+58h+arg_0]
0x180005aa4  add     rsp, 20h
0x180005aa8  pop     r15
0x180005aaa  pop     r14
0x180005aac  pop     r13
0x180005aae  pop     r12
0x180005ab0  pop     rdi
0x180005ab1  pop     rsi
0x180005ab2  pop     rbp
0x180005ab3  retn
```
