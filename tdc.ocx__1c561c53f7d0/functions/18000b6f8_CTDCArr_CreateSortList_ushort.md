# CTDCArr::CreateSortList(ushort *)

- ea: `0x18000b6f8`
- end: `0x18000b861`
- name: `?CreateSortList@CTDCArr@@AEAAJPEAG@Z`
- size: `361`
- prototype: `__int64 __fastcall(CTDCArr *__hidden this, OLECHAR *strIn)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000b370`

## callees

- `0x180001194`
- `0x1800011b8`
- `0x18000b154`
- `0x18000b6f8`
- `0x18000c5a8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000b7c8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000b7c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b7e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b7e6`

## pseudocode

```c
__int64 __fastcall CTDCArr::CreateSortList(CTDCArr *this, OLECHAR *strIn)
{
  _QWORD *v2; // r14
  _QWORD *v3; // rsi
  OLECHAR *v4; // rbx
  unsigned int v6; // edi
  CTDCSortCriterion *v7; // rcx
  const OLECHAR *i; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  bool v11; // r15
  const OLECHAR *v12; // rax
  unsigned __int16 *v13; // rax
  OLECHAR *v14; // rsi
  int Col; // ebp
  _QWORD *v16; // rax

  v2 = (_QWORD *)((char *)this + 56);
  v3 = (_QWORD *)*((_QWORD *)this + 7);
  v4 = strIn;
  v6 = 0;
  if ( v3 )
  {
    v7 = (CTDCSortCriterion *)v3[1];
    if ( v7 )
      CTDCSortCriterion::`scalar deleting destructor'(v7, (unsigned int)strIn);
    operator delete(v3);
    *v2 = 0;
  }
  if ( v4 )
  {
    while ( *v4 )
    {
      for ( i = v4; ; ++i )
      {
        v9 = *i;
        if ( (unsigned int)v9 > 0x3B )
          break;
        v10 = 0x800000100000200LL;
        if ( !_bittest64(&v10, v9) )
          break;
      }
      if ( (((_WORD)v9 - 43) & 0xFFFD) != 0 )
      {
        v11 = 1;
      }
      else
      {
        ++i;
        v11 = (_DWORD)v9 == 43;
        while ( 1 )
        {
          LOWORD(v9) = *i;
          if ( *i != 32 && (_WORD)v9 != 9 )
            break;
          ++i;
        }
      }
      v4 = (OLECHAR *)i;
      if ( (_WORD)v9 )
      {
        do
        {
          if ( (_WORD)v9 == 59 )
            break;
          LOWORD(v9) = *++v4;
        }
        while ( *v4 );
        if ( i < v4 )
        {
          do
          {
            v12 = v4 - 1;
            if ( *(v4 - 1) != 32 && *v12 != 9 )
              break;
            --v4;
          }
          while ( i < v12 );
          if ( i < v4 )
          {
            v13 = SysAllocStringLen(i, v4 - i);
            v14 = v13;
            if ( !v13 )
              return (unsigned int)-2147024882;
            Col = CTDCArr::FindCol(this, v13);
            SysFreeString(v14);
            if ( Col > 0 )
            {
              v16 = operator new(0x10u);
              if ( !v16 )
              {
                *v2 = 0;
                return (unsigned int)-2147024882;
              }
              v16[1] = 0;
              *v2 = v16;
              *((_BYTE *)v16 + 4) = v11;
              *(_DWORD *)*v2 = Col;
              v2 = (_QWORD *)(*v2 + 8LL);
            }
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000b6f8  push    rbx
0x18000b6fa  push    rbp
0x18000b6fb  push    rsi
0x18000b6fc  push    rdi
0x18000b6fd  push    r12
0x18000b6ff  push    r13
0x18000b701  push    r14
0x18000b703  push    r15
0x18000b705  sub     rsp, 28h
0x18000b709  xor     r12d, r12d
0x18000b70c  lea     r14, [rcx+38h]
0x18000b710  mov     rsi, [r14]
0x18000b713  mov     rbx, rdx
0x18000b716  mov     r13, rcx
0x18000b719  mov     edi, r12d
0x18000b71c  test    rsi, rsi
0x18000b71f  jz      short loc_18000B73A
0x18000b721  mov     rcx, [rsi+8]; this
0x18000b725  test    rcx, rcx
0x18000b728  jz      short loc_18000B72F
0x18000b72a  call    ??_GCTDCSortCriterion@@QEAAPEAXI@Z; CTDCSortCriterion::`scalar deleting destructor'(uint)
0x18000b72f  mov     rcx, rsi; Block
0x18000b732  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b737  mov     [r14], r12
0x18000b73a  test    rbx, rbx
0x18000b73d  jz      loc_18000B84E
0x18000b743  jmp     loc_18000B816
0x18000b748  mov     rcx, rbx; strIn
0x18000b74b  movzx   edx, word ptr [rcx]
0x18000b74e  cmp     edx, 3Bh ; ';'
0x18000b751  ja      short loc_18000B769
0x18000b753  mov     r8, 800000100000200h
0x18000b75d  bt      r8, rdx
0x18000b761  jnb     short loc_18000B769
0x18000b763  add     rcx, 2
0x18000b767  jmp     short loc_18000B74B
0x18000b769  lea     eax, [rdx-2Bh]
0x18000b76c  mov     r8d, 0FFFDh
0x18000b772  test    r8w, ax
0x18000b776  jz      loc_18000B822
0x18000b77c  mov     r15b, 1
0x18000b77f  mov     rbx, rcx
0x18000b782  test    dx, dx
0x18000b785  jz      loc_18000B816
0x18000b78b  cmp     dx, 3Bh ; ';'
0x18000b78f  jz      short loc_18000B79D
0x18000b791  add     rbx, 2
0x18000b795  movzx   edx, word ptr [rbx]
0x18000b798  test    dx, dx
0x18000b79b  jnz     short loc_18000B78B
0x18000b79d  cmp     rcx, rbx
0x18000b7a0  jnb     short loc_18000B816
0x18000b7a2  lea     rax, [rbx-2]
0x18000b7a6  cmp     word ptr [rax], 20h ; ' '
0x18000b7aa  jz      short loc_18000B7B2
0x18000b7ac  cmp     word ptr [rax], 9
0x18000b7b0  jnz     short loc_18000B7BA
0x18000b7b2  mov     rbx, rax
0x18000b7b5  cmp     rcx, rax
0x18000b7b8  jb      short loc_18000B7A2
0x18000b7ba  cmp     rcx, rbx
0x18000b7bd  jnb     short loc_18000B816
0x18000b7bf  mov     rdx, rbx
0x18000b7c2  sub     rdx, rcx
0x18000b7c5  sar     rdx, 1; ui
0x18000b7c8  call    cs:__imp_SysAllocStringLen
0x18000b7ce  mov     rsi, rax
0x18000b7d1  test    rax, rax
0x18000b7d4  jz      short loc_18000B849
0x18000b7d6  mov     rdx, rax; unsigned __int16 *
0x18000b7d9  mov     rcx, r13; this
0x18000b7dc  call    ?FindCol@CTDCArr@@AEAAJPEAG@Z; CTDCArr::FindCol(ushort *)
0x18000b7e1  mov     rcx, rsi; bstrString
0x18000b7e4  mov     ebp, eax
0x18000b7e6  call    cs:__imp_SysFreeString
0x18000b7ec  test    ebp, ebp
0x18000b7ee  jle     short loc_18000B816
0x18000b7f0  mov     ecx, 10h; Size
0x18000b7f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b7fa  test    rax, rax
0x18000b7fd  jz      short loc_18000B846
0x18000b7ff  mov     [rax+8], r12
0x18000b803  mov     [r14], rax
0x18000b806  mov     [rax+4], r15b
0x18000b80a  mov     rax, [r14]
0x18000b80d  mov     [rax], ebp
0x18000b80f  mov     r14, [r14]
0x18000b812  add     r14, 8
0x18000b816  cmp     [rbx], r12w
0x18000b81a  jnz     loc_18000B748
0x18000b820  jmp     short loc_18000B84E
0x18000b822  add     rcx, 2
0x18000b826  cmp     edx, 2Bh ; '+'
0x18000b829  setz    r15b
0x18000b82d  movzx   edx, word ptr [rcx]
0x18000b830  cmp     dx, 20h ; ' '
0x18000b834  jz      short loc_18000B840
0x18000b836  cmp     dx, 9
0x18000b83a  jnz     loc_18000B77F
0x18000b840  add     rcx, 2
0x18000b844  jmp     short loc_18000B82D
0x18000b846  mov     [r14], r12
0x18000b849  mov     edi, 8007000Eh
0x18000b84e  mov     eax, edi
0x18000b850  add     rsp, 28h
0x18000b854  pop     r15
0x18000b856  pop     r14
0x18000b858  pop     r13
0x18000b85a  pop     r12
0x18000b85c  pop     rdi
0x18000b85d  pop     rsi
0x18000b85e  pop     rbp
0x18000b85f  pop     rbx
0x18000b860  retn
```
