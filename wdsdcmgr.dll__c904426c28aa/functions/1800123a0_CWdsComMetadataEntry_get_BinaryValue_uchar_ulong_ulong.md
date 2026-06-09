# CWdsComMetadataEntry::get_BinaryValue(uchar *,ulong,ulong *)

- ea: `0x1800123a0`
- end: `0x180012471`
- name: `?get_BinaryValue@CWdsComMetadataEntry@@UEAAJPEAEKPEAK@Z`
- size: `209`
- prototype: `int(CWdsComMetadataEntry *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009c30`
- `0x1800123a0`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x1800123d3`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180012405`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x18001242e`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_BinaryValue(
        CWdsComMetadataEntry *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  size_t v5; // rbp
  unsigned int v8; // ebx
  signed int BinaryValue; // edi
  const char *v10; // rdx
  unsigned __int64 v11; // rax
  unsigned int v12; // ecx
  unsigned __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v14 = 0;
  v5 = a3;
  if ( a2 && a4
    || (v8 = -2147024809,
        (int)ElValidateHr(
               -2147024809,
               (const char *)a2,
               "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp",
               0x2D1u) >= 0) )
  {
    BinaryValue = CWdsMetadataValue::GetBinaryValue((CWdsComMetadataEntry *)((char *)this + 104), a2, v5, &v14);
    if ( ElValidateWin32(BinaryValue, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x2D5u) )
    {
      v8 = (unsigned __int16)BinaryValue | 0x80070000;
      if ( BinaryValue <= 0 )
        return (unsigned int)BinaryValue;
    }
    else
    {
      v11 = v14;
      v12 = -1;
      if ( v14 <= 0xFFFFFFFF )
        v12 = v14;
      *a4 = v12;
      v8 = v11 > 0xFFFFFFFF ? 0x80070216 : 0;
      ElValidateHr(
        v8,
        (const char *)0xFFFFFFFFLL,
        "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp",
        0x2D8u);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800123a0  mov     [rsp+arg_0], rbx
0x1800123a5  mov     [rsp+arg_10], rbp
0x1800123aa  push    rsi
0x1800123ab  push    rdi
0x1800123ac  push    r14
0x1800123ae  sub     rsp, 20h
0x1800123b2  and     [rsp+38h+arg_8], 0
0x1800123b8  mov     rsi, r9
0x1800123bb  mov     ebp, r8d
0x1800123be  mov     rdi, rdx
0x1800123c1  mov     r14, rcx
0x1800123c4  test    rdx, rdx
0x1800123c7  jz      short loc_1800123CE
0x1800123c9  test    r9, r9
0x1800123cc  jnz     short loc_1800123EB
0x1800123ce  mov     ebx, 80070057h
0x1800123d3  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800123da  mov     ecx, ebx; int
0x1800123dc  mov     r9d, 2D1h; unsigned int
0x1800123e2  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800123e7  test    eax, eax
0x1800123e9  js      short loc_18001245C
0x1800123eb  mov     r8, rbp; unsigned __int64
0x1800123ee  lea     rcx, [r14+68h]; this
0x1800123f2  lea     r9, [rsp+38h+arg_8]; unsigned __int64 *
0x1800123f7  mov     rdx, rdi; unsigned __int8 *
0x1800123fa  call    ?GetBinaryValue@CWdsMetadataValue@@QEBAKPEAE_KPEA_K@Z; CWdsMetadataValue::GetBinaryValue(uchar *,unsigned __int64,unsigned __int64 *)
0x1800123ff  mov     r9d, 2D5h; unsigned int
0x180012405  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001240c  mov     ecx, eax; unsigned int
0x18001240e  mov     edi, eax
0x180012410  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012415  test    eax, eax
0x180012417  jz      short loc_180012429
0x180012419  movzx   ebx, di
0x18001241c  or      ebx, 80070000h
0x180012422  test    edi, edi
0x180012424  cmovle  ebx, edi
0x180012427  jmp     short loc_18001245C
0x180012429  mov     rax, [rsp+38h+arg_8]
0x18001242e  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180012435  mov     edx, 0FFFFFFFFh; char *
0x18001243a  mov     r9d, 2D8h; unsigned int
0x180012440  cmp     rax, rdx
0x180012443  mov     ecx, edx
0x180012445  cmovbe  ecx, eax
0x180012448  cmp     rdx, rax
0x18001244b  mov     [rsi], ecx
0x18001244d  sbb     ebx, ebx
0x18001244f  and     ebx, 80070216h
0x180012455  mov     ecx, ebx; int
0x180012457  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001245c  mov     rbp, [rsp+38h+arg_10]
0x180012461  mov     eax, ebx
0x180012463  mov     rbx, [rsp+38h+arg_0]
0x180012468  add     rsp, 20h
0x18001246c  pop     r14
0x18001246e  pop     rdi
0x18001246f  pop     rsi
0x180012470  retn
```
