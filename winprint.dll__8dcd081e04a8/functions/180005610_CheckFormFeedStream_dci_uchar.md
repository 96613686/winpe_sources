# CheckFormFeedStream(dci *,uchar)

- ea: `0x180005610`
- end: `0x180005827`
- name: `?CheckFormFeedStream@@YAXPEAUdci@@E@Z`
- size: `535`
- prototype: `void __fastcall(struct dci *, unsigned __int8)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001590`

## callees

- `0x180005610`

## pseudocode

```c
void __fastcall CheckFormFeedStream(struct dci *a1, unsigned __int8 a2)
{
  int v3; // r9d
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  bool v9; // zf
  struct EscapeSequence near **v10; // rdx
  unsigned int v11; // esi
  int v12; // r11d
  unsigned int v13; // r10d
  int v14; // ebx
  int v15; // ecx
  unsigned int v16; // eax
  unsigned int v17; // eax
  struct EscapeSequence near *v18; // r11
  struct EscapeSequence near *v19; // rcx
  int v20; // edi
  __int64 v21; // r9
  struct EscapeSequence near **v22; // r9
  struct EscapeSequence near *v23; // r10
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx

  v3 = a2;
  v4 = *(_DWORD *)a1;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( v8 == 1 )
            {
              *((_DWORD *)a1 + 1) += a2 << 8;
              *(_DWORD *)a1 = *((_DWORD *)a1 + 1) != 0 ? 2 : 0;
            }
          }
          else
          {
            *((_DWORD *)a1 + 1) = a2;
            *(_DWORD *)a1 = 5;
          }
          return;
        }
        v9 = a2 == *((char *)a1 + 24);
      }
      else
      {
        v9 = (*((_DWORD *)a1 + 1))-- == 1;
      }
      if ( !v9 )
        return;
LABEL_12:
      *(_DWORD *)a1 = 0;
      return;
    }
    v10 = (struct EscapeSequence near **)*((_QWORD *)a1 + 1);
    if ( v10 )
    {
      v14 = v3;
    }
    else
    {
      v11 = 0;
      v12 = 52;
      v13 = 26;
      while ( 1 )
      {
        v14 = v3;
        v10 = &EscapeStrings + 2 * v13;
        v15 = *(char *)*v10;
        if ( v3 == v15 )
          break;
        v16 = v13;
        if ( v3 - v15 <= 0 )
        {
          v16 = v11;
          v12 = v13;
        }
        v11 = v16;
        v17 = v13;
        v13 = (v12 + v11) >> 1;
        if ( v17 == v13 )
          goto LABEL_12;
      }
      *((_QWORD *)a1 + 1) = v10;
      *((_QWORD *)a1 + 2) = *v10;
    }
    v18 = (struct EscapeSequence near *)*((_QWORD *)a1 + 2);
    LODWORD(v19) = *(char *)v18;
    v20 = v14 - (_DWORD)v19;
    while ( v14 != (char)v19 )
    {
      v21 = 2;
      if ( v20 <= 0 )
        v21 = 0x1FFFFFFFFFFFFFFELL;
      v22 = &v10[v21];
      if ( v22 < &EscapeStrings || v22 > (struct EscapeSequence near **)&off_18000D330 )
        goto LABEL_12;
      _mm_lfence();
      v23 = *v10;
      v19 = *v22;
      while ( v23 < v18 )
      {
        if ( *(_BYTE *)v19 != *(_BYTE *)v23 )
          goto LABEL_12;
        v23 = (struct EscapeSequence near *)((char *)v23 + 1);
        v19 = (struct EscapeSequence near *)((char *)v19 + 1);
      }
      *((_QWORD *)a1 + 1) = v22;
      v18 = v19;
      *((_QWORD *)a1 + 2) = v19;
      v10 = v22;
      LOBYTE(v19) = *(_BYTE *)v19;
    }
    *((_QWORD *)a1 + 2) = (char *)v18 + 1;
    if ( !*((_BYTE *)v18 + 1) )
    {
      v24 = *((_DWORD *)v10 + 2);
      if ( !v24 )
        goto LABEL_12;
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            v28 = v27 - 1;
            if ( v28 )
            {
              if ( v28 == 1 )
              {
                *(_DWORD *)a1 = 0;
                *((_DWORD *)a1 + 7) = 3;
              }
            }
            else
            {
              *(_DWORD *)a1 = 0;
              *((_DWORD *)a1 + 7) = 2;
            }
          }
          else
          {
            *(_DWORD *)a1 = 4;
          }
        }
        else
        {
          *(_DWORD *)a1 = 2;
          *((_DWORD *)a1 + 1) = *((_DWORD *)v10 + 3);
        }
      }
      else
      {
        *(_DWORD *)a1 = 3;
        *((_BYTE *)a1 + 24) = *((_BYTE *)v10 + 12);
      }
    }
  }
  else if ( a2 < 0x20u )
  {
    if ( a2 == 12 )
    {
      *((_DWORD *)a1 + 7) = 1;
    }
    else if ( a2 == 27 )
    {
      *(_DWORD *)a1 = 1;
      *((_QWORD *)a1 + 1) = 0;
    }
  }
  else
  {
    *((_DWORD *)a1 + 7) = 0;
  }
}

```

## disassembly

```asm
0x180005610  push    rbx
0x180005612  push    rsi
0x180005613  push    rdi
0x180005614  push    r14
0x180005616  mov     r8, rcx
0x180005619  movzx   r9d, dl
0x18000561d  mov     ecx, [rcx]
0x18000561f  test    ecx, ecx
0x180005621  jz      loc_1800057EC
0x180005627  sub     ecx, 1
0x18000562a  jz      short loc_180005692
0x18000562c  sub     ecx, 1
0x18000562f  jz      short loc_18000567B
0x180005631  sub     ecx, 1
0x180005634  jz      short loc_180005671
0x180005636  sub     ecx, 1
0x180005639  jz      short loc_180005661
0x18000563b  cmp     ecx, 1
0x18000563e  jnz     loc_180005821
0x180005644  mov     eax, r9d
0x180005647  shl     eax, 8
0x18000564a  add     [r8+4], eax
0x18000564e  mov     eax, [r8+4]
0x180005652  neg     eax
0x180005654  sbb     ecx, ecx
0x180005656  and     ecx, 2
0x180005659  mov     [r8], ecx
0x18000565c  jmp     loc_180005821
0x180005661  mov     [r8+4], r9d
0x180005665  mov     dword ptr [r8], 5
0x18000566c  jmp     loc_180005821
0x180005671  movsx   eax, byte ptr [r8+18h]
0x180005676  cmp     r9d, eax
0x180005679  jmp     short loc_180005680
0x18000567b  add     dword ptr [r8+4], 0FFFFFFFFh
0x180005680  jnz     loc_180005821
0x180005686  mov     dword ptr [r8], 0
0x18000568d  jmp     loc_180005821
0x180005692  mov     rdx, [r8+8]
0x180005696  lea     r14, ?EscapeStrings@@3PAUEscapeSequence@@A; EscapeSequence near * EscapeStrings
0x18000569d  test    rdx, rdx
0x1800056a0  jnz     short loc_1800056F2
0x1800056a2  xor     esi, esi
0x1800056a4  lea     r11d, [rdx+34h]
0x1800056a8  lea     r10d, [rdx+1Ah]
0x1800056ac  mov     edx, r10d
0x1800056af  mov     edi, r9d
0x1800056b2  shl     rdx, 4
0x1800056b6  mov     ebx, r9d
0x1800056b9  add     rdx, r14
0x1800056bc  mov     rax, [rdx]
0x1800056bf  movsx   ecx, byte ptr [rax]
0x1800056c2  sub     edi, ecx
0x1800056c4  jz      short loc_1800056E5
0x1800056c6  test    edi, edi
0x1800056c8  mov     eax, r10d
0x1800056cb  cmovle  eax, esi
0x1800056ce  cmovle  r11d, r10d
0x1800056d2  mov     esi, eax
0x1800056d4  mov     eax, r10d
0x1800056d7  lea     r10d, [r11+rsi]
0x1800056db  shr     r10d, 1
0x1800056de  cmp     eax, r10d
0x1800056e1  jnz     short loc_1800056AC
0x1800056e3  jmp     short loc_180005686
0x1800056e5  mov     [r8+8], rdx
0x1800056e9  mov     rax, [rdx]
0x1800056ec  mov     [r8+10h], rax
0x1800056f0  jmp     short loc_1800056F5
0x1800056f2  mov     ebx, r9d
0x1800056f5  mov     r11, [r8+10h]
0x1800056f9  mov     edi, ebx
0x1800056fb  movsx   ecx, byte ptr [r11]
0x1800056ff  sub     edi, ecx
0x180005701  movsx   ecx, cl
0x180005704  cmp     ebx, ecx
0x180005706  jz      short loc_180005768
0x180005708  mov     rcx, 0FFFFFFFFFFFFFFF0h
0x18000570f  test    edi, edi
0x180005711  lea     r9d, [rcx+20h]
0x180005715  cmovle  r9, rcx
0x180005719  add     r9, rdx
0x18000571c  cmp     r9, r14
0x18000571f  jb      loc_180005686
0x180005725  lea     rax, off_18000D330; "o"
0x18000572c  cmp     r9, rax
0x18000572f  ja      loc_180005686
0x180005735  lfence
0x180005738  mov     r10, [rdx]
0x18000573b  mov     rcx, [r9]
0x18000573e  cmp     r10, r11
0x180005741  jnb     short loc_180005756
0x180005743  mov     al, [r10]
0x180005746  cmp     [rcx], al
0x180005748  jnz     loc_180005686
0x18000574e  inc     r10
0x180005751  inc     rcx
0x180005754  jmp     short loc_18000573E
0x180005756  mov     [r8+8], r9
0x18000575a  mov     r11, rcx
0x18000575d  mov     [r8+10h], rcx
0x180005761  mov     rdx, r9
0x180005764  mov     cl, [rcx]
0x180005766  jmp     short loc_180005701
0x180005768  lea     rax, [r11+1]
0x18000576c  mov     [r8+10h], rax
0x180005770  cmp     byte ptr [rax], 0
0x180005773  jnz     loc_180005821
0x180005779  mov     ecx, [rdx+8]
0x18000577c  test    ecx, ecx
0x18000577e  jz      loc_180005686
0x180005784  sub     ecx, 1
0x180005787  jz      short loc_1800057DC
0x180005789  sub     ecx, 1
0x18000578c  jz      short loc_1800057CC
0x18000578e  sub     ecx, 1
0x180005791  jz      short loc_1800057C3
0x180005793  sub     ecx, 1
0x180005796  jz      short loc_1800057B2
0x180005798  cmp     ecx, 1
0x18000579b  jnz     loc_180005821
0x1800057a1  mov     dword ptr [r8], 0
0x1800057a8  mov     dword ptr [r8+1Ch], 3
0x1800057b0  jmp     short loc_180005821
0x1800057b2  mov     dword ptr [r8], 0
0x1800057b9  mov     dword ptr [r8+1Ch], 2
0x1800057c1  jmp     short loc_180005821
0x1800057c3  mov     dword ptr [r8], 4
0x1800057ca  jmp     short loc_180005821
0x1800057cc  mov     dword ptr [r8], 2
0x1800057d3  mov     eax, [rdx+0Ch]
0x1800057d6  mov     [r8+4], eax
0x1800057da  jmp     short loc_180005821
0x1800057dc  mov     dword ptr [r8], 3
0x1800057e3  mov     al, [rdx+0Ch]
0x1800057e6  mov     [r8+18h], al
0x1800057ea  jmp     short loc_180005821
0x1800057ec  cmp     r9b, 20h ; ' '
0x1800057f0  jb      short loc_1800057FC
0x1800057f2  mov     dword ptr [r8+1Ch], 0
0x1800057fa  jmp     short loc_180005821
0x1800057fc  cmp     r9b, 0Ch
0x180005800  jnz     short loc_18000580C
0x180005802  mov     dword ptr [r8+1Ch], 1
0x18000580a  jmp     short loc_180005821
0x18000580c  cmp     r9b, 1Bh
0x180005810  jnz     short loc_180005821
0x180005812  mov     dword ptr [r8], 1
0x180005819  mov     qword ptr [r8+8], 0
0x180005821  pop     r14
0x180005823  pop     rdi
0x180005824  pop     rsi
0x180005825  pop     rbx
0x180005826  retn
```
