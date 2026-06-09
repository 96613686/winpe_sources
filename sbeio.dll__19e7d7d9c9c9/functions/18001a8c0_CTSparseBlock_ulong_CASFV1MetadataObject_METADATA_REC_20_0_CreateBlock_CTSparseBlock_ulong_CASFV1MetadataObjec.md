# CTSparseBlock<ulong,CASFV1MetadataObject::METADATA_REC,20,0>::CreateBlock(CTSparseBlock<ulong,CASFV1MetadataObject::METADATA_REC,20,0> * *)

- ea: `0x18001a8c0`
- end: `0x18001a926`
- name: `?CreateBlock@?$CTSparseBlock@KUMETADATA_REC@CASFV1MetadataObject@@$0BE@$0A@@@MEAAJPEAPEAV1@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011a0`
- `0x18001a8c0`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFV1MetadataObject::METADATA_REC,20,0>::CreateBlock(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  __int64 result; // rax

  v3 = operator new(0x250u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &CTSparseBlock<unsigned long,CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20,0>::`vftable';
    *((_WORD *)v3 + 21) = 0;
    *((_BYTE *)v3 + 44) = 0;
    v3[71] = 0;
    v3[72] = v3;
    *((_DWORD *)v3 + 146) = 0;
  }
  else
  {
    v4 = 0;
  }
  *a2 = v4;
  result = 0;
  if ( !v4 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x18001a8c0  push    rbx
0x18001a8c2  sub     rsp, 20h
0x18001a8c6  mov     ecx, 250h; Size
0x18001a8cb  mov     rbx, rdx
0x18001a8ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a8d3  xor     r8d, r8d
0x18001a8d6  mov     rcx, rax
0x18001a8d9  test    rax, rax
0x18001a8dc  jz      short loc_18001A90C
0x18001a8de  lea     rax, ??_7?$CTSparseBlock@KUMETADATA_LIBRARY_REC@CASFV1MetadataLibraryObject@@$0BE@$0A@@@6B@; const CTSparseBlock<ulong,CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20,0>::`vftable'
0x18001a8e5  mov     [rcx+8], r8
0x18001a8e9  mov     [rcx], rax
0x18001a8ec  xor     eax, eax
0x18001a8ee  mov     [rcx+2Ah], ax
0x18001a8f2  mov     [rcx+2Ch], al
0x18001a8f5  mov     [rcx+238h], r8
0x18001a8fc  mov     [rcx+240h], rcx
0x18001a903  mov     [rcx+248h], r8d
0x18001a90a  jmp     short loc_18001A90F
0x18001a90c  mov     rcx, r8
0x18001a90f  test    rcx, rcx
0x18001a912  mov     [rbx], rcx
0x18001a915  mov     eax, r8d
0x18001a918  mov     edx, 8007000Eh
0x18001a91d  cmovz   eax, edx
0x18001a920  add     rsp, 20h
0x18001a924  pop     rbx
0x18001a925  retn
```
