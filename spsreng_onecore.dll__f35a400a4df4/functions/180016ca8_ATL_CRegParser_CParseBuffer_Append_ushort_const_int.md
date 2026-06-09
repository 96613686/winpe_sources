# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180016ca8`
- end: `0x180016d67`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019f20`

## callees

- `0x180016ca8`
- `0x180016efc`
- `0x18001ca5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180016cfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180016cfd`

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
0x180016ca8  push    rbx
0x180016caa  push    rbp
0x180016cab  push    rsi
0x180016cac  push    rdi
0x180016cad  sub     rsp, 28h
0x180016cb1  mov     rdi, rcx
0x180016cb4  mov     esi, r8d
0x180016cb7  lea     ecx, [r8+1]
0x180016cbb  mov     rbp, rdx
0x180016cbe  add     ecx, [rdi]
0x180016cc0  cmp     ecx, [rdi]
0x180016cc2  jle     loc_180016D5C
0x180016cc8  cmp     ecx, r8d
0x180016ccb  jle     loc_180016D5C
0x180016cd1  mov     ebx, [rdi+4]
0x180016cd4  cmp     ecx, ebx
0x180016cd6  jl      short loc_180016D0F
0x180016cd8  cmp     ecx, ebx
0x180016cda  jl      short loc_180016CE8
0x180016cdc  cmp     ebx, 3FFFFFFFh
0x180016ce2  jg      short loc_180016D5C
0x180016ce4  add     ebx, ebx
0x180016ce6  jmp     short loc_180016CD8
0x180016ce8  mov     eax, ebx
0x180016cea  mov     ecx, 0FFFFFFFFh
0x180016cef  add     rax, rax
0x180016cf2  cmp     rax, rcx
0x180016cf5  ja      short loc_180016D5C
0x180016cf7  mov     rcx, [rdi+8]; pv
0x180016cfb  mov     edx, eax; cb
0x180016cfd  call    cs:__imp_CoTaskMemRealloc
0x180016d03  test    rax, rax
0x180016d06  jz      short loc_180016D5C
0x180016d08  mov     [rdi+8], rax
0x180016d0c  mov     [rdi+4], ebx
0x180016d0f  cmp     dword ptr [rdi], 0
0x180016d12  jl      short loc_180016D5C
0x180016d14  cmp     [rdi], ebx
0x180016d16  jge     short loc_180016D5C
0x180016d18  mov     ecx, ebx
0x180016d1a  sub     ecx, [rdi]
0x180016d1c  cmp     ecx, ebx
0x180016d1e  jg      short loc_180016D5C
0x180016d20  movsxd  rdx, ecx
0x180016d23  lea     eax, [rsi+rsi]
0x180016d26  movsxd  rcx, dword ptr [rdi]
0x180016d29  add     rdx, rdx; DestinationSize
0x180016d2c  movsxd  r9, eax; SourceSize
0x180016d2f  mov     r8, rbp; Source
0x180016d32  mov     rax, [rdi+8]
0x180016d36  lea     rcx, [rax+rcx*2]; Destination
0x180016d3a  call    memcpy_s
0x180016d3f  mov     ecx, eax; int
0x180016d41  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016d46  add     [rdi], esi
0x180016d48  movsxd  rdx, dword ptr [rdi]
0x180016d4b  xor     eax, eax
0x180016d4d  mov     rcx, [rdi+8]
0x180016d51  mov     [rcx+rdx*2], ax
0x180016d55  mov     eax, 1
0x180016d5a  jmp     short loc_180016D5E
0x180016d5c  xor     eax, eax
0x180016d5e  add     rsp, 28h
0x180016d62  pop     rdi
0x180016d63  pop     rsi
0x180016d64  pop     rbp
0x180016d65  pop     rbx
0x180016d66  retn
```
