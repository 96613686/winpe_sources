# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800188e0`
- end: `0x18001899e`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `190`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800198f0`

## callees

- `0x1800188e0`
- `0x180018b24`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180018970`
- `msvcrt!memcpy_s` at `0x180018970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180018933`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180018933`

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
    if ( v6 < v7 )
    {
LABEL_9:
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
    else
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
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800188e0  push    rbx
0x1800188e2  push    rbp
0x1800188e3  push    rsi
0x1800188e4  push    rdi
0x1800188e5  sub     rsp, 28h
0x1800188e9  mov     rdi, rcx
0x1800188ec  mov     esi, r8d
0x1800188ef  lea     ecx, [r8+1]
0x1800188f3  mov     rbp, rdx
0x1800188f6  add     ecx, [rdi]
0x1800188f8  cmp     ecx, [rdi]
0x1800188fa  jle     loc_180018993
0x180018900  cmp     ecx, r8d
0x180018903  jle     loc_180018993
0x180018909  mov     ebx, [rdi+4]
0x18001890c  cmp     ecx, ebx
0x18001890e  jl      short loc_180018945
0x180018910  cmp     ebx, 3FFFFFFFh
0x180018916  jg      short loc_180018993
0x180018918  add     ebx, ebx
0x18001891a  cmp     ecx, ebx
0x18001891c  jge     short loc_180018910
0x18001891e  mov     eax, ebx
0x180018920  mov     ecx, 0FFFFFFFFh
0x180018925  add     rax, rax
0x180018928  cmp     rax, rcx
0x18001892b  ja      short loc_180018993
0x18001892d  mov     rcx, [rdi+8]; pv
0x180018931  mov     edx, eax; cb
0x180018933  call    cs:__imp_CoTaskMemRealloc
0x180018939  test    rax, rax
0x18001893c  jz      short loc_180018993
0x18001893e  mov     [rdi+8], rax
0x180018942  mov     [rdi+4], ebx
0x180018945  cmp     dword ptr [rdi], 0
0x180018948  jl      short loc_180018993
0x18001894a  cmp     [rdi], ebx
0x18001894c  jge     short loc_180018993
0x18001894e  mov     ecx, ebx
0x180018950  sub     ecx, [rdi]
0x180018952  cmp     ecx, ebx
0x180018954  jg      short loc_180018993
0x180018956  movsxd  rdx, ecx
0x180018959  lea     eax, [rsi+rsi]
0x18001895c  movsxd  rcx, dword ptr [rdi]
0x18001895f  add     rdx, rdx; DestinationSize
0x180018962  movsxd  r9, eax; SourceSize
0x180018965  mov     r8, rbp; Source
0x180018968  mov     rax, [rdi+8]
0x18001896c  lea     rcx, [rax+rcx*2]; Destination
0x180018970  call    cs:__imp_memcpy_s
0x180018976  mov     ecx, eax; int
0x180018978  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001897d  add     [rdi], esi
0x18001897f  movsxd  rdx, dword ptr [rdi]
0x180018982  xor     eax, eax
0x180018984  mov     rcx, [rdi+8]
0x180018988  mov     [rcx+rdx*2], ax
0x18001898c  mov     eax, 1
0x180018991  jmp     short loc_180018995
0x180018993  xor     eax, eax
0x180018995  add     rsp, 28h
0x180018999  pop     rdi
0x18001899a  pop     rsi
0x18001899b  pop     rbp
0x18001899c  pop     rbx
0x18001899d  retn
```
