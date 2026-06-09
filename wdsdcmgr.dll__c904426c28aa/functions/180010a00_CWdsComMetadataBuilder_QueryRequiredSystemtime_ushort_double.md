# CWdsComMetadataBuilder::QueryRequiredSystemtime(ushort *,double *)

- ea: `0x180010a00`
- end: `0x180010b4c`
- name: `?QueryRequiredSystemtime@CWdsComMetadataBuilder@@UEAAJPEAGPEAN@Z`
- size: `332`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, double *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000b1a8`
- `0x18000e3e4`
- `0x180010a00`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180010b00`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180010b00`

## string_xrefs

- `0x180010a54`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010a8d`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010ae6`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010b0f`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryRequiredSystemtime(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        double *a3)
{
  unsigned int v6; // ebx
  const char *v7; // rdx
  signed int v8; // edi
  const char *v9; // rdx
  const char *v10; // rdx
  const char *v11; // rdx
  int v13; // [rsp+20h] [rbp-48h] BYREF
  struct _SYSTEMTIME v14; // [rsp+28h] [rbp-40h]
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-30h] BYREF

  v13 = 0;
  v14 = (struct _SYSTEMTIME)0LL;
  v6 = 0;
  *(_QWORD *)&SystemTime.wYear = 0;
  *(_QWORD *)&SystemTime.wHour = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3
    || (v6 = -2147024809,
        (int)ElValidateHr(-2147024809, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x7F5u) >= 0) )
  {
    v8 = CWdsMetadata::QueryRequired((char *)this + 64, a2, 3, &v13);
    if ( ElValidateWin32(v8, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x7F9u)
      || ((v8 = 0, v13 != 3)
        ? (v8 = ElValidateWin32(0xDu, v10, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x69Fu))
        : (SystemTime = v14),
          ElValidateWin32(v8, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x7FCu)) )
    {
      v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v6 = v8;
    }
    else if ( !SystemTimeToVariantTime(&SystemTime, a3) )
    {
      v6 = -2147467259;
      ElValidateHr(-2147467259, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x801u);
    }
  }
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v13);
  return v6;
}

```

## disassembly

```asm
0x180010a00  mov     r11, rsp
0x180010a03  mov     [r11+20h], rbx
0x180010a07  push    rbp
0x180010a08  push    rsi
0x180010a09  push    rdi
0x180010a0a  sub     rsp, 50h
0x180010a0e  mov     rax, cs:__security_cookie
0x180010a15  xor     rax, rsp
0x180010a18  mov     [rsp+68h+var_20], rax
0x180010a1d  xor     eax, eax
0x180010a1f  mov     rbp, rcx
0x180010a22  and     [rsp+68h+var_48], eax
0x180010a26  mov     rcx, rdx; pbstr
0x180010a29  mov     [r11-40h], rax
0x180010a2d  mov     rsi, r8
0x180010a30  mov     [r11-38h], rax
0x180010a34  mov     rdi, rdx
0x180010a37  xor     ebx, ebx
0x180010a39  mov     [r11-30h], rax
0x180010a3d  mov     [r11-28h], rax
0x180010a41  call    ValidateNonEmptyBstr
0x180010a46  test    eax, eax
0x180010a48  jz      short loc_180010A4F
0x180010a4a  test    rsi, rsi
0x180010a4d  jnz     short loc_180010A70
0x180010a4f  mov     ebx, 80070057h
0x180010a54  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010a5b  mov     ecx, ebx; int
0x180010a5d  mov     r9d, 7F5h; unsigned int
0x180010a63  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010a68  test    eax, eax
0x180010a6a  js      loc_180010B23
0x180010a70  lea     rcx, [rbp+40h]
0x180010a74  mov     r8d, 3
0x180010a7a  lea     r9, [rsp+68h+var_48]
0x180010a7f  mov     rdx, rdi
0x180010a82  call    ?QueryRequired@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@@Z; CWdsMetadata::QueryRequired(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *)
0x180010a87  mov     r9d, 7F9h; unsigned int
0x180010a8d  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010a94  mov     ecx, eax; unsigned int
0x180010a96  mov     edi, eax
0x180010a98  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010a9d  test    eax, eax
0x180010a9f  jz      short loc_180010AB1
0x180010aa1  movzx   ebx, di
0x180010aa4  or      ebx, 80070000h
0x180010aaa  test    edi, edi
0x180010aac  cmovle  ebx, edi
0x180010aaf  jmp     short loc_180010B23
0x180010ab1  xor     edi, edi
0x180010ab3  cmp     [rsp+68h+var_48], 3
0x180010ab8  jnz     short loc_180010AC7
0x180010aba  movups  xmm0, [rsp+68h+var_40]
0x180010abf  movdqu  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x180010ac5  jmp     short loc_180010AE0
0x180010ac7  mov     r9d, 69Fh; unsigned int
0x180010acd  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180010ad4  mov     ecx, 0Dh; unsigned int
0x180010ad9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010ade  mov     edi, eax
0x180010ae0  mov     r9d, 7FCh; unsigned int
0x180010ae6  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010aed  mov     ecx, edi; unsigned int
0x180010aef  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010af4  test    eax, eax
0x180010af6  jnz     short loc_180010AA1
0x180010af8  mov     rdx, rsi; pvtime
0x180010afb  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180010b00  call    cs:__imp_SystemTimeToVariantTime
0x180010b06  test    eax, eax
0x180010b08  jnz     short loc_180010B23
0x180010b0a  mov     ebx, 80004005h
0x180010b0f  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010b16  mov     ecx, ebx; int
0x180010b18  mov     r9d, 801h; unsigned int
0x180010b1e  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010b23  lea     rcx, [rsp+68h+var_48]; this
0x180010b28  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180010b2d  mov     eax, ebx
0x180010b2f  mov     rcx, [rsp+68h+var_20]
0x180010b34  xor     rcx, rsp; StackCookie
0x180010b37  call    __security_check_cookie
0x180010b3c  mov     rbx, [rsp+68h+arg_18]
0x180010b44  add     rsp, 50h
0x180010b48  pop     rdi
0x180010b49  pop     rsi
0x180010b4a  pop     rbp
0x180010b4b  retn
```
