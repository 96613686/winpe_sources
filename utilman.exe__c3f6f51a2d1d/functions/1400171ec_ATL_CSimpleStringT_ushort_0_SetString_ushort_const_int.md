# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x1400171ec`
- end: `0x140017288`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `156`
- prototype: ``
- caller_count: `12`
- callee_count: `6`
- tags: ``

## callers

- `0x140013b44`
- `0x140014128`
- `0x140014290`
- `0x140014310`
- `0x140015720`
- `0x140015c74`
- `0x140015fb8`
- `0x140017cc0`
- `0x140018694`
- `0x140018ac8`
- `0x140018d0c`
- `0x14001bf80`

## callees

- `0x140002f58`
- `0x14000d678`
- `0x140014c24`
- `0x140016804`
- `0x1400171b4`
- `0x1400171ec`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x14001725c`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x14001725c`

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
  {
    ATL::AtlThrowImpl(-2147024809);
    __debugbreak();
  }
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
0x1400171ec  push    rbx
0x1400171ee  push    rbp
0x1400171ef  push    rsi
0x1400171f0  push    rdi
0x1400171f1  push    r14
0x1400171f3  sub     rsp, 20h
0x1400171f7  movsxd  rdi, r8d
0x1400171fa  mov     rbp, rdx
0x1400171fd  mov     rbx, rcx
0x140017200  test    r8d, r8d
0x140017203  jnz     short loc_14001720C
0x140017205  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14001720a  jmp     short loc_14001727C
0x14001720c  test    rbp, rbp
0x14001720f  jnz     short loc_14001721C
0x140017211  mov     ecx, 80070057h; int
0x140017216  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001721b  int     3; Trap to Debugger
0x14001721c  mov     rax, [rcx]
0x14001721f  mov     rsi, rbp
0x140017222  sub     rsi, rax
0x140017225  mov     ecx, 1
0x14001722a  sar     rsi, 1
0x14001722d  sub     ecx, [rax-8]
0x140017230  mov     r14d, [rax-10h]
0x140017234  mov     eax, [rax-0Ch]
0x140017237  sub     eax, edi
0x140017239  or      ecx, eax
0x14001723b  jge     short loc_140017247
0x14001723d  mov     edx, edi
0x14001723f  mov     rcx, rbx
0x140017242  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140017247  mov     rcx, [rbx]; Destination
0x14001724a  mov     rdx, rdi
0x14001724d  add     rdx, rdx; DestinationSize
0x140017250  mov     r9, rdx; SourceSize
0x140017253  cmp     rsi, r14
0x140017256  ja      short loc_14001726A
0x140017258  lea     r8, [rcx+rsi*2]; Source
0x14001725c  call    cs:__imp_memmove_s
0x140017263  nop     dword ptr [rax+rax+00h]
0x140017268  jmp     short loc_140017272
0x14001726a  mov     r8, rbp; Source
0x14001726d  call    memcpy_s
0x140017272  mov     edx, edi
0x140017274  mov     rcx, rbx
0x140017277  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x14001727c  add     rsp, 20h
0x140017280  pop     r14
0x140017282  pop     rdi
0x140017283  pop     rsi
0x140017284  pop     rbp
0x140017285  pop     rbx
0x140017286  retn
```
