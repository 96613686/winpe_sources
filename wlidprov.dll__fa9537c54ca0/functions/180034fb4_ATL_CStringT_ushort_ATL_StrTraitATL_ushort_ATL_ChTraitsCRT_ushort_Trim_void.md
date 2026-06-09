# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)

- ea: `0x180034fb4`
- end: `0x18003507f`
- name: `?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800332a0`

## callees

- `0x180003250`
- `0x180003cb0`
- `0x180015788`
- `0x180025a38`
- `0x180034fb4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18003505c`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18003505c`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180034fd2`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18003501b`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180034fd2`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18003501b`

## pseudocode

```c
unsigned __int16 **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(
        unsigned __int16 **a1)
{
  unsigned __int16 *v1; // rsi
  unsigned __int16 v3; // ax
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rax
  unsigned __int16 *i; // rsi
  unsigned __int16 *v7; // rdx
  __int64 v8; // rsi
  char *v9; // rax
  unsigned int v10; // ebx
  errno_t v11; // eax

  v1 = *a1;
  v3 = **a1;
  if ( v3 )
  {
    v4 = 0;
    do
    {
      if ( (unsigned int)_o_iswspace(v3) )
      {
        v5 = v1;
        if ( v4 )
          v5 = v4;
        v4 = v5;
      }
      else
      {
        v4 = 0;
      }
      v3 = *++v1;
    }
    while ( *v1 );
    if ( v4 )
      ATL::CSimpleStringT<unsigned short,0>::Truncate(a1, (unsigned int)(v4 - *a1));
  }
  for ( i = *a1; (unsigned int)_o_iswspace(*i); ++i )
    ;
  v7 = *a1;
  if ( i != *a1 )
  {
    v8 = i - v7;
    v9 = (char *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(a1, *((unsigned int *)v7 - 4));
    v10 = *((_DWORD *)*a1 - 4) - v8;
    v11 = memmove_s(v9, 2LL * (int)(v10 + 1), &v9[2 * (int)v8], 2LL * (int)(v10 + 1));
    ATL::AtlCrtErrorCheck(v11);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v10);
  }
  return a1;
}

```

## disassembly

```asm
0x180034fb4  push    rbx
0x180034fb6  push    rbp
0x180034fb7  push    rsi
0x180034fb8  push    rdi
0x180034fb9  sub     rsp, 28h
0x180034fbd  mov     rsi, [rcx]
0x180034fc0  xor     ebp, ebp
0x180034fc2  mov     rdi, rcx
0x180034fc5  movzx   eax, word ptr [rsi]
0x180034fc8  test    ax, ax
0x180034fcb  jz      short loc_18003500F
0x180034fcd  mov     ebx, ebp
0x180034fcf  movzx   ecx, ax
0x180034fd2  call    cs:__imp__o_iswspace
0x180034fd8  test    eax, eax
0x180034fda  jz      short loc_180034FEB
0x180034fdc  test    rbx, rbx
0x180034fdf  mov     rax, rsi
0x180034fe2  cmovnz  rax, rbx
0x180034fe6  mov     rbx, rax
0x180034fe9  jmp     short loc_180034FEE
0x180034feb  mov     rbx, rbp
0x180034fee  add     rsi, 2
0x180034ff2  movzx   eax, word ptr [rsi]
0x180034ff5  test    ax, ax
0x180034ff8  jnz     short loc_180034FCF
0x180034ffa  test    rbx, rbx
0x180034ffd  jz      short loc_18003500F
0x180034fff  sub     rbx, [rdi]
0x180035002  mov     rcx, rdi
0x180035005  sar     rbx, 1
0x180035008  mov     edx, ebx
0x18003500a  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18003500f  mov     rsi, [rdi]
0x180035012  jmp     short loc_180035018
0x180035014  add     rsi, 2
0x180035018  movzx   ecx, word ptr [rsi]
0x18003501b  call    cs:__imp__o_iswspace
0x180035021  test    eax, eax
0x180035023  jnz     short loc_180035014
0x180035025  mov     rdx, [rdi]
0x180035028  cmp     rsi, rdx
0x18003502b  jz      short loc_180035073
0x18003502d  sub     rsi, rdx
0x180035030  mov     rcx, rdi
0x180035033  mov     edx, [rdx-10h]
0x180035036  sar     rsi, 1
0x180035039  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18003503e  mov     rcx, [rdi]
0x180035041  mov     ebx, [rcx-10h]
0x180035044  sub     ebx, esi
0x180035046  lea     ecx, [rbx+1]
0x180035049  movsxd  rdx, ecx
0x18003504c  movsxd  rcx, esi
0x18003504f  add     rdx, rdx; DestinationSize
0x180035052  mov     r9, rdx; SourceSize
0x180035055  lea     r8, [rax+rcx*2]; Source
0x180035059  mov     rcx, rax; Destination
0x18003505c  call    cs:__imp_memmove_s
0x180035062  mov     ecx, eax; int
0x180035064  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180035069  mov     edx, ebx
0x18003506b  mov     rcx, rdi
0x18003506e  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180035073  mov     rax, rdi
0x180035076  add     rsp, 28h
0x18003507a  pop     rdi
0x18003507b  pop     rsi
0x18003507c  pop     rbp
0x18003507d  pop     rbx
0x18003507e  retn
```
