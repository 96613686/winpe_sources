# CWdsMetadataStorePacket::GetMetadata(ushort const *,CWdsMetadata *)

- ea: `0x1800115e4`
- end: `0x180011704`
- name: `?GetMetadata@CWdsMetadataStorePacket@@QEAAKPEBGPEAVCWdsMetadata@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(CWdsMetadataStorePacket *this, const unsigned __int16 *, struct CWdsMetadata *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d954`

## callees

- `0x18000ba74`
- `0x1800115e4`
- `0x1800129e4`
- `0x180012ac8`
- `0x180014d58`
- `0x1800150b8`

## string_xrefs

- `0x180011638`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`
- `0x180011683`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`
- `0x1800116ad`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsMetadataStorePacket::GetMetadata(
        CWdsMetadataStorePacket *this,
        const unsigned __int16 *a2,
        struct CWdsMetadata *a3,
        unsigned int a4)
{
  unsigned int ULONG; // eax
  const char *v7; // rdx
  unsigned int String; // edi
  unsigned int v9; // esi
  const char *v10; // rdx
  unsigned int v11; // eax
  void *v12; // rbx
  const char *v13; // rdx
  unsigned int v15; // [rsp+58h] [rbp+10h] BYREF
  int v16; // [rsp+5Ch] [rbp+14h]
  void *Block; // [rsp+68h] [rbp+20h] BYREF

  v16 = HIDWORD(a2);
  Block = 0;
  v15 = 0;
  ULONG = CControlPacket::GetULONG(this, L"M", L"C", a4, &v15);
  String = ULONG;
  if ( ULONG != 2
    && !ElValidateWin32(ULONG, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp", 0x198u) )
  {
    v9 = 0;
    if ( v15 )
    {
      do
      {
        String = CControlPacket::GetString(this, L"M", L"E", v9, (unsigned __int16 **)&Block);
        v11 = ElValidateWin32(String, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp", 0x1A0u);
        v12 = Block;
        if ( v11 )
          break;
        String = CWdsMetadata::AppendEntry(a3, (const unsigned __int16 *)Block);
        if ( ElValidateWin32(String, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp", 0x1A3u) )
          break;
        if ( v12 )
        {
          operator delete(v12);
          v12 = 0;
          Block = 0;
        }
        ++v9;
      }
      while ( v9 < v15 );
      if ( v12 )
        operator delete(v12);
    }
  }
  return String;
}

```

## disassembly

```asm
0x1800115e4  mov     rax, rsp
0x1800115e7  mov     [rax+8], rbx
0x1800115eb  mov     [rax+18h], rsi
0x1800115ef  mov     [rax+10h], rdx
0x1800115f3  push    rdi
0x1800115f4  push    r14
0x1800115f6  push    r15
0x1800115f8  sub     rsp, 30h
0x1800115fc  and     qword ptr [rax+20h], 0
0x180011601  mov     r15, r8
0x180011604  and     dword ptr [rax+10h], 0
0x180011608  lea     rax, [rax+10h]
0x18001160c  lea     r8, aC; "C"
0x180011613  mov     [rsp+48h+var_28], rax; unsigned int *
0x180011618  lea     rdx, aM; "M"
0x18001161f  mov     r14, rcx
0x180011622  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x180011627  mov     edi, eax
0x180011629  cmp     eax, 2
0x18001162c  jz      loc_1800116EE
0x180011632  mov     r9d, 198h; unsigned int
0x180011638  lea     r8, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001163f  mov     ecx, eax; unsigned int
0x180011641  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011646  test    eax, eax
0x180011648  jnz     loc_1800116EE
0x18001164e  xor     esi, esi
0x180011650  cmp     [rsp+48h+arg_8], esi
0x180011654  jbe     loc_1800116EE
0x18001165a  lea     rax, [rsp+48h+Block]
0x18001165f  mov     r9d, esi; unsigned int
0x180011662  lea     r8, aE; "E"
0x180011669  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x18001166e  lea     rdx, aM; "M"
0x180011675  mov     rcx, r14; this
0x180011678  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18001167d  mov     r9d, 1A0h; unsigned int
0x180011683  lea     r8, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001168a  mov     ecx, eax; unsigned int
0x18001168c  mov     edi, eax
0x18001168e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011693  mov     rbx, [rsp+48h+Block]
0x180011698  test    eax, eax
0x18001169a  jnz     short loc_1800116E1
0x18001169c  mov     rdx, rbx; unsigned __int16 *
0x18001169f  mov     rcx, r15; this
0x1800116a2  call    ?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendEntry(ushort const *)
0x1800116a7  mov     r9d, 1A3h; unsigned int
0x1800116ad  lea     r8, aBaseEcoWdsLibM_4; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800116b4  mov     ecx, eax; unsigned int
0x1800116b6  mov     edi, eax
0x1800116b8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800116bd  test    eax, eax
0x1800116bf  jnz     short loc_1800116E1
0x1800116c1  test    rbx, rbx
0x1800116c4  jz      short loc_1800116D5
0x1800116c6  mov     rcx, rbx; Block
0x1800116c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800116ce  xor     ebx, ebx
0x1800116d0  mov     [rsp+48h+Block], rbx
0x1800116d5  inc     esi
0x1800116d7  cmp     esi, [rsp+48h+arg_8]
0x1800116db  jb      loc_18001165A
0x1800116e1  test    rbx, rbx
0x1800116e4  jz      short loc_1800116EE
0x1800116e6  mov     rcx, rbx; Block
0x1800116e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800116ee  mov     rbx, [rsp+48h+arg_0]
0x1800116f3  mov     eax, edi
0x1800116f5  mov     rsi, [rsp+48h+arg_10]
0x1800116fa  add     rsp, 30h
0x1800116fe  pop     r15
0x180011700  pop     r14
0x180011702  pop     rdi
0x180011703  retn
```
