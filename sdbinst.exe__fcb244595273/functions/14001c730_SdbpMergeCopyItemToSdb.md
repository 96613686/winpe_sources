# SdbpMergeCopyItemToSdb

- ea: `0x14001c730`
- end: `0x14001cc98`
- name: `SdbpMergeCopyItemToSdb`
- size: `1384`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x14001c730`
- `0x14001d808`
- `0x14002069c`

## callees

- `0x14001008c`
- `0x140013824`
- `0x140013898`
- `0x140013938`
- `0x140013b84`
- `0x140013cb8`
- `0x140013dc0`
- `0x140013e60`
- `0x140014500`
- `0x140014b64`
- `0x140014d4c`
- `0x140014f94`
- `0x140014fe0`
- `0x1400150b8`
- `0x140015838`
- `0x140015e14`
- `0x140016070`
- `0x140016148`
- `0x14001c730`
- `0x14002e3e2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001cad8`
- `ntdll!RtlAllocateHeap` at `0x14001cad8`
- `ntdll!RtlReAllocateHeap` at `0x14001cafd`
- `ntdll!RtlReAllocateHeap` at `0x14001cafd`

## string_xrefs

- `0x14001c803`: `SdbpMergeCopyItemToSdb`
- `0x14001cc74`: `SdbpMergeCopyItemToSdb`
- `0x14001cc67`: `Failed to copy TAG_TYPE_NULL to output sdb`
- `0x14001c919`: `SdbEndWriteListTag failed to write end of list tag`
- `0x14001cbe7`: `Failed to copy TAG_TYPE_WORD to output sdb`
- `0x14001cc32`: `Failed to copy TAG_TYPE_BYTE to output sdb`
- `0x14001ca28`: `Attempt to copy from an unknown pdb to the output pdb`
- `0x14001c9e8`: `Failed to read tagid from original pdb`
- `0x14001cbb4`: `Failed to copy TAG_TYPE_DWORD to output sdb`
- `0x14001c93b`: `Failed to read string from original sdb`
- `0x14001c999`: `Failed to copy TAG_TYPE_QWORD to output sdb`
- `0x14001c963`: `Failed to write string/stringref to output sdb`
- `0x14001c88f`: `Failed to write binary data (size: %d)`

## pseudocode

```c
__int64 __fastcall SdbpMergeCopyItemToSdb(__int64 *a1, int a2, int a3, _QWORD **a4, unsigned __int64 *a5)
{
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 v8; // rcx
  __int64 v10; // rbp
  unsigned __int16 TagFromTagID; // ax
  unsigned int v12; // r12d
  unsigned __int16 v13; // di
  int v14; // ecx
  unsigned int TagDataSize; // esi
  __int64 BinaryTagData; // r8
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned int FirstChild; // edi
  __int64 v21; // r14
  __int64 StringTagPtr; // rax
  __int64 QWORDTag; // rax
  __int64 v24; // rax
  int v25; // r15d
  unsigned __int64 *v26; // rsi
  _QWORD *v27; // r13
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rcx
  __int64 v30; // r12
  unsigned __int64 v31; // r12
  unsigned __int128 v32; // rax
  void *v33; // r8
  void *v34; // rcx
  PVOID v35; // rax
  PVOID Heap; // r14
  _QWORD *v37; // r8
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // kr40_8
  _DWORD *v40; // rax
  unsigned int DWORDTag; // eax
  unsigned __int16 WORDTag; // ax
  __int128 v44; // [rsp+30h] [rbp-58h] BYREF
  size_t Size; // [rsp+90h] [rbp+8h]
  int v47; // [rsp+A0h] [rbp+18h] BYREF
  unsigned __int64 v48; // [rsp+A8h] [rbp+20h]

  v47 = a3;
  v5 = a4[2];
  v6 = *((unsigned int *)a1 + 2);
  v8 = *a1;
  v44 = 0;
  v10 = *v5;
  TagFromTagID = SdbGetTagFromTagID(v8, v6);
  v12 = *(_DWORD *)(v10 + 20);
  v13 = TagFromTagID;
  v47 = v12;
  v14 = TagFromTagID & 0xF000;
  switch ( v14 )
  {
    case 4096:
      if ( (TagFromTagID & 0xF000) != 0x1000 || !(unsigned int)SdbpWriteTagData(v10, TagFromTagID, 0, 0) )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1555, "Failed to copy TAG_TYPE_NULL to output sdb");
        return 0;
      }
      return v12;
    case 8192:
      LOBYTE(v47) = SdbReadBYTETag(*a1, *((unsigned int *)a1 + 2));
      if ( (v13 & 0xF000) != 0x2000 || !(unsigned int)SdbpWriteTagData(v10, v13, &v47, 1) )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1563, "Failed to copy TAG_TYPE_BYTE to output sdb");
        return 0;
      }
      return v12;
    case 12288:
      WORDTag = SdbReadWORDTag(*a1, *((unsigned int *)a1 + 2), 0);
      if ( !(unsigned int)SdbWriteWORDTag(v10, v13, WORDTag) )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1571, "Failed to copy TAG_TYPE_WORD to output sdb");
        return 0;
      }
      return v12;
    case 16384:
      if ( TagFromTagID == 16477 )
      {
        v25 = 34;
      }
      else
      {
        v24 = 0;
        while ( *((_WORD *)qword_140039F50 + v24) != v13 )
        {
          if ( (unsigned __int64)++v24 >= 9 )
            goto LABEL_59;
        }
        if ( !(unsigned int)SdbReadDWORDTag(*a1, *((unsigned int *)a1 + 2), 0) )
        {
          AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1589, "Failed to read tagid from original pdb");
          return 0;
        }
        a2 = *((_DWORD *)a1 + 2);
        if ( *a1 == **a4 )
        {
          v25 = 16;
        }
        else
        {
          if ( *a1 != *a4[1] )
          {
            AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1628, "Attempt to copy from an unknown pdb to the output pdb");
            return 0;
          }
          v25 = 17;
        }
      }
      v26 = a5;
      v27 = a5 + 2;
      v28 = a5[2];
      v48 = v28;
      if ( v28 < a5[3] )
      {
        v37 = a5 + 2;
      }
      else
      {
        v29 = v28 + 1;
        if ( v28 + 1 <= a5[3] )
          goto LABEL_54;
        v30 = a5[4] - 1;
        if ( v30 + v29 < v29 )
          goto LABEL_54;
        if ( !is_mul_ok(a5[3], a5[1]) )
          goto LABEL_54;
        v31 = (v30 + v29) & ~v30;
        v32 = v31 * (unsigned __int128)a5[1];
        Size = v31 * a5[1];
        if ( !is_mul_ok(v31, a5[1]) )
          goto LABEL_54;
        v33 = (void *)a5[5];
        v34 = (void *)*a5;
        if ( v33 )
        {
          Heap = RtlReAllocateHeap(v34, DWORD2(v32), v33, v32);
        }
        else
        {
          v35 = RtlAllocateHeap(v34, DWORD2(v32), v32);
          Heap = v35;
          if ( v35 )
            memset_0(v35, 0, Size);
        }
        if ( !Heap )
          goto LABEL_54;
        v28 = v48;
        v37 = v26 + 2;
        v26[3] = v31;
        v12 = v47;
        v26[5] = (unsigned __int64)Heap;
      }
      v39 = v28;
      v38 = v26[1] * v28;
      if ( is_mul_ok(v26[1], v39) )
      {
        v40 = (_DWORD *)(v26[5] + v38);
        if ( (unsigned __int64)v40 >= v26[5] )
        {
          *v40 = a2;
          v40[1] = v25;
          v40[2] = v12;
          *v27 = *v37 + 1LL;
LABEL_59:
          DWORDTag = SdbReadDWORDTag(*a1, *((unsigned int *)a1 + 2), 0);
          if ( !(unsigned int)SdbWriteDWORDTag(v10, v13, DWORDTag) )
          {
            AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1640, "Failed to copy TAG_TYPE_DWORD to output sdb");
            return 0;
          }
          return v12;
        }
      }
LABEL_54:
      AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1634, "Failed to append fix tagid refernce info.");
      return 0;
    case 20480:
      QWORDTag = SdbReadQWORDTag(*a1, *((unsigned int *)a1 + 2), 0);
      if ( !(unsigned int)SdbWriteQWORDTag(v10, v13, QWORDTag) )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1648, "Failed to copy TAG_TYPE_QWORD to output sdb");
        return 0;
      }
      return v12;
    case 24576:
      goto LABEL_24;
    case 28672:
      v17 = SdbBeginWriteListTag(v10, TagFromTagID);
      v18 = *a1;
      v12 = v17;
      v19 = *((unsigned int *)a1 + 2);
      v44 = (unsigned __int64)*a1;
      FirstChild = SdbGetFirstChild(v18, v19);
      if ( FirstChild )
      {
        v21 = (__int64)a5;
        do
        {
          DWORD2(v44) = FirstChild;
          SdbpMergeCopyItemToSdb((unsigned int)&v44, v12, 0, (_DWORD)a4, v21);
          FirstChild = SdbGetNextChild(*a1, *((unsigned int *)a1 + 2), FirstChild);
        }
        while ( FirstChild );
      }
      if ( !(unsigned int)SdbEndWriteListTag(v10, v12) )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1547, "SdbEndWriteListTag failed to write end of list tag");
        return 0;
      }
      return v12;
    case 32768:
LABEL_24:
      StringTagPtr = SdbGetStringTagPtr(*a1, *((unsigned int *)a1 + 2));
      if ( !StringTagPtr )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1658, "Failed to read string from original sdb");
        return 0;
      }
      if ( !(unsigned int)SdbWriteStringTag(v10, v13, StringTagPtr) )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1663, "Failed to write string/stringref to output sdb");
        return 0;
      }
      return v12;
    case 36864:
      TagDataSize = SdbGetTagDataSize(*a1, *((unsigned int *)a1 + 2));
      if ( TagDataSize == 0x20000000 )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1673, "SdbGetTagDataSize failed to return data size");
        return 0;
      }
      BinaryTagData = SdbGetBinaryTagData(*a1, *((unsigned int *)a1 + 2));
      if ( !BinaryTagData && TagDataSize )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1680, "SdbGetBinaryTagData failed to return data");
        return 0;
      }
      if ( (v13 & 0xF000) != 0x9000 || !(unsigned int)SdbpWriteTagData(v10, v13, BinaryTagData, TagDataSize) )
      {
        AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1685, "Failed to write binary data (size: %d)", TagDataSize);
        return 0;
      }
      return v12;
  }
  AslLogCallPrintf(1, "SdbpMergeCopyItemToSdb", 1693, "Unknown tag type encountered for tag: %x", TagFromTagID);
  return 0;
}

```

## disassembly

```asm
0x14001c730  mov     [rsp+arg_10], r8d
0x14001c735  mov     [rsp+arg_8], edx
0x14001c739  push    rbx
0x14001c73a  push    rbp
0x14001c73b  push    rsi
0x14001c73c  push    rdi
0x14001c73d  push    r12
0x14001c73f  push    r13
0x14001c741  push    r14
0x14001c743  push    r15
0x14001c745  sub     rsp, 48h
0x14001c749  mov     rax, [r9+10h]
0x14001c74d  xorps   xmm0, xmm0
0x14001c750  mov     edx, [rcx+8]
0x14001c753  mov     rbx, rcx
0x14001c756  mov     rcx, [rcx]
0x14001c759  mov     rsi, r9
0x14001c75c  movups  [rsp+88h+var_58], xmm0
0x14001c761  mov     rbp, [rax]
0x14001c764  call    SdbGetTagFromTagID
0x14001c769  mov     r12d, [rbp+14h]
0x14001c76d  mov     r14d, 0F000h
0x14001c773  movzx   edi, ax
0x14001c776  mov     edx, 1000h; Flags
0x14001c77b  mov     ecx, edi
0x14001c77d  mov     [rsp+88h+arg_10], r12d
0x14001c785  and     ecx, r14d
0x14001c788  cmp     ecx, edx
0x14001c78a  jz      loc_14001CC41
0x14001c790  mov     r15d, 2000h
0x14001c796  cmp     ecx, r15d
0x14001c799  jz      loc_14001CBF6
0x14001c79f  cmp     ecx, 3000h
0x14001c7a5  jz      loc_14001CBC6
0x14001c7ab  cmp     ecx, 4000h
0x14001c7b1  jz      loc_14001C9AB
0x14001c7b7  cmp     ecx, 5000h
0x14001c7bd  jz      loc_14001C975
0x14001c7c3  cmp     ecx, 6000h
0x14001c7c9  jz      loc_14001C92B
0x14001c7cf  cmp     ecx, 7000h
0x14001c7d5  jz      loc_14001C8A1
0x14001c7db  cmp     ecx, 8000h
0x14001c7e1  jz      loc_14001C92B
0x14001c7e7  mov     r15d, 9000h
0x14001c7ed  cmp     ecx, r15d
0x14001c7f0  jz      short loc_14001C819
0x14001c7f2  mov     dword ptr [rsp+88h+var_68], edi
0x14001c7f6  lea     r9, aUnknownTagType; "Unknown tag type encountered for tag: %"...
0x14001c7fd  mov     r8d, 69Dh
0x14001c803  lea     rdx, aSdbpmergecopyi; "SdbpMergeCopyItemToSdb"
0x14001c80a  mov     ecx, 1
0x14001c80f  call    AslLogCallPrintf
0x14001c814  jmp     loc_14001CC85
0x14001c819  mov     edx, [rbx+8]
0x14001c81c  mov     rcx, [rbx]
0x14001c81f  call    SdbGetTagDataSize
0x14001c824  mov     esi, eax
0x14001c826  cmp     eax, 20000000h
0x14001c82b  jnz     short loc_14001C83F
0x14001c82d  lea     r9, aSdbgettagdatas; "SdbGetTagDataSize failed to return data"...
0x14001c834  mov     r8d, 689h
0x14001c83a  jmp     loc_14001CC74
0x14001c83f  mov     edx, [rbx+8]
0x14001c842  mov     rcx, [rbx]
0x14001c845  call    SdbGetBinaryTagData
0x14001c84a  mov     r8, rax
0x14001c84d  test    rax, rax
0x14001c850  jnz     short loc_14001C868
0x14001c852  test    esi, esi
0x14001c854  jz      short loc_14001C868
0x14001c856  lea     r9, aSdbgetbinaryta_0; "SdbGetBinaryTagData failed to return da"...
0x14001c85d  mov     r8d, 690h
0x14001c863  jmp     loc_14001CC74
0x14001c868  movzx   eax, di
0x14001c86b  and     ax, r14w
0x14001c86f  cmp     ax, r15w
0x14001c873  jnz     short loc_14001C88B
0x14001c875  mov     r9d, esi
0x14001c878  movzx   edx, di
0x14001c87b  mov     rcx, rbp
0x14001c87e  call    SdbpWriteTagData
0x14001c883  test    eax, eax
0x14001c885  jnz     loc_14001CC62
0x14001c88b  mov     dword ptr [rsp+88h+var_68], esi
0x14001c88f  lea     r9, aFailedToWriteB; "Failed to write binary data (size: %d)"
0x14001c896  mov     r8d, 695h
0x14001c89c  jmp     loc_14001C803
0x14001c8a1  movzx   edx, di
0x14001c8a4  mov     rcx, rbp
0x14001c8a7  call    SdbBeginWriteListTag
0x14001c8ac  mov     rcx, [rbx]
0x14001c8af  mov     r12d, eax
0x14001c8b2  mov     edx, [rbx+8]
0x14001c8b5  mov     qword ptr [rsp+88h+var_58], rcx
0x14001c8ba  mov     qword ptr [rsp+88h+var_58+8], 0
0x14001c8c3  call    SdbGetFirstChild
0x14001c8c8  mov     edi, eax
0x14001c8ca  test    eax, eax
0x14001c8cc  jz      short loc_14001C906
0x14001c8ce  mov     r14, [rsp+88h+arg_20]
0x14001c8d6  mov     r9, rsi
0x14001c8d9  mov     dword ptr [rsp+88h+var_58+8], edi
0x14001c8dd  xor     r8d, r8d
0x14001c8e0  mov     [rsp+88h+var_68], r14
0x14001c8e5  mov     edx, r12d
0x14001c8e8  lea     rcx, [rsp+88h+var_58]
0x14001c8ed  call    SdbpMergeCopyItemToSdb
0x14001c8f2  mov     edx, [rbx+8]
0x14001c8f5  mov     r8d, edi
0x14001c8f8  mov     rcx, [rbx]
0x14001c8fb  call    SdbGetNextChild
0x14001c900  mov     edi, eax
0x14001c902  test    eax, eax
0x14001c904  jnz     short loc_14001C8D6
0x14001c906  mov     edx, r12d
0x14001c909  mov     rcx, rbp
0x14001c90c  call    SdbEndWriteListTag
0x14001c911  test    eax, eax
0x14001c913  jnz     loc_14001CC62
0x14001c919  lea     r9, aSdbendwritelis_2; "SdbEndWriteListTag failed to write end "...
0x14001c920  mov     r8d, 60Bh
0x14001c926  jmp     loc_14001CC74
0x14001c92b  mov     edx, [rbx+8]
0x14001c92e  mov     rcx, [rbx]
0x14001c931  call    SdbGetStringTagPtr
0x14001c936  test    rax, rax
0x14001c939  jnz     short loc_14001C94D
0x14001c93b  lea     r9, aFailedToReadSt_0; "Failed to read string from original sdb"
0x14001c942  mov     r8d, 67Ah
0x14001c948  jmp     loc_14001CC74
0x14001c94d  mov     r8, rax
0x14001c950  movzx   edx, di
0x14001c953  mov     rcx, rbp
0x14001c956  call    SdbWriteStringTag
0x14001c95b  test    eax, eax
0x14001c95d  jnz     loc_14001CC62
0x14001c963  lea     r9, aFailedToWriteS_0; "Failed to write string/stringref to out"...
0x14001c96a  mov     r8d, 67Fh
0x14001c970  jmp     loc_14001CC74
0x14001c975  mov     edx, [rbx+8]
0x14001c978  xor     r8d, r8d
0x14001c97b  mov     rcx, [rbx]
0x14001c97e  call    SdbReadQWORDTag
0x14001c983  mov     r8, rax
0x14001c986  movzx   edx, di
0x14001c989  mov     rcx, rbp
0x14001c98c  call    SdbWriteQWORDTag
0x14001c991  test    eax, eax
0x14001c993  jnz     loc_14001CC62
0x14001c999  lea     r9, aFailedToCopyTa_2; "Failed to copy TAG_TYPE_QWORD to output"...
0x14001c9a0  mov     r8d, 670h
0x14001c9a6  jmp     loc_14001CC74
0x14001c9ab  mov     eax, 405Dh
0x14001c9b0  cmp     di, ax
0x14001c9b3  jz      loc_14001CA3A
0x14001c9b9  xor     eax, eax
0x14001c9bb  lea     rcx, qword_140039F50
0x14001c9c2  cmp     [rcx+rax*2], di
0x14001c9c6  jz      short loc_14001C9D6
0x14001c9c8  inc     rax
0x14001c9cb  cmp     rax, 9
0x14001c9cf  jb      short loc_14001C9BB
0x14001c9d1  jmp     loc_14001CB90
0x14001c9d6  mov     edx, [rbx+8]
0x14001c9d9  xor     r8d, r8d
0x14001c9dc  mov     rcx, [rbx]
0x14001c9df  call    SdbReadDWORDTag
0x14001c9e4  test    eax, eax
0x14001c9e6  jnz     short loc_14001C9FA
0x14001c9e8  lea     r9, aFailedToReadTa_2; "Failed to read tagid from original pdb"
0x14001c9ef  mov     r8d, 635h
0x14001c9f5  jmp     loc_14001CC74
0x14001c9fa  mov     eax, [rbx+8]
0x14001c9fd  mov     rcx, [rbx]
0x14001ca00  mov     [rsp+88h+arg_8], eax
0x14001ca07  mov     rax, [rsi]
0x14001ca0a  cmp     rcx, [rax]
0x14001ca0d  jnz     short loc_14001CA17
0x14001ca0f  mov     r15d, 10h
0x14001ca15  jmp     short loc_14001CA40
0x14001ca17  mov     rax, [rsi+8]
0x14001ca1b  cmp     rcx, [rax]
0x14001ca1e  jnz     short loc_14001CA28
0x14001ca20  mov     r15d, 11h
0x14001ca26  jmp     short loc_14001CA40
0x14001ca28  lea     r9, aAttemptToCopyF; "Attempt to copy from an unknown pdb to "...
0x14001ca2f  mov     r8d, 65Ch
0x14001ca35  jmp     loc_14001CC74
0x14001ca3a  mov     r15d, 22h ; '"'
0x14001ca40  mov     rsi, [rsp+88h+arg_20]
0x14001ca48  lea     r13, [rsi+10h]
0x14001ca4c  mov     rax, [r13+0]
0x14001ca50  mov     [rsp+88h+arg_18], rax
0x14001ca58  cmp     rax, [rsi+18h]
0x14001ca5c  jb      loc_14001CB53
0x14001ca62  lea     rcx, [rax+1]
0x14001ca66  cmp     rcx, [rsi+18h]
0x14001ca6a  ja      short loc_14001CA76
0x14001ca6c  mov     eax, 0C000000Dh
0x14001ca71  jmp     loc_14001CB3D
0x14001ca76  mov     r12, [rsi+20h]
0x14001ca7a  dec     r12
0x14001ca7d  lea     r8, [r12+rcx]
0x14001ca81  cmp     r8, rcx
0x14001ca84  jb      loc_14001CB30
0x14001ca8a  mov     rax, [rsi+8]
0x14001ca8e  mul     qword ptr [rsi+18h]
0x14001ca92  mov     [rsp+88h+Size], 0
0x14001ca9e  test    rdx, rdx
0x14001caa1  jnz     loc_14001CB30
0x14001caa7  mov     rax, [rsi+8]
0x14001caab  not     r12
0x14001caae  and     r12, r8
0x14001cab1  mov     [rsp+88h+Size], rdx
0x14001cab9  mul     r12
0x14001cabc  mov     [rsp+88h+Size], rax
0x14001cac4  test    rdx, rdx
0x14001cac7  jnz     short loc_14001CB30
0x14001cac9  mov     r8, [rsi+28h]; Ptr
0x14001cacd  mov     rcx, [rsi]; Heap
0x14001cad0  test    r8, r8
0x14001cad3  jnz     short loc_14001CAFA
0x14001cad5  mov     r8, rax; Size
0x14001cad8  call    cs:__imp_RtlAllocateHeap
0x14001cade  mov     r14, rax
0x14001cae1  test    rax, rax
0x14001cae4  jz      short loc_14001CB06
0x14001cae6  mov     r8, [rsp+88h+Size]; Size
0x14001caee  xor     edx, edx; Val
0x14001caf0  mov     rcx, rax; void *
0x14001caf3  call    memset_0
0x14001caf8  jmp     short loc_14001CB06
0x14001cafa  mov     r9, rax; Size
0x14001cafd  call    cs:__imp_RtlReAllocateHeap
0x14001cb03  mov     r14, rax
0x14001cb06  test    r14, r14
0x14001cb09  jnz     short loc_14001CB12
0x14001cb0b  mov     eax, 0C0000017h
0x14001cb10  jmp     short loc_14001CB35
0x14001cb12  mov     rax, [rsp+88h+arg_18]
0x14001cb1a  lea     r8, [rsi+10h]
0x14001cb1e  mov     [rsi+18h], r12
0x14001cb22  mov     r12d, [rsp+88h+arg_10]
0x14001cb2a  mov     [rsi+28h], r14
0x14001cb2e  jmp     short loc_14001CB56
0x14001cb30  mov     eax, 0C0000095h
0x14001cb35  mov     r12d, [rsp+88h+arg_10]
0x14001cb3d  test    eax, eax
0x14001cb3f  jz      short loc_14001CB90
0x14001cb41  lea     r9, aFailedToAppend_3; "Failed to append fix tagid refernce inf"...
0x14001cb48  mov     r8d, 662h
0x14001cb4e  jmp     loc_14001CC74
0x14001cb53  mov     r8, r13
0x14001cb56  mul     qword ptr [rsi+8]
0x14001cb5a  mov     [rsp+88h+Size], 0
0x14001cb66  test    rdx, rdx
0x14001cb69  jnz     short loc_14001CB41
0x14001cb6b  add     rax, [rsi+28h]
0x14001cb6f  cmp     rax, [rsi+28h]
0x14001cb73  jb      short loc_14001CB41
0x14001cb75  mov     ecx, [rsp+88h+arg_8]
0x14001cb7c  mov     [rax], ecx
0x14001cb7e  mov     [rax+4], r15d
0x14001cb82  mov     [rax+8], r12d
0x14001cb86  mov     rax, [r8]
0x14001cb89  inc     rax
0x14001cb8c  mov     [r13+0], rax
0x14001cb90  mov     edx, [rbx+8]
0x14001cb93  xor     r8d, r8d
0x14001cb96  mov     rcx, [rbx]
0x14001cb99  call    SdbReadDWORDTag
0x14001cb9e  mov     r8d, eax
0x14001cba1  movzx   edx, di
0x14001cba4  mov     rcx, rbp
0x14001cba7  call    SdbWriteDWORDTag
0x14001cbac  test    eax, eax
0x14001cbae  jnz     loc_14001CC62
0x14001cbb4  lea     r9, aFailedToCopyTa_1; "Failed to copy TAG_TYPE_DWORD to output"...
0x14001cbbb  mov     r8d, 668h
0x14001cbc1  jmp     loc_14001CC74
0x14001cbc6  mov     edx, [rbx+8]
0x14001cbc9  xor     r8d, r8d
0x14001cbcc  mov     rcx, [rbx]
0x14001cbcf  call    SdbReadWORDTag
0x14001cbd4  movzx   r8d, ax
0x14001cbd8  movzx   edx, di
0x14001cbdb  mov     rcx, rbp
0x14001cbde  call    SdbWriteWORDTag
0x14001cbe3  test    eax, eax
0x14001cbe5  jnz     short loc_14001CC62
0x14001cbe7  lea     r9, aFailedToCopyTa_3; "Failed to copy TAG_TYPE_WORD to output "...
0x14001cbee  mov     r8d, 623h
0x14001cbf4  jmp     short loc_14001CC74
0x14001cbf6  mov     edx, [rbx+8]
0x14001cbf9  mov     rcx, [rbx]
0x14001cbfc  call    SdbReadBYTETag
0x14001cc01  mov     byte ptr [rsp+88h+arg_10], al
0x14001cc08  movzx   eax, di
0x14001cc0b  and     ax, r14w
  ... truncated ...
```
