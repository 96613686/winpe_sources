# ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::InsertAt(unsigned __int64,ATL::CComPtr<CUICommand> const &,unsigned __int64)

- ea: `0x18000fd20`
- end: `0x18000fde2`
- name: `?InsertAt@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAAX_KAEBV?$CComPtr@VCUICommand@@@2@0@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000fc8c`

## callees

- `0x180004c00`
- `0x1800054a0`
- `0x18000d578`
- `0x18000d5d0`
- `0x18000d60c`
- `0x18000fd20`
- `0x180011418`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000fd97`
- `msvcrt!memmove_s` at `0x18000fd97`

## pseudocode

```c
struct IUnknown *__fastcall ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::InsertAt(
        struct IUnknown **a1,
        __int64 a2,
        struct IUnknown **a3,
        unsigned __int64 a4)
{
  struct IUnknown *v7; // rbx
  struct IUnknown *result; // rax
  rsize_t v9; // rbx
  errno_t v10; // eax
  unsigned __int64 i; // rbx
  struct IUnknown **v12; // rcx
  errno_t v13; // eax
  struct IUnknown *v15; // [rsp+48h] [rbp+10h]

  v7 = a1[1];
  if ( !v7 )
  {
    result = (struct IUnknown *)ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(
                                  a1,
                                  a4);
    if ( (_BYTE)result )
      goto LABEL_7;
LABEL_5:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(
                           a1,
                           (char *)v7 + a4) )
    goto LABEL_5;
  v15 = v7;
  v9 = 8LL * (_QWORD)v7;
  ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallDestructors(
    &(*a1)[v9 / 8],
    a4);
  v10 = memmove_s(&(*a1)[a4], v9, *a1, v9);
  ATL::AtlCrtErrorCheck(v10);
  try
  {
    result = (struct IUnknown *)ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallConstructors(
                                  *a1,
                                  a4);
  }
  catch ( ... )
  {
    v13 = memmove_s(*a1, 8LL * (_QWORD)v15, &(*a1)[a4], 8LL * (_QWORD)v15);
    ATL::AtlCrtErrorCheck(v13);
    ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(a1, v15);
    throw;
  }
LABEL_7:
  for ( i = 0; i < a4; ++i )
  {
    result = *a1;
    v12 = (struct IUnknown **)&(*a1)[i];
    if ( *v12 != *a3 )
      result = ATL::AtlComPtrAssign(v12, *a3);
  }
  return result;
}

```

## disassembly

```asm
0x18000fd20  mov     rax, rsp
0x18000fd23  mov     [rax+18h], rbx
0x18000fd27  mov     [rax+20h], r9
0x18000fd2b  mov     [rax+10h], rdx
0x18000fd2f  mov     [rax+8], rcx
0x18000fd33  push    rsi
0x18000fd34  push    rdi
0x18000fd35  push    r14
0x18000fd37  sub     rsp, 20h
0x18000fd3b  mov     rdi, r9
0x18000fd3e  mov     r14, r8
0x18000fd41  mov     rsi, rcx
0x18000fd44  mov     rbx, [rcx+8]
0x18000fd48  test    rbx, rbx
0x18000fd4b  jnz     short loc_18000FD5B
0x18000fd4d  mov     rdx, r9
0x18000fd50  call    ?SetCount@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(unsigned __int64,int)
0x18000fd55  test    al, al
0x18000fd57  jz      short loc_18000FD68
0x18000fd59  jmp     short loc_18000FDB1
0x18000fd5b  lea     rdx, [rbx+r9]
0x18000fd5f  call    ?SetCount@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(unsigned __int64,int)
0x18000fd64  test    al, al
0x18000fd66  jnz     short loc_18000FD73
0x18000fd68  mov     ecx, 8007000Eh; int
0x18000fd6d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000fd73  mov     [rsp+38h+arg_8], rbx
0x18000fd78  shl     rbx, 3
0x18000fd7c  mov     rcx, [rsi]
0x18000fd7f  add     rcx, rbx
0x18000fd82  mov     rdx, rdi
0x18000fd85  call    ?CallDestructors@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@CAXPEAV?$CComPtr@VCUICommand@@@2@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallDestructors(ATL::CComPtr<CUICommand> *,unsigned __int64)
0x18000fd8a  mov     r8, [rsi]; Source
0x18000fd8d  lea     rcx, [r8+rdi*8]; Destination
0x18000fd91  mov     r9, rbx; SourceSize
0x18000fd94  mov     rdx, rbx; DestinationSize
0x18000fd97  call    cs:__imp_memmove_s
0x18000fd9d  mov     ecx, eax; int
0x18000fd9f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000fda4  nop
0x18000fda5  mov     rdx, rdi
0x18000fda8  mov     rcx, [rsi]
0x18000fdab  call    ?CallConstructors@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@CAXPEAV?$CComPtr@VCUICommand@@@2@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallConstructors(ATL::CComPtr<CUICommand> *,unsigned __int64)
0x18000fdb0  nop
0x18000fdb1  xor     ebx, ebx
0x18000fdb3  test    rdi, rdi
0x18000fdb6  jz      short loc_18000FDD4
0x18000fdb8  mov     rax, [rsi]
0x18000fdbb  lea     rcx, [rax+rbx*8]; struct IUnknown **
0x18000fdbf  mov     rdx, [r14]; struct IUnknown *
0x18000fdc2  cmp     [rcx], rdx
0x18000fdc5  jz      short loc_18000FDCC
0x18000fdc7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000fdcc  inc     rbx
0x18000fdcf  cmp     rbx, rdi
0x18000fdd2  jb      short loc_18000FDB8
0x18000fdd4  mov     rbx, [rsp+38h+arg_10]
0x18000fdd9  add     rsp, 20h
0x18000fddd  pop     r14
0x18000fddf  pop     rdi
0x18000fde0  pop     rsi
0x18000fde1  retn
```
