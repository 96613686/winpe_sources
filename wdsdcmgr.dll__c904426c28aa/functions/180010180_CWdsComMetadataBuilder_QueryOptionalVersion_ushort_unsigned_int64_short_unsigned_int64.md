# CWdsComMetadataBuilder::QueryOptionalVersion(ushort *,unsigned __int64,short *,unsigned __int64 *)

- ea: `0x180010180`
- end: `0x1800102d7`
- name: `?QueryOptionalVersion@CWdsComMetadataBuilder@@UEAAJPEAG_KPEAFPEA_K@Z`
- size: `343`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int64, __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000af78`
- `0x18000e3e4`
- `0x180010180`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x1800101e1`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010222`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010281`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryOptionalVersion(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        __int16 *a4,
        unsigned __int64 *a5)
{
  unsigned int v6; // ebx
  int v10; // esi
  const char *v11; // rdx
  signed int v12; // edi
  const char *v13; // rdx
  const char *v14; // rdx
  int v16; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-28h]
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
        (int)ElValidateHr(-2147024809, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x681u) >= 0) )
  {
    v12 = CWdsMetadata::QueryOptional((char *)this + 64, a2, 5, &v16, &v19);
    if ( ElValidateWin32(v12, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x685u) )
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
      if ( v16 == 5 )
        a3 = v17;
      else
        v12 = ElValidateWin32(0xDu, v14, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x67Bu);
      if ( ElValidateWin32(v12, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x691u) )
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
0x180010180  mov     [rsp-28h+arg_0], rbx
0x180010185  mov     [rsp-28h+arg_8], rsi
0x18001018a  mov     [rsp-28h+arg_10], rdi
0x18001018f  push    rbp
0x180010190  push    r12
0x180010192  push    r13
0x180010194  push    r14
0x180010196  push    r15
0x180010198  mov     rbp, rsp
0x18001019b  sub     rsp, 60h
0x18001019f  xor     eax, eax
0x1800101a1  mov     r13, rcx
0x1800101a4  and     [rbp+var_30], eax
0x1800101a7  xor     ebx, ebx
0x1800101a9  and     [rbp+var_18], ebx
0x1800101ac  mov     rcx, rdx; pbstr
0x1800101af  mov     [rbp+var_10], rax
0x1800101b3  mov     r15, r9
0x1800101b6  mov     [rbp+var_8], rax
0x1800101ba  mov     r14, r8
0x1800101bd  mov     [rbp+var_28], rax
0x1800101c1  mov     rdi, rdx
0x1800101c4  mov     [rbp+var_20], rax
0x1800101c8  xor     esi, esi
0x1800101ca  call    ValidateNonEmptyBstr
0x1800101cf  mov     r12, [rbp+arg_20]
0x1800101d3  test    eax, eax
0x1800101d5  jz      short loc_1800101DC
0x1800101d7  test    r12, r12
0x1800101da  jnz     short loc_1800101FD
0x1800101dc  mov     ebx, 80070057h
0x1800101e1  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800101e8  mov     ecx, ebx; int
0x1800101ea  mov     r9d, 681h; unsigned int
0x1800101f0  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800101f5  test    eax, eax
0x1800101f7  js      loc_1800102A5
0x1800101fd  lea     rax, [rbp+var_18]
0x180010201  mov     r8d, 5
0x180010207  lea     rcx, [r13+40h]
0x18001020b  mov     [rsp+60h+var_40], rax
0x180010210  lea     r9, [rbp+var_30]
0x180010214  mov     rdx, rdi
0x180010217  call    ?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z; CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)
0x18001021c  mov     r9d, 685h; unsigned int
0x180010222  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010229  mov     ecx, eax; unsigned int
0x18001022b  mov     edi, eax
0x18001022d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010232  test    eax, eax
0x180010234  jz      short loc_180010246
0x180010236  movzx   ebx, di
0x180010239  or      ebx, 80070000h
0x18001023f  test    edi, edi
0x180010241  cmovle  ebx, edi
0x180010244  jmp     short loc_1800102A5
0x180010246  mov     eax, [rbp+var_30]
0x180010249  test    eax, eax
0x18001024b  jnz     short loc_180010252
0x18001024d  lea     esi, [rax+1]
0x180010250  jmp     short loc_180010293
0x180010252  xor     r14d, r14d
0x180010255  xor     edi, edi
0x180010257  cmp     eax, 5
0x18001025a  jnz     short loc_180010262
0x18001025c  mov     r14, [rbp+var_28]
0x180010260  jmp     short loc_18001027B
0x180010262  mov     r9d, 67Bh; unsigned int
0x180010268  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18001026f  mov     ecx, 0Dh; unsigned int
0x180010274  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010279  mov     edi, eax
0x18001027b  mov     r9d, 691h; unsigned int
0x180010281  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010288  mov     ecx, edi; unsigned int
0x18001028a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001028f  test    eax, eax
0x180010291  jnz     short loc_180010236
0x180010293  mov     [r12], r14
0x180010297  test    r15, r15
0x18001029a  jz      short loc_1800102A5
0x18001029c  neg     esi
0x18001029e  sbb     cx, cx
0x1800102a1  mov     [r15], cx
0x1800102a5  lea     rcx, [rbp+var_30]; this
0x1800102a9  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x1800102ae  lea     rcx, [rbp+var_18]; this
0x1800102b2  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x1800102b7  lea     r11, [rsp+60h+var_s0]
0x1800102bc  mov     eax, ebx
0x1800102be  mov     rbx, [r11+30h]
0x1800102c2  mov     rsi, [r11+38h]
0x1800102c6  mov     rdi, [r11+40h]
0x1800102ca  mov     rsp, r11
0x1800102cd  pop     r15
0x1800102cf  pop     r14
0x1800102d1  pop     r13
0x1800102d3  pop     r12
0x1800102d5  pop     rbp
0x1800102d6  retn
```
