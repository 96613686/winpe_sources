# SdbDeclareIndexEx

- ea: `0x1400147d0`
- end: `0x140014b5b`
- name: `SdbDeclareIndexEx`
- size: `907`
- prototype: `__int64 __fastcall(_DWORD *, unsigned __int16, unsigned __int16, unsigned int, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d808`

## callees

- `0x14001008c`
- `0x140014500`
- `0x1400147d0`
- `0x140014b64`
- `0x140014d4c`
- `0x1400150b8`
- `0x140015838`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400149d9`
- `ntdll!RtlAllocateHeap` at `0x1400149d9`
- `ntdll!RtlFreeHeap` at `0x140014a36`
- `ntdll!RtlFreeHeap` at `0x140014a55`
- `ntdll!RtlFreeHeap` at `0x140014a36`
- `ntdll!RtlFreeHeap` at `0x140014a55`

## string_xrefs

- `0x1400148e5`: `Hit limit of %d indexes. Increase SDB_MAX_INDEXES and recompile`

## pseudocode

```c
__int64 __fastcall SdbDeclareIndexEx(
        _DWORD *a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6)
{
  __int64 v6; // r15
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // r12d
  unsigned int v13; // ecx
  unsigned int v14; // r15d
  PVOID Heap; // rbp
  int v16; // ecx
  int v18; // [rsp+34h] [rbp-54h]

  v6 = a4;
  if ( (a2 & 0xF000) != 0x7000 )
  {
    AslLogCallPrintf(1, "SdbDeclareIndexEx", 1802, "Illegal to index non-LIST tag");
    return 0;
  }
  if ( (a3 & 0xF000) == 0x7000 )
  {
    AslLogCallPrintf(1, "SdbDeclareIndexEx", 1807, "Illegal to use LIST type as a key");
    return 0;
  }
  v10 = 1;
  if ( (a5 & 2) != 0 )
  {
    if ( (a5 & 1) != 0 )
    {
      AslLogCallPrintf(1, "SdbDeclareIndexEx", 1817, "Illegal to use trailing characters for unique index");
      return 0;
    }
    if ( (a3 & 0xF000) != 0x6000 )
    {
      AslLogCallPrintf(1, "SdbDeclareIndexEx", 1827, "Illegal to use trailing characters for non-string attribute");
      return 0;
    }
  }
  if ( !a1[665] )
  {
    if ( a1[5] != 12 )
    {
      AslLogCallPrintf(1, "SdbDeclareIndexEx", 1833, "Began declaring indexes after writing other data");
      return 0;
    }
    a1[665] = 1;
    v11 = SdbBeginWriteListTag((__int64)a1, 30722);
    a1[666] = v11;
    if ( !v11 )
    {
      AslLogCallPrintf(1, "SdbDeclareIndexEx", 1839, "Error beginning TAG_INDEXES");
      return 0;
    }
  }
  if ( a1[659] == 64 )
  {
    AslLogCallPrintf(
      1,
      "SdbDeclareIndexEx",
      1845,
      "Hit limit of %d indexes. Increase SDB_MAX_INDEXES and recompile",
      64);
    return 0;
  }
  v12 = SdbBeginWriteListTag((__int64)a1, 30723);
  if ( !v12 )
  {
    AslLogCallPrintf(1, "SdbDeclareIndexEx", 1851, "Error beginning TAG_INDEX");
    return 0;
  }
  if ( !(unsigned int)SdbWriteWORDTag(a1, 14338, a2) )
  {
    AslLogCallPrintf(1, "SdbDeclareIndexEx", 1856, "Error writing TAG_INDEX_TAG");
    return 0;
  }
  if ( !(unsigned int)SdbWriteWORDTag(a1, 14339, a3) )
  {
    AslLogCallPrintf(1, "SdbDeclareIndexEx", 1861, "Error writing TAG_INDEX_KEY");
    return 0;
  }
  if ( a5 && !(unsigned int)SdbWriteDWORDTag(a1, 16406, a5) )
  {
    AslLogCallPrintf(1, "SdbDeclareIndexEx", 1866, "Error writing TAG_INDEX_FLAGS");
    return 0;
  }
  v13 = 12 * v6;
  if ( (unsigned __int64)(12 * v6) > 0xFFFFFFFF )
  {
    AslLogCallPrintf(1, "SdbDeclareIndexEx", 1875, "Invalid size allocation request");
    return 0;
  }
  v14 = 12 * v6;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v13);
  if ( !Heap )
    return 0;
  v18 = a1[5];
  if ( (unsigned int)SdbpWriteTagData(a1, 38913, Heap, v14) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( !(unsigned int)SdbEndWriteListTag(a1, v12) )
    {
      AslLogCallPrintf(1, "SdbDeclareIndexEx", 1895, "Error ending TAG_INDEX");
      return 0;
    }
    LOWORD(a1[10 * a1[659] + 13]) = a2;
    HIWORD(a1[10 * a1[659] + 13]) = a3;
    a1[10 * a1[659] + 12] = v18;
    a1[10 * a1[659] + 18] = v18 + 6;
    a1[10 * a1[659] + 19] = v14 + a1[10 * a1[659] + 18];
    *(_QWORD *)&a1[10 * a1[659] + 16] = -1;
    a1[10 * a1[659] + 15] = a5 & 1;
    a1[10 * a1[659] + 20] = a5;
    v16 = a1[659];
    *a6 = v16;
    a1[659] = v16 + 1;
  }
  else
  {
    AslLogCallPrintf(1, "SdbDeclareIndexEx", 1887, "Error writing TAG_INDEX_BITS");
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x1400147d0  mov     [rsp+arg_8], dx
0x1400147d5  push    rbx
0x1400147d6  push    rbp
0x1400147d7  push    rsi
0x1400147d8  push    rdi
0x1400147d9  push    r12
0x1400147db  push    r13
0x1400147dd  push    r14
0x1400147df  push    r15
0x1400147e1  sub     rsp, 48h
0x1400147e5  movzx   eax, dx
0x1400147e8  mov     r15d, r9d
0x1400147eb  mov     rdi, rcx
0x1400147ee  mov     [rsp+88h+var_58], 0
0x1400147f6  mov     ecx, 0F000h
0x1400147fb  movzx   ebp, dx
0x1400147fe  and     ax, cx
0x140014801  mov     edx, 7000h
0x140014806  movzx   r13d, r8w
0x14001480a  cmp     ax, dx
0x14001480d  jz      short loc_140014826
0x14001480f  lea     r9, aIllegalToIndex; "Illegal to index non-LIST tag"
0x140014816  mov     r8d, 70Ah
0x14001481c  mov     ecx, 1
0x140014821  jmp     loc_140014B38
0x140014826  movzx   eax, r13w
0x14001482a  and     ax, cx
0x14001482d  cmp     ax, dx
0x140014830  jnz     short loc_140014841
0x140014832  lea     r9, aIllegalToUseLi; "Illegal to use LIST type as a key"
0x140014839  mov     r8d, 70Fh
0x14001483f  jmp     short loc_14001481C
0x140014841  mov     esi, [rsp+88h+arg_20]
0x140014848  mov     ebx, 1
0x14001484d  mov     r14d, esi
0x140014850  and     r14d, ebx
0x140014853  test    sil, 2
0x140014857  jz      short loc_14001488C
0x140014859  test    r14d, r14d
0x14001485c  jz      short loc_140014870
0x14001485e  lea     r9, aIllegalToUseTr_0; "Illegal to use trailing characters for "...
0x140014865  mov     r8d, 719h
0x14001486b  jmp     loc_140014B36
0x140014870  mov     ecx, 6000h
0x140014875  cmp     ax, cx
0x140014878  jz      short loc_14001488C
0x14001487a  lea     r9, aIllegalToUseTr; "Illegal to use trailing characters for "...
0x140014881  mov     r8d, 723h
0x140014887  jmp     loc_140014B36
0x14001488c  cmp     dword ptr [rdi+0A64h], 0
0x140014893  jnz     short loc_1400148DC
0x140014895  cmp     dword ptr [rdi+14h], 0Ch
0x140014899  jz      short loc_1400148AD
0x14001489b  lea     r9, aBeganDeclaring; "Began declaring indexes after writing o"...
0x1400148a2  mov     r8d, 729h
0x1400148a8  jmp     loc_140014B36
0x1400148ad  mov     edx, 7802h
0x1400148b2  mov     [rdi+0A64h], ebx
0x1400148b8  mov     rcx, rdi
0x1400148bb  call    SdbBeginWriteListTag
0x1400148c0  mov     [rdi+0A68h], eax
0x1400148c6  test    eax, eax
0x1400148c8  jnz     short loc_1400148DC
0x1400148ca  lea     r9, aErrorBeginning_0; "Error beginning TAG_INDEXES"
0x1400148d1  mov     r8d, 72Fh
0x1400148d7  jmp     loc_140014B36
0x1400148dc  cmp     dword ptr [rdi+0A4Ch], 40h ; '@'
0x1400148e3  jnz     short loc_14001490D
0x1400148e5  lea     r9, aHitLimitOfDInd; "Hit limit of %d indexes. Increase SDB_M"...
0x1400148ec  mov     [rsp+88h+var_68], 40h ; '@'
0x1400148f4  mov     r8d, 735h
0x1400148fa  lea     rdx, aSdbdeclareinde; "SdbDeclareIndexEx"
0x140014901  mov     ecx, ebx
0x140014903  call    AslLogCallPrintf
0x140014908  jmp     loc_140014B44
0x14001490d  mov     edx, 7803h
0x140014912  mov     rcx, rdi
0x140014915  call    SdbBeginWriteListTag
0x14001491a  mov     r12d, eax
0x14001491d  test    eax, eax
0x14001491f  jnz     short loc_140014933
0x140014921  lea     r9, aErrorBeginning; "Error beginning TAG_INDEX"
0x140014928  mov     r8d, 73Bh
0x14001492e  jmp     loc_140014B36
0x140014933  mov     edx, 3802h
0x140014938  movzx   r8d, bp
0x14001493c  mov     rcx, rdi
0x14001493f  call    SdbWriteWORDTag
0x140014944  test    eax, eax
0x140014946  jnz     short loc_14001495A
0x140014948  lea     r9, aErrorWritingTa_1; "Error writing TAG_INDEX_TAG"
0x14001494f  mov     r8d, 740h
0x140014955  jmp     loc_140014B36
0x14001495a  mov     edx, 3803h
0x14001495f  movzx   r8d, r13w
0x140014963  mov     rcx, rdi
0x140014966  call    SdbWriteWORDTag
0x14001496b  test    eax, eax
0x14001496d  jnz     short loc_140014981
0x14001496f  lea     r9, aErrorWritingTa; "Error writing TAG_INDEX_KEY"
0x140014976  mov     r8d, 745h
0x14001497c  jmp     loc_140014B36
0x140014981  test    esi, esi
0x140014983  jz      short loc_1400149AB
0x140014985  mov     edx, 4016h
0x14001498a  mov     r8d, esi
0x14001498d  mov     rcx, rdi
0x140014990  call    SdbWriteDWORDTag
0x140014995  test    eax, eax
0x140014997  jnz     short loc_1400149AB
0x140014999  lea     r9, aErrorWritingTa_0; "Error writing TAG_INDEX_FLAGS"
0x1400149a0  mov     r8d, 74Ah
0x1400149a6  jmp     loc_140014B36
0x1400149ab  lea     rcx, [r15+r15*2]
0x1400149af  mov     eax, 0FFFFFFFFh
0x1400149b4  shl     rcx, 2
0x1400149b8  cmp     rcx, rax
0x1400149bb  ja      loc_140014B29
0x1400149c1  mov     r15d, ecx
0x1400149c4  mov     edx, 8; Flags
0x1400149c9  mov     r8d, ecx; Size
0x1400149cc  mov     rcx, gs:60h
0x1400149d5  mov     rcx, [rcx+30h]; HeapHandle
0x1400149d9  call    cs:__imp_RtlAllocateHeap
0x1400149df  mov     rbp, rax
0x1400149e2  test    rax, rax
0x1400149e5  jz      loc_140014B44
0x1400149eb  mov     eax, [rdi+14h]
0x1400149ee  mov     edx, 9801h
0x1400149f3  mov     r9d, r15d
0x1400149f6  mov     [rsp+88h+var_54], eax
0x1400149fa  mov     r8, rbp
0x1400149fd  mov     rcx, rdi
0x140014a00  call    SdbpWriteTagData
0x140014a05  test    eax, eax
0x140014a07  jnz     short loc_140014A43
0x140014a09  lea     r9, aErrorWritingTa_2; "Error writing TAG_INDEX_BITS"
0x140014a10  mov     r8d, 75Fh
0x140014a16  lea     rdx, aSdbdeclareinde; "SdbDeclareIndexEx"
0x140014a1d  mov     ecx, ebx
0x140014a1f  call    AslLogCallPrintf
0x140014a24  mov     rcx, gs:60h
0x140014a2d  mov     r8, rbp; P
0x140014a30  xor     edx, edx; Flags
0x140014a32  mov     rcx, [rcx+30h]; HeapHandle
0x140014a36  call    cs:__imp_RtlFreeHeap
0x140014a3c  xor     ebx, ebx
0x140014a3e  jmp     loc_140014B48
0x140014a43  mov     rcx, gs:60h
0x140014a4c  mov     r8, rbp; P
0x140014a4f  xor     edx, edx; Flags
0x140014a51  mov     rcx, [rcx+30h]; HeapHandle
0x140014a55  call    cs:__imp_RtlFreeHeap
0x140014a5b  mov     edx, r12d
0x140014a5e  mov     rcx, rdi
0x140014a61  call    SdbEndWriteListTag
0x140014a66  test    eax, eax
0x140014a68  jnz     short loc_140014A7C
0x140014a6a  lea     r9, aErrorEndingTag; "Error ending TAG_INDEX"
0x140014a71  mov     r8d, 767h
0x140014a77  jmp     loc_140014B36
0x140014a7c  mov     eax, [rdi+0A4Ch]
0x140014a82  lea     rcx, [rax+rax*4]
0x140014a86  movzx   eax, [rsp+88h+arg_8]
0x140014a8e  mov     [rdi+rcx*8+34h], ax
0x140014a93  mov     eax, [rdi+0A4Ch]
0x140014a99  lea     rcx, [rax+rax*4]
0x140014a9d  mov     [rdi+rcx*8+36h], r13w
0x140014aa3  mov     eax, [rdi+0A4Ch]
0x140014aa9  lea     rcx, [rax+rax*4]
0x140014aad  mov     eax, [rsp+88h+var_54]
0x140014ab1  mov     [rdi+rcx*8+30h], eax
0x140014ab5  lea     edx, [rax+6]
0x140014ab8  mov     eax, [rdi+0A4Ch]
0x140014abe  lea     rcx, [rax+rax*4]
0x140014ac2  mov     [rdi+rcx*8+48h], edx
0x140014ac6  mov     eax, [rdi+0A4Ch]
0x140014acc  lea     rdx, [rax+rax*4]
0x140014ad0  mov     ecx, [rdi+rdx*8+48h]
0x140014ad4  add     ecx, r15d
0x140014ad7  mov     [rdi+rdx*8+4Ch], ecx
0x140014adb  mov     eax, [rdi+0A4Ch]
0x140014ae1  lea     rcx, [rax+rax*4]
0x140014ae5  mov     qword ptr [rdi+rcx*8+40h], 0FFFFFFFFFFFFFFFFh
0x140014aee  mov     eax, [rdi+0A4Ch]
0x140014af4  lea     rcx, [rax+rax*4]
0x140014af8  mov     [rdi+rcx*8+3Ch], r14d
0x140014afd  mov     eax, [rdi+0A4Ch]
0x140014b03  add     rax, 2
0x140014b07  lea     rax, [rax+rax*4]
0x140014b0b  mov     [rdi+rax*8], esi
0x140014b0e  mov     ecx, [rdi+0A4Ch]
0x140014b14  mov     rax, [rsp+88h+arg_28]
0x140014b1c  mov     [rax], ecx
0x140014b1e  lea     eax, [rcx+1]
0x140014b21  mov     [rdi+0A4Ch], eax
0x140014b27  jmp     short loc_140014B48
0x140014b29  lea     r9, aInvalidSizeAll; "Invalid size allocation request"
0x140014b30  mov     r8d, 753h
0x140014b36  mov     ecx, ebx
0x140014b38  lea     rdx, aSdbdeclareinde; "SdbDeclareIndexEx"
0x140014b3f  call    AslLogCallPrintf
0x140014b44  mov     ebx, [rsp+88h+var_58]
0x140014b48  mov     eax, ebx
0x140014b4a  add     rsp, 48h
0x140014b4e  pop     r15
0x140014b50  pop     r14
0x140014b52  pop     r13
0x140014b54  pop     r12
0x140014b56  pop     rdi
0x140014b57  pop     rsi
0x140014b58  pop     rbp
0x140014b59  pop     rbx
0x140014b5a  retn
```
