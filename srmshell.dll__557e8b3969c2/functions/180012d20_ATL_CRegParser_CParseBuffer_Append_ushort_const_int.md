# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180012d20`
- end: `0x180012e14`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800141f0`

## callees

- `0x1800065bc`
- `0x180012d20`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012db4`
- `msvcrt!memcpy_s` at `0x180012db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012d77`

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
0x180012d20  push    rbx
0x180012d22  push    rbp
0x180012d23  push    rsi
0x180012d24  push    rdi
0x180012d25  sub     rsp, 28h
0x180012d29  mov     rdi, rcx
0x180012d2c  mov     esi, r8d
0x180012d2f  lea     ecx, [r8+1]
0x180012d33  mov     rbp, rdx
0x180012d36  add     ecx, [rdi]
0x180012d38  cmp     ecx, [rdi]
0x180012d3a  jle     loc_180012DE8
0x180012d40  cmp     ecx, r8d
0x180012d43  jle     loc_180012DE8
0x180012d49  mov     ebx, [rdi+4]
0x180012d4c  cmp     ecx, ebx
0x180012d4e  jl      short loc_180012D89
0x180012d50  cmp     ebx, 3FFFFFFFh
0x180012d56  jg      loc_180012DE8
0x180012d5c  add     ebx, ebx
0x180012d5e  cmp     ecx, ebx
0x180012d60  jge     short loc_180012D50
0x180012d62  mov     eax, ebx
0x180012d64  mov     ecx, 0FFFFFFFFh
0x180012d69  add     rax, rax
0x180012d6c  cmp     rax, rcx
0x180012d6f  ja      short loc_180012DE8
0x180012d71  mov     rcx, [rdi+8]; pv
0x180012d75  mov     edx, eax; cb
0x180012d77  call    cs:__imp_CoTaskMemRealloc
0x180012d7d  test    rax, rax
0x180012d80  jz      short loc_180012DE8
0x180012d82  mov     [rdi+8], rax
0x180012d86  mov     [rdi+4], ebx
0x180012d89  cmp     dword ptr [rdi], 0
0x180012d8c  jl      short loc_180012DE8
0x180012d8e  cmp     [rdi], ebx
0x180012d90  jge     short loc_180012DE8
0x180012d92  mov     ecx, ebx
0x180012d94  sub     ecx, [rdi]
0x180012d96  cmp     ecx, ebx
0x180012d98  jg      short loc_180012DE8
0x180012d9a  movsxd  rdx, ecx
0x180012d9d  lea     eax, [rsi+rsi]
0x180012da0  movsxd  rcx, dword ptr [rdi]
0x180012da3  add     rdx, rdx; DestinationSize
0x180012da6  movsxd  r9, eax; SourceSize
0x180012da9  mov     r8, rbp; Source
0x180012dac  mov     rax, [rdi+8]
0x180012db0  lea     rcx, [rax+rcx*2]; Destination
0x180012db4  call    cs:__imp_memcpy_s
0x180012dba  test    eax, eax
0x180012dbc  jz      short loc_180012DD2
0x180012dbe  cmp     eax, 0Ch
0x180012dc1  jz      short loc_180012E09
0x180012dc3  cmp     eax, 16h
0x180012dc6  jz      short loc_180012DFE
0x180012dc8  cmp     eax, 22h ; '"'
0x180012dcb  jz      short loc_180012DFE
0x180012dcd  cmp     eax, 50h ; 'P'
0x180012dd0  jnz     short loc_180012DF3
0x180012dd2  add     [rdi], esi
0x180012dd4  movsxd  rdx, dword ptr [rdi]
0x180012dd7  xor     eax, eax
0x180012dd9  mov     rcx, [rdi+8]
0x180012ddd  mov     [rcx+rdx*2], ax
0x180012de1  mov     eax, 1
0x180012de6  jmp     short loc_180012DEA
0x180012de8  xor     eax, eax
0x180012dea  add     rsp, 28h
0x180012dee  pop     rdi
0x180012def  pop     rsi
0x180012df0  pop     rbp
0x180012df1  pop     rbx
0x180012df2  retn
0x180012df3  mov     ecx, 80004005h; int
0x180012df8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012dfe  mov     ecx, 80070057h; int
0x180012e03  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012e09  mov     ecx, 8007000Eh; int
0x180012e0e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
