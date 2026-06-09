# SymCryptEcurveValidateAndComputeSizes

- ea: `0x180024744`
- end: `0x180024975`
- name: `SymCryptEcurveValidateAndComputeSizes`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180023d70`

## callees

- `0x180024744`
- `0x180029ca8`
- `0x18002bd98`
- `0x18002c2e0`

## pseudocode

```c
char __fastcall SymCryptEcurveValidateAndComputeSizes(_DWORD *a1, unsigned int *a2)
{
  unsigned int v2; // r9d
  char v3; // r14
  unsigned int v6; // ecx
  unsigned int v7; // edx
  unsigned int v8; // ebp
  unsigned int v9; // r9d
  unsigned int v10; // r8d
  unsigned int v11; // r10d
  unsigned int v12; // eax
  unsigned int v13; // r11d
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // r11d
  unsigned int v17; // r15d
  unsigned int v18; // eax
  unsigned int v19; // r8d
  unsigned int v20; // r12d
  unsigned int v21; // eax
  int v22; // r8d
  unsigned int v23; // r9d
  unsigned int v24; // r13d
  unsigned int v25; // edi
  int v26; // eax
  int v27; // r10d
  int v28; // edx
  int v29; // r8d
  unsigned int v30; // esi
  int v31; // eax
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // r9
  unsigned int v34; // r10d
  unsigned int v35; // r11d
  int v36; // eax
  unsigned int v37; // ecx
  unsigned int v38; // edx
  unsigned int v39; // r10d
  unsigned int v40; // eax

  v2 = a1[3];
  v3 = 0;
  if ( v2 <= 0x80 )
  {
    v6 = a1[4];
    if ( v6 <= 0x81 )
    {
      v7 = a1[5];
      v8 = 2;
      if ( v7 <= 2 && a1[6] <= 0x100u )
      {
        v9 = 8 * v2;
        v10 = 1;
        if ( v9 )
        {
          if ( v9 <= 0x100000 )
            v11 = (v9 >> 9) + (((v9 & 0x1FF) + 511) >> 9);
          else
            v11 = 0;
        }
        else
        {
          v11 = 1;
        }
        v12 = 8 * v6;
        *a2 = v11;
        if ( 8 * v6 )
        {
          if ( v12 <= 0x100000 )
            v13 = (v12 >> 9) + (((v12 & 0x1FF) + 511) >> 9);
          else
            v13 = 0;
        }
        else
        {
          v13 = 1;
        }
        v14 = 8 * v7;
        a2[1] = v13;
        if ( 8 * v7 )
        {
          if ( v14 <= 0x100000 )
            v10 = (v14 >> 9) + (((v14 & 0x1FF) + 511) >> 9);
          else
            v10 = 0;
        }
        a2[2] = v10;
        v15 = SymCryptFdefSizeofModulusFromDigits(v11);
        a2[4] = v15;
        v17 = v15;
        v18 = SymCryptFdefSizeofModulusFromDigits(v16);
        a2[7] = v18;
        v20 = v18;
        v21 = SymCryptFdefSizeofIntFromDigits(v19);
        v22 = a1[1];
        v24 = v21;
        a2[8] = v21;
        v25 = ((v23 >> 9) + (((v23 & 0x1FF) + 511) >> 9)) << 6;
        a2[5] = v25;
        switch ( v22 )
        {
          case 1:
            a2[10] = 67;
            v8 = 3;
            break;
          case 2:
            a2[10] = 84;
            v8 = 4;
            break;
          case 3:
            a2[10] = 98;
            break;
          default:
            return v3;
        }
        v26 = SymCryptSizeofEcpointEx(v25, v8);
        a2[6] = v26;
        v28 = v26;
        if ( (unsigned int)(v29 - 1) <= 1 )
          v28 = 16 * v26;
        a2[3] = v17 + v20 + v24 + 2 * v25 + 672 + v28;
        v30 = (v27 << 8) + 64;
        v31 = SymCryptSizeofEcpointEx(v25, 4);
        if ( v33 <= v32 )
          LODWORD(v33) = v32;
        v36 = v33 + v31;
        if ( v34 <= v35 )
          v34 = v35;
        v37 = v36 + 8 * v25;
        v38 = (v34 << 8) + 192;
        v39 = 16 * v34;
        v40 = v39;
        if ( v39 <= v38 )
          v40 = v38;
        if ( v37 <= v40 )
        {
          v37 = v38;
          if ( v39 > v38 )
            v37 = v39;
        }
        v3 = 1;
        if ( v37 <= v30 )
          v37 = v30;
        a2[9] = v37;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180024744  push    rbx
0x180024746  push    rbp
0x180024747  push    rsi
0x180024748  push    rdi
0x180024749  push    r12
0x18002474b  push    r13
0x18002474d  push    r14
0x18002474f  push    r15
0x180024751  sub     rsp, 28h
0x180024755  mov     r9d, [rcx+0Ch]
0x180024759  xor     r14b, r14b
0x18002475c  mov     rbx, rdx
0x18002475f  mov     rsi, rcx
0x180024762  cmp     r9d, 80h
0x180024769  ja      loc_180024960
0x18002476f  mov     ecx, [rcx+10h]
0x180024772  cmp     ecx, 81h
0x180024778  ja      loc_180024960
0x18002477e  mov     edx, [rsi+14h]
0x180024781  mov     ebp, 2
0x180024786  cmp     edx, ebp
0x180024788  ja      loc_180024960
0x18002478e  cmp     dword ptr [rsi+18h], 100h
0x180024795  ja      loc_180024960
0x18002479b  shl     r9d, 3
0x18002479f  lea     r8d, [rbp-1]
0x1800247a3  mov     edi, 1FFh
0x1800247a8  mov     r15d, 100000h
0x1800247ae  test    r9d, r9d
0x1800247b1  jnz     short loc_1800247B8
0x1800247b3  mov     r10d, r8d
0x1800247b6  jmp     short loc_1800247D8
0x1800247b8  cmp     r9d, r15d
0x1800247bb  jbe     short loc_1800247C2
0x1800247bd  xor     r10d, r10d
0x1800247c0  jmp     short loc_1800247D8
0x1800247c2  mov     r10d, r9d
0x1800247c5  mov     eax, r9d
0x1800247c8  and     r10d, edi
0x1800247cb  shr     eax, 9
0x1800247ce  add     r10d, edi
0x1800247d1  shr     r10d, 9
0x1800247d5  add     r10d, eax
0x1800247d8  lea     eax, ds:0[rcx*8]
0x1800247df  mov     [rbx], r10d
0x1800247e2  test    eax, eax
0x1800247e4  jnz     short loc_1800247EB
0x1800247e6  mov     r11d, r8d
0x1800247e9  jmp     short loc_180024808
0x1800247eb  cmp     eax, r15d
0x1800247ee  jbe     short loc_1800247F5
0x1800247f0  xor     r11d, r11d
0x1800247f3  jmp     short loc_180024808
0x1800247f5  mov     r11d, eax
0x1800247f8  shr     eax, 9
0x1800247fb  and     r11d, edi
0x1800247fe  add     r11d, edi
0x180024801  shr     r11d, 9
0x180024805  add     r11d, eax
0x180024808  lea     eax, ds:0[rdx*8]
0x18002480f  mov     [rbx+4], r11d
0x180024813  test    eax, eax
0x180024815  jz      short loc_180024834
0x180024817  cmp     eax, r15d
0x18002481a  jbe     short loc_180024821
0x18002481c  xor     r8d, r8d
0x18002481f  jmp     short loc_180024834
0x180024821  mov     r8d, eax
0x180024824  shr     eax, 9
0x180024827  and     r8d, edi
0x18002482a  add     r8d, edi
0x18002482d  shr     r8d, 9
0x180024831  add     r8d, eax
0x180024834  mov     ecx, r10d
0x180024837  mov     [rbx+8], r8d
0x18002483b  call    SymCryptFdefSizeofModulusFromDigits
0x180024840  mov     ecx, r11d
0x180024843  mov     [rbx+10h], eax
0x180024846  mov     r15d, eax
0x180024849  call    SymCryptFdefSizeofModulusFromDigits
0x18002484e  mov     ecx, r8d
0x180024851  mov     [rbx+1Ch], eax
0x180024854  mov     r12d, eax
0x180024857  call    SymCryptFdefSizeofIntFromDigits
0x18002485c  mov     r8d, [rsi+4]
0x180024860  mov     edi, r9d
0x180024863  shr     r9d, 9
0x180024867  mov     r13d, eax
0x18002486a  mov     [rbx+20h], eax
0x18002486d  mov     ecx, r8d
0x180024870  mov     eax, 1FFh
0x180024875  and     edi, eax
0x180024877  add     edi, eax
0x180024879  shr     edi, 9
0x18002487c  add     edi, r9d
0x18002487f  shl     edi, 6
0x180024882  mov     [rbx+14h], edi
0x180024885  sub     ecx, 1
0x180024888  jz      short loc_1800248AF
0x18002488a  sub     ecx, 1
0x18002488d  jz      short loc_1800248A1
0x18002488f  cmp     ecx, 1
0x180024892  jnz     loc_180024960
0x180024898  mov     dword ptr [rbx+28h], 62h ; 'b'
0x18002489f  jmp     short loc_1800248BB
0x1800248a1  mov     dword ptr [rbx+28h], 54h ; 'T'
0x1800248a8  mov     ebp, 4
0x1800248ad  jmp     short loc_1800248BB
0x1800248af  mov     dword ptr [rbx+28h], 43h ; 'C'
0x1800248b6  mov     ebp, 3
0x1800248bb  mov     edx, ebp
0x1800248bd  mov     ecx, edi
0x1800248bf  call    SymCryptSizeofEcpointEx
0x1800248c4  lea     ecx, ds:2A0h[rdi*2]
0x1800248cb  mov     [rbx+18h], eax
0x1800248ce  add     ecx, r13d
0x1800248d1  mov     edx, eax
0x1800248d3  add     ecx, r12d
0x1800248d6  lea     eax, [r8-1]
0x1800248da  add     ecx, r15d
0x1800248dd  cmp     eax, 1
0x1800248e0  ja      short loc_1800248E5
0x1800248e2  shl     edx, 4
0x1800248e5  lea     eax, [rcx+rdx]
0x1800248e8  mov     ecx, r10d
0x1800248eb  mov     [rbx+0Ch], eax
0x1800248ee  mov     edx, 4
0x1800248f3  shl     ecx, 6
0x1800248f6  mov     eax, r10d
0x1800248f9  shl     eax, 8
0x1800248fc  add     rcx, 40h ; '@'
0x180024900  mov     r8d, eax
0x180024903  lea     esi, [rax+40h]
0x180024906  lea     rax, [rsi+rcx]
0x18002490a  mov     r9d, esi
0x18002490d  lea     rax, [rax+rcx*2]
0x180024911  mov     ecx, edi
0x180024913  add     r8, rax
0x180024916  call    SymCryptSizeofEcpointEx
0x18002491b  cmp     r9, r8
0x18002491e  cmovbe  r9d, r8d
0x180024922  add     eax, r9d
0x180024925  cmp     r10d, r11d
0x180024928  cmovbe  r10d, r11d
0x18002492c  lea     ecx, [rax+rdi*8]
0x18002492f  mov     edx, r10d
0x180024932  shl     edx, 8
0x180024935  add     edx, 0C0h
0x18002493b  shl     r10d, 4
0x18002493f  cmp     r10d, edx
0x180024942  mov     eax, r10d
0x180024945  cmovbe  eax, edx
0x180024948  cmp     ecx, eax
0x18002494a  ja      short loc_180024955
0x18002494c  cmp     r10d, edx
0x18002494f  mov     ecx, edx
0x180024951  cmova   ecx, r10d
0x180024955  cmp     ecx, esi
0x180024957  mov     r14b, 1
0x18002495a  cmovbe  ecx, esi
0x18002495d  mov     [rbx+24h], ecx
0x180024960  mov     al, r14b
0x180024963  add     rsp, 28h
0x180024967  pop     r15
0x180024969  pop     r14
0x18002496b  pop     r13
0x18002496d  pop     r12
0x18002496f  pop     rdi
0x180024970  pop     rsi
0x180024971  pop     rbp
0x180024972  pop     rbx
0x180024973  retn
```
