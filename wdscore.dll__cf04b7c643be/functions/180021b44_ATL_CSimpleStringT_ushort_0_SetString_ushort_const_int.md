# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180021b44`
- end: `0x180021c28`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180020bbc`

## callees

- `0x180020e70`
- `0x180021738`
- `0x180021930`
- `0x180021b0c`
- `0x180021b44`
- `0x18002a010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180021bf5`
- `msvcrt!memmove_s` at `0x180021bf5`
- `msvcrt!memcpy_s` at `0x180021c06`
- `msvcrt!memcpy_s` at `0x180021c06`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, unsigned int a3)
{
  __int64 v3; // rbx
  ATL::CStringData *v6; // rcx
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rsi
  char *v10; // rcx
  rsize_t v11; // rdx
  rsize_t v12; // r9

  v3 = (int)a3;
  if ( a3 )
  {
    if ( !a2 )
      ATL::AtlThrowImpl(-2147024809);
    v8 = *((unsigned int *)*a1 - 4);
    v9 = (a2 - *a1) >> 1;
    if ( (((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) & 0x80000000) != 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v10 = *a1;
    v11 = 2 * v3;
    v12 = 2 * v3;
    if ( v9 > v8 )
      memcpy_s(v10, v11, a2, v12);
    else
      memmove_s(v10, v11, &v10[2 * v9], v12);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v3);
  }
  else
  {
    v6 = (ATL::CStringData *)(*a1 - 24);
    if ( *((_DWORD *)v6 + 2) )
    {
      if ( *((int *)v6 + 4) >= 0 )
      {
        v7 = *(_QWORD *)v6;
        ATL::CStringData::Release(v6);
        *a1 = (char *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x180021b44  push    rbx
0x180021b46  push    rbp
0x180021b47  push    rsi
0x180021b48  push    rdi
0x180021b49  push    r14
0x180021b4b  sub     rsp, 30h
0x180021b4f  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180021b58  movsxd  rbx, r8d
0x180021b5b  mov     rbp, rdx
0x180021b5e  mov     rdi, rcx
0x180021b61  test    r8d, r8d
0x180021b64  jnz     short loc_180021BA5
0x180021b66  mov     rcx, [rcx]
0x180021b69  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021b6d  cmp     [rcx+8], r8d
0x180021b71  jz      short loc_180021BA3
0x180021b73  cmp     [rcx+10h], r8d
0x180021b77  jge     short loc_180021B85
0x180021b79  xor     edx, edx
0x180021b7b  mov     rcx, rdi
0x180021b7e  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180021b83  jmp     short loc_180021BA3
0x180021b85  mov     rbx, [rcx]
0x180021b88  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021b8d  mov     rax, [rbx]
0x180021b90  mov     rcx, rbx
0x180021b93  mov     rax, [rax+18h]
0x180021b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b9c  add     rax, 18h
0x180021ba0  mov     [rdi], rax
0x180021ba3  jmp     short loc_180021C1C
0x180021ba5  test    rbp, rbp
0x180021ba8  jnz     short loc_180021BB5
0x180021baa  mov     ecx, 80070057h; int
0x180021baf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180021bb5  mov     rax, [rcx]
0x180021bb8  mov     r14d, [rax-10h]
0x180021bbc  mov     rsi, rbp
0x180021bbf  sub     rsi, rax
0x180021bc2  sar     rsi, 1
0x180021bc5  mov     ecx, 1
0x180021bca  sub     ecx, [rax-8]
0x180021bcd  mov     eax, [rax-0Ch]
0x180021bd0  sub     eax, ebx
0x180021bd2  or      ecx, eax
0x180021bd4  jge     short loc_180021BE0
0x180021bd6  mov     edx, ebx
0x180021bd8  mov     rcx, rdi
0x180021bdb  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180021be0  mov     rcx, [rdi]; Destination
0x180021be3  mov     rdx, rbx
0x180021be6  add     rdx, rdx; DestinationSize
0x180021be9  mov     r9, rdx; SourceSize
0x180021bec  cmp     rsi, r14
0x180021bef  ja      short loc_180021C03
0x180021bf1  lea     r8, [rcx+rsi*2]; Source
0x180021bf5  call    cs:__imp_memmove_s
0x180021bfc  nop     dword ptr [rax+rax+00h]
0x180021c01  jmp     short loc_180021C12
0x180021c03  mov     r8, rbp; Source
0x180021c06  call    cs:__imp_memcpy_s
0x180021c0d  nop     dword ptr [rax+rax+00h]
0x180021c12  mov     edx, ebx
0x180021c14  mov     rcx, rdi
0x180021c17  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180021c1c  add     rsp, 30h
0x180021c20  pop     r14
0x180021c22  pop     rdi
0x180021c23  pop     rsi
0x180021c24  pop     rbp
0x180021c25  pop     rbx
0x180021c26  retn
```
