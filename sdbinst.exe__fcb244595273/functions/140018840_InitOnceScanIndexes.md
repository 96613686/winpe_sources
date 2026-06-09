# InitOnceScanIndexes

- ea: `0x140018840`
- end: `0x140018a9a`
- name: `InitOnceScanIndexes`
- size: `602`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14001008c`
- `0x140013cb8`
- `0x140013e60`
- `0x140014380`
- `0x14001443c`
- `0x140016148`
- `0x140018840`
- `0x14002e3e2`

## string_xrefs

- `0x140018a88`: `Too many indexes in file: recompile and increase SDB_MAX_INDEXES`

## pseudocode

```c
__int64 __fastcall InitOnceScanIndexes(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  _DWORD *v6; // r15
  unsigned int v7; // ebp
  unsigned int i; // eax
  unsigned int FirstTag; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  int v12; // edx
  __int64 v13; // rax
  unsigned int v14; // esi

  if ( !a2 )
  {
    AslLogCallPrintf(1, "InitOnceScanIndexes", 1346, "PDB was not supplied for InitOnceScanIndexes");
    return 0;
  }
  if ( !a3 )
  {
    AslLogCallPrintf(1, "InitOnceScanIndexes", 1352, "No return context was supplied for InitOnceScanIndexes");
    return 0;
  }
  v6 = a2 + 12;
  v7 = 0;
  memset_0(a2 + 12, 0, 0xA00u);
  if ( a2[5] > 0xCu )
  {
    if ( (unsigned __int16)SdbGetTagFromTagID(a2, 12) == 30722 )
    {
      a2[659] = 0;
      for ( i = SdbFindFirstTag(a2, 12, 30723); ; i = SdbFindNextTag(a2, 12, v14) )
      {
        v14 = i;
        if ( !i )
        {
          *a3 = v6;
          return 1;
        }
        if ( a2[659] == 64 )
          break;
        FirstTag = SdbFindFirstTag(a2, i, 14338);
        if ( !FirstTag )
        {
          AslLogCallPrintf(1, "InitOnceScanIndexes", 1394, "Index missing TAG_INDEX_TAG");
          return v7;
        }
        LOWORD(a2[10 * a2[659] + 13]) = SdbReadWORDTag(a2, FirstTag, 0);
        v10 = SdbFindFirstTag(a2, v14, 14339);
        if ( !v10 )
        {
          AslLogCallPrintf(1, "InitOnceScanIndexes", 1403, "Index missing TAG_INDEX_KEY");
          return v7;
        }
        HIWORD(a2[10 * a2[659] + 13]) = SdbReadWORDTag(a2, v10, 0);
        v11 = SdbFindFirstTag(a2, v14, 16406);
        if ( v11 )
          a2[10 * a2[659] + 20] = SdbReadDWORDTag(a2, v11, 0);
        else
          a2[10 * a2[659] + 20] = 0;
        v12 = SdbFindFirstTag(a2, v14, 38913);
        v13 = (unsigned int)a2[659];
        if ( !v12 )
        {
          LOWORD(a2[10 * v13 + 13]) = 0;
          AslLogCallPrintf(1, "InitOnceScanIndexes", 1420, "Index missing TAG_INDEX_BITS");
          return v7;
        }
        a2[10 * v13 + 12] = v12;
        ++a2[659];
      }
      AslLogCallPrintf(
        1,
        "InitOnceScanIndexes",
        1387,
        "Too many indexes in file: recompile and increase SDB_MAX_INDEXES");
    }
    else
    {
      AslLogCallPrintf(1, "InitOnceScanIndexes", 1372, "Root child tag is not index tagid 0x%lx", 12);
    }
  }
  else
  {
    AslLogCallPrintf(1, "InitOnceScanIndexes", 1367, "Failed to get the child index from root");
  }
  return v7;
}

```

## disassembly

```asm
0x140018840  push    rbx
0x140018842  push    rbp
0x140018843  push    rsi
0x140018844  push    r14
0x140018846  push    r15
0x140018848  sub     rsp, 30h
0x14001884c  mov     r14, r8
0x14001884f  mov     rbx, rdx
0x140018852  test    rdx, rdx
0x140018855  jnz     short loc_14001887C
0x140018857  lea     r9, aPdbWasNotSuppl; "PDB was not supplied for InitOnceScanIn"...
0x14001885e  mov     r8d, 542h
0x140018864  lea     rdx, aInitoncescanin; "InitOnceScanIndexes"
0x14001886b  mov     ecx, 1
0x140018870  call    AslLogCallPrintf
0x140018875  xor     eax, eax
0x140018877  jmp     loc_140018A3F
0x14001887c  test    r14, r14
0x14001887f  jnz     short loc_140018890
0x140018881  lea     r9, aNoReturnContex; "No return context was supplied for Init"...
0x140018888  mov     r8d, 548h
0x14001888e  jmp     short loc_140018864
0x140018890  lea     r15, [rdx+30h]
0x140018894  mov     r8d, 0A00h; Size
0x14001889a  mov     rcx, r15; void *
0x14001889d  xor     edx, edx; Val
0x14001889f  xor     ebp, ebp
0x1400188a1  call    memset_0
0x1400188a6  cmp     dword ptr [rbx+14h], 0Ch
0x1400188aa  ja      short loc_1400188CF
0x1400188ac  lea     r9, aFailedToGetThe_2; "Failed to get the child index from root"
0x1400188b3  mov     r8d, 557h
0x1400188b9  lea     rdx, aInitoncescanin; "InitOnceScanIndexes"
0x1400188c0  mov     ecx, 1
0x1400188c5  call    AslLogCallPrintf
0x1400188ca  jmp     loc_140018A3D
0x1400188cf  mov     edx, 0Ch
0x1400188d4  mov     rcx, rbx
0x1400188d7  call    SdbGetTagFromTagID
0x1400188dc  mov     ecx, 7802h
0x1400188e1  cmp     ax, cx
0x1400188e4  jz      short loc_140018911
0x1400188e6  lea     r9, aRootChildTagIs; "Root child tag is not index tagid 0x%lx"
0x1400188ed  mov     [rsp+58h+var_38], 0Ch
0x1400188f5  mov     r8d, 55Ch
0x1400188fb  lea     rdx, aInitoncescanin; "InitOnceScanIndexes"
0x140018902  mov     ecx, 1
0x140018907  call    AslLogCallPrintf
0x14001890c  jmp     loc_140018A3D
0x140018911  mov     edx, 0Ch
0x140018916  mov     [rbx+0A4Ch], ebp
0x14001891c  mov     r8d, 7803h
0x140018922  mov     rcx, rbx
0x140018925  call    SdbFindFirstTag
0x14001892a  jmp     loc_140018A2B
0x14001892f  cmp     dword ptr [rbx+0A4Ch], 40h ; '@'
0x140018936  jz      loc_140018A88
0x14001893c  mov     r8d, 3802h
0x140018942  mov     edx, esi
0x140018944  mov     rcx, rbx
0x140018947  call    SdbFindFirstTag
0x14001894c  test    eax, eax
0x14001894e  jz      loc_140018A76
0x140018954  xor     r8d, r8d
0x140018957  mov     edx, eax
0x140018959  mov     rcx, rbx
0x14001895c  call    SdbReadWORDTag
0x140018961  movzx   edx, ax
0x140018964  mov     r8d, 3803h
0x14001896a  mov     eax, [rbx+0A4Ch]
0x140018970  lea     rcx, [rax+rax*4]
0x140018974  mov     [rbx+rcx*8+34h], dx
0x140018979  mov     edx, esi
0x14001897b  mov     rcx, rbx
0x14001897e  call    SdbFindFirstTag
0x140018983  test    eax, eax
0x140018985  jz      loc_140018A64
0x14001898b  xor     r8d, r8d
0x14001898e  mov     edx, eax
0x140018990  mov     rcx, rbx
0x140018993  call    SdbReadWORDTag
0x140018998  movzx   edx, ax
0x14001899b  mov     r8d, 4016h
0x1400189a1  mov     eax, [rbx+0A4Ch]
0x1400189a7  lea     rcx, [rax+rax*4]
0x1400189ab  mov     [rbx+rcx*8+36h], dx
0x1400189b0  mov     edx, esi
0x1400189b2  mov     rcx, rbx
0x1400189b5  call    SdbFindFirstTag
0x1400189ba  test    eax, eax
0x1400189bc  jz      short loc_1400189E0
0x1400189be  xor     r8d, r8d
0x1400189c1  mov     edx, eax
0x1400189c3  mov     rcx, rbx
0x1400189c6  call    SdbReadDWORDTag
0x1400189cb  mov     ecx, [rbx+0A4Ch]
0x1400189d1  mov     edx, eax
0x1400189d3  add     rcx, 2
0x1400189d7  lea     rax, [rcx+rcx*4]
0x1400189db  mov     [rbx+rax*8], edx
0x1400189de  jmp     short loc_1400189F1
0x1400189e0  mov     eax, [rbx+0A4Ch]
0x1400189e6  add     rax, 2
0x1400189ea  lea     rax, [rax+rax*4]
0x1400189ee  mov     [rbx+rax*8], ebp
0x1400189f1  mov     r8d, 9801h
0x1400189f7  mov     edx, esi
0x1400189f9  mov     rcx, rbx
0x1400189fc  call    SdbFindFirstTag
0x140018a01  mov     edx, eax
0x140018a03  mov     eax, [rbx+0A4Ch]
0x140018a09  lea     rcx, [rax+rax*4]
0x140018a0d  test    edx, edx
0x140018a0f  jz      short loc_140018A4B
0x140018a11  mov     [rbx+rcx*8+30h], edx
0x140018a15  mov     r8d, esi
0x140018a18  inc     dword ptr [rbx+0A4Ch]
0x140018a1e  mov     edx, 0Ch
0x140018a23  mov     rcx, rbx
0x140018a26  call    SdbFindNextTag
0x140018a2b  mov     esi, eax
0x140018a2d  test    eax, eax
0x140018a2f  jnz     loc_14001892F
0x140018a35  mov     [r14], r15
0x140018a38  mov     ebp, 1
0x140018a3d  mov     eax, ebp
0x140018a3f  add     rsp, 30h
0x140018a43  pop     r15
0x140018a45  pop     r14
0x140018a47  pop     rsi
0x140018a48  pop     rbp
0x140018a49  pop     rbx
0x140018a4a  retn
0x140018a4b  xor     eax, eax
0x140018a4d  lea     r9, aIndexMissingTa; "Index missing TAG_INDEX_BITS"
0x140018a54  mov     [rbx+rcx*8+34h], ax
0x140018a59  mov     r8d, 58Ch
0x140018a5f  jmp     loc_1400188B9
0x140018a64  lea     r9, aIndexMissingTa_1; "Index missing TAG_INDEX_KEY"
0x140018a6b  mov     r8d, 57Bh
0x140018a71  jmp     loc_1400188B9
0x140018a76  lea     r9, aIndexMissingTa_0; "Index missing TAG_INDEX_TAG"
0x140018a7d  mov     r8d, 572h
0x140018a83  jmp     loc_1400188B9
0x140018a88  lea     r9, aTooManyIndexes; "Too many indexes in file: recompile and"...
0x140018a8f  mov     r8d, 56Bh
0x140018a95  jmp     loc_1400188B9
```
