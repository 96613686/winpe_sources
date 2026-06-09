# WdsCopyMultiSzContentsToWdsStringArray(ushort *,CDynArray<ushort *,CDeallocateString> *,int)

- ea: `0x1800081e0`
- end: `0x1800082b6`
- name: `?WdsCopyMultiSzContentsToWdsStringArray@@YAKPEAGPEAV?$CDynArray@PEAGVCDeallocateString@@@@H@Z`
- size: `214`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180007e20`

## callees

- `0x180007078`
- `0x1800073a0`
- `0x1800081e0`
- `0x180008974`
- `0x180015830`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008294`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008294`

## pseudocode

```c
__int64 __fastcall WdsCopyMultiSzContentsToWdsStringArray(unsigned __int16 *a1, __int64 a2, int a3)
{
  unsigned __int16 *v4; // rbx
  const unsigned __int16 *v5; // rdi
  unsigned int v6; // esi
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned __int16 *v14; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  v5 = a1;
  v14 = 0;
  v6 = 0;
  if ( a1 && a2 )
  {
    if ( !a3 )
      CDynArray<unsigned short *,CDeallocateString>::Clear(a2);
    while ( *v5 )
    {
      v6 = DuplicateStringWBom(v5, 0, &v14);
      v9 = ElValidateWin32_1(v6, v7, v8, 0x637u);
      v4 = v14;
      if ( v9 )
        goto LABEL_13;
      v6 = CDynArray<unsigned short *,CDeallocateString>::AddItem(a2, v14);
      if ( (unsigned int)ElValidateWin32_1(v6, v10, v11, 0x63Au) )
        goto LABEL_13;
      v14 = 0;
      v12 = -1;
      do
        ++v12;
      while ( v5[v12] );
      v5 += v12 + 1;
    }
  }
  else
  {
    v6 = 87;
LABEL_13:
    if ( v4 )
      operator delete(v4);
  }
  return v6;
}

```

## disassembly

```asm
0x1800081e0  mov     [rsp+arg_8], rbx
0x1800081e5  mov     [rsp+arg_10], rbp
0x1800081ea  push    rsi
0x1800081eb  push    rdi
0x1800081ec  push    r14
0x1800081ee  sub     rsp, 20h
0x1800081f2  xor     r14d, r14d
0x1800081f5  mov     rbp, rdx
0x1800081f8  mov     ebx, r14d
0x1800081fb  mov     rdi, rcx
0x1800081fe  mov     [rsp+38h+arg_0], rbx
0x180008203  mov     esi, r14d
0x180008206  test    rcx, rcx
0x180008209  jz      short loc_180008287
0x18000820b  test    rdx, rdx
0x18000820e  jz      short loc_180008287
0x180008210  test    r8d, r8d
0x180008213  jnz     short loc_18000827F
0x180008215  mov     rcx, rdx
0x180008218  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x18000821d  jmp     short loc_18000827F
0x18000821f  lea     r8, [rsp+38h+arg_0]; unsigned __int16 **
0x180008224  xor     edx, edx; int
0x180008226  mov     rcx, rdi; unsigned __int16 *
0x180008229  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x18000822e  mov     r9d, 637h
0x180008234  mov     ecx, eax
0x180008236  mov     esi, eax
0x180008238  call    ElValidateWin32_1
0x18000823d  mov     rbx, [rsp+38h+arg_0]
0x180008242  test    eax, eax
0x180008244  jnz     short loc_18000828C
0x180008246  mov     rdx, rbx
0x180008249  mov     rcx, rbp
0x18000824c  call    ?AddItem@?$CDynArray@PEAGVCDeallocateString@@@@QEAAKPEAG@Z; CDynArray<ushort *,CDeallocateString>::AddItem(ushort *)
0x180008251  mov     r9d, 63Ah
0x180008257  mov     ecx, eax
0x180008259  mov     esi, eax
0x18000825b  call    ElValidateWin32_1
0x180008260  test    eax, eax
0x180008262  jnz     short loc_18000828C
0x180008264  mov     [rsp+38h+arg_0], r14
0x180008269  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000826d  inc     rax
0x180008270  cmp     [rdi+rax*2], r14w
0x180008275  jnz     short loc_18000826D
0x180008277  lea     rdi, [rdi+rax*2]
0x18000827b  add     rdi, 2
0x18000827f  cmp     [rdi], r14w
0x180008283  jnz     short loc_18000821F
0x180008285  jmp     short loc_1800082A0
0x180008287  mov     esi, 57h ; 'W'
0x18000828c  test    rbx, rbx
0x18000828f  jz      short loc_1800082A0
0x180008291  mov     rcx, rbx
0x180008294  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000829b  nop     dword ptr [rax+rax+00h]
0x1800082a0  mov     rbx, [rsp+38h+arg_8]
0x1800082a5  mov     eax, esi
0x1800082a7  mov     rbp, [rsp+38h+arg_10]
0x1800082ac  add     rsp, 20h
0x1800082b0  pop     r14
0x1800082b2  pop     rdi
0x1800082b3  pop     rsi
0x1800082b4  retn
```
