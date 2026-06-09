# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x1800031f8`
- end: `0x180003316`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `286`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003c7c`

## callees

- `0x1800031f8`
- `0x18000335c`
- `0x180005420`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x180003262`
- `ole32!CoTaskMemRealloc` at `0x180003262`

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
0x1800031f8  mov     rax, rsp
0x1800031fb  mov     [rax+8], rbx
0x1800031ff  mov     [rax+10h], rbp
0x180003203  mov     [rax+18h], rsi
0x180003207  mov     [rax+20h], rdi
0x18000320b  push    r14
0x18000320d  sub     rsp, 20h
0x180003211  mov     rdi, rcx
0x180003214  mov     esi, r8d
0x180003217  lea     ecx, [r8+1]
0x18000321b  mov     rbp, rdx
0x18000321e  add     ecx, [rdi]
0x180003220  cmp     ecx, [rdi]
0x180003222  jle     loc_1800032D7
0x180003228  cmp     ecx, r8d
0x18000322b  jle     loc_1800032D7
0x180003231  mov     ebx, [rdi+4]
0x180003234  xor     r14d, r14d
0x180003237  cmp     ecx, ebx
0x180003239  jl      short loc_18000327A
0x18000323b  cmp     ebx, 3FFFFFFFh
0x180003241  jg      loc_1800032D7
0x180003247  add     ebx, ebx
0x180003249  cmp     ecx, ebx
0x18000324b  jge     short loc_18000323B
0x18000324d  mov     eax, ebx
0x18000324f  mov     ecx, 0FFFFFFFFh
0x180003254  add     rax, rax
0x180003257  cmp     rax, rcx
0x18000325a  ja      short loc_1800032D7
0x18000325c  mov     rcx, [rdi+8]; pv
0x180003260  mov     edx, eax; cb
0x180003262  call    cs:__imp_CoTaskMemRealloc
0x180003269  nop     dword ptr [rax+rax+00h]
0x18000326e  test    rax, rax
0x180003271  jz      short loc_1800032D7
0x180003273  mov     [rdi+8], rax
0x180003277  mov     [rdi+4], ebx
0x18000327a  cmp     [rdi], r14d
0x18000327d  jl      short loc_1800032D7
0x18000327f  cmp     [rdi], ebx
0x180003281  jge     short loc_1800032D7
0x180003283  mov     ecx, ebx
0x180003285  sub     ecx, [rdi]
0x180003287  cmp     ecx, ebx
0x180003289  jg      short loc_1800032D7
0x18000328b  movsxd  rdx, ecx
0x18000328e  lea     eax, [rsi+rsi]
0x180003291  movsxd  rcx, dword ptr [rdi]
0x180003294  add     rdx, rdx; DestinationSize
0x180003297  movsxd  r9, eax; SourceSize
0x18000329a  mov     r8, rbp; Source
0x18000329d  mov     rax, [rdi+8]
0x1800032a1  lea     rcx, [rax+rcx*2]; Destination
0x1800032a5  call    memcpy_s
0x1800032aa  test    eax, eax
0x1800032ac  jz      short loc_1800032C2
0x1800032ae  cmp     eax, 0Ch
0x1800032b1  jz      short loc_18000330B
0x1800032b3  cmp     eax, 16h
0x1800032b6  jz      short loc_180003300
0x1800032b8  cmp     eax, 22h ; '"'
0x1800032bb  jz      short loc_180003300
0x1800032bd  cmp     eax, 50h ; 'P'
0x1800032c0  jnz     short loc_1800032F5
0x1800032c2  add     [rdi], esi
0x1800032c4  mov     rax, [rdi+8]
0x1800032c8  movsxd  rcx, dword ptr [rdi]
0x1800032cb  mov     [rax+rcx*2], r14w
0x1800032d0  mov     eax, 1
0x1800032d5  jmp     short loc_1800032D9
0x1800032d7  xor     eax, eax
0x1800032d9  mov     rbx, [rsp+28h+arg_0]
0x1800032de  mov     rbp, [rsp+28h+arg_8]
0x1800032e3  mov     rsi, [rsp+28h+arg_10]
0x1800032e8  mov     rdi, [rsp+28h+arg_18]
0x1800032ed  add     rsp, 20h
0x1800032f1  pop     r14
0x1800032f3  retn
0x1800032f5  mov     ecx, 80004005h; int
0x1800032fa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003300  mov     ecx, 80070057h; int
0x180003305  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000330b  mov     ecx, 8007000Eh; int
0x180003310  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
