# SymCryptRsakeyCreateAllObjects

- ea: `0x1800231c4`
- end: `0x180023318`
- name: `SymCryptRsakeyCreateAllObjects`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180023390`

## callees

- `0x1800231c4`
- `0x18002bc28`
- `0x18002bd98`
- `0x18002c2e0`

## pseudocode

```c
__int64 __fastcall SymCryptRsakeyCreateAllObjects(unsigned int *a1)
{
  __int64 v1; // rsi
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  _DWORD *v11; // r8
  int v12; // r9d
  int v13; // r11d
  __int64 result; // rax
  __int64 i; // r8
  int v16; // eax
  _DWORD *v17; // rdx
  __int64 v18; // r8
  int v19; // r10d
  int v20; // r11d

  v1 = 0;
  if ( a1[7] )
  {
    do
    {
      v3 = SymCryptFdefSizeofModulusFromDigits(a1[v1 + 10]);
      *(_QWORD *)&a1[2 * v1 + 32] = SymCryptFdefModulusCreate(*(_QWORD *)&a1[2 * v1 + 16], v3);
      v1 = (unsigned int)(v1 + 1);
      v4 = a1[7];
    }
    while ( (unsigned int)v1 < v4 );
    v5 = 0;
    if ( v4 )
    {
      do
      {
        v6 = *(_QWORD *)&a1[2 * v5 + 20];
        v7 = (unsigned int)((*(_DWORD *)(*(_QWORD *)&a1[2 * v5 + 32] + 4LL) << 6) - 64);
        *(_QWORD *)(v7 + v6) = 0;
        *(_QWORD *)(v7 + v6 + 8) = 0;
        *(_QWORD *)(v7 + v6 + 16) = 0;
        *(_QWORD *)(v7 + v6 + 24) = 0;
        *(_QWORD *)(v7 + v6 + 32) = 0;
        *(_QWORD *)(v7 + v6 + 40) = 0;
        *(_QWORD *)(v7 + v6 + 48) = 0;
        *(_QWORD *)(v7 + v6 + 56) = 0;
        *(_QWORD *)&a1[2 * v5 + 36] = v6;
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (unsigned int)v5 < a1[7] );
    }
  }
  v8 = a1[6];
  if ( v8 )
  {
    do
    {
      v9 = SymCryptFdefSizeofIntFromDigits(a1[5]);
      if ( v9 )
      {
        v11 = *(_DWORD **)&a1[2 * v10 + 24];
        *v11 = v13;
        v11[1] = v12;
        v11[2] = v9;
      }
      *(_QWORD *)&a1[2 * v10 + 40] = v11;
      v8 = a1[6];
    }
    while ( (int)v10 + 1 < v8 );
  }
  result = a1[7] * v8;
  for ( i = 0; (unsigned int)i < (unsigned int)result; result = a1[6] * a1[7] )
  {
    v16 = SymCryptFdefSizeofIntFromDigits(a1[i + 10]);
    if ( v16 )
    {
      v17 = *(_DWORD **)&a1[2 * v18 + 26];
      *v17 = v20;
      v17[1] = v19;
      v17[2] = v16;
    }
    *(_QWORD *)&a1[2 * v18 + 42] = v17;
    i = (unsigned int)(v18 + 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800231c4  mov     [rsp+arg_0], rbx
0x1800231c9  mov     [rsp+arg_8], rsi
0x1800231ce  push    rdi
0x1800231cf  sub     rsp, 20h
0x1800231d3  xor     esi, esi
0x1800231d5  mov     rdi, rcx
0x1800231d8  cmp     [rcx+1Ch], esi
0x1800231db  jbe     loc_180023280
0x1800231e1  mov     r8d, [rdi+rsi*4+28h]
0x1800231e6  mov     ecx, r8d
0x1800231e9  call    SymCryptFdefSizeofModulusFromDigits
0x1800231ee  mov     rcx, [rdi+rsi*8+40h]
0x1800231f3  mov     edx, eax
0x1800231f5  call    SymCryptFdefModulusCreate
0x1800231fa  mov     [rdi+rsi*8+80h], rax
0x180023202  inc     esi
0x180023204  mov     eax, [rdi+1Ch]
0x180023207  cmp     esi, eax
0x180023209  jb      short loc_1800231E1
0x18002320b  xor     r9d, r9d
0x18002320e  test    eax, eax
0x180023210  jz      short loc_180023280
0x180023212  mov     rax, [rdi+r9*8+80h]
0x18002321a  mov     rdx, [rdi+r9*8+50h]
0x18002321f  mov     ecx, [rax+4]
0x180023222  shl     ecx, 6
0x180023225  sub     ecx, 40h ; '@'
0x180023228  mov     qword ptr [rcx+rdx], 0
0x180023230  mov     qword ptr [rcx+rdx+8], 0
0x180023239  mov     qword ptr [rcx+rdx+10h], 0
0x180023242  mov     qword ptr [rcx+rdx+18h], 0
0x18002324b  mov     qword ptr [rcx+rdx+20h], 0
0x180023254  mov     qword ptr [rcx+rdx+28h], 0
0x18002325d  mov     qword ptr [rcx+rdx+30h], 0
0x180023266  mov     qword ptr [rcx+rdx+38h], 0
0x18002326f  mov     [rdi+r9*8+90h], rdx
0x180023277  inc     r9d
0x18002327a  cmp     r9d, [rdi+1Ch]
0x18002327e  jb      short loc_180023212
0x180023280  mov     eax, [rdi+18h]
0x180023283  xor     edx, edx
0x180023285  mov     r11d, 67490000h
0x18002328b  test    eax, eax
0x18002328d  jz      short loc_1800232C3
0x18002328f  mov     r9d, [rdi+14h]
0x180023293  xor     r8d, r8d
0x180023296  mov     ecx, r9d
0x180023299  call    SymCryptFdefSizeofIntFromDigits
0x18002329e  test    eax, eax
0x1800232a0  jz      short loc_1800232B2
0x1800232a2  mov     r8, [rdi+rdx*8+60h]
0x1800232a7  mov     [r8], r11d
0x1800232aa  mov     [r8+4], r9d
0x1800232ae  mov     [r8+8], eax
0x1800232b2  mov     [rdi+rdx*8+0A0h], r8
0x1800232ba  inc     edx
0x1800232bc  mov     eax, [rdi+18h]
0x1800232bf  cmp     edx, eax
0x1800232c1  jb      short loc_18002328F
0x1800232c3  imul    eax, [rdi+1Ch]
0x1800232c7  xor     r8d, r8d
0x1800232ca  test    eax, eax
0x1800232cc  jz      short loc_180023307
0x1800232ce  mov     r10d, [rdi+r8*4+28h]
0x1800232d3  xor     edx, edx
0x1800232d5  mov     ecx, r10d
0x1800232d8  call    SymCryptFdefSizeofIntFromDigits
0x1800232dd  test    eax, eax
0x1800232df  jz      short loc_1800232F0
0x1800232e1  mov     rdx, [rdi+r8*8+68h]
0x1800232e6  mov     [rdx], r11d
0x1800232e9  mov     [rdx+4], r10d
0x1800232ed  mov     [rdx+8], eax
0x1800232f0  mov     [rdi+r8*8+0A8h], rdx
0x1800232f8  inc     r8d
0x1800232fb  mov     eax, [rdi+1Ch]
0x1800232fe  imul    eax, [rdi+18h]
0x180023302  cmp     r8d, eax
0x180023305  jb      short loc_1800232CE
0x180023307  mov     rbx, [rsp+28h+arg_0]
0x18002330c  mov     rsi, [rsp+28h+arg_8]
0x180023311  add     rsp, 20h
0x180023315  pop     rdi
0x180023316  retn
```
