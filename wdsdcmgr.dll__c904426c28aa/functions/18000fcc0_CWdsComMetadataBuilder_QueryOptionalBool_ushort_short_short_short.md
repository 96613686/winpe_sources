# CWdsComMetadataBuilder::QueryOptionalBool(ushort *,short,short *,short *)

- ea: `0x18000fcc0`
- end: `0x18000fe2d`
- name: `?QueryOptionalBool@CWdsComMetadataBuilder@@UEAAJPEAGFPEAF1@Z`
- size: `365`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, __int16, __int16 *, __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009838`
- `0x18000af78`
- `0x18000e3e4`
- `0x18000fcc0`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x18000fd26`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000fd6b`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000fdd0`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryOptionalBool(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        __int16 a3,
        __int16 *a4,
        __int16 *a5)
{
  unsigned int v5; // ebx
  int v9; // esi
  int v10; // r14d
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

  v5 = 0;
  v19 = 0;
  v16 = 0;
  v20 = 0;
  v21 = 0;
  v17 = 0;
  v9 = 0;
  v18 = 0;
  v10 = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a5
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x58Cu) >= 0) )
  {
    v12 = CWdsMetadata::QueryOptional((char *)this + 64, a2, 2, &v16, &v19);
    if ( ElValidateWin32(v12, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x593u) )
    {
LABEL_5:
      v5 = (unsigned __int16)v12 | 0x80070000;
      if ( v12 <= 0 )
        v5 = v12;
      goto LABEL_16;
    }
    if ( v16 )
    {
      v12 = 0;
      if ( v16 == 2 )
        v9 = v17;
      else
        v12 = ElValidateWin32(0xDu, v14, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x633u);
      if ( ElValidateWin32(v12, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x59Du) )
        goto LABEL_5;
    }
    else
    {
      v10 = 1;
      LOBYTE(v9) = a3 == -1;
    }
    *a5 = -(v9 != 0);
    if ( a4 )
      *a4 = -(v10 != 0);
  }
LABEL_16:
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v16);
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v19);
  return v5;
}

```

## disassembly

```asm
0x18000fcc0  mov     rax, rsp
0x18000fcc3  mov     [rax+10h], rbx
0x18000fcc7  mov     [rax+18h], rsi
0x18000fccb  mov     [rax+20h], rdi
0x18000fccf  mov     [rax+8], rcx
0x18000fcd3  push    rbp
0x18000fcd4  push    r12
0x18000fcd6  push    r13
0x18000fcd8  push    r14
0x18000fcda  push    r15
0x18000fcdc  mov     rbp, rsp
0x18000fcdf  sub     rsp, 60h
0x18000fce3  xor     eax, eax
0x18000fce5  xor     ebx, ebx
0x18000fce7  and     [rbp+var_18], ebx
0x18000fcea  mov     rcx, rdx; pbstr
0x18000fced  and     [rbp+var_30], eax
0x18000fcf0  mov     r15, r9
0x18000fcf3  mov     [rbp+var_10], rax
0x18000fcf7  movzx   r13d, r8w
0x18000fcfb  mov     [rbp+var_8], rax
0x18000fcff  mov     rdi, rdx
0x18000fd02  mov     [rbp+var_28], rax
0x18000fd06  xor     esi, esi
0x18000fd08  mov     [rbp+var_20], rax
0x18000fd0c  xor     r14d, r14d
0x18000fd0f  call    ValidateNonEmptyBstr
0x18000fd14  mov     r12, [rbp+arg_20]
0x18000fd18  test    eax, eax
0x18000fd1a  jz      short loc_18000FD21
0x18000fd1c  test    r12, r12
0x18000fd1f  jnz     short loc_18000FD42
0x18000fd21  mov     ebx, 80070057h
0x18000fd26  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fd2d  mov     ecx, ebx; int
0x18000fd2f  mov     r9d, 58Ch; unsigned int
0x18000fd35  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000fd3a  test    eax, eax
0x18000fd3c  js      loc_18000FDFB
0x18000fd42  mov     rcx, [rbp+arg_0]
0x18000fd46  lea     rax, [rbp+var_18]
0x18000fd4a  add     rcx, 40h ; '@'
0x18000fd4e  mov     [rsp+60h+var_40], rax
0x18000fd53  lea     r9, [rbp+var_30]
0x18000fd57  mov     r8d, 2
0x18000fd5d  mov     rdx, rdi
0x18000fd60  call    ?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z; CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)
0x18000fd65  mov     r9d, 593h; unsigned int
0x18000fd6b  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fd72  mov     ecx, eax; unsigned int
0x18000fd74  mov     edi, eax
0x18000fd76  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000fd7b  test    eax, eax
0x18000fd7d  jz      short loc_18000FD8F
0x18000fd7f  movzx   ebx, di
0x18000fd82  or      ebx, 80070000h
0x18000fd88  test    edi, edi
0x18000fd8a  cmovle  ebx, edi
0x18000fd8d  jmp     short loc_18000FDFB
0x18000fd8f  mov     eax, [rbp+var_30]
0x18000fd92  test    eax, eax
0x18000fd94  jnz     short loc_18000FDA5
0x18000fd96  cmp     r13w, 0FFFFh
0x18000fd9b  lea     r14d, [rax+1]
0x18000fd9f  setz    sil
0x18000fda3  jmp     short loc_18000FDE2
0x18000fda5  xor     edi, edi
0x18000fda7  cmp     eax, 2
0x18000fdaa  jnz     short loc_18000FDB1
0x18000fdac  mov     esi, dword ptr [rbp+var_28]
0x18000fdaf  jmp     short loc_18000FDCA
0x18000fdb1  mov     r9d, 633h; unsigned int
0x18000fdb7  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000fdbe  mov     ecx, 0Dh; unsigned int
0x18000fdc3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000fdc8  mov     edi, eax
0x18000fdca  mov     r9d, 59Dh; unsigned int
0x18000fdd0  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000fdd7  mov     ecx, edi; unsigned int
0x18000fdd9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000fdde  test    eax, eax
0x18000fde0  jnz     short loc_18000FD7F
0x18000fde2  neg     esi
0x18000fde4  sbb     cx, cx
0x18000fde7  mov     [r12], cx
0x18000fdec  test    r15, r15
0x18000fdef  jz      short loc_18000FDFB
0x18000fdf1  neg     r14d
0x18000fdf4  sbb     cx, cx
0x18000fdf7  mov     [r15], cx
0x18000fdfb  lea     rcx, [rbp+var_30]; this
0x18000fdff  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000fe04  lea     rcx, [rbp+var_18]; this
0x18000fe08  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000fe0d  lea     r11, [rsp+60h+var_s0]
0x18000fe12  mov     eax, ebx
0x18000fe14  mov     rbx, [r11+38h]
0x18000fe18  mov     rsi, [r11+40h]
0x18000fe1c  mov     rdi, [r11+48h]
0x18000fe20  mov     rsp, r11
0x18000fe23  pop     r15
0x18000fe25  pop     r14
0x18000fe27  pop     r13
0x18000fe29  pop     r12
0x18000fe2b  pop     rbp
0x18000fe2c  retn
```
