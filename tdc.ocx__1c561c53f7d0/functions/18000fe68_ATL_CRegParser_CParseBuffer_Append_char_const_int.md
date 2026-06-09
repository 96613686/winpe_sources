# ATL::CRegParser::CParseBuffer::Append(char const *,int)

- ea: `0x18000fe68`
- end: `0x18000ff3b`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBDH@Z`
- size: `211`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f68c`
- `0x1800111c8`

## callees

- `0x180003b70`
- `0x18000fe68`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000fedd`
- `msvcrt!memcpy_s` at `0x18000fedd`
- `ole32!CoTaskMemRealloc` at `0x18000feaa`
- `ole32!CoTaskMemRealloc` at `0x18000feaa`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(ATL::CRegParser::CParseBuffer *this, const char *a2, int a3)
{
  rsize_t v4; // rsi
  int v6; // ecx
  int v7; // ebx
  LPVOID v8; // rax
  int v9; // eax
  errno_t v10; // eax

  v4 = a3;
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
        v8 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v7);
        if ( !v8 )
          return 0;
        *((_QWORD *)this + 1) = v8;
        *((_DWORD *)this + 1) = v7;
        goto LABEL_8;
      }
    }
    return 0;
  }
LABEL_8:
  if ( *(int *)this < 0 )
    return 0;
  if ( *(_DWORD *)this >= v7 )
    return 0;
  v9 = v7 - *(_DWORD *)this;
  if ( v9 > v7 )
    return 0;
  v10 = memcpy_s((void *const)(*((_QWORD *)this + 1) + *(int *)this), v9, a2, v4);
  if ( v10 )
  {
    if ( v10 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v10 == 22 || v10 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v10 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *(_DWORD *)this += v4;
  *(_BYTE *)(*(int *)this + *((_QWORD *)this + 1)) = 0;
  return 1;
}

```

## disassembly

```asm
0x18000fe68  push    rbx
0x18000fe6a  push    rbp
0x18000fe6b  push    rsi
0x18000fe6c  push    rdi
0x18000fe6d  sub     rsp, 28h
0x18000fe71  mov     rdi, rcx
0x18000fe74  movsxd  rsi, r8d
0x18000fe77  mov     rbp, rdx
0x18000fe7a  lea     ecx, [rsi+1]
0x18000fe7d  add     ecx, [rdi]
0x18000fe7f  cmp     ecx, [rdi]
0x18000fe81  jle     loc_18000FF0F
0x18000fe87  cmp     ecx, esi
0x18000fe89  jle     loc_18000FF0F
0x18000fe8f  mov     ebx, [rdi+4]
0x18000fe92  cmp     ecx, ebx
0x18000fe94  jl      short loc_18000FEBC
0x18000fe96  cmp     ebx, 3FFFFFFFh
0x18000fe9c  jg      short loc_18000FF0F
0x18000fe9e  add     ebx, ebx
0x18000fea0  cmp     ecx, ebx
0x18000fea2  jge     short loc_18000FE96
0x18000fea4  mov     rcx, [rdi+8]; pv
0x18000fea8  mov     edx, ebx; cb
0x18000feaa  call    cs:__imp_CoTaskMemRealloc
0x18000feb0  test    rax, rax
0x18000feb3  jz      short loc_18000FF0F
0x18000feb5  mov     [rdi+8], rax
0x18000feb9  mov     [rdi+4], ebx
0x18000febc  cmp     dword ptr [rdi], 0
0x18000febf  jl      short loc_18000FF0F
0x18000fec1  cmp     [rdi], ebx
0x18000fec3  jge     short loc_18000FF0F
0x18000fec5  mov     eax, ebx
0x18000fec7  sub     eax, [rdi]
0x18000fec9  cmp     eax, ebx
0x18000fecb  jg      short loc_18000FF0F
0x18000fecd  movsxd  rcx, dword ptr [rdi]
0x18000fed0  mov     r9, rsi; SourceSize
0x18000fed3  add     rcx, [rdi+8]; Destination
0x18000fed7  mov     r8, rbp; Source
0x18000feda  movsxd  rdx, eax; DestinationSize
0x18000fedd  call    cs:__imp_memcpy_s
0x18000fee3  test    eax, eax
0x18000fee5  jz      short loc_18000FEFB
0x18000fee7  cmp     eax, 0Ch
0x18000feea  jz      short loc_18000FF30
0x18000feec  cmp     eax, 16h
0x18000feef  jz      short loc_18000FF25
0x18000fef1  cmp     eax, 22h ; '"'
0x18000fef4  jz      short loc_18000FF25
0x18000fef6  cmp     eax, 50h ; 'P'
0x18000fef9  jnz     short loc_18000FF1A
0x18000fefb  add     [rdi], esi
0x18000fefd  mov     rax, [rdi+8]
0x18000ff01  movsxd  rcx, dword ptr [rdi]
0x18000ff04  mov     byte ptr [rcx+rax], 0
0x18000ff08  mov     eax, 1
0x18000ff0d  jmp     short loc_18000FF11
0x18000ff0f  xor     eax, eax
0x18000ff11  add     rsp, 28h
0x18000ff15  pop     rdi
0x18000ff16  pop     rsi
0x18000ff17  pop     rbp
0x18000ff18  pop     rbx
0x18000ff19  retn
0x18000ff1a  mov     ecx, 80004005h; int
0x18000ff1f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ff25  mov     ecx, 80070057h; int
0x18000ff2a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ff30  mov     ecx, 8007000Eh; int
0x18000ff35  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
