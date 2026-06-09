# CiSortAndCopyImageSectionTable

- ea: `0x180046834`
- end: `0x1800468f2`
- name: `CiSortAndCopyImageSectionTable`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011ef0`

## callees

- `0x18003393e`
- `0x180046834`

## pseudocode

```c
void __fastcall CiSortAndCopyImageSectionTable(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v6; // rdi
  __int64 v7; // r9
  unsigned int v8; // edx
  unsigned int v9; // r8d
  unsigned int v10; // eax
  bool v11; // cf
  __int64 v12; // r14
  __int64 v13; // rax
  __int64 v14; // rcx

  if ( a2 )
  {
    v6 = 0;
    do
    {
      LODWORD(v7) = v6;
      if ( !(_DWORD)v6 )
        goto LABEL_12;
      v8 = *(_DWORD *)(a1 + 40 * v6 + 20);
      while ( 1 )
      {
        v9 = v7;
        v7 = (unsigned int)(v7 - 1);
        v10 = *(_DWORD *)(a3 + 40 * v7 + 20);
        v11 = v10 < v8;
        if ( v10 < v8 )
          break;
        if ( !(_DWORD)v7 )
        {
          v11 = v10 < v8;
          break;
        }
      }
      if ( v11 )
        v7 = v9;
      if ( (_DWORD)v7 == (_DWORD)v6 )
      {
LABEL_12:
        v12 = (unsigned int)v7;
      }
      else
      {
        v12 = (unsigned int)v7;
        memmove_0(
          (void *)(a3 + 40LL * (unsigned int)(v7 + 1)),
          (const void *)(a3 + 40 * v7),
          40LL * (unsigned int)(v6 - v7));
      }
      v13 = 5 * v6;
      v6 = (unsigned int)(v6 + 1);
      v14 = 5 * v12;
      *(_OWORD *)(a3 + 8 * v14) = *(_OWORD *)(a1 + 8 * v13);
      *(_OWORD *)(a3 + 8 * v14 + 16) = *(_OWORD *)(a1 + 8 * v13 + 16);
      *(_QWORD *)(a3 + 8 * v14 + 32) = *(_QWORD *)(a1 + 8 * v13 + 32);
    }
    while ( (unsigned int)v6 < a2 );
  }
}

```

## disassembly

```asm
0x180046834  test    edx, edx
0x180046836  jz      locret_1800468F0
0x18004683c  push    rbx
0x18004683d  push    rbp
0x18004683e  push    rsi
0x18004683f  push    rdi
0x180046840  push    r14
0x180046842  push    r15
0x180046844  sub     rsp, 28h
0x180046848  mov     rsi, r8
0x18004684b  mov     r15d, edx
0x18004684e  mov     rbp, rcx
0x180046851  xor     edi, edi
0x180046853  mov     r9d, edi
0x180046856  test    edi, edi
0x180046858  jz      short loc_1800468AF
0x18004685a  lea     rax, [rdi+rdi*4]
0x18004685e  mov     edx, [rbp+rax*8+14h]
0x180046862  mov     r8d, r9d
0x180046865  dec     r9d
0x180046868  lea     rcx, [r9+r9*4]
0x18004686c  mov     eax, [rsi+rcx*8+14h]
0x180046870  cmp     eax, edx
0x180046872  jb      short loc_18004687B
0x180046874  test    r9d, r9d
0x180046877  jnz     short loc_180046862
0x180046879  cmp     eax, edx
0x18004687b  cmovb   r9d, r8d
0x18004687f  cmp     r9d, edi
0x180046882  jz      short loc_1800468AF
0x180046884  mov     eax, edi
0x180046886  mov     r14d, r9d
0x180046889  sub     eax, r9d
0x18004688c  lea     r8, [rax+rax*4]
0x180046890  lea     rax, [r9+r9*4]
0x180046894  shl     r8, 3; Size
0x180046898  lea     rdx, [rsi+rax*8]; Src
0x18004689c  lea     eax, [r9+1]
0x1800468a0  lea     rax, [rax+rax*4]
0x1800468a4  lea     rcx, [rsi+rax*8]; void *
0x1800468a8  call    memmove_0
0x1800468ad  jmp     short loc_1800468B2
0x1800468af  mov     r14d, r9d
0x1800468b2  lea     rax, [rdi+rdi*4]
0x1800468b6  inc     edi
0x1800468b8  lea     rcx, [r14+r14*4]
0x1800468bc  movups  xmm0, xmmword ptr [rbp+rax*8+0]
0x1800468c1  movups  xmmword ptr [rsi+rcx*8], xmm0
0x1800468c5  movups  xmm1, xmmword ptr [rbp+rax*8+10h]
0x1800468ca  movups  xmmword ptr [rsi+rcx*8+10h], xmm1
0x1800468cf  movsd   xmm0, qword ptr [rbp+rax*8+20h]
0x1800468d5  movsd   qword ptr [rsi+rcx*8+20h], xmm0
0x1800468db  cmp     edi, r15d
0x1800468de  jb      loc_180046853
0x1800468e4  add     rsp, 28h
0x1800468e8  pop     r15
0x1800468ea  pop     r14
0x1800468ec  pop     rdi
0x1800468ed  pop     rsi
0x1800468ee  pop     rbp
0x1800468ef  pop     rbx
0x1800468f0  retn
```
