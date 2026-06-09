# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180008c58`
- end: `0x180008d17`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b670`

## callees

- `0x180008c58`
- `0x180008e8c`
- `0x18000d62c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008cad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180008cad`

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
0x180008c58  push    rbx
0x180008c5a  push    rbp
0x180008c5b  push    rsi
0x180008c5c  push    rdi
0x180008c5d  sub     rsp, 28h
0x180008c61  mov     rdi, rcx
0x180008c64  mov     esi, r8d
0x180008c67  lea     ecx, [r8+1]
0x180008c6b  mov     rbp, rdx
0x180008c6e  add     ecx, [rdi]
0x180008c70  cmp     ecx, [rdi]
0x180008c72  jle     loc_180008D0C
0x180008c78  cmp     ecx, r8d
0x180008c7b  jle     loc_180008D0C
0x180008c81  mov     ebx, [rdi+4]
0x180008c84  cmp     ecx, ebx
0x180008c86  jl      short loc_180008CBF
0x180008c88  cmp     ecx, ebx
0x180008c8a  jl      short loc_180008C98
0x180008c8c  cmp     ebx, 3FFFFFFFh
0x180008c92  jg      short loc_180008D0C
0x180008c94  add     ebx, ebx
0x180008c96  jmp     short loc_180008C88
0x180008c98  mov     eax, ebx
0x180008c9a  mov     ecx, 0FFFFFFFFh
0x180008c9f  add     rax, rax
0x180008ca2  cmp     rax, rcx
0x180008ca5  ja      short loc_180008D0C
0x180008ca7  mov     rcx, [rdi+8]; pv
0x180008cab  mov     edx, eax; cb
0x180008cad  call    cs:__imp_CoTaskMemRealloc
0x180008cb3  test    rax, rax
0x180008cb6  jz      short loc_180008D0C
0x180008cb8  mov     [rdi+8], rax
0x180008cbc  mov     [rdi+4], ebx
0x180008cbf  cmp     dword ptr [rdi], 0
0x180008cc2  jl      short loc_180008D0C
0x180008cc4  cmp     [rdi], ebx
0x180008cc6  jge     short loc_180008D0C
0x180008cc8  mov     ecx, ebx
0x180008cca  sub     ecx, [rdi]
0x180008ccc  cmp     ecx, ebx
0x180008cce  jg      short loc_180008D0C
0x180008cd0  movsxd  rdx, ecx
0x180008cd3  lea     eax, [rsi+rsi]
0x180008cd6  movsxd  rcx, dword ptr [rdi]
0x180008cd9  add     rdx, rdx; DestinationSize
0x180008cdc  movsxd  r9, eax; SourceSize
0x180008cdf  mov     r8, rbp; Source
0x180008ce2  mov     rax, [rdi+8]
0x180008ce6  lea     rcx, [rax+rcx*2]; Destination
0x180008cea  call    memcpy_s
0x180008cef  mov     ecx, eax; int
0x180008cf1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180008cf6  add     [rdi], esi
0x180008cf8  movsxd  rdx, dword ptr [rdi]
0x180008cfb  xor     eax, eax
0x180008cfd  mov     rcx, [rdi+8]
0x180008d01  mov     [rcx+rdx*2], ax
0x180008d05  mov     eax, 1
0x180008d0a  jmp     short loc_180008D0E
0x180008d0c  xor     eax, eax
0x180008d0e  add     rsp, 28h
0x180008d12  pop     rdi
0x180008d13  pop     rsi
0x180008d14  pop     rbp
0x180008d15  pop     rbx
0x180008d16  retn
```
