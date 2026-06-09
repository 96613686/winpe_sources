# CWdsComMetadataBuilder::QueryRequiredBool(ushort *,short *)

- ea: `0x1800108e0`
- end: `0x1800109f7`
- name: `?QueryRequiredBool@CWdsComMetadataBuilder@@UEAAJPEAGPEAF@Z`
- size: `279`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000b1a8`
- `0x18000e3e4`
- `0x1800108e0`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x18001092a`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010963`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x1800109b5`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryRequiredBool(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        __int16 *a3)
{
  unsigned int v4; // ebx
  int v7; // esi
  const char *v8; // rdx
  signed int v9; // edi
  const char *v10; // rdx
  const char *v11; // rdx
  int v13; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+28h] [rbp-20h]
  __int64 v15; // [rsp+30h] [rbp-18h]

  v4 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v7 = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3
    || (v4 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x7C3u) >= 0) )
  {
    v9 = CWdsMetadata::QueryRequired((char *)this + 64, a2, 2, &v13);
    if ( ElValidateWin32(v9, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x7C7u)
      || ((v9 = 0, v13 != 2)
        ? (v9 = ElValidateWin32(0xDu, v11, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x633u))
        : (v7 = v14),
          ElValidateWin32(v9, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x7CAu)) )
    {
      v4 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v4 = v9;
    }
    else
    {
      *a3 = -(v7 != 0);
    }
  }
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v13);
  return v4;
}

```

## disassembly

```asm
0x1800108e0  mov     r11, rsp
0x1800108e3  mov     [r11+8], rbx
0x1800108e7  mov     [r11+10h], rbp
0x1800108eb  mov     [r11+18h], rsi
0x1800108ef  mov     [r11+20h], rdi
0x1800108f3  push    r14
0x1800108f5  sub     rsp, 40h
0x1800108f9  xor     eax, eax
0x1800108fb  mov     rbp, rcx
0x1800108fe  xor     ebx, ebx
0x180010900  mov     rcx, rdx; pbstr
0x180010903  and     [rsp+48h+var_28], ebx
0x180010907  mov     r14, r8
0x18001090a  mov     [r11-20h], rax
0x18001090e  mov     rdi, rdx
0x180010911  mov     [r11-18h], rax
0x180010915  xor     esi, esi
0x180010917  call    ValidateNonEmptyBstr
0x18001091c  test    eax, eax
0x18001091e  jz      short loc_180010925
0x180010920  test    r14, r14
0x180010923  jnz     short loc_180010946
0x180010925  mov     ebx, 80070057h
0x18001092a  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010931  mov     ecx, ebx; int
0x180010933  mov     r9d, 7C3h; unsigned int
0x180010939  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001093e  test    eax, eax
0x180010940  js      loc_1800109D0
0x180010946  lea     rcx, [rbp+40h]
0x18001094a  mov     r8d, 2
0x180010950  lea     r9, [rsp+48h+var_28]
0x180010955  mov     rdx, rdi
0x180010958  call    ?QueryRequired@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@@Z; CWdsMetadata::QueryRequired(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *)
0x18001095d  mov     r9d, 7C7h; unsigned int
0x180010963  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001096a  mov     ecx, eax; unsigned int
0x18001096c  mov     edi, eax
0x18001096e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010973  test    eax, eax
0x180010975  jz      short loc_180010987
0x180010977  movzx   ebx, di
0x18001097a  or      ebx, 80070000h
0x180010980  test    edi, edi
0x180010982  cmovle  ebx, edi
0x180010985  jmp     short loc_1800109D0
0x180010987  xor     edi, edi
0x180010989  cmp     [rsp+48h+var_28], 2
0x18001098e  jnz     short loc_180010996
0x180010990  mov     esi, dword ptr [rsp+48h+var_20]
0x180010994  jmp     short loc_1800109AF
0x180010996  mov     r9d, 633h; unsigned int
0x18001099c  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x1800109a3  mov     ecx, 0Dh; unsigned int
0x1800109a8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800109ad  mov     edi, eax
0x1800109af  mov     r9d, 7CAh; unsigned int
0x1800109b5  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800109bc  mov     ecx, edi; unsigned int
0x1800109be  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800109c3  test    eax, eax
0x1800109c5  jnz     short loc_180010977
0x1800109c7  neg     esi
0x1800109c9  sbb     cx, cx
0x1800109cc  mov     [r14], cx
0x1800109d0  lea     rcx, [rsp+48h+var_28]; this
0x1800109d5  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x1800109da  mov     rbp, [rsp+48h+arg_8]
0x1800109df  mov     eax, ebx
0x1800109e1  mov     rbx, [rsp+48h+arg_0]
0x1800109e6  mov     rsi, [rsp+48h+arg_10]
0x1800109eb  mov     rdi, [rsp+48h+arg_18]
0x1800109f0  add     rsp, 40h
0x1800109f4  pop     r14
0x1800109f6  retn
```
