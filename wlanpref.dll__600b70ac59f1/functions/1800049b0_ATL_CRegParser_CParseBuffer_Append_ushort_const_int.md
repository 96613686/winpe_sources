# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800049b0`
- end: `0x180004a70`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009274`

## callees

- `0x1800049b0`
- `0x180004c00`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004a42`
- `msvcrt!memcpy_s` at `0x180004a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004a05`

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
0x1800049b0  push    rbx
0x1800049b2  push    rbp
0x1800049b3  push    rsi
0x1800049b4  push    rdi
0x1800049b5  sub     rsp, 28h
0x1800049b9  mov     rdi, rcx
0x1800049bc  mov     esi, r8d
0x1800049bf  lea     ecx, [r8+1]
0x1800049c3  mov     rbp, rdx
0x1800049c6  add     ecx, [rdi]
0x1800049c8  cmp     ecx, [rdi]
0x1800049ca  jle     loc_180004A65
0x1800049d0  cmp     ecx, r8d
0x1800049d3  jle     loc_180004A65
0x1800049d9  mov     ebx, [rdi+4]
0x1800049dc  cmp     ecx, ebx
0x1800049de  jl      short loc_180004A17
0x1800049e0  cmp     ecx, ebx
0x1800049e2  jl      short loc_1800049F0
0x1800049e4  cmp     ebx, 3FFFFFFFh
0x1800049ea  jg      short loc_180004A65
0x1800049ec  add     ebx, ebx
0x1800049ee  jmp     short loc_1800049E0
0x1800049f0  mov     eax, ebx
0x1800049f2  mov     ecx, 0FFFFFFFFh
0x1800049f7  add     rax, rax
0x1800049fa  cmp     rax, rcx
0x1800049fd  ja      short loc_180004A65
0x1800049ff  mov     rcx, [rdi+8]; pv
0x180004a03  mov     edx, eax; cb
0x180004a05  call    cs:__imp_CoTaskMemRealloc
0x180004a0b  test    rax, rax
0x180004a0e  jz      short loc_180004A65
0x180004a10  mov     [rdi+8], rax
0x180004a14  mov     [rdi+4], ebx
0x180004a17  cmp     dword ptr [rdi], 0
0x180004a1a  jl      short loc_180004A65
0x180004a1c  cmp     [rdi], ebx
0x180004a1e  jge     short loc_180004A65
0x180004a20  mov     ecx, ebx
0x180004a22  sub     ecx, [rdi]
0x180004a24  cmp     ecx, ebx
0x180004a26  jg      short loc_180004A65
0x180004a28  movsxd  rdx, ecx
0x180004a2b  lea     eax, [rsi+rsi]
0x180004a2e  movsxd  rcx, dword ptr [rdi]
0x180004a31  add     rdx, rdx; DestinationSize
0x180004a34  movsxd  r9, eax; SourceSize
0x180004a37  mov     r8, rbp; Source
0x180004a3a  mov     rax, [rdi+8]
0x180004a3e  lea     rcx, [rax+rcx*2]; Destination
0x180004a42  call    cs:__imp_memcpy_s
0x180004a48  mov     ecx, eax; int
0x180004a4a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180004a4f  add     [rdi], esi
0x180004a51  movsxd  rdx, dword ptr [rdi]
0x180004a54  xor     eax, eax
0x180004a56  mov     rcx, [rdi+8]
0x180004a5a  mov     [rcx+rdx*2], ax
0x180004a5e  mov     eax, 1
0x180004a63  jmp     short loc_180004A67
0x180004a65  xor     eax, eax
0x180004a67  add     rsp, 28h
0x180004a6b  pop     rdi
0x180004a6c  pop     rsi
0x180004a6d  pop     rbp
0x180004a6e  pop     rbx
0x180004a6f  retn
```
