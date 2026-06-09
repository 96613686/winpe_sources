# ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::InsertAt(unsigned __int64,CAdapter const &,unsigned __int64)

- ea: `0x18002b108`
- end: `0x18002b1ce`
- name: `?InsertAt@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAAX_KAEBVCAdapter@@0@Z`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002b06c`
- `0x18002b8c0`

## callees

- `0x180004c00`
- `0x1800054a0`
- `0x18000d650`
- `0x180029d18`
- `0x18002a17c`
- `0x18002b108`
- `0x18002c3ac`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002b185`
- `msvcrt!memmove_s` at `0x18002b185`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::InsertAt(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v7; // rsi
  __int64 result; // rax
  rsize_t v9; // rsi
  errno_t v10; // eax
  unsigned __int64 i; // rsi
  errno_t v12; // eax
  __int64 v14; // [rsp+48h] [rbp+10h]

  v7 = a1[1];
  if ( !v7 )
  {
    result = ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(a1, a4);
    if ( (_BYTE)result )
      goto LABEL_7;
LABEL_5:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( !(unsigned __int8)ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(a1, v7 + a4) )
    goto LABEL_5;
  v14 = v7;
  v9 = 32 * v7;
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::CallDestructors(v9 + *a1, a4);
  v10 = memmove_s((void *const)(*a1 + 32 * a4), v9, (const void *const)*a1, v9);
  ATL::AtlCrtErrorCheck(v10);
  try
  {
    result = ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::CallConstructors(*a1, a4);
  }
  catch ( ... )
  {
    v12 = memmove_s((void *const)*a1, 32 * v14, (const void *const)(*a1 + 32 * a4), 32 * v14);
    ATL::AtlCrtErrorCheck(v12);
    ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(a1, v14);
    throw;
  }
LABEL_7:
  for ( i = 0; i < a4; ++i )
    result = CAdapter::operator=(*a1 + 32 * i, a3);
  return result;
}

```

## disassembly

```asm
0x18002b108  mov     rax, rsp
0x18002b10b  mov     [rax+18h], rbx
0x18002b10f  mov     [rax+20h], r9
0x18002b113  mov     [rax+10h], rdx
0x18002b117  mov     [rax+8], rcx
0x18002b11b  push    rsi
0x18002b11c  push    rdi
0x18002b11d  push    r14
0x18002b11f  sub     rsp, 20h
0x18002b123  mov     rbx, r9
0x18002b126  mov     r14, r8
0x18002b129  mov     rdi, rcx
0x18002b12c  mov     rsi, [rcx+8]
0x18002b130  test    rsi, rsi
0x18002b133  jnz     short loc_18002B143
0x18002b135  mov     rdx, rbx
0x18002b138  call    ?SetCount@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(unsigned __int64,int)
0x18002b13d  test    al, al
0x18002b13f  jz      short loc_18002B150
0x18002b141  jmp     short loc_18002B19F
0x18002b143  lea     rdx, [rsi+r9]
0x18002b147  call    ?SetCount@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::SetCount(unsigned __int64,int)
0x18002b14c  test    al, al
0x18002b14e  jnz     short loc_18002B15B
0x18002b150  mov     ecx, 8007000Eh; int
0x18002b155  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002b15b  mov     [rsp+38h+arg_8], rsi
0x18002b160  shl     rsi, 5
0x18002b164  mov     rcx, [rdi]
0x18002b167  add     rcx, rsi
0x18002b16a  mov     rdx, rbx
0x18002b16d  call    ?CallDestructors@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@CAXPEAVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::CallDestructors(CAdapter *,unsigned __int64)
0x18002b172  mov     rcx, rbx
0x18002b175  shl     rcx, 5
0x18002b179  add     rcx, [rdi]; Destination
0x18002b17c  mov     r9, rsi; SourceSize
0x18002b17f  mov     r8, [rdi]; Source
0x18002b182  mov     rdx, rsi; DestinationSize
0x18002b185  call    cs:__imp_memmove_s
0x18002b18b  mov     ecx, eax; int
0x18002b18d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002b192  nop
0x18002b193  mov     rdx, rbx
0x18002b196  mov     rcx, [rdi]
0x18002b199  call    ?CallConstructors@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@CAXPEAVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::CallConstructors(CAdapter *,unsigned __int64)
0x18002b19e  nop
0x18002b19f  xor     esi, esi
0x18002b1a1  test    rbx, rbx
0x18002b1a4  jz      short loc_18002B1C0
0x18002b1a6  mov     rcx, rsi
0x18002b1a9  shl     rcx, 5
0x18002b1ad  add     rcx, [rdi]
0x18002b1b0  mov     rdx, r14
0x18002b1b3  call    ??4CAdapter@@QEAAAEBV0@AEBV0@@Z; CAdapter::operator=(CAdapter const &)
0x18002b1b8  inc     rsi
0x18002b1bb  cmp     rsi, rbx
0x18002b1be  jb      short loc_18002B1A6
0x18002b1c0  mov     rbx, [rsp+38h+arg_10]
0x18002b1c5  add     rsp, 20h
0x18002b1c9  pop     r14
0x18002b1cb  pop     rdi
0x18002b1cc  pop     rsi
0x18002b1cd  retn
```
