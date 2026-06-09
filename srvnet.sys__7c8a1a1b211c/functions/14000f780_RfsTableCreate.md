# RfsTableCreate

- ea: `0x14000f780`
- end: `0x14000f8d6`
- name: `RfsTableCreate`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fc18`
- `0x140024bb8`

## callees

- `0x14000f780`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f7e0`
- `ntoskrnl!ExAllocatePool2` at `0x14000f7e0`

## pseudocode

```c
__int64 __fastcall RfsTableCreate(__int64 a1, _DWORD *a2, __int64 a3, int a4, __int64 a5)
{
  int v5; // r8d
  char v6; // di
  __int64 i; // rcx
  int v9; // edx
  __int64 result; // rax
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // ecx
  unsigned int v14; // ebx
  __int64 v15; // r11
  __int64 v16; // r9
  __int64 v17; // rcx

  v5 = 0;
  v6 = a4;
  for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
  {
    v9 = a2[i];
    if ( (unsigned int)(v9 - 1) > 0x12 )
      return 0;
    v5 += v9;
  }
  if ( (unsigned int)(v5 + a4) > 0x1E )
    return 0;
  result = ExAllocatePool2(256, 8 * (1LL << *a2) + 112, 1382437708);
  if ( !result )
    return 0;
  v11 = 0;
  *(_QWORD *)(result + 88) = 256;
  v12 = 2;
  do
  {
    v13 = a2[v11];
    *(_DWORD *)(result + 4 * v11 + 48) = v12;
    *(_DWORD *)(result + 4 * v11 + 24) = (1 << v13) - 1;
    v12 += v13;
    ++v11;
  }
  while ( v11 != 2 );
  *(_DWORD *)(result + 68) = v12;
  *(_DWORD *)(result + 72) = 2;
  v14 = 0;
  *(_BYTE *)(result + 104) = 0;
  *(_DWORD *)(result + 44) = (1 << v6) - 1;
  *(_QWORD *)(result + 96) = a5;
  *(_QWORD *)(result + 16) = result + 112;
  *(_QWORD *)result = 0;
  v15 = *(unsigned int *)(result + 24);
  if ( (_DWORD)v15 != -1 )
  {
    do
    {
      v16 = v14++;
      *(_DWORD *)(*(_QWORD *)(result + 16) + 8 * v16) = ((v14 & *(_DWORD *)(result + 24)) << *(_DWORD *)(result + 48))
                                                      | *(_DWORD *)(*(_QWORD *)(result + 16) + 8 * v16)
                                                      & ~(*(_DWORD *)(result + 24) << *(_DWORD *)(result + 48));
      *(_DWORD *)(*(_QWORD *)(result + 16) + 8 * v16) = *(_DWORD *)(*(_QWORD *)(result + 16) + 8 * v16) & 0xFFFFFFFC | 1;
    }
    while ( v14 < (int)v15 + 1 );
  }
  *(_DWORD *)(*(_QWORD *)(result + 16) + 8 * v15) = -1;
  v17 = *(_QWORD *)(result + 16);
  *(_DWORD *)(result + 76) = 1;
  *(_QWORD *)(result + 80) = v17 + 8 * v15;
  return result;
}

```

## disassembly

```asm
0x14000f780  mov     [rsp+arg_0], rbx
0x14000f785  mov     [rsp+arg_8], rsi
0x14000f78a  push    rdi
0x14000f78b  sub     rsp, 20h
0x14000f78f  xor     r8d, r8d
0x14000f792  mov     edi, r9d
0x14000f795  xor     ecx, ecx
0x14000f797  mov     rbx, rdx
0x14000f79a  lea     esi, [rcx+1]
0x14000f79d  cmp     ecx, 2
0x14000f7a0  jnb     short loc_14000F7B8
0x14000f7a2  mov     edx, [rbx+rcx*4]
0x14000f7a5  lea     eax, [rdx-1]
0x14000f7a8  cmp     eax, 12h
0x14000f7ab  ja      loc_14000F8C3
0x14000f7b1  add     r8d, edx
0x14000f7b4  add     ecx, esi
0x14000f7b6  jmp     short loc_14000F79D
0x14000f7b8  lea     eax, [r8+r9]
0x14000f7bc  cmp     eax, 1Eh
0x14000f7bf  ja      loc_14000F8C3
0x14000f7c5  mov     ecx, [rbx]
0x14000f7c7  mov     rdx, rsi
0x14000f7ca  shl     rdx, cl
0x14000f7cd  mov     r8d, 5266534Ch
0x14000f7d3  mov     ecx, 100h
0x14000f7d8  lea     rdx, ds:70h[rdx*8]
0x14000f7e0  call    cs:__imp_ExAllocatePool2
0x14000f7e7  nop     dword ptr [rax+rax+00h]
0x14000f7ec  mov     r10, rax
0x14000f7ef  test    rax, rax
0x14000f7f2  jz      loc_14000F8C3
0x14000f7f8  xor     edx, edx
0x14000f7fa  mov     qword ptr [rax+58h], 100h
0x14000f802  lea     r8d, [rdx+2]
0x14000f806  mov     ecx, [rbx+rdx*4]
0x14000f809  mov     eax, esi
0x14000f80b  shl     eax, cl
0x14000f80d  sub     eax, esi
0x14000f80f  mov     [r10+rdx*4+30h], r8d
0x14000f814  mov     [r10+rdx*4+18h], eax
0x14000f819  add     r8d, ecx
0x14000f81c  add     rdx, rsi
0x14000f81f  cmp     rdx, 2
0x14000f823  jnz     short loc_14000F806
0x14000f825  mov     ecx, edi
0x14000f827  mov     [r10+44h], r8d
0x14000f82b  mov     eax, esi
0x14000f82d  mov     [r10+48h], edx
0x14000f831  shl     eax, cl
0x14000f833  xor     ebx, ebx
0x14000f835  sub     eax, esi
0x14000f837  mov     byte ptr [r10+68h], 0
0x14000f83c  mov     [r10+2Ch], eax
0x14000f840  mov     rax, [rsp+28h+arg_20]
0x14000f845  mov     [r10+60h], rax
0x14000f849  lea     rax, [r10+70h]
0x14000f84d  mov     [r10+10h], rax
0x14000f851  mov     qword ptr [r10], 0
0x14000f858  mov     r11d, [r10+18h]
0x14000f85c  lea     edi, [r11+1]
0x14000f860  test    edi, edi
0x14000f862  jz      short loc_14000F8A2
0x14000f864  mov     ecx, [r10+30h]
0x14000f868  mov     r8d, [r10+18h]
0x14000f86c  mov     eax, r8d
0x14000f86f  mov     rdx, [r10+10h]
0x14000f873  shl     eax, cl
0x14000f875  mov     r9d, ebx
0x14000f878  not     eax
0x14000f87a  inc     ebx
0x14000f87c  and     r8d, ebx
0x14000f87f  shl     r8d, cl
0x14000f882  and     eax, [rdx+r9*8]
0x14000f886  or      eax, r8d
0x14000f889  mov     [rdx+r9*8], eax
0x14000f88d  mov     rcx, [r10+10h]
0x14000f891  mov     eax, [rcx+r9*8]
0x14000f895  and     eax, 0FFFFFFFDh
0x14000f898  or      eax, esi
0x14000f89a  mov     [rcx+r9*8], eax
0x14000f89e  cmp     ebx, edi
0x14000f8a0  jb      short loc_14000F864
0x14000f8a2  mov     rcx, [r10+10h]
0x14000f8a6  mov     rax, r10
0x14000f8a9  mov     dword ptr [rcx+r11*8], 0FFFFFFFFh
0x14000f8b1  mov     rcx, [r10+10h]
0x14000f8b5  mov     [r10+4Ch], esi
0x14000f8b9  lea     rdx, [rcx+r11*8]
0x14000f8bd  mov     [r10+50h], rdx
0x14000f8c1  jmp     short loc_14000F8C5
0x14000f8c3  xor     eax, eax
0x14000f8c5  mov     rbx, [rsp+28h+arg_0]
0x14000f8ca  mov     rsi, [rsp+28h+arg_8]
0x14000f8cf  add     rsp, 20h
0x14000f8d3  pop     rdi
0x14000f8d4  retn
```
