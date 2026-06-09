# CASFV1MetadataLibraryObject::AddDescriptor(ushort,ushort,ushort const *,ushort,uchar const *,ulong)

- ea: `0x1800176e0`
- end: `0x1800177d3`
- name: `?AddDescriptor@CASFV1MetadataLibraryObject@@QEAAJGGPEBGGPEBEK@Z`
- size: `243`
- prototype: `int(CASFV1MetadataLibraryObject *__hidden this, unsigned __int16, unsigned __int16, const unsigned __int16 *, unsigned __int16, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001a720`

## callees

- `0x180005060`
- `0x1800173b8`
- `0x1800176e0`
- `0x18001ad08`
- `0x180026ce4`

## pseudocode

```c
__int64 __fastcall CASFV1MetadataLibraryObject::AddDescriptor(
        CASFV1MetadataLibraryObject *this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        const unsigned __int16 *a4,
        unsigned __int16 a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  CASFV1MetadataLibraryObject *v10; // rcx
  unsigned int v11; // r9d
  unsigned __int16 v12; // r10
  const unsigned __int16 *v13; // r11
  int v14; // ebx
  _OWORD v16[2]; // [rsp+40h] [rbp-48h] BYREF
  _OWORD v17[2]; // [rsp+60h] [rbp-28h] BYREF

  if ( !a4
    || (int)StringCchLengthW(a4, 0x400u, 0) < 0
    || (int)ValidateMetadataTypeAndSize(a5, a7) < 0
    || v12 == 2 && v11 != 4 )
  {
    return 2147942487LL;
  }
  memset(v16, 0, 26);
  v14 = CASFV1MetadataLibraryObject::FillRecord(
          v10,
          (struct CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC *)v16,
          a3,
          v13,
          a2,
          v12,
          a6,
          v11);
  if ( v14 >= 0 )
  {
    v17[0] = v16[0];
    *(_OWORD *)((char *)v17 + 10) = *(_OWORD *)((char *)v16 + 10);
    CTDynArray<CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20>::Add((char *)this + 56, v17);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800176e0  mov     [rsp+arg_0], rbx
0x1800176e5  mov     [rsp+arg_8], rsi
0x1800176ea  push    rdi
0x1800176eb  sub     rsp, 80h
0x1800176f2  mov     r11, r9
0x1800176f5  movzx   ebx, r8w
0x1800176f9  movzx   esi, dx
0x1800176fc  mov     rdi, rcx
0x1800176ff  test    r9, r9
0x180017702  jz      loc_1800177B9
0x180017708  xor     r8d, r8d; unsigned __int64 *
0x18001770b  mov     edx, 400h; unsigned __int64
0x180017710  mov     rcx, r9; unsigned __int16 *
0x180017713  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180017718  test    eax, eax
0x18001771a  js      loc_1800177B9
0x180017720  movzx   r10d, [rsp+88h+arg_20]
0x180017729  mov     r9d, [rsp+88h+arg_30]
0x180017731  movzx   ecx, r10w; unsigned __int16
0x180017735  mov     edx, r9d; unsigned int
0x180017738  call    ?ValidateMetadataTypeAndSize@@YAJGK@Z; ValidateMetadataTypeAndSize(ushort,ulong)
0x18001773d  test    eax, eax
0x18001773f  js      short loc_1800177B9
0x180017741  mov     eax, 2
0x180017746  cmp     ax, r10w
0x18001774a  jnz     short loc_180017752
0x18001774c  cmp     r9d, 4
0x180017750  jnz     short loc_1800177B9
0x180017752  mov     rax, [rsp+88h+arg_28]
0x18001775a  lea     rdx, [rsp+88h+var_48]; struct CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC *
0x18001775f  mov     [rsp+88h+var_50], r9d; unsigned int
0x180017764  xorps   xmm0, xmm0
0x180017767  mov     [rsp+88h+var_58], rax; unsigned __int8 *
0x18001776c  mov     r9, r11; unsigned __int16 *
0x18001776f  mov     [rsp+88h+var_60], r10w; unsigned __int16
0x180017775  movzx   r8d, bx; unsigned __int16
0x180017779  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x18001777e  mov     [rsp+88h+var_68], si; unsigned __int16
0x180017783  movups  xmmword ptr [rsp+88h+var_48+0Ah], xmm0
0x180017788  call    ?FillRecord@CASFV1MetadataLibraryObject@@QEAAJPEAUMETADATA_LIBRARY_REC@1@GPEBGGGPEBEK@Z; CASFV1MetadataLibraryObject::FillRecord(CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC *,ushort,ushort const *,ushort,ushort,uchar const *,ulong)
0x18001778d  mov     ebx, eax
0x18001778f  test    eax, eax
0x180017791  js      short loc_1800177B5
0x180017793  movups  xmm0, xmmword ptr [rsp+88h+var_48]
0x180017798  lea     rcx, [rdi+38h]
0x18001779c  movups  xmm1, xmmword ptr [rsp+88h+var_48+0Ah]
0x1800177a1  lea     rdx, [rsp+88h+var_28]
0x1800177a6  movaps  xmmword ptr [rsp+88h+var_28], xmm0
0x1800177ab  movups  xmmword ptr [rsp+88h+var_28+0Ah], xmm1
0x1800177b0  call    ?Add@?$CTDynArray@UMETADATA_LIBRARY_REC@CASFV1MetadataLibraryObject@@$0BE@@@QEAAHUMETADATA_LIBRARY_REC@CASFV1MetadataLibraryObject@@PEAK@Z; CTDynArray<CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20>::Add(CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,ulong *)
0x1800177b5  mov     eax, ebx
0x1800177b7  jmp     short loc_1800177BE
0x1800177b9  mov     eax, 80070057h
0x1800177be  lea     r11, [rsp+88h+var_8]
0x1800177c6  mov     rbx, [r11+10h]
0x1800177ca  mov     rsi, [r11+18h]
0x1800177ce  mov     rsp, r11
0x1800177d1  pop     rdi
0x1800177d2  retn
```
