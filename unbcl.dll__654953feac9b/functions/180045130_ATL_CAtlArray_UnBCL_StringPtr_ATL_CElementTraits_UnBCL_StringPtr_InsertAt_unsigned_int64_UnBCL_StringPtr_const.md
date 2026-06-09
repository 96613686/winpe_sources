# ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::InsertAt(unsigned __int64,UnBCL::StringPtr const &,unsigned __int64)

- ea: `0x180045130`
- end: `0x180045270`
- name: `?InsertAt@?$CAtlArray@VStringPtr@UnBCL@@V?$CElementTraits@VStringPtr@UnBCL@@@ATL@@@ATL@@QEAAX_KAEBVStringPtr@UnBCL@@0@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180045064`

## callees

- `0x180002f50`
- `0x1800066cc`
- `0x1800434a4`
- `0x180043508`
- `0x180045130`
- `0x1800461e8`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800451d9`
- `msvcrt!memmove_s` at `0x1800451d9`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::InsertAt(
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
    if ( (unsigned __int8)ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::SetCount(
                            a1,
                            v6 + 1,
                            0xFFFFFFFFLL) )
    {
      ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::CallDestructors(*a1 + 32 * v6, 1);
      v7 = v4 + 1;
      v9 = memmove_s(
             (void *const)(*a1 + 32 * (v4 + 1)),
             32 * (v6 - v4),
             (const void *const)(*a1 + 32 * v4),
             32 * (v6 - v4));
      if ( !v9 )
      {
LABEL_10:
        result = ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::CallConstructors(
                   32 * v4 + *a1,
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
  result = ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::SetCount(a1, a2 + 1, 0xFFFFFFFFLL);
  if ( !(_BYTE)result )
    goto LABEL_14;
LABEL_12:
  while ( v4 < v7 )
  {
    result = UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(
               *a1 + 32 * v4 + 8 + *(int *)(*(_QWORD *)(*a1 + 32 * v4 + 8) + 4LL),
               *(_QWORD *)(*(int *)(*(_QWORD *)(a3 + 8) + 4LL) + a3 + 16));
    ++v4;
  }
  return result;
}

```

## disassembly

```asm
0x180045130  mov     rax, rsp
0x180045133  mov     [rax+20h], r9
0x180045137  mov     [rax+10h], rdx
0x18004513b  mov     [rax+8], rcx
0x18004513f  push    rsi
0x180045140  push    rdi
0x180045141  push    r12
0x180045143  push    r14
0x180045145  push    r15
0x180045147  sub     rsp, 30h
0x18004514b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180045153  mov     [rax+18h], rbx
0x180045157  mov     r15, r8
0x18004515a  mov     rbx, rdx
0x18004515d  mov     rdi, rcx
0x180045160  mov     rsi, [rcx+8]
0x180045164  or      r8d, 0FFFFFFFFh
0x180045168  cmp     rdx, rsi
0x18004516b  jb      short loc_180045186
0x18004516d  lea     r14, [rdx+1]
0x180045171  mov     rdx, r14
0x180045174  call    ?SetCount@?$CAtlArray@VStringPtr@UnBCL@@V?$CElementTraits@VStringPtr@UnBCL@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::SetCount(unsigned __int64,int)
0x180045179  test    al, al
0x18004517b  jz      loc_18004524F
0x180045181  jmp     loc_180045238
0x180045186  lea     rdx, [rsi+1]
0x18004518a  call    ?SetCount@?$CAtlArray@VStringPtr@UnBCL@@V?$CElementTraits@VStringPtr@UnBCL@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::SetCount(unsigned __int64,int)
0x18004518f  test    al, al
0x180045191  jz      loc_18004524F
0x180045197  mov     [rsp+58h+arg_18], rsi
0x18004519c  mov     rcx, rsi
0x18004519f  shl     rcx, 5
0x1800451a3  add     rcx, [rdi]
0x1800451a6  mov     edx, 1
0x1800451ab  call    ?CallDestructors@?$CAtlArray@VStringPtr@UnBCL@@V?$CElementTraits@VStringPtr@UnBCL@@@ATL@@@ATL@@CAXPEAVStringPtr@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::CallDestructors(UnBCL::StringPtr *,unsigned __int64)
0x1800451b0  mov     rax, [rdi]
0x1800451b3  mov     r12, rbx
0x1800451b6  shl     r12, 5
0x1800451ba  sub     rsi, rbx
0x1800451bd  shl     rsi, 5
0x1800451c1  lea     r14, [rbx+1]
0x1800451c5  lea     r8, [rax+r12]; Source
0x1800451c9  mov     rcx, r14
0x1800451cc  shl     rcx, 5
0x1800451d0  add     rcx, rax; Destination
0x1800451d3  mov     r9, rsi; SourceSize
0x1800451d6  mov     rdx, rsi; DestinationSize
0x1800451d9  call    cs:__imp_memmove_s
0x1800451df  test    eax, eax
0x1800451e1  jz      short loc_1800451F7
0x1800451e3  cmp     eax, 0Ch
0x1800451e6  jz      short loc_18004524F
0x1800451e8  cmp     eax, 16h
0x1800451eb  jz      short loc_180045265
0x1800451ed  cmp     eax, 22h ; '"'
0x1800451f0  jz      short loc_180045265
0x1800451f2  cmp     eax, 50h ; 'P'
0x1800451f5  jnz     short loc_18004525A
0x1800451f7  mov     rcx, [rdi]
0x1800451fa  add     rcx, r12
0x1800451fd  mov     edx, 1
0x180045202  call    ?CallConstructors@?$CAtlArray@VStringPtr@UnBCL@@V?$CElementTraits@VStringPtr@UnBCL@@@ATL@@@ATL@@CAXPEAVStringPtr@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::StringPtr,ATL::CElementTraits<UnBCL::StringPtr>>::CallConstructors(UnBCL::StringPtr *,unsigned __int64)
0x180045207  nop
0x180045208  jmp     short loc_180045238
0x18004520a  mov     r8, rbx
0x18004520d  shl     r8, 5
0x180045211  add     r8, [rdi]
0x180045214  mov     rax, [r15+8]
0x180045218  movsxd  rdx, dword ptr [rax+4]
0x18004521c  mov     rax, [r8+8]
0x180045220  movsxd  rcx, dword ptr [rax+4]
0x180045224  add     r8, 8
0x180045228  add     rcx, r8
0x18004522b  mov     rdx, [rdx+r15+10h]
0x180045230  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180045235  inc     rbx
0x180045238  cmp     rbx, r14
0x18004523b  jb      short loc_18004520A
0x18004523d  mov     rbx, [rsp+58h+arg_10]
0x180045242  add     rsp, 30h
0x180045246  pop     r15
0x180045248  pop     r14
0x18004524a  pop     r12
0x18004524c  pop     rdi
0x18004524d  pop     rsi
0x18004524e  retn
0x18004524f  mov     ecx, 8007000Eh; int
0x180045254  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004525a  mov     ecx, 80004005h; int
0x18004525f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180045265  mov     ecx, 80070057h; int
0x18004526a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
