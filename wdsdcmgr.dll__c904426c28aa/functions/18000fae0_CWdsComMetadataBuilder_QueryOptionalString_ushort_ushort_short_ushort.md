# CWdsComMetadataBuilder::QueryOptionalString(ushort *,ushort *,short *,ushort * *)

- ea: `0x18000fae0`
- end: `0x18000fcaf`
- name: `?QueryOptionalString@CWdsComMetadataBuilder@@UEAAJPEAG0PEAFPEAPEAG@Z`
- size: `463`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int16 *, __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000af78`
- `0x18000e3e4`
- `0x18000fae0`
- `0x18001381c`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000fc77`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc77`

## string_xrefs

- `0x18000fb45`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000fb80`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryOptionalString(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int16 *a4,
        unsigned __int16 **a5)
{
  int v6; // esi
  const char *v10; // rdx
  unsigned int v11; // ebx
  signed int v12; // edi
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  unsigned __int16 *v16; // rbx
  const char *v17; // rdx
  OLECHAR *v18; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  int v21; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v22; // [rsp+40h] [rbp-30h]
  __int64 v23; // [rsp+48h] [rbp-28h]
  int v24; // [rsp+50h] [rbp-20h] BYREF
  __int64 v25; // [rsp+58h] [rbp-18h]
  __int64 v26; // [rsp+60h] [rbp-10h]

  v24 = 0;
  v25 = 0;
  v26 = 0;
  v6 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  bstrString = 0;
  if ( !(unsigned int)ValidateNonEmptyBstr(a2) || !a5 )
  {
    v11 = -2147024809;
    if ( (int)ElValidateHr(-2147024809, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x534u) < 0 )
      goto LABEL_23;
  }
  v12 = CWdsMetadata::QueryOptional((char *)this + 64, a2, 1, &v21, &v24);
  if ( ElValidateWin32(v12, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x538u) )
  {
LABEL_5:
    v11 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 <= 0 )
      v11 = v12;
    goto LABEL_23;
  }
  if ( v21 )
  {
    v16 = 0;
    v12 = 0;
    if ( v21 == 1 )
      v16 = v22;
    else
      v12 = ElValidateWin32(0xDu, v14, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x60Fu);
    if ( ElValidateWin32(v12, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x548u) )
      goto LABEL_5;
    v11 = SysAllocStringHr(v16, &bstrString);
    if ( (int)ElValidateHr(v11, v17, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x54Bu) >= 0 )
      goto LABEL_18;
  }
  else
  {
    if ( !a3 )
      a3 = (unsigned __int16 *)&word_18001870C;
    v11 = SysAllocStringHr(a3, &bstrString);
    if ( (int)ElValidateHr(v11, v15, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x53Du) >= 0 )
    {
      v6 = 1;
LABEL_18:
      v18 = 0;
      *a5 = bstrString;
      if ( !a4 )
        goto LABEL_23;
      *a4 = -(v6 != 0);
      goto LABEL_21;
    }
  }
  v18 = bstrString;
LABEL_21:
  if ( v18 )
    SysFreeString(v18);
LABEL_23:
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v21);
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v24);
  return v11;
}

```

## disassembly

```asm
0x18000fae0  mov     [rsp-28h+arg_0], rbx
0x18000fae5  mov     [rsp-28h+arg_8], rsi
0x18000faea  mov     [rsp-28h+arg_10], rdi
0x18000faef  push    rbp
0x18000faf0  push    r12
0x18000faf2  push    r13
0x18000faf4  push    r14
0x18000faf6  push    r15
0x18000faf8  mov     rbp, rsp
0x18000fafb  sub     rsp, 70h
0x18000faff  xor     eax, eax
0x18000fb01  xor     ebx, ebx
0x18000fb03  mov     r13, rcx
0x18000fb06  mov     [rbp+var_20], ebx
0x18000fb09  mov     rcx, rdx; pbstr
0x18000fb0c  mov     [rbp+var_18], rax
0x18000fb10  mov     [rbp+var_10], rax
0x18000fb14  mov     esi, ebx
0x18000fb16  mov     [rbp+var_38], ebx
0x18000fb19  mov     r15, r9
0x18000fb1c  mov     [rbp+var_30], rax
0x18000fb20  mov     r14, r8
0x18000fb23  mov     [rbp+var_28], rax
0x18000fb27  mov     rdi, rdx
0x18000fb2a  mov     [rbp+bstrString], rbx
0x18000fb2e  call    ValidateNonEmptyBstr
0x18000fb33  mov     r12, [rbp+arg_20]
0x18000fb37  test    eax, eax
0x18000fb39  jz      short loc_18000FB40
0x18000fb3b  test    r12, r12
0x18000fb3e  jnz     short loc_18000FB61
0x18000fb40  mov     ebx, 80070057h
0x18000fb45  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fb4c  mov     ecx, ebx; int
0x18000fb4e  mov     r9d, 534h; unsigned int
0x18000fb54  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000fb59  test    eax, eax
0x18000fb5b  js      loc_18000FC7D
0x18000fb61  lea     rax, [rbp+var_20]
0x18000fb65  mov     r8d, 1
0x18000fb6b  lea     rcx, [r13+40h]
0x18000fb6f  mov     [rsp+70h+var_50], rax
0x18000fb74  lea     r9, [rbp+var_38]
0x18000fb78  mov     rdx, rdi
0x18000fb7b  call    ?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z; CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)
0x18000fb80  lea     r13, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fb87  mov     r9d, 538h; unsigned int
0x18000fb8d  mov     r8, r13; char *
0x18000fb90  mov     ecx, eax; unsigned int
0x18000fb92  mov     edi, eax
0x18000fb94  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000fb99  test    eax, eax
0x18000fb9b  jz      short loc_18000FBB0
0x18000fb9d  movzx   ebx, di
0x18000fba0  or      ebx, 80070000h
0x18000fba6  test    edi, edi
0x18000fba8  cmovle  ebx, edi
0x18000fbab  jmp     loc_18000FC7D
0x18000fbb0  mov     eax, [rbp+var_38]
0x18000fbb3  test    eax, eax
0x18000fbb5  jnz     short loc_18000FBF2
0x18000fbb7  lea     rax, word_18001870C
0x18000fbbe  test    r14, r14
0x18000fbc1  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x18000fbc5  cmovz   r14, rax
0x18000fbc9  mov     rcx, r14; unsigned __int16 *
0x18000fbcc  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x18000fbd1  mov     r9d, 53Dh; unsigned int
0x18000fbd7  mov     r8, r13; char *
0x18000fbda  mov     ecx, eax; int
0x18000fbdc  mov     ebx, eax
0x18000fbde  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000fbe3  test    eax, eax
0x18000fbe5  js      loc_18000FC6E
0x18000fbeb  mov     esi, 1
0x18000fbf0  jmp     short loc_18000FC54
0x18000fbf2  xor     ebx, ebx
0x18000fbf4  xor     edi, edi
0x18000fbf6  cmp     eax, 1
0x18000fbf9  jnz     short loc_18000FC01
0x18000fbfb  mov     rbx, [rbp+var_30]
0x18000fbff  jmp     short loc_18000FC1A
0x18000fc01  mov     r9d, 60Fh; unsigned int
0x18000fc07  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000fc0e  mov     ecx, 0Dh; unsigned int
0x18000fc13  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000fc18  mov     edi, eax
0x18000fc1a  mov     r9d, 548h; unsigned int
0x18000fc20  mov     r8, r13; char *
0x18000fc23  mov     ecx, edi; unsigned int
0x18000fc25  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000fc2a  test    eax, eax
0x18000fc2c  jnz     loc_18000FB9D
0x18000fc32  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x18000fc36  mov     rcx, rbx; unsigned __int16 *
0x18000fc39  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x18000fc3e  mov     r9d, 54Bh; unsigned int
0x18000fc44  mov     r8, r13; char *
0x18000fc47  mov     ecx, eax; int
0x18000fc49  mov     ebx, eax
0x18000fc4b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000fc50  test    eax, eax
0x18000fc52  js      short loc_18000FC6E
0x18000fc54  mov     rax, [rbp+bstrString]
0x18000fc58  xor     ecx, ecx
0x18000fc5a  mov     [r12], rax
0x18000fc5e  test    r15, r15
0x18000fc61  jz      short loc_18000FC7D
0x18000fc63  neg     esi
0x18000fc65  sbb     ax, ax
0x18000fc68  mov     [r15], ax
0x18000fc6c  jmp     short loc_18000FC72
0x18000fc6e  mov     rcx, [rbp+bstrString]; bstrString
0x18000fc72  test    rcx, rcx
0x18000fc75  jz      short loc_18000FC7D
0x18000fc77  call    cs:__imp_SysFreeString
0x18000fc7d  lea     rcx, [rbp+var_38]; this
0x18000fc81  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000fc86  lea     rcx, [rbp+var_20]; this
0x18000fc8a  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000fc8f  lea     r11, [rsp+70h+var_s0]
0x18000fc94  mov     eax, ebx
0x18000fc96  mov     rbx, [r11+30h]
0x18000fc9a  mov     rsi, [r11+38h]
0x18000fc9e  mov     rdi, [r11+40h]
0x18000fca2  mov     rsp, r11
0x18000fca5  pop     r15
0x18000fca7  pop     r14
0x18000fca9  pop     r13
0x18000fcab  pop     r12
0x18000fcad  pop     rbp
0x18000fcae  retn
```
