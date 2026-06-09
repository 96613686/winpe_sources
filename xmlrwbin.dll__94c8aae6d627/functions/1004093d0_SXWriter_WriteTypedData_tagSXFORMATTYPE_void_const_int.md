# SXWriter::WriteTypedData(tagSXFORMATTYPE,void const *,int)

- ea: `0x1004093d0`
- end: `0x1004095a3`
- name: `?WriteTypedData@SXWriter@@AEAAXW4tagSXFORMATTYPE@@PEBXH@Z`
- size: `467`
- prototype: `void __fastcall(__int64, int, unsigned __int64 *, int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1004098d0`
- `0x10040a950`
- `0x10040aa20`
- `0x10040ab90`

## callees

- `0x1004086f0`
- `0x100409320`
- `0x1004093d0`
- `0x100409840`
- `0x10040aab0`
- `0x100415d60`

## pseudocode

```c
void __fastcall SXWriter::WriteTypedData(__int64 a1, int a2, unsigned __int64 *a3, int a4)
{
  unsigned __int64 v4; // rbp
  unsigned __int64 *v5; // rdi
  _BYTE *v8; // rax
  unsigned __int64 v9; // rsi
  unsigned int v10; // ebp
  unsigned int v11; // eax
  __int64 v12; // rsi
  unsigned int v13; // eax
  _BYTE *v14; // rcx
  unsigned int v15; // edi
  _BYTE *v16; // rax
  int v17; // eax
  int v18; // ecx
  unsigned int v19; // edx
  unsigned int v20; // eax
  __int64 v21; // rsi

  v4 = a4;
  v5 = a3;
  switch ( a2 )
  {
    case 17:
      v8 = *(_BYTE **)(a1 + 304);
      v9 = (unsigned __int64)a4 >> 1;
      if ( v8 == *(_BYTE **)(a1 + 312) )
      {
        SXWriter::writeBuffer((SXWriter *)a1);
        v8 = *(_BYTE **)(a1 + 304);
      }
      *v8 = 17;
      ++*(_QWORD *)(a1 + 304);
      SXWriter::WriteMb32((SXWriter *)a1, v9);
      v10 = 2 * v9;
      if ( 2 * (_DWORD)v9 )
      {
        while ( 1 )
        {
          v11 = v10;
          if ( *(_DWORD *)(a1 + 312) - *(_DWORD *)(a1 + 304) <= v10 )
            v11 = *(_DWORD *)(a1 + 312) - *(_DWORD *)(a1 + 304);
          v12 = v11;
          memmove(*(void **)(a1 + 304), v5, v11);
          *(_QWORD *)(a1 + 304) += v12;
          v10 -= v12;
          if ( !v10 )
            break;
          SXWriter::writeBuffer((SXWriter *)a1);
          v5 = (unsigned __int64 *)((char *)v5 + v12);
        }
      }
      break;
    case 140:
      v13 = SXWriter::MapHandleToUnitoken((SXWriter *)a1, *a3);
      v14 = *(_BYTE **)(a1 + 304);
      v15 = v13;
      if ( v14 == *(_BYTE **)(a1 + 312) )
      {
        SXWriter::writeBuffer((SXWriter *)a1);
        v14 = *(_BYTE **)(a1 + 304);
      }
      *v14 = -116;
      ++*(_QWORD *)(a1 + 304);
      if ( (byte_100434BA0 & 0x40) != 0 )
        SXWriter::WriteMb32((SXWriter *)a1, 0);
      SXWriter::WriteMb32((SXWriter *)a1, v15);
      break;
    case 141:
      SXWriter::WriteQNameHandleData((SXWriter *)a1, (struct QNAME_TRIPLE *)a3);
      break;
    default:
      v16 = *(_BYTE **)(a1 + 304);
      if ( v16 == *(_BYTE **)(a1 + 312) )
      {
        SXWriter::writeBuffer((SXWriter *)a1);
        v16 = *(_BYTE **)(a1 + 304);
      }
      *v16 = a2;
      ++*(_QWORD *)(a1 + 304);
      v17 = a2 - 100;
      if ( a2 < 128 )
        v17 = a2;
      v18 = *((unsigned __int8 *)&SXFormatDataByType + 8 * v17);
      if ( (v18 & 0x40) != 0 )
      {
        v19 = v4;
        if ( v18 != 64 )
          v19 = v4 >> 1;
        SXWriter::WriteMb32((SXWriter *)a1, v19);
      }
      if ( (_DWORD)v4 )
      {
        while ( 1 )
        {
          v20 = v4;
          if ( *(_DWORD *)(a1 + 312) - *(_DWORD *)(a1 + 304) <= (unsigned int)v4 )
            v20 = *(_DWORD *)(a1 + 312) - *(_DWORD *)(a1 + 304);
          v21 = v20;
          memmove(*(void **)(a1 + 304), v5, v20);
          *(_QWORD *)(a1 + 304) += v21;
          LODWORD(v4) = v4 - v21;
          if ( !(_DWORD)v4 )
            break;
          SXWriter::writeBuffer((SXWriter *)a1);
          v5 = (unsigned __int64 *)((char *)v5 + v21);
        }
      }
      break;
  }
}

```

## disassembly

```asm
0x1004093d0  mov     [rsp+arg_0], rbx
0x1004093d5  mov     [rsp+arg_8], rbp
0x1004093da  mov     [rsp+arg_10], rsi
0x1004093df  push    rdi
0x1004093e0  sub     rsp, 20h
0x1004093e4  movsxd  rbp, r9d
0x1004093e7  mov     rdi, r8
0x1004093ea  mov     esi, edx
0x1004093ec  mov     rbx, rcx
0x1004093ef  cmp     edx, 11h
0x1004093f2  jnz     loc_10040947F
0x1004093f8  mov     rax, [rcx+130h]
0x1004093ff  mov     rsi, rbp
0x100409402  shr     rsi, 1
0x100409405  cmp     rax, [rcx+138h]
0x10040940c  jnz     short loc_10040941A
0x10040940e  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x100409413  mov     rax, [rbx+130h]
0x10040941a  mov     byte ptr [rax], 11h
0x10040941d  mov     edx, esi; unsigned int
0x10040941f  inc     qword ptr [rbx+130h]
0x100409426  mov     rcx, rbx; this
0x100409429  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x10040942e  lea     ebp, [rsi+rsi]
0x100409431  test    ebp, ebp
0x100409433  jz      loc_1004094D7
0x100409439  nop     dword ptr [rax+00000000h]
0x100409440  mov     ecx, [rbx+138h]
0x100409446  mov     eax, ebp
0x100409448  sub     ecx, [rbx+130h]
0x10040944e  mov     rdx, rdi; Src
0x100409451  cmp     ecx, ebp
0x100409453  cmovbe  eax, ecx
0x100409456  mov     rcx, [rbx+130h]; void *
0x10040945d  mov     r8d, eax; Size
0x100409460  mov     esi, eax
0x100409462  call    memmove
0x100409467  add     [rbx+130h], rsi
0x10040946e  sub     ebp, esi
0x100409470  jz      short loc_1004094D7
0x100409472  mov     rcx, rbx; this
0x100409475  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040947a  add     rdi, rsi
0x10040947d  jmp     short loc_100409440
0x10040947f  cmp     esi, 8Ch
0x100409485  jnz     short loc_1004094EC
0x100409487  mov     rdx, [r8]; unsigned __int64
0x10040948a  call    ?MapHandleToUnitoken@SXWriter@@AEAAK_K@Z; SXWriter::MapHandleToUnitoken(unsigned __int64)
0x10040948f  mov     rcx, [rbx+130h]
0x100409496  mov     edi, eax
0x100409498  cmp     rcx, [rbx+138h]
0x10040949f  jnz     short loc_1004094B0
0x1004094a1  mov     rcx, rbx; this
0x1004094a4  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x1004094a9  mov     rcx, [rbx+130h]
0x1004094b0  mov     byte ptr [rcx], 8Ch
0x1004094b3  inc     qword ptr [rbx+130h]
0x1004094ba  test    cs:byte_100434BA0, 40h
0x1004094c1  jz      short loc_1004094CD
0x1004094c3  xor     edx, edx; unsigned int
0x1004094c5  mov     rcx, rbx; this
0x1004094c8  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x1004094cd  mov     edx, edi; unsigned int
0x1004094cf  mov     rcx, rbx; this
0x1004094d2  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x1004094d7  mov     rbx, [rsp+28h+arg_0]
0x1004094dc  mov     rbp, [rsp+28h+arg_8]
0x1004094e1  mov     rsi, [rsp+28h+arg_10]
0x1004094e6  add     rsp, 20h
0x1004094ea  pop     rdi
0x1004094eb  retn
0x1004094ec  cmp     esi, 8Dh
0x1004094f2  jnz     short loc_1004094FE
0x1004094f4  mov     rdx, r8; struct QNAME_TRIPLE *
0x1004094f7  call    ?WriteQNameHandleData@SXWriter@@AEAAXPEAUQNAME_TRIPLE@@@Z; SXWriter::WriteQNameHandleData(QNAME_TRIPLE *)
0x1004094fc  jmp     short loc_1004094D7
0x1004094fe  mov     rax, [rcx+130h]
0x100409505  cmp     rax, [rcx+138h]
0x10040950c  jnz     short loc_10040951A
0x10040950e  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x100409513  mov     rax, [rbx+130h]
0x10040951a  mov     [rax], sil
0x10040951d  lea     rcx, ?SXFormatDataByType@@3PAUSXFORMATTYPEDATA@@A; SXFORMATTYPEDATA near * SXFormatDataByType
0x100409524  inc     qword ptr [rbx+130h]
0x10040952b  lea     eax, [rsi-64h]
0x10040952e  cmp     esi, 80h
0x100409534  cmovl   eax, esi
0x100409537  cdqe
0x100409539  movzx   ecx, byte ptr [rcx+rax*8]
0x10040953d  test    cl, 40h
0x100409540  jz      short loc_100409558
0x100409542  mov     edx, ebp
0x100409544  mov     rax, rbp
0x100409547  shr     rax, 1
0x10040954a  cmp     ecx, 40h ; '@'
0x10040954d  mov     rcx, rbx; this
0x100409550  cmovnz  edx, eax; unsigned int
0x100409553  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x100409558  test    ebp, ebp
0x10040955a  jz      loc_1004094D7
0x100409560  mov     ecx, [rbx+138h]
0x100409566  mov     eax, ebp
0x100409568  sub     ecx, [rbx+130h]
0x10040956e  mov     rdx, rdi; Src
0x100409571  cmp     ecx, ebp
0x100409573  cmovbe  eax, ecx
0x100409576  mov     rcx, [rbx+130h]; void *
0x10040957d  mov     r8d, eax; Size
0x100409580  mov     esi, eax
0x100409582  call    memmove
0x100409587  add     [rbx+130h], rsi
0x10040958e  sub     ebp, esi
0x100409590  jz      loc_1004094D7
0x100409596  mov     rcx, rbx; this
0x100409599  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040959e  add     rdi, rsi
0x1004095a1  jmp     short loc_100409560
```
