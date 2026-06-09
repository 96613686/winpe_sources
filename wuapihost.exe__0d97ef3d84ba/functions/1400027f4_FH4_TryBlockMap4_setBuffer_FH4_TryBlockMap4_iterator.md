# FH4::TryBlockMap4::setBuffer(FH4::TryBlockMap4::iterator)

- ea: `0x1400027f4`
- end: `0x1400029dd`
- name: `?setBuffer@TryBlockMap4@FH4@@QEAAXViterator@12@@Z`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002544`

## callees

- `0x1400027f4`

## pseudocode

```c
__int64 __fastcall FH4::TryBlockMap4::setBuffer(__int64 a1, __int64 a2)
{
  _BYTE *v2; // r8
  __int64 v4; // rcx
  _BYTE *v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  _BYTE *v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int *v11; // r8
  _BYTE *v12; // r10
  bool v13; // zf
  __int64 result; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  _BYTE *v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  _DWORD *v25; // r10
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // r8
  _BYTE *v30; // rdx
  __int64 v31; // rcx
  unsigned int *v32; // r10

  v2 = *(_BYTE **)(a1 + 16);
  *(_QWORD *)(a1 + 8) = v2;
  v4 = *v2 & 0xF;
  v5 = &v2[-*((char *)&FH4::s_negLengthTab + v4)];
  *(_DWORD *)(a1 + 24) = *((_DWORD *)v5 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v4);
  *(_QWORD *)(a1 + 8) = v5;
  v6 = *v5 & 0xF;
  v7 = *((char *)&FH4::s_negLengthTab + v6);
  LOBYTE(v6) = *((_BYTE *)&FH4::s_shiftTab + v6);
  v8 = &v5[-v7];
  LODWORD(v7) = *((_DWORD *)v8 - 1);
  *(_QWORD *)(a1 + 8) = v8;
  *(_DWORD *)(a1 + 28) = (unsigned int)v7 >> v6;
  v9 = *v8 & 0xF;
  v10 = *((char *)&FH4::s_negLengthTab + v9);
  LOBYTE(v9) = *((_BYTE *)&FH4::s_shiftTab + v9);
  v11 = (unsigned int *)&v8[-v10];
  LODWORD(v10) = *(v11 - 1);
  v12 = v11 + 1;
  *(_QWORD *)(a1 + 8) = v11;
  v13 = *(_DWORD *)(a2 + 8) == 0;
  *(_DWORD *)(a1 + 32) = (unsigned int)v10 >> v9;
  result = *v11;
  *(_QWORD *)(a1 + 8) = v11 + 1;
  *(_DWORD *)(a1 + 36) = result;
  if ( !v13 )
  {
    v15 = *(unsigned int *)(a2 + 8);
    do
    {
      v16 = *v12 & 0xF;
      v17 = *((char *)&FH4::s_negLengthTab + v16);
      LOBYTE(v16) = *((_BYTE *)&FH4::s_shiftTab + v16);
      v18 = *(_DWORD *)&v12[-v17 - 4];
      *(_QWORD *)(a1 + 8) = &v12[-v17];
      *(_DWORD *)(a1 + 24) = v18 >> v16;
      v19 = v12[-v17] & 0xF;
      v20 = *((char *)&FH4::s_negLengthTab + v19);
      LOBYTE(v19) = *((_BYTE *)&FH4::s_shiftTab + v19);
      v21 = &v12[-v20 - v17];
      v22 = *((_DWORD *)v21 - 1);
      *(_QWORD *)(a1 + 8) = v21;
      *(_DWORD *)(a1 + 28) = v22 >> v19;
      v23 = *v21 & 0xF;
      v24 = *((char *)&FH4::s_negLengthTab + v23);
      LOBYTE(v23) = *((_BYTE *)&FH4::s_shiftTab + v23);
      v25 = &v12[-v24 - v20 - v17];
      LODWORD(v24) = *(v25 - 1);
      *(_QWORD *)(a1 + 8) = v25;
      *(_DWORD *)(a1 + 32) = (unsigned int)v24 >> v23;
      LODWORD(v24) = *v25++;
      *(_QWORD *)(a1 + 8) = v25;
      *(_DWORD *)(a1 + 36) = v24;
      v26 = *(_BYTE *)v25 & 0xF;
      v27 = *((char *)&FH4::s_negLengthTab + v26);
      LOBYTE(v26) = *((_BYTE *)&FH4::s_shiftTab + v26);
      LODWORD(v24) = *(_DWORD *)((char *)v25 - v27 - 4);
      *(_QWORD *)(a1 + 8) = (char *)v25 - v27;
      *(_DWORD *)(a1 + 24) = (unsigned int)v24 >> v26;
      v28 = *((_BYTE *)v25 - v27) & 0xF;
      v29 = *((char *)&FH4::s_negLengthTab + v28);
      v30 = (char *)v25 - v29 - v27;
      LODWORD(v24) = *((_DWORD *)v30 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v28);
      *(_QWORD *)(a1 + 8) = v30;
      *(_DWORD *)(a1 + 28) = v24;
      v31 = *v30 & 0xF;
      v32 = (_DWORD *)((char *)v25 + -v29 - *((char *)&FH4::s_negLengthTab + v31) - v27);
      LODWORD(v24) = *(v32 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v31);
      *(_QWORD *)(a1 + 8) = v32;
      *(_DWORD *)(a1 + 32) = v24;
      result = *v32;
      v12 = v32 + 1;
      *(_QWORD *)(a1 + 8) = v12;
      *(_DWORD *)(a1 + 36) = result;
      --v15;
    }
    while ( v15 );
  }
  return result;
}

```

## disassembly

```asm
0x1400027f4  mov     [rsp+arg_0], rbx
0x1400027f9  mov     [rsp+arg_8], rdi
0x1400027fe  mov     r8, [rcx+10h]
0x140002802  lea     rdi, cs:140000000h
0x140002809  mov     [rcx+8], r8
0x14000280d  mov     r11, rcx
0x140002810  movzx   ecx, byte ptr [r8]
0x140002814  and     ecx, 0Fh
0x140002817  movsx   rax, byte ptr [rcx+rdi+7460h]
0x140002820  mov     cl, [rcx+rdi+7470h]
0x140002827  sub     r8, rax
0x14000282a  mov     eax, [r8-4]
0x14000282e  shr     eax, cl
0x140002830  mov     [r11+18h], eax
0x140002834  mov     [r11+8], r8
0x140002838  movzx   ecx, byte ptr [r8]
0x14000283c  and     ecx, 0Fh
0x14000283f  movsx   rax, byte ptr [rcx+rdi+7460h]
0x140002848  mov     cl, [rcx+rdi+7470h]
0x14000284f  sub     r8, rax
0x140002852  mov     eax, [r8-4]
0x140002856  mov     [r11+8], r8
0x14000285a  shr     eax, cl
0x14000285c  mov     [r11+1Ch], eax
0x140002860  movzx   ecx, byte ptr [r8]
0x140002864  and     ecx, 0Fh
0x140002867  movsx   rax, byte ptr [rcx+rdi+7460h]
0x140002870  mov     cl, [rcx+rdi+7470h]
0x140002877  sub     r8, rax
0x14000287a  mov     eax, [r8-4]
0x14000287e  lea     r10, [r8+4]
0x140002882  mov     [r11+8], r8
0x140002886  shr     eax, cl
0x140002888  cmp     dword ptr [rdx+8], 0
0x14000288c  mov     [r11+20h], eax
0x140002890  mov     eax, [r8]
0x140002893  mov     [r11+8], r10
0x140002897  mov     [r11+24h], eax
0x14000289b  jz      loc_1400029D2
0x1400028a1  mov     ebx, [rdx+8]
0x1400028a4  movzx   ecx, byte ptr [r10]
0x1400028a8  mov     rdx, r10
0x1400028ab  and     ecx, 0Fh
0x1400028ae  movsx   r9, byte ptr [rcx+rdi+7460h]
0x1400028b7  mov     cl, [rcx+rdi+7470h]
0x1400028be  sub     rdx, r9
0x1400028c1  mov     eax, [rdx-4]
0x1400028c4  mov     [r11+8], rdx
0x1400028c8  shr     eax, cl
0x1400028ca  mov     [r11+18h], eax
0x1400028ce  movzx   ecx, byte ptr [rdx]
0x1400028d1  mov     rdx, r10
0x1400028d4  and     ecx, 0Fh
0x1400028d7  movsx   r8, byte ptr [rcx+rdi+7460h]
0x1400028e0  mov     cl, [rcx+rdi+7470h]
0x1400028e7  sub     rdx, r8
0x1400028ea  sub     rdx, r9
0x1400028ed  mov     eax, [rdx-4]
0x1400028f0  mov     [r11+8], rdx
0x1400028f4  shr     eax, cl
0x1400028f6  mov     [r11+1Ch], eax
0x1400028fa  movzx   ecx, byte ptr [rdx]
0x1400028fd  and     ecx, 0Fh
0x140002900  movsx   rax, byte ptr [rcx+rdi+7460h]
0x140002909  mov     cl, [rcx+rdi+7470h]
0x140002910  sub     r10, rax
0x140002913  sub     r10, r8
0x140002916  sub     r10, r9
0x140002919  mov     eax, [r10-4]
0x14000291d  mov     [r11+8], r10
0x140002921  shr     eax, cl
0x140002923  mov     [r11+20h], eax
0x140002927  mov     eax, [r10]
0x14000292a  add     r10, 4
0x14000292e  mov     [r11+8], r10
0x140002932  mov     rdx, r10
0x140002935  mov     [r11+24h], eax
0x140002939  movzx   ecx, byte ptr [r10]
0x14000293d  and     ecx, 0Fh
0x140002940  movsx   r9, byte ptr [rcx+rdi+7460h]
0x140002949  mov     cl, [rcx+rdi+7470h]
0x140002950  sub     rdx, r9
0x140002953  mov     eax, [rdx-4]
0x140002956  mov     [r11+8], rdx
0x14000295a  shr     eax, cl
0x14000295c  mov     [r11+18h], eax
0x140002960  movzx   ecx, byte ptr [rdx]
0x140002963  mov     rdx, r10
0x140002966  and     ecx, 0Fh
0x140002969  movsx   r8, byte ptr [rcx+rdi+7460h]
0x140002972  mov     cl, [rcx+rdi+7470h]
0x140002979  sub     rdx, r8
0x14000297c  sub     rdx, r9
0x14000297f  mov     eax, [rdx-4]
0x140002982  shr     eax, cl
0x140002984  mov     [r11+8], rdx
0x140002988  mov     [r11+1Ch], eax
0x14000298c  movzx   ecx, byte ptr [rdx]
0x14000298f  and     ecx, 0Fh
0x140002992  movsx   rax, byte ptr [rcx+rdi+7460h]
0x14000299b  mov     cl, [rcx+rdi+7470h]
0x1400029a2  sub     r10, rax
0x1400029a5  sub     r10, r8
0x1400029a8  sub     r10, r9
0x1400029ab  mov     eax, [r10-4]
0x1400029af  shr     eax, cl
0x1400029b1  mov     [r11+8], r10
0x1400029b5  mov     [r11+20h], eax
0x1400029b9  mov     eax, [r10]
0x1400029bc  add     r10, 4
0x1400029c0  mov     [r11+8], r10
0x1400029c4  mov     [r11+24h], eax
0x1400029c8  sub     rbx, 1
0x1400029cc  jnz     loc_1400028A4
0x1400029d2  mov     rbx, [rsp+arg_0]
0x1400029d7  mov     rdi, [rsp+arg_8]
0x1400029dc  retn
```
