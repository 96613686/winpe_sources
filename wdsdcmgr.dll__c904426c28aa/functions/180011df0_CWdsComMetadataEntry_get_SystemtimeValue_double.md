# CWdsComMetadataEntry::get_SystemtimeValue(double *)

- ea: `0x180011df0`
- end: `0x180011efb`
- name: `?get_SystemtimeValue@CWdsComMetadataEntry@@UEAAJPEAN@Z`
- size: `267`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, double *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180011df0`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180011ead`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180011ead`

## string_xrefs

- `0x180011e32`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011e81`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011ebc`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_SystemtimeValue(CWdsComMetadataEntry *this, double *a2)
{
  unsigned int v2; // ebx
  signed int v5; // edi
  const char *v6; // rdx
  DOUBLE pvtime; // [rsp+20h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-30h] BYREF

  v2 = 0;
  *(_QWORD *)&SystemTime.wYear = 0;
  pvtime = 0.0;
  *(_QWORD *)&SystemTime.wHour = 0;
  if ( a2
    || (v2 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x1E9u) >= 0) )
  {
    v5 = 0;
    if ( *((_DWORD *)this + 26) == 3 )
      SystemTime = (struct _SYSTEMTIME)*((_OWORD *)this + 7);
    else
      v5 = ElValidateWin32(0xDu, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x69Fu);
    if ( ElValidateWin32(v5, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x1EDu) )
    {
      v2 = (unsigned __int16)v5 | 0x80070000;
      if ( v5 <= 0 )
        return (unsigned int)v5;
    }
    else if ( SystemTimeToVariantTime(&SystemTime, &pvtime)
           || (v2 = -2147418113,
               (int)ElValidateHr(-2147418113, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x1F2u) >= 0) )
    {
      *a2 = pvtime;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180011df0  mov     [rsp+arg_10], rbx
0x180011df5  push    rbp
0x180011df6  push    rsi
0x180011df7  push    rdi
0x180011df8  sub     rsp, 40h
0x180011dfc  mov     rax, cs:__security_cookie
0x180011e03  xor     rax, rsp
0x180011e06  mov     [rsp+58h+var_20], rax
0x180011e0b  xor     eax, eax
0x180011e0d  xor     ebx, ebx
0x180011e0f  mov     qword ptr [rsp+58h+SystemTime.wYear], rax
0x180011e14  xorps   xmm0, xmm0
0x180011e17  movsd   [rsp+58h+pvtime], xmm0
0x180011e1d  mov     rbp, rdx
0x180011e20  mov     qword ptr [rsp+58h+SystemTime.wHour], rax
0x180011e25  mov     rsi, rcx
0x180011e28  test    rdx, rdx
0x180011e2b  jnz     short loc_180011E4E
0x180011e2d  mov     ebx, 80070057h
0x180011e32  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011e39  mov     ecx, ebx; int
0x180011e3b  mov     r9d, 1E9h; unsigned int
0x180011e41  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011e46  test    eax, eax
0x180011e48  js      loc_180011EDF
0x180011e4e  xor     edi, edi
0x180011e50  cmp     dword ptr [rsi+68h], 3
0x180011e54  jnz     short loc_180011E62
0x180011e56  movups  xmm0, xmmword ptr [rsi+70h]
0x180011e5a  movdqu  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x180011e60  jmp     short loc_180011E7B
0x180011e62  mov     r9d, 69Fh; unsigned int
0x180011e68  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180011e6f  mov     ecx, 0Dh; unsigned int
0x180011e74  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011e79  mov     edi, eax
0x180011e7b  mov     r9d, 1EDh; unsigned int
0x180011e81  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011e88  mov     ecx, edi; unsigned int
0x180011e8a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011e8f  test    eax, eax
0x180011e91  jz      short loc_180011EA3
0x180011e93  movzx   ebx, di
0x180011e96  or      ebx, 80070000h
0x180011e9c  test    edi, edi
0x180011e9e  cmovle  ebx, edi
0x180011ea1  jmp     short loc_180011EDF
0x180011ea3  lea     rdx, [rsp+58h+pvtime]; pvtime
0x180011ea8  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180011ead  call    cs:__imp_SystemTimeToVariantTime
0x180011eb3  test    eax, eax
0x180011eb5  jnz     short loc_180011ED4
0x180011eb7  mov     ebx, 8000FFFFh
0x180011ebc  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011ec3  mov     ecx, ebx; int
0x180011ec5  mov     r9d, 1F2h; unsigned int
0x180011ecb  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011ed0  test    eax, eax
0x180011ed2  js      short loc_180011EDF
0x180011ed4  movsd   xmm0, [rsp+58h+pvtime]
0x180011eda  movsd   qword ptr [rbp+0], xmm0
0x180011edf  mov     eax, ebx
0x180011ee1  mov     rcx, [rsp+58h+var_20]
0x180011ee6  xor     rcx, rsp; StackCookie
0x180011ee9  call    __security_check_cookie
0x180011eee  mov     rbx, [rsp+58h+arg_10]
0x180011ef3  add     rsp, 40h
0x180011ef7  pop     rdi
0x180011ef8  pop     rsi
0x180011ef9  pop     rbp
0x180011efa  retn
```
