# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180004148`
- end: `0x180004208`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `192`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006cc8`

## callees

- `0x180004148`
- `0x180004324`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800041da`
- `msvcrt!memcpy_s` at `0x1800041da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000419d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000419d`

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
0x180004148  push    rbx
0x18000414a  push    rbp
0x18000414b  push    rsi
0x18000414c  push    rdi
0x18000414d  sub     rsp, 28h
0x180004151  mov     rdi, rcx
0x180004154  mov     esi, r8d
0x180004157  lea     ecx, [r8+1]
0x18000415b  mov     rbp, rdx
0x18000415e  add     ecx, [rdi]
0x180004160  cmp     ecx, [rdi]
0x180004162  jle     loc_1800041FD
0x180004168  cmp     ecx, r8d
0x18000416b  jle     loc_1800041FD
0x180004171  mov     ebx, [rdi+4]
0x180004174  cmp     ecx, ebx
0x180004176  jl      short loc_1800041AF
0x180004178  cmp     ecx, ebx
0x18000417a  jl      short loc_180004188
0x18000417c  cmp     ebx, 3FFFFFFFh
0x180004182  jg      short loc_1800041FD
0x180004184  add     ebx, ebx
0x180004186  jmp     short loc_180004178
0x180004188  mov     eax, ebx
0x18000418a  mov     ecx, 0FFFFFFFFh
0x18000418f  add     rax, rax
0x180004192  cmp     rax, rcx
0x180004195  ja      short loc_1800041FD
0x180004197  mov     rcx, [rdi+8]; pv
0x18000419b  mov     edx, eax; cb
0x18000419d  call    cs:__imp_CoTaskMemRealloc
0x1800041a3  test    rax, rax
0x1800041a6  jz      short loc_1800041FD
0x1800041a8  mov     [rdi+8], rax
0x1800041ac  mov     [rdi+4], ebx
0x1800041af  cmp     dword ptr [rdi], 0
0x1800041b2  jl      short loc_1800041FD
0x1800041b4  cmp     [rdi], ebx
0x1800041b6  jge     short loc_1800041FD
0x1800041b8  mov     ecx, ebx
0x1800041ba  sub     ecx, [rdi]
0x1800041bc  cmp     ecx, ebx
0x1800041be  jg      short loc_1800041FD
0x1800041c0  movsxd  rdx, ecx
0x1800041c3  lea     eax, [rsi+rsi]
0x1800041c6  movsxd  rcx, dword ptr [rdi]
0x1800041c9  add     rdx, rdx; DestinationSize
0x1800041cc  movsxd  r9, eax; SourceSize
0x1800041cf  mov     r8, rbp; Source
0x1800041d2  mov     rax, [rdi+8]
0x1800041d6  lea     rcx, [rax+rcx*2]; Destination
0x1800041da  call    cs:__imp_memcpy_s
0x1800041e0  mov     ecx, eax; int
0x1800041e2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800041e7  add     [rdi], esi
0x1800041e9  movsxd  rdx, dword ptr [rdi]
0x1800041ec  xor     eax, eax
0x1800041ee  mov     rcx, [rdi+8]
0x1800041f2  mov     [rcx+rdx*2], ax
0x1800041f6  mov     eax, 1
0x1800041fb  jmp     short loc_1800041FF
0x1800041fd  xor     eax, eax
0x1800041ff  add     rsp, 28h
0x180004203  pop     rdi
0x180004204  pop     rsi
0x180004205  pop     rbp
0x180004206  pop     rbx
0x180004207  retn
```
