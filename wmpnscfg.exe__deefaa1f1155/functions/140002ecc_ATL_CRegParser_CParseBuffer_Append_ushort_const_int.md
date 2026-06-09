# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x140002ecc`
- end: `0x140002fbf`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `243`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140003924`

## callees

- `0x140002ecc`
- `0x140003004`
- `0x1400055c8`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x140002f23`
- `ole32!CoTaskMemRealloc` at `0x140002f23`

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
0x140002ecc  push    rbx
0x140002ece  push    rbp
0x140002ecf  push    rsi
0x140002ed0  push    rdi
0x140002ed1  sub     rsp, 28h
0x140002ed5  mov     rdi, rcx
0x140002ed8  mov     esi, r8d
0x140002edb  lea     ecx, [r8+1]
0x140002edf  mov     rbp, rdx
0x140002ee2  add     ecx, [rdi]
0x140002ee4  cmp     ecx, [rdi]
0x140002ee6  jle     loc_140002F93
0x140002eec  cmp     ecx, r8d
0x140002eef  jle     loc_140002F93
0x140002ef5  mov     ebx, [rdi+4]
0x140002ef8  cmp     ecx, ebx
0x140002efa  jl      short loc_140002F35
0x140002efc  cmp     ebx, 3FFFFFFFh
0x140002f02  jg      loc_140002F93
0x140002f08  add     ebx, ebx
0x140002f0a  cmp     ecx, ebx
0x140002f0c  jge     short loc_140002EFC
0x140002f0e  mov     eax, ebx
0x140002f10  mov     ecx, 0FFFFFFFFh
0x140002f15  add     rax, rax
0x140002f18  cmp     rax, rcx
0x140002f1b  ja      short loc_140002F93
0x140002f1d  mov     rcx, [rdi+8]; pv
0x140002f21  mov     edx, eax; cb
0x140002f23  call    cs:__imp_CoTaskMemRealloc
0x140002f29  test    rax, rax
0x140002f2c  jz      short loc_140002F93
0x140002f2e  mov     [rdi+8], rax
0x140002f32  mov     [rdi+4], ebx
0x140002f35  cmp     dword ptr [rdi], 0
0x140002f38  jl      short loc_140002F93
0x140002f3a  cmp     [rdi], ebx
0x140002f3c  jge     short loc_140002F93
0x140002f3e  mov     ecx, ebx
0x140002f40  sub     ecx, [rdi]
0x140002f42  cmp     ecx, ebx
0x140002f44  jg      short loc_140002F93
0x140002f46  movsxd  rdx, ecx
0x140002f49  lea     eax, [rsi+rsi]
0x140002f4c  movsxd  rcx, dword ptr [rdi]
0x140002f4f  add     rdx, rdx; DestinationSize
0x140002f52  movsxd  r9, eax; SourceSize
0x140002f55  mov     r8, rbp; Source
0x140002f58  mov     rax, [rdi+8]
0x140002f5c  lea     rcx, [rax+rcx*2]; Destination
0x140002f60  call    memcpy_s
0x140002f65  test    eax, eax
0x140002f67  jz      short loc_140002F7D
0x140002f69  cmp     eax, 0Ch
0x140002f6c  jz      short loc_140002FB4
0x140002f6e  cmp     eax, 16h
0x140002f71  jz      short loc_140002FA9
0x140002f73  cmp     eax, 22h ; '"'
0x140002f76  jz      short loc_140002FA9
0x140002f78  cmp     eax, 50h ; 'P'
0x140002f7b  jnz     short loc_140002F9E
0x140002f7d  add     [rdi], esi
0x140002f7f  movsxd  rdx, dword ptr [rdi]
0x140002f82  xor     eax, eax
0x140002f84  mov     rcx, [rdi+8]
0x140002f88  mov     [rcx+rdx*2], ax
0x140002f8c  mov     eax, 1
0x140002f91  jmp     short loc_140002F95
0x140002f93  xor     eax, eax
0x140002f95  add     rsp, 28h
0x140002f99  pop     rdi
0x140002f9a  pop     rsi
0x140002f9b  pop     rbp
0x140002f9c  pop     rbx
0x140002f9d  retn
0x140002f9e  mov     ecx, 80004005h; int
0x140002fa3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140002fa9  mov     ecx, 80070057h; int
0x140002fae  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140002fb4  mov     ecx, 8007000Eh; int
0x140002fb9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
