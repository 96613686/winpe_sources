# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180003580`
- end: `0x180003675`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `245`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800047b0`

## callees

- `0x180003580`
- `0x1800037ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000362f`
- `msvcrt!memcpy_s` at `0x18000362f`
- `ole32!CoTaskMemRealloc` at `0x1800035ec`
- `ole32!CoTaskMemRealloc` at `0x1800035ec`

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
  int v10; // edx
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
0x180003580  mov     rax, rsp
0x180003583  mov     [rax+8], rbx
0x180003587  mov     [rax+10h], rbp
0x18000358b  mov     [rax+18h], rsi
0x18000358f  mov     [rax+20h], rdi
0x180003593  push    r14
0x180003595  sub     rsp, 20h
0x180003599  mov     rdi, rcx
0x18000359c  mov     esi, r8d
0x18000359f  lea     ecx, [r8+1]
0x1800035a3  mov     rbp, rdx
0x1800035a6  add     ecx, [rdi]
0x1800035a8  cmp     ecx, [rdi]
0x1800035aa  jle     loc_180003657
0x1800035b0  cmp     ecx, r8d
0x1800035b3  jle     loc_180003657
0x1800035b9  mov     ebx, [rdi+4]
0x1800035bc  xor     r14d, r14d
0x1800035bf  cmp     ecx, ebx
0x1800035c1  jl      short loc_180003604
0x1800035c3  cmp     ecx, ebx
0x1800035c5  jl      short loc_1800035D7
0x1800035c7  cmp     ebx, 3FFFFFFFh
0x1800035cd  jg      loc_180003657
0x1800035d3  add     ebx, ebx
0x1800035d5  jmp     short loc_1800035C3
0x1800035d7  mov     eax, ebx
0x1800035d9  mov     ecx, 0FFFFFFFFh
0x1800035de  add     rax, rax
0x1800035e1  cmp     rax, rcx
0x1800035e4  ja      short loc_180003657
0x1800035e6  mov     rcx, [rdi+8]; pv
0x1800035ea  mov     edx, eax; cb
0x1800035ec  call    cs:__imp_CoTaskMemRealloc
0x1800035f3  nop     dword ptr [rax+rax+00h]
0x1800035f8  test    rax, rax
0x1800035fb  jz      short loc_180003657
0x1800035fd  mov     [rdi+8], rax
0x180003601  mov     [rdi+4], ebx
0x180003604  cmp     [rdi], r14d
0x180003607  jl      short loc_180003657
0x180003609  cmp     [rdi], ebx
0x18000360b  jge     short loc_180003657
0x18000360d  mov     edx, ebx
0x18000360f  sub     edx, [rdi]
0x180003611  cmp     edx, ebx
0x180003613  jg      short loc_180003657
0x180003615  mov     rax, [rdi+8]
0x180003619  mov     r8, rbp; Source
0x18000361c  movsxd  rcx, dword ptr [rdi]
0x18000361f  movsxd  rdx, edx
0x180003622  add     rdx, rdx; DestinationSize
0x180003625  lea     rcx, [rax+rcx*2]; Destination
0x180003629  lea     eax, [rsi+rsi]
0x18000362c  movsxd  r9, eax; SourceSize
0x18000362f  call    cs:__imp_memcpy_s
0x180003636  nop     dword ptr [rax+rax+00h]
0x18000363b  mov     ecx, eax; int
0x18000363d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180003642  add     [rdi], esi
0x180003644  mov     rax, [rdi+8]
0x180003648  movsxd  rcx, dword ptr [rdi]
0x18000364b  mov     [rax+rcx*2], r14w
0x180003650  mov     eax, 1
0x180003655  jmp     short loc_180003659
0x180003657  xor     eax, eax
0x180003659  mov     rbx, [rsp+28h+arg_0]
0x18000365e  mov     rbp, [rsp+28h+arg_8]
0x180003663  mov     rsi, [rsp+28h+arg_10]
0x180003668  mov     rdi, [rsp+28h+arg_18]
0x18000366d  add     rsp, 20h
0x180003671  pop     r14
0x180003673  retn
```
