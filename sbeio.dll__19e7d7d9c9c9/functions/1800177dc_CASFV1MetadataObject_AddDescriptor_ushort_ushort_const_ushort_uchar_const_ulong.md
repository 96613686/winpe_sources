# CASFV1MetadataObject::AddDescriptor(ushort,ushort const *,ushort,uchar const *,ulong)

- ea: `0x1800177dc`
- end: `0x180017a15`
- name: `?AddDescriptor@CASFV1MetadataObject@@QEAAJGPEBGGPEBEK@Z`
- size: `569`
- prototype: `int(CASFV1MetadataObject *__hidden this, unsigned __int16, const unsigned __int16 *, unsigned __int16, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001a7e0`

## callees

- `0x1800011ec`
- `0x180005060`
- `0x18000774c`
- `0x180013090`
- `0x180016500`
- `0x180017400`
- `0x1800177dc`
- `0x180017ff0`
- `0x18001fcf0`
- `0x180026ce4`
- `0x18002a070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800178dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800178dd`

## pseudocode

```c
__int64 __fastcall CASFV1MetadataObject::AddDescriptor(
        CASFV1MetadataObject *this,
        __int16 a2,
        unsigned __int16 *a3,
        unsigned __int16 a4,
        const unsigned __int8 *Src,
        unsigned int Size)
{
  char *v8; // r14
  unsigned __int16 v9; // bp
  unsigned __int16 i; // di
  __int64 Ptr; // rax
  unsigned int v13; // r10d
  __int16 v14; // r11
  _BYTE *v15; // rbx
  __int64 v16; // rax
  CASFV1MetadataObject *v17; // rcx
  int v18; // ebp
  int v19; // esi
  unsigned __int64 v20; // rax
  void *v21; // rax
  unsigned __int16 *v22; // rcx
  CASFV1MetadataObject *v23; // rcx
  _DWORD *v24; // rax
  __int128 v25; // xmm1
  unsigned __int64 v27; // [rsp+28h] [rbp-80h] BYREF
  _BYTE v28[26]; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v29[88]; // [rsp+50h] [rbp-58h] BYREF

  memset(v29, 0, 26);
  if ( !a3 )
    return 2147942487LL;
  if ( !*a3 )
    return 2147942487LL;
  v8 = (char *)this + 56;
  v27 = 0;
  v9 = *((_WORD *)this + 324);
  if ( (int)StringCchLengthW(a3, 0x400u, &v27) < 0 )
    return 2147942487LL;
  if ( Size )
  {
    if ( !Src )
      return 2147942487LL;
  }
  else if ( Src )
  {
    return 2147942487LL;
  }
  if ( (int)ValidateMetadataTypeAndSize(a4, Size) < 0 || a4 == 2 && (Size & 0xFFFFFFFB) != 0 )
    return 2147942487LL;
  for ( i = 0; i < v9; ++i )
  {
    Ptr = CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::GetPtr(v8, i);
    v15 = (_BYTE *)Ptr;
    if ( Ptr )
    {
      if ( *(_WORD *)(Ptr + 2) == v14 )
      {
        v16 = CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::operator[](v8, v28, v13);
        if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v16 + 6), a3) )
        {
          v18 = 1;
          CASFV1MetadataObject::CleanRecord(v17, (struct CASFV1MetadataObject::METADATA_REC *)v15);
          goto LABEL_19;
        }
      }
    }
  }
  v18 = 0;
  v15 = v29;
  i = 0;
LABEL_19:
  if ( Size )
  {
    v20 = 2 * ++v27;
    if ( !is_mul_ok(v27, 2u) )
      v20 = -1;
    *(_QWORD *)(v15 + 6) = operator new[](v20);
    v21 = operator new[](Size);
    v22 = *(unsigned __int16 **)(v15 + 6);
    *(_QWORD *)(v15 + 14) = v21;
    if ( v22 && v21 )
    {
      v19 = StringCchCopyW(v22, v27, a3);
      if ( v19 >= 0 )
      {
        memcpy_0(*(void **)(v15 + 14), Src, Size);
        *((_WORD *)v15 + 1) = a2;
        *((_WORD *)v15 + 2) = a4;
        *(_DWORD *)(v15 + 22) = Size;
        if ( a4 == 2 )
        {
          v24 = *(_DWORD **)(v15 + 14);
          if ( *v24 )
            *v24 = 1;
        }
        if ( !v18 )
        {
          v25 = *(_OWORD *)(v15 + 10);
          *(_OWORD *)v28 = *(_OWORD *)v15;
          *(_OWORD *)&v28[10] = v25;
          CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::Add(v8, v28);
        }
      }
      else
      {
        CASFV1MetadataObject::CleanRecord(v23, (struct CASFV1MetadataObject::METADATA_REC *)v15);
      }
    }
    else
    {
      CASFV1MetadataObject::CleanRecord((CASFV1MetadataObject *)v22, (struct CASFV1MetadataObject::METADATA_REC *)v15);
      if ( v18 )
        CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::RemoveAt(v8, i);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v19 = 0;
    if ( v18 )
      CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::RemoveAt(v8, i);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800177dc  mov     [rsp+arg_8], rbx
0x1800177e1  push    rbp
0x1800177e2  push    rsi
0x1800177e3  push    rdi
0x1800177e4  push    r12
0x1800177e6  push    r13
0x1800177e8  push    r14
0x1800177ea  push    r15
0x1800177ec  sub     rsp, 70h
0x1800177f0  mov     r13, [rsp+0A8h+Src]
0x1800177f8  xorps   xmm0, xmm0
0x1800177fb  mov     r15d, dword ptr [rsp+0A8h+Size]
0x180017803  xor     eax, eax
0x180017805  mov     [rsp+0A8h+var_88], dx
0x18001780a  movzx   r12d, r9w
0x18001780e  mov     rsi, r8
0x180017811  movzx   r11d, dx
0x180017815  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x18001781a  movups  xmmword ptr [rsp+0A8h+var_58+0Ah], xmm0
0x18001781f  test    r8, r8
0x180017822  jz      short loc_18001785B
0x180017824  cmp     ax, [r8]
0x180017828  jz      short loc_18001785B
0x18001782a  lea     r14, [rcx+38h]
0x18001782e  mov     [rsp+0A8h+var_80], rax
0x180017833  movzx   ebp, word ptr [r14+250h]
0x18001783b  lea     r8, [rsp+0A8h+var_80]; unsigned __int64 *
0x180017840  mov     rcx, rsi; unsigned __int16 *
0x180017843  mov     edx, 400h; unsigned __int64
0x180017848  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001784d  test    eax, eax
0x18001784f  js      short loc_18001785B
0x180017851  test    r15d, r15d
0x180017854  jnz     short loc_180017878
0x180017856  test    r13, r13
0x180017859  jz      short loc_18001787D
0x18001785b  mov     eax, 80070057h
0x180017860  mov     rbx, [rsp+0A8h+arg_8]
0x180017868  add     rsp, 70h
0x18001786c  pop     r15
0x18001786e  pop     r14
0x180017870  pop     r13
0x180017872  pop     r12
0x180017874  pop     rdi
0x180017875  pop     rsi
0x180017876  pop     rbp
0x180017877  retn
0x180017878  test    r13, r13
0x18001787b  jz      short loc_18001785B
0x18001787d  mov     edx, r15d; unsigned int
0x180017880  movzx   ecx, r12w; unsigned __int16
0x180017884  call    ?ValidateMetadataTypeAndSize@@YAJGK@Z; ValidateMetadataTypeAndSize(ushort,ulong)
0x180017889  test    eax, eax
0x18001788b  js      short loc_18001785B
0x18001788d  mov     edx, 2
0x180017892  cmp     dx, r12w
0x180017896  jnz     short loc_1800178A1
0x180017898  test    r15d, 0FFFFFFFBh
0x18001789f  jnz     short loc_18001785B
0x1800178a1  xor     edi, edi
0x1800178a3  cmp     di, bp
0x1800178a6  jnb     short loc_180017901
0x1800178a8  movzx   r10d, di
0x1800178ac  mov     rcx, r14
0x1800178af  mov     edx, r10d
0x1800178b2  call    ?GetPtr@?$CTDynArray@UMETADATA_REC@CASFV1MetadataObject@@$0BE@@@QEAAPEAUMETADATA_REC@CASFV1MetadataObject@@K@Z; CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::GetPtr(ulong)
0x1800178b7  mov     rbx, rax
0x1800178ba  test    rax, rax
0x1800178bd  jz      short loc_1800178ED
0x1800178bf  cmp     [rax+2], r11w
0x1800178c4  jnz     short loc_1800178ED
0x1800178c6  mov     r8d, r10d
0x1800178c9  lea     rdx, [rsp+0A8h+var_78]
0x1800178ce  mov     rcx, r14
0x1800178d1  call    ??A?$CTDynArray@UMETADATA_REC@CASFV1MetadataObject@@$0BE@@@QEBA?AUMETADATA_REC@CASFV1MetadataObject@@K@Z; CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::operator[](ulong)
0x1800178d6  mov     rdx, rsi
0x1800178d9  mov     rcx, [rax+6]
0x1800178dd  call    cs:__imp__o__wcsicmp
0x1800178e3  test    eax, eax
0x1800178e5  jz      short loc_1800178F2
0x1800178e7  movzx   r11d, [rsp+0A8h+var_88]
0x1800178ed  inc     di
0x1800178f0  jmp     short loc_1800178A3
0x1800178f2  mov     rdx, rbx; struct CASFV1MetadataObject::METADATA_REC *
0x1800178f5  mov     ebp, 1
0x1800178fa  call    ?CleanRecord@CASFV1MetadataObject@@QEAAXPEAUMETADATA_REC@1@@Z; CASFV1MetadataObject::CleanRecord(CASFV1MetadataObject::METADATA_REC *)
0x1800178ff  jmp     short loc_18001790D
0x180017901  xor     ebp, ebp
0x180017903  lea     rbx, [rsp+0A8h+var_58]
0x180017908  xor     eax, eax
0x18001790a  movzx   edi, ax
0x18001790d  test    r15d, r15d
0x180017910  jnz     short loc_18001792C
0x180017912  xor     esi, esi
0x180017914  test    ebp, ebp
0x180017916  jz      loc_180017A0E
0x18001791c  movzx   edx, di
0x18001791f  mov     rcx, r14
0x180017922  call    ?RemoveAt@?$CTDynArray@UMETADATA_REC@CASFV1MetadataObject@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::RemoveAt(ulong,ulong)
0x180017927  jmp     loc_180017A0E
0x18001792c  mov     rcx, [rsp+0A8h+var_80]
0x180017931  mov     eax, 2
0x180017936  inc     rcx
0x180017939  mul     rcx
0x18001793c  mov     [rsp+0A8h+var_80], rcx
0x180017941  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017948  cmovb   rax, rcx
0x18001794c  mov     rcx, rax; unsigned __int64
0x18001794f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017954  mov     rcx, r15; unsigned __int64
0x180017957  mov     [rbx+6], rax
0x18001795b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017960  mov     rcx, [rbx+6]; this
0x180017964  mov     [rbx+0Eh], rax
0x180017968  test    rcx, rcx
0x18001796b  jz      loc_1800179F2
0x180017971  test    rax, rax
0x180017974  jz      short loc_1800179F2
0x180017976  mov     rdx, [rsp+0A8h+var_80]; unsigned __int64
0x18001797b  mov     r8, rsi; unsigned __int16 *
0x18001797e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017983  mov     esi, eax
0x180017985  test    eax, eax
0x180017987  jns     short loc_180017993
0x180017989  mov     rdx, rbx; struct CASFV1MetadataObject::METADATA_REC *
0x18001798c  call    ?CleanRecord@CASFV1MetadataObject@@QEAAXPEAUMETADATA_REC@1@@Z; CASFV1MetadataObject::CleanRecord(CASFV1MetadataObject::METADATA_REC *)
0x180017991  jmp     short loc_180017A0E
0x180017993  mov     rcx, [rbx+0Eh]; void *
0x180017997  mov     r8, r15; Size
0x18001799a  mov     rdx, r13; Src
0x18001799d  call    memcpy_0
0x1800179a2  movzx   eax, [rsp+0A8h+var_88]
0x1800179a7  mov     [rbx+2], ax
0x1800179ab  mov     eax, 2
0x1800179b0  mov     [rbx+4], r12w
0x1800179b5  mov     [rbx+16h], r15d
0x1800179b9  cmp     ax, r12w
0x1800179bd  jnz     short loc_1800179CE
0x1800179bf  mov     rax, [rbx+0Eh]
0x1800179c3  cmp     dword ptr [rax], 0
0x1800179c6  jz      short loc_1800179CE
0x1800179c8  mov     dword ptr [rax], 1
0x1800179ce  test    ebp, ebp
0x1800179d0  jnz     short loc_180017A0E
0x1800179d2  movups  xmm0, xmmword ptr [rbx]
0x1800179d5  lea     rdx, [rsp+0A8h+var_78]
0x1800179da  mov     rcx, r14
0x1800179dd  movups  xmm1, xmmword ptr [rbx+0Ah]
0x1800179e1  movaps  [rsp+0A8h+var_78], xmm0
0x1800179e6  movups  [rsp+0A8h+var_78+0Ah], xmm1
0x1800179eb  call    ?Add@?$CTDynArray@UMETADATA_REC@CASFV1MetadataObject@@$0BE@@@QEAAHUMETADATA_REC@CASFV1MetadataObject@@PEAK@Z; CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::Add(CASFV1MetadataObject::METADATA_REC,ulong *)
0x1800179f0  jmp     short loc_180017A0E
0x1800179f2  mov     rdx, rbx; struct CASFV1MetadataObject::METADATA_REC *
0x1800179f5  call    ?CleanRecord@CASFV1MetadataObject@@QEAAXPEAUMETADATA_REC@1@@Z; CASFV1MetadataObject::CleanRecord(CASFV1MetadataObject::METADATA_REC *)
0x1800179fa  test    ebp, ebp
0x1800179fc  jz      short loc_180017A09
0x1800179fe  movzx   edx, di
0x180017a01  mov     rcx, r14
0x180017a04  call    ?RemoveAt@?$CTDynArray@UMETADATA_REC@CASFV1MetadataObject@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::RemoveAt(ulong,ulong)
0x180017a09  mov     esi, 8007000Eh
0x180017a0e  mov     eax, esi
0x180017a10  jmp     loc_180017860
```
