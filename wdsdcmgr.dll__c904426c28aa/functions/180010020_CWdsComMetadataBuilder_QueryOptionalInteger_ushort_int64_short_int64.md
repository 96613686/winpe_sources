# CWdsComMetadataBuilder::QueryOptionalInteger(ushort *,__int64,short *,__int64 *)

- ea: `0x180010020`
- end: `0x180010177`
- name: `?QueryOptionalInteger@CWdsComMetadataBuilder@@UEAAJPEAG_JPEAFPEA_J@Z`
- size: `343`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, __int64, __int16 *, __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000af78`
- `0x18000e3e4`
- `0x180010020`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x180010081`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x1800100c2`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010121`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryOptionalInteger(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        __int64 a3,
        __int16 *a4,
        __int64 *a5)
{
  unsigned int v6; // ebx
  int v10; // esi
  const char *v11; // rdx
  signed int v12; // edi
  const char *v13; // rdx
  const char *v14; // rdx
  int v16; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-28h]
  __int64 v18; // [rsp+40h] [rbp-20h]
  int v19; // [rsp+48h] [rbp-18h] BYREF
  __int64 v20; // [rsp+50h] [rbp-10h]
  __int64 v21; // [rsp+58h] [rbp-8h]

  v16 = 0;
  v6 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v17 = 0;
  v18 = 0;
  v10 = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a5
    || (v6 = -2147024809,
        (int)ElValidateHr(-2147024809, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x632u) >= 0) )
  {
    v12 = CWdsMetadata::QueryOptional((char *)this + 64, a2, 4, &v16, &v19);
    if ( ElValidateWin32(v12, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x636u) )
    {
LABEL_5:
      v6 = (unsigned __int16)v12 | 0x80070000;
      if ( v12 <= 0 )
        v6 = v12;
      goto LABEL_16;
    }
    if ( v16 )
    {
      a3 = 0;
      v12 = 0;
      if ( v16 == 4 )
        a3 = v17;
      else
        v12 = ElValidateWin32(0xDu, v14, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x657u);
      if ( ElValidateWin32(v12, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x642u) )
        goto LABEL_5;
    }
    else
    {
      v10 = 1;
    }
    *a5 = a3;
    if ( a4 )
      *a4 = -(v10 != 0);
  }
LABEL_16:
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v16);
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v19);
  return v6;
}

```

## disassembly

```asm
0x180010020  mov     [rsp-28h+arg_0], rbx
0x180010025  mov     [rsp-28h+arg_8], rsi
0x18001002a  mov     [rsp-28h+arg_10], rdi
0x18001002f  push    rbp
0x180010030  push    r12
0x180010032  push    r13
0x180010034  push    r14
0x180010036  push    r15
0x180010038  mov     rbp, rsp
0x18001003b  sub     rsp, 60h
0x18001003f  xor     eax, eax
0x180010041  mov     r13, rcx
0x180010044  and     [rbp+var_30], eax
0x180010047  xor     ebx, ebx
0x180010049  and     [rbp+var_18], ebx
0x18001004c  mov     rcx, rdx; pbstr
0x18001004f  mov     [rbp+var_10], rax
0x180010053  mov     r15, r9
0x180010056  mov     [rbp+var_8], rax
0x18001005a  mov     r14, r8
0x18001005d  mov     [rbp+var_28], rax
0x180010061  mov     rdi, rdx
0x180010064  mov     [rbp+var_20], rax
0x180010068  xor     esi, esi
0x18001006a  call    ValidateNonEmptyBstr
0x18001006f  mov     r12, [rbp+arg_20]
0x180010073  test    eax, eax
0x180010075  jz      short loc_18001007C
0x180010077  test    r12, r12
0x18001007a  jnz     short loc_18001009D
0x18001007c  mov     ebx, 80070057h
0x180010081  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010088  mov     ecx, ebx; int
0x18001008a  mov     r9d, 632h; unsigned int
0x180010090  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010095  test    eax, eax
0x180010097  js      loc_180010145
0x18001009d  lea     rax, [rbp+var_18]
0x1800100a1  mov     r8d, 4
0x1800100a7  lea     rcx, [r13+40h]
0x1800100ab  mov     [rsp+60h+var_40], rax
0x1800100b0  lea     r9, [rbp+var_30]
0x1800100b4  mov     rdx, rdi
0x1800100b7  call    ?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z; CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)
0x1800100bc  mov     r9d, 636h; unsigned int
0x1800100c2  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800100c9  mov     ecx, eax; unsigned int
0x1800100cb  mov     edi, eax
0x1800100cd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800100d2  test    eax, eax
0x1800100d4  jz      short loc_1800100E6
0x1800100d6  movzx   ebx, di
0x1800100d9  or      ebx, 80070000h
0x1800100df  test    edi, edi
0x1800100e1  cmovle  ebx, edi
0x1800100e4  jmp     short loc_180010145
0x1800100e6  mov     eax, [rbp+var_30]
0x1800100e9  test    eax, eax
0x1800100eb  jnz     short loc_1800100F2
0x1800100ed  lea     esi, [rax+1]
0x1800100f0  jmp     short loc_180010133
0x1800100f2  xor     r14d, r14d
0x1800100f5  xor     edi, edi
0x1800100f7  cmp     eax, 4
0x1800100fa  jnz     short loc_180010102
0x1800100fc  mov     r14, [rbp+var_28]
0x180010100  jmp     short loc_18001011B
0x180010102  mov     r9d, 657h; unsigned int
0x180010108  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18001010f  mov     ecx, 0Dh; unsigned int
0x180010114  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010119  mov     edi, eax
0x18001011b  mov     r9d, 642h; unsigned int
0x180010121  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010128  mov     ecx, edi; unsigned int
0x18001012a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001012f  test    eax, eax
0x180010131  jnz     short loc_1800100D6
0x180010133  mov     [r12], r14
0x180010137  test    r15, r15
0x18001013a  jz      short loc_180010145
0x18001013c  neg     esi
0x18001013e  sbb     cx, cx
0x180010141  mov     [r15], cx
0x180010145  lea     rcx, [rbp+var_30]; this
0x180010149  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18001014e  lea     rcx, [rbp+var_18]; this
0x180010152  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180010157  lea     r11, [rsp+60h+var_s0]
0x18001015c  mov     eax, ebx
0x18001015e  mov     rbx, [r11+30h]
0x180010162  mov     rsi, [r11+38h]
0x180010166  mov     rdi, [r11+40h]
0x18001016a  mov     rsp, r11
0x18001016d  pop     r15
0x18001016f  pop     r14
0x180010171  pop     r13
0x180010173  pop     r12
0x180010175  pop     rbp
0x180010176  retn
```
