# CWdsComMetadataEntry::get_StringValue(ushort * *)

- ea: `0x180011c40`
- end: `0x180011d25`
- name: `?get_StringValue@CWdsComMetadataEntry@@UEAAJPEAPEAG@Z`
- size: `229`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180011c40`
- `0x18001381c`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011d0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d0a`

## string_xrefs

- `0x180011c69`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011cb2`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011ce7`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_StringValue(CWdsComMetadataEntry *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // rbp
  unsigned int v5; // ebx
  signed int v6; // edi
  const char *v7; // rdx
  int v8; // eax
  unsigned __int16 *v9; // rcx
  unsigned __int16 *v11; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v11 = 0;
  if ( a2
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x192u) >= 0) )
  {
    v6 = 0;
    if ( *((_DWORD *)this + 26) == 1 )
      v2 = (const unsigned __int16 *)*((_QWORD *)this + 14);
    else
      v6 = ElValidateWin32(0xDu, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x60Fu);
    if ( ElValidateWin32(v6, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x196u) )
    {
      v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        return (unsigned int)v6;
    }
    else
    {
      v5 = SysAllocStringHr(v2, &v11);
      v8 = ElValidateHr(v5, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x199u);
      v9 = v11;
      if ( v8 >= 0 )
      {
        *a2 = v11;
        v9 = 0;
      }
      if ( v9 )
        SysFreeString(v9);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180011c40  mov     [rsp+arg_0], rbx
0x180011c45  mov     [rsp+arg_10], rbp
0x180011c4a  push    rsi
0x180011c4b  push    rdi
0x180011c4c  push    r14
0x180011c4e  sub     rsp, 20h
0x180011c52  xor     ebp, ebp
0x180011c54  mov     r14, rdx
0x180011c57  and     [rsp+38h+arg_8], rbp
0x180011c5c  mov     rsi, rcx
0x180011c5f  test    rdx, rdx
0x180011c62  jnz     short loc_180011C85
0x180011c64  mov     ebx, 80070057h
0x180011c69  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011c70  mov     ecx, ebx; int
0x180011c72  mov     r9d, 192h; unsigned int
0x180011c78  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011c7d  test    eax, eax
0x180011c7f  js      loc_180011D10
0x180011c85  xor     edi, edi
0x180011c87  cmp     dword ptr [rsi+68h], 1
0x180011c8b  jnz     short loc_180011C93
0x180011c8d  mov     rbp, [rsi+70h]
0x180011c91  jmp     short loc_180011CAC
0x180011c93  mov     r9d, 60Fh; unsigned int
0x180011c99  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180011ca0  mov     ecx, 0Dh; unsigned int
0x180011ca5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011caa  mov     edi, eax
0x180011cac  mov     r9d, 196h; unsigned int
0x180011cb2  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011cb9  mov     ecx, edi; unsigned int
0x180011cbb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011cc0  test    eax, eax
0x180011cc2  jz      short loc_180011CD4
0x180011cc4  movzx   ebx, di
0x180011cc7  or      ebx, 80070000h
0x180011ccd  test    edi, edi
0x180011ccf  cmovle  ebx, edi
0x180011cd2  jmp     short loc_180011D10
0x180011cd4  lea     rdx, [rsp+38h+arg_8]; unsigned __int16 **
0x180011cd9  mov     rcx, rbp; unsigned __int16 *
0x180011cdc  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180011ce1  mov     r9d, 199h; unsigned int
0x180011ce7  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011cee  mov     ecx, eax; int
0x180011cf0  mov     ebx, eax
0x180011cf2  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011cf7  mov     rcx, [rsp+38h+arg_8]
0x180011cfc  test    eax, eax
0x180011cfe  js      short loc_180011D05
0x180011d00  mov     [r14], rcx
0x180011d03  xor     ecx, ecx; bstrString
0x180011d05  test    rcx, rcx
0x180011d08  jz      short loc_180011D10
0x180011d0a  call    cs:__imp_SysFreeString
0x180011d10  mov     rbp, [rsp+38h+arg_10]
0x180011d15  mov     eax, ebx
0x180011d17  mov     rbx, [rsp+38h+arg_0]
0x180011d1c  add     rsp, 20h
0x180011d20  pop     r14
0x180011d22  pop     rdi
0x180011d23  pop     rsi
0x180011d24  retn
```
