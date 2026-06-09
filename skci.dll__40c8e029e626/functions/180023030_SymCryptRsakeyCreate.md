# SymCryptRsakeyCreate

- ea: `0x180023030`
- end: `0x1800231bd`
- name: `SymCryptRsakeyCreate`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002859c`
- `0x18004f740`

## callees

- `0x180009780`
- `0x180023030`
- `0x180023ce0`
- `0x18002bc28`
- `0x18002bd98`
- `0x18002c2e0`

## pseudocode

```c
__int64 __fastcall SymCryptRsakeyCreate(__int64 a1, unsigned __int64 a2, _DWORD *a3)
{
  __int64 v6; // r14
  unsigned int v7; // edi
  unsigned int v8; // eax
  unsigned int v9; // r8d
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // r9
  __int64 v14; // r8
  int v15; // r10d
  unsigned int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned int v19; // r8d
  unsigned int v20; // eax
  __int64 i; // r8
  __int64 v22; // rdx
  int v23; // r8d
  __int64 v24; // r9
  __int64 v25; // r8
  unsigned int v26; // eax
  int v27; // r8d
  __int64 v28; // r9

  v6 = 0;
  v7 = SymCryptSizeofRsakeyFromParams(a3);
  if ( a2 >= v7 && (unsigned int)(a3[1] - 256) <= 0xFF00 && a3[3] == 1 && (a3[2] & 0xFFFFFFFD) == 0 )
  {
    v6 = a1;
    SymCryptWipeAsm(a1, a2);
    v8 = a3[1];
    *(_DWORD *)(a1 + 4) = v7;
    *(_BYTE *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 12) = v8;
    if ( v8 )
    {
      if ( v8 <= 0x100000 )
        v9 = (v8 >> 9) + (((v8 & 0x1FF) + 511) >> 9);
      else
        v9 = 0;
    }
    else
    {
      v9 = 1;
    }
    *(_DWORD *)(a1 + 28) = a3[2];
    *(_DWORD *)(a1 + 24) = a3[3];
    *(_DWORD *)(a1 + 20) = v9;
    v10 = (unsigned int)SymCryptFdefSizeofModulusFromDigits(v9);
    v11 = SymCryptFdefModulusCreate(a1 + 192, v10);
    v12 = 0;
    *(_QWORD *)(a1 + 120) = v11;
    v13 = v10 + a1 + 192;
    if ( *(_DWORD *)(a1 + 28) )
    {
      do
      {
        *(_QWORD *)(a1 + 8 * v12 + 64) = v13;
        v14 = (unsigned int)SymCryptFdefSizeofModulusFromDigits(*(unsigned int *)(a1 + 20));
        v12 = (unsigned int)(v15 + 1);
        v16 = *(_DWORD *)(a1 + 28);
        v13 = v14 + v17;
      }
      while ( (unsigned int)v12 < v16 );
      if ( v16 )
      {
        v18 = 0;
        v19 = ((a3[1] >> 9) + (((a3[1] & 0x1FFu) + 511) >> 9)) << 6;
        do
        {
          *(_QWORD *)(a1 + 8 * v18 + 80) = v13;
          v13 += v19;
          v18 = (unsigned int)(v18 + 1);
        }
        while ( (unsigned int)v18 < *(_DWORD *)(a1 + 28) );
      }
    }
    v20 = *(_DWORD *)(a1 + 24);
    for ( i = 0; (unsigned int)i < v20; v13 = v22 + v24 )
    {
      *(_QWORD *)(a1 + 8 * i + 96) = v13;
      v22 = (unsigned int)SymCryptFdefSizeofIntFromDigits(*(unsigned int *)(a1 + 20));
      i = (unsigned int)(v23 + 1);
      v20 = *(_DWORD *)(a1 + 24);
    }
    v25 = 0;
    if ( *(_DWORD *)(a1 + 28) * v20 )
    {
      do
      {
        *(_QWORD *)(a1 + 8 * v25 + 104) = v13;
        v26 = SymCryptFdefSizeofIntFromDigits(*(unsigned int *)(a1 + 20));
        v25 = (unsigned int)(v27 + 1);
        v13 = v26 + v28;
      }
      while ( (unsigned int)v25 < *(_DWORD *)(a1 + 24) * *(_DWORD *)(a1 + 28) );
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180023030  push    rbx
0x180023032  push    rbp
0x180023033  push    rsi
0x180023034  push    rdi
0x180023035  push    r12
0x180023037  push    r14
0x180023039  sub     rsp, 28h
0x18002303d  mov     rsi, rcx
0x180023040  mov     rbp, r8
0x180023043  mov     rcx, r8
0x180023046  mov     rbx, rdx
0x180023049  xor     r14d, r14d
0x18002304c  call    SymCryptSizeofRsakeyFromParams
0x180023051  mov     edi, eax
0x180023053  cmp     rbx, rdi
0x180023056  jb      loc_1800231AC
0x18002305c  mov     eax, [rbp+4]
0x18002305f  sub     eax, 100h
0x180023064  cmp     eax, 0FF00h
0x180023069  ja      loc_1800231AC
0x18002306f  cmp     dword ptr [rbp+0Ch], 1
0x180023073  jnz     loc_1800231AC
0x180023079  test    dword ptr [rbp+8], 0FFFFFFFDh
0x180023080  jnz     loc_1800231AC
0x180023086  mov     rdx, rbx
0x180023089  mov     rcx, rsi
0x18002308c  mov     r14, rsi
0x18002308f  call    SymCryptWipeAsm
0x180023094  mov     eax, [rbp+4]
0x180023097  mov     r12d, 1FFh
0x18002309d  mov     [rsi+4], edi
0x1800230a0  mov     byte ptr [rsi+8], 0
0x1800230a4  mov     [rsi+0Ch], eax
0x1800230a7  test    eax, eax
0x1800230a9  jnz     short loc_1800230B1
0x1800230ab  lea     r8d, [rax+1]
0x1800230af  jmp     short loc_1800230D0
0x1800230b1  cmp     eax, 100000h
0x1800230b6  jbe     short loc_1800230BD
0x1800230b8  xor     r8d, r8d
0x1800230bb  jmp     short loc_1800230D0
0x1800230bd  mov     r8d, eax
0x1800230c0  shr     eax, 9
0x1800230c3  and     r8d, r12d
0x1800230c6  add     r8d, r12d
0x1800230c9  shr     r8d, 9
0x1800230cd  add     r8d, eax
0x1800230d0  mov     eax, [rbp+8]
0x1800230d3  lea     rdi, [rsi+0C0h]
0x1800230da  mov     [rsi+1Ch], eax
0x1800230dd  mov     ecx, r8d
0x1800230e0  mov     eax, [rbp+0Ch]
0x1800230e3  mov     [rsi+18h], eax
0x1800230e6  mov     [rsi+14h], r8d
0x1800230ea  call    SymCryptFdefSizeofModulusFromDigits
0x1800230ef  mov     edx, eax
0x1800230f1  mov     rcx, rdi
0x1800230f4  mov     ebx, eax
0x1800230f6  call    SymCryptFdefModulusCreate
0x1800230fb  xor     r10d, r10d
0x1800230fe  mov     [rsi+78h], rax
0x180023102  lea     r9, [rbx+rdi]
0x180023106  cmp     [rsi+1Ch], r10d
0x18002310a  jbe     short loc_180023159
0x18002310c  mov     [rsi+r10*8+40h], r9
0x180023111  mov     ecx, [rsi+14h]
0x180023114  call    SymCryptFdefSizeofModulusFromDigits
0x180023119  mov     r8d, eax
0x18002311c  inc     r10d
0x18002311f  mov     eax, [rsi+1Ch]
0x180023122  add     r9, r8
0x180023125  cmp     r10d, eax
0x180023128  jb      short loc_18002310C
0x18002312a  test    eax, eax
0x18002312c  jz      short loc_180023159
0x18002312e  mov     eax, [rbp+4]
0x180023131  xor     edx, edx
0x180023133  mov     r8d, eax
0x180023136  shr     eax, 9
0x180023139  and     r8d, r12d
0x18002313c  add     r8d, r12d
0x18002313f  shr     r8d, 9
0x180023143  add     r8d, eax
0x180023146  shl     r8d, 6
0x18002314a  mov     [rsi+rdx*8+50h], r9
0x18002314f  add     r9, r8
0x180023152  inc     edx
0x180023154  cmp     edx, [rsi+1Ch]
0x180023157  jb      short loc_18002314A
0x180023159  mov     eax, [rsi+18h]
0x18002315c  xor     r8d, r8d
0x18002315f  test    eax, eax
0x180023161  jz      short loc_180023180
0x180023163  mov     [rsi+r8*8+60h], r9
0x180023168  mov     ecx, [rsi+14h]
0x18002316b  call    SymCryptFdefSizeofIntFromDigits
0x180023170  mov     edx, eax
0x180023172  inc     r8d
0x180023175  mov     eax, [rsi+18h]
0x180023178  add     r9, rdx
0x18002317b  cmp     r8d, eax
0x18002317e  jb      short loc_180023163
0x180023180  imul    eax, [rsi+1Ch]
0x180023184  xor     r8d, r8d
0x180023187  test    eax, eax
0x180023189  jz      short loc_1800231AC
0x18002318b  mov     [rsi+r8*8+68h], r9
0x180023190  mov     ecx, [rsi+14h]
0x180023193  call    SymCryptFdefSizeofIntFromDigits
0x180023198  mov     ecx, [rsi+1Ch]
0x18002319b  inc     r8d
0x18002319e  imul    ecx, [rsi+18h]
0x1800231a2  mov     edx, eax
0x1800231a4  add     r9, rdx
0x1800231a7  cmp     r8d, ecx
0x1800231aa  jb      short loc_18002318B
0x1800231ac  mov     rax, r14
0x1800231af  add     rsp, 28h
0x1800231b3  pop     r14
0x1800231b5  pop     r12
0x1800231b7  pop     rdi
0x1800231b8  pop     rsi
0x1800231b9  pop     rbp
0x1800231ba  pop     rbx
0x1800231bb  retn
```
