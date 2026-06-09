# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800062dc`
- end: `0x180006399`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `189`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007120`

## callees

- `0x180002fb0`
- `0x1800062dc`
- `0x180006510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000632f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000632f`

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
0x1800062dc  push    rbx
0x1800062de  push    rbp
0x1800062df  push    rsi
0x1800062e0  push    rdi
0x1800062e1  sub     rsp, 28h
0x1800062e5  mov     rdi, rcx
0x1800062e8  mov     esi, r8d
0x1800062eb  lea     ecx, [r8+1]
0x1800062ef  mov     rbp, rdx
0x1800062f2  add     ecx, [rdi]
0x1800062f4  cmp     ecx, [rdi]
0x1800062f6  jle     loc_18000638E
0x1800062fc  cmp     ecx, r8d
0x1800062ff  jle     loc_18000638E
0x180006305  mov     ebx, [rdi+4]
0x180006308  cmp     ecx, ebx
0x18000630a  jl      short loc_180006341
0x18000630c  cmp     ebx, 3FFFFFFFh
0x180006312  jg      short loc_18000638E
0x180006314  add     ebx, ebx
0x180006316  cmp     ecx, ebx
0x180006318  jge     short loc_18000630C
0x18000631a  mov     eax, ebx
0x18000631c  mov     ecx, 0FFFFFFFFh
0x180006321  add     rax, rax
0x180006324  cmp     rax, rcx
0x180006327  ja      short loc_18000638E
0x180006329  mov     rcx, [rdi+8]; pv
0x18000632d  mov     edx, eax; cb
0x18000632f  call    cs:__imp_CoTaskMemRealloc
0x180006335  test    rax, rax
0x180006338  jz      short loc_18000638E
0x18000633a  mov     [rdi+8], rax
0x18000633e  mov     [rdi+4], ebx
0x180006341  cmp     dword ptr [rdi], 0
0x180006344  jl      short loc_18000638E
0x180006346  cmp     [rdi], ebx
0x180006348  jge     short loc_18000638E
0x18000634a  mov     ecx, ebx
0x18000634c  sub     ecx, [rdi]
0x18000634e  cmp     ecx, ebx
0x180006350  jg      short loc_18000638E
0x180006352  movsxd  rdx, ecx
0x180006355  lea     eax, [rsi+rsi]
0x180006358  movsxd  rcx, dword ptr [rdi]
0x18000635b  add     rdx, rdx; DestinationSize
0x18000635e  movsxd  r9, eax; SourceSize
0x180006361  mov     r8, rbp; Source
0x180006364  mov     rax, [rdi+8]
0x180006368  lea     rcx, [rax+rcx*2]; Destination
0x18000636c  call    memcpy_s
0x180006371  mov     ecx, eax; int
0x180006373  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006378  add     [rdi], esi
0x18000637a  movsxd  rdx, dword ptr [rdi]
0x18000637d  xor     eax, eax
0x18000637f  mov     rcx, [rdi+8]
0x180006383  mov     [rcx+rdx*2], ax
0x180006387  mov     eax, 1
0x18000638c  jmp     short loc_180006390
0x18000638e  xor     eax, eax
0x180006390  add     rsp, 28h
0x180006394  pop     rdi
0x180006395  pop     rsi
0x180006396  pop     rbp
0x180006397  pop     rbx
0x180006398  retn
```
