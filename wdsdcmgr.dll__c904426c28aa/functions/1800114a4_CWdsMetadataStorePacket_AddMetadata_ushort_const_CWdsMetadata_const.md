# CWdsMetadataStorePacket::AddMetadata(ushort const *,CWdsMetadata const *)

- ea: `0x1800114a4`
- end: `0x1800115de`
- name: `?AddMetadata@CWdsMetadataStorePacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(CWdsMetadataStorePacket *this, unsigned __int16 *, const struct CWdsMetadata *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d540`

## callees

- `0x18000a3f0`
- `0x18000ad94`
- `0x1800114a4`
- `0x18001284c`
- `0x180012910`
- `0x180014d58`
- `0x1800150b8`

## string_xrefs

- `0x1800114e3`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`
- `0x180011520`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`
- `0x18001154d`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`
- `0x180011586`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsMetadataStorePacket::AddMetadata(
        CWdsMetadataStorePacket *this,
        unsigned __int16 *a2,
        const struct CWdsMetadata *a3,
        __int64 a4)
{
  unsigned int v4; // ebp
  void *v6; // rbx
  unsigned int v9; // esi
  const char *v10; // rdx
  unsigned int v11; // edi
  const char *v12; // rdx
  const char *v13; // rdx
  unsigned int v14; // eax
  const char *v15; // rdx
  void *Block; // [rsp+70h] [rbp+18h] BYREF
  struct CWdsMetadataEntry *v18; // [rsp+78h] [rbp+20h] BYREF

  v4 = *((_DWORD *)a3 + 15);
  v6 = 0;
  Block = 0;
  v9 = CControlPacket::AddULONG(this, a2, L"C", a4, v4);
  if ( !ElValidateWin32(v9, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp", 0x8Fu) )
  {
    v11 = 0;
    if ( v4 )
    {
      do
      {
        v18 = 0;
        v9 = CWdsMetadata::GetByIndex(a3, v11, &v18);
        if ( ElValidateWin32(v9, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp", 0x96u) )
          break;
        v9 = CWdsMetadataEntry::ToString(v18, (unsigned __int16 **)&Block);
        v14 = ElValidateWin32(v9, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp", 0x99u);
        v6 = Block;
        if ( v14 )
          break;
        v9 = CControlPacket::AddString(this, (const char *)a2, L"E", v11, (unsigned __int16 *)Block);
        if ( ElValidateWin32(v9, v15, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp", 0x9Fu) )
          break;
        if ( v6 )
        {
          operator delete(v6);
          v6 = 0;
          Block = 0;
        }
        ++v11;
      }
      while ( v11 < v4 );
      if ( v6 )
        operator delete(v6);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800114a4  mov     rax, rsp
0x1800114a7  mov     [rax+8], rbx
0x1800114ab  mov     [rax+10h], rbp
0x1800114af  push    rsi
0x1800114b0  push    rdi
0x1800114b1  push    r12
0x1800114b3  push    r14
0x1800114b5  push    r15
0x1800114b7  sub     rsp, 30h
0x1800114bb  mov     ebp, [r8+3Ch]
0x1800114bf  mov     r14, r8
0x1800114c2  xor     ebx, ebx
0x1800114c4  mov     [rax-38h], ebp
0x1800114c7  lea     r8, aC; "C"
0x1800114ce  mov     [rax+18h], rbx
0x1800114d2  mov     r15, rdx
0x1800114d5  mov     r12, rcx
0x1800114d8  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x1800114dd  mov     r9d, 8Fh; unsigned int
0x1800114e3  lea     r8, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800114ea  mov     ecx, eax; unsigned int
0x1800114ec  mov     esi, eax
0x1800114ee  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800114f3  test    eax, eax
0x1800114f5  jnz     loc_1800115C5
0x1800114fb  xor     edi, edi
0x1800114fd  test    ebp, ebp
0x1800114ff  jz      loc_1800115C5
0x180011505  and     [rsp+58h+arg_18], 0
0x18001150b  lea     r8, [rsp+58h+arg_18]; struct CWdsMetadataEntry **
0x180011510  mov     edx, edi; unsigned int
0x180011512  mov     rcx, r14; this
0x180011515  call    ?GetByIndex@CWdsMetadata@@QEBAKKPEAPEBVCWdsMetadataEntry@@@Z; CWdsMetadata::GetByIndex(ulong,CWdsMetadataEntry const * *)
0x18001151a  mov     r9d, 96h; unsigned int
0x180011520  lea     r8, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011527  mov     ecx, eax; unsigned int
0x180011529  mov     esi, eax
0x18001152b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011530  test    eax, eax
0x180011532  jnz     loc_1800115B8
0x180011538  mov     rcx, [rsp+58h+arg_18]; this
0x18001153d  lea     rdx, [rsp+58h+Block]; unsigned __int16 **
0x180011542  call    ?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z; CWdsMetadataEntry::ToString(ushort * *)
0x180011547  mov     r9d, 99h; unsigned int
0x18001154d  lea     r8, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011554  mov     ecx, eax; unsigned int
0x180011556  mov     esi, eax
0x180011558  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001155d  mov     rbx, [rsp+58h+Block]
0x180011562  test    eax, eax
0x180011564  jnz     short loc_1800115B8
0x180011566  mov     r9d, edi; unsigned int
0x180011569  mov     [rsp+58h+var_38], rbx; unsigned __int16 *
0x18001156e  lea     r8, aE; "E"
0x180011575  mov     rdx, r15; unsigned __int16 *
0x180011578  mov     rcx, r12; this
0x18001157b  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x180011580  mov     r9d, 9Fh; unsigned int
0x180011586  lea     r8, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001158d  mov     ecx, eax; unsigned int
0x18001158f  mov     esi, eax
0x180011591  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011596  test    eax, eax
0x180011598  jnz     short loc_1800115B8
0x18001159a  test    rbx, rbx
0x18001159d  jz      short loc_1800115AE
0x18001159f  mov     rcx, rbx; Block
0x1800115a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800115a7  xor     ebx, ebx
0x1800115a9  mov     [rsp+58h+Block], rbx
0x1800115ae  inc     edi
0x1800115b0  cmp     edi, ebp
0x1800115b2  jb      loc_180011505
0x1800115b8  test    rbx, rbx
0x1800115bb  jz      short loc_1800115C5
0x1800115bd  mov     rcx, rbx; Block
0x1800115c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800115c5  mov     rbx, [rsp+58h+arg_0]
0x1800115ca  mov     eax, esi
0x1800115cc  mov     rbp, [rsp+58h+arg_8]
0x1800115d1  add     rsp, 30h
0x1800115d5  pop     r15
0x1800115d7  pop     r14
0x1800115d9  pop     r12
0x1800115db  pop     rdi
0x1800115dc  pop     rsi
0x1800115dd  retn
```
