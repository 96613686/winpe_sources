# CWdsComMetadataBuilder::QueryRequiredBinary(ushort *,uchar *,ulong,ulong *)

- ea: `0x180011000`
- end: `0x180011143`
- name: `?QueryRequiredBinary@CWdsComMetadataBuilder@@UEAAJPEAGPEAEKPEAK@Z`
- size: `323`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x180009c30`
- `0x18000b1a8`
- `0x18000e3e4`
- `0x180011000`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x18001105e`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180011097`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x1800110d6`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x1800110ef`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryRequiredBinary(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int *a5)
{
  size_t v7; // rsi
  const char *v9; // rdx
  unsigned int v10; // ebx
  signed int BinaryValue; // edi
  const char *v12; // rdx
  const char *v13; // rdx
  unsigned __int64 v14; // rax
  unsigned int v15; // ecx
  unsigned __int64 v17; // [rsp+20h] [rbp-38h] BYREF
  int v18; // [rsp+28h] [rbp-30h] BYREF
  __int64 v19; // [rsp+30h] [rbp-28h]
  __int64 v20; // [rsp+38h] [rbp-20h]

  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v7 = a4;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3 && (_DWORD)v7 && a5
    || (v10 = -2147024809,
        (int)ElValidateHr(-2147024809, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x8D9u) >= 0) )
  {
    BinaryValue = CWdsMetadata::QueryRequired((char *)this + 64, a2, 7, &v18);
    if ( ElValidateWin32(BinaryValue, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x8DDu)
      || (BinaryValue = CWdsMetadataValue::GetBinaryValue((CWdsMetadataValue *)&v18, a3, v7, &v17),
          ElValidateWin32(BinaryValue, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x8E0u)) )
    {
      v10 = (unsigned __int16)BinaryValue | 0x80070000;
      if ( BinaryValue <= 0 )
        v10 = BinaryValue;
    }
    else
    {
      v14 = v17;
      v15 = -1;
      if ( v17 <= 0xFFFFFFFF )
        v15 = v17;
      *a5 = v15;
      v10 = v14 > 0xFFFFFFFF ? 0x80070216 : 0;
      ElValidateHr(
        v10,
        (const char *)0xFFFFFFFFLL,
        "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp",
        0x8E3u);
    }
  }
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v18);
  return v10;
}

```

## disassembly

```asm
0x180011000  mov     r11, rsp
0x180011003  mov     [r11+8], rbx
0x180011007  mov     [r11+10h], rbp
0x18001100b  mov     [r11+18h], rsi
0x18001100f  push    rdi
0x180011010  push    r14
0x180011012  push    r15
0x180011014  sub     rsp, 40h
0x180011018  and     [rsp+58h+var_30], 0
0x18001101d  xor     eax, eax
0x18001101f  and     [r11-38h], rax
0x180011023  mov     r15, rcx
0x180011026  mov     rcx, rdx; pbstr
0x180011029  mov     [r11-28h], rax
0x18001102d  mov     [r11-20h], rax
0x180011031  mov     rbp, r8
0x180011034  mov     esi, r9d
0x180011037  mov     rdi, rdx
0x18001103a  call    ValidateNonEmptyBstr
0x18001103f  mov     r14, [rsp+58h+arg_20]
0x180011047  test    eax, eax
0x180011049  jz      short loc_180011059
0x18001104b  test    rbp, rbp
0x18001104e  jz      short loc_180011059
0x180011050  test    esi, esi
0x180011052  jz      short loc_180011059
0x180011054  test    r14, r14
0x180011057  jnz     short loc_18001107A
0x180011059  mov     ebx, 80070057h
0x18001105e  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011065  mov     ecx, ebx; int
0x180011067  mov     r9d, 8D9h; unsigned int
0x18001106d  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011072  test    eax, eax
0x180011074  js      loc_18001111E
0x18001107a  lea     rcx, [r15+40h]
0x18001107e  mov     r8d, 7
0x180011084  lea     r9, [rsp+58h+var_30]
0x180011089  mov     rdx, rdi
0x18001108c  call    ?QueryRequired@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@@Z; CWdsMetadata::QueryRequired(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *)
0x180011091  mov     r9d, 8DDh; unsigned int
0x180011097  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001109e  mov     ecx, eax; unsigned int
0x1800110a0  mov     edi, eax
0x1800110a2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800110a7  test    eax, eax
0x1800110a9  jz      short loc_1800110BB
0x1800110ab  movzx   ebx, di
0x1800110ae  or      ebx, 80070000h
0x1800110b4  test    edi, edi
0x1800110b6  cmovle  ebx, edi
0x1800110b9  jmp     short loc_18001111E
0x1800110bb  mov     r8, rsi; unsigned __int64
0x1800110be  lea     r9, [rsp+58h+var_38]; unsigned __int64 *
0x1800110c3  mov     rdx, rbp; unsigned __int8 *
0x1800110c6  lea     rcx, [rsp+58h+var_30]; this
0x1800110cb  call    ?GetBinaryValue@CWdsMetadataValue@@QEBAKPEAE_KPEA_K@Z; CWdsMetadataValue::GetBinaryValue(uchar *,unsigned __int64,unsigned __int64 *)
0x1800110d0  mov     r9d, 8E0h; unsigned int
0x1800110d6  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800110dd  mov     ecx, eax; unsigned int
0x1800110df  mov     edi, eax
0x1800110e1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800110e6  test    eax, eax
0x1800110e8  jnz     short loc_1800110AB
0x1800110ea  mov     rax, [rsp+58h+var_38]
0x1800110ef  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800110f6  mov     edx, 0FFFFFFFFh; char *
0x1800110fb  mov     r9d, 8E3h; unsigned int
0x180011101  cmp     rax, rdx
0x180011104  mov     ecx, edx
0x180011106  cmovbe  ecx, eax
0x180011109  cmp     rdx, rax
0x18001110c  mov     [r14], ecx
0x18001110f  sbb     ebx, ebx
0x180011111  and     ebx, 80070216h
0x180011117  mov     ecx, ebx; int
0x180011119  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001111e  lea     rcx, [rsp+58h+var_30]; this
0x180011123  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180011128  mov     rbp, [rsp+58h+arg_8]
0x18001112d  mov     eax, ebx
0x18001112f  mov     rbx, [rsp+58h+arg_0]
0x180011134  mov     rsi, [rsp+58h+arg_10]
0x180011139  add     rsp, 40h
0x18001113d  pop     r15
0x18001113f  pop     r14
0x180011141  pop     rdi
0x180011142  retn
```
