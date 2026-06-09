# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800040ac`
- end: `0x1800041b1`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `261`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ab0c`

## callees

- `0x1800040ac`
- `0x1800041f8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000414a`
- `msvcrt!memcpy_s` at `0x18000414a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004107`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004107`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // ecx
  errno_t v11; // eax

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 <= *(_DWORD *)this || v6 <= a3 )
    return 0;
  v7 = *((_DWORD *)this + 1);
  if ( v6 >= v7 )
  {
    while ( v7 <= 0x3FFFFFFF )
    {
      v7 *= 2;
      if ( v6 < v7 )
      {
        v8 = 2LL * (unsigned int)v7;
        if ( v8 <= 0xFFFFFFFF )
        {
          v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
          if ( v9 )
          {
            *((_QWORD *)this + 1) = v9;
            *((_DWORD *)this + 1) = v7;
            goto LABEL_9;
          }
        }
        return 0;
      }
    }
    return 0;
  }
LABEL_9:
  if ( *(int *)this < 0 )
    return 0;
  if ( *(_DWORD *)this >= v7 )
    return 0;
  v10 = v7 - *(_DWORD *)this;
  if ( v10 > v7 )
    return 0;
  v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
  if ( v11 )
  {
    if ( v11 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v11 == 22 || v11 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v11 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *(_DWORD *)this += a3;
  *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
  return 1;
}

```

## disassembly

```asm
0x1800040ac  push    rbx
0x1800040ae  push    rbp
0x1800040af  push    rsi
0x1800040b0  push    rdi
0x1800040b1  sub     rsp, 28h
0x1800040b5  mov     rdi, rcx
0x1800040b8  mov     esi, r8d
0x1800040bb  lea     ecx, [r8+1]
0x1800040bf  mov     rbp, rdx
0x1800040c2  add     ecx, [rdi]
0x1800040c4  cmp     ecx, [rdi]
0x1800040c6  jle     loc_180004184
0x1800040cc  cmp     ecx, r8d
0x1800040cf  jle     loc_180004184
0x1800040d5  mov     ebx, [rdi+4]
0x1800040d8  cmp     ecx, ebx
0x1800040da  jl      short loc_18000411F
0x1800040dc  cmp     ebx, 3FFFFFFFh
0x1800040e2  jg      loc_180004184
0x1800040e8  add     ebx, ebx
0x1800040ea  cmp     ecx, ebx
0x1800040ec  jge     short loc_1800040DC
0x1800040ee  mov     eax, ebx
0x1800040f0  mov     ecx, 0FFFFFFFFh
0x1800040f5  add     rax, rax
0x1800040f8  cmp     rax, rcx
0x1800040fb  ja      loc_180004184
0x180004101  mov     rcx, [rdi+8]; pv
0x180004105  mov     edx, eax; cb
0x180004107  call    cs:__imp_CoTaskMemRealloc
0x18000410e  nop     dword ptr [rax+rax+00h]
0x180004113  test    rax, rax
0x180004116  jz      short loc_180004184
0x180004118  mov     [rdi+8], rax
0x18000411c  mov     [rdi+4], ebx
0x18000411f  cmp     dword ptr [rdi], 0
0x180004122  jl      short loc_180004184
0x180004124  cmp     [rdi], ebx
0x180004126  jge     short loc_180004184
0x180004128  mov     ecx, ebx
0x18000412a  sub     ecx, [rdi]
0x18000412c  cmp     ecx, ebx
0x18000412e  jg      short loc_180004184
0x180004130  movsxd  rdx, ecx
0x180004133  lea     eax, [rsi+rsi]
0x180004136  movsxd  rcx, dword ptr [rdi]
0x180004139  add     rdx, rdx; DestinationSize
0x18000413c  movsxd  r9, eax; SourceSize
0x18000413f  mov     r8, rbp; Source
0x180004142  mov     rax, [rdi+8]
0x180004146  lea     rcx, [rax+rcx*2]; Destination
0x18000414a  call    cs:__imp_memcpy_s
0x180004151  nop     dword ptr [rax+rax+00h]
0x180004156  test    eax, eax
0x180004158  jz      short loc_18000416E
0x18000415a  cmp     eax, 0Ch
0x18000415d  jz      short loc_1800041A6
0x18000415f  cmp     eax, 16h
0x180004162  jz      short loc_18000419B
0x180004164  cmp     eax, 22h ; '"'
0x180004167  jz      short loc_18000419B
0x180004169  cmp     eax, 50h ; 'P'
0x18000416c  jnz     short loc_180004190
0x18000416e  add     [rdi], esi
0x180004170  movsxd  rdx, dword ptr [rdi]
0x180004173  xor     eax, eax
0x180004175  mov     rcx, [rdi+8]
0x180004179  mov     [rcx+rdx*2], ax
0x18000417d  mov     eax, 1
0x180004182  jmp     short loc_180004186
0x180004184  xor     eax, eax
0x180004186  add     rsp, 28h
0x18000418a  pop     rdi
0x18000418b  pop     rsi
0x18000418c  pop     rbp
0x18000418d  pop     rbx
0x18000418e  retn
0x180004190  mov     ecx, 80004005h; int
0x180004195  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000419b  mov     ecx, 80070057h; int
0x1800041a0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800041a6  mov     ecx, 8007000Eh; int
0x1800041ab  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
