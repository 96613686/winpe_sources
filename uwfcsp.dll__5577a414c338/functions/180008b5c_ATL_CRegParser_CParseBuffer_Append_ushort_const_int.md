# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180008b5c`
- end: `0x180008c50`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009c8c`

## callees

- `0x180008b5c`
- `0x180008c94`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008bf0`
- `msvcrt!memcpy_s` at `0x180008bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008bb3`

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
0x180008b5c  push    rbx
0x180008b5e  push    rbp
0x180008b5f  push    rsi
0x180008b60  push    rdi
0x180008b61  sub     rsp, 28h
0x180008b65  mov     rdi, rcx
0x180008b68  mov     esi, r8d
0x180008b6b  lea     ecx, [r8+1]
0x180008b6f  mov     rbp, rdx
0x180008b72  add     ecx, [rdi]
0x180008b74  cmp     ecx, [rdi]
0x180008b76  jle     loc_180008C24
0x180008b7c  cmp     ecx, r8d
0x180008b7f  jle     loc_180008C24
0x180008b85  mov     ebx, [rdi+4]
0x180008b88  cmp     ecx, ebx
0x180008b8a  jl      short loc_180008BC5
0x180008b8c  cmp     ebx, 3FFFFFFFh
0x180008b92  jg      loc_180008C24
0x180008b98  add     ebx, ebx
0x180008b9a  cmp     ecx, ebx
0x180008b9c  jge     short loc_180008B8C
0x180008b9e  mov     eax, ebx
0x180008ba0  mov     ecx, 0FFFFFFFFh
0x180008ba5  add     rax, rax
0x180008ba8  cmp     rax, rcx
0x180008bab  ja      short loc_180008C24
0x180008bad  mov     rcx, [rdi+8]; pv
0x180008bb1  mov     edx, eax; cb
0x180008bb3  call    cs:__imp_CoTaskMemRealloc
0x180008bb9  test    rax, rax
0x180008bbc  jz      short loc_180008C24
0x180008bbe  mov     [rdi+8], rax
0x180008bc2  mov     [rdi+4], ebx
0x180008bc5  cmp     dword ptr [rdi], 0
0x180008bc8  jl      short loc_180008C24
0x180008bca  cmp     [rdi], ebx
0x180008bcc  jge     short loc_180008C24
0x180008bce  mov     ecx, ebx
0x180008bd0  sub     ecx, [rdi]
0x180008bd2  cmp     ecx, ebx
0x180008bd4  jg      short loc_180008C24
0x180008bd6  movsxd  rdx, ecx
0x180008bd9  lea     eax, [rsi+rsi]
0x180008bdc  movsxd  rcx, dword ptr [rdi]
0x180008bdf  add     rdx, rdx; DestinationSize
0x180008be2  movsxd  r9, eax; SourceSize
0x180008be5  mov     r8, rbp; Source
0x180008be8  mov     rax, [rdi+8]
0x180008bec  lea     rcx, [rax+rcx*2]; Destination
0x180008bf0  call    cs:__imp_memcpy_s
0x180008bf6  test    eax, eax
0x180008bf8  jz      short loc_180008C0E
0x180008bfa  cmp     eax, 0Ch
0x180008bfd  jz      short loc_180008C45
0x180008bff  cmp     eax, 16h
0x180008c02  jz      short loc_180008C3A
0x180008c04  cmp     eax, 22h ; '"'
0x180008c07  jz      short loc_180008C3A
0x180008c09  cmp     eax, 50h ; 'P'
0x180008c0c  jnz     short loc_180008C2F
0x180008c0e  add     [rdi], esi
0x180008c10  movsxd  rdx, dword ptr [rdi]
0x180008c13  xor     eax, eax
0x180008c15  mov     rcx, [rdi+8]
0x180008c19  mov     [rcx+rdx*2], ax
0x180008c1d  mov     eax, 1
0x180008c22  jmp     short loc_180008C26
0x180008c24  xor     eax, eax
0x180008c26  add     rsp, 28h
0x180008c2a  pop     rdi
0x180008c2b  pop     rsi
0x180008c2c  pop     rbp
0x180008c2d  pop     rbx
0x180008c2e  retn
0x180008c2f  mov     ecx, 80004005h; int
0x180008c34  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008c3a  mov     ecx, 80070057h; int
0x180008c3f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008c45  mov     ecx, 8007000Eh; int
0x180008c4a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
