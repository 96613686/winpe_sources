# ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::InsertAt(unsigned __int64,UnBCL::SmartPtr<UnBCL::String> const &,unsigned __int64)

- ea: `0x18002df30`
- end: `0x18002e058`
- name: `?InsertAt@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@QEAAX_KAEBV?$SmartPtr@VString@UnBCL@@@UnBCL@@0@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002de64`

## callees

- `0x180002f50`
- `0x1800066cc`
- `0x18002803c`
- `0x180028090`
- `0x18002df30`
- `0x18002fec8`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002dfd9`
- `msvcrt!memmove_s` at `0x18002dfd9`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::InsertAt(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r14
  __int64 result; // rax
  errno_t v9; // eax

  v4 = a2;
  v6 = a1[1];
  if ( a2 < v6 )
  {
    if ( (unsigned __int8)ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::SetCount(
                            a1,
                            v6 + 1,
                            0xFFFFFFFFLL) )
    {
      ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallDestructors(
        *a1 + 16 * v6,
        1);
      v7 = v4 + 1;
      v9 = memmove_s(
             (void *const)(*a1 + 16 * (v4 + 1)),
             16 * (v6 - v4),
             (const void *const)(*a1 + 16 * v4),
             16 * (v6 - v4));
      if ( !v9 )
      {
LABEL_10:
        result = ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallConstructors(
                   16 * v4 + *a1,
                   1);
        goto LABEL_12;
      }
      if ( v9 != 12 )
      {
        if ( v9 == 22 || v9 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v9 != 80 )
          ATL::AtlThrowImpl(-2147467259);
        goto LABEL_10;
      }
    }
LABEL_14:
    ATL::AtlThrowImpl(-2147024882);
  }
  v7 = a2 + 1;
  result = ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::SetCount(
             a1,
             a2 + 1,
             0xFFFFFFFFLL);
  if ( !(_BYTE)result )
    goto LABEL_14;
LABEL_12:
  while ( v4 < v7 )
    result = UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(*a1 + 16 * v4++, *(_QWORD *)(a3 + 8));
  return result;
}

```

## disassembly

```asm
0x18002df30  mov     rax, rsp
0x18002df33  mov     [rax+20h], r9
0x18002df37  mov     [rax+10h], rdx
0x18002df3b  mov     [rax+8], rcx
0x18002df3f  push    rsi
0x18002df40  push    rdi
0x18002df41  push    r13
0x18002df43  push    r14
0x18002df45  push    r15
0x18002df47  sub     rsp, 30h
0x18002df4b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18002df53  mov     [rax+18h], rbx
0x18002df57  mov     r13, r8
0x18002df5a  mov     rbx, rdx
0x18002df5d  mov     rdi, rcx
0x18002df60  mov     rsi, [rcx+8]
0x18002df64  or      r8d, 0FFFFFFFFh
0x18002df68  cmp     rdx, rsi
0x18002df6b  jb      short loc_18002DF86
0x18002df6d  lea     r14, [rdx+1]
0x18002df71  mov     rdx, r14
0x18002df74  call    ?SetCount@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::SetCount(unsigned __int64,int)
0x18002df79  test    al, al
0x18002df7b  jz      loc_18002E037
0x18002df81  jmp     loc_18002E020
0x18002df86  lea     rdx, [rsi+1]
0x18002df8a  call    ?SetCount@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::SetCount(unsigned __int64,int)
0x18002df8f  test    al, al
0x18002df91  jz      loc_18002E037
0x18002df97  mov     [rsp+58h+arg_18], rsi
0x18002df9c  mov     rcx, rsi
0x18002df9f  shl     rcx, 4
0x18002dfa3  add     rcx, [rdi]
0x18002dfa6  mov     edx, 1
0x18002dfab  call    ?CallDestructors@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@CAXPEAV?$SmartPtr@VString@UnBCL@@@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallDestructors(UnBCL::SmartPtr<UnBCL::String> *,unsigned __int64)
0x18002dfb0  mov     rax, [rdi]
0x18002dfb3  mov     r15, rbx
0x18002dfb6  shl     r15, 4
0x18002dfba  sub     rsi, rbx
0x18002dfbd  shl     rsi, 4
0x18002dfc1  lea     r14, [rbx+1]
0x18002dfc5  lea     r8, [rax+r15]; Source
0x18002dfc9  mov     rcx, r14
0x18002dfcc  shl     rcx, 4
0x18002dfd0  add     rcx, rax; Destination
0x18002dfd3  mov     r9, rsi; SourceSize
0x18002dfd6  mov     rdx, rsi; DestinationSize
0x18002dfd9  call    cs:__imp_memmove_s
0x18002dfdf  test    eax, eax
0x18002dfe1  jz      short loc_18002DFF7
0x18002dfe3  cmp     eax, 0Ch
0x18002dfe6  jz      short loc_18002E037
0x18002dfe8  cmp     eax, 16h
0x18002dfeb  jz      short loc_18002E04D
0x18002dfed  cmp     eax, 22h ; '"'
0x18002dff0  jz      short loc_18002E04D
0x18002dff2  cmp     eax, 50h ; 'P'
0x18002dff5  jnz     short loc_18002E042
0x18002dff7  mov     rcx, [rdi]
0x18002dffa  add     rcx, r15
0x18002dffd  mov     edx, 1
0x18002e002  call    ?CallConstructors@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@CAXPEAV?$SmartPtr@VString@UnBCL@@@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallConstructors(UnBCL::SmartPtr<UnBCL::String> *,unsigned __int64)
0x18002e007  nop
0x18002e008  jmp     short loc_18002E020
0x18002e00a  mov     rcx, rbx
0x18002e00d  shl     rcx, 4
0x18002e011  add     rcx, [rdi]
0x18002e014  mov     rdx, [r13+8]
0x18002e018  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002e01d  inc     rbx
0x18002e020  cmp     rbx, r14
0x18002e023  jb      short loc_18002E00A
0x18002e025  mov     rbx, [rsp+58h+arg_10]
0x18002e02a  add     rsp, 30h
0x18002e02e  pop     r15
0x18002e030  pop     r14
0x18002e032  pop     r13
0x18002e034  pop     rdi
0x18002e035  pop     rsi
0x18002e036  retn
0x18002e037  mov     ecx, 8007000Eh; int
0x18002e03c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002e042  mov     ecx, 80004005h; int
0x18002e047  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002e04d  mov     ecx, 80070057h; int
0x18002e052  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
