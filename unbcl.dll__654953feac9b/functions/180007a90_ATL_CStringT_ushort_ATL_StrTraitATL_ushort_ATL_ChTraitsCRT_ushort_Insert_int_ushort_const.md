# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort const *)

- ea: `0x180007a90`
- end: `0x180007bba`
- name: `?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHPEBG@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18005c9d0`
- `0x18005cb20`

## callees

- `0x1800066cc`
- `0x180007a90`
- `0x180008310`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007b21`
- `msvcrt!memmove_s` at `0x180007b21`
- `msvcrt!memcpy_s` at `0x180007b4c`
- `msvcrt!memcpy_s` at `0x180007b4c`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(
        _QWORD *a1,
        int a2,
        _WORD *a3)
{
  int v4; // eax
  int v6; // esi
  int v7; // r15d
  __int64 v8; // rdi
  int v9; // ebx
  rsize_t v10; // rdx
  void *v11; // rsi
  errno_t v12; // eax
  errno_t v13; // eax

  v4 = 0;
  if ( a2 >= 0 )
    v4 = a2;
  v6 = *(_DWORD *)(*a1 - 16LL);
  v7 = v6;
  if ( v4 <= v6 )
    v7 = v4;
  if ( !a3 )
    return *(unsigned int *)(*a1 - 16LL);
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( (int)v8 <= 0 )
    return *(unsigned int *)(*a1 - 16LL);
  v9 = v6 + v8;
  if ( (int)((*(_DWORD *)(*a1 - 12LL) - (v6 + v8)) | (1 - *(_DWORD *)(*a1 - 8LL))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v9, a3);
  v10 = 2LL * (v6 - v7 + 1);
  v11 = (void *)(*a1 + 2LL * v7);
  v12 = memmove_s((void *const)(*a1 + 2 * ((int)v8 + (__int64)v7)), v10, v11, v10);
  if ( v12 )
  {
    if ( v12 == 12 )
      goto LABEL_27;
    if ( v12 == 22 || v12 == 34 )
      goto LABEL_28;
    if ( v12 != 80 )
      goto LABEL_26;
  }
  v13 = memcpy_s(v11, 2LL * (int)v8, a3, 2LL * (int)v8);
  if ( v13 )
  {
    if ( v13 != 12 )
    {
      if ( v13 != 22 && v13 != 34 )
      {
        if ( v13 == 80 )
          goto LABEL_21;
LABEL_26:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_28:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_27:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_21:
  if ( v9 < 0 || v9 > *(_DWORD *)(*a1 - 12LL) )
    goto LABEL_28;
  *(_DWORD *)(*a1 - 16LL) = v9;
  *(_WORD *)(*a1 + 2LL * v9) = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007a90  push    rbx
0x180007a92  push    rbp
0x180007a93  push    rsi
0x180007a94  push    rdi
0x180007a95  push    r12
0x180007a97  push    r14
0x180007a99  push    r15
0x180007a9b  sub     rsp, 20h
0x180007a9f  xor     r12d, r12d
0x180007aa2  mov     rbp, r8
0x180007aa5  test    edx, edx
0x180007aa7  mov     eax, r12d
0x180007aaa  mov     r14, rcx
0x180007aad  cmovns  eax, edx
0x180007ab0  mov     rdx, [rcx]
0x180007ab3  mov     esi, [rdx-10h]
0x180007ab6  cmp     eax, esi
0x180007ab8  mov     r15d, esi
0x180007abb  cmovle  r15d, eax
0x180007abf  test    r8, r8
0x180007ac2  jz      loc_180007B86
0x180007ac8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007acc  inc     rdi
0x180007acf  cmp     [r8+rdi*2], r12w
0x180007ad4  jnz     short loc_180007ACC
0x180007ad6  test    edi, edi
0x180007ad8  jle     loc_180007B86
0x180007ade  mov     eax, [rdx-0Ch]
0x180007ae1  lea     ebx, [rsi+rdi]
0x180007ae4  mov     ecx, 1
0x180007ae9  sub     eax, ebx
0x180007aeb  sub     ecx, [rdx-8]
0x180007aee  or      ecx, eax
0x180007af0  jge     short loc_180007AFC
0x180007af2  mov     edx, ebx
0x180007af4  mov     rcx, r14
0x180007af7  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180007afc  mov     rcx, [r14]
0x180007aff  sub     esi, r15d
0x180007b02  movsxd  rax, r15d
0x180007b05  inc     esi
0x180007b07  movsxd  rdx, esi
0x180007b0a  add     rdx, rdx; DestinationSize
0x180007b0d  movsxd  rdi, edi
0x180007b10  mov     r9, rdx; SourceSize
0x180007b13  lea     rsi, [rcx+rax*2]
0x180007b17  add     rax, rdi
0x180007b1a  mov     r8, rsi; Source
0x180007b1d  lea     rcx, [rcx+rax*2]; Destination
0x180007b21  call    cs:__imp_memmove_s
0x180007b27  test    eax, eax
0x180007b29  jz      short loc_180007B3F
0x180007b2b  cmp     eax, 0Ch
0x180007b2e  jz      short loc_180007BA4
0x180007b30  cmp     eax, 16h
0x180007b33  jz      short loc_180007BAF
0x180007b35  cmp     eax, 22h ; '"'
0x180007b38  jz      short loc_180007BAF
0x180007b3a  cmp     eax, 50h ; 'P'
0x180007b3d  jnz     short loc_180007B99
0x180007b3f  lea     rdx, [rdi+rdi]; DestinationSize
0x180007b43  mov     r8, rbp; Source
0x180007b46  mov     r9, rdx; SourceSize
0x180007b49  mov     rcx, rsi; Destination
0x180007b4c  call    cs:__imp_memcpy_s
0x180007b52  test    eax, eax
0x180007b54  jz      short loc_180007B6A
0x180007b56  cmp     eax, 0Ch
0x180007b59  jz      short loc_180007BA4
0x180007b5b  cmp     eax, 16h
0x180007b5e  jz      short loc_180007BAF
0x180007b60  cmp     eax, 22h ; '"'
0x180007b63  jz      short loc_180007BAF
0x180007b65  cmp     eax, 50h ; 'P'
0x180007b68  jnz     short loc_180007B99
0x180007b6a  test    ebx, ebx
0x180007b6c  js      short loc_180007BAF
0x180007b6e  mov     rax, [r14]
0x180007b71  cmp     ebx, [rax-0Ch]
0x180007b74  jg      short loc_180007BAF
0x180007b76  mov     [rax-10h], ebx
0x180007b79  mov     rcx, [r14]
0x180007b7c  movsxd  rdx, ebx
0x180007b7f  mov     [rcx+rdx*2], r12w
0x180007b84  jmp     short loc_180007B88
0x180007b86  mov     ebx, esi
0x180007b88  mov     eax, ebx
0x180007b8a  add     rsp, 20h
0x180007b8e  pop     r15
0x180007b90  pop     r14
0x180007b92  pop     r12
0x180007b94  pop     rdi
0x180007b95  pop     rsi
0x180007b96  pop     rbp
0x180007b97  pop     rbx
0x180007b98  retn
0x180007b99  mov     ecx, 80004005h; int
0x180007b9e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007ba4  mov     ecx, 8007000Eh; int
0x180007ba9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007baf  mov     ecx, 80070057h; int
0x180007bb4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
