# CWdsComMetadataBuilder::QueryRequiredString(ushort *,ushort * *)

- ea: `0x180010790`
- end: `0x1800108cf`
- name: `?QueryRequiredString@CWdsComMetadataBuilder@@UEAAJPEAGPEAPEAG@Z`
- size: `319`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000b1a8`
- `0x18000e3e4`
- `0x180010790`
- `0x18001381c`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800108aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108aa`

## string_xrefs

- `0x1800107d6`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18001080f`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010862`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010887`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryRequiredString(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rbp
  const char *v7; // rdx
  unsigned int v8; // ebx
  signed int v9; // edi
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  int v13; // eax
  unsigned __int16 *v14; // rcx
  int v16; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v17; // [rsp+28h] [rbp-30h]
  __int64 v18; // [rsp+30h] [rbp-28h]
  unsigned __int16 *v19; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v16 = 0;
  v19 = 0;
  v17 = 0;
  v18 = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3
    || (v8 = -2147024809,
        (int)ElValidateHr(-2147024809, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x78Bu) >= 0) )
  {
    v9 = CWdsMetadata::QueryRequired((char *)this + 64, a2, 1, &v16);
    if ( ElValidateWin32(v9, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x78Fu)
      || ((v9 = 0, v16 != 1)
        ? (unsigned __int16 *)(v9 = ElValidateWin32(
                                      0xDu,
                                      v11,
                                      "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
                                      0x60Fu))
        : (v3 = v17),
          ElValidateWin32(v9, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x792u)) )
    {
      v8 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v8 = v9;
    }
    else
    {
      v8 = SysAllocStringHr(v3, &v19);
      v13 = ElValidateHr(v8, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x795u);
      v14 = v19;
      if ( v13 >= 0 )
      {
        *a3 = v19;
        v14 = 0;
      }
      if ( v14 )
        SysFreeString(v14);
    }
  }
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v16);
  return v8;
}

```

## disassembly

```asm
0x180010790  mov     r11, rsp
0x180010793  mov     [r11+8], rbx
0x180010797  mov     [r11+10h], rbp
0x18001079b  push    rsi
0x18001079c  push    rdi
0x18001079d  push    r14
0x18001079f  sub     rsp, 40h
0x1800107a3  xor     eax, eax
0x1800107a5  xor     ebp, ebp
0x1800107a7  and     [rsp+58h+var_38], ebp
0x1800107ab  mov     r14, rcx
0x1800107ae  and     [r11+20h], rbp
0x1800107b2  mov     rcx, rdx; pbstr
0x1800107b5  mov     [r11-30h], rax
0x1800107b9  mov     rsi, r8
0x1800107bc  mov     [r11-28h], rax
0x1800107c0  mov     rdi, rdx
0x1800107c3  call    ValidateNonEmptyBstr
0x1800107c8  test    eax, eax
0x1800107ca  jz      short loc_1800107D1
0x1800107cc  test    rsi, rsi
0x1800107cf  jnz     short loc_1800107F2
0x1800107d1  mov     ebx, 80070057h
0x1800107d6  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800107dd  mov     ecx, ebx; int
0x1800107df  mov     r9d, 78Bh; unsigned int
0x1800107e5  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800107ea  test    eax, eax
0x1800107ec  js      loc_1800108B0
0x1800107f2  lea     rcx, [r14+40h]
0x1800107f6  mov     r8d, 1
0x1800107fc  lea     r9, [rsp+58h+var_38]
0x180010801  mov     rdx, rdi
0x180010804  call    ?QueryRequired@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@@Z; CWdsMetadata::QueryRequired(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *)
0x180010809  mov     r9d, 78Fh; unsigned int
0x18001080f  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010816  mov     ecx, eax; unsigned int
0x180010818  mov     edi, eax
0x18001081a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001081f  test    eax, eax
0x180010821  jz      short loc_180010833
0x180010823  movzx   ebx, di
0x180010826  or      ebx, 80070000h
0x18001082c  test    edi, edi
0x18001082e  cmovle  ebx, edi
0x180010831  jmp     short loc_1800108B0
0x180010833  xor     edi, edi
0x180010835  cmp     [rsp+58h+var_38], 1
0x18001083a  jnz     short loc_180010843
0x18001083c  mov     rbp, [rsp+58h+var_30]
0x180010841  jmp     short loc_18001085C
0x180010843  mov     r9d, 60Fh; unsigned int
0x180010849  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180010850  mov     ecx, 0Dh; unsigned int
0x180010855  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001085a  mov     edi, eax
0x18001085c  mov     r9d, 792h; unsigned int
0x180010862  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010869  mov     ecx, edi; unsigned int
0x18001086b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010870  test    eax, eax
0x180010872  jnz     short loc_180010823
0x180010874  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 **
0x180010879  mov     rcx, rbp; unsigned __int16 *
0x18001087c  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180010881  mov     r9d, 795h; unsigned int
0x180010887  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001088e  mov     ecx, eax; int
0x180010890  mov     ebx, eax
0x180010892  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010897  mov     rcx, [rsp+58h+arg_18]
0x18001089c  test    eax, eax
0x18001089e  js      short loc_1800108A5
0x1800108a0  mov     [rsi], rcx
0x1800108a3  xor     ecx, ecx; bstrString
0x1800108a5  test    rcx, rcx
0x1800108a8  jz      short loc_1800108B0
0x1800108aa  call    cs:__imp_SysFreeString
0x1800108b0  lea     rcx, [rsp+58h+var_38]; this
0x1800108b5  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x1800108ba  mov     rbp, [rsp+58h+arg_8]
0x1800108bf  mov     eax, ebx
0x1800108c1  mov     rbx, [rsp+58h+arg_0]
0x1800108c6  add     rsp, 40h
0x1800108ca  pop     r14
0x1800108cc  pop     rdi
0x1800108cd  pop     rsi
0x1800108ce  retn
```
