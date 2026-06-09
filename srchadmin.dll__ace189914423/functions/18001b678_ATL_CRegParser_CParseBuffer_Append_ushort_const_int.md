# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18001b678`
- end: `0x18001b74c`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `212`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d958`

## callees

- `0x180009e90`
- `0x180012f8c`
- `0x18001a188`
- `0x18001b678`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001b6e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001b6e2`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  LPVOID v8; // rax
  int v9; // ecx
  errno_t v10; // eax
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF

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
      LODWORD(cb) = 0;
      if ( (int)ATL::AtlMultiply<unsigned long>(&cb, (unsigned int)v7, 2) < 0 )
        return 0;
      v8 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)cb);
      if ( !v8 )
        return 0;
      *((_QWORD *)this + 1) = v8;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v9 = v7 - *(_DWORD *)this;
      if ( v9 <= v7 )
      {
        v10 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v9, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v10);
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
0x18001b678  push    rbx
0x18001b67a  push    rbp
0x18001b67b  push    rsi
0x18001b67c  push    rdi
0x18001b67d  sub     rsp, 28h
0x18001b681  mov     rdi, rcx
0x18001b684  mov     esi, r8d
0x18001b687  lea     ecx, [r8+1]
0x18001b68b  mov     rbp, rdx
0x18001b68e  add     ecx, [rdi]
0x18001b690  cmp     ecx, [rdi]
0x18001b692  jle     loc_18001B741
0x18001b698  cmp     ecx, r8d
0x18001b69b  jle     loc_18001B741
0x18001b6a1  mov     ebx, [rdi+4]
0x18001b6a4  cmp     ecx, ebx
0x18001b6a6  jl      short loc_18001B6F4
0x18001b6a8  cmp     ecx, ebx
0x18001b6aa  jl      short loc_18001B6BC
0x18001b6ac  cmp     ebx, 3FFFFFFFh
0x18001b6b2  jg      loc_18001B741
0x18001b6b8  add     ebx, ebx
0x18001b6ba  jmp     short loc_18001B6A8
0x18001b6bc  mov     r8d, 2
0x18001b6c2  mov     dword ptr [rsp+48h+cb], 0
0x18001b6ca  mov     edx, ebx
0x18001b6cc  lea     rcx, [rsp+48h+cb]
0x18001b6d1  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18001b6d6  test    eax, eax
0x18001b6d8  js      short loc_18001B741
0x18001b6da  mov     edx, dword ptr [rsp+48h+cb]; cb
0x18001b6de  mov     rcx, [rdi+8]; pv
0x18001b6e2  call    cs:__imp_CoTaskMemRealloc
0x18001b6e8  test    rax, rax
0x18001b6eb  jz      short loc_18001B741
0x18001b6ed  mov     [rdi+8], rax
0x18001b6f1  mov     [rdi+4], ebx
0x18001b6f4  cmp     dword ptr [rdi], 0
0x18001b6f7  jl      short loc_18001B741
0x18001b6f9  cmp     [rdi], ebx
0x18001b6fb  jge     short loc_18001B741
0x18001b6fd  mov     ecx, ebx
0x18001b6ff  sub     ecx, [rdi]
0x18001b701  cmp     ecx, ebx
0x18001b703  jg      short loc_18001B741
0x18001b705  movsxd  rdx, ecx
0x18001b708  lea     eax, [rsi+rsi]
0x18001b70b  movsxd  rcx, dword ptr [rdi]
0x18001b70e  add     rdx, rdx; DestinationSize
0x18001b711  movsxd  r9, eax; SourceSize
0x18001b714  mov     r8, rbp; Source
0x18001b717  mov     rax, [rdi+8]
0x18001b71b  lea     rcx, [rax+rcx*2]; Destination
0x18001b71f  call    memcpy_s
0x18001b724  mov     ecx, eax; int
0x18001b726  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001b72b  add     [rdi], esi
0x18001b72d  movsxd  rdx, dword ptr [rdi]
0x18001b730  xor     eax, eax
0x18001b732  mov     rcx, [rdi+8]
0x18001b736  mov     [rcx+rdx*2], ax
0x18001b73a  mov     eax, 1
0x18001b73f  jmp     short loc_18001B743
0x18001b741  xor     eax, eax
0x18001b743  add     rsp, 28h
0x18001b747  pop     rdi
0x18001b748  pop     rsi
0x18001b749  pop     rbp
0x18001b74a  pop     rbx
0x18001b74b  retn
```
