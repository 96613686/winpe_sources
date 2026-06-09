# CWdsComMetadataBuilder::QueryOptionalBinary(ushort *,uchar *,ulong,short *,uchar *,ulong,ulong *)

- ea: `0x1800105d0`
- end: `0x18001077d`
- name: `?QueryOptionalBinary@CWdsComMetadataBuilder@@UEAAJPEAGPEAEKPEAF1KPEAK@Z`
- size: `429`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int8 *, unsigned int, __int16 *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x180009c30`
- `0x18000af78`
- `0x18000e3e4`
- `0x1800105d0`
- `0x180014d58`
- `0x180014ee0`
- `0x180015c91`

## string_xrefs

- `0x180010658`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18001069e`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010703`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18001071d`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryOptionalBinary(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        __int16 *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8)
{
  size_t v8; // rsi
  unsigned int v10; // ebx
  const char *v11; // rdx
  signed int BinaryValue; // edi
  const char *v13; // rdx
  const char *v14; // rdx
  unsigned __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned __int64 v18; // [rsp+30h] [rbp-40h] BYREF
  int v19; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-30h]
  __int64 v21; // [rsp+48h] [rbp-28h]
  int v22; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+60h] [rbp-10h]

  v8 = a4;
  v20 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v10 = 0;
  v19 = 0;
  v22 = 0;
  v18 = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3 && (_DWORD)v8 && a6 && a7 && a8 && a5 && (unsigned int)v8 <= a7
    || (v10 = -2147024809,
        (int)ElValidateHr(-2147024809, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x741u) >= 0) )
  {
    BinaryValue = CWdsMetadata::QueryOptional((char *)this + 64, a2, 7, &v19, &v22);
    if ( ElValidateWin32(BinaryValue, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x745u) )
      goto LABEL_11;
    if ( !v19 )
    {
      memmove_0(a6, a3, v8);
      *a8 = v8;
      *a5 = -1;
      goto LABEL_21;
    }
    BinaryValue = CWdsMetadataValue::GetBinaryValue((CWdsMetadataValue *)&v19, a6, a7, &v18);
    if ( ElValidateWin32(BinaryValue, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x75Bu) )
    {
LABEL_11:
      v10 = (unsigned __int16)BinaryValue | 0x80070000;
      if ( BinaryValue <= 0 )
        v10 = BinaryValue;
    }
    else
    {
      v15 = v18;
      v16 = -1;
      if ( v18 <= 0xFFFFFFFF )
        v16 = v18;
      *a8 = v16;
      v10 = v15 > 0xFFFFFFFF ? 0x80070216 : 0;
      if ( (int)ElValidateHr(
                  v10,
                  (const char *)0xFFFFFFFFLL,
                  "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp",
                  0x75Eu) >= 0 )
        *a5 = 0;
    }
  }
LABEL_21:
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v22);
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v19);
  return v10;
}

```

## disassembly

```asm
0x1800105d0  mov     rax, rsp
0x1800105d3  mov     [rax+20h], rbx
0x1800105d7  mov     [rax+18h], r8
0x1800105db  mov     [rax+10h], rdx
0x1800105df  mov     [rax+8], rcx
0x1800105e3  push    rbp
0x1800105e4  push    rsi
0x1800105e5  push    rdi
0x1800105e6  push    r13
0x1800105e8  push    r14
0x1800105ea  mov     rbp, rsp
0x1800105ed  sub     rsp, 70h
0x1800105f1  xor     ecx, ecx
0x1800105f3  mov     esi, r9d
0x1800105f6  mov     rax, rdx
0x1800105f9  mov     [rbp+var_30], rcx
0x1800105fd  xor     edx, edx
0x1800105ff  mov     [rbp+var_28], rcx
0x180010603  mov     [rbp+var_18], rcx
0x180010607  mov     rdi, r8
0x18001060a  mov     [rbp+var_10], rcx
0x18001060e  mov     ebx, edx
0x180010610  mov     rcx, rax; pbstr
0x180010613  mov     [rbp+var_38], edx
0x180010616  mov     [rbp+var_20], edx
0x180010619  mov     [rbp+var_40], rdx
0x18001061d  call    ValidateNonEmptyBstr
0x180010622  mov     r13, [rbp+arg_38]
0x180010626  xor     ecx, ecx
0x180010628  mov     r14, [rbp+arg_20]
0x18001062c  test    eax, eax
0x18001062e  jz      short loc_180010653
0x180010630  test    rdi, rdi
0x180010633  jz      short loc_180010653
0x180010635  test    esi, esi
0x180010637  jz      short loc_180010653
0x180010639  cmp     [rbp+arg_28], rcx
0x18001063d  jz      short loc_180010653
0x18001063f  cmp     [rbp+arg_30], ecx
0x180010642  jz      short loc_180010653
0x180010644  test    r13, r13
0x180010647  jz      short loc_180010653
0x180010649  test    r14, r14
0x18001064c  jz      short loc_180010653
0x18001064e  cmp     esi, [rbp+arg_30]
0x180010651  jbe     short loc_180010674
0x180010653  mov     ebx, 80070057h
0x180010658  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001065f  mov     ecx, ebx; int
0x180010661  mov     r9d, 741h; unsigned int
0x180010667  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001066c  test    eax, eax
0x18001066e  js      loc_180010755
0x180010674  mov     rcx, [rbp+arg_0]
0x180010678  lea     rax, [rbp+var_20]
0x18001067c  mov     rdx, [rbp+arg_8]
0x180010680  lea     r9, [rbp+var_38]
0x180010684  add     rcx, 40h ; '@'
0x180010688  mov     [rsp+70h+var_50], rax
0x18001068d  mov     r8d, 7
0x180010693  call    ?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z; CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)
0x180010698  mov     r9d, 745h; unsigned int
0x18001069e  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800106a5  mov     ecx, eax; unsigned int
0x1800106a7  mov     edi, eax
0x1800106a9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800106ae  test    eax, eax
0x1800106b0  jz      short loc_1800106C5
0x1800106b2  movzx   ebx, di
0x1800106b5  or      ebx, 80070000h
0x1800106bb  test    edi, edi
0x1800106bd  cmovle  ebx, edi
0x1800106c0  jmp     loc_180010755
0x1800106c5  cmp     [rbp+var_38], 0
0x1800106c9  jnz     short loc_1800106E8
0x1800106cb  mov     rdx, [rbp+Src]; Src
0x1800106cf  mov     r8, rsi; Size
0x1800106d2  mov     rcx, [rbp+arg_28]; void *
0x1800106d6  call    memmove_0
0x1800106db  or      eax, 0FFFFFFFFh
0x1800106de  mov     [r13+0], esi
0x1800106e2  mov     [r14], ax
0x1800106e6  jmp     short loc_180010755
0x1800106e8  mov     r8d, [rbp+arg_30]; unsigned __int64
0x1800106ec  lea     r9, [rbp+var_40]; unsigned __int64 *
0x1800106f0  mov     rdx, [rbp+arg_28]; unsigned __int8 *
0x1800106f4  lea     rcx, [rbp+var_38]; this
0x1800106f8  call    ?GetBinaryValue@CWdsMetadataValue@@QEBAKPEAE_KPEA_K@Z; CWdsMetadataValue::GetBinaryValue(uchar *,unsigned __int64,unsigned __int64 *)
0x1800106fd  mov     r9d, 75Bh; unsigned int
0x180010703  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001070a  mov     ecx, eax; unsigned int
0x18001070c  mov     edi, eax
0x18001070e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010713  xor     esi, esi
0x180010715  test    eax, eax
0x180010717  jnz     short loc_1800106B2
0x180010719  mov     rax, [rbp+var_40]
0x18001071d  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010724  mov     edx, 0FFFFFFFFh; char *
0x180010729  mov     r9d, 75Eh; unsigned int
0x18001072f  cmp     rax, rdx
0x180010732  mov     ecx, edx
0x180010734  cmovbe  ecx, eax
0x180010737  cmp     rdx, rax
0x18001073a  mov     [r13+0], ecx
0x18001073e  sbb     ebx, ebx
0x180010740  and     ebx, 80070216h
0x180010746  mov     ecx, ebx; int
0x180010748  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001074d  test    eax, eax
0x18001074f  js      short loc_180010755
0x180010751  mov     [r14], si
0x180010755  lea     rcx, [rbp+var_20]; this
0x180010759  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18001075e  lea     rcx, [rbp+var_38]; this
0x180010762  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180010767  mov     eax, ebx
0x180010769  mov     rbx, [rsp+70h+arg_18]
0x180010771  add     rsp, 70h
0x180010775  pop     r14
0x180010777  pop     r13
0x180010779  pop     rdi
0x18001077a  pop     rsi
0x18001077b  pop     rbp
0x18001077c  retn
```
