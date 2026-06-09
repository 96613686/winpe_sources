# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180008c10`
- end: `0x180008cb9`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `169`
- prototype: ``
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x180003200`
- `0x1800032c0`
- `0x180003a80`
- `0x180003b80`
- `0x1800045f0`
- `0x180004680`
- `0x1800046c0`
- `0x1800047a0`
- `0x180004ab0`
- `0x180007200`
- `0x180008be0`
- `0x18005b800`
- `0x18005c9d0`
- `0x18005d720`
- `0x18005dce0`
- `0x18005f5b0`
- `0x18005f680`
- `0x18005fdc0`

## callees

- `0x1800066cc`
- `0x180006de0`
- `0x180008310`
- `0x180008c10`

## import_xrefs

- `msvcrt!memmove_s` at `0x180008c83`
- `msvcrt!memmove_s` at `0x180008c83`
- `msvcrt!memcpy_s` at `0x180008c8e`
- `msvcrt!memcpy_s` at `0x180008c8e`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // r15
  char *v9; // rcx
  rsize_t v10; // r9
  rsize_t v11; // rdx

  v3 = (int)a3;
  if ( !(_DWORD)a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty();
  if ( !a2 )
    goto LABEL_12;
  v7 = (a2 - *a1) >> 1;
  v8 = *((unsigned int *)*a1 - 4);
  if ( (int)((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)a3, a3);
  v9 = *a1;
  v10 = 2 * v3;
  v11 = 2 * v3;
  if ( v7 > v8 )
    memcpy_s(v9, v11, a2, v10);
  else
    memmove_s(v9, v11, &v9[2 * v7], v10);
  if ( (int)v3 < 0 || (int)v3 > *((_DWORD *)*a1 - 3) )
LABEL_12:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v3;
  result = 0;
  *(_WORD *)&(*a1)[2 * v3] = 0;
  return result;
}

```

## disassembly

```asm
0x180008c10  push    rbx
0x180008c12  push    rbp
0x180008c13  push    rsi
0x180008c14  push    rdi
0x180008c15  push    r14
0x180008c17  push    r15
0x180008c19  sub     rsp, 28h
0x180008c1d  movsxd  rbx, r8d
0x180008c20  mov     r14, rdx
0x180008c23  mov     rdi, rcx
0x180008c26  test    r8d, r8d
0x180008c29  jnz     short loc_180008C3D
0x180008c2b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180008c30  add     rsp, 28h
0x180008c34  pop     r15
0x180008c36  pop     r14
0x180008c38  pop     rdi
0x180008c39  pop     rsi
0x180008c3a  pop     rbp
0x180008c3b  pop     rbx
0x180008c3c  retn
0x180008c3d  test    r14, r14
0x180008c40  jz      short loc_180008CAE
0x180008c42  mov     rax, [rcx]
0x180008c45  mov     rbp, r14
0x180008c48  sub     rbp, rax
0x180008c4b  mov     ecx, 1
0x180008c50  sar     rbp, 1
0x180008c53  sub     ecx, [rax-8]
0x180008c56  mov     r15d, [rax-10h]
0x180008c5a  mov     eax, [rax-0Ch]
0x180008c5d  sub     eax, ebx
0x180008c5f  or      ecx, eax
0x180008c61  jge     short loc_180008C6D
0x180008c63  mov     edx, ebx
0x180008c65  mov     rcx, rdi
0x180008c68  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180008c6d  mov     rcx, [rdi]; Destination
0x180008c70  lea     rsi, [rbx+rbx]
0x180008c74  mov     r9, rsi; SourceSize
0x180008c77  mov     rdx, rsi; DestinationSize
0x180008c7a  cmp     rbp, r15
0x180008c7d  ja      short loc_180008C8B
0x180008c7f  lea     r8, [rcx+rbp*2]; Source
0x180008c83  call    cs:__imp_memmove_s
0x180008c89  jmp     short loc_180008C94
0x180008c8b  mov     r8, r14; Source
0x180008c8e  call    cs:__imp_memcpy_s
0x180008c94  test    ebx, ebx
0x180008c96  js      short loc_180008CAE
0x180008c98  mov     rax, [rdi]
0x180008c9b  cmp     ebx, [rax-0Ch]
0x180008c9e  jg      short loc_180008CAE
0x180008ca0  mov     [rax-10h], ebx
0x180008ca3  xor     eax, eax
0x180008ca5  mov     rcx, [rdi]
0x180008ca8  mov     [rsi+rcx], ax
0x180008cac  jmp     short loc_180008C30
0x180008cae  mov     ecx, 80070057h; int
0x180008cb3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
