# CWdsComMetadataBuilder::QueryOptionalSystemtime(ushort *,double,short *,double *)

- ea: `0x18000fe40`
- end: `0x180010019`
- name: `?QueryOptionalSystemtime@CWdsComMetadataBuilder@@UEAAJPEAGNPEAFPEAN@Z`
- size: `473`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, double, __int16 *, double *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000af78`
- `0x18000e3e4`
- `0x18000fe40`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18000ffaa`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18000ffaa`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18000ff2a`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18000ff2a`

## string_xrefs

- `0x18000feb4`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000fef5`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000ff39`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000ff8d`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000ffb9`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryOptionalSystemtime(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        DOUBLE a3,
        __int16 *a4,
        double *pvtime)
{
  unsigned int v6; // ebx
  int v9; // esi
  const char *v10; // rdx
  signed int v11; // edi
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  int v17; // [rsp+38h] [rbp-41h] BYREF
  struct _SYSTEMTIME v18; // [rsp+40h] [rbp-39h]
  int v19; // [rsp+50h] [rbp-29h] BYREF
  __int64 v20; // [rsp+58h] [rbp-21h]
  __int64 v21; // [rsp+60h] [rbp-19h]
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-11h] BYREF

  v17 = 0;
  v6 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v18 = (struct _SYSTEMTIME)0LL;
  *(_QWORD *)&SystemTime.wYear = 0;
  v9 = 0;
  *(_QWORD *)&SystemTime.wHour = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && pvtime
    || (v6 = -2147024809,
        (int)ElValidateHr(-2147024809, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x5DAu) >= 0) )
  {
    v11 = CWdsMetadata::QueryOptional((char *)this + 64, a2, 3, &v17, &v19);
    if ( ElValidateWin32(v11, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x5E1u) )
    {
LABEL_5:
      v6 = (unsigned __int16)v11 | 0x80070000;
      if ( v11 <= 0 )
        v6 = v11;
      goto LABEL_20;
    }
    if ( v17 )
    {
      v11 = 0;
      if ( v17 == 3 )
        SystemTime = v18;
      else
        v11 = ElValidateWin32(0xDu, v13, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x69Fu);
      if ( ElValidateWin32(v11, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x5F0u) )
        goto LABEL_5;
    }
    else
    {
      if ( !VariantTimeToSystemTime(a3, &SystemTime) )
      {
        v6 = -2147467259;
        if ( (int)ElValidateHr(
                    -2147467259,
                    v14,
                    "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp",
                    0x5E8u) < 0 )
          goto LABEL_20;
      }
      v9 = 1;
    }
    if ( SystemTimeToVariantTime(&SystemTime, pvtime)
      || (v6 = -2147467259,
          (int)ElValidateHr(-2147467259, v15, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x5FAu) >= 0) )
    {
      if ( a4 )
        *a4 = -(v9 != 0);
    }
  }
LABEL_20:
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v17);
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v19);
  return v6;
}

```

## disassembly

```asm
0x18000fe40  mov     rax, rsp
0x18000fe43  push    rbp
0x18000fe44  push    rbx
0x18000fe45  push    rsi
0x18000fe46  push    rdi
0x18000fe47  push    r13
0x18000fe49  push    r14
0x18000fe4b  push    r15
0x18000fe4d  lea     rbp, [rax-57h]
0x18000fe51  sub     rsp, 90h
0x18000fe58  movaps  xmmword ptr [rax-48h], xmm6
0x18000fe5c  mov     rax, cs:__security_cookie
0x18000fe63  xor     rax, rsp
0x18000fe66  mov     [rbp+4Fh+var_50], rax
0x18000fe6a  mov     r15, [rbp+4Fh+pvtime]
0x18000fe6e  xor     eax, eax
0x18000fe70  and     [rbp+4Fh+var_90], eax
0x18000fe73  mov     r13, rcx
0x18000fe76  xor     ebx, ebx
0x18000fe78  mov     [rbp+4Fh+var_70], rax
0x18000fe7c  and     [rbp+4Fh+var_78], ebx
0x18000fe7f  mov     rcx, rdx; pbstr
0x18000fe82  mov     [rbp+4Fh+var_68], rax
0x18000fe86  mov     r14, r9
0x18000fe89  mov     qword ptr [rbp+4Fh+var_88], rax
0x18000fe8d  movaps  xmm6, xmm2
0x18000fe90  mov     qword ptr [rbp+4Fh+var_88+8], rax
0x18000fe94  mov     rdi, rdx
0x18000fe97  mov     qword ptr [rbp+4Fh+SystemTime.wYear], rax
0x18000fe9b  xor     esi, esi
0x18000fe9d  mov     qword ptr [rbp+4Fh+SystemTime.wHour], rax
0x18000fea1  call    ValidateNonEmptyBstr
0x18000fea6  test    eax, eax
0x18000fea8  jz      short loc_18000FEAF
0x18000feaa  test    r15, r15
0x18000fead  jnz     short loc_18000FED0
0x18000feaf  mov     ebx, 80070057h
0x18000feb4  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000febb  mov     ecx, ebx; int
0x18000febd  mov     r9d, 5DAh; unsigned int
0x18000fec3  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000fec8  test    eax, eax
0x18000feca  js      loc_18000FFDF
0x18000fed0  lea     rax, [rbp+4Fh+var_78]
0x18000fed4  mov     r8d, 3
0x18000feda  lea     rcx, [r13+40h]
0x18000fede  mov     [rsp+20h], rax
0x18000fee3  lea     r9, [rbp+4Fh+var_90]
0x18000fee7  mov     rdx, rdi
0x18000feea  call    ?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z; CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)
0x18000feef  mov     r9d, 5E1h; unsigned int
0x18000fef5  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fefc  mov     ecx, eax; unsigned int
0x18000fefe  mov     edi, eax
0x18000ff00  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ff05  test    eax, eax
0x18000ff07  jz      short loc_18000FF1C
0x18000ff09  movzx   ebx, di
0x18000ff0c  or      ebx, 80070000h
0x18000ff12  test    edi, edi
0x18000ff14  cmovle  ebx, edi
0x18000ff17  jmp     loc_18000FFDF
0x18000ff1c  mov     eax, [rbp+4Fh+var_90]
0x18000ff1f  test    eax, eax
0x18000ff21  jnz     short loc_18000FF5C
0x18000ff23  lea     rdx, [rbp+4Fh+SystemTime]; lpSystemTime
0x18000ff27  movaps  xmm0, xmm6; vtime
0x18000ff2a  call    cs:__imp_VariantTimeToSystemTime
0x18000ff30  test    eax, eax
0x18000ff32  jnz     short loc_18000FF55
0x18000ff34  mov     ebx, 80004005h
0x18000ff39  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ff40  mov     ecx, ebx; int
0x18000ff42  mov     r9d, 5E8h; unsigned int
0x18000ff48  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000ff4d  test    eax, eax
0x18000ff4f  js      loc_18000FFDF
0x18000ff55  mov     esi, 1
0x18000ff5a  jmp     short loc_18000FFA3
0x18000ff5c  xor     edi, edi
0x18000ff5e  cmp     eax, 3
0x18000ff61  jnz     short loc_18000FF6E
0x18000ff63  movups  xmm0, [rbp+4Fh+var_88]
0x18000ff67  movdqu  xmmword ptr [rbp+4Fh+SystemTime.wYear], xmm0
0x18000ff6c  jmp     short loc_18000FF87
0x18000ff6e  mov     r9d, 69Fh; unsigned int
0x18000ff74  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000ff7b  mov     ecx, 0Dh; unsigned int
0x18000ff80  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ff85  mov     edi, eax
0x18000ff87  mov     r9d, 5F0h; unsigned int
0x18000ff8d  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ff94  mov     ecx, edi; unsigned int
0x18000ff96  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ff9b  test    eax, eax
0x18000ff9d  jnz     loc_18000FF09
0x18000ffa3  mov     rdx, r15; pvtime
0x18000ffa6  lea     rcx, [rbp+4Fh+SystemTime]; lpSystemTime
0x18000ffaa  call    cs:__imp_SystemTimeToVariantTime
0x18000ffb0  test    eax, eax
0x18000ffb2  jnz     short loc_18000FFD1
0x18000ffb4  mov     ebx, 80004005h
0x18000ffb9  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ffc0  mov     ecx, ebx; int
0x18000ffc2  mov     r9d, 5FAh; unsigned int
0x18000ffc8  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000ffcd  test    eax, eax
0x18000ffcf  js      short loc_18000FFDF
0x18000ffd1  test    r14, r14
0x18000ffd4  jz      short loc_18000FFDF
0x18000ffd6  neg     esi
0x18000ffd8  sbb     cx, cx
0x18000ffdb  mov     [r14], cx
0x18000ffdf  lea     rcx, [rbp+4Fh+var_90]; this
0x18000ffe3  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000ffe8  lea     rcx, [rbp+4Fh+var_78]; this
0x18000ffec  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000fff1  mov     eax, ebx
0x18000fff3  mov     rcx, [rbp+4Fh+var_50]
0x18000fff7  xor     rcx, rsp; StackCookie
0x18000fffa  call    __security_check_cookie
0x18000ffff  movaps  xmm6, [rsp+0C0h+var_48+8]
0x180010007  add     rsp, 90h
0x18001000e  pop     r15
0x180010010  pop     r14
0x180010012  pop     r13
0x180010014  pop     rdi
0x180010015  pop     rsi
0x180010016  pop     rbx
0x180010017  pop     rbp
0x180010018  retn
```
