# CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::GetPtr(ulong)

- ea: `0x180013090`
- end: `0x1800130e0`
- name: `?GetPtr@?$CTDynArray@UMETADATA_REC@CASFV1MetadataObject@@$0BE@@@QEAAPEAUMETADATA_REC@CASFV1MetadataObject@@K@Z`
- size: `80`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180014054`
- `0x1800177dc`
- `0x18001a7e0`
- `0x18001f620`
- `0x18001fc80`
- `0x180026510`

## callees

- `0x180013090`

## pseudocode

```c
__int64 __fastcall CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::GetPtr(__int64 a1, unsigned int a2)
{
  unsigned int v3; // ecx
  unsigned int v4; // edx

  while ( a1 )
  {
    v3 = *(_DWORD *)(a1 + 8);
    if ( a2 >= v3 && a2 < v3 + 20 )
    {
      v4 = a2 - v3;
      if ( (*(_BYTE *)(((unsigned __int64)v4 >> 3) + a1 + 42)
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFV1MetadataObject::METADATA_REC,20,0>::s_bSingleBitMasks[v4 & 7]) != 0 )
        return a1 + 26LL * v4 + 45;
      return 0;
    }
    a1 = *(_QWORD *)(a1 + 568);
  }
  return 0;
}

```

## disassembly

```asm
0x180013090  mov     r8, rcx
0x180013093  test    r8, r8
0x180013096  jz      short loc_1800130DD
0x180013098  mov     ecx, [r8+8]
0x18001309c  cmp     edx, ecx
0x18001309e  jb      short loc_1800130A7
0x1800130a0  lea     eax, [rcx+14h]
0x1800130a3  cmp     edx, eax
0x1800130a5  jb      short loc_1800130B0
0x1800130a7  mov     r8, [r8+238h]
0x1800130ae  jmp     short loc_180013093
0x1800130b0  sub     edx, ecx
0x1800130b2  mov     ecx, edx
0x1800130b4  mov     eax, edx
0x1800130b6  and     ecx, 7
0x1800130b9  shr     rax, 3
0x1800130bd  mov     r9d, edx
0x1800130c0  lea     rdx, ?s_bSingleBitMasks@?$CTSparseBlock@KUMETADATA_REC@CASFV1MetadataObject@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFV1MetadataObject::METADATA_REC,20,0>::s_bSingleBitMasks
0x1800130c7  mov     al, [rax+r8+2Ah]
0x1800130cc  test    [rcx+rdx], al
0x1800130cf  jz      short loc_1800130DD
0x1800130d1  imul    rax, r9, 1Ah
0x1800130d5  add     rax, 2Dh ; '-'
0x1800130d9  add     rax, r8
0x1800130dc  retn
0x1800130dd  xor     eax, eax
0x1800130df  retn
```
