# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180025d84`
- end: `0x180025e44`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180029c78`

## callees

- `0x180025d84`
- `0x180025f74`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180025e16`
- `msvcrt!memcpy_s` at `0x180025e16`
- `ole32!CoTaskMemRealloc` at `0x180025dd9`
- `ole32!CoTaskMemRealloc` at `0x180025dd9`

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
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 >= v7 )
    {
      while ( v6 >= v7 )
      {
        if ( v7 > 0x3FFFFFFF )
          return 0;
        v7 *= 2;
      }
      v8 = 2LL * (unsigned int)v7;
      if ( v8 > 0xFFFFFFFF )
        return 0;
      v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
      if ( !v9 )
        return 0;
      *((_QWORD *)this + 1) = v9;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v10 = v7 - *(_DWORD *)this;
      if ( v10 <= v7 )
      {
        v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v11);
        *(_DWORD *)this += a3;
        *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180025d84  push    rbx
0x180025d86  push    rbp
0x180025d87  push    rsi
0x180025d88  push    rdi
0x180025d89  sub     rsp, 28h
0x180025d8d  mov     rdi, rcx
0x180025d90  mov     esi, r8d
0x180025d93  lea     ecx, [r8+1]
0x180025d97  mov     rbp, rdx
0x180025d9a  add     ecx, [rdi]
0x180025d9c  cmp     ecx, [rdi]
0x180025d9e  jle     loc_180025E39
0x180025da4  cmp     ecx, r8d
0x180025da7  jle     loc_180025E39
0x180025dad  mov     ebx, [rdi+4]
0x180025db0  cmp     ecx, ebx
0x180025db2  jl      short loc_180025DEB
0x180025db4  cmp     ecx, ebx
0x180025db6  jl      short loc_180025DC4
0x180025db8  cmp     ebx, 3FFFFFFFh
0x180025dbe  jg      short loc_180025E39
0x180025dc0  add     ebx, ebx
0x180025dc2  jmp     short loc_180025DB4
0x180025dc4  mov     eax, ebx
0x180025dc6  mov     ecx, 0FFFFFFFFh
0x180025dcb  add     rax, rax
0x180025dce  cmp     rax, rcx
0x180025dd1  ja      short loc_180025E39
0x180025dd3  mov     rcx, [rdi+8]; pv
0x180025dd7  mov     edx, eax; cb
0x180025dd9  call    cs:__imp_CoTaskMemRealloc
0x180025ddf  test    rax, rax
0x180025de2  jz      short loc_180025E39
0x180025de4  mov     [rdi+8], rax
0x180025de8  mov     [rdi+4], ebx
0x180025deb  cmp     dword ptr [rdi], 0
0x180025dee  jl      short loc_180025E39
0x180025df0  cmp     [rdi], ebx
0x180025df2  jge     short loc_180025E39
0x180025df4  mov     ecx, ebx
0x180025df6  sub     ecx, [rdi]
0x180025df8  cmp     ecx, ebx
0x180025dfa  jg      short loc_180025E39
0x180025dfc  movsxd  rdx, ecx
0x180025dff  lea     eax, [rsi+rsi]
0x180025e02  movsxd  rcx, dword ptr [rdi]
0x180025e05  add     rdx, rdx; DestinationSize
0x180025e08  movsxd  r9, eax; SourceSize
0x180025e0b  mov     r8, rbp; Source
0x180025e0e  mov     rax, [rdi+8]
0x180025e12  lea     rcx, [rax+rcx*2]; Destination
0x180025e16  call    cs:__imp_memcpy_s
0x180025e1c  mov     ecx, eax; int
0x180025e1e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180025e23  add     [rdi], esi
0x180025e25  movsxd  rdx, dword ptr [rdi]
0x180025e28  xor     eax, eax
0x180025e2a  mov     rcx, [rdi+8]
0x180025e2e  mov     [rcx+rdx*2], ax
0x180025e32  mov     eax, 1
0x180025e37  jmp     short loc_180025E3B
0x180025e39  xor     eax, eax
0x180025e3b  add     rsp, 28h
0x180025e3f  pop     rdi
0x180025e40  pop     rsi
0x180025e41  pop     rbp
0x180025e42  pop     rbx
0x180025e43  retn
```
