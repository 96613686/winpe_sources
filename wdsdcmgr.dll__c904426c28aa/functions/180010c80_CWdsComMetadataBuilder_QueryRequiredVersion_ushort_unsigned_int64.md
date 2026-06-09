# CWdsComMetadataBuilder::QueryRequiredVersion(ushort *,unsigned __int64 *)

- ea: `0x180010c80`
- end: `0x180010d92`
- name: `?QueryRequiredVersion@CWdsComMetadataBuilder@@UEAAJPEAGPEA_K@Z`
- size: `274`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000b1a8`
- `0x18000e3e4`
- `0x180010c80`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x180010cca`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010d03`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010d56`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryRequiredVersion(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int64 *a3)
{
  unsigned __int64 v4; // rbx
  unsigned int v7; // edi
  const char *v8; // rdx
  signed int v9; // esi
  const char *v10; // rdx
  const char *v11; // rdx
  int v13; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-20h]
  __int64 v15; // [rsp+30h] [rbp-18h]

  v4 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v7 = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x85Du) >= 0) )
  {
    v9 = CWdsMetadata::QueryRequired((char *)this + 64, a2, 5, &v13);
    if ( ElValidateWin32(v9, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x861u)
      || ((v9 = 0, v13 != 5)
        ? (v9 = ElValidateWin32(0xDu, v11, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x67Bu))
        : (v4 = v14),
          ElValidateWin32(v9, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x864u)) )
    {
      v7 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v7 = v9;
    }
    else
    {
      *a3 = v4;
    }
  }
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v13);
  return v7;
}

```

## disassembly

```asm
0x180010c80  mov     r11, rsp
0x180010c83  mov     [r11+8], rbx
0x180010c87  mov     [r11+10h], rbp
0x180010c8b  mov     [r11+18h], rsi
0x180010c8f  mov     [r11+20h], rdi
0x180010c93  push    r14
0x180010c95  sub     rsp, 40h
0x180010c99  xor     eax, eax
0x180010c9b  mov     rbp, rcx
0x180010c9e  xor     ebx, ebx
0x180010ca0  mov     rcx, rdx; pbstr
0x180010ca3  and     [rsp+48h+var_28], ebx
0x180010ca7  mov     r14, r8
0x180010caa  mov     [r11-20h], rax
0x180010cae  mov     rsi, rdx
0x180010cb1  mov     [r11-18h], rax
0x180010cb5  xor     edi, edi
0x180010cb7  call    ValidateNonEmptyBstr
0x180010cbc  test    eax, eax
0x180010cbe  jz      short loc_180010CC5
0x180010cc0  test    r14, r14
0x180010cc3  jnz     short loc_180010CE6
0x180010cc5  mov     edi, 80070057h
0x180010cca  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010cd1  mov     ecx, edi; int
0x180010cd3  mov     r9d, 85Dh; unsigned int
0x180010cd9  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010cde  test    eax, eax
0x180010ce0  js      loc_180010D6B
0x180010ce6  lea     rcx, [rbp+40h]
0x180010cea  mov     r8d, 5
0x180010cf0  lea     r9, [rsp+48h+var_28]
0x180010cf5  mov     rdx, rsi
0x180010cf8  call    ?QueryRequired@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@@Z; CWdsMetadata::QueryRequired(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *)
0x180010cfd  mov     r9d, 861h; unsigned int
0x180010d03  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010d0a  mov     ecx, eax; unsigned int
0x180010d0c  mov     esi, eax
0x180010d0e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010d13  test    eax, eax
0x180010d15  jz      short loc_180010D27
0x180010d17  movzx   edi, si
0x180010d1a  or      edi, 80070000h
0x180010d20  test    esi, esi
0x180010d22  cmovle  edi, esi
0x180010d25  jmp     short loc_180010D6B
0x180010d27  xor     esi, esi
0x180010d29  cmp     [rsp+48h+var_28], 5
0x180010d2e  jnz     short loc_180010D37
0x180010d30  mov     rbx, [rsp+48h+var_20]
0x180010d35  jmp     short loc_180010D50
0x180010d37  mov     r9d, 67Bh; unsigned int
0x180010d3d  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180010d44  mov     ecx, 0Dh; unsigned int
0x180010d49  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010d4e  mov     esi, eax
0x180010d50  mov     r9d, 864h; unsigned int
0x180010d56  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010d5d  mov     ecx, esi; unsigned int
0x180010d5f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010d64  test    eax, eax
0x180010d66  jnz     short loc_180010D17
0x180010d68  mov     [r14], rbx
0x180010d6b  lea     rcx, [rsp+48h+var_28]; this
0x180010d70  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180010d75  mov     rbx, [rsp+48h+arg_0]
0x180010d7a  mov     eax, edi
0x180010d7c  mov     rdi, [rsp+48h+arg_18]
0x180010d81  mov     rbp, [rsp+48h+arg_8]
0x180010d86  mov     rsi, [rsp+48h+arg_10]
0x180010d8b  add     rsp, 40h
0x180010d8f  pop     r14
0x180010d91  retn
```
