# CASFV1MetadataObject::CleanRecord(CASFV1MetadataObject::METADATA_REC *)

- ea: `0x180017ff0`
- end: `0x180018039`
- name: `?CleanRecord@CASFV1MetadataObject@@QEAAXPEAUMETADATA_REC@1@@Z`
- size: `73`
- prototype: `void(CASFV1MetadataObject *__hidden this, struct CASFV1MetadataObject::METADATA_REC *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800177dc`
- `0x18001ad08`
- `0x18001fc10`
- `0x18001fc80`
- `0x180023e50`
- `0x180024120`

## callees

- `0x180001194`
- `0x180017ff0`
- `0x18001ce9c`

## pseudocode

```c
void __fastcall CASFV1MetadataObject::CleanRecord(
        CASFV1MetadataObject *this,
        struct CASFV1MetadataObject::METADATA_REC *a2)
{
  void *v2; // rcx
  void *v4; // rcx

  v2 = *(void **)((char *)a2 + 6);
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)((char *)a2 + 6) = 0;
  }
  v4 = *(void **)((char *)a2 + 14);
  if ( v4 )
  {
    operator delete(v4);
    *(_QWORD *)((char *)a2 + 14) = 0;
  }
  *(_DWORD *)((char *)a2 + 22) = 0;
  CASFV1MetadataObject::InitRecord((CASFV1MetadataObject *)v4, a2);
}

```

## disassembly

```asm
0x180017ff0  push    rbx
0x180017ff2  sub     rsp, 20h
0x180017ff6  mov     rcx, [rdx+6]; void *
0x180017ffa  mov     rbx, rdx
0x180017ffd  test    rcx, rcx
0x180018000  jz      short loc_18001800F
0x180018002  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018007  mov     qword ptr [rbx+6], 0
0x18001800f  mov     rcx, [rbx+0Eh]; void *
0x180018013  test    rcx, rcx
0x180018016  jz      short loc_180018025
0x180018018  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001801d  mov     qword ptr [rbx+0Eh], 0
0x180018025  mov     rdx, rbx; struct CASFV1MetadataObject::METADATA_REC *
0x180018028  mov     dword ptr [rbx+16h], 0
0x18001802f  add     rsp, 20h
0x180018033  pop     rbx
0x180018034  jmp     ?InitRecord@CASFV1MetadataObject@@QEAAXPEAUMETADATA_REC@1@@Z; CASFV1MetadataObject::InitRecord(CASFV1MetadataObject::METADATA_REC *)
```
