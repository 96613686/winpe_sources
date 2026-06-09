# ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::Reallocate(unsigned __int64)

- ea: `0x140007258`
- end: `0x1400073ab`
- name: `?Reallocate@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140006fe8`

## callees

- `0x140001e22`
- `0x140001ebe`
- `0x140002e98`
- `0x140003004`
- `0x14000339c`
- `0x1400055c8`
- `0x140007224`
- `0x140007258`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000736e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000736e`

## pseudocode

```c
_OWORD *__fastcall ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::Reallocate(__int64 a1, unsigned __int64 a2)
{
  _OWORD *v3; // r8
  unsigned __int64 v4; // rsi
  _OWORD *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  _OWORD *v10; // rcx
  errno_t v11; // eax

  if ( a2 >= 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_23;
  v3 = *(_OWORD **)a1;
  v4 = 2 * a2;
  if ( *(_QWORD *)a1 )
  {
    v6 = (_OWORD *)(a1 + 8);
    if ( v4 > 0x80 )
    {
      if ( v3 != v6 )
      {
        ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::ReAllocateHeap(a1, v4);
        return *(_OWORD **)a1;
      }
      ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(a1, v4);
      v10 = *(_OWORD **)a1;
      if ( *(_QWORD *)a1 )
      {
        if ( v6 )
        {
          *v10 = *v6;
          v10[1] = v6[1];
          v10[2] = v6[2];
          v10[3] = v6[3];
          v10[4] = v6[4];
          v10[5] = v6[5];
          v10[6] = v6[6];
          v10[7] = v6[7];
          return *(_OWORD **)a1;
        }
        memset_0(v10, 0, v4);
      }
      *(_DWORD *)_o__errno(v10, v7, v8, v9) = 22;
      invalid_parameter_noinfo();
      ATL::AtlThrowImpl(-2147024809);
    }
    if ( v3 == v6 )
    {
LABEL_20:
      *(_QWORD *)a1 = v6;
      return *(_OWORD **)a1;
    }
    v11 = memcpy_s((void *const)(a1 + 8), 0x80u, v3, v4);
    switch ( v11 )
    {
      case 0:
        goto LABEL_19;
      case 12:
        ATL::AtlThrowImpl(-2147024882);
      case 22:
      case 34:
        ATL::AtlThrowImpl(-2147024809);
      case 80:
LABEL_19:
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(a1);
        goto LABEL_20;
    }
LABEL_23:
    ATL::AtlThrowImpl(-2147467259);
  }
  if ( v4 <= 0x80 )
    *(_QWORD *)a1 = a1 + 8;
  else
    ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(a1, v4);
  return *(_OWORD **)a1;
}

```

## disassembly

```asm
0x140007258  mov     [rsp+arg_0], rbx
0x14000725d  mov     [rsp+arg_8], rsi
0x140007262  push    rdi
0x140007263  sub     rsp, 20h
0x140007267  mov     rax, 7FFFFFFFFFFFFFFFh
0x140007271  mov     rbx, rcx
0x140007274  cmp     rdx, rax
0x140007277  jnb     loc_14000738A
0x14000727d  mov     r8, [rcx]; Source
0x140007280  lea     rsi, [rdx+rdx]
0x140007284  mov     edx, 80h; DestinationSize
0x140007289  test    r8, r8
0x14000728c  jnz     short loc_1400072B7
0x14000728e  cmp     rsi, rdx
0x140007291  jbe     short loc_14000729D
0x140007293  mov     rdx, rsi
0x140007296  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000729b  jmp     short loc_1400072A4
0x14000729d  lea     rax, [rcx+8]
0x1400072a1  mov     [rcx], rax
0x1400072a4  mov     rax, [rbx]
0x1400072a7  mov     rbx, [rsp+28h+arg_0]
0x1400072ac  mov     rsi, [rsp+28h+arg_8]
0x1400072b1  add     rsp, 20h
0x1400072b5  pop     rdi
0x1400072b6  retn
0x1400072b7  lea     rdi, [rcx+8]
0x1400072bb  cmp     rsi, rdx
0x1400072be  jbe     short loc_14000732C
0x1400072c0  mov     rdx, rsi
0x1400072c3  cmp     r8, rdi
0x1400072c6  jnz     short loc_140007322
0x1400072c8  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1400072cd  mov     rcx, [rbx]; void *
0x1400072d0  test    rcx, rcx
0x1400072d3  jz      loc_14000736E
0x1400072d9  test    rdi, rdi
0x1400072dc  jz      loc_140007364
0x1400072e2  movups  xmm0, xmmword ptr [rdi]
0x1400072e5  movups  xmmword ptr [rcx], xmm0
0x1400072e8  movups  xmm1, xmmword ptr [rdi+10h]
0x1400072ec  movups  xmmword ptr [rcx+10h], xmm1
0x1400072f0  movups  xmm0, xmmword ptr [rdi+20h]
0x1400072f4  movups  xmmword ptr [rcx+20h], xmm0
0x1400072f8  movups  xmm1, xmmword ptr [rdi+30h]
0x1400072fc  movups  xmmword ptr [rcx+30h], xmm1
0x140007300  movups  xmm0, xmmword ptr [rdi+40h]
0x140007304  movups  xmmword ptr [rcx+40h], xmm0
0x140007308  movups  xmm1, xmmword ptr [rdi+50h]
0x14000730c  movups  xmmword ptr [rcx+50h], xmm1
0x140007310  movups  xmm0, xmmword ptr [rdi+60h]
0x140007314  movups  xmmword ptr [rcx+60h], xmm0
0x140007318  movups  xmm1, xmmword ptr [rdi+70h]
0x14000731c  movups  xmmword ptr [rcx+70h], xmm1
0x140007320  jmp     short loc_1400072A4
0x140007322  call    ?ReAllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::ReAllocateHeap(unsigned __int64)
0x140007327  jmp     loc_1400072A4
0x14000732c  cmp     r8, rdi
0x14000732f  jz      short loc_14000735C
0x140007331  mov     r9, rsi; SourceSize
0x140007334  mov     rcx, rdi; Destination
0x140007337  call    memcpy_s
0x14000733c  test    eax, eax
0x14000733e  jz      short loc_140007354
0x140007340  cmp     eax, 0Ch
0x140007343  jz      short loc_1400073A0
0x140007345  cmp     eax, 16h
0x140007348  jz      short loc_140007395
0x14000734a  cmp     eax, 22h ; '"'
0x14000734d  jz      short loc_140007395
0x14000734f  cmp     eax, 50h ; 'P'
0x140007352  jnz     short loc_14000738A
0x140007354  mov     rcx, rbx
0x140007357  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000735c  mov     [rbx], rdi
0x14000735f  jmp     loc_1400072A4
0x140007364  mov     r8, rsi; Size
0x140007367  xor     edx, edx; Val
0x140007369  call    memset_0
0x14000736e  call    cs:__imp__o__errno
0x140007374  mov     dword ptr [rax], 16h
0x14000737a  call    _invalid_parameter_noinfo
0x14000737f  mov     ecx, 80070057h; int
0x140007384  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000738a  mov     ecx, 80004005h; int
0x14000738f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140007395  mov     ecx, 80070057h; int
0x14000739a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400073a0  mov     ecx, 8007000Eh; int
0x1400073a5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
