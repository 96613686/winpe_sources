# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180004c48`
- end: `0x180004cde`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `150`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x18000485c`
- `0x180005220`
- `0x1800052cc`
- `0x18000592c`
- `0x180005cf4`
- `0x180006fec`
- `0x180007120`
- `0x18000750c`
- `0x180009300`
- `0x180009590`
- `0x18000ac7e`

## callees

- `0x1800044f8`
- `0x180004930`
- `0x180004b50`
- `0x180004c10`
- `0x180004c48`

## import_xrefs

- `msvcrt!memmove_s` at `0x180004cb8`
- `msvcrt!memmove_s` at `0x180004cb8`
- `msvcrt!memcpy_s` at `0x180004cc3`
- `msvcrt!memcpy_s` at `0x180004cc3`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, unsigned int a3)
{
  __int64 v3; // rdi
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r14
  char *v9; // rcx
  rsize_t v10; // rdx
  rsize_t v11; // r9

  v3 = (int)a3;
  if ( !a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty();
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v7 = (a2 - *a1) >> 1;
  v8 = *((unsigned int *)*a1 - 4);
  if ( (((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) & 0x80000000) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
  v9 = *a1;
  v10 = 2 * v3;
  v11 = 2 * v3;
  if ( v7 > v8 )
    memcpy_s(v9, v10, a2, v11);
  else
    memmove_s(v9, v10, &v9[2 * v7], v11);
  return ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v3);
}

```

## disassembly

```asm
0x180004c48  push    rbx
0x180004c4a  push    rbp
0x180004c4b  push    rsi
0x180004c4c  push    rdi
0x180004c4d  push    r14
0x180004c4f  sub     rsp, 20h
0x180004c53  movsxd  rdi, r8d
0x180004c56  mov     rbp, rdx
0x180004c59  mov     rbx, rcx
0x180004c5c  test    r8d, r8d
0x180004c5f  jnz     short loc_180004C68
0x180004c61  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180004c66  jmp     short loc_180004CD3
0x180004c68  test    rbp, rbp
0x180004c6b  jnz     short loc_180004C78
0x180004c6d  mov     ecx, 80070057h; int
0x180004c72  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004c78  mov     rax, [rcx]
0x180004c7b  mov     rsi, rbp
0x180004c7e  sub     rsi, rax
0x180004c81  mov     ecx, 1
0x180004c86  sar     rsi, 1
0x180004c89  sub     ecx, [rax-8]
0x180004c8c  mov     r14d, [rax-10h]
0x180004c90  mov     eax, [rax-0Ch]
0x180004c93  sub     eax, edi
0x180004c95  or      ecx, eax
0x180004c97  jge     short loc_180004CA3
0x180004c99  mov     edx, edi
0x180004c9b  mov     rcx, rbx
0x180004c9e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180004ca3  mov     rcx, [rbx]; Destination
0x180004ca6  mov     rdx, rdi
0x180004ca9  add     rdx, rdx; DestinationSize
0x180004cac  mov     r9, rdx; SourceSize
0x180004caf  cmp     rsi, r14
0x180004cb2  ja      short loc_180004CC0
0x180004cb4  lea     r8, [rcx+rsi*2]; Source
0x180004cb8  call    cs:__imp_memmove_s
0x180004cbe  jmp     short loc_180004CC9
0x180004cc0  mov     r8, rbp; Source
0x180004cc3  call    cs:__imp_memcpy_s
0x180004cc9  mov     edx, edi
0x180004ccb  mov     rcx, rbx
0x180004cce  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180004cd3  add     rsp, 20h
0x180004cd7  pop     r14
0x180004cd9  pop     rdi
0x180004cda  pop     rsi
0x180004cdb  pop     rbp
0x180004cdc  pop     rbx
0x180004cdd  retn
```
