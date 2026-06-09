# WdsCopyWdsStringArrayContents(CDynArray<ushort *,CDeallocateString> *,CDynArray<ushort *,CDeallocateString> *,int)

- ea: `0x180008540`
- end: `0x180008656`
- name: `?WdsCopyWdsStringArrayContents@@YAKPEAV?$CDynArray@PEAGVCDeallocateString@@@@0H@Z`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180007078`
- `0x1800073a0`
- `0x180008540`
- `0x180008974`
- `0x180015830`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000862a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000862a`

## pseudocode

```c
__int64 __fastcall WdsCopyWdsStringArrayContents(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int16 *v3; // rdi
  unsigned int v4; // ebx
  const unsigned __int16 *v5; // r13
  unsigned int v8; // r12d
  unsigned int v9; // esi
  __int64 v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned __int16 *v17; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  v17 = 0;
  if ( a1 && a2 )
  {
    v8 = *(_DWORD *)(a1 + 12);
    if ( !(_DWORD)a3 )
      CDynArray<unsigned short *,CDeallocateString>::Clear(a2);
    v9 = 0;
    if ( v8 )
    {
      v10 = 0;
      do
      {
        v4 = 0;
        if ( v9 < *(_DWORD *)(a1 + 12) )
          v5 = *(const unsigned __int16 **)(v10 + *(_QWORD *)a1);
        else
          v4 = 1413;
        if ( (unsigned int)ElValidateWin32_1(v4, a2, a3, 0x540u) )
          break;
        v4 = DuplicateStringWBom(v5, 0, &v17);
        v13 = ElValidateWin32_1(v4, v11, v12, 0x544u);
        v3 = v17;
        if ( v13 )
          goto LABEL_16;
        v4 = CDynArray<unsigned short *,CDeallocateString>::AddItem(a2, v17);
        if ( (unsigned int)ElValidateWin32_1(v4, v14, v15, 0x547u) )
          goto LABEL_16;
        v17 = 0;
        ++v9;
        v10 += 8;
      }
      while ( v9 < v8 );
    }
  }
  else
  {
    v4 = 87;
LABEL_16:
    if ( v3 )
      operator delete(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x180008540  mov     rax, rsp
0x180008543  mov     [rax+10h], rbx
0x180008547  mov     [rax+18h], rbp
0x18000854b  mov     [rax+20h], rsi
0x18000854f  push    rdi
0x180008550  push    r12
0x180008552  push    r13
0x180008554  push    r14
0x180008556  push    r15
0x180008558  sub     rsp, 20h
0x18000855c  xor     edi, edi
0x18000855e  xor     ebx, ebx
0x180008560  xor     r13d, r13d
0x180008563  mov     [rax+8], rdi
0x180008567  mov     rbp, rdx
0x18000856a  mov     r14, rcx
0x18000856d  test    rcx, rcx
0x180008570  jz      loc_18000861D
0x180008576  test    rdx, rdx
0x180008579  jz      loc_18000861D
0x18000857f  mov     r12d, [rcx+0Ch]
0x180008583  test    r8d, r8d
0x180008586  jnz     short loc_180008590
0x180008588  mov     rcx, rdx
0x18000858b  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x180008590  xor     esi, esi
0x180008592  test    r12d, r12d
0x180008595  jz      loc_180008636
0x18000859b  xor     r15d, r15d
0x18000859e  xor     ebx, ebx
0x1800085a0  cmp     esi, [r14+0Ch]
0x1800085a4  jb      short loc_1800085AD
0x1800085a6  mov     ebx, 585h
0x1800085ab  jmp     short loc_1800085B4
0x1800085ad  mov     rax, [r14]
0x1800085b0  mov     r13, [r15+rax]
0x1800085b4  mov     r9d, 540h
0x1800085ba  mov     ecx, ebx
0x1800085bc  call    ElValidateWin32_1
0x1800085c1  test    eax, eax
0x1800085c3  jnz     short loc_180008636
0x1800085c5  lea     r8, [rsp+48h+arg_0]; unsigned __int16 **
0x1800085ca  xor     edx, edx; int
0x1800085cc  mov     rcx, r13; unsigned __int16 *
0x1800085cf  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x1800085d4  mov     r9d, 544h
0x1800085da  mov     ecx, eax
0x1800085dc  mov     ebx, eax
0x1800085de  call    ElValidateWin32_1
0x1800085e3  mov     rdi, [rsp+48h+arg_0]
0x1800085e8  test    eax, eax
0x1800085ea  jnz     short loc_180008622
0x1800085ec  mov     rdx, rdi
0x1800085ef  mov     rcx, rbp
0x1800085f2  call    ?AddItem@?$CDynArray@PEAGVCDeallocateString@@@@QEAAKPEAG@Z; CDynArray<ushort *,CDeallocateString>::AddItem(ushort *)
0x1800085f7  mov     r9d, 547h
0x1800085fd  mov     ecx, eax
0x1800085ff  mov     ebx, eax
0x180008601  call    ElValidateWin32_1
0x180008606  test    eax, eax
0x180008608  jnz     short loc_180008622
0x18000860a  and     [rsp+48h+arg_0], 0
0x180008610  inc     esi
0x180008612  add     r15, 8
0x180008616  cmp     esi, r12d
0x180008619  jb      short loc_18000859E
0x18000861b  jmp     short loc_180008636
0x18000861d  mov     ebx, 57h ; 'W'
0x180008622  test    rdi, rdi
0x180008625  jz      short loc_180008636
0x180008627  mov     rcx, rdi
0x18000862a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008631  nop     dword ptr [rax+rax+00h]
0x180008636  mov     rbp, [rsp+48h+arg_10]
0x18000863b  mov     eax, ebx
0x18000863d  mov     rbx, [rsp+48h+arg_8]
0x180008642  mov     rsi, [rsp+48h+arg_18]
0x180008647  add     rsp, 20h
0x18000864b  pop     r15
0x18000864d  pop     r14
0x18000864f  pop     r13
0x180008651  pop     r12
0x180008653  pop     rdi
0x180008654  retn
```
