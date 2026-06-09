# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18001ff88`
- end: `0x18002019c`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e334`

## callees

- `0x1800085b8`
- `0x18000dd14`
- `0x18001ff88`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800200f4`
- `msvcrt!memcpy_s` at `0x1800200f4`
- `msvcrt!memmove_s` at `0x1800200ac`
- `msvcrt!memmove_s` at `0x1800200ac`
- `msvcrt!wcsstr` at `0x18001ffd1`
- `msvcrt!wcsstr` at `0x180020135`
- `msvcrt!wcsstr` at `0x18001ffd1`
- `msvcrt!wcsstr` at `0x180020135`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        const wchar_t **a1)
{
  const wchar_t *v1; // rbx
  int v3; // r14d
  unsigned __int64 v4; // rbp
  wchar_t *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbp
  int v8; // ebx
  __int64 v9; // rdx
  const wchar_t *v10; // r12
  const wchar_t *v11; // rdi
  unsigned __int64 v12; // r13
  errno_t v14; // eax
  errno_t v15; // eax
  wchar_t *v16; // rax
  wchar_t *v17; // r15
  __int64 v18; // rax
  int v19; // [rsp+80h] [rbp+18h]

  v1 = *a1;
  v3 = 0;
  v4 = (unsigned __int64)&(*a1)[*((int *)*a1 - 4)];
  if ( (unsigned __int64)*a1 < v4 )
  {
    do
    {
      while ( 1 )
      {
        v5 = wcsstr(v1, L"\\Framework64\\");
        if ( !v5 )
          break;
        ++v3;
        v1 = v5 + 13;
      }
      if ( v1 )
      {
        v6 = -1;
        do
          ++v6;
        while ( v1[v6] );
      }
      else
      {
        LODWORD(v6) = 0;
      }
      v1 += (int)v6 + 1;
    }
    while ( (unsigned __int64)v1 < v4 );
    if ( v3 > 0 )
    {
      v7 = *((int *)*a1 - 4);
      v8 = *((_DWORD *)*a1 - 4) - 2 * v3;
      v9 = (unsigned int)v8;
      if ( v8 <= (int)v7 )
        v9 = (unsigned int)v7;
      if ( (int)((*((_DWORD *)*a1 - 3) - v9) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v9);
      v10 = *a1;
      v11 = *a1;
      v12 = (unsigned __int64)&(*a1)[v7];
      if ( (unsigned __int64)*a1 < v12 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v16 = wcsstr(v11, L"\\Framework64\\");
            v17 = v16;
            if ( v16 )
              break;
            if ( v11 )
            {
              v18 = -1;
              do
                ++v18;
              while ( v11[v18] );
            }
            else
            {
              LODWORD(v18) = 0;
            }
            v11 += (int)v18 + 1;
            if ( (unsigned __int64)v11 >= v12 )
              goto LABEL_17;
          }
          v11 = v16 + 11;
          v19 = v7 - (v16 - v10) - 13;
          v14 = memmove_s(v16 + 11, 2LL * v19, v16 + 13, 2LL * v19);
          if ( v14 )
          {
            if ( v14 == 12 )
              goto LABEL_40;
            if ( v14 == 22 || v14 == 34 )
              goto LABEL_41;
            if ( v14 != 80 )
              goto LABEL_42;
          }
          v15 = memcpy_s(v17, 0x16u, L"\\Framework\\", 0x16u);
          if ( v15 )
          {
            if ( v15 == 12 )
LABEL_40:
              ATL::AtlThrowImpl(-2147024882);
            if ( v15 == 22 || v15 == 34 )
              goto LABEL_41;
            if ( v15 != 80 )
LABEL_42:
              ATL::AtlThrowImpl(-2147467259);
          }
          LODWORD(v7) = v7 - 2;
          v17[v19 + 11] = 0;
        }
      }
LABEL_17:
      if ( v8 < 0 || v8 > *((_DWORD *)*a1 - 3) )
LABEL_41:
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)*a1 - 4) = v8;
      (*a1)[v8] = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001ff88  mov     [rsp+arg_10], r8
0x18001ff8d  push    rbx
0x18001ff8e  push    rbp
0x18001ff8f  push    rsi
0x18001ff90  push    rdi
0x18001ff91  push    r12
0x18001ff93  push    r13
0x18001ff95  push    r14
0x18001ff97  push    r15
0x18001ff99  sub     rsp, 28h
0x18001ff9d  mov     rbx, [rcx]
0x18001ffa0  xor     r15d, r15d
0x18001ffa3  mov     rsi, rcx
0x18001ffa6  mov     r14d, r15d
0x18001ffa9  movsxd  rax, dword ptr [rbx-10h]
0x18001ffad  lea     rbp, [rbx+rax*2]
0x18001ffb1  cmp     rbx, rbp
0x18001ffb4  jnb     loc_18002006C
0x18001ffba  lea     edi, [r15+1]
0x18001ffbe  jmp     short loc_18001FFC7
0x18001ffc0  add     r14d, edi
0x18001ffc3  lea     rbx, [rax+1Ah]
0x18001ffc7  lea     rdx, aFramework64; "\\Framework64\\"
0x18001ffce  mov     rcx, rbx; Str
0x18001ffd1  call    cs:__imp_wcsstr
0x18001ffd8  nop     dword ptr [rax+rax+00h]
0x18001ffdd  test    rax, rax
0x18001ffe0  jnz     short loc_18001FFC0
0x18001ffe2  test    rbx, rbx
0x18001ffe5  jz      short loc_18001FFF7
0x18001ffe7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ffeb  inc     rax
0x18001ffee  cmp     [rbx+rax*2], r15w
0x18001fff3  jnz     short loc_18001FFEB
0x18001fff5  jmp     short loc_18001FFFA
0x18001fff7  mov     eax, r15d
0x18001fffa  inc     eax
0x18001fffc  movsxd  rcx, eax
0x18001ffff  lea     rbx, [rbx+rcx*2]
0x180020003  cmp     rbx, rbp
0x180020006  jb      short loc_18001FFC7
0x180020008  test    r14d, r14d
0x18002000b  jle     short loc_18002006C
0x18002000d  mov     rcx, [rsi]
0x180020010  lea     eax, [r14+r14]
0x180020014  movsxd  rbp, dword ptr [rcx-10h]
0x180020018  mov     ebx, ebp
0x18002001a  sub     ebx, eax
0x18002001c  mov     eax, [rcx-0Ch]
0x18002001f  cmp     ebx, ebp
0x180020021  mov     edx, ebx
0x180020023  cmovle  edx, ebp
0x180020026  sub     edi, [rcx-8]
0x180020029  sub     eax, edx
0x18002002b  or      edi, eax
0x18002002d  jge     short loc_180020037
0x18002002f  mov     rcx, rsi
0x180020032  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180020037  mov     r12, [rsi]
0x18002003a  mov     rdi, r12
0x18002003d  lea     r13, [r12+rbp*2]
0x180020041  cmp     r12, r13
0x180020044  jb      loc_18002012B
0x18002004a  test    ebx, ebx
0x18002004c  js      loc_180020186
0x180020052  mov     rax, [rsi]
0x180020055  cmp     ebx, [rax-0Ch]
0x180020058  jg      loc_180020186
0x18002005e  mov     [rax-10h], ebx
0x180020061  mov     rcx, [rsi]
0x180020064  movsxd  rdx, ebx
0x180020067  mov     [rcx+rdx*2], r15w
0x18002006c  mov     eax, r14d
0x18002006f  add     rsp, 28h
0x180020073  pop     r15
0x180020075  pop     r14
0x180020077  pop     r13
0x180020079  pop     r12
0x18002007b  pop     rdi
0x18002007c  pop     rsi
0x18002007d  pop     rbp
0x18002007e  pop     rbx
0x18002007f  retn
0x180020081  mov     eax, ebp
0x180020083  lea     rdi, [r15+16h]
0x180020087  mov     rcx, r15
0x18002008a  lea     r8, [r15+1Ah]; Source
0x18002008e  sub     rcx, r12
0x180020091  sar     rcx, 1
0x180020094  sub     eax, ecx
0x180020096  mov     rcx, rdi; Destination
0x180020099  add     eax, 0FFFFFFF3h
0x18002009c  movsxd  rdx, eax
0x18002009f  add     rdx, rdx; DestinationSize
0x1800200a2  mov     dword ptr [rsp+68h+arg_10], eax
0x1800200a9  mov     r9, rdx; SourceSize
0x1800200ac  call    cs:__imp_memmove_s
0x1800200b3  nop     dword ptr [rax+rax+00h]
0x1800200b8  test    eax, eax
0x1800200ba  jz      short loc_1800200E0
0x1800200bc  cmp     eax, 0Ch
0x1800200bf  jz      loc_18002017B
0x1800200c5  cmp     eax, 16h
0x1800200c8  jz      loc_180020186
0x1800200ce  cmp     eax, 22h ; '"'
0x1800200d1  jz      loc_180020186
0x1800200d7  cmp     eax, 50h ; 'P'
0x1800200da  jnz     loc_180020191
0x1800200e0  mov     eax, 16h
0x1800200e5  lea     r8, aFramework; "\\Framework\\"
0x1800200ec  mov     r9d, eax; SourceSize
0x1800200ef  mov     edx, eax; DestinationSize
0x1800200f1  mov     rcx, r15; Destination
0x1800200f4  call    cs:__imp_memcpy_s
0x1800200fb  nop     dword ptr [rax+rax+00h]
0x180020100  test    eax, eax
0x180020102  jz      short loc_180020118
0x180020104  cmp     eax, 0Ch
0x180020107  jz      short loc_18002017B
0x180020109  cmp     eax, 16h
0x18002010c  jz      short loc_180020186
0x18002010e  cmp     eax, 22h ; '"'
0x180020111  jz      short loc_180020186
0x180020113  cmp     eax, 50h ; 'P'
0x180020116  jnz     short loc_180020191
0x180020118  movsxd  rcx, dword ptr [rsp+68h+arg_10]
0x180020120  xor     eax, eax
0x180020122  sub     ebp, 2
0x180020125  mov     [r15+rcx*2+16h], ax
0x18002012b  lea     rdx, aFramework64; "\\Framework64\\"
0x180020132  mov     rcx, rdi; Str
0x180020135  call    cs:__imp_wcsstr
0x18002013c  nop     dword ptr [rax+rax+00h]
0x180020141  mov     r15, rax
0x180020144  test    rax, rax
0x180020147  jnz     loc_180020081
0x18002014d  xor     r15d, r15d
0x180020150  test    rdi, rdi
0x180020153  jz      short loc_180020165
0x180020155  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020159  inc     rax
0x18002015c  cmp     [rdi+rax*2], r15w
0x180020161  jnz     short loc_180020159
0x180020163  jmp     short loc_180020168
0x180020165  mov     eax, r15d
0x180020168  inc     eax
0x18002016a  movsxd  rcx, eax
0x18002016d  lea     rdi, [rdi+rcx*2]
0x180020171  cmp     rdi, r13
0x180020174  jb      short loc_18002012B
0x180020176  jmp     loc_18002004A
0x18002017b  mov     ecx, 8007000Eh; int
0x180020180  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180020186  mov     ecx, 80070057h; int
0x18002018b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180020191  mov     ecx, 80004005h; int
0x180020196  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
