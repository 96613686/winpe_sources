# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18000362c`
- end: `0x180003720`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `244`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000418c`

## callees

- `0x18000362c`
- `0x180003870`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800036c0`
- `msvcrt!memcpy_s` at `0x1800036c0`
- `ole32!CoTaskMemRealloc` at `0x180003683`
- `ole32!CoTaskMemRealloc` at `0x180003683`

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
0x18000362c  push    rbx
0x18000362e  push    rbp
0x18000362f  push    rsi
0x180003630  push    rdi
0x180003631  sub     rsp, 28h
0x180003635  mov     rdi, rcx
0x180003638  mov     esi, r8d
0x18000363b  lea     ecx, [r8+1]
0x18000363f  mov     rbp, rdx
0x180003642  add     ecx, [rdi]
0x180003644  cmp     ecx, [rdi]
0x180003646  jle     loc_1800036F4
0x18000364c  cmp     ecx, r8d
0x18000364f  jle     loc_1800036F4
0x180003655  mov     ebx, [rdi+4]
0x180003658  cmp     ecx, ebx
0x18000365a  jl      short loc_180003695
0x18000365c  cmp     ebx, 3FFFFFFFh
0x180003662  jg      loc_1800036F4
0x180003668  add     ebx, ebx
0x18000366a  cmp     ecx, ebx
0x18000366c  jge     short loc_18000365C
0x18000366e  mov     eax, ebx
0x180003670  mov     ecx, 0FFFFFFFFh
0x180003675  add     rax, rax
0x180003678  cmp     rax, rcx
0x18000367b  ja      short loc_1800036F4
0x18000367d  mov     rcx, [rdi+8]; pv
0x180003681  mov     edx, eax; cb
0x180003683  call    cs:__imp_CoTaskMemRealloc
0x180003689  test    rax, rax
0x18000368c  jz      short loc_1800036F4
0x18000368e  mov     [rdi+8], rax
0x180003692  mov     [rdi+4], ebx
0x180003695  cmp     dword ptr [rdi], 0
0x180003698  jl      short loc_1800036F4
0x18000369a  cmp     [rdi], ebx
0x18000369c  jge     short loc_1800036F4
0x18000369e  mov     ecx, ebx
0x1800036a0  sub     ecx, [rdi]
0x1800036a2  cmp     ecx, ebx
0x1800036a4  jg      short loc_1800036F4
0x1800036a6  movsxd  rdx, ecx
0x1800036a9  lea     eax, [rsi+rsi]
0x1800036ac  movsxd  rcx, dword ptr [rdi]
0x1800036af  add     rdx, rdx; DestinationSize
0x1800036b2  movsxd  r9, eax; SourceSize
0x1800036b5  mov     r8, rbp; Source
0x1800036b8  mov     rax, [rdi+8]
0x1800036bc  lea     rcx, [rax+rcx*2]; Destination
0x1800036c0  call    cs:__imp_memcpy_s
0x1800036c6  test    eax, eax
0x1800036c8  jz      short loc_1800036DE
0x1800036ca  cmp     eax, 0Ch
0x1800036cd  jz      short loc_180003715
0x1800036cf  cmp     eax, 16h
0x1800036d2  jz      short loc_18000370A
0x1800036d4  cmp     eax, 22h ; '"'
0x1800036d7  jz      short loc_18000370A
0x1800036d9  cmp     eax, 50h ; 'P'
0x1800036dc  jnz     short loc_1800036FF
0x1800036de  add     [rdi], esi
0x1800036e0  movsxd  rdx, dword ptr [rdi]
0x1800036e3  xor     eax, eax
0x1800036e5  mov     rcx, [rdi+8]
0x1800036e9  mov     [rcx+rdx*2], ax
0x1800036ed  mov     eax, 1
0x1800036f2  jmp     short loc_1800036F6
0x1800036f4  xor     eax, eax
0x1800036f6  add     rsp, 28h
0x1800036fa  pop     rdi
0x1800036fb  pop     rsi
0x1800036fc  pop     rbp
0x1800036fd  pop     rbx
0x1800036fe  retn
0x1800036ff  mov     ecx, 80004005h; int
0x180003704  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000370a  mov     ecx, 80070057h; int
0x18000370f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003715  mov     ecx, 8007000Eh; int
0x18000371a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
