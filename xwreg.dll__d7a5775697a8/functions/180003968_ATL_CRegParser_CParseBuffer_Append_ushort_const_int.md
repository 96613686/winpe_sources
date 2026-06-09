# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003968`
- end: `0x180003a28`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004d18`

## callees

- `0x180003968`
- `0x180003b44`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800039fa`
- `msvcrt!memcpy_s` at `0x1800039fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800039bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800039bd`

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
0x180003968  push    rbx
0x18000396a  push    rbp
0x18000396b  push    rsi
0x18000396c  push    rdi
0x18000396d  sub     rsp, 28h
0x180003971  mov     rdi, rcx
0x180003974  mov     esi, r8d
0x180003977  lea     ecx, [r8+1]
0x18000397b  mov     rbp, rdx
0x18000397e  add     ecx, [rdi]
0x180003980  cmp     ecx, [rdi]
0x180003982  jle     loc_180003A1D
0x180003988  cmp     ecx, r8d
0x18000398b  jle     loc_180003A1D
0x180003991  mov     ebx, [rdi+4]
0x180003994  cmp     ecx, ebx
0x180003996  jl      short loc_1800039CF
0x180003998  cmp     ecx, ebx
0x18000399a  jl      short loc_1800039A8
0x18000399c  cmp     ebx, 3FFFFFFFh
0x1800039a2  jg      short loc_180003A1D
0x1800039a4  add     ebx, ebx
0x1800039a6  jmp     short loc_180003998
0x1800039a8  mov     eax, ebx
0x1800039aa  mov     ecx, 0FFFFFFFFh
0x1800039af  add     rax, rax
0x1800039b2  cmp     rax, rcx
0x1800039b5  ja      short loc_180003A1D
0x1800039b7  mov     rcx, [rdi+8]; pv
0x1800039bb  mov     edx, eax; cb
0x1800039bd  call    cs:__imp_CoTaskMemRealloc
0x1800039c3  test    rax, rax
0x1800039c6  jz      short loc_180003A1D
0x1800039c8  mov     [rdi+8], rax
0x1800039cc  mov     [rdi+4], ebx
0x1800039cf  cmp     dword ptr [rdi], 0
0x1800039d2  jl      short loc_180003A1D
0x1800039d4  cmp     [rdi], ebx
0x1800039d6  jge     short loc_180003A1D
0x1800039d8  mov     ecx, ebx
0x1800039da  sub     ecx, [rdi]
0x1800039dc  cmp     ecx, ebx
0x1800039de  jg      short loc_180003A1D
0x1800039e0  movsxd  rdx, ecx
0x1800039e3  lea     eax, [rsi+rsi]
0x1800039e6  movsxd  rcx, dword ptr [rdi]
0x1800039e9  add     rdx, rdx; DestinationSize
0x1800039ec  movsxd  r9, eax; SourceSize
0x1800039ef  mov     r8, rbp; Source
0x1800039f2  mov     rax, [rdi+8]
0x1800039f6  lea     rcx, [rax+rcx*2]; Destination
0x1800039fa  call    cs:__imp_memcpy_s
0x180003a00  mov     ecx, eax; int
0x180003a02  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003a07  add     [rdi], esi
0x180003a09  movsxd  rdx, dword ptr [rdi]
0x180003a0c  xor     eax, eax
0x180003a0e  mov     rcx, [rdi+8]
0x180003a12  mov     [rcx+rdx*2], ax
0x180003a16  mov     eax, 1
0x180003a1b  jmp     short loc_180003A1F
0x180003a1d  xor     eax, eax
0x180003a1f  add     rsp, 28h
0x180003a23  pop     rdi
0x180003a24  pop     rsi
0x180003a25  pop     rbp
0x180003a26  pop     rbx
0x180003a27  retn
```
